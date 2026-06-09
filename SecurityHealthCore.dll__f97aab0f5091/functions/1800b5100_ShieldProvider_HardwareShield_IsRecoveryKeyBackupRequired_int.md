# ShieldProvider::HardwareShield::IsRecoveryKeyBackupRequired(int *)

- ea: `0x1800b5100`
- end: `0x1800b54d2`
- name: `?IsRecoveryKeyBackupRequired@HardwareShield@ShieldProvider@@UEAAJPEAH@Z`
- size: `978`
- prototype: `__int64 __fastcall(ShieldProvider::HardwareShield *__hidden this, int *)`
- caller_count: `13`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b54e0`
- `0x1800b54f0`
- `0x1800b5500`
- `0x1800b5510`
- `0x1800b5520`
- `0x1800b5530`
- `0x1800b5540`
- `0x1800b5550`
- `0x1800b5560`
- `0x1800b5570`
- `0x1800b5580`
- `0x1800b5590`
- `0x1800b9798`

## callees

- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x1800b5100`
- `0x1800dd3e8`
- `0x1800dd908`
- `0x1800dde6c`
- `0x1800de1bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5256`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b52e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b52ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5355`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b53c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5436`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5449`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5480`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b548f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b54aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5256`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b52e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b52ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5355`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b53c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5436`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5449`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5480`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b548f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b54aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800b528e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1800b528e`

## pseudocode

