# SxStopTracing(ushort const *)

- ea: `0x14000fd0c`
- end: `0x14000fe14`
- name: `?SxStopTracing@@YAJPEBG@Z`
- size: `264`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1400039e4`
- `0x140003dc4`

## callees

- `0x140002e1c`
- `0x14000e324`
- `0x14000e41c`
- `0x14000ec40`
- `0x14000fd0c`

## import_xrefs

- `ADVAPI32!ControlTraceW` at `0x14000fdb8`
- `ADVAPI32!ControlTraceW` at `0x14000fdd0`
- `ADVAPI32!ControlTraceW` at `0x14000fdb8`
- `ADVAPI32!ControlTraceW` at `0x14000fdd0`
- `ole32!CoTaskMemFree` at `0x14000fdf5`
- `ole32!CoTaskMemFree` at `0x14000fdf5`

## string_xrefs

- `0x14000fdaf`: `BuiltInSrTasksTracing`
- `0x14000fdc4`: `BuiltInSrTasksTracing`

## pseudocode

```c
__int64 __fastcall SxStopTracing(struct _EVENT_TRACE_PROPERTIES *a1)
{
  int v1; // eax
  struct _EVENT_TRACE_PROPERTIES *v2; // rbx
  bool v3; // sf
  __int16 v4; // ax
  signed int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-40h] BYREF
  __int16 v9; // [rsp+24h] [rbp-3Ch]
  __int16 v10; // [rsp+26h] [rbp-3Ah]
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+70h] [rbp+10h] BYREF

  Properties = a1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "SxStopTracing", 0x2ADu, 1u);
  Properties = 0;
  v9 = 689;
  v8 = 0;
  v1 = SxAllocateEventTraceProp(&Properties);
  v2 = Properties;
  v3 = v1 < 0;
  v8 = v1;
  v4 = 691;
  if ( v3 )
    goto LABEL_5;
  v9 = 691;
  ControlTraceW(0, L"BuiltInSrTasksTracing", Properties, 3u);
  v5 = ControlTraceW(0, L"BuiltInSrTasksTracing", v2, 1u);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  v8 = v5;
  v3 = v5 < 0;
  v4 = 695;
  if ( v3 )
LABEL_5:
    v10 = v4;
  else
    v9 = 695;
  CoTaskMemFree(v2);
  v6 = v8;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return v6;
}

```

## disassembly

```asm
0x14000fd0c  mov     [rsp-8+arg_8], rbx
0x14000fd11  mov     [rsp-8+Properties], rcx
0x14000fd16  push    rbp
0x14000fd17  mov     rbp, rsp
0x14000fd1a  sub     rsp, 60h
0x14000fd1e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd25  lea     rax, WPP_GLOBAL_Control
0x14000fd2c  cmp     rcx, rax
0x14000fd2f  jz      short loc_14000FD4F
0x14000fd31  test    dword ptr [rcx+1Ch], 20000000h
0x14000fd38  jz      short loc_14000FD4F
0x14000fd3a  mov     rcx, [rcx+10h]
0x14000fd3e  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x14000fd45  mov     edx, 19h
0x14000fd4a  call    WPP_SF_
0x14000fd4f  mov     r9d, 1; unsigned __int16
0x14000fd55  lea     rdx, aSxstoptracing; "SxStopTracing"
0x14000fd5c  mov     r8d, 2ADh; unsigned __int16
0x14000fd62  lea     rcx, [rbp+var_40]; this
0x14000fd66  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x14000fd6b  mov     eax, 2B1h
0x14000fd70  mov     [rbp+Properties], 0
0x14000fd78  lea     rcx, [rbp+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x14000fd7c  mov     [rbp+var_3C], ax
0x14000fd80  mov     [rbp+var_40], 0
0x14000fd87  call    ?SxAllocateEventTraceProp@@YAJPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; SxAllocateEventTraceProp(_EVENT_TRACE_PROPERTIES * *)
0x14000fd8c  mov     rbx, [rbp+Properties]
0x14000fd90  test    eax, eax
0x14000fd92  mov     [rbp+var_40], eax
0x14000fd95  mov     eax, 2B3h
0x14000fd9a  jns     short loc_14000FDA2
0x14000fd9c  mov     [rbp+var_3A], ax
0x14000fda0  jmp     short loc_14000FDF2
0x14000fda2  mov     r9d, 3; ControlCode
0x14000fda8  mov     [rbp+var_3C], ax
0x14000fdac  mov     r8, rbx; Properties
0x14000fdaf  lea     rdx, aBuiltinsrtasks; "BuiltInSrTasksTracing"
0x14000fdb6  xor     ecx, ecx; TraceHandle
0x14000fdb8  call    cs:__imp_ControlTraceW
0x14000fdbe  mov     r9d, 1; ControlCode
0x14000fdc4  lea     rdx, aBuiltinsrtasks; "BuiltInSrTasksTracing"
0x14000fdcb  mov     r8, rbx; Properties
0x14000fdce  xor     ecx, ecx; TraceHandle
0x14000fdd0  call    cs:__imp_ControlTraceW
0x14000fdd6  test    eax, eax
0x14000fdd8  jle     short loc_14000FDE2
0x14000fdda  movzx   eax, ax
0x14000fddd  or      eax, 80070000h
0x14000fde2  mov     [rbp+var_40], eax
0x14000fde5  test    eax, eax
0x14000fde7  mov     eax, 2B7h
0x14000fdec  js      short loc_14000FD9C
0x14000fdee  mov     [rbp+var_3C], ax
0x14000fdf2  mov     rcx, rbx; pv
0x14000fdf5  call    cs:__imp_CoTaskMemFree
0x14000fdfb  mov     ebx, [rbp+var_40]
0x14000fdfe  lea     rcx, [rbp+var_40]; this
0x14000fe02  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x14000fe07  mov     eax, ebx
0x14000fe09  mov     rbx, [rsp+60h+arg_8]
0x14000fe0e  add     rsp, 60h
0x14000fe12  pop     rbp
0x14000fe13  retn
```
