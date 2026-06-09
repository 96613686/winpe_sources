# _anonymous_namespace_::CTracingSink::Initialize

- ea: `0x180073634`
- end: `0x18007376d`
- name: `_anonymous_namespace_::CTracingSink::Initialize`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180073774`

## callees

- `0x18000ea3c`
- `0x1800293a0`
- `0x180044754`
- `0x180073634`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18007370e`
- `ntdll!NtCreateFile` at `0x18007370e`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800736b2`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800736b2`
- `ntdll!RtlFreeHeap` at `0x18007372f`
- `ntdll!RtlFreeHeap` at `0x18007372f`

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
0x180073634  mov     [rsp-8+arg_10], rbx
0x180073639  push    rbp
0x18007363a  push    rsi
0x18007363b  push    rdi
0x18007363c  lea     rbp, [rsp-47h]
0x180073641  sub     rsp, 0C0h
0x180073648  mov     rax, cs:__security_cookie
0x18007364f  xor     rax, rsp
0x180073652  mov     [rbp+57h+var_20], rax
0x180073656  xorps   xmm0, xmm0
0x180073659  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180073661  lea     rdi, [rcx+10h]
0x180073665  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18007366d  lea     rax, [rbp+57h+NtPathName]
0x180073671  xor     esi, esi
0x180073673  mov     rcx, rdi
0x180073676  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18007367a  mov     rbx, rdx
0x18007367d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180073681  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x180073685  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18007368a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18007368e  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180073693  test    rbx, rbx
0x180073696  jz      loc_18007374B
0x18007369c  cmp     [rbx], si
0x18007369f  jz      loc_18007374B
0x1800736a5  xor     r9d, r9d; DirectoryInfo
0x1800736a8  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x1800736ac  xor     r8d, r8d; NtFileNamePart
0x1800736af  mov     rcx, rbx; DosPathName
0x1800736b2  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800736b9  nop     dword ptr [rax+rax+00h]
0x1800736be  test    al, al
0x1800736c0  jnz     short loc_1800736CC
0x1800736c2  mov     eax, 0C0000001h
0x1800736c7  jmp     loc_18007374D
0x1800736cc  mov     rcx, rdi
0x1800736cf  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x1800736d4  mov     [rsp+0D0h+EaLength], esi; EaLength
0x1800736d8  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800736dc  mov     [rsp+0D0h+EaBuffer], rsi; EaBuffer
0x1800736e1  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800736e5  mov     [rsp+0D0h+CreateOptions], 60h ; '`'; CreateOptions
0x1800736ed  mov     edx, 40100080h; DesiredAccess
0x1800736f2  mov     [rsp+0D0h+CreateDisposition], 3; CreateDisposition
0x1800736fa  mov     rcx, rax; FileHandle
0x1800736fd  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x180073705  mov     [rsp+0D0h+FileAttributes], esi; FileAttributes
0x180073709  mov     [rsp+0D0h+AllocationSize], rsi; AllocationSize
0x18007370e  call    cs:__imp_NtCreateFile
0x180073715  nop     dword ptr [rax+rax+00h]
0x18007371a  mov     rcx, gs:60h
0x180073723  xor     edx, edx; Flags
0x180073725  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x180073729  mov     ebx, eax
0x18007372b  mov     rcx, [rcx+30h]; HeapHandle
0x18007372f  call    cs:__imp_RtlFreeHeap
0x180073736  nop     dword ptr [rax+rax+00h]
0x18007373b  test    ebx, ebx
0x18007373d  jns     short loc_180073747
0x18007373f  mov     rcx, rdi
0x180073742  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180073747  mov     eax, ebx
0x180073749  jmp     short loc_18007374D
0x18007374b  xor     eax, eax
0x18007374d  mov     rcx, [rbp+57h+var_20]
0x180073751  xor     rcx, rsp; StackCookie
0x180073754  call    __security_check_cookie
0x180073759  mov     rbx, [rsp+0D0h+arg_10]
0x180073761  add     rsp, 0C0h
0x180073768  pop     rdi
0x180073769  pop     rsi
0x18007376a  pop     rbp
0x18007376b  retn
```
