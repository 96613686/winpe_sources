# TraceLoggingRegister_EtwRegister_EtwSetInformation

- ea: `0x140017008`
- end: `0x1400170b6`
- name: `TraceLoggingRegister_EtwRegister_EtwSetInformation`
- size: `174`
- prototype: `__int64 __fastcall(PVOID CallbackContext)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400092a4`
- `0x14001903c`

## callees

- `0x14000a680`
- `0x140017008`

## import_xrefs

- `ntoskrnl!EtwRegister` at `0x14001706a`
- `ntoskrnl!EtwRegister` at `0x14001706a`
- `ntoskrnl!EtwSetInformation` at `0x14001708a`
- `ntoskrnl!EtwSetInformation` at `0x14001708a`

## pseudocode

```c
__int64 __fastcall TraceLoggingRegister_EtwRegister_EtwSetInformation(char *CallbackContext)
{
  REGHANDLE *v1; // rdi
  bool v2; // zf
  unsigned int v4; // esi
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  v1 = (REGHANDLE *)(CallbackContext + 32);
  v2 = *((_QWORD *)CallbackContext + 4) == 0;
  ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
  if ( !v2 )
    __fastfail(5u);
  *((_QWORD *)CallbackContext + 5) = 0;
  *((_QWORD *)CallbackContext + 6) = 0;
  v4 = EtwRegister(&ProviderId, tlgEnableCallback, CallbackContext, (PREGHANDLE)CallbackContext + 4);
  if ( !v4 )
    EtwSetInformation(
      *v1,
      EventProviderSetTraits,
      *((PVOID *)CallbackContext + 1),
      **((unsigned __int16 **)CallbackContext + 1));
  return v4;
}

```

## disassembly

```asm
0x140017008  mov     [rsp+arg_8], rbx
0x14001700d  mov     [rsp+arg_10], rsi
0x140017012  push    rdi
0x140017013  sub     rsp, 40h
0x140017017  mov     rax, cs:__security_cookie
0x14001701e  xor     rax, rsp
0x140017021  mov     [rsp+48h+var_18], rax
0x140017026  mov     rax, [rcx+8]
0x14001702a  lea     rdi, [rcx+20h]
0x14001702e  cmp     qword ptr [rdi], 0
0x140017032  mov     rbx, rcx
0x140017035  movups  xmm0, xmmword ptr [rax-10h]
0x140017039  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x14001703f  jz      short loc_140017048
0x140017041  mov     ecx, 5
0x140017046  int     29h; Win8: RtlFailFast(ecx)
0x140017048  mov     r9, rdi; RegHandle
0x14001704b  mov     qword ptr [rbx+28h], 0
0x140017053  mov     r8, rbx; CallbackContext
0x140017056  mov     qword ptr [rbx+30h], 0
0x14001705e  lea     rdx, _tlgEnableCallback; EnableCallback
0x140017065  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x14001706a  call    cs:__imp_EtwRegister
0x140017071  nop     dword ptr [rax+rax+00h]
0x140017076  mov     esi, eax
0x140017078  test    eax, eax
0x14001707a  jnz     short loc_140017096
0x14001707c  mov     r8, [rbx+8]; EventInformation
0x140017080  lea     edx, [rax+2]; InformationClass
0x140017083  mov     rcx, [rdi]; RegHandle
0x140017086  movzx   r9d, word ptr [r8]; InformationLength
0x14001708a  call    cs:__imp_EtwSetInformation
0x140017091  nop     dword ptr [rax+rax+00h]
0x140017096  mov     eax, esi
0x140017098  mov     rcx, [rsp+48h+var_18]
0x14001709d  xor     rcx, rsp; StackCookie
0x1400170a0  call    __security_check_cookie
0x1400170a5  mov     rbx, [rsp+48h+arg_8]
0x1400170aa  mov     rsi, [rsp+48h+arg_10]
0x1400170af  add     rsp, 40h
0x1400170b3  pop     rdi
0x1400170b4  retn
```
