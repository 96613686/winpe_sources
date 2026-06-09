# TraceLoggingRegisterEx_EventRegister_EventSetInformation

- ea: `0x180001950`
- end: `0x180001a00`
- name: `TraceLoggingRegisterEx_EventRegister_EventSetInformation`
- size: `176`
- prototype: `__int64 __fastcall(_QWORD *CallbackContext)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180001d50`
- `0x18000914c`

## callees

- `0x180001950`
- `0x18000b640`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800019b2`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800019b2`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800019db`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800019db`

## pseudocode

```c
__int64 __fastcall TraceLoggingRegisterEx_EventRegister_EventSetInformation(_QWORD *CallbackContext)
{
  _QWORD *v1; // rsi
  bool v2; // zf
  signed int v4; // eax
  unsigned int v5; // ebx
  GUID ProviderId; // [rsp+20h] [rbp-28h] BYREF

  v1 = CallbackContext + 4;
  v2 = CallbackContext[4] == 0;
  ProviderId = *(GUID *)(CallbackContext[1] - 16LL);
  if ( !v2 )
    __fastfail(5u);
  CallbackContext[5] = 0;
  CallbackContext[6] = 0;
  v4 = EventRegister(&ProviderId, (PENABLECALLBACK)tlgEnableCallback, CallbackContext, CallbackContext + 4);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      return (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    EventSetInformation(
      *v1,
      2,
      CallbackContext[1],
      *(unsigned __int16 *)CallbackContext[1],
      *(_QWORD *)&ProviderId.Data1,
      *(_QWORD *)ProviderId.Data4);
  }
  return v5;
}

```

## disassembly

```asm
0x180001950  mov     [rsp+arg_8], rbx
0x180001955  mov     [rsp+arg_10], rsi
0x18000195a  push    rdi
0x18000195b  sub     rsp, 40h
0x18000195f  mov     rax, cs:__security_cookie
0x180001966  xor     rax, rsp
0x180001969  mov     [rsp+48h+var_18], rax
0x18000196e  mov     rax, [rcx+8]
0x180001972  lea     rsi, [rcx+20h]
0x180001976  cmp     qword ptr [rsi], 0
0x18000197a  mov     rdi, rcx
0x18000197d  movups  xmm0, xmmword ptr [rax-10h]
0x180001981  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x180001987  jz      short loc_180001990
0x180001989  mov     ecx, 5
0x18000198e  int     29h; Win8: RtlFailFast(ecx)
0x180001990  mov     r9, rsi; RegHandle
0x180001993  mov     qword ptr [rdi+28h], 0
0x18000199b  mov     r8, rdi; CallbackContext
0x18000199e  mov     qword ptr [rdi+30h], 0
0x1800019a6  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800019ad  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x1800019b2  call    cs:__imp_EventRegister
0x1800019b8  mov     ebx, eax
0x1800019ba  test    eax, eax
0x1800019bc  jz      short loc_1800019CB
0x1800019be  jle     short loc_1800019E1
0x1800019c0  movzx   ebx, ax
0x1800019c3  or      ebx, 80070000h
0x1800019c9  jmp     short loc_1800019E1
0x1800019cb  mov     r8, [rdi+8]
0x1800019cf  mov     edx, 2
0x1800019d4  mov     rcx, [rsi]
0x1800019d7  movzx   r9d, word ptr [r8]
0x1800019db  call    cs:__imp_EventSetInformation
0x1800019e1  mov     eax, ebx
0x1800019e3  mov     rcx, [rsp+48h+var_18]
0x1800019e8  xor     rcx, rsp; StackCookie
0x1800019eb  call    __security_check_cookie
0x1800019f0  mov     rbx, [rsp+48h+arg_8]
0x1800019f5  mov     rsi, [rsp+48h+arg_10]
0x1800019fa  add     rsp, 40h
0x1800019fe  pop     rdi
0x1800019ff  retn
```
