# CClipTaskSchedulerT<CEmptyType>::GetSchedulerObjects(ushort *,ushort *,IRegisteredTask * *,ITaskFolder * *)

- ea: `0x1400077fc`
- end: `0x140007a2b`
- name: `?GetSchedulerObjects@?$CClipTaskSchedulerT@VCEmptyType@@@@CAJPEAG0PEAPEAUIRegisteredTask@@PEAPEAUITaskFolder@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140006ab8`
- `0x140007a34`

## callees

- `0x140003454`
- `0x140004780`
- `0x1400077fc`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007857`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007857`
- `OLEAUT32!__imp_VariantInit` at `0x140007872`
- `OLEAUT32!__imp_VariantInit` at `0x140007872`

## pseudocode

```c
__int64 __fastcall CClipTaskSchedulerT<CEmptyType>::GetSchedulerObjects(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 *v6; // rdi
  __int64 *v7; // rsi
  __int64 *v8; // rbx
  HRESULT v9; // eax
  int v10; // r14d
  __int64 v11; // rax
  __int64 (__fastcall *v12)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 *v17; // rax
  __int64 *v19; // [rsp+30h] [rbp-89h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-81h] BYREF
  __int128 v21; // [rsp+50h] [rbp-69h] BYREF
  IRecordInfo *pRecInfo; // [rsp+60h] [rbp-59h]
  VARIANTARG v23; // [rsp+70h] [rbp-49h] BYREF
  VARIANTARG v24; // [rsp+90h] [rbp-29h] BYREF
  VARIANTARG v25; // [rsp+B0h] [rbp-9h] BYREF
  LPVOID ppv; // [rsp+138h] [rbp+7Fh] BYREF

  ppv = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v9 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &IID_ITaskService, &ppv);
  v10 = v9;
  if ( v9 < 0 )
    goto LABEL_2;
  VariantInit(&pvarg);
  v21 = *(_OWORD *)&pvarg.vt;
  v11 = *(_QWORD *)ppv;
  pRecInfo = pvarg.pRecInfo;
  v23 = pvarg;
  v12 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v11 + 80);
  v24 = pvarg;
  v25 = pvarg;
  v9 = v12(ppv, &v25, &v24, &v23, &v21);
  v10 = v9;
  if ( v9 < 0 )
  {
LABEL_2:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v9);
  }
  else
  {
    v6 = (__int64 *)ppv;
    ppv = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v10 < 0 )
    goto LABEL_8;
  v13 = *v6;
  v19 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 **))(v13 + 56))(v6, a2, &v19);
  v10 = v14;
  if ( v14 >= 0 )
  {
    v7 = v19;
    v19 = 0;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v14);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
  if ( v19 )
    (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
  if ( v10 < 0 )
    goto LABEL_8;
  v15 = *v7;
  v19 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 **))(v15 + 104))(v7, a1, &v19);
  v10 = v16;
  if ( v16 >= 0 )
  {
    v8 = v19;
    v19 = 0;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
  if ( v19 )
    (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
  if ( v10 < 0 )
  {
LABEL_8:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v10);
  }
  else
  {
    v17 = v8;
    v8 = 0;
    *a3 = v17;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
  if ( v8 )
    (*(void (__fastcall **)(__int64 *))(*v8 + 16))(v8);
  if ( v7 )
    (*(void (__fastcall **)(__int64 *))(*v7 + 16))(v7);
  if ( v6 )
    (*(void (__fastcall **)(__int64 *))(*v6 + 16))(v6);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400077fc  mov     [rsp-8+arg_18], r9
0x140007801  push    rbp
0x140007802  push    rbx
0x140007803  push    rsi
0x140007804  push    rdi
0x140007805  push    r12
0x140007807  push    r13
0x140007809  push    r14
0x14000780b  push    r15
0x14000780d  lea     rbp, [rsp-1Fh]
0x140007812  sub     rsp, 0D8h
0x140007819  xor     eax, eax
0x14000781b  lea     r9, IID_ITaskService; riid
0x140007822  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x140007826  mov     r12, r8
0x140007829  mov     [rbp+57h+arg_18], rax
0x14000782d  mov     r15, rdx
0x140007830  mov     r13, rcx
0x140007833  lea     rax, [rbp+57h+arg_18]
0x140007837  xorps   xmm0, xmm0
0x14000783a  mov     [rsp+110h+ppv], rax; ppv
0x14000783f  xor     edi, edi
0x140007841  lea     rcx, CLSID_TaskScheduler; rclsid
0x140007848  xor     edx, edx; pUnkOuter
0x14000784a  xor     esi, esi
0x14000784c  xor     ebx, ebx
0x14000784e  movups  xmmword ptr [rsp+110h+pvarg], xmm0
0x140007853  lea     r8d, [rdi+1]; dwClsContext
0x140007857  call    cs:__imp_CoCreateInstance
0x14000785d  mov     r14d, eax
0x140007860  test    eax, eax
0x140007862  jns     short loc_14000786D
0x140007864  mov     ecx, eax
0x140007866  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000786b  jmp     short loc_1400078DA
0x14000786d  lea     rcx, [rsp+110h+pvarg]; pvarg
0x140007872  call    cs:__imp_VariantInit
0x140007878  movups  xmm1, xmmword ptr [rsp+110h+pvarg]
0x14000787d  lea     rdx, [rbp+57h+var_C0]
0x140007881  mov     rcx, [rbp+57h+arg_18]
0x140007885  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x14000788a  lea     r9, [rbp+57h+var_A0]
0x14000788e  mov     [rsp+110h+ppv], rdx
0x140007893  lea     r8, [rbp+57h+var_80]
0x140007897  lea     rdx, [rbp+57h+var_60]
0x14000789b  movaps  [rbp+57h+var_C0], xmm1
0x14000789f  mov     rax, [rcx]
0x1400078a2  movsd   [rbp+57h+var_B0], xmm0
0x1400078a7  movaps  [rbp+57h+var_A0], xmm1
0x1400078ab  movsd   [rbp+57h+var_90], xmm0
0x1400078b0  mov     rax, [rax+50h]
0x1400078b4  movaps  [rbp+57h+var_80], xmm1
0x1400078b8  movsd   [rbp+57h+var_70], xmm0
0x1400078bd  movaps  [rbp+57h+var_60], xmm1
0x1400078c1  movsd   [rbp+57h+var_50], xmm0
0x1400078c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400078cb  mov     r14d, eax
0x1400078ce  test    eax, eax
0x1400078d0  js      short loc_140007864
0x1400078d2  mov     rdi, [rbp+57h+arg_18]
0x1400078d6  mov     [rbp+57h+arg_18], rbx
0x1400078da  mov     ecx, r14d
0x1400078dd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400078e2  mov     rcx, [rbp+57h+arg_18]
0x1400078e6  test    rcx, rcx
0x1400078e9  jz      short loc_1400078FB
0x1400078eb  mov     rax, [rcx]
0x1400078ee  mov     rax, [rax+10h]
0x1400078f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400078f7  mov     [rbp+57h+arg_18], rbx
0x1400078fb  test    r14d, r14d
0x1400078fe  jns     short loc_14000790D
0x140007900  mov     ecx, r14d
0x140007903  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140007908  jmp     loc_1400079D0
0x14000790d  mov     rax, [rdi]
0x140007910  lea     r8, [rsp+110h+var_E0]
0x140007915  mov     rdx, r15
0x140007918  mov     [rsp+110h+var_E0], rbx
0x14000791d  mov     rcx, rdi
0x140007920  mov     rax, [rax+38h]
0x140007924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007929  mov     r14d, eax
0x14000792c  test    eax, eax
0x14000792e  jns     short loc_140007939
0x140007930  mov     ecx, eax
0x140007932  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140007937  jmp     short loc_140007943
0x140007939  mov     rsi, [rsp+110h+var_E0]
0x14000793e  mov     [rsp+110h+var_E0], rbx
0x140007943  mov     ecx, r14d
0x140007946  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000794b  mov     rcx, [rsp+110h+var_E0]
0x140007950  test    rcx, rcx
0x140007953  jz      short loc_140007961
0x140007955  mov     rax, [rcx]
0x140007958  mov     rax, [rax+10h]
0x14000795c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007961  test    r14d, r14d
0x140007964  js      short loc_140007900
0x140007966  mov     rax, [rsi]
0x140007969  lea     r8, [rsp+110h+var_E0]
0x14000796e  mov     rdx, r13
0x140007971  mov     [rsp+110h+var_E0], rbx
0x140007976  mov     rcx, rsi
0x140007979  mov     rax, [rax+68h]
0x14000797d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007982  mov     r14d, eax
0x140007985  test    eax, eax
0x140007987  jns     short loc_140007992
0x140007989  mov     ecx, eax
0x14000798b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140007990  jmp     short loc_1400079A0
0x140007992  mov     rbx, [rsp+110h+var_E0]
0x140007997  mov     [rsp+110h+var_E0], 0
0x1400079a0  mov     ecx, r14d
0x1400079a3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400079a8  mov     rcx, [rsp+110h+var_E0]
0x1400079ad  test    rcx, rcx
0x1400079b0  jz      short loc_1400079BE
0x1400079b2  mov     rax, [rcx]
0x1400079b5  mov     rax, [rax+10h]
0x1400079b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400079be  test    r14d, r14d
0x1400079c1  js      loc_140007900
0x1400079c7  mov     rax, rbx
0x1400079ca  xor     ebx, ebx
0x1400079cc  mov     [r12], rax
0x1400079d0  mov     ecx, r14d
0x1400079d3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1400079d8  test    rbx, rbx
0x1400079db  jz      short loc_1400079EC
0x1400079dd  mov     rax, [rbx]
0x1400079e0  mov     rcx, rbx
0x1400079e3  mov     rax, [rax+10h]
0x1400079e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400079ec  test    rsi, rsi
0x1400079ef  jz      short loc_140007A00
0x1400079f1  mov     rax, [rsi]
0x1400079f4  mov     rcx, rsi
0x1400079f7  mov     rax, [rax+10h]
0x1400079fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a00  test    rdi, rdi
0x140007a03  jz      short loc_140007A14
0x140007a05  mov     rcx, [rdi]
0x140007a08  mov     rax, [rcx+10h]
0x140007a0c  mov     rcx, rdi
0x140007a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a14  mov     eax, r14d
0x140007a17  add     rsp, 0D8h
0x140007a1e  pop     r15
0x140007a20  pop     r14
0x140007a22  pop     r13
0x140007a24  pop     r12
0x140007a26  pop     rdi
0x140007a27  pop     rsi
0x140007a28  pop     rbx
0x140007a29  pop     rbp
0x140007a2a  retn
```
