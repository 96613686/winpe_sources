# AiSvcpEnableRunTask(ushort const *,ulong,ulong)

- ea: `0x180003268`
- end: `0x18000357d`
- name: `?AiSvcpEnableRunTask@@YAKPEBGKK@Z`
- size: `789`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002c40`
- `0x180003590`
- `0x180003a90`

## callees

- `0x180003268`
- `0x180004870`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800032bd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800032bd`
- `OLEAUT32!__imp_VariantInit` at `0x1800032fb`
- `OLEAUT32!__imp_VariantInit` at `0x1800032fb`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000355f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000355f`

## pseudocode

```c
__int64 __fastcall AiSvcpEnableRunTask(const unsigned __int16 *a1, __int64 a2, int a3)
{
  int v5; // ebx
  __int64 v6; // r8
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 (__fastcall *v10)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *); // rax
  __int64 v11; // rax
  NTSTATUS v12; // ebx
  unsigned int v13; // edi
  LPVOID ppv; // [rsp+40h] [rbp-79h] BYREF
  __int64 v16; // [rsp+48h] [rbp-71h] BYREF
  __int64 v17; // [rsp+50h] [rbp-69h]
  VARIANTARG pvarg; // [rsp+58h] [rbp-61h] BYREF
  VARIANTARG v19; // [rsp+70h] [rbp-49h] BYREF
  __int128 v20; // [rsp+90h] [rbp-29h] BYREF
  IRecordInfo *pRecInfo; // [rsp+A0h] [rbp-19h]
  VARIANTARG v22; // [rsp+B0h] [rbp-9h] BYREF
  VARIANTARG v23; // [rsp+D0h] [rbp+17h] BYREF
  __int64 *v24; // [rsp+138h] [rbp+7Fh] BYREF

  ppv = 0;
  v16 = 0;
  v24 = 0;
  v17 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v5 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  if ( v5 >= 0 )
  {
    VariantInit(&pvarg);
    v20 = *(_OWORD *)&pvarg.vt;
    v9 = *(_QWORD *)ppv;
    pRecInfo = pvarg.pRecInfo;
    v22 = pvarg;
    v10 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *, __int128 *))(v9 + 80);
    v23 = pvarg;
    v19 = pvarg;
    v5 = v10(ppv, &v19, &v23, &v22, &v20);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 56LL))(
             ppv,
             L"\\Microsoft\\Windows\\AppID",
             &v16);
      if ( v5 >= 0 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64 **))(*(_QWORD *)v16 + 104LL))(
               v16,
               a1,
               &v24);
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v24 + 88))(v24, 0xFFFFFFFFLL);
          if ( v5 >= 0 )
          {
            if ( !a3 )
              goto LABEL_27;
            v11 = *v24;
            v19 = pvarg;
            v5 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int64))(v11 + 104))(v24, &v19, 2);
            if ( v5 >= 0 )
              goto LABEL_27;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
            {
              goto LABEL_27;
            }
            v8 = 46;
          }
          else
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
            {
              goto LABEL_27;
            }
            v8 = 45;
          }
        }
        else
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
          {
            goto LABEL_27;
          }
          v8 = 44;
        }
      }
      else
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
          goto LABEL_27;
        v8 = 43;
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        goto LABEL_27;
      v8 = 42;
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      goto LABEL_27;
    v8 = 41;
  }
  WPP_SF_d(v7[2], v8, v6, (unsigned int)v5);
