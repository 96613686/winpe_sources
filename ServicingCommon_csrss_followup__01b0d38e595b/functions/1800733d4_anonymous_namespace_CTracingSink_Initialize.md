# _anonymous_namespace_::CTracingSink::Initialize

- ea: `0x1800733d4`
- end: `0x18007350d`
- name: `_anonymous_namespace_::CTracingSink::Initialize`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180073514`

## callees

- `0x180018df0`
- `0x18002d2b0`
- `0x180047884`
- `0x1800733d4`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800734ae`
- `ntdll!NtCreateFile` at `0x1800734ae`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180073452`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180073452`
- `ntdll!RtlFreeHeap` at `0x1800734cf`
- `ntdll!RtlFreeHeap` at `0x1800734cf`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::CTracingSink::Initialize(__int64 a1, const WCHAR *a2)
{
  __int64 v2; // rdi
  __int64 v4; // rdx
  void **InitPointer; // rax
  NTSTATUS v7; // ebx
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp+27h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  v2 = a1 + 16;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &NtPathName;
  NtPathName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(a1 + 16);
  if ( !a2 || !*a2 )
    return 0;
  if ( !RtlDosPathNameToNtPathName_U(a2, &NtPathName, 0, 0) )
    return 3221225473LL;
  InitPointer = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                           v2,
                           v4);
  v7 = NtCreateFile(InitPointer, 0x40100080u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 3u, 0x60u, 0, 0);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( v7 < 0 )
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(v2);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800733d4  mov     [rsp-8+arg_10], rbx
0x1800733d9  push    rbp
0x1800733da  push    rsi
0x1800733db  push    rdi
0x1800733dc  lea     rbp, [rsp-47h]
0x1800733e1  sub     rsp, 0C0h
0x1800733e8  mov     rax, cs:__security_cookie
0x1800733ef  xor     rax, rsp
0x1800733f2  mov     [rbp+57h+var_20], rax
0x1800733f6  xorps   xmm0, xmm0
0x1800733f9  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180073401  lea     rdi, [rcx+10h]
0x180073405  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18007340d  lea     rax, [rbp+57h+NtPathName]
0x180073411  xor     esi, esi
0x180073413  mov     rcx, rdi
0x180073416  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18007341a  mov     rbx, rdx
0x18007341d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180073421  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x180073425  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007342a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18007342e  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180073433  test    rbx, rbx
0x180073436  jz      loc_1800734EB
0x18007343c  cmp     [rbx], si
0x18007343f  jz      loc_1800734EB
0x180073445  xor     r9d, r9d; DirectoryInfo
0x180073448  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x18007344c  xor     r8d, r8d; NtFileNamePart
0x18007344f  mov     rcx, rbx; DosPathName
0x180073452  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180073459  nop     dword ptr [rax+rax+00h]
0x18007345e  test    al, al
0x180073460  jnz     short loc_18007346C
0x180073462  mov     eax, 0C0000001h
0x180073467  jmp     loc_1800734ED
0x18007346c  mov     rcx, rdi
0x18007346f  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x180073474  mov     [rsp+0D0h+EaLength], esi; EaLength
0x180073478  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18007347c  mov     [rsp+0D0h+EaBuffer], rsi; EaBuffer
0x180073481  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180073485  mov     [rsp+0D0h+CreateOptions], 60h ; '`'; CreateOptions
0x18007348d  mov     edx, 40100080h; DesiredAccess
0x180073492  mov     [rsp+0D0h+CreateDisposition], 3; CreateDisposition
0x18007349a  mov     rcx, rax; FileHandle
0x18007349d  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x1800734a5  mov     [rsp+0D0h+FileAttributes], esi; FileAttributes
0x1800734a9  mov     [rsp+0D0h+AllocationSize], rsi; AllocationSize
0x1800734ae  call    cs:__imp_NtCreateFile
0x1800734b5  nop     dword ptr [rax+rax+00h]
0x1800734ba  mov     rcx, gs:60h
0x1800734c3  xor     edx, edx; Flags
0x1800734c5  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x1800734c9  mov     ebx, eax
0x1800734cb  mov     rcx, [rcx+30h]; HeapHandle
0x1800734cf  call    cs:__imp_RtlFreeHeap
0x1800734d6  nop     dword ptr [rax+rax+00h]
0x1800734db  test    ebx, ebx
0x1800734dd  jns     short loc_1800734E7
0x1800734df  mov     rcx, rdi
0x1800734e2  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1800734e7  mov     eax, ebx
0x1800734e9  jmp     short loc_1800734ED
0x1800734eb  xor     eax, eax
0x1800734ed  mov     rcx, [rbp+57h+var_20]
0x1800734f1  xor     rcx, rsp; StackCookie
0x1800734f4  call    __security_check_cookie
0x1800734f9  mov     rbx, [rsp+0D0h+arg_10]
0x180073501  add     rsp, 0C0h
0x180073508  pop     rdi
0x180073509  pop     rsi
0x18007350a  pop     rbp
0x18007350b  retn
```
