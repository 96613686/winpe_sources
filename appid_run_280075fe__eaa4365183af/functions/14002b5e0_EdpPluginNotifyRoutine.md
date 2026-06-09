# EdpPluginNotifyRoutine

- ea: `0x14002b5e0`
- end: `0x14002ba5d`
- name: `EdpPluginNotifyRoutine`
- size: `1149`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x140001010`
- `0x140001044`
- `0x140001610`
- `0x140003c8c`
- `0x140003ec0`
- `0x140005544`
- `0x140006418`
- `0x140006a20`
- `0x140006c40`
- `0x140006f40`
- `0x14002b5e0`
- `0x14002be08`
- `0x14002d170`
- `0x1400328b0`
- `0x1400331f0`
- `0x140033dc0`
- `0x140035c50`

## import_xrefs

- `ntoskrnl!SeLocateProcessImageName` at `0x14002b6f1`
- `ntoskrnl!SeLocateProcessImageName` at `0x14002b6f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b9d0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002b9d0`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14002b698`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14002b698`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002b6b5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002b6b5`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14002ba25`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14002ba25`
- `ntoskrnl!wcsrchr` at `0x14002b886`
- `ntoskrnl!wcsrchr` at `0x14002b886`
- `ntoskrnl!ZwClose` at `0x14002b9e6`
- `ntoskrnl!ZwClose` at `0x14002b9fb`
- `ntoskrnl!ZwClose` at `0x14002b9e6`
- `ntoskrnl!ZwClose` at `0x14002b9fb`

## pseudocode

