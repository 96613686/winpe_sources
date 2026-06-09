# Windows::Networking::UX::Internal::StateBase::StartTimer(ulong)

- ea: `0x18006c174`
- end: `0x18006c265`
- name: `?StartTimer@StateBase@Internal@UX@Networking@Windows@@IEAAXK@Z`
- size: `241`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::StateBase *__hidden this, DWORD DueTime)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18006e3b0`
- `0x18006eb30`
- `0x18006eb70`

## callees

- `0x18000de4c`
- `0x18001d4d4`
- `0x18006b16c`
- `0x18006c174`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c204`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18006c1e8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18006c1e8`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::StateBase::StartTimer(void **this, DWORD DueTime)
{
  PVOID *v4; // rcx
  signed int LastError; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_5dd97abf89e6303816d5c30271157f49_Traceguids);
  if ( this[29] != (void *)-1LL )
    Windows::Networking::UX::Internal::StateBase::DeleteTimer((Windows::Networking::UX::Internal::StateBase *)this);
  if ( CreateTimerQueueTimer(
         this + 29,
         0,
         Windows::Networking::UX::Internal::StateBase::s_TimerCallback,
         this,
         DueTime,
         0,
         8u) )
  {
    goto LABEL_12;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      37,
      WPP_5dd97abf89e6303816d5c30271157f49_Traceguids,
      (unsigned int)LastError);
LABEL_12:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x40) != 0 )
    WPP_SF_(v4[2], 38, WPP_5dd97abf89e6303816d5c30271157f49_Traceguids);
}

```

## disassembly

```asm
0x18006c174  push    rbx
0x18006c176  push    rbp
0x18006c177  push    rsi
0x18006c178  push    rdi
0x18006c179  sub     rsp, 48h
0x18006c17d  mov     esi, edx
0x18006c17f  mov     rbx, rcx
0x18006c182  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c189  lea     rbp, WPP_GLOBAL_Control
0x18006c190  cmp     rcx, rbp
0x18006c193  jz      short loc_18006C1B0
0x18006c195  test    byte ptr [rcx+1Ch], 40h
0x18006c199  jz      short loc_18006C1B0
0x18006c19b  mov     rcx, [rcx+10h]
0x18006c19f  lea     r8, WPP_5dd97abf89e6303816d5c30271157f49_Traceguids
0x18006c1a6  mov     edx, 24h ; '$'
0x18006c1ab  call    WPP_SF_
0x18006c1b0  lea     rdi, [rbx+0E8h]
0x18006c1b7  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18006c1bb  jz      short loc_18006C1C5
0x18006c1bd  mov     rcx, rbx; this
0x18006c1c0  call    ?DeleteTimer@StateBase@Internal@UX@Networking@Windows@@IEAAXXZ; Windows::Networking::UX::Internal::StateBase::DeleteTimer(void)
0x18006c1c5  mov     [rsp+68h+Flags], 8; Flags
0x18006c1cd  lea     r8, ?s_TimerCallback@StateBase@Internal@UX@Networking@Windows@@SAXPEAXH@Z; Callback
0x18006c1d4  mov     [rsp+68h+Period], 0; Period
0x18006c1dc  mov     r9, rbx; Parameter
0x18006c1df  xor     edx, edx; TimerQueue
0x18006c1e1  mov     [rsp+68h+DueTime], esi; DueTime
0x18006c1e5  mov     rcx, rdi; phNewTimer
0x18006c1e8  call    cs:__imp_CreateTimerQueueTimer
0x18006c1ee  test    eax, eax
0x18006c1f0  jnz     short loc_18006C235
0x18006c1f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c1f9  cmp     rcx, rbp
0x18006c1fc  jz      short loc_18006C25C
0x18006c1fe  test    byte ptr [rcx+1Ch], 2
0x18006c202  jz      short loc_18006C23C
0x18006c204  call    cs:__imp_GetLastError
0x18006c20a  test    eax, eax
0x18006c20c  jle     short loc_18006C216
0x18006c20e  movzx   eax, ax
0x18006c211  or      eax, 80070000h
0x18006c216  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c21d  lea     r8, WPP_5dd97abf89e6303816d5c30271157f49_Traceguids
0x18006c224  mov     edx, 25h ; '%'
0x18006c229  mov     r9d, eax
0x18006c22c  mov     rcx, [rcx+10h]
0x18006c230  call    WPP_SF_d
0x18006c235  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c23c  cmp     rcx, rbp
0x18006c23f  jz      short loc_18006C25C
0x18006c241  test    byte ptr [rcx+1Ch], 40h
0x18006c245  jz      short loc_18006C25C
0x18006c247  mov     rcx, [rcx+10h]
0x18006c24b  lea     r8, WPP_5dd97abf89e6303816d5c30271157f49_Traceguids
0x18006c252  mov     edx, 26h ; '&'
0x18006c257  call    WPP_SF_
0x18006c25c  add     rsp, 48h
0x18006c260  pop     rdi
0x18006c261  pop     rsi
0x18006c262  pop     rbp
0x18006c263  pop     rbx
0x18006c264  retn
```
