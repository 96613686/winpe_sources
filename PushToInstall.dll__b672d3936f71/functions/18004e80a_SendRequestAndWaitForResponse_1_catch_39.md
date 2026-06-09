# _SendRequestAndWaitForResponse_::_1_::catch$39

- ea: `0x18004e80a`
- end: `0x18004e8d8`
- name: `_SendRequestAndWaitForResponse_::_1_::catch$39`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800426d8`
- `0x1800480ec`
- `0x18004e80a`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004e829`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004e829`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18004e84a`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18004e84a`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18004e857`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18004e857`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18004e836`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18004e836`

## string_xrefs

- `0x18004e8b5`: `onecoreuap\enduser\winstore\servicescommon\lib\httpforservices.cpp`

## pseudocode

```c
__int64 __fastcall SendRequestAndWaitForResponse_::_1_::catch_39(__int64 a1, __int64 a2)
{
  wil *v3; // rcx
  unsigned int v4; // eax
  __int64 v5; // r9
  _QWORD *v6; // rdx
  const char *v7; // rax

  *(_OWORD *)(a2 + 128) = 0;
  __ExceptionPtrCreate((void *)(a2 + 128));
  __ExceptionPtrCurrentException((void *)(a2 + 128));
  __ExceptionPtrAssign((void *)(a2 + 144), (const void *)(a2 + 128));
  __ExceptionPtrDestroy((void *)(a2 + 128));
  v4 = wil::ResultFromCaughtException(v3);
  v5 = v4;
  if ( v4 == -2147012867 )
    v5 = 2151657495LL;
  *(_DWORD *)(a2 + 128) = v5;
  v6 = *(_QWORD **)(a2 + 80);
  if ( v6[3] > 7u )
    v6 = (_QWORD *)*v6;
  v7 = *(const char **)(a2 + 96);
  if ( *((_QWORD *)v7 + 3) > 7u )
    v7 = *(const char **)v7;
  wil::details::in1diag3::Log_HrMsg(
    *(wil::details::in1diag3 **)(a2 + 472),
    (void *)0x109,
    (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\lib\\httpforservices.cpp",
    (const char *)v5,
    (int)"Failed to connect to %ws with proxy %ws",
    v7,
    v6);
  return 0;
}

```

## disassembly

```asm
0x18004e80a  mov     [rsp+arg_8], rdx
0x18004e80f  push    rbp
0x18004e810  sub     rsp, 40h
0x18004e814  mov     rbp, rdx
0x18004e817  xorps   xmm0, xmm0
0x18004e81a  movdqu  xmmword ptr [rbp+80h], xmm0
0x18004e822  lea     rcx, [rbp+80h]
0x18004e829  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18004e82f  lea     rcx, [rbp+80h]
0x18004e836  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18004e83c  lea     rdx, [rbp+80h]
0x18004e843  lea     rcx, [rbp+90h]
0x18004e84a  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18004e850  lea     rcx, [rbp+80h]
0x18004e857  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18004e85d  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18004e862  mov     r9d, eax
0x18004e865  mov     eax, 803FB017h
0x18004e86a  cmp     r9d, 80072EFDh
0x18004e871  cmovz   r9d, eax; char *
0x18004e875  mov     [rbp+80h], r9d
0x18004e87c  mov     rdx, [rbp+50h]
0x18004e880  cmp     qword ptr [rdx+18h], 7
0x18004e885  jbe     short loc_18004E88A
0x18004e887  mov     rdx, [rdx]
0x18004e88a  mov     rax, [rbp+60h]
0x18004e88e  cmp     qword ptr [rax+18h], 7
0x18004e893  jbe     short loc_18004E898
0x18004e895  mov     rax, [rax]
0x18004e898  mov     rcx, [rbp+1D8h]; this
0x18004e89f  mov     [rsp+48h+var_18], rdx
0x18004e8a4  mov     [rsp+48h+var_20], rax; char *
0x18004e8a9  lea     rax, aFailedToConnec_2; "Failed to connect to %ws with proxy %ws"
0x18004e8b0  mov     qword ptr [rsp+48h+var_28], rax; int
0x18004e8b5  lea     r8, aOnecoreuapEndu_13; "onecoreuap\\enduser\\winstore\\services"...
0x18004e8bc  mov     edx, 109h; void *
0x18004e8c1  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004e8c6  nop
0x18004e8c7  mov     rax, 0
0x18004e8d1  add     rsp, 40h
0x18004e8d5  pop     rbp
0x18004e8d6  retn
```
