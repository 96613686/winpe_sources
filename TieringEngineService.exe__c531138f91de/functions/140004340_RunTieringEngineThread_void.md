# RunTieringEngineThread(void *)

- ea: `0x140004340`
- end: `0x14000443a`
- name: `?RunTieringEngineThread@@YAKPEAX@Z`
- size: `250`
- prototype: `__int64 __fastcall(void **Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140004340`
- `0x140004a68`
- `0x140007f18`
- `0x140008e04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000434d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000434d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000442c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000442c`

## pseudocode

```c
__int64 __fastcall RunTieringEngineThread(void **Parameter)
{
  HRESULT v2; // eax
  CTieringEngineLib *v3; // rcx
  unsigned int v4; // ebx
  int started; // eax
  CTieringEngineLib *v6; // rcx
  _QWORD *v7; // r10
  __int64 v8; // rdx

  v2 = CoInitializeEx(0, 0);
  if ( v2 >= 0 )
  {
    if ( TieringEngineLibInstance )
    {
      started = CTieringEngineLib::StartTieringEngine(v3, Parameter[85]);
      v4 = 1;
      if ( started < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_19;
        }
        v8 = 28;
        goto LABEL_17;
      }
      started = CTieringEngineLib::ProcessTieringEvents(v6);
      if ( started < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_19;
        }
        v8 = 29;
LABEL_17:
        WPP_SF_d(v7[2], v8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids, (unsigned int)started);
LABEL_19:
        CoUninitialize();
        return v4;
      }
    }
    v4 = 0;
    goto LABEL_19;
  }
  v4 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids, (unsigned int)v2);
  }
  return v4;
}

```

## disassembly

```asm
0x140004340  push    rbx
0x140004342  sub     rsp, 20h
0x140004346  mov     rbx, rcx
0x140004349  xor     edx, edx; dwCoInit
0x14000434b  xor     ecx, ecx; pvReserved
0x14000434d  call    cs:__imp_CoInitializeEx
0x140004353  test    eax, eax
0x140004355  jns     short loc_1400043A3
0x140004357  mov     r10, cs:WPP_GLOBAL_Control
0x14000435e  lea     rcx, WPP_GLOBAL_Control
0x140004365  mov     ebx, 1
0x14000436a  cmp     r10, rcx
0x14000436d  jz      loc_140004432
0x140004373  test    [r10+1Ch], bl
0x140004377  jz      loc_140004432
0x14000437d  cmp     byte ptr [r10+19h], 2
0x140004382  jb      loc_140004432
0x140004388  mov     rcx, [r10+10h]
0x14000438c  lea     edx, [rbx+1Ah]
0x14000438f  mov     r9d, eax
0x140004392  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140004399  call    WPP_SF_d
0x14000439e  jmp     loc_140004432
0x1400043a3  cmp     cs:?TieringEngineLibInstance@@3PEAVCTieringEngineLib@@EA, 0; CTieringEngineLib * TieringEngineLibInstance
0x1400043ab  jz      short loc_14000442A
0x1400043ad  mov     rdx, [rbx+2A8h]; void *
0x1400043b4  call    ?StartTieringEngine@CTieringEngineLib@@QEAAJPEAX@Z; CTieringEngineLib::StartTieringEngine(void *)
0x1400043b9  mov     ebx, 1
0x1400043be  test    eax, eax
0x1400043c0  jns     short loc_1400043E7
0x1400043c2  mov     r10, cs:WPP_GLOBAL_Control
0x1400043c9  lea     rcx, WPP_GLOBAL_Control
0x1400043d0  cmp     r10, rcx
0x1400043d3  jz      short loc_14000442C
0x1400043d5  test    [r10+1Ch], bl
0x1400043d9  jz      short loc_14000442C
0x1400043db  cmp     byte ptr [r10+19h], 2
0x1400043e0  jb      short loc_14000442C
0x1400043e2  lea     edx, [rbx+1Bh]
0x1400043e5  jmp     short loc_140004415
0x1400043e7  call    ?ProcessTieringEvents@CTieringEngineLib@@QEAAJXZ; CTieringEngineLib::ProcessTieringEvents(void)
0x1400043ec  test    eax, eax
0x1400043ee  jns     short loc_14000442A
0x1400043f0  mov     r10, cs:WPP_GLOBAL_Control
0x1400043f7  lea     rcx, WPP_GLOBAL_Control
0x1400043fe  cmp     r10, rcx
0x140004401  jz      short loc_14000442C
0x140004403  test    [r10+1Ch], bl
0x140004407  jz      short loc_14000442C
0x140004409  cmp     byte ptr [r10+19h], 2
0x14000440e  jb      short loc_14000442C
0x140004410  mov     edx, 1Dh
0x140004415  mov     rcx, [r10+10h]
0x140004419  lea     r8, WPP_ef66010c4da23316be47f4e1f0858c5c_Traceguids
0x140004420  mov     r9d, eax
0x140004423  call    WPP_SF_d
0x140004428  jmp     short loc_14000442C
0x14000442a  xor     ebx, ebx
0x14000442c  call    cs:__imp_CoUninitialize
0x140004432  mov     eax, ebx
0x140004434  add     rsp, 20h
0x140004438  pop     rbx
0x140004439  retn
```
