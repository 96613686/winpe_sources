# appv::shared::kernel::SidFromPid<appv::shared::kernel::UnicodeString_allocator>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,uchar *)

- ea: `0x140014640`
- end: `0x140014757`
- name: `??$SidFromPid@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@012@PEAE@Z`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140014934`
- `0x140014c40`

## callees

- `0x140014640`
- `0x140014760`

## import_xrefs

- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400146d9`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400146d9`
- `ntoskrnl!ZwOpenProcess` at `0x1400146aa`
- `ntoskrnl!ZwOpenProcess` at `0x1400146aa`
- `ntoskrnl!ZwClose` at `0x1400146f3`
- `ntoskrnl!ZwClose` at `0x14001471f`
- `ntoskrnl!ZwClose` at `0x140014733`
- `ntoskrnl!ZwClose` at `0x1400146f3`
- `ntoskrnl!ZwClose` at `0x14001471f`
- `ntoskrnl!ZwClose` at `0x140014733`

## pseudocode

```c
NTSTATUS __fastcall appv::shared::kernel::SidFromPid<appv::shared::kernel::UnicodeString_allocator>(
        void *a1,
        __int64 a2,
        __int64 a3)
{
  NTSTATUS result; // eax
  void *v6; // rbx
  NTSTATUS v7; // edi
  void *v8; // rdi
  int v9; // esi
  struct _CLIENT_ID ClientId; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *ProcessHandle; // [rsp+80h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+98h] [rbp+38h] BYREF

  ClientId.UniqueProcess = a1;
  ProcessHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  ClientId.UniqueThread = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenProcess(&ProcessHandle, 0, &ObjectAttributes, &ClientId);
  if ( result >= 0 )
  {
    v6 = ProcessHandle;
    TokenHandle = 0;
    v7 = ZwOpenProcessTokenEx(ProcessHandle, 0x20008u, 0x200u, &TokenHandle);
    if ( v7 >= 0 )
    {
      v8 = TokenHandle;
      v9 = appv::shared::kernel::SidFromToken<appv::shared::kernel::UnicodeString_allocator>(TokenHandle, a2, a3);
      if ( v8 )
        ZwClose(v8);
      if ( v6 )
        ZwClose(v6);
      return v9;
    }
    else
    {
      if ( v6 )
        ZwClose(v6);
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140014640  mov     [rsp-18h+arg_8], rbx
0x140014645  mov     [rsp-18h+arg_10], rsi
0x14001464a  push    rbp
0x14001464b  push    rdi
0x14001464c  push    r14
0x14001464e  mov     rbp, rsp
0x140014651  sub     rsp, 60h
0x140014655  mov     rsi, r8
0x140014658  mov     [rbp+ClientId.UniqueProcess], rcx
0x14001465c  mov     r14, rdx
0x14001465f  mov     [rbp+ProcessHandle], 0
0x140014667  xorps   xmm0, xmm0
0x14001466a  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140014672  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140014676  mov     qword ptr [rbp+ObjectAttributes.Attributes], 200h
0x14001467e  xor     edx, edx; DesiredAccess
0x140014680  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140014688  lea     rcx, [rbp+ProcessHandle]; ProcessHandle
0x14001468c  mov     [rbp+ObjectAttributes.ObjectName], 0
0x140014694  lea     r9, [rbp+ClientId]; ClientId
0x140014698  mov     [rbp+ClientId.UniqueThread], 0
0x1400146a0  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400146a5  mov     edi, 200h
0x1400146aa  call    cs:__imp_ZwOpenProcess
0x1400146b1  nop     dword ptr [rax+rax+00h]
0x1400146b6  test    eax, eax
0x1400146b8  js      loc_140014741
0x1400146be  mov     rbx, [rbp+ProcessHandle]
0x1400146c2  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1400146c6  mov     rcx, rbx; ProcessHandle
0x1400146c9  mov     [rbp+TokenHandle], 0
0x1400146d1  mov     r8d, edi; HandleAttributes
0x1400146d4  mov     edx, 20008h; DesiredAccess
0x1400146d9  call    cs:__imp_ZwOpenProcessTokenEx
0x1400146e0  nop     dword ptr [rax+rax+00h]
0x1400146e5  mov     edi, eax
0x1400146e7  test    eax, eax
0x1400146e9  jns     short loc_140014703
0x1400146eb  test    rbx, rbx
0x1400146ee  jz      short loc_1400146FF
0x1400146f0  mov     rcx, rbx; Handle
0x1400146f3  call    cs:__imp_ZwClose
0x1400146fa  nop     dword ptr [rax+rax+00h]
0x1400146ff  mov     eax, edi
0x140014701  jmp     short loc_140014741
0x140014703  mov     rdi, [rbp+TokenHandle]
0x140014707  mov     r8, rsi
0x14001470a  mov     rcx, rdi
0x14001470d  mov     rdx, r14
0x140014710  call    ??$SidFromToken@UUnicodeString_allocator@kernel@shared@appv@@@kernel@shared@appv@@YAJPEAXAEAV?$managed_unicode_string@UUnicodeString_allocator@kernel@shared@appv@@@012@PEAE@Z; appv::shared::kernel::SidFromToken<appv::shared::kernel::UnicodeString_allocator>(void *,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::UnicodeString_allocator> &,uchar *)
0x140014715  mov     esi, eax
0x140014717  test    rdi, rdi
0x14001471a  jz      short loc_14001472B
0x14001471c  mov     rcx, rdi; Handle
0x14001471f  call    cs:__imp_ZwClose
0x140014726  nop     dword ptr [rax+rax+00h]
0x14001472b  test    rbx, rbx
0x14001472e  jz      short loc_14001473F
0x140014730  mov     rcx, rbx; Handle
0x140014733  call    cs:__imp_ZwClose
0x14001473a  nop     dword ptr [rax+rax+00h]
0x14001473f  mov     eax, esi
0x140014741  lea     r11, [rsp+60h+var_s0]
0x140014746  mov     rbx, [r11+28h]
0x14001474a  mov     rsi, [r11+30h]
0x14001474e  mov     rsp, r11
0x140014751  pop     r14
0x140014753  pop     rdi
0x140014754  pop     rbp
0x140014755  retn
```
