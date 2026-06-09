# ShieldProvider::DataProtectionShield::CheckIsOneDriveInstalled(bool *)

- ea: `0x180076ea0`
- end: `0x180077128`
- name: `?CheckIsOneDriveInstalled@DataProtectionShield@ShieldProvider@@AEAAJPEA_N@Z`
- size: `648`
- prototype: `__int64 __fastcall(ShieldProvider::DataProtectionShield *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180079a00`

## callees

- `0x180004ae0`
- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x180015894`
- `0x180076ea0`
- `0x1800dd3e8`
- `0x1800ddaa8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076f77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077007`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077097`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800770a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800770fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007710c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076f77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077007`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180077097`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800770a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800770fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007710c`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180076f1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180076f1e`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::CheckIsOneDriveInstalled(
        ShieldProvider::DataProtectionShield *this,
        bool *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  int Key; // eax
  HKEY v7; // rcx
  HKEY v8; // rbx
  int ValueString; // eax
  const struct std::nothrow_t *v10; // rdx
  unsigned int v11; // edi
  void *v12; // rcx
  const struct std::nothrow_t *v13; // rdx
  void *v14; // rdi
  struct _SECURITY_ATTRIBUTES *v16; // [rsp+28h] [rbp-10h]
  HKEY phkResult; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF
  void *v19; // [rsp+70h] [rbp+38h] BYREF
  __int64 v20; // [rsp+78h] [rbp+40h] BYREF

  phkResult = (HKEY)this;
  *a2 = 0;
  v20 = 0;
  v3 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&v20);
  v4 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
        (unsigned int)v3);
    goto LABEL_49;
  }
  phkResult = 0;
  v5 = RegOpenCurrentUser(0x20019u, &phkResult);
  v4 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
    if ( (v4 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, v4);
LABEL_12:
      if ( phkResult )
        RegCloseKey(phkResult);
      goto LABEL_49;
    }
  }
  hKey = 0;
  Key = CommonUtil::UtilRegCreateKey(
          (CommonUtil *)&hKey,
          (HKEY *)phkResult,
          (const WCHAR *)&stru_1800FD9B8,
          (const unsigned __int16 *)0x20019,
          0,
          v16);
  v4 = Key;
  if ( Key == -2147024894 )
  {
    v7 = hKey;
    if ( hKey )
      goto LABEL_45;
    goto LABEL_46;
  }
  if ( Key < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
        (unsigned int)Key);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_12;
  }
  v8 = hKey;
  v19 = 0;
  ValueString = CommonUtil::UtilRegGetValueString(hKey, L"Version", &v19);
  v11 = ValueString;
  if ( ValueString == -2147024894 )
  {
    v12 = v19;
    if ( !v19 )
      goto LABEL_43;
    goto LABEL_42;
  }
  if ( ValueString >= 0 )
  {
    v10 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    v14 = v19;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, v19);
    *a2 = 1;
    if ( !v14 )
    {
LABEL_43:
      if ( v8 )
      {
        v7 = v8;
LABEL_45:
        RegCloseKey(v7);
      }
LABEL_46:
      if ( phkResult )
        RegCloseKey(phkResult);
      v4 = 0;
      goto LABEL_49;
    }
    v12 = v14;
LABEL_42:
    operator delete(v12, v10);
    goto LABEL_43;
  }
  v13 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      61,
      WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
      (unsigned int)ValueString);
  if ( v19 )
    operator delete(v19, v13);
  if ( v8 )
    RegCloseKey(v8);
  if ( phkResult )
    RegCloseKey(phkResult);
  v4 = v11;
LABEL_49:
  CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v20);
  return v4;
}