```c
__int64 __fastcall EdpPluginNotifyRoutine(
        __int64 a1,
        int a2,
        __int64 a3,
        struct _KPROCESS *a4,
        void *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9)
{
  char *v9; // r15
  __int64 v13; // rdi
  struct _UNICODE_STRING *v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  unsigned int v17; // ebx
  void *v18; // rdx
  _WORD *v19; // rbx
  wchar_t *v20; // rsi
  const void *v21; // rdx
  unsigned __int64 v22; // rcx
  wchar_t *v23; // rax
  __int64 v24; // rbx
  __int64 v25; // r8
  __int64 v26; // r9
  const wchar_t *v27; // rcx
  __int64 v28; // rax
  unsigned __int16 *v29; // rax
  int v30; // edx
  char v32; // [rsp+28h] [rbp-D8h]
  _BYTE v33[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v39[3]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v40[12]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+E0h] [rbp-20h]
  __int64 v42; // [rsp+E8h] [rbp-18h]
  _DWORD *v43; // [rsp+F0h] [rbp-10h]
  __int128 v44; // [rsp+F8h] [rbp-8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v45; // [rsp+110h] [rbp+10h] BYREF
  const wchar_t *v46; // [rsp+130h] [rbp+30h]
  int v47; // [rsp+138h] [rbp+38h]
  int v48; // [rsp+13Ch] [rbp+3Ch]
  int *v49; // [rsp+140h] [rbp+40h]
  __int64 v50; // [rsp+148h] [rbp+48h]
  __int64 v51; // [rsp+150h] [rbp+50h]
  int v52[2]; // [rsp+158h] [rbp+58h] BYREF
  int *v53; // [rsp+160h] [rbp+60h]
  __int64 v54; // [rsp+168h] [rbp+68h]
  wchar_t Str[264]; // [rsp+170h] [rbp+70h] BYREF

  v9 = 0;
  v43 = a9;
  v42 = a6;
  LOBYTE(v13) = 0;
  v39[0] = a3;
  v41 = a8;
  v37 = 0;
  v35 = 0;
  v36 = 0;
  Handle = 0;
  v34 = 0;
  memset(v40, 0, sizeof(v40));
  v33[0] = 0;
  v44 = 0;
  if ( RtlRunOnceExecuteOnce(&RunOnce, EdppInitializeCallback, 0, 0) >= 0 )
  {
    ExAcquirePushLockSharedEx(&EdppRuntimeConfig, 0);
    v9 = byte_140019508;
    if ( (unsigned __int8)EdpIsPluginConfigPresent(byte_140019508) )
    {
      if ( (*(_DWORD *)(a7 + 8) & 1) != 0 )
      {
        v14 = *(struct _UNICODE_STRING **)(a7 + 48);
        v40[3] = v14;
      }
      else
      {
        if ( SeLocateProcessImageName(a4, (PUNICODE_STRING *)&v40[3]) < 0 )
          goto LABEL_19;
        v14 = (struct _UNICODE_STRING *)v40[3];
      }
      if ( (int)AiOpenImageFile(v14, *(_QWORD **)(a7 + 40), (void **)&v40[4]) >= 0
        && (int)AiCapturePackageMoniker(a4, v33, 0, (__int64)&v44) >= 0
        && (int)AiOpenTokenByProcessId(a5, &Handle) >= 0 )
      {
        v40[6] = Handle;
        v40[7] = v41;
        v40[5] = v42;
        v40[8] = *(_QWORD *)(a7 + 40);
        v40[11] = v39[0];
        v40[2] = &v44;
        v40[1] = a4;
        v40[9] = a1;
        LODWORD(v40[10]) = a2;
        v40[0] = byte_140019508;
        v15 = EdpPluginEvaluate(
                (unsigned int)v40,
                (unsigned int)&v34,
                (unsigned int)&v37,
                (unsigned int)&v36,
                (__int64)&v35);
        v13 = v37;
        if ( v15 >= 0 )
        {
          v17 = v35;
          if ( (!v35 || (v37 & 1) != 0) && (v37 & 2) == 0 )
          {
            v18 = *(void **)(a7 + 16);
            v33[0] = 0;
            EdppSMBFileOverride(v40, v18, v33);
            if ( v33[0] )
              v13 |= 0x11uLL;
          }
          if ( dword_14001950C == 1 )
            v13 |= 0x80uLL;
          EdpPluginAction((__int64)v40, v16, v13, v36, v17, v32, 0);
        }
      }
    }
  }
LABEL_19:
  v19 = (_WORD *)v40[3];
  if ( dword_140019000 )
  {
    Str[0] = 0;
    v20 = 0;
    if ( v40[3] )
    {
      v21 = *(const void **)(v40[3] + 8LL);
      if ( v21 )
      {
        if ( *(_WORD *)v40[3] < 0x208u )
        {
          memmove(Str, v21, *(unsigned __int16 *)v40[3]);
          v22 = *v19 & 0xFFFE;
          if ( v22 >= 0x208 )
            _report_rangecheckfailure();
          *(wchar_t *)((char *)Str + v22) = 0;
          v23 = wcsrchr(Str, 0x5Cu);
          v20 = v23;
          if ( v23 && *v23 == 92 )
            v20 = v23 + 1;
          v19 = (_WORD *)v40[3];
        }
      }
    }
    if ( v34 == -1073740956 && (v13 & 2) != 0 )
    {
      v39[1] = L"APPID://FQBN";
      v36 = 0;
      v39[0] = 1703960;
      SrpGetAttributeFromToken(v40[6], (unsigned int)v39, 1, (unsigned int)&v36, 0);
      v24 = v36;
      if ( (unsigned int)dword_140019000 > 4
        && (unsigned __int8)tlgKeywordOn((unsigned int)dword_140019000, 0x400000000000LL) )
      {
        v27 = L"NA";
        if ( v20 )
          v27 = v20;
        v28 = -1;
        do
          ++v28;
        while ( v27[v28] );
        v46 = v27;
        v47 = 2 * v28 + 2;
        v48 = 0;
        v29 = (unsigned __int16 *)v39;
        if ( v24 )
          v29 = (unsigned __int16 *)v24;
        v30 = *v29;
        v51 = *((_QWORD *)v29 + 1);
        v53 = &v34;
        v52[0] = v30;
        v49 = v52;
        v50 = 2;
        v52[1] = 0;
        v34 = v25;
        v54 = 4;
        tlgWriteTransfer_EtwWriteTransfer((__int64)v52, (unsigned __int8 *)&unk_1400160D8, v25, v26, 6u, &v45);
      }
      SrpDeleteEnterpriseContext(v24);
      v19 = (_WORD *)v40[3];
    }
  }
  if ( v19 && v19 != *(_WORD **)(a7 + 48) )
    ExFreePoolWithTag(v19, 0);
  if ( Handle )
    ZwClose(Handle);
  if ( v40[4] )
    ZwClose((HANDLE)v40[4]);
  AiFree(*((_QWORD *)&v44 + 1));
  *v43 = 0;
  if ( v9 )
    ExReleasePushLockSharedEx(&EdppRuntimeConfig, 0);
  return 0;
}

```

