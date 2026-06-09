# SxCheckWBDiagSession(void)

- ea: `0x14000ed4c`
- end: `0x14000ef36`
- name: `?SxCheckWBDiagSession@@YAJXZ`
- size: `490`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x1400039e4`

## callees

- `0x140002e1c`
- `0x1400054f4`
- `0x140005554`
- `0x14000e324`
- `0x14000e41c`
- `0x14000ec40`
- `0x14000ed4c`

## import_xrefs

- `ADVAPI32!ControlTraceW` at `0x14000ee31`
- `ADVAPI32!ControlTraceW` at `0x14000ee31`
- `ole32!CoTaskMemFree` at `0x14000ee57`
- `ole32!CoTaskMemFree` at `0x14000ee57`

## pseudocode

```c
__int64 SxCheckWBDiagSession(void)
{
  __int16 v0; // ax
  signed int v1; // eax
  bool v2; // sf
  int v3; // ebx
  unsigned int v4; // ebx
  int v6; // [rsp+30h] [rbp-39h] BYREF
  __int16 v7; // [rsp+34h] [rbp-35h]
  __int16 v8; // [rsp+36h] [rbp-33h]
  int v9; // [rsp+68h] [rbp-1h] BYREF
  __int16 v10; // [rsp+6Ch] [rbp+3h]
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+D0h] [rbp+67h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "SxCheckWBDiagSession", 293, 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v6, "SxQueryTraceSession", 93, 1);
  Properties = 0;
  v7 = 97;
  v6 = 0;
  v6 = SxAllocateEventTraceProp(&Properties);
  v0 = 99;
  if ( v6 < 0 )
    goto LABEL_8;
  v7 = 99;
  v1 = ControlTraceW(0, L"blblog", Properties, 0);
  if ( v1 > 0 )
    v1 = (unsigned __int16)v1 | 0x80070000;
  v6 = v1;
  v2 = v1 < 0;
  v0 = 101;
  if ( v2 )
LABEL_8:
    v8 = v0;
  else
    v7 = 101;
  CoTaskMemFree(Properties);
  v3 = v6;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v6);
  if ( v3 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids, L"blblog");
    v9 = 1;
    v10 = 313;
  }
  else if ( v3 == -2147020695 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids, L"blblog");
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids,
      (unsigned int)L"blblog",
      v3);
  }
  v4 = v9;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return v4;
}

