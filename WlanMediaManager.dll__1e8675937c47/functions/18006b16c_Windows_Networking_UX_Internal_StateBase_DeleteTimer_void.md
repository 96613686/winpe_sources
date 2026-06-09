# Windows::Networking::UX::Internal::StateBase::DeleteTimer(void)

- ea: `0x18006b16c`
- end: `0x18006b273`
- name: `?DeleteTimer@StateBase@Internal@UX@Networking@Windows@@IEAAXXZ`
- size: `263`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::StateBase *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18006b144`
- `0x18006c174`
- `0x18006f7b0`
- `0x18006f840`

## callees

- `0x18000de4c`
- `0x18001d4d4`
- `0x18006b16c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b1ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006b1ee`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18006b1c1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18006b1c1`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::StateBase::DeleteTimer(
        Windows::Networking::UX::Internal::StateBase *this)
{
  PVOID *v2; // rcx
  void *v3; // rdx
  signed int LastError; // eax

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_5dd97abf89e6303816d5c30271157f49_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = (void *)*((_QWORD *)this + 29);
  if ( v3 != (void *)-1LL )
  {
    if ( DeleteTimerQueueTimer(0, v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      *((_QWORD *)this + 29) = -1;
    }
    else
    {
      v2 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_16;
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        WPP_5dd97abf89e6303816d5c30271157f49_Traceguids,
        (unsigned int)LastError);
    }
    goto LABEL_15;
  }
  if ( v2 == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)v2 + 28) & 2) != 0 )
  {
    WPP_SF_(v2[2], 41, WPP_5dd97abf89e6303816d5c30271157f49_Traceguids);
LABEL_15:
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_16:
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 0x40) != 0 )
    WPP_SF_(v2[2], 42, WPP_5dd97abf89e6303816d5c30271157f49_Traceguids);
}

```

## disassembly

```asm
0x18006b16c  mov     [rsp+arg_0], rbx
0x18006b171  push    rdi
0x18006b172  sub     rsp, 20h
0x18006b176  mov     rbx, rcx
0x18006b179  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b180  lea     rdi, WPP_GLOBAL_Control
0x18006b187  cmp     rcx, rdi
0x18006b18a  jz      short loc_18006B1AE
0x18006b18c  test    byte ptr [rcx+1Ch], 40h
0x18006b190  jz      short loc_18006B1AE
0x18006b192  mov     rcx, [rcx+10h]
0x18006b196  lea     r8, WPP_5dd97abf89e6303816d5c30271157f49_Traceguids
0x18006b19d  mov     edx, 27h ; '''
0x18006b1a2  call    WPP_SF_
0x18006b1a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b1ae  mov     rdx, [rbx+0E8h]; Timer
0x18006b1b5  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18006b1b9  jz      short loc_18006B221
0x18006b1bb  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18006b1bf  xor     ecx, ecx; TimerQueue
0x18006b1c1  call    cs:__imp_DeleteTimerQueueTimer
0x18006b1c7  test    eax, eax
0x18006b1c9  jz      short loc_18006B1D8
0x18006b1cb  mov     qword ptr [rbx+0E8h], 0FFFFFFFFFFFFFFFFh
0x18006b1d6  jmp     short loc_18006B241
0x18006b1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b1df  cmp     rcx, rdi
0x18006b1e2  jz      loc_18006B268
0x18006b1e8  test    byte ptr [rcx+1Ch], 2
0x18006b1ec  jz      short loc_18006B248
0x18006b1ee  call    cs:__imp_GetLastError
0x18006b1f4  test    eax, eax
0x18006b1f6  jle     short loc_18006B200
0x18006b1f8  movzx   eax, ax
0x18006b1fb  or      eax, 80070000h
0x18006b200  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b207  lea     r8, WPP_5dd97abf89e6303816d5c30271157f49_Traceguids
0x18006b20e  mov     edx, 28h ; '('
0x18006b213  mov     r9d, eax
0x18006b216  mov     rcx, [rcx+10h]
0x18006b21a  call    WPP_SF_d
0x18006b21f  jmp     short loc_18006B241
0x18006b221  cmp     rcx, rdi
0x18006b224  jz      short loc_18006B268
0x18006b226  test    byte ptr [rcx+1Ch], 2
0x18006b22a  jz      short loc_18006B248
0x18006b22c  mov     rcx, [rcx+10h]
0x18006b230  lea     r8, WPP_5dd97abf89e6303816d5c30271157f49_Traceguids
0x18006b237  mov     edx, 29h ; ')'
0x18006b23c  call    WPP_SF_
0x18006b241  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b248  cmp     rcx, rdi
0x18006b24b  jz      short loc_18006B268
0x18006b24d  test    byte ptr [rcx+1Ch], 40h
0x18006b251  jz      short loc_18006B268
0x18006b253  mov     rcx, [rcx+10h]
0x18006b257  lea     r8, WPP_5dd97abf89e6303816d5c30271157f49_Traceguids
0x18006b25e  mov     edx, 2Ah ; '*'
0x18006b263  call    WPP_SF_
0x18006b268  mov     rbx, [rsp+28h+arg_0]
0x18006b26d  add     rsp, 20h
0x18006b271  pop     rdi
0x18006b272  retn
```
