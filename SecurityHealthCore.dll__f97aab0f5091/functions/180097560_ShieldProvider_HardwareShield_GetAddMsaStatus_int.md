# ShieldProvider::HardwareShield::GetAddMsaStatus(int *)

- ea: `0x180097560`
- end: `0x18009785e`
- name: `?GetAddMsaStatus@HardwareShield@ShieldProvider@@UEAAJPEAH@Z`
- size: `766`
- prototype: `__int64 __fastcall(ShieldProvider::HardwareShield *__hidden this, int *)`
- caller_count: `6`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180097870`
- `0x180097880`
- `0x180097890`
- `0x1800978a0`
- `0x1800978b0`
- `0x1800978c0`

## callees

- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x180097560`
- `0x1800d7c64`
- `0x1800dd3e8`
- `0x1800dd908`
- `0x1800dde6c`
- `0x1800de1bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009765f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180097706`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180097715`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009772f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800977a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800977b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009782e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009783d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009765f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180097706`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180097715`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009772f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800977a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800977b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009782e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009783d`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18009760b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18009760b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ShieldProvider::HardwareShield::GetAddMsaStatus(ShieldProvider::HardwareShield *this, int *a2)
{
  int Key; // ebx
  LSTATUS v4; // eax
  int *v5; // rdx
  int ValueDword; // ecx
  unsigned int *v7; // r9
  HKEY v8; // rbx
  int DataEncryptionNudgeStatus; // esi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  HKEY *v12; // rsi
  struct _SECURITY_ATTRIBUTES *v14; // [rsp+28h] [rbp-28h]
  unsigned __int64 v15; // [rsp+30h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  __int64 v18; // [rsp+48h] [rbp-8h] BYREF
  BOOL v19; // [rsp+80h] [rbp+30h] BYREF
  int v20; // [rsp+88h] [rbp+38h] BYREF

  v18 = 0;
  Key = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&v18);
  if ( Key < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        314,
        &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
        (unsigned int)Key);
    goto LABEL_48;
  }
  v15 = 0;
  hKey = 0;
  v20 = 0;
  v19 = 0;
  if ( !a2 )
  {
    Key = -2147467261;
    goto LABEL_48;
  }
  *a2 = 0;
  phkResult = 0;
  v4 = RegOpenCurrentUser(0xF003Fu, &phkResult);
  Key = v4;
  if ( v4 > 0 )
    Key = (unsigned __int16)v4 | 0x80070000;
  if ( Key < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        315,
        &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
        (unsigned int)Key);
    if ( phkResult )
      RegCloseKey(phkResult);
    goto LABEL_48;
  }
  ValueDword = CommonUtil::UtilRegOpenKey(
                 (CommonUtil *)&hKey,
                 (HKEY *)phkResult,
                 (const WCHAR *)&stru_1800FF3F0,
                 (const unsigned __int16 *)0x2001F);
  v8 = hKey;
  if ( ValueDword >= 0 )
  {
    ValueDword = CommonUtil::UtilRegGetValueDword(
                   (CommonUtil *)hKey,
                   (HKEY)&stru_1800FF300,
                   (const unsigned __int16 *)&v20,
                   v7);
    v19 = v20 == 1;
  }
  if ( ValueDword == -2147024894 )
  {
    DataEncryptionNudgeStatus = ShieldProvider::GetDataEncryptionNudgeStatus((ShieldProvider *)&v19, v5);
    if ( DataEncryptionNudgeStatus < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v11 = 316;
LABEL_23:
      WPP_SF_d(v10[2], v11, &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids, (unsigned int)DataEncryptionNudgeStatus);
LABEL_24:
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( v8 )
        RegCloseKey(v8);
      Key = DataEncryptionNudgeStatus;
      goto LABEL_48;
    }
    v12 = (HKEY *)phkResult;
    if ( v8 )
    {
      RegCloseKey(v8);
      hKey = 0;
    }
    Key = CommonUtil::UtilRegCreateKey(
            (CommonUtil *)&hKey,
            v12,
            (const WCHAR *)&stru_1800FF3F0,
            (const unsigned __int16 *)0x20006,
            0,
            v14);
    if ( Key < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          317,
          &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
          (unsigned int)Key);
      if ( phkResult )
        RegCloseKey(phkResult);
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_48;
    }
    LODWORD(v15) = v19;
    v8 = hKey;
    DataEncryptionNudgeStatus = CommonUtil::UtilRegSetValueInternal(
                                  (CommonUtil *)hKey,
                                  (const WCHAR *)&stru_1800FF300,
                                  (const unsigned __int16 *)4,
                                  4,
                                  (BYTE *)&v15);
    if ( DataEncryptionNudgeStatus < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v11 = 318;
      goto LABEL_23;
    }
  }
  *a2 = v19;
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v8 )
    RegCloseKey(v8);
  Key = 0;
LABEL_48:
  CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v18);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x180097560  mov     [rsp-18h+arg_0], rbx