```

## disassembly

```asm
0x14000ed4c  push    rbp
0x14000ed4e  push    rbx
0x14000ed4f  push    rsi
0x14000ed50  push    rdi
0x14000ed51  lea     rbp, [rsp-3Fh]
0x14000ed56  sub     rsp, 0A8h
0x14000ed5d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ed64  lea     rdi, WPP_GLOBAL_Control
0x14000ed6b  lea     rsi, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x14000ed72  mov     ebx, 20000000h
0x14000ed77  cmp     rcx, rdi
0x14000ed7a  jz      short loc_14000ED92
0x14000ed7c  test    [rcx+1Ch], ebx
0x14000ed7f  jz      short loc_14000ED92
0x14000ed81  mov     rcx, [rcx+10h]
0x14000ed85  mov     edx, 0Fh
0x14000ed8a  mov     r8, rsi
0x14000ed8d  call    WPP_SF_
0x14000ed92  mov     r9d, 1; unsigned __int16
0x14000ed98  lea     rdx, aSxcheckwbdiags; "SxCheckWBDiagSession"
0x14000ed9f  mov     r8d, 125h; unsigned __int16
0x14000eda5  lea     rcx, [rbp+57h+var_58]; this
0x14000eda9  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000edae  mov     rcx, cs:WPP_GLOBAL_Control
0x14000edb5  cmp     rcx, rdi
0x14000edb8  jz      short loc_14000EDD0
0x14000edba  test    [rcx+1Ch], ebx
0x14000edbd  jz      short loc_14000EDD0
0x14000edbf  mov     rcx, [rcx+10h]
0x14000edc3  mov     edx, 0Ch
0x14000edc8  mov     r8, rsi
0x14000edcb  call    WPP_SF_
0x14000edd0  mov     r9d, 1; unsigned __int16
0x14000edd6  lea     rdx, aSxquerytracese; "SxQueryTraceSession"
0x14000eddd  lea     rcx, [rbp+57h+var_90]; this
0x14000ede1  lea     r8d, [r9+5Ch]; unsigned __int16
0x14000ede5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000edea  mov     eax, 61h ; 'a'
0x14000edef  mov     [rbp+57h+Properties], 0
0x14000edf7  lea     rcx, [rbp+57h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x14000edfb  mov     [rbp+57h+var_8C], ax
0x14000edff  mov     [rbp+57h+var_90], 0
0x14000ee06  call    ?SxAllocateEventTraceProp@@YAJPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; SxAllocateEventTraceProp(_EVENT_TRACE_PROPERTIES * *)
0x14000ee0b  mov     [rbp+57h+var_90], eax
0x14000ee0e  test    eax, eax
0x14000ee10  mov     eax, 63h ; 'c'
0x14000ee15  jns     short loc_14000EE1D
0x14000ee17  mov     [rbp+57h+var_8A], ax
0x14000ee1b  jmp     short loc_14000EE53
0x14000ee1d  mov     r8, [rbp+57h+Properties]; Properties
0x14000ee21  lea     rdx, InstanceName; "blblog"
0x14000ee28  xor     r9d, r9d; ControlCode
0x14000ee2b  mov     [rbp+57h+var_8C], ax
0x14000ee2f  xor     ecx, ecx; TraceHandle
0x14000ee31  call    cs:__imp_ControlTraceW
0x14000ee37  test    eax, eax
0x14000ee39  jle     short loc_14000EE43
0x14000ee3b  movzx   eax, ax
0x14000ee3e  or      eax, 80070000h
0x14000ee43  mov     [rbp+57h+var_90], eax
0x14000ee46  test    eax, eax
0x14000ee48  mov     eax, 65h ; 'e'
0x14000ee4d  js      short loc_14000EE17
0x14000ee4f  mov     [rbp+57h+var_8C], ax
0x14000ee53  mov     rcx, [rbp+57h+Properties]; pv
0x14000ee57  call    cs:__imp_CoTaskMemFree
0x14000ee5d  mov     ebx, [rbp+57h+var_90]
0x14000ee60  lea     rcx, [rbp+57h+var_90]; this
0x14000ee64  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x14000ee69  test    ebx, ebx
0x14000ee6b  jns     short loc_14000EEDF
0x14000ee6d  cmp     ebx, 80071069h
0x14000ee73  jnz     short loc_14000EEAC
0x14000ee75  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ee7c  cmp     rcx, rdi
0x14000ee7f  jz      loc_14000EF1C
0x14000ee85  test    dword ptr [rcx+1Ch], 8000000h
0x14000ee8c  jz      loc_14000EF1C
0x14000ee92  mov     rcx, [rcx+10h]
0x14000ee96  lea     r9, InstanceName; "blblog"
0x14000ee9d  mov     edx, 10h
0x14000eea2  mov     r8, rsi
0x14000eea5  call    WPP_SF_S
0x14000eeaa  jmp     short loc_14000EF1C
0x14000eeac  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eeb3  cmp     rcx, rdi
0x14000eeb6  jz      short loc_14000EF1C
0x14000eeb8  test    dword ptr [rcx+1Ch], 4000000h
0x14000eebf  jz      short loc_14000EF1C
0x14000eec1  mov     rcx, [rcx+10h]
0x14000eec5  lea     r9, InstanceName; "blblog"
0x14000eecc  mov     edx, 11h
0x14000eed1  mov     [rsp+0C0h+var_A0], ebx
0x14000eed5  mov     r8, rsi
0x14000eed8  call    WPP_SF_SD
0x14000eedd  jmp     short loc_14000EF1C
0x14000eedf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eee6  cmp     rcx, rdi
0x14000eee9  jz      short loc_14000EF0C
0x14000eeeb  test    dword ptr [rcx+1Ch], 8000000h
0x14000eef2  jz      short loc_14000EF0C
0x14000eef4  mov     rcx, [rcx+10h]
0x14000eef8  lea     r9, InstanceName; "blblog"
0x14000eeff  mov     edx, 12h
0x14000ef04  mov     r8, rsi
0x14000ef07  call    WPP_SF_S
0x14000ef0c  mov     eax, 139h
0x14000ef11  mov     [rbp+57h+var_58], 1
0x14000ef18  mov     [rbp+57h+var_54], ax
0x14000ef1c  mov     ebx, [rbp+57h+var_58]
0x14000ef1f  lea     rcx, [rbp+57h+var_58]; this
0x14000ef23  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x14000ef28  mov     eax, ebx
0x14000ef2a  add     rsp, 0A8h
0x14000ef31  pop     rdi
0x14000ef32  pop     rsi
0x14000ef33  pop     rbx
0x14000ef34  pop     rbp
0x14000ef35  retn
```
