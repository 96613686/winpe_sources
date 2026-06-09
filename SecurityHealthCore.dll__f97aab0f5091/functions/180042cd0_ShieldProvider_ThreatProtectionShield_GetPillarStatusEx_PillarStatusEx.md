# ShieldProvider::ThreatProtectionShield::GetPillarStatusEx(PillarStatusEx * *)

- ea: `0x180042cd0`
- end: `0x18004310c`
- name: `?GetPillarStatusEx@ThreatProtectionShield@ShieldProvider@@UEAAJPEAPEAUPillarStatusEx@@@Z`
- size: `1084`
- prototype: `__int64 __fastcall(ShieldProvider::ThreatProtectionShield *__hidden this, struct PillarStatusEx **)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ccd4`
- `0x18000d7fc`
- `0x18000d83c`
- `0x180011730`
- `0x180011cbc`
- `0x180037d70`
- `0x180042cd0`
- `0x1800e1764`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x180042f10`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x180042f10`
- `ole32!CoTaskMemFree` at `0x180042de7`
- `ole32!CoTaskMemFree` at `0x180042dfe`
- `ole32!CoTaskMemFree` at `0x180042e0f`
- `ole32!CoTaskMemFree` at `0x180042e9c`
- `ole32!CoTaskMemFree` at `0x180042eb3`
- `ole32!CoTaskMemFree` at `0x180042ec4`
- `ole32!CoTaskMemFree` at `0x180042de7`
- `ole32!CoTaskMemFree` at `0x180042dfe`
- `ole32!CoTaskMemFree` at `0x180042e0f`
- `ole32!CoTaskMemFree` at `0x180042e9c`
- `ole32!CoTaskMemFree` at `0x180042eb3`
- `ole32!CoTaskMemFree` at `0x180042ec4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ShieldProvider::ThreatProtectionShield::GetPillarStatusEx(
        ShieldProvider::ThreatProtectionShield *this,
        struct PillarStatusEx **a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  int v5; // eax
  unsigned int v6; // edi
  _QWORD *v7; // rbx
  void *v8; // rcx
  void *v9; // rcx
  int v10; // eax
  struct tagWSC_AV_PRODUCT_INFO_LIST *v11; // rdx
  unsigned __int16 *v12; // r8
  int v13; // r14d
  _DWORD *v14; // rbx
  void *v15; // rcx
  void *v16; // rcx
  int v17; // edi
  int v18; // r13d
  unsigned __int16 **v19; // r12
  unsigned __int16 **v20; // r15
  ShieldProvider *v21; // rax
  unsigned int v22; // r14d
  bool v23; // zf
  __int64 v24; // rcx
  __int64 v25; // r9
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  ShieldProvider *v29; // [rsp+30h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v31[2]; // [rsp+40h] [rbp-10h] BYREF
  int v33; // [rsp+A8h] [rbp+58h]

  if ( !a2 )
  {
    v3 = -2147024809;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_4608de75ba8c308c3f60bea69d382694_Traceguids, 2147942487LL);
    return v3;
  }
  v31[0] = 0;
  v4 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(v31);
  v3 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        WPP_4608de75ba8c308c3f60bea69d382694_Traceguids,
        (unsigned int)v4);
    goto LABEL_85;
  }
  pv = 0;
  v5 = CommonUtil::UtilCoTaskMemAllocObject<PillarStatusEx>(&pv);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        WPP_4608de75ba8c308c3f60bea69d382694_Traceguids,
        (unsigned int)v5);
    v7 = pv;
    if ( pv )
    {
      v8 = (void *)*((_QWORD *)pv + 1);
      if ( v8 )
      {
        CoTaskMemFree(v8);
        v7[1] = 0;
      }
      v9 = (void *)v7[2];
      if ( v9 )
      {
        CoTaskMemFree(v9);
        v7[2] = 0;
      }
      CoTaskMemFree(v7);
    }
    v3 = v6;
    goto LABEL_85;
  }
  v29 = 0;
  v10 = (*(__int64 (__fastcall **)(ShieldProvider::ThreatProtectionShield *, ShieldProvider **))(*(_QWORD *)this + 80LL))(
          this,
          &v29);
  v13 = v10;
  v33 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_4608de75ba8c308c3f60bea69d382694_Traceguids,
        (unsigned int)v10);
    if ( v29 )
      ShieldProvider::FreeWscAntivirusProductList(v29, v11);
    v14 = pv;
    goto LABEL_27;
  }
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = v29;
  if ( !*(_DWORD *)v29 )
    goto LABEL_65;
  v22 = 0;
  do
  {
    v23 = _wcsnicmp(*(const wchar_t **)(*((_QWORD *)v21 + 1) + 80LL * v22 + 16), L"windowsdefender://", 0x12u) == 0;
    v21 = v29;
    if ( v23 )
      goto LABEL_63;
    v24 = *((_QWORD *)v29 + 1);
    if ( *(_DWORD *)(v24 + 80LL * v22 + 32) == 54 )
      goto LABEL_63;
    v25 = *(unsigned int *)(v24 + 80LL * v22 + 36);
    switch ( (_DWORD)v25 )
    {
      case 2:
        if ( v17 < 2 )
        {
          v17 = 2;
          v18 = 85;
        }
        break;
      case 4:
        if ( v17 < 4 )
        {
          v17 = 4;
          v18 = 86;
LABEL_43:
          v19 = *(unsigned __int16 ***)(v24 + 80LL * v22 + 8);
          v20 = *(unsigned __int16 ***)(v24 + 80LL * v22 + 16);
          break;
        }
        if ( v17 == 4 )
          v18 = 88;
        else
LABEL_53:
          v18 = 89;
        goto LABEL_59;
      case 8:
        if ( v17 >= 8 )
          goto LABEL_53;
        if ( v17 == 4 )
        {
          v18 = 89;
          v19 = 0;
          v20 = 0;
        }
        else
        {
          v18 = 87;
          v19 = *(unsigned __int16 ***)(v24 + 80LL * v22 + 8);
          v20 = *(unsigned __int16 ***)(v24 + 80LL * v22 + 16);
        }
        v17 = 8;
        break;
      case 1:
        if ( !v17 )
        {
          v17 = 1;
          v18 = 143;
          goto LABEL_43;
        }
        if ( v17 != 1 )
          break;
        v18 = 0;
LABEL_59:
        v19 = 0;
        v20 = 0;
        break;
      default:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_4608de75ba8c308c3f60bea69d382694_Traceguids, v25, v17);
          v21 = v29;
        }
        break;
    }
LABEL_63:
    ++v22;
  }
  while ( v22 < *(_DWORD *)v21 );
  v13 = v33;
  if ( !v17 )
LABEL_65:
    v17 = 1;
  v14 = pv;
  *(_DWORD *)pv = v18;
  v14[1] = v17;
  if ( v19 )
  {
    v13 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v14 + 2), v19, v12);
    if ( v13 < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v27 = 30;
        goto LABEL_71;
      }
      goto LABEL_72;
    }
  }
  else
  {
    *((_QWORD *)v14 + 1) = 0;
  }
  if ( !v20 )
  {
    *((_QWORD *)v14 + 2) = 0;
LABEL_82:
    *a2 = (struct PillarStatusEx *)v14;
    if ( v29 )
      ShieldProvider::FreeWscAntivirusProductList(v29, v11);
    goto LABEL_84;
  }
  v13 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v14 + 4), v20, v12);
  if ( v13 >= 0 )
    goto LABEL_82;
  v26 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v27 = 31;
LABEL_71:
    WPP_SF_d(v26[2], v27, WPP_4608de75ba8c308c3f60bea69d382694_Traceguids, (unsigned int)v13);
  }
LABEL_72:
  if ( v29 )
    ShieldProvider::FreeWscAntivirusProductList(v29, v11);
LABEL_27:
  if ( v14 )
  {
    v15 = (void *)*((_QWORD *)v14 + 1);
    if ( v15 )
    {
      CoTaskMemFree(v15);
      *((_QWORD *)v14 + 1) = 0;
    }
    v16 = (void *)*((_QWORD *)v14 + 2);
    if ( v16 )
    {
      CoTaskMemFree(v16);
      *((_QWORD *)v14 + 2) = 0;
    }
    CoTaskMemFree(v14);
  }
LABEL_84:
  v3 = v13;
LABEL_85:
  CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(v31);
  return v3;
}

```