0x180097565  push    rbp
0x180097566  push    rsi
0x180097567  push    rdi
0x180097568  mov     rbp, rsp
0x18009756b  sub     rsp, 50h
0x18009756f  mov     rdi, rdx
0x180097572  mov     [rbp+var_8], 0
0x18009757a  lea     rcx, [rbp+var_8]
0x18009757e  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x180097583  mov     ebx, eax
0x180097585  test    eax, eax
0x180097587  jns     short loc_1800975C7
0x180097589  lea     rax, WPP_GLOBAL_Control
0x180097590  mov     rcx, cs:WPP_GLOBAL_Control
0x180097597  cmp     rcx, rax
0x18009759a  jz      loc_180097846
0x1800975a0  test    byte ptr [rcx+1Ch], 1
0x1800975a4  jz      loc_180097846
0x1800975aa  mov     edx, 13Ah
0x1800975af  mov     r9d, ebx
0x1800975b2  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800975b9  mov     rcx, [rcx+10h]
0x1800975bd  call    WPP_SF_d
0x1800975c2  jmp     loc_180097846
0x1800975c7  mov     [rbp+var_20], 0
0x1800975cf  mov     [rbp+hKey], 0
0x1800975d7  mov     [rbp+arg_18], 0
0x1800975de  mov     [rbp+arg_10], 0
0x1800975e5  test    rdi, rdi
0x1800975e8  jnz     short loc_1800975F4
0x1800975ea  mov     ebx, 80004003h
0x1800975ef  jmp     loc_180097846
0x1800975f4  mov     dword ptr [rdi], 0
0x1800975fa  mov     [rbp+phkResult], 0
0x180097602  lea     rdx, [rbp+phkResult]; phkResult
0x180097606  mov     ecx, 0F003Fh; samDesired
0x18009760b  call    cs:__imp_RegOpenCurrentUser
0x180097611  mov     ebx, eax
0x180097613  test    eax, eax
0x180097615  jle     short loc_180097620
0x180097617  movzx   ebx, ax
0x18009761a  or      ebx, 80070000h
0x180097620  test    ebx, ebx
0x180097622  jns     short loc_18009766B
0x180097624  lea     rax, WPP_GLOBAL_Control
0x18009762b  mov     rcx, cs:WPP_GLOBAL_Control
0x180097632  cmp     rcx, rax
0x180097635  jz      short loc_180097656
0x180097637  test    byte ptr [rcx+1Ch], 1
0x18009763b  jz      short loc_180097656
0x18009763d  mov     edx, 13Bh
0x180097642  mov     r9d, ebx
0x180097645  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x18009764c  mov     rcx, [rcx+10h]
0x180097650  call    WPP_SF_d
0x180097655  nop
0x180097656  mov     rcx, [rbp+phkResult]; hKey
0x18009765a  test    rcx, rcx
0x18009765d  jz      short loc_180097666
0x18009765f  call    cs:__imp_RegCloseKey
0x180097665  nop
0x180097666  jmp     loc_180097846
0x18009766b  mov     r9d, 2001Fh; unsigned __int16 *
0x180097671  lea     r8, stru_1800FF3F0; HKEY
0x180097678  mov     rdx, [rbp+phkResult]; HKEY *
0x18009767c  lea     rcx, [rbp+hKey]; this
0x180097680  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,ushort const *,ulong)
0x180097685  mov     ecx, eax
0x180097687  mov     rbx, [rbp+hKey]
0x18009768b  test    eax, eax
0x18009768d  js      short loc_1800976B0
0x18009768f  lea     r8, [rbp+arg_18]; unsigned __int16 *
0x180097693  lea     rdx, stru_1800FF300; HKEY
0x18009769a  mov     rcx, rbx; this
0x18009769d  call    ?UtilRegGetValueDword@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAK@Z; CommonUtil::UtilRegGetValueDword(HKEY__ *,ushort const *,ulong *)
0x1800976a2  mov     ecx, eax
0x1800976a4  xor     eax, eax
0x1800976a6  cmp     [rbp+arg_18], 1
0x1800976aa  setz    al
0x1800976ad  mov     [rbp+arg_10], eax
0x1800976b0  cmp     ecx, 80070002h
0x1800976b6  jnz     loc_180097820
0x1800976bc  lea     rcx, [rbp+arg_10]; this
0x1800976c0  call    ?GetDataEncryptionNudgeStatus@ShieldProvider@@YAJPEAH@Z; ShieldProvider::GetDataEncryptionNudgeStatus(int *)
0x1800976c5  mov     esi, eax
0x1800976c7  test    eax, eax
0x1800976c9  jns     short loc_180097723
0x1800976cb  lea     rax, WPP_GLOBAL_Control
0x1800976d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800976d9  cmp     rcx, rax
0x1800976dc  jz      short loc_1800976FD
0x1800976de  test    byte ptr [rcx+1Ch], 1
0x1800976e2  jz      short loc_1800976FD
0x1800976e4  mov     edx, 13Ch
0x1800976e9  mov     r9d, esi
0x1800976ec  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800976f3  mov     rcx, [rcx+10h]
0x1800976f7  call    WPP_SF_d
0x1800976fc  nop
0x1800976fd  mov     rcx, [rbp+phkResult]; hKey
0x180097701  test    rcx, rcx
0x180097704  jz      short loc_18009770D
0x180097706  call    cs:__imp_RegCloseKey
0x18009770c  nop
0x18009770d  test    rbx, rbx
0x180097710  jz      short loc_18009771C
0x180097712  mov     rcx, rbx; hKey
0x180097715  call    cs:__imp_RegCloseKey
0x18009771b  nop
0x18009771c  mov     ebx, esi
0x18009771e  jmp     loc_180097846
0x180097723  mov     rsi, [rbp+phkResult]
0x180097727  test    rbx, rbx
0x18009772a  jz      short loc_18009773D
0x18009772c  mov     rcx, rbx; hKey
0x18009772f  call    cs:__imp_RegCloseKey
0x180097735  mov     [rbp+hKey], 0
0x18009773d  mov     qword ptr [rsp+50h+var_30], 0; unsigned int
0x180097746  mov     r9d, 20006h; unsigned __int16 *
0x18009774c  lea     r8, stru_1800FF3F0; HKEY
0x180097753  mov     rdx, rsi; HKEY *
0x180097756  lea     rcx, [rbp+hKey]; this
0x18009775a  call    ?UtilRegCreateKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGKPEAU_SECURITY_ATTRIBUTES@@K@Z; CommonUtil::UtilRegCreateKey(HKEY__ * *,HKEY__ *,ushort const *,ulong,_SECURITY_ATTRIBUTES *,ulong)
0x18009775f  mov     ebx, eax
0x180097761  test    eax, eax
0x180097763  jns     short loc_1800977BF
0x180097765  lea     rax, WPP_GLOBAL_Control
0x18009776c  mov     rcx, cs:WPP_GLOBAL_Control
0x180097773  cmp     rcx, rax
0x180097776  jz      short loc_180097797
0x180097778  test    byte ptr [rcx+1Ch], 1
0x18009777c  jz      short loc_180097797
0x18009777e  mov     edx, 13Dh
0x180097783  mov     r9d, ebx
0x180097786  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x18009778d  mov     rcx, [rcx+10h]
0x180097791  call    WPP_SF_d
0x180097796  nop
0x180097797  mov     rcx, [rbp+phkResult]; hKey
0x18009779b  test    rcx, rcx
0x18009779e  jz      short loc_1800977A7
0x1800977a0  call    cs:__imp_RegCloseKey
0x1800977a6  nop
0x1800977a7  mov     rcx, [rbp+hKey]; hKey
0x1800977ab  test    rcx, rcx
0x1800977ae  jz      loc_180097666
0x1800977b4  call    cs:__imp_RegCloseKey
0x1800977ba  jmp     loc_180097666
0x1800977bf  xor     eax, eax
0x1800977c1  cmp     [rbp+arg_10], eax
0x1800977c4  setnz   al
0x1800977c7  mov     dword ptr [rbp+var_20], eax
0x1800977ca  lea     rax, [rbp+var_20]
0x1800977ce  mov     qword ptr [rsp+50h+var_30], rax; unsigned __int64
0x1800977d3  mov     r8d, 4; unsigned __int16 *
0x1800977d9  mov     r9d, r8d; unsigned int
0x1800977dc  lea     rdx, stru_1800FF300; HKEY
0x1800977e3  mov     rbx, [rbp+hKey]
0x1800977e7  mov     rcx, rbx; this
0x1800977ea  call    ?UtilRegSetValueInternal@CommonUtil@@YAJPEAUHKEY__@@PEBGK_KPEBX@Z; CommonUtil::UtilRegSetValueInternal(HKEY__ *,ushort const *,ulong,unsigned __int64,void const *)
0x1800977ef  mov     esi, eax
0x1800977f1  test    eax, eax
0x1800977f3  jns     short loc_180097820
0x1800977f5  lea     rax, WPP_GLOBAL_Control
0x1800977fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180097803  cmp     rcx, rax
0x180097806  jz      loc_1800976FD
0x18009780c  test    byte ptr [rcx+1Ch], 1
0x180097810  jz      loc_1800976FD
0x180097816  mov     edx, 13Eh
0x18009781b  jmp     loc_1800976E9
0x180097820  mov     eax, [rbp+arg_10]
0x180097823  mov     [rdi], eax
0x180097825  mov     rcx, [rbp+phkResult]; hKey
0x180097829  test    rcx, rcx
0x18009782c  jz      short loc_180097835
0x18009782e  call    cs:__imp_RegCloseKey
0x180097834  nop
0x180097835  test    rbx, rbx
0x180097838  jz      short loc_180097844
0x18009783a  mov     rcx, rbx; hKey
0x18009783d  call    cs:__imp_RegCloseKey
0x180097843  nop
0x180097844  xor     ebx, ebx
0x180097846  lea     rcx, [rbp+var_8]
0x18009784a  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18009784f  mov     eax, ebx
0x180097851  mov     rbx, [rsp+50h+arg_0]
0x180097856  add     rsp, 50h
0x18009785a  pop     rdi
0x18009785b  pop     rsi
0x18009785c  pop     rbp
0x18009785d  retn
```
