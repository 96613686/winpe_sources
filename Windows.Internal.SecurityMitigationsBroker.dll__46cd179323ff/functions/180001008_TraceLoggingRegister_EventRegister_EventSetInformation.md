# TraceLoggingRegister_EventRegister_EventSetInformation

- ea: `0x180001008`
- end: `0x1800010b8`
- name: `TraceLoggingRegister_EventRegister_EventSetInformation`
- size: `176`
- prototype: `__int64 __fastcall(PVOID CallbackContext)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004210`

## callees

- `0x180001008`
- `0x180006980`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000106a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000106a`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180001093`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180001093`

## pseudocode

```c
__int64 __fastcall TraceLoggingRegister_EventRegister_EventSetInformation(_QWORD *CallbackContext)
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
0x180001008  mov     [rsp+arg_8], rbx
0x18000100d  mov     [rsp+arg_10], rsi
0x180001012  push    rdi
0x180001013  sub     rsp, 40h
0x180001017  mov     rax, cs:__security_cookie
0x18000101e  xor     rax, rsp
0x180001021  mov     [rsp+48h+var_18], rax
0x180001026  mov     rax, [rcx+8]
0x18000102a  lea     rsi, [rcx+20h]
0x18000102e  cmp     qword ptr [rsi], 0
0x180001032  mov     rdi, rcx
0x180001035  movups  xmm0, xmmword ptr [rax-10h]
0x180001039  movdqu  xmmword ptr [rsp+48h+ProviderId.Data1], xmm0
0x18000103f  jz      short loc_180001048
0x180001041  mov     ecx, 5
0x180001046  int     29h; Win8: RtlFailFast(ecx)
0x180001048  mov     r9, rsi; RegHandle
0x18000104b  mov     qword ptr [rdi+28h], 0
0x180001053  mov     r8, rdi; CallbackContext
0x180001056  mov     qword ptr [rdi+30h], 0
0x18000105e  lea     rdx, _tlgEnableCallback; EnableCallback
0x180001065  lea     rcx, [rsp+48h+ProviderId]; ProviderId
0x18000106a  call    cs:__imp_EventRegister
0x180001070  mov     ebx, eax
0x180001072  test    eax, eax
0x180001074  jz      short loc_180001083
0x180001076  jle     short loc_180001099
0x180001078  movzx   ebx, ax
0x18000107b  or      ebx, 80070000h
0x180001081  jmp     short loc_180001099
0x180001083  mov     r8, [rdi+8]
0x180001087  mov     edx, 2
0x18000108c  mov     rcx, [rsi]
0x18000108f  movzx   r9d, word ptr [r8]
0x180001093  call    cs:__imp_EventSetInformation
0x180001099  mov     eax, ebx
0x18000109b  mov     rcx, [rsp+48h+var_18]
0x1800010a0  xor     rcx, rsp; StackCookie
0x1800010a3  call    __security_check_cookie
0x1800010a8  mov     rbx, [rsp+48h+arg_8]
0x1800010ad  mov     rsi, [rsp+48h+arg_10]
0x1800010b2  add     rsp, 40h
0x1800010b6  pop     rdi
0x1800010b7  retn
```