## disassembly

```asm
0x180042cd0  mov     [rsp-38h+arg_0], rbx
0x180042cd5  mov     [rsp-38h+arg_8], rdx
0x180042cda  push    rbp
0x180042cdb  push    rsi
0x180042cdc  push    rdi
0x180042cdd  push    r12
0x180042cdf  push    r13
0x180042ce1  push    r14
0x180042ce3  push    r15
0x180042ce5  mov     rbp, rsp
0x180042ce8  sub     rsp, 50h
0x180042cec  mov     rsi, rcx
0x180042cef  test    rdx, rdx
0x180042cf2  jnz     short loc_180042D37
0x180042cf4  lea     rsi, WPP_GLOBAL_Control
0x180042cfb  mov     ebx, 80070057h
0x180042d00  mov     rcx, cs:WPP_GLOBAL_Control
0x180042d07  cmp     rcx, rsi
0x180042d0a  jz      loc_1800430F2
0x180042d10  test    byte ptr [rcx+1Ch], 1
0x180042d14  jz      loc_1800430F2
0x180042d1a  mov     edx, 19h
0x180042d1f  mov     r9d, ebx
0x180042d22  lea     r8, WPP_4608de75ba8c308c3f60bea69d382694_Traceguids
0x180042d29  mov     rcx, [rcx+10h]
0x180042d2d  call    WPP_SF_d
0x180042d32  jmp     loc_1800430F2
0x180042d37  mov     [rbp+var_10], 0
0x180042d3f  lea     rcx, [rbp+var_10]
0x180042d43  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x180042d48  mov     ebx, eax
0x180042d4a  test    eax, eax
0x180042d4c  jns     short loc_180042D8C
0x180042d4e  lea     rsi, WPP_GLOBAL_Control
0x180042d55  mov     rcx, cs:WPP_GLOBAL_Control
0x180042d5c  cmp     rcx, rsi
0x180042d5f  jz      loc_1800430E9
0x180042d65  test    byte ptr [rcx+1Ch], 1
0x180042d69  jz      loc_1800430E9
0x180042d6f  mov     edx, 1Ah
0x180042d74  mov     r9d, eax
0x180042d77  lea     r8, WPP_4608de75ba8c308c3f60bea69d382694_Traceguids
0x180042d7e  mov     rcx, [rcx+10h]
0x180042d82  call    WPP_SF_d
0x180042d87  jmp     loc_1800430E9
0x180042d8c  mov     [rbp+pv], 0
0x180042d94  lea     rcx, [rbp+pv]
0x180042d98  call    ??$UtilCoTaskMemAllocObject@UPillarStatusEx@@@CommonUtil@@YAJPEAPEAUPillarStatusEx@@_K_N@Z; CommonUtil::UtilCoTaskMemAllocObject<PillarStatusEx>(PillarStatusEx * *,unsigned __int64,bool)
0x180042d9d  mov     edi, eax
0x180042d9f  test    eax, eax
0x180042da1  jns     short loc_180042E1C
0x180042da3  lea     rsi, WPP_GLOBAL_Control
0x180042daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180042db1  cmp     rcx, rsi
0x180042db4  jz      short loc_180042DD5
0x180042db6  test    byte ptr [rcx+1Ch], 1
0x180042dba  jz      short loc_180042DD5
0x180042dbc  mov     edx, 1Bh
0x180042dc1  mov     r9d, eax
0x180042dc4  lea     r8, WPP_4608de75ba8c308c3f60bea69d382694_Traceguids
0x180042dcb  mov     rcx, [rcx+10h]
0x180042dcf  call    WPP_SF_d
0x180042dd4  nop
0x180042dd5  mov     rbx, [rbp+pv]
0x180042dd9  test    rbx, rbx
0x180042ddc  jz      short loc_180042E15
0x180042dde  mov     rcx, [rbx+8]; pv
0x180042de2  test    rcx, rcx
0x180042de5  jz      short loc_180042DF5
0x180042de7  call    cs:__imp_CoTaskMemFree
0x180042ded  mov     qword ptr [rbx+8], 0
0x180042df5  mov     rcx, [rbx+10h]; pv
0x180042df9  test    rcx, rcx
0x180042dfc  jz      short loc_180042E0C
0x180042dfe  call    cs:__imp_CoTaskMemFree
0x180042e04  mov     qword ptr [rbx+10h], 0
0x180042e0c  mov     rcx, rbx; pv
0x180042e0f  call    cs:__imp_CoTaskMemFree
0x180042e15  mov     ebx, edi
0x180042e17  jmp     loc_1800430E9
0x180042e1c  mov     [rbp+var_20], 0
0x180042e24  mov     rax, [rsi]
0x180042e27  lea     rdx, [rbp+var_20]
0x180042e2b  mov     rcx, rsi
0x180042e2e  mov     rax, [rax+50h]
0x180042e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e37  mov     r14d, eax
0x180042e3a  mov     [rbp+arg_18], eax
0x180042e3d  test    eax, eax
0x180042e3f  jns     loc_180042ECF
0x180042e45  lea     rsi, WPP_GLOBAL_Control
0x180042e4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042e53  cmp     rcx, rsi
0x180042e56  jz      short loc_180042E77
0x180042e58  test    byte ptr [rcx+1Ch], 1
0x180042e5c  jz      short loc_180042E77
0x180042e5e  mov     edx, 1Ch
0x180042e63  mov     r9d, eax
0x180042e66  lea     r8, WPP_4608de75ba8c308c3f60bea69d382694_Traceguids
0x180042e6d  mov     rcx, [rcx+10h]
0x180042e71  call    WPP_SF_d
0x180042e76  nop
0x180042e77  mov     rcx, [rbp+var_20]; this
0x180042e7b  test    rcx, rcx
0x180042e7e  jz      short loc_180042E86
0x180042e80  call    ?FreeWscAntivirusProductList@ShieldProvider@@YAXPEAUtagWSC_AV_PRODUCT_INFO_LIST@@@Z; ShieldProvider::FreeWscAntivirusProductList(tagWSC_AV_PRODUCT_INFO_LIST *)
0x180042e85  nop
0x180042e86  mov     rbx, [rbp+pv]
0x180042e8a  test    rbx, rbx
0x180042e8d  jz      loc_1800430E6
0x180042e93  mov     rcx, [rbx+8]; pv
0x180042e97  test    rcx, rcx
0x180042e9a  jz      short loc_180042EAA
0x180042e9c  call    cs:__imp_CoTaskMemFree
0x180042ea2  mov     qword ptr [rbx+8], 0
0x180042eaa  mov     rcx, [rbx+10h]; pv
0x180042eae  test    rcx, rcx
0x180042eb1  jz      short loc_180042EC1
0x180042eb3  call    cs:__imp_CoTaskMemFree
0x180042eb9  mov     qword ptr [rbx+10h], 0
0x180042ec1  mov     rcx, rbx; pv
0x180042ec4  call    cs:__imp_CoTaskMemFree
0x180042eca  jmp     loc_1800430E6
0x180042ecf  xor     edi, edi
0x180042ed1  xor     r13d, r13d
0x180042ed4  xor     r12d, r12d
0x180042ed7  xor     r15d, r15d
0x180042eda  lea     rsi, WPP_GLOBAL_Control
0x180042ee1  mov     rax, [rbp+var_20]
0x180042ee5  cmp     [rax], edi
0x180042ee7  jbe     loc_180043029
0x180042eed  mov     r14d, edi
0x180042ef0  mov     ecx, r14d
0x180042ef3  lea     rbx, [rcx+rcx*4]
0x180042ef7  add     rbx, rbx
0x180042efa  mov     rcx, [rax+8]
0x180042efe  mov     r8d, 12h; MaxCount
0x180042f04  lea     rdx, aWindowsdefende; "windowsdefender://"
0x180042f0b  mov     rcx, [rcx+rbx*8+10h]; String1
0x180042f10  call    cs:__imp__wcsnicmp
0x180042f16  test    eax, eax
0x180042f18  mov     rax, [rbp+var_20]
0x180042f1c  jz      loc_180043015
0x180042f22  mov     rcx, [rax+8]
0x180042f26  cmp     dword ptr [rcx+rbx*8+20h], 36h ; '6'
0x180042f2b  jz      loc_180043015
0x180042f31  mov     r9d, [rcx+rbx*8+24h]
0x180042f36  cmp     r9d, 2
0x180042f3a  jnz     short loc_180042F51
0x180042f3c  cmp     r9d, edi
0x180042f3f  jle     loc_180043015
0x180042f45  mov     edi, r9d
0x180042f48  lea     r13d, [r9+53h]
0x180042f4c  jmp     loc_180043015
0x180042f51  cmp     r9d, 4
0x180042f55  jnz     short loc_180042F84
0x180042f57  cmp     r9d, edi
0x180042f5a  jle     short loc_180042F72
0x180042f5c  mov     edi, r9d
0x180042f5f  lea     r13d, [r9+52h]
0x180042f63  mov     r12, [rcx+rbx*8+8]
0x180042f68  mov     r15, [rcx+rbx*8+10h]
0x180042f6d  jmp     loc_180043015
0x180042f72  jnz     short loc_180042F7C
0x180042f74  mov     r13d, 58h ; 'X'
0x180042f7a  jmp     short loc_180042FDE
0x180042f7c  jge     loc_180043015
0x180042f82  jmp     short loc_180042FB9
0x180042f84  cmp     r9d, 8
0x180042f88  jnz     short loc_180042FC1
0x180042f8a  cmp     r9d, edi
0x180042f8d  jle     short loc_180042FB7
0x180042f8f  cmp     edi, 4
0x180042f92  jnz     short loc_180042FA0
0x180042f94  lea     r13d, [r9+51h]
0x180042f98  xor     r12d, r12d
0x180042f9b  xor     r15d, r15d
0x180042f9e  jmp     short loc_180042FB0
0x180042fa0  mov     r13d, 57h ; 'W'
0x180042fa6  mov     r12, [rcx+rbx*8+8]
0x180042fab  mov     r15, [rcx+rbx*8+10h]
0x180042fb0  mov     edi, 8
0x180042fb5  jmp     short loc_180043015
0x180042fb7  jnz     short loc_180043015
0x180042fb9  mov     r13d, 59h ; 'Y'
0x180042fbf  jmp     short loc_180042FDE
0x180042fc1  cmp     r9d, 1
0x180042fc5  jnz     short loc_180042FE6
0x180042fc7  test    edi, edi
0x180042fc9  jnz     short loc_180042FD6
0x180042fcb  mov     edi, r9d
0x180042fce  mov     r13d, 8Fh
0x180042fd4  jmp     short loc_180042F63
0x180042fd6  cmp     edi, 1
0x180042fd9  jnz     short loc_180043015
0x180042fdb  xor     r13d, r13d
0x180042fde  xor     r12d, r12d
0x180042fe1  xor     r15d, r15d
0x180042fe4  jmp     short loc_180043015
0x180042fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x180042fed  cmp     rcx, rsi
0x180042ff0  jz      short loc_180043015
0x180042ff2  test    byte ptr [rcx+1Ch], 1
0x180042ff6  jz      short loc_180043015
0x180042ff8  mov     edx, 1Dh
0x180042ffd  mov     [rsp+50h+var_30], edi
0x180043001  lea     r8, WPP_4608de75ba8c308c3f60bea69d382694_Traceguids
0x180043008  mov     rcx, [rcx+10h]
0x18004300c  call    WPP_SF_Dd
0x180043011  mov     rax, [rbp+var_20]
0x180043015  inc     r14d
0x180043018  cmp     r14d, [rax]
0x18004301b  jb      loc_180042EF0
0x180043021  test    edi, edi
0x180043023  mov     r14d, [rbp+arg_18]
0x180043027  jnz     short loc_18004302E
0x180043029  mov     edi, 1
0x18004302e  mov     rbx, [rbp+pv]
0x180043032  mov     [rbx], r13d
0x180043035  mov     [rbx+4], edi
0x180043038  test    r12, r12
0x18004303b  jz      short loc_18004308F
0x18004303d  lea     rcx, [rbx+8]; this
0x180043041  mov     rdx, r12; unsigned __int16 **
0x180043044  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x180043049  mov     r14d, eax
0x18004304c  test    eax, eax
0x18004304e  jns     short loc_180043097
0x180043050  mov     rcx, cs:WPP_GLOBAL_Control
0x180043057  cmp     rcx, rsi
0x18004305a  jz      short loc_18004307B
0x18004305c  test    byte ptr [rcx+1Ch], 1
0x180043060  jz      short loc_18004307B
0x180043062  mov     edx, 1Eh
0x180043067  mov     r9d, r14d
0x18004306a  lea     r8, WPP_4608de75ba8c308c3f60bea69d382694_Traceguids
0x180043071  mov     rcx, [rcx+10h]
0x180043075  call    WPP_SF_d
0x18004307a  nop
0x18004307b  mov     rcx, [rbp+var_20]; this
0x18004307f  test    rcx, rcx
0x180043082  jz      short loc_18004308A
0x180043084  call    ?FreeWscAntivirusProductList@ShieldProvider@@YAXPEAUtagWSC_AV_PRODUCT_INFO_LIST@@@Z; ShieldProvider::FreeWscAntivirusProductList(tagWSC_AV_PRODUCT_INFO_LIST *)
0x180043089  nop
0x18004308a  jmp     loc_180042E8A
0x18004308f  mov     qword ptr [rbx+8], 0
0x180043097  test    r15, r15
0x18004309a  jz      short loc_1800430C8
0x18004309c  lea     rcx, [rbx+10h]; this
0x1800430a0  mov     rdx, r15; unsigned __int16 **
0x1800430a3  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800430a8  mov     r14d, eax
0x1800430ab  test    eax, eax
0x1800430ad  jns     short loc_1800430D0
0x1800430af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800430b6  cmp     rcx, rsi
0x1800430b9  jz      short loc_18004307B
0x1800430bb  test    byte ptr [rcx+1Ch], 1
0x1800430bf  jz      short loc_18004307B
0x1800430c1  mov     edx, 1Fh
0x1800430c6  jmp     short loc_180043067
0x1800430c8  mov     qword ptr [rbx+10h], 0
0x1800430d0  mov     rax, [rbp+arg_8]
0x1800430d4  mov     [rax], rbx
0x1800430d7  mov     rcx, [rbp+var_20]; this
0x1800430db  test    rcx, rcx
0x1800430de  jz      short loc_1800430E6
0x1800430e0  call    ?FreeWscAntivirusProductList@ShieldProvider@@YAXPEAUtagWSC_AV_PRODUCT_INFO_LIST@@@Z; ShieldProvider::FreeWscAntivirusProductList(tagWSC_AV_PRODUCT_INFO_LIST *)
0x1800430e5  nop
0x1800430e6  mov     ebx, r14d
0x1800430e9  lea     rcx, [rbp+var_10]
0x1800430ed  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x1800430f2  mov     eax, ebx
0x1800430f4  mov     rbx, [rsp+50h+arg_0]
0x1800430fc  add     rsp, 50h
0x180043100  pop     r15
0x180043102  pop     r14
0x180043104  pop     r13
0x180043106  pop     r12
0x180043108  pop     rdi
0x180043109  pop     rsi
0x18004310a  pop     rbp
0x18004310b  retn
```
