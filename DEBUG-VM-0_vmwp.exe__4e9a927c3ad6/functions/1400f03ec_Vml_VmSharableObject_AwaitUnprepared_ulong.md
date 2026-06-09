# Vml::VmSharableObject::AwaitUnprepared(ulong)

- ea: `0x1400f03ec`
- end: `0x1400f0518`
- name: `?AwaitUnprepared@VmSharableObject@Vml@@QEBA_NK@Z`
- size: `300`
- prototype: `bool __fastcall(Vml::VmSharableObject *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400f01b8`
- `0x14028ab30`

## callees

- `0x14008c964`
- `0x14009f9ec`
- `0x1400f03ec`
- `0x14013ac8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400f04c3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400f04c3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400f0441`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400f0441`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400f048c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400f048c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400f046c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400f046c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400f0413`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400f0413`

## string_xrefs

- `0x1400f049c`: `onecore\vm\common\vml\VmSharableObject.h`
- `0x1400f04df`: `onecore\vm\common\vml\VmSharableObject.h`
- `0x1400f0506`: `onecore\vm\common\vml\VmSharableObject.h`

## pseudocode

```c
char __fastcall Vml::VmSharableObject::AwaitUnprepared(Vml::VmSharableObject *this, int a2, __int64 a3, const char *a4)
{
  char v5; // di
  void *v6; // rbx
  HANDLE EventW; // rax
  const char *v8; // r9
  DWORD TimeRemaining; // eax
  DWORD v10; // eax
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v14; // [rsp+50h] [rbp+8h] BYREF
  DWORD TickCount; // [rsp+54h] [rbp+Ch]

  if ( (*((_DWORD *)this + 4) & 0x7000000u) < 0x3000000 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x12A9,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSharableObject.h",
      a4);
  v5 = 0;
  v14 = a2;
  TickCount = GetTickCount();
LABEL_3:
  v6 = (void *)*((_QWORD *)this + 8);
  while ( 1 )
  {
    if ( v6 == (void *)-1LL )
      return 1;
    if ( v6 )
      goto LABEL_13;
    EventW = CreateEventW(0, 1, 0, 0);
    if ( !EventW )
    {
      if ( (unsigned int)Vml::VmTimeoutTimer::IsExpired((Vml::VmTimeoutTimer *)&v14) )
        return v5;
      Sleep(0x12Cu);
      goto LABEL_3;
    }
    v6 = (void *)_InterlockedCompareExchange64((volatile signed __int64 *)this + 8, (signed __int64)EventW, 0);
    if ( !v6 )
      break;
    if ( !CloseHandle(EventW) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x12DA,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSharableObject.h",
        v8);
  }
  v6 = EventW;
LABEL_13:
  TimeRemaining = Vml::VmTimeoutTimer::GetTimeRemaining((Vml::VmTimeoutTimer *)&v14);
  v10 = WaitForSingleObject(v6, TimeRemaining);
  if ( !v10 )
    return 1;
  if ( v10 != 258 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x12FA,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSharableObject.h",
      v11);
  return v5;
}

```

## disassembly

```asm
0x1400f03ec  push    rbx
0x1400f03ee  push    rbp
0x1400f03ef  push    rsi
0x1400f03f0  push    rdi
0x1400f03f1  sub     rsp, 28h
0x1400f03f5  mov     rax, [rcx+10h]
0x1400f03f9  mov     rsi, rcx
0x1400f03fc  and     eax, 7000000h
0x1400f0401  cmp     eax, 3000000h
0x1400f0406  jb      loc_1400F0501
0x1400f040c  xor     dil, dil
0x1400f040f  mov     [rsp+48h+arg_0], edx
0x1400f0413  call    cs:__imp_GetTickCount
0x1400f041a  nop     dword ptr [rax+rax+00h]
0x1400f041f  mov     [rsp+48h+arg_4], eax
0x1400f0423  mov     rbx, [rsi+40h]
0x1400f0427  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400f042b  jz      loc_1400F04F1
0x1400f0431  test    rbx, rbx
0x1400f0434  jnz     short loc_1400F04B4
0x1400f0436  xor     r9d, r9d; lpName
0x1400f0439  lea     edx, [rbx+1]; bManualReset
0x1400f043c  xor     r8d, r8d; bInitialState
0x1400f043f  xor     ecx, ecx; lpEventAttributes
0x1400f0441  call    cs:__imp_CreateEventW
0x1400f0448  nop     dword ptr [rax+rax+00h]
0x1400f044d  mov     rcx, rax; hObject
0x1400f0450  test    rax, rax
0x1400f0453  jnz     short loc_1400F047A
0x1400f0455  lea     rcx, [rsp+48h+arg_0]; this
0x1400f045a  call    ?IsExpired@VmTimeoutTimer@Vml@@QEBAHXZ; Vml::VmTimeoutTimer::IsExpired(void)
0x1400f045f  test    eax, eax
0x1400f0461  jnz     loc_1400F04F4
0x1400f0467  mov     ecx, 12Ch; dwMilliseconds
0x1400f046c  call    cs:__imp_Sleep
0x1400f0473  nop     dword ptr [rax+rax+00h]
0x1400f0478  jmp     short loc_1400F0423
0x1400f047a  xor     eax, eax
0x1400f047c  lock cmpxchg [rsi+40h], rcx
0x1400f0482  mov     rbx, rax
0x1400f0485  jz      short loc_1400F04B1
0x1400f0487  mov     rbp, [rsp+48h]
0x1400f048c  call    cs:__imp_CloseHandle
0x1400f0493  nop     dword ptr [rax+rax+00h]
0x1400f0498  test    eax, eax
0x1400f049a  jnz     short loc_1400F0427
0x1400f049c  lea     r8, aOnecoreVmCommo_68; "onecore\\vm\\common\\vml\\VmSharableObj"...
0x1400f04a3  mov     edx, 12DAh; void *
0x1400f04a8  mov     rcx, rbp; this
0x1400f04ab  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400f04b1  mov     rbx, rcx
0x1400f04b4  lea     rcx, [rsp+48h+arg_0]; this
0x1400f04b9  call    ?GetTimeRemaining@VmTimeoutTimer@Vml@@QEBAKXZ; Vml::VmTimeoutTimer::GetTimeRemaining(void)
0x1400f04be  mov     edx, eax; dwMilliseconds
0x1400f04c0  mov     rcx, rbx; hHandle
0x1400f04c3  call    cs:__imp_WaitForSingleObject
0x1400f04ca  nop     dword ptr [rax+rax+00h]
0x1400f04cf  test    eax, eax
0x1400f04d1  jz      short loc_1400F04F1
0x1400f04d3  cmp     eax, 102h
0x1400f04d8  jz      short loc_1400F04F4
0x1400f04da  mov     rcx, [rsp+48h]; this
0x1400f04df  lea     r8, aOnecoreVmCommo_68; "onecore\\vm\\common\\vml\\VmSharableObj"...
0x1400f04e6  mov     edx, 12FAh; void *
0x1400f04eb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1400f04f1  mov     dil, 1
0x1400f04f4  mov     al, dil
0x1400f04f7  add     rsp, 28h
0x1400f04fb  pop     rdi
0x1400f04fc  pop     rsi
0x1400f04fd  pop     rbp
0x1400f04fe  pop     rbx
0x1400f04ff  retn
0x1400f0501  mov     rcx, [rsp+48h]; this
0x1400f0506  lea     r8, aOnecoreVmCommo_68; "onecore\\vm\\common\\vml\\VmSharableObj"...
0x1400f050d  mov     edx, 12A9h; void *
0x1400f0512  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
