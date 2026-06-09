# _anonymous_namespace_::CTracingSink::Initialize

- ea: `0x180035764`
- end: `0x1800358ec`
- name: `_anonymous_namespace_::CTracingSink::Initialize`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800358f4`

## callees

- `0x1800031d0`
- `0x18000aedc`
- `0x180035764`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180035884`
- `ntdll!RtlFreeHeap` at `0x180035884`
- `ntdll!NtCreateFile` at `0x180035863`
- `ntdll!NtCreateFile` at `0x180035863`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800357ff`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800357ff`
- `ntdll!NtClose` at `0x1800357c8`
- `ntdll!NtClose` at `0x1800358a1`
- `ntdll!NtClose` at `0x1800357c8`
- `ntdll!NtClose` at `0x1800358a1`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::CTracingSink::Initialize(__int64 a1, const WCHAR *a2)
{
  void **v2; // rbx
  char *v3; // rcx
  NTSTATUS v6; // edi
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-19h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp+27h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  v2 = (void **)(a1 + 16);
  ObjectAttributes.RootDirectory = 0;
  v3 = *(char **)(a1 + 16);
  NtPathName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( NtClose(v3) < 0 )
      __fastfail(7u);
    *v2 = 0;
  }
  if ( !a2 || !*a2 )
    return 0;
  if ( !RtlDosPathNameToNtPathName_U(a2, &NtPathName, 0, 0) )
    return 3221225473LL;
  if ( (char *)*v2 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1800358EBLL);
  }
  v6 = NtCreateFile(v2, 0x40100080u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 3u, 0x60u, 0, 0);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( v6 < 0 && (char *)*v2 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( NtClose(*v2) < 0 )
      __fastfail(7u);
    *v2 = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180035764  mov     [rsp-8+arg_10], rbx
0x180035769  push    rbp
0x18003576a  push    rsi
0x18003576b  push    rdi
0x18003576c  lea     rbp, [rsp-47h]
0x180035771  sub     rsp, 0C0h
0x180035778  mov     rax, cs:__security_cookie
0x18003577f  xor     rax, rsp
0x180035782  mov     [rbp+57h+var_20], rax
0x180035786  xorps   xmm0, xmm0
0x180035789  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180035791  lea     rax, [rbp+57h+NtPathName]
0x180035795  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18003579d  xor     esi, esi
0x18003579f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800357a3  lea     rbx, [rcx+10h]
0x1800357a7  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1800357ab  mov     rcx, [rbx]; Handle
0x1800357ae  mov     rdi, rdx
0x1800357b1  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x1800357b5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800357ba  lea     rax, [rcx-1]
0x1800357be  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800357c2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800357c6  ja      short loc_1800357E0
0x1800357c8  call    cs:__imp_NtClose
0x1800357cf  nop     dword ptr [rax+rax+00h]
0x1800357d4  test    eax, eax
0x1800357d6  jns     short loc_1800357DD
0x1800357d8  lea     ecx, [rsi+7]
0x1800357db  int     29h; Win8: RtlFailFast(ecx)
0x1800357dd  mov     [rbx], rsi
0x1800357e0  test    rdi, rdi
0x1800357e3  jz      loc_1800358BF
0x1800357e9  cmp     [rdi], si
0x1800357ec  jz      loc_1800358BF
0x1800357f2  xor     r9d, r9d; DirectoryInfo
0x1800357f5  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x1800357f9  xor     r8d, r8d; NtFileNamePart
0x1800357fc  mov     rcx, rdi; DosPathName
0x1800357ff  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180035806  nop     dword ptr [rax+rax+00h]
0x18003580b  test    al, al
0x18003580d  jnz     short loc_180035819
0x18003580f  mov     eax, 0C0000001h
0x180035814  jmp     loc_1800358C1
0x180035819  mov     rax, [rbx]
0x18003581c  dec     rax
0x18003581f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180035823  jbe     loc_1800358E1
0x180035829  mov     [rsp+0D0h+EaLength], esi; EaLength
0x18003582d  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180035831  mov     [rsp+0D0h+EaBuffer], rsi; EaBuffer
0x180035836  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003583a  mov     [rsp+0D0h+CreateOptions], 60h ; '`'; CreateOptions
0x180035842  mov     edx, 40100080h; DesiredAccess
0x180035847  mov     [rsp+0D0h+CreateDisposition], 3; CreateDisposition
0x18003584f  mov     rcx, rbx; FileHandle
0x180035852  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x18003585a  mov     [rsp+0D0h+FileAttributes], esi; FileAttributes
0x18003585e  mov     [rsp+0D0h+AllocationSize], rsi; AllocationSize
0x180035863  call    cs:__imp_NtCreateFile
0x18003586a  nop     dword ptr [rax+rax+00h]
0x18003586f  mov     rcx, gs:60h
0x180035878  xor     edx, edx; Flags
0x18003587a  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x18003587e  mov     edi, eax
0x180035880  mov     rcx, [rcx+30h]; HeapHandle
0x180035884  call    cs:__imp_RtlFreeHeap
0x18003588b  nop     dword ptr [rax+rax+00h]
0x180035890  test    edi, edi
0x180035892  jns     short loc_1800358BB
0x180035894  mov     rcx, [rbx]; Handle
0x180035897  lea     rdx, [rcx-1]
0x18003589b  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003589f  ja      short loc_1800358BB
0x1800358a1  call    cs:__imp_NtClose
0x1800358a8  nop     dword ptr [rax+rax+00h]
0x1800358ad  test    eax, eax
0x1800358af  jns     short loc_1800358B8
0x1800358b1  mov     ecx, 7
0x1800358b6  int     29h; Win8: RtlFailFast(ecx)
0x1800358b8  mov     [rbx], rsi
0x1800358bb  mov     eax, edi
0x1800358bd  jmp     short loc_1800358C1
0x1800358bf  xor     eax, eax
0x1800358c1  mov     rcx, [rbp+57h+var_20]
0x1800358c5  xor     rcx, rsp; StackCookie
0x1800358c8  call    __security_check_cookie
0x1800358cd  mov     rbx, [rsp+0D0h+arg_10]
0x1800358d5  add     rsp, 0C0h
0x1800358dc  pop     rdi
0x1800358dd  pop     rsi
0x1800358de  pop     rbp
0x1800358df  retn
0x1800358e1  mov     ecx, 0C00000E5h; int
0x1800358e6  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
