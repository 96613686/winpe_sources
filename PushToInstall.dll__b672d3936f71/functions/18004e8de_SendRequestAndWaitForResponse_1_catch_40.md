# _SendRequestAndWaitForResponse_::_1_::catch$40

- ea: `0x18004e8de`
- end: `0x18004e979`
- name: `_SendRequestAndWaitForResponse_::_1_::catch$40`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180022724`
- `0x18004e8de`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004e93c`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004e93c`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18004e957`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18004e957`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18004e961`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18004e961`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18004e946`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18004e946`

## string_xrefs

- `0x18004e91f`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
__int64 __fastcall SendRequestAndWaitForResponse_::_1_::catch_40(__int64 a1, __int64 a2)
{
  _QWORD *v3; // rax
  const char *v4; // rdx

  v3 = *(_QWORD **)(a2 + 80);
  if ( v3[3] > 7u )
    v3 = (_QWORD *)*v3;
  v4 = *(const char **)(a2 + 96);
  if ( *((_QWORD *)v4 + 3) > 7u )
    v4 = *(const char **)v4;
  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 472),
    (void *)0x116,
    (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
    "Failed to connect to %ws with proxy %ws",
    v4,
    v3);
  *(_OWORD *)(a2 + 104) = 0;
  __ExceptionPtrCreate((void *)(a2 + 104));
  __ExceptionPtrCurrentException((void *)(a2 + 104));
  __ExceptionPtrAssign((void *)(a2 + 144), (const void *)(a2 + 104));
  __ExceptionPtrDestroy((void *)(a2 + 104));
  return 0;
}

```

## disassembly

```asm
0x18004e8de  mov     [rsp+arg_8], rdx
0x18004e8e3  push    rbp
0x18004e8e4  sub     rsp, 40h
0x18004e8e8  mov     rbp, rdx
0x18004e8eb  mov     rax, [rbp+50h]
0x18004e8ef  cmp     qword ptr [rax+18h], 7
0x18004e8f4  jbe     short loc_18004E8F9
0x18004e8f6  mov     rax, [rax]
0x18004e8f9  mov     rdx, [rbp+60h]
0x18004e8fd  cmp     qword ptr [rdx+18h], 7
0x18004e902  jbe     short loc_18004E907
0x18004e904  mov     rdx, [rdx]
0x18004e907  mov     rcx, [rbp+1D8h]; this
0x18004e90e  mov     [rsp+48h+var_20], rax
0x18004e913  mov     [rsp+48h+var_28], rdx; char *
0x18004e918  lea     r9, aFailedToConnec_2; "Failed to connect to %ws with proxy %ws"
0x18004e91f  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x18004e926  mov     edx, 116h; void *
0x18004e92b  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x18004e930  xorps   xmm0, xmm0
0x18004e933  movdqu  xmmword ptr [rbp+68h], xmm0
0x18004e938  lea     rcx, [rbp+68h]
0x18004e93c  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18004e942  lea     rcx, [rbp+68h]
0x18004e946  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18004e94c  lea     rdx, [rbp+68h]
0x18004e950  lea     rcx, [rbp+90h]
0x18004e957  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18004e95d  lea     rcx, [rbp+68h]
0x18004e961  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18004e967  nop
0x18004e968  mov     rax, 0
0x18004e972  add     rsp, 40h
0x18004e976  pop     rbp
0x18004e977  retn
```