```c
__int64 __fastcall ShieldProvider::HardwareShield::IsRecoveryKeyBackupRequired(
        ShieldProvider::HardwareShield *this,
        int *a2)
{
  int v3; // ebx
  int v4; // eax
  unsigned int *v5; // r9
  HKEY v6; // rbx
  int ValueDword; // esi
  unsigned int *v8; // r9
  int v9; // edi
  int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  LSTATUS v13; // eax
  int Key; // edi
  int v15; // eax
  unsigned int *v16; // r9
  HKEY v17; // rdi
  HKEY *v18; // rsi
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  struct _SECURITY_ATTRIBUTES *v22; // [rsp+28h] [rbp-38h]
  unsigned __int16 v23[4]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v24; // [rsp+38h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v27[2]; // [rsp+50h] [rbp-10h] BYREF
  int v28; // [rsp+A0h] [rbp+40h] BYREF
  int v29; // [rsp+A8h] [rbp+48h] BYREF

  v27[0] = 0;
  v3 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(v27);
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        299,
        &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
        (unsigned int)v3);
    goto LABEL_70;
  }
  *(_DWORD *)v23 = 0;
  v29 = 0;
  v28 = 0;
  hKey = 0;
  if ( !a2 )
  {
    v3 = -2147467261;
    goto LABEL_70;
  }
  *a2 = 0;
  v4 = CommonUtil::UtilRegOpenKey(
         (CommonUtil *)&hKey,
         (HKEY *)0xFFFFFFFF80000002LL,
         (const WCHAR *)&stru_1800FF130,
         (const unsigned __int16 *)0x20019);
  v6 = hKey;
  if ( v4 < 0 )
  {
    v9 = 2;
    v29 = 2;
LABEL_25:
    v28 = 2;
    goto LABEL_26;
  }
  ValueDword = CommonUtil::UtilRegGetValueDword(
                 (CommonUtil *)hKey,
                 (HKEY)&stru_1800FF170,
                 (const unsigned __int16 *)&v29,
                 v5);
  v9 = 2;
  if ( ValueDword == -2147024894 )
  {
    v29 = 2;
  }
  else if ( ValueDword < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v12 = 300;
    goto LABEL_19;
  }
  v10 = CommonUtil::UtilRegGetValueDword((CommonUtil *)v6, (HKEY)&stru_1800FF250, (const unsigned __int16 *)&v28, v8);
  ValueDword = v10;
  if ( v10 == -2147024894 )
    goto LABEL_25;
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_20;
    v12 = 301;
LABEL_19:
    WPP_SF_d(v11[2], v12, &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids, (unsigned int)ValueDword);
LABEL_20:
    if ( v6 )
      RegCloseKey(v6);
    v3 = ValueDword;
    goto LABEL_70;
  }
  v9 = v28;
LABEL_26:
  if ( v29 || v9 )
  {
    phkResult = 0;
    v13 = RegOpenCurrentUser(0x20019u, &phkResult);
    Key = v13;
    if ( v13 > 0 )
      Key = (unsigned __int16)v13 | 0x80070000;
    if ( Key < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          302,
          &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
          (unsigned int)Key);
LABEL_34:
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( v6 )
        RegCloseKey(v6);
      v3 = Key;
      goto LABEL_70;
    }
    hKey = 0;
    v15 = CommonUtil::UtilRegOpenKey(
            (CommonUtil *)&hKey,
            (HKEY *)phkResult,
            (const WCHAR *)&stru_1800FF270,
            (const unsigned __int16 *)0x20019);
    v17 = hKey;
    ValueDword = v15;
    if ( v15 >= 0 )
      ValueDword = CommonUtil::UtilRegGetValueDword((CommonUtil *)hKey, (HKEY)&stru_1800FF1B8, v23, v16);
    if ( ValueDword == -2147024894 )
    {
      v18 = (HKEY *)phkResult;
      *(_DWORD *)v23 = 0;
      if ( v17 )
      {
        RegCloseKey(v17);
        hKey = 0;
      }
      Key = CommonUtil::UtilRegCreateKey(
              (CommonUtil *)&hKey,
              v18,
              (const WCHAR *)&stru_1800FF270,
              (const unsigned __int16 *)0x20006,
              0,
              v22);
      if ( Key < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            303,
            &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
            (unsigned int)Key);
        if ( hKey )
          RegCloseKey(hKey);
        goto LABEL_34;
      }
      v17 = hKey;
      LODWORD(v24) = *(_DWORD *)v23;
      ValueDword = CommonUtil::UtilRegSetValueInternal(
                     (CommonUtil *)hKey,
                     (const WCHAR *)&stru_1800FF1B8,
                     (const unsigned __int16 *)4,
                     4,
                     (BYTE *)&v24);
      if ( ValueDword < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_55;
        v20 = 304;
LABEL_54:
        WPP_SF_d(v19[2], v20, &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids, (unsigned int)ValueDword);
LABEL_55:
        if ( v17 )
          RegCloseKey(v17);
        if ( phkResult )
          RegCloseKey(phkResult);
        goto LABEL_20;
      }
    }
    else if ( ValueDword < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_55;
      v20 = 305;
      goto LABEL_54;
    }
    if ( v17 )
      RegCloseKey(v17);
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  *a2 = *(_DWORD *)v23 == 1;
  if ( v6 )
    RegCloseKey(v6);
  v3 = 0;
LABEL_70:
  CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(v27);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800b5100  mov     [rsp-28h+arg_0], rbx
0x1800b5105  push    rbp
0x1800b5106  push    rsi
0x1800b5107  push    rdi
0x1800b5108  push    r14
0x1800b510a  push    r15
0x1800b510c  mov     rbp, rsp
0x1800b510f  sub     rsp, 60h
0x1800b5113  xor     r15d, r15d
0x1800b5116  lea     rcx, [rbp+var_10]
0x1800b511a  mov     [rbp+var_10], r15
0x1800b511e  mov     r14, rdx
0x1800b5121  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x1800b5126  mov     ebx, eax
0x1800b5128  test    eax, eax
0x1800b512a  jns     short loc_1800B516A
0x1800b512c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5133  lea     rax, WPP_GLOBAL_Control
0x1800b513a  cmp     rcx, rax
0x1800b513d  jz      loc_1800B54B3
0x1800b5143  test    byte ptr [rcx+1Ch], 1
0x1800b5147  jz      loc_1800B54B3
0x1800b514d  mov     rcx, [rcx+10h]
0x1800b5151  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800b5158  mov     edx, 12Bh
0x1800b515d  mov     r9d, ebx
0x1800b5160  call    WPP_SF_d
0x1800b5165  jmp     loc_1800B54B3
0x1800b516a  mov     dword ptr [rbp+var_30], r15d
0x1800b516e  mov     [rbp+arg_18], r15d
0x1800b5172  mov     [rbp+arg_10], r15d
0x1800b5176  mov     [rbp+hKey], r15
0x1800b517a  test    r14, r14
0x1800b517d  jnz     short loc_1800B5189
0x1800b517f  mov     ebx, 80004003h
0x1800b5184  jmp     loc_1800B54B3
0x1800b5189  mov     r9d, 20019h; unsigned __int16 *
0x1800b518f  mov     [r14], r15d
0x1800b5192  lea     r8, stru_1800FF130; HKEY
0x1800b5199  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x1800b51a0  lea     rcx, [rbp+hKey]; this
0x1800b51a4  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,ushort const *,ulong)
0x1800b51a9  mov     rbx, [rbp+hKey]
0x1800b51ad  test    eax, eax
0x1800b51af  js      loc_1800B5268
0x1800b51b5  lea     r8, [rbp+arg_18]; unsigned __int16 *
0x1800b51b9  mov     rcx, rbx; this
0x1800b51bc  lea     rdx, stru_1800FF170; HKEY
0x1800b51c3  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,ushort const *,ulong *)
0x1800b51c8  mov     esi, eax
0x1800b51ca  mov     edi, 2
0x1800b51cf  cmp     eax, 80070002h
0x1800b51d4  jnz     short loc_1800B5219
0x1800b51d6  mov     [rbp+arg_18], edi
0x1800b51d9  lea     r8, [rbp+arg_10]; unsigned __int16 *
0x1800b51dd  mov     rcx, rbx; this
0x1800b51e0  lea     rdx, stru_1800FF250; HKEY
0x1800b51e7  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,ushort const *,ulong *)
0x1800b51ec  mov     esi, eax
0x1800b51ee  cmp     eax, 80070002h
0x1800b51f3  jz      short loc_1800B5270
0x1800b51f5  test    eax, eax
0x1800b51f7  jns     short loc_1800B5263
0x1800b51f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5200  lea     rax, WPP_GLOBAL_Control
0x1800b5207  cmp     rcx, rax
0x1800b520a  jz      short loc_1800B524E
0x1800b520c  test    byte ptr [rcx+1Ch], 1
0x1800b5210  jz      short loc_1800B524E
0x1800b5212  mov     edx, 12Dh
0x1800b5217  jmp     short loc_1800B523B
0x1800b5219  test    esi, esi
0x1800b521b  jns     short loc_1800B51D9
0x1800b521d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5224  lea     rax, WPP_GLOBAL_Control
0x1800b522b  cmp     rcx, rax
0x1800b522e  jz      short loc_1800B524E
0x1800b5230  test    byte ptr [rcx+1Ch], 1
0x1800b5234  jz      short loc_1800B524E
0x1800b5236  mov     edx, 12Ch
0x1800b523b  mov     rcx, [rcx+10h]
0x1800b523f  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800b5246  mov     r9d, esi
0x1800b5249  call    WPP_SF_d
0x1800b524e  test    rbx, rbx
0x1800b5251  jz      short loc_1800B525C
0x1800b5253  mov     rcx, rbx; hKey
0x1800b5256  call    cs:__imp_RegCloseKey
0x1800b525c  mov     ebx, esi
0x1800b525e  jmp     loc_1800B54B3
0x1800b5263  mov     edi, [rbp+arg_10]
0x1800b5266  jmp     short loc_1800B5273
0x1800b5268  mov     edi, 2
0x1800b526d  mov     [rbp+arg_18], edi
0x1800b5270  mov     [rbp+arg_10], edi
0x1800b5273  cmp     [rbp+arg_18], r15d
0x1800b5277  jnz     short loc_1800B5281
0x1800b5279  test    edi, edi
0x1800b527b  jz      loc_1800B5495
0x1800b5281  lea     rdx, [rbp+phkResult]; phkResult
0x1800b5285  mov     [rbp+phkResult], r15
0x1800b5289  mov     ecx, 20019h; samDesired
0x1800b528e  call    cs:__imp_RegOpenCurrentUser
0x1800b5294  mov     edi, eax
0x1800b5296  test    eax, eax
0x1800b5298  jle     short loc_1800B52A3
0x1800b529a  movzx   edi, ax
0x1800b529d  or      edi, 80070000h
0x1800b52a3  test    edi, edi
0x1800b52a5  jns     short loc_1800B52FC
0x1800b52a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b52ae  lea     rax, WPP_GLOBAL_Control
0x1800b52b5  cmp     rcx, rax
0x1800b52b8  jz      short loc_1800B52D8
0x1800b52ba  test    byte ptr [rcx+1Ch], 1
0x1800b52be  jz      short loc_1800B52D8
0x1800b52c0  mov     rcx, [rcx+10h]
0x1800b52c4  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800b52cb  mov     edx, 12Eh
0x1800b52d0  mov     r9d, edi
0x1800b52d3  call    WPP_SF_d
0x1800b52d8  mov     rcx, [rbp+phkResult]; hKey
0x1800b52dc  test    rcx, rcx
0x1800b52df  jz      short loc_1800B52E7
0x1800b52e1  call    cs:__imp_RegCloseKey
0x1800b52e7  test    rbx, rbx
0x1800b52ea  jz      short loc_1800B52F5
0x1800b52ec  mov     rcx, rbx; hKey
0x1800b52ef  call    cs:__imp_RegCloseKey
0x1800b52f5  mov     ebx, edi
0x1800b52f7  jmp     loc_1800B54B3
0x1800b52fc  mov     rdx, [rbp+phkResult]; HKEY *
0x1800b5300  lea     r8, stru_1800FF270; HKEY
0x1800b5307  mov     r9d, 20019h; unsigned __int16 *
0x1800b530d  mov     [rbp+hKey], r15
0x1800b5311  lea     rcx, [rbp+hKey]; this
0x1800b5315  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,ushort const *,ulong)
0x1800b531a  mov     rdi, [rbp+hKey]
0x1800b531e  mov     esi, eax
0x1800b5320  test    eax, eax
0x1800b5322  js      short loc_1800B5339
0x1800b5324  lea     r8, [rbp+var_30]; unsigned __int16 *
0x1800b5328  mov     rcx, rdi; this
0x1800b532b  lea     rdx, stru_1800FF1B8; HKEY
0x1800b5332  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,ushort const *,ulong *)
0x1800b5337  mov     esi, eax
0x1800b5339  cmp     esi, 80070002h
0x1800b533f  jnz     loc_1800B5454
0x1800b5345  mov     rsi, [rbp+phkResult]
0x1800b5349  mov     dword ptr [rbp+var_30], r15d
0x1800b534d  test    rdi, rdi
0x1800b5350  jz      short loc_1800B535F
0x1800b5352  mov     rcx, rdi; hKey
0x1800b5355  call    cs:__imp_RegCloseKey
0x1800b535b  mov     [rbp+hKey], r15
0x1800b535f  mov     r9d, 20006h; unsigned __int16 *
0x1800b5365  mov     qword ptr [rsp+60h+var_40], r15; unsigned int
0x1800b536a  lea     r8, stru_1800FF270; HKEY
0x1800b5371  mov     rdx, rsi; HKEY *
0x1800b5374  lea     rcx, [rbp+hKey]; this
0x1800b5378  call    ?UtilRegCreateKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGKPEAU_SECURITY_ATTRIBUTES@@K@Z; CommonUtil::UtilRegCreateKey(HKEY__ * *,HKEY__ *,ushort const *,ulong,_SECURITY_ATTRIBUTES *,ulong)
0x1800b537d  mov     edi, eax
0x1800b537f  test    eax, eax
0x1800b5381  jns     short loc_1800B53CC
0x1800b5383  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b538a  lea     rax, WPP_GLOBAL_Control
0x1800b5391  cmp     rcx, rax
0x1800b5394  jz      short loc_1800B53B4
0x1800b5396  test    byte ptr [rcx+1Ch], 1
0x1800b539a  jz      short loc_1800B53B4
0x1800b539c  mov     rcx, [rcx+10h]
0x1800b53a0  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800b53a7  mov     edx, 12Fh
0x1800b53ac  mov     r9d, edi
0x1800b53af  call    WPP_SF_d
0x1800b53b4  mov     rcx, [rbp+hKey]; hKey
0x1800b53b8  test    rcx, rcx
0x1800b53bb  jz      loc_1800B52D8
0x1800b53c1  call    cs:__imp_RegCloseKey
0x1800b53c7  jmp     loc_1800B52D8
0x1800b53cc  mov     eax, dword ptr [rbp+var_30]
0x1800b53cf  lea     rdx, stru_1800FF1B8; HKEY
0x1800b53d6  mov     rdi, [rbp+hKey]
0x1800b53da  mov     r8d, 4; unsigned __int16 *
0x1800b53e0  mov     dword ptr [rbp+var_28], eax
0x1800b53e3  mov     r9d, r8d; unsigned int
0x1800b53e6  lea     rax, [rbp+var_28]
0x1800b53ea  mov     rcx, rdi; this
0x1800b53ed  mov     qword ptr [rsp+60h+var_40], rax; unsigned __int64
0x1800b53f2  call    ?UtilRegSetValueInternal@CommonUtil@@YAJPEAUHKEY__@@PEBGK_KPEBX@Z; CommonUtil::UtilRegSetValueInternal(HKEY__ *,ushort const *,ulong,unsigned __int64,void const *)
0x1800b53f7  mov     esi, eax
0x1800b53f9  test    eax, eax
0x1800b53fb  jns     short loc_1800B5478
0x1800b53fd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b5404  lea     rax, WPP_GLOBAL_Control
0x1800b540b  cmp     rcx, rax
0x1800b540e  jz      short loc_1800B542E
0x1800b5410  test    byte ptr [rcx+1Ch], 1
0x1800b5414  jz      short loc_1800B542E
0x1800b5416  mov     edx, 130h
0x1800b541b  mov     rcx, [rcx+10h]
0x1800b541f  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800b5426  mov     r9d, esi
0x1800b5429  call    WPP_SF_d
0x1800b542e  test    rdi, rdi
0x1800b5431  jz      short loc_1800B543C
0x1800b5433  mov     rcx, rdi; hKey
0x1800b5436  call    cs:__imp_RegCloseKey
0x1800b543c  mov     rcx, [rbp+phkResult]; hKey
0x1800b5440  test    rcx, rcx
0x1800b5443  jz      loc_1800B524E
0x1800b5449  call    cs:__imp_RegCloseKey
0x1800b544f  jmp     loc_1800B524E
0x1800b5454  test    esi, esi
0x1800b5456  jns     short loc_1800B5478
0x1800b5458  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b545f  lea     rax, WPP_GLOBAL_Control
0x1800b5466  cmp     rcx, rax
0x1800b5469  jz      short loc_1800B542E
0x1800b546b  test    byte ptr [rcx+1Ch], 1
0x1800b546f  jz      short loc_1800B542E
0x1800b5471  mov     edx, 131h
0x1800b5476  jmp     short loc_1800B541B
0x1800b5478  test    rdi, rdi
0x1800b547b  jz      short loc_1800B5486
0x1800b547d  mov     rcx, rdi; hKey
0x1800b5480  call    cs:__imp_RegCloseKey
0x1800b5486  mov     rcx, [rbp+phkResult]; hKey
0x1800b548a  test    rcx, rcx
0x1800b548d  jz      short loc_1800B5495
0x1800b548f  call    cs:__imp_RegCloseKey
0x1800b5495  cmp     dword ptr [rbp+var_30], 1
0x1800b5499  mov     eax, r15d
0x1800b549c  setz    al
0x1800b549f  mov     [r14], eax
0x1800b54a2  test    rbx, rbx
0x1800b54a5  jz      short loc_1800B54B0
0x1800b54a7  mov     rcx, rbx; hKey
0x1800b54aa  call    cs:__imp_RegCloseKey
0x1800b54b0  mov     ebx, r15d
0x1800b54b3  lea     rcx, [rbp+var_10]
0x1800b54b7  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x1800b54bc  mov     eax, ebx
0x1800b54be  mov     rbx, [rsp+60h+arg_0]
0x1800b54c6  add     rsp, 60h
0x1800b54ca  pop     r15
0x1800b54cc  pop     r14
0x1800b54ce  pop     rdi
0x1800b54cf  pop     rsi
0x1800b54d0  pop     rbp
0x1800b54d1  retn
```