LABEL_27:
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v24 )
    (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v5 >= 0 )
    return 0;
  if ( (v5 & 0xFFFF0000) == 0x80070000 )
    return (unsigned __int16)v5;
  if ( (v5 & 0x10000000) == 0 )
    return (unsigned int)v5;
  v12 = v5 & 0xEFFFFFFF;
  v13 = v12;
  if ( v12 >= 0 )
  {
    return 0;
  }
  else
  {
    v5 = RtlNtStatusToDosErrorNoTeb(v12);
    if ( v5 == 317 )
      return v13;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180003268  push    rbp
0x18000326a  push    rbx
0x18000326b  push    rsi
0x18000326c  push    rdi
0x18000326d  lea     rbp, [rsp-3Fh]
0x180003272  sub     rsp, 0F8h
0x180003279  xor     eax, eax
0x18000327b  mov     [rbp+57h+var_D0], 0
0x180003283  xor     edx, edx; pUnkOuter
0x180003285  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180003289  mov     [rbp+57h+var_C8], rax
0x18000328d  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180003294  mov     [rbp+57h+arg_18], rax
0x180003298  mov     edi, r8d
0x18000329b  mov     [rbp+57h+var_C0], rax
0x18000329f  mov     rsi, rcx
0x1800032a2  xorps   xmm0, xmm0
0x1800032a5  lea     rax, [rbp+57h+var_D0]
0x1800032a9  lea     r8d, [rdx+1]; dwClsContext
0x1800032ad  mov     [rsp+110h+ppv], rax; ppv
0x1800032b2  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800032b9  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800032bd  call    cs:__imp_CoCreateInstance
0x1800032c3  mov     ebx, eax
0x1800032c5  test    eax, eax
0x1800032c7  jns     short loc_1800032F7
0x1800032c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032d0  lea     rax, WPP_GLOBAL_Control
0x1800032d7  cmp     rcx, rax
0x1800032da  jz      loc_1800034DE
0x1800032e0  test    dword ptr [rcx+1Ch], 400h
0x1800032e7  jz      loc_1800034DE
0x1800032ed  mov     edx, 29h ; ')'
0x1800032f2  jmp     loc_1800034D2
0x1800032f7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800032fb  call    cs:__imp_VariantInit
0x180003301  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x180003305  lea     rdx, [rbp+57h+var_80]
0x180003309  mov     rcx, [rbp+57h+var_D0]
0x18000330d  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x180003312  lea     r9, [rbp+57h+var_60]
0x180003316  mov     [rsp+110h+ppv], rdx
0x18000331b  lea     r8, [rbp+57h+var_40]
0x18000331f  lea     rdx, [rbp+57h+var_A0]
0x180003323  movaps  [rbp+57h+var_80], xmm1
0x180003327  mov     rax, [rcx]
0x18000332a  movsd   [rbp+57h+var_70], xmm0
0x18000332f  movaps  [rbp+57h+var_60], xmm1
0x180003333  movsd   [rbp+57h+var_50], xmm0
0x180003338  mov     rax, [rax+50h]
0x18000333c  movaps  [rbp+57h+var_40], xmm1
0x180003340  movsd   [rbp+57h+var_30], xmm0
0x180003345  movaps  [rbp+57h+var_A0], xmm1
0x180003349  movsd   [rbp+57h+var_90], xmm0
0x18000334e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003353  mov     ebx, eax
0x180003355  test    eax, eax
0x180003357  jns     short loc_180003387
0x180003359  mov     rcx, cs:WPP_GLOBAL_Control
0x180003360  lea     rax, WPP_GLOBAL_Control
0x180003367  cmp     rcx, rax
0x18000336a  jz      loc_1800034DE
0x180003370  test    dword ptr [rcx+1Ch], 400h
0x180003377  jz      loc_1800034DE
0x18000337d  mov     edx, 2Ah ; '*'
0x180003382  jmp     loc_1800034D2
0x180003387  mov     rcx, [rbp+57h+var_D0]
0x18000338b  lea     r8, [rbp+57h+var_C8]
0x18000338f  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\AppID"
0x180003396  mov     rax, [rcx]
0x180003399  mov     rax, [rax+38h]
0x18000339d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033a2  mov     ebx, eax
0x1800033a4  test    eax, eax
0x1800033a6  jns     short loc_1800033D6
0x1800033a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033af  lea     rax, WPP_GLOBAL_Control
0x1800033b6  cmp     rcx, rax
0x1800033b9  jz      loc_1800034DE
0x1800033bf  test    dword ptr [rcx+1Ch], 400h
0x1800033c6  jz      loc_1800034DE
0x1800033cc  mov     edx, 2Bh ; '+'
0x1800033d1  jmp     loc_1800034D2
0x1800033d6  mov     rcx, [rbp+57h+var_C8]
0x1800033da  lea     r8, [rbp+57h+arg_18]
0x1800033de  mov     rdx, rsi
0x1800033e1  mov     rax, [rcx]
0x1800033e4  mov     rax, [rax+68h]
0x1800033e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033ed  mov     ebx, eax
0x1800033ef  test    eax, eax
0x1800033f1  jns     short loc_180003421
0x1800033f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033fa  lea     rax, WPP_GLOBAL_Control
0x180003401  cmp     rcx, rax
0x180003404  jz      loc_1800034DE
0x18000340a  test    dword ptr [rcx+1Ch], 400h
0x180003411  jz      loc_1800034DE
0x180003417  mov     edx, 2Ch ; ','
0x18000341c  jmp     loc_1800034D2
0x180003421  mov     rcx, [rbp+57h+arg_18]
0x180003425  or      edx, 0FFFFFFFFh
0x180003428  mov     rax, [rcx]
0x18000342b  mov     rax, [rax+58h]
0x18000342f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003434  mov     ebx, eax
0x180003436  test    eax, eax
0x180003438  jns     short loc_180003465
0x18000343a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003441  lea     rax, WPP_GLOBAL_Control
0x180003448  cmp     rcx, rax
0x18000344b  jz      loc_1800034DE
0x180003451  test    dword ptr [rcx+1Ch], 400h
0x180003458  jz      loc_1800034DE
0x18000345e  mov     edx, 2Dh ; '-'
0x180003463  jmp     short loc_1800034D2
0x180003465  test    edi, edi
0x180003467  jz      short loc_1800034DE
0x180003469  mov     rcx, [rbp+57h+arg_18]
0x18000346d  lea     rdx, [rbp+57h+var_C0]
0x180003471  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180003475  xor     r9d, r9d
0x180003478  mov     [rsp+110h+var_E8], rdx
0x18000347d  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180003482  lea     rdx, qword_1800112E8
0x180003489  mov     rax, [rcx]
0x18000348c  mov     [rsp+110h+ppv], rdx
0x180003491  lea     rdx, [rbp+57h+var_A0]
0x180003495  lea     r8d, [r9+2]
0x180003499  movaps  [rbp+57h+var_A0], xmm0
0x18000349d  movsd   [rbp+57h+var_90], xmm1
0x1800034a2  mov     rax, [rax+68h]
0x1800034a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ab  mov     ebx, eax
0x1800034ad  test    eax, eax
0x1800034af  jns     short loc_1800034DE
0x1800034b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034b8  lea     rax, WPP_GLOBAL_Control
0x1800034bf  cmp     rcx, rax
0x1800034c2  jz      short loc_1800034DE
0x1800034c4  test    dword ptr [rcx+1Ch], 400h
0x1800034cb  jz      short loc_1800034DE
0x1800034cd  mov     edx, 2Eh ; '.'
0x1800034d2  mov     rcx, [rcx+10h]
0x1800034d6  mov     r9d, ebx
0x1800034d9  call    WPP_SF_d
0x1800034de  mov     rcx, [rbp+57h+var_C0]
0x1800034e2  test    rcx, rcx
0x1800034e5  jz      short loc_1800034F3
0x1800034e7  mov     rax, [rcx]
0x1800034ea  mov     rax, [rax+10h]
0x1800034ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034f3  mov     rcx, [rbp+57h+arg_18]
0x1800034f7  test    rcx, rcx
0x1800034fa  jz      short loc_180003508
0x1800034fc  mov     rax, [rcx]
0x1800034ff  mov     rax, [rax+10h]
0x180003503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003508  mov     rcx, [rbp+57h+var_C8]
0x18000350c  test    rcx, rcx
0x18000350f  jz      short loc_18000351D
0x180003511  mov     rax, [rcx]
0x180003514  mov     rax, [rax+10h]
0x180003518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000351d  mov     rcx, [rbp+57h+var_D0]
0x180003521  test    rcx, rcx
0x180003524  jz      short loc_180003532
0x180003526  mov     rax, [rcx]
0x180003529  mov     rax, [rax+10h]
0x18000352d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003532  test    ebx, ebx
0x180003534  js      short loc_18000353A
0x180003536  xor     ebx, ebx
0x180003538  jmp     short loc_18000356F
0x18000353a  mov     eax, ebx
0x18000353c  and     eax, 0FFFF0000h
0x180003541  cmp     eax, 80070000h
0x180003546  jnz     short loc_18000354D
0x180003548  movzx   ebx, bx
0x18000354b  jmp     short loc_18000356F
0x18000354d  bt      ebx, 1Ch
0x180003551  jnb     short loc_18000356F
0x180003553  and     ebx, 0EFFFFFFFh
0x180003559  mov     edi, ebx
0x18000355b  jge     short loc_180003536
0x18000355d  mov     ecx, ebx; Status
0x18000355f  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180003565  cmp     eax, 13Dh
0x18000356a  mov     ebx, eax
0x18000356c  cmovz   ebx, edi
0x18000356f  mov     eax, ebx
0x180003571  add     rsp, 0F8h
0x180003578  pop     rdi
0x180003579  pop     rsi
0x18000357a  pop     rbx
0x18000357b  pop     rbp
0x18000357c  retn
```
