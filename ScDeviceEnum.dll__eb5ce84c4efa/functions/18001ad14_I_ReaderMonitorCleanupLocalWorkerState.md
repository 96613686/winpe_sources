# I_ReaderMonitorCleanupLocalWorkerState

- ea: `0x18001ad14`
- end: `0x18001ae4d`
- name: `I_ReaderMonitorCleanupLocalWorkerState`
- size: `313`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001ba4c`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x18001714c`
- `0x18001ad14`
- `0x18001cc6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001adf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001adf9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001addc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001addc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ada9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001adc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ada9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001adc2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001ad83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001ad83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001ad90`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001ad90`

## pseudocode

```c
__int64 __fastcall I_ReaderMonitorCleanupLocalWorkerState(__int64 a1)
{
  PVOID v2; // rcx
  unsigned int v3; // esi
  struct _TP_CLEANUP_GROUP *v4; // rcx
  void *v5; // rcx

  WppTraceIndent(a1, 0);
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( a1 )
  {
    v4 = *(struct _TP_CLEANUP_GROUP **)(a1 + 344);
    v3 = 0;
    if ( v4 )
    {
      CloseThreadpoolCleanupGroupMembers(v4, 0, 0);
      CloseThreadpoolCleanupGroup(*(PTP_CLEANUP_GROUP *)(a1 + 344));
      *(_QWORD *)(a1 + 344) = 0;
    }
    v5 = *(void **)(a1 + 352);
    if ( v5 )
    {
      CloseHandle(v5);
      *(_QWORD *)(a1 + 352) = 0;
    }
    v2 = *(PVOID *)(a1 + 360);
    if ( v2 )
    {
      CloseHandle(v2);
      *(_QWORD *)(a1 + 360) = 0;
    }
    if ( *(_QWORD *)(a1 + 368) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
      I_ReaderListFree(*(_QWORD **)(a1 + 368));
      *(_QWORD *)(a1 + 368) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
    }
  }
  else
  {
    v3 = 87;
  }
  WppTraceIndent(v2, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      201,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v3);
  }
  return v3;
}

```

## disassembly

```asm
0x18001ad14  push    rbx
0x18001ad16  push    rsi
0x18001ad17  push    rdi
0x18001ad18  push    r14
0x18001ad1a  sub     rsp, 38h
0x18001ad1e  xor     edx, edx
0x18001ad20  mov     rdi, rcx
0x18001ad23  call    WppTraceIndent
0x18001ad28  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad2f  lea     r14, WPP_GLOBAL_Control
0x18001ad36  cmp     rcx, r14
0x18001ad39  jz      short loc_18001AD63
0x18001ad3b  test    byte ptr [rcx+1Ch], 2
0x18001ad3f  jz      short loc_18001AD63
0x18001ad41  cmp     byte ptr [rcx+19h], 5
0x18001ad45  jb      short loc_18001AD63
0x18001ad47  mov     r9, cs:WPP_pszIndent
0x18001ad4e  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001ad55  mov     rcx, [rcx+10h]
0x18001ad59  mov     edx, 0C8h
0x18001ad5e  call    WPP_SF_s
0x18001ad63  test    rdi, rdi
0x18001ad66  jnz     short loc_18001AD70
0x18001ad68  lea     esi, [rdi+57h]
0x18001ad6b  jmp     loc_18001ADFF
0x18001ad70  mov     rcx, [rdi+158h]; ptpcg
0x18001ad77  xor     esi, esi
0x18001ad79  test    rcx, rcx
0x18001ad7c  jz      short loc_18001AD9D
0x18001ad7e  xor     r8d, r8d; pvCleanupContext
0x18001ad81  xor     edx, edx; fCancelPendingCallbacks
0x18001ad83  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001ad89  mov     rcx, [rdi+158h]; ptpcg
0x18001ad90  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001ad96  mov     [rdi+158h], rsi
0x18001ad9d  mov     rcx, [rdi+160h]; hObject
0x18001ada4  test    rcx, rcx
0x18001ada7  jz      short loc_18001ADB6
0x18001ada9  call    cs:__imp_CloseHandle
0x18001adaf  mov     [rdi+160h], rsi
0x18001adb6  mov     rcx, [rdi+168h]; hObject
0x18001adbd  test    rcx, rcx
0x18001adc0  jz      short loc_18001ADCF
0x18001adc2  call    cs:__imp_CloseHandle
0x18001adc8  mov     [rdi+168h], rsi
0x18001adcf  cmp     [rdi+170h], rsi
0x18001add6  jz      short loc_18001ADFF
0x18001add8  lea     rcx, [rdi+30h]; lpCriticalSection
0x18001addc  call    cs:__imp_EnterCriticalSection
0x18001ade2  mov     rcx, [rdi+170h]
0x18001ade9  call    I_ReaderListFree
0x18001adee  lea     rcx, [rdi+30h]; lpCriticalSection
0x18001adf2  mov     [rdi+170h], rsi
0x18001adf9  call    cs:__imp_LeaveCriticalSection
0x18001adff  mov     edx, 1
0x18001ae04  call    WppTraceIndent
0x18001ae09  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae10  cmp     rcx, r14
0x18001ae13  jz      short loc_18001AE41
0x18001ae15  test    byte ptr [rcx+1Ch], 2
0x18001ae19  jz      short loc_18001AE41
0x18001ae1b  cmp     byte ptr [rcx+19h], 5
0x18001ae1f  jb      short loc_18001AE41
0x18001ae21  mov     r9, cs:WPP_pszIndent
0x18001ae28  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001ae2f  mov     rcx, [rcx+10h]
0x18001ae33  mov     edx, 0C9h
0x18001ae38  mov     [rsp+58h+var_38], esi
0x18001ae3c  call    WPP_SF_sd
0x18001ae41  mov     eax, esi
0x18001ae43  add     rsp, 38h
0x18001ae47  pop     r14
0x18001ae49  pop     rdi
0x18001ae4a  pop     rsi
0x18001ae4b  pop     rbx
0x18001ae4c  retn
```
