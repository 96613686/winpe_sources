# Streaming::Utils::GetCurrentProcessAndUserNotSystem(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,void * &)

- ea: `0x140014934`
- end: `0x140014a47`
- name: `?GetCurrentProcessAndUserNotSystem@Utils@Streaming@@YAJAEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@AEAPEAX@Z`
- size: `275`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000a310`
- `0x140014c40`

## callees

- `0x140003770`
- `0x140014640`
- `0x140014760`
- `0x140014934`

## import_xrefs

- `ntoskrnl!ZwOpenThreadTokenEx` at `0x140014982`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x140014982`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001494f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14001494f`
- `ntoskrnl!ZwClose` at `0x1400149b3`
- `ntoskrnl!ZwClose` at `0x1400149b3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014a24`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014a24`

## pseudocode

```c
__int64 __fastcall Streaming::Utils::GetCurrentProcessAndUserNotSystem(__int64 a1, _QWORD *a2)
{
  HANDLE CurrentProcessId; // rbp
  NTSTATUS v5; // edi
  HANDLE v6; // rbx
  const WCHAR *v7; // rdx
  unsigned int v8; // ecx
  __int16 v9; // dx
  __int16 v10; // ax
  char v12; // [rsp+70h] [rbp+18h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp+20h] BYREF

  v12 = 1;
  CurrentProcessId = PsGetCurrentProcessId();
  Handle = 0;
  v5 = ZwOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x20008u, 0, 0x200u, &Handle);
  if ( v5 >= 0 )
  {
    v6 = Handle;
    v5 = appv::shared::kernel::SidFromToken<appv::shared::kernel::UnicodeString_allocator>(Handle, a1, &v12);
    if ( v6 )
      ZwClose(v6);
  }
  if ( v5 == -1073741700 )
    v5 = appv::shared::kernel::SidFromPid<appv::shared::kernel::UnicodeString_allocator>(
           CurrentProcessId,
           a1,
           (__int64)&v12);
  if ( v5 >= 0 )
  {
    if ( v12 )
    {
      appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(a1, 0);
      if ( *(_DWORD *)a1 )
      {
        v8 = *(_DWORD *)a1 >> 1;
        if ( v8 > 0xFFFF )
          v9 = -1;
        else
          v9 = *(_DWORD *)a1 >> 1;
        v10 = 0;
        if ( v8 <= 0xFFFF )
          v10 = v9;
        v7 = 0;
        if ( v10 )
          v7 = *(const WCHAR **)(a1 + 8);
      }
      else
      {
        v7 = 0;
      }
      RtlInitUnicodeString((PUNICODE_STRING)(a1 + 16), v7);
    }
    *a2 = CurrentProcessId;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140014934  mov     [rsp+arg_0], rbx
0x140014939  push    rbp
0x14001493a  push    rsi
0x14001493b  push    rdi
0x14001493c  push    r14
0x14001493e  push    r15
0x140014940  sub     rsp, 30h
0x140014944  mov     r14, rdx
0x140014947  mov     [rsp+58h+arg_10], 1
0x14001494c  mov     rsi, rcx
0x14001494f  call    cs:__imp_PsGetCurrentProcessId
0x140014956  nop     dword ptr [rax+rax+00h]
0x14001495b  xor     r15d, r15d
0x14001495e  mov     r9d, 200h; HandleAttributes
0x140014964  mov     rbp, rax
0x140014967  mov     [rsp+58h+Handle], r15
0x14001496c  lea     rax, [rsp+58h+Handle]
0x140014971  xor     r8d, r8d; OpenAsSelf
0x140014974  mov     edx, 20008h; DesiredAccess
0x140014979  mov     [rsp+58h+TokenHandle], rax; TokenHandle
0x14001497e  lea     rcx, [r15-2]; ThreadHandle
0x140014982  call    cs:__imp_ZwOpenThreadTokenEx
0x140014989  nop     dword ptr [rax+rax+00h]
0x14001498e  mov     edi, eax
0x140014990  test    eax, eax
0x140014992  js      short loc_1400149BF
0x140014994  mov     rbx, [rsp+58h+Handle]
0x140014999  lea     r8, [rsp+58h+arg_10]
0x14001499e  mov     rcx, rbx
0x1400149a1  mov     rdx, rsi
0x1400149a4  call    ??$SidFromToken@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@012@PEAE@Z; appv::shared::kernel::SidFromToken<appv::shared::kernel::UnicodeString_allocator>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,uchar *)
0x1400149a9  mov     edi, eax
0x1400149ab  test    rbx, rbx
0x1400149ae  jz      short loc_1400149BF
0x1400149b0  mov     rcx, rbx; Handle
0x1400149b3  call    cs:__imp_ZwClose
0x1400149ba  nop     dword ptr [rax+rax+00h]
0x1400149bf  cmp     edi, 0C000007Ch
0x1400149c5  jnz     short loc_1400149D9
0x1400149c7  lea     r8, [rsp+58h+arg_10]
0x1400149cc  mov     rdx, rsi
0x1400149cf  mov     rcx, rbp
0x1400149d2  call    ??$SidFromPid@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@012@PEAE@Z; appv::shared::kernel::SidFromPid<appv::shared::kernel::UnicodeString_allocator>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,uchar *)
0x1400149d7  mov     edi, eax
0x1400149d9  test    edi, edi
0x1400149db  js      short loc_140014A33
0x1400149dd  cmp     [rsp+58h+arg_10], r15b
0x1400149e2  jz      short loc_140014A30
0x1400149e4  xor     edx, edx
0x1400149e6  mov     rcx, rsi
0x1400149e9  call    ?resize@?$buffer@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z; appv::shared::kernel::buffer<appv::shared::kernel::UnicodeString_allocator>::resize(ulong)
0x1400149ee  mov     ecx, [rsi]
0x1400149f0  test    ecx, ecx
0x1400149f2  jnz     short loc_1400149F8
0x1400149f4  xor     edx, edx
0x1400149f6  jmp     short loc_140014A20
0x1400149f8  shr     ecx, 1
0x1400149fa  mov     r8d, 0FFFFh
0x140014a00  cmp     ecx, r8d
0x140014a03  ja      short loc_140014A0A
0x140014a05  movzx   edx, cx
0x140014a08  jmp     short loc_140014A0D
0x140014a0a  mov     edx, r8d
0x140014a0d  mov     eax, r15d
0x140014a10  cmovbe  ax, dx
0x140014a14  mov     rdx, r15
0x140014a17  test    ax, ax
0x140014a1a  jz      short loc_140014A20
0x140014a1c  mov     rdx, [rsi+8]; SourceString
0x140014a20  lea     rcx, [rsi+10h]; DestinationString
0x140014a24  call    cs:__imp_RtlInitUnicodeString
0x140014a2b  nop     dword ptr [rax+rax+00h]
0x140014a30  mov     [r14], rbp
0x140014a33  mov     rbx, [rsp+58h+arg_0]
0x140014a38  mov     eax, edi
0x140014a3a  add     rsp, 30h
0x140014a3e  pop     r15
0x140014a40  pop     r14
0x140014a42  pop     rdi
0x140014a43  pop     rsi
0x140014a44  pop     rbp
0x140014a45  retn
```