```

## disassembly

```asm
0x180076ea0  mov     [rsp-20h+phkResult], rcx
0x180076ea5  push    rbp
0x180076ea6  push    rbx
0x180076ea7  push    rsi
0x180076ea8  push    rdi
0x180076ea9  mov     rbp, rsp
0x180076eac  sub     rsp, 38h
0x180076eb0  lea     rcx, [rbp+arg_18]
0x180076eb4  mov     byte ptr [rdx], 0
0x180076eb7  mov     rsi, rdx
0x180076eba  mov     [rbp+arg_18], 0
0x180076ec2  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x180076ec7  mov     ebx, eax
0x180076ec9  test    eax, eax
0x180076ecb  jns     short loc_180076F0B
0x180076ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180076ed4  lea     rdx, WPP_GLOBAL_Control
0x180076edb  cmp     rcx, rdx
0x180076ede  jz      loc_180077114
0x180076ee4  test    byte ptr [rcx+1Ch], 1
0x180076ee8  jz      loc_180077114
0x180076eee  mov     rcx, [rcx+10h]
0x180076ef2  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180076ef9  mov     edx, 3Ah ; ':'
0x180076efe  mov     r9d, eax
0x180076f01  call    WPP_SF_d
0x180076f06  jmp     loc_180077114
0x180076f0b  mov     edi, 20019h
0x180076f10  mov     [rbp+phkResult], 0
0x180076f18  mov     ecx, edi; samDesired
0x180076f1a  lea     rdx, [rbp+phkResult]; phkResult
0x180076f1e  call    cs:__imp_RegOpenCurrentUser
0x180076f24  mov     ebx, eax
0x180076f26  test    eax, eax
0x180076f28  jz      short loc_180076F82
0x180076f2a  jle     short loc_180076F35
0x180076f2c  movzx   ebx, ax
0x180076f2f  or      ebx, 80070000h
0x180076f35  test    ebx, ebx
0x180076f37  jns     short loc_180076F82
0x180076f39  mov     rcx, cs:WPP_GLOBAL_Control
0x180076f40  lea     rdx, WPP_GLOBAL_Control
0x180076f47  cmp     rcx, rdx
0x180076f4a  jz      short loc_180076F6A
0x180076f4c  test    byte ptr [rcx+1Ch], 1
0x180076f50  jz      short loc_180076F6A
0x180076f52  mov     rcx, [rcx+10h]
0x180076f56  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180076f5d  mov     edx, 3Bh ; ';'
0x180076f62  mov     r9d, ebx
0x180076f65  call    WPP_SF_d
0x180076f6a  mov     rcx, [rbp+phkResult]; hKey
0x180076f6e  test    rcx, rcx
0x180076f71  jz      loc_180077114
0x180076f77  call    cs:__imp_RegCloseKey
0x180076f7d  jmp     loc_180077114
0x180076f82  mov     rdx, [rbp+phkResult]; HKEY *
0x180076f86  lea     r8, stru_1800FD9B8; HKEY
0x180076f8d  mov     r9d, edi; unsigned __int16 *
0x180076f90  mov     [rbp+hKey], 0
0x180076f98  lea     rcx, [rbp+hKey]; this
0x180076f9c  mov     qword ptr [rsp+38h+var_18], 0; unsigned int
0x180076fa5  call    ?UtilRegCreateKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGKPEAU_SECURITY_ATTRIBUTES@@K@Z; CommonUtil::UtilRegCreateKey(HKEY__ * *,HKEY__ *,ushort const *,ulong,_SECURITY_ATTRIBUTES *,ulong)
0x180076faa  mov     ebx, eax
0x180076fac  cmp     eax, 80070002h
0x180076fb1  jnz     short loc_180076FC5
0x180076fb3  mov     rcx, [rbp+hKey]
0x180076fb7  test    rcx, rcx
0x180076fba  jz      loc_180077103
0x180076fc0  jmp     loc_1800770FD
0x180076fc5  test    eax, eax
0x180076fc7  jns     short loc_180077012
0x180076fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180076fd0  lea     rdx, WPP_GLOBAL_Control
0x180076fd7  cmp     rcx, rdx
0x180076fda  jz      short loc_180076FFA
0x180076fdc  test    byte ptr [rcx+1Ch], 1
0x180076fe0  jz      short loc_180076FFA
0x180076fe2  mov     rcx, [rcx+10h]
0x180076fe6  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180076fed  mov     edx, 3Ch ; '<'
0x180076ff2  mov     r9d, eax
0x180076ff5  call    WPP_SF_d
0x180076ffa  mov     rcx, [rbp+hKey]; hKey
0x180076ffe  test    rcx, rcx
0x180077001  jz      loc_180076F6A
0x180077007  call    cs:__imp_RegCloseKey
0x18007700d  jmp     loc_180076F6A
0x180077012  mov     rbx, [rbp+hKey]
0x180077016  lea     r8, [rbp+arg_10]
0x18007701a  mov     rcx, rbx
0x18007701d  mov     [rbp+arg_10], 0
0x180077025  lea     rdx, aVersion; "Version"
0x18007702c  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAPEAGW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,ushort const *,ushort * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x180077031  mov     edi, eax
0x180077033  cmp     eax, 80070002h
0x180077038  jnz     short loc_18007704C
0x18007703a  mov     rcx, [rbp+arg_10]
0x18007703e  test    rcx, rcx
0x180077041  jz      loc_1800770F5
0x180077047  jmp     loc_1800770F0
0x18007704c  test    edi, edi
0x18007704e  jns     short loc_1800770B0
0x180077050  mov     rcx, cs:WPP_GLOBAL_Control
0x180077057  lea     rdx, WPP_GLOBAL_Control
0x18007705e  cmp     rcx, rdx
0x180077061  jz      short loc_180077081
0x180077063  test    byte ptr [rcx+1Ch], 1
0x180077067  jz      short loc_180077081
0x180077069  mov     rcx, [rcx+10h]
0x18007706d  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x180077074  mov     edx, 3Dh ; '='
0x180077079  mov     r9d, edi
0x18007707c  call    WPP_SF_d
0x180077081  mov     rcx, [rbp+arg_10]; void *
0x180077085  test    rcx, rcx
0x180077088  jz      short loc_18007708F
0x18007708a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007708f  test    rbx, rbx
0x180077092  jz      short loc_18007709D
0x180077094  mov     rcx, rbx; hKey
0x180077097  call    cs:__imp_RegCloseKey
0x18007709d  mov     rcx, [rbp+phkResult]; hKey
0x1800770a1  test    rcx, rcx
0x1800770a4  jz      short loc_1800770AC
0x1800770a6  call    cs:__imp_RegCloseKey
0x1800770ac  mov     ebx, edi
0x1800770ae  jmp     short loc_180077114
0x1800770b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800770b7  lea     rdx, WPP_GLOBAL_Control
0x1800770be  mov     rdi, [rbp+arg_10]
0x1800770c2  cmp     rcx, rdx
0x1800770c5  jz      short loc_1800770E5
0x1800770c7  test    byte ptr [rcx+1Ch], 10h
0x1800770cb  jz      short loc_1800770E5
0x1800770cd  mov     rcx, [rcx+10h]
0x1800770d1  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x1800770d8  mov     edx, 3Eh ; '>'
0x1800770dd  mov     r9, rdi
0x1800770e0  call    WPP_SF_S
0x1800770e5  mov     byte ptr [rsi], 1
0x1800770e8  test    rdi, rdi
0x1800770eb  jz      short loc_1800770F5
0x1800770ed  mov     rcx, rdi; void *
0x1800770f0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800770f5  test    rbx, rbx
0x1800770f8  jz      short loc_180077103
0x1800770fa  mov     rcx, rbx; hKey
0x1800770fd  call    cs:__imp_RegCloseKey
0x180077103  mov     rcx, [rbp+phkResult]; hKey
0x180077107  test    rcx, rcx
0x18007710a  jz      short loc_180077112
0x18007710c  call    cs:__imp_RegCloseKey
0x180077112  xor     ebx, ebx
0x180077114  lea     rcx, [rbp+arg_18]
0x180077118  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18007711d  mov     eax, ebx
0x18007711f  add     rsp, 38h
0x180077123  pop     rdi
0x180077124  pop     rsi
0x180077125  pop     rbx
0x180077126  pop     rbp
0x180077127  retn
```
