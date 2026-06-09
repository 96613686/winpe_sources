# BdeSvcDeletePersistentRequestTimer(void)

- ea: `0x180004894`
- end: `0x18000496b`
- name: `?BdeSvcDeletePersistentRequestTimer@@YAXXZ`
- size: `215`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800042f0`
- `0x18005b530`
- `0x18005b934`

## callees

- `0x180004894`
- `0x180009f30`
- `0x180009f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048f0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800048e0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800048e0`

## pseudocode

```c
void BdeSvcDeletePersistentRequestTimer(void)
{
  PVOID *v0; // rcx
  signed int LastError; // eax

  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_8a3f59d54824346350fe913136af4d55_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( g_hPersistentReqTimer )
  {
    if ( !DeleteTimerQueueTimer(0, g_hPersistentReqTimer, 0) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v0 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_12;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_8a3f59d54824346350fe913136af4d55_Traceguids,
        (unsigned int)LastError);
    }
    v0 = (PVOID *)WPP_GLOBAL_Control;
LABEL_12:
    g_hPersistentReqTimer = 0;
  }
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 0x20) != 0 )
    WPP_SF_(v0[2], 18, WPP_8a3f59d54824346350fe913136af4d55_Traceguids);
}

```

## disassembly

```asm
0x180004894  push    rbx
0x180004896  sub     rsp, 20h
0x18000489a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048a1  lea     rbx, WPP_GLOBAL_Control
0x1800048a8  cmp     rcx, rbx
0x1800048ab  jz      short loc_1800048CF
0x1800048ad  test    byte ptr [rcx+1Ch], 20h
0x1800048b1  jz      short loc_1800048CF
0x1800048b3  mov     rcx, [rcx+10h]
0x1800048b7  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x1800048be  mov     edx, 10h
0x1800048c3  call    WPP_SF_
0x1800048c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048cf  mov     rdx, cs:?g_hPersistentReqTimer@@3PEAXEA; Timer
0x1800048d6  test    rdx, rdx
0x1800048d9  jz      short loc_180004944
0x1800048db  xor     r8d, r8d; CompletionEvent
0x1800048de  xor     ecx, ecx; TimerQueue
0x1800048e0  call    cs:__imp_DeleteTimerQueueTimer
0x1800048e7  nop     dword ptr [rax+rax+00h]
0x1800048ec  test    eax, eax
0x1800048ee  jnz     short loc_180004932
0x1800048f0  call    cs:__imp_GetLastError
0x1800048f7  nop     dword ptr [rax+rax+00h]
0x1800048fc  test    eax, eax
0x1800048fe  jle     short loc_180004908
0x180004900  movzx   eax, ax
0x180004903  or      eax, 80070000h
0x180004908  mov     rcx, cs:WPP_GLOBAL_Control
0x18000490f  cmp     rcx, rbx
0x180004912  jz      short loc_180004939
0x180004914  test    byte ptr [rcx+1Ch], 2
0x180004918  jz      short loc_180004939
0x18000491a  mov     rcx, [rcx+10h]
0x18000491e  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x180004925  mov     edx, 11h
0x18000492a  mov     r9d, eax
0x18000492d  call    WPP_SF_d
0x180004932  mov     rcx, cs:WPP_GLOBAL_Control
0x180004939  mov     cs:?g_hPersistentReqTimer@@3PEAXEA, 0; void * g_hPersistentReqTimer
0x180004944  cmp     rcx, rbx
0x180004947  jz      short loc_180004964
0x180004949  test    byte ptr [rcx+1Ch], 20h
0x18000494d  jz      short loc_180004964
0x18000494f  mov     rcx, [rcx+10h]
0x180004953  lea     r8, WPP_8a3f59d54824346350fe913136af4d55_Traceguids
0x18000495a  mov     edx, 12h
0x18000495f  call    WPP_SF_
0x180004964  add     rsp, 20h
0x180004968  pop     rbx
0x180004969  retn
```