## disassembly

```asm
0x14002b5e0  push    rbp
0x14002b5e2  push    rbx
0x14002b5e3  push    rsi
0x14002b5e4  push    rdi
0x14002b5e5  push    r12
0x14002b5e7  push    r13
0x14002b5e9  push    r14
0x14002b5eb  push    r15
0x14002b5ed  lea     rbp, [rsp-298h]
0x14002b5f5  sub     rsp, 398h
0x14002b5fc  mov     rax, cs:__security_cookie
0x14002b603  xor     rax, rsp
0x14002b606  mov     [rbp+2D0h+var_50], rax
0x14002b60d  mov     rax, [rbp+2D0h+arg_40]
0x14002b614  xor     r15d, r15d
0x14002b617  mov     rsi, [rbp+2D0h+arg_20]
0x14002b61e  mov     r13d, edx
0x14002b621  mov     r14, [rbp+2D0h+arg_30]
0x14002b628  mov     r12, rcx
0x14002b62b  mov     [rbp+2D0h+var_2E0], rax
0x14002b62f  lea     rcx, [rbp+2D0h+var_350]; void *
0x14002b633  mov     rax, [rbp+2D0h+arg_28]
0x14002b63a  xor     edx, edx; Val
0x14002b63c  mov     [rbp+2D0h+var_2E8], rax
0x14002b640  mov     rbx, r9
0x14002b643  mov     rax, [rbp+2D0h+arg_38]
0x14002b64a  mov     edi, r15d
0x14002b64d  mov     [rsp+3D0h+var_368], r8
0x14002b652  lea     r8d, [r15+60h]; Size
0x14002b656  mov     [rbp+2D0h+var_2F0], rax
0x14002b65a  mov     [rsp+3D0h+var_378], r15
0x14002b65f  mov     [rsp+3D0h+var_388], r15d
0x14002b664  mov     [rsp+3D0h+var_380], r15
0x14002b669  mov     [rsp+3D0h+Handle], r15
0x14002b66e  mov     [rsp+3D0h+var_38C], r15d
0x14002b673  call    memset
0x14002b678  xorps   xmm0, xmm0
0x14002b67b  mov     [rsp+3D0h+var_390], r15b
0x14002b680  xor     r9d, r9d; Context
0x14002b683  lea     rdx, EdppInitializeCallback; InitFn
0x14002b68a  xor     r8d, r8d; Parameter
0x14002b68d  lea     rcx, RunOnce; RunOnce
0x14002b694  movups  [rbp+2D0h+var_2D8], xmm0
0x14002b698  call    cs:__imp_RtlRunOnceExecuteOnce
0x14002b69f  nop     dword ptr [rax+rax+00h]
0x14002b6a4  test    eax, eax
0x14002b6a6  js      loc_14002B81F
0x14002b6ac  xor     edx, edx
0x14002b6ae  lea     rcx, EdppRuntimeConfig
0x14002b6b5  call    cs:__imp_ExAcquirePushLockSharedEx
0x14002b6bc  nop     dword ptr [rax+rax+00h]
0x14002b6c1  lea     r15, byte_140019508
0x14002b6c8  mov     rcx, r15
0x14002b6cb  call    EdpIsPluginConfigPresent
0x14002b6d0  test    al, al
0x14002b6d2  jz      loc_14002B81F
0x14002b6d8  mov     eax, [r14+8]
0x14002b6dc  test    al, 1
0x14002b6de  jz      short loc_14002B6EA
0x14002b6e0  mov     rcx, [r14+30h]
0x14002b6e4  mov     [rbp+2D0h+pImageFileName], rcx
0x14002b6e8  jmp     short loc_14002B709
0x14002b6ea  lea     rdx, [rbp+2D0h+pImageFileName]; pImageFileName
0x14002b6ee  mov     rcx, rbx; Process
0x14002b6f1  call    cs:__imp_SeLocateProcessImageName
0x14002b6f8  nop     dword ptr [rax+rax+00h]
0x14002b6fd  test    eax, eax
0x14002b6ff  js      loc_14002B81F
0x14002b705  mov     rcx, [rbp+2D0h+pImageFileName]
0x14002b709  mov     rdx, [r14+28h]
0x14002b70d  lea     r8, [rbp+2D0h+var_330]
0x14002b711  call    AiOpenImageFile
0x14002b716  test    eax, eax
0x14002b718  js      loc_14002B81F
0x14002b71e  lea     r9, [rbp+2D0h+var_2D8]
0x14002b722  xor     r8d, r8d
0x14002b725  lea     rdx, [rsp+3D0h+var_390]
0x14002b72a  mov     rcx, rbx
0x14002b72d  call    AiCapturePackageMoniker
0x14002b732  test    eax, eax
0x14002b734  js      loc_14002B81F
0x14002b73a  lea     rdx, [rsp+3D0h+Handle]
0x14002b73f  mov     rcx, rsi
0x14002b742  call    AiOpenTokenByProcessId
0x14002b747  test    eax, eax
0x14002b749  js      loc_14002B81F
0x14002b74f  mov     rax, [rsp+3D0h+Handle]
0x14002b754  lea     r9, [rsp+3D0h+var_380]
0x14002b759  mov     [rbp+2D0h+var_320], rax
0x14002b75d  lea     r8, [rsp+3D0h+var_378]
0x14002b762  mov     rax, [rbp+2D0h+var_2F0]
0x14002b766  lea     rdx, [rsp+3D0h+var_38C]
0x14002b76b  mov     [rbp+2D0h+var_318], rax
0x14002b76f  lea     rcx, [rbp+2D0h+var_350]
0x14002b773  mov     rax, [rbp+2D0h+var_2E8]
0x14002b777  mov     [rbp+2D0h+var_328], rax
0x14002b77b  mov     rax, [r14+28h]
0x14002b77f  mov     [rbp+2D0h+var_310], rax
0x14002b783  mov     rax, [rsp+3D0h+var_368]
0x14002b788  mov     [rbp+2D0h+var_2F8], rax
0x14002b78c  lea     rax, [rbp+2D0h+var_2D8]
0x14002b790  mov     [rbp+2D0h+var_340], rax
0x14002b794  lea     rax, [rsp+3D0h+var_388]
0x14002b799  mov     qword ptr [rsp+3D0h+var_3B0], rax
0x14002b79e  mov     [rbp+2D0h+var_348], rbx
0x14002b7a2  mov     [rbp+2D0h+var_308], r12
0x14002b7a6  mov     [rbp+2D0h+var_300], r13d
0x14002b7aa  mov     [rbp+2D0h+var_350], r15
0x14002b7ae  call    EdpPluginEvaluate
0x14002b7b3  mov     rdi, [rsp+3D0h+var_378]
0x14002b7b8  xor     r12d, r12d
0x14002b7bb  test    eax, eax
0x14002b7bd  js      short loc_14002B822
0x14002b7bf  mov     ebx, [rsp+3D0h+var_388]
0x14002b7c3  test    ebx, ebx
0x14002b7c5  jz      short loc_14002B7CD
0x14002b7c7  test    dil, 1
0x14002b7cb  jz      short loc_14002B7F5
0x14002b7cd  test    dil, 2
0x14002b7d1  jnz     short loc_14002B7F5
0x14002b7d3  mov     rdx, [r14+10h]
0x14002b7d7  lea     r8, [rsp+3D0h+var_390]
0x14002b7dc  lea     rcx, [rbp+2D0h+var_350]
0x14002b7e0  mov     [rsp+3D0h+var_390], r12b
0x14002b7e5  call    EdppSMBFileOverride
0x14002b7ea  cmp     [rsp+3D0h+var_390], r12b
0x14002b7ef  jz      short loc_14002B7F5
0x14002b7f1  or      rdi, 11h
0x14002b7f5  cmp     cs:dword_14001950C, 1
0x14002b7fc  jnz     short loc_14002B803
0x14002b7fe  bts     rdi, 7
0x14002b803  mov     r9, [rsp+3D0h+var_380]
0x14002b808  lea     rcx, [rbp+2D0h+var_350]
0x14002b80c  mov     [rsp+3D0h+var_3A0], r12d
0x14002b811  mov     r8, rdi
0x14002b814  mov     [rsp+3D0h+var_3B0], ebx
0x14002b818  call    EdpPluginAction
0x14002b81d  jmp     short loc_14002B822
0x14002b81f  xor     r12d, r12d
0x14002b822  mov     eax, cs:dword_140019000
0x14002b828  mov     rbx, [rbp+2D0h+pImageFileName]
0x14002b82c  test    eax, eax
0x14002b82e  jz      loc_14002B9C0
0x14002b834  mov     [rbp+2D0h+Str], r12w
0x14002b839  mov     rsi, r12
0x14002b83c  test    rbx, rbx
0x14002b83f  jz      short loc_14002B8A7
0x14002b841  mov     rdx, [rbx+8]; Src
0x14002b845  test    rdx, rdx
0x14002b848  jz      short loc_14002B8A7
0x14002b84a  movzx   eax, word ptr [rbx]
0x14002b84d  mov     r13d, 208h
0x14002b853  cmp     r13w, ax
0x14002b857  jbe     short loc_14002B8A7
0x14002b859  mov     r8d, eax; Size
0x14002b85c  lea     rcx, [rbp+2D0h+Str]; void *
0x14002b860  call    memmove
0x14002b865  movzx   ecx, word ptr [rbx]
0x14002b868  and     rcx, 0FFFFFFFFFFFFFFFEh
0x14002b86c  cmp     rcx, r13
0x14002b86f  jnb     loc_14002BA57
0x14002b875  mov     [rbp+rcx+2D0h+Str], r12w
0x14002b87b  mov     ebx, 5Ch ; '\'
0x14002b880  mov     edx, ebx; Ch
0x14002b882  lea     rcx, [rbp+2D0h+Str]; Str
0x14002b886  call    cs:__imp_wcsrchr
0x14002b88d  nop     dword ptr [rax+rax+00h]
0x14002b892  mov     rsi, rax
0x14002b895  test    rax, rax
0x14002b898  jz      short loc_14002B8A3
0x14002b89a  cmp     [rax], bx
0x14002b89d  jnz     short loc_14002B8A3
0x14002b89f  add     rsi, 2
0x14002b8a3  mov     rbx, [rbp+2D0h+pImageFileName]
0x14002b8a7  cmp     [rsp+3D0h+var_38C], 0C0000364h
0x14002b8af  jnz     loc_14002B9C0
0x14002b8b5  test    dil, 2
0x14002b8b9  jz      loc_14002B9C0
0x14002b8bf  mov     rcx, [rbp+2D0h+var_320]
0x14002b8c3  lea     rax, aAppidFqbn
0x14002b8ca  mov     r8d, 1
0x14002b8d0  mov     [rsp+3D0h+var_360], rax
0x14002b8d5  lea     r9, [rsp+3D0h+var_380]
0x14002b8da  mov     [rsp+3D0h+var_380], r12
0x14002b8df  lea     rdx, [rsp+3D0h+var_368]
0x14002b8e4  mov     [rsp+3D0h+var_368], 1A0018h
0x14002b8ed  mov     qword ptr [rsp+3D0h+var_3B0], r12
0x14002b8f2  call    SrpGetAttributeFromToken
0x14002b8f7  mov     ecx, cs:dword_140019000
0x14002b8fd  mov     r8d, eax
0x14002b900  mov     rbx, [rsp+3D0h+var_380]
0x14002b905  cmp     ecx, 4
0x14002b908  jbe     loc_14002B9B4
0x14002b90e  mov     rdx, 400000000000h
0x14002b918  call    _tlgKeywordOn
0x14002b91d  test    al, al
0x14002b91f  jz      loc_14002B9B4
0x14002b925  test    rsi, rsi
0x14002b928  lea     rcx, aNa
0x14002b92f  cmovnz  rcx, rsi
0x14002b933  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002b937  inc     rax
0x14002b93a  cmp     [rcx+rax*2], r12w
0x14002b93f  jnz     short loc_14002B937
0x14002b941  lea     eax, ds:2[rax*2]
0x14002b948  mov     [rbp+2D0h+var_2A0], rcx
0x14002b94c  mov     [rbp+2D0h+var_298], eax
0x14002b94f  lea     rcx, [rbp+2D0h+var_278]; int
0x14002b953  mov     [rbp+2D0h+var_294], r12d
0x14002b957  lea     rax, [rsp+3D0h+var_368]
0x14002b95c  test    rbx, rbx
0x14002b95f  cmovnz  rax, rbx
0x14002b963  movzx   edx, word ptr [rax]
0x14002b966  mov     rax, [rax+8]
0x14002b96a  mov     [rbp+2D0h+var_280], rax
0x14002b96e  lea     rax, [rsp+3D0h+var_38C]
0x14002b973  mov     [rbp+2D0h+var_270], rax
0x14002b977  lea     rax, [rbp+2D0h+var_2C0]
0x14002b97b  mov     [rbp+2D0h+var_278], edx
0x14002b97e  lea     rdx, unk_1400160D8; int
0x14002b985  mov     [rsp+3D0h+var_3A8], rax; __int64
0x14002b98a  mov     [rsp+3D0h+var_3B0], 6; ULONG
0x14002b992  mov     [rbp+2D0h+var_290], rcx
0x14002b996  mov     [rbp+2D0h+var_288], 2
0x14002b99e  mov     [rbp+2D0h+var_274], r12d
0x14002b9a2  mov     [rsp+3D0h+var_38C], r8d
0x14002b9a7  mov     [rbp+2D0h+var_268], 4
0x14002b9af  call    _tlgWriteTransfer_EtwWriteTransfer
0x14002b9b4  mov     rcx, rbx
0x14002b9b7  call    SrpDeleteEnterpriseContext
0x14002b9bc  mov     rbx, [rbp+2D0h+pImageFileName]
0x14002b9c0  test    rbx, rbx
0x14002b9c3  jz      short loc_14002B9DC
0x14002b9c5  cmp     rbx, [r14+30h]
0x14002b9c9  jz      short loc_14002B9DC
0x14002b9cb  xor     edx, edx; Tag
0x14002b9cd  mov     rcx, rbx; P
0x14002b9d0  call    cs:__imp_ExFreePoolWithTag
0x14002b9d7  nop     dword ptr [rax+rax+00h]
0x14002b9dc  mov     rcx, [rsp+3D0h+Handle]; Handle
0x14002b9e1  test    rcx, rcx
0x14002b9e4  jz      short loc_14002B9F2
0x14002b9e6  call    cs:__imp_ZwClose
0x14002b9ed  nop     dword ptr [rax+rax+00h]
0x14002b9f2  mov     rcx, [rbp+2D0h+var_330]; Handle
0x14002b9f6  test    rcx, rcx
0x14002b9f9  jz      short loc_14002BA07
0x14002b9fb  call    cs:__imp_ZwClose
0x14002ba02  nop     dword ptr [rax+rax+00h]
0x14002ba07  mov     rcx, qword ptr [rbp+2D0h+var_2D8+8]
0x14002ba0b  call    AiFree
0x14002ba10  mov     rax, [rbp+2D0h+var_2E0]
0x14002ba14  mov     [rax], r12d
0x14002ba17  test    r15, r15
0x14002ba1a  jz      short loc_14002BA31
0x14002ba1c  xor     edx, edx
0x14002ba1e  lea     rcx, EdppRuntimeConfig
0x14002ba25  call    cs:__imp_ExReleasePushLockSharedEx
0x14002ba2c  nop     dword ptr [rax+rax+00h]
0x14002ba31  xor     eax, eax
0x14002ba33  mov     rcx, [rbp+2D0h+var_50]
0x14002ba3a  xor     rcx, rsp; StackCookie
0x14002ba3d  call    __security_check_cookie
0x14002ba42  add     rsp, 398h
0x14002ba49  pop     r15
0x14002ba4b  pop     r14
0x14002ba4d  pop     r13
0x14002ba4f  pop     r12
0x14002ba51  pop     rdi
0x14002ba52  pop     rsi
0x14002ba53  pop     rbx
0x14002ba54  pop     rbp
0x14002ba55  retn
0x14002ba57  call    __report_rangecheckfailure
```
