# CTieringEngineService::WaitForTieringEngineToStop(void)

- ea: `0x1400046d4`
- end: `0x1400047b6`
- name: `?WaitForTieringEngineToStop@CTieringEngineService@@QEAAXXZ`
- size: `226`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x1400037bc`
- `0x1400047e0`

## callees

- `0x140001a00`
- `0x1400045d0`
- `0x1400046d4`
- `0x140004a40`
- `0x140005504`
- `0x140008c04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004777`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004777`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400046f6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400046f6`

## pseudocode

```c
void __fastcall CTieringEngineService::WaitForTieringEngineToStop(HANDLE *this)
{
  CTieringEngineLib *v2; // rcx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  PVOID v5; // rbx

  if ( TieringEngineLibInstance )
  {
    SetEvent(this[85]);
    CTieringEngineLib::SignalShutdownAndWait(v2);
    if ( this[86] )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        do
        {
LABEL_12:
          if ( WaitForSingleObject(this[86], 0x1388u) != 258 )
            goto LABEL_13;
          CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus((__int64)this, 3);
          v3 = WPP_GLOBAL_Control;
        }
        while ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
             || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
             || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u );
        v4 = 21;
      }
      else
      {
        v4 = 20;
      }
      WPP_SF_(v3[2], v4, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids);
      goto LABEL_12;
    }
LABEL_13:
    v5 = TieringEngineLibInstance;
    if ( TieringEngineLibInstance )
    {
      CTieringEngineLib::~CTieringEngineLib((CTieringEngineLib *)TieringEngineLibInstance);
      operator delete(v5);
    }
    TieringEngineLibInstance = 0;
  }
}

```

## disassembly

```asm
0x1400046d4  mov     [rsp+arg_0], rbx
0x1400046d9  push    rsi
0x1400046da  sub     rsp, 20h
0x1400046de  cmp     cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA, 0; CTieringEngineLib * TieringEngineLibInstance
0x1400046e6  mov     rbx, rcx
0x1400046e9  jz      loc_1400047AB
0x1400046ef  mov     rcx, [rcx+2A8h]; hEvent
0x1400046f6  call    cs:__imp_SetEvent
0x1400046fc  call    ?SignalShutdownAndWait@CTieringEngineLib@@QEAAXXZ; CTieringEngineLib::SignalShutdownAndWait(void)
0x140004701  cmp     qword ptr [rbx+2B0h], 0
0x140004709  jz      short loc_140004784
0x14000470b  mov     rcx, cs:WPP_GLOBAL_Control
0x140004712  lea     rsi, WPP_GLOBAL_Control
0x140004719  cmp     rcx, rsi
0x14000471c  jz      short loc_14000476B
0x14000471e  test    byte ptr [rcx+1Ch], 1
0x140004722  jz      short loc_14000476B
0x140004724  cmp     byte ptr [rcx+19h], 4
0x140004728  jb      short loc_14000476B
0x14000472a  mov     edx, 14h
0x14000472f  jmp     short loc_14000475B
0x140004731  mov     edx, 3
0x140004736  mov     rcx, rbx
0x140004739  call    ?SetServiceStatus@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@QEAAXK@Z; CMyAtlServiceModuleT<CTieringEngineService,102>::SetServiceStatus(ulong)
0x14000473e  mov     rcx, cs:WPP_GLOBAL_Control
0x140004745  cmp     rcx, rsi
0x140004748  jz      short loc_14000476B
0x14000474a  test    byte ptr [rcx+1Ch], 1
0x14000474e  jz      short loc_14000476B
0x140004750  cmp     byte ptr [rcx+19h], 4
0x140004754  jb      short loc_14000476B
0x140004756  mov     edx, 15h
0x14000475b  mov     rcx, [rcx+10h]
0x14000475f  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140004766  call    WPP_SF_
0x14000476b  mov     rcx, [rbx+2B0h]; hHandle
0x140004772  mov     edx, 1388h; dwMilliseconds
0x140004777  call    cs:__imp_WaitForSingleObject
0x14000477d  cmp     eax, 102h
0x140004782  jz      short loc_140004731
0x140004784  mov     rbx, cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA; CTieringEngineLib * TieringEngineLibInstance
0x14000478b  test    rbx, rbx
0x14000478e  jz      short loc_1400047A0
0x140004790  mov     rcx, rbx; this
0x140004793  call    ??1CTieringEngineLib@@QEAA@XZ; CTieringEngineLib::~CTieringEngineLib(void)
0x140004798  mov     rcx, rbx; Block
0x14000479b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400047a0  mov     cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA, 0; CTieringEngineLib * TieringEngineLibInstance
0x1400047ab  mov     rbx, [rsp+28h+arg_0]
0x1400047b0  add     rsp, 20h
0x1400047b4  pop     rsi
0x1400047b5  retn
```
