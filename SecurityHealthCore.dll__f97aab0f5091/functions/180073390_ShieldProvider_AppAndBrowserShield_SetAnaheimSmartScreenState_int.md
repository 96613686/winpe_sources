# ShieldProvider::AppAndBrowserShield::SetAnaheimSmartScreenState(int)

- ea: `0x180073390`
- end: `0x180073624`
- name: `?SetAnaheimSmartScreenState@AppAndBrowserShield@ShieldProvider@@UEAAJH@Z`
- size: `660`
- prototype: `__int64 __fastcall(ShieldProvider::AppAndBrowserShield *__hidden this, int)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180073630`
- `0x180073640`
- `0x180073650`
- `0x180073660`

## callees

- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x180073390`
- `0x1800d0180`
- `0x1800d0c14`
- `0x1800dd3e8`
- `0x1800de1bc`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007346c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800734e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007355e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007356e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800735ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800735fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007346c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800734e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007355e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007356e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800735ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800735fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180073412`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180073412`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ShieldProvider::AppAndBrowserShield::SetAnaheimSmartScreenState(
        ShieldProvider::AppAndBrowserShield *this,
        int a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  int Key; // eax
  HKEY v8; // rbx
  int v9; // eax
  unsigned int v10; // edi
  int v11; // eax
  struct _SECURITY_ATTRIBUTES *v13; // [rsp+28h] [rbp-28h]
  HKEY phkResult; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v16[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v17; // [rsp+80h] [rbp+30h] BYREF
  int v18; // [rsp+88h] [rbp+38h] BYREF

  v16[0] = 0;
  v4 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(v16);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        166,
        WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
        (unsigned int)v4);
    goto LABEL_40;
  }
  phkResult = 0;
  v6 = RegOpenCurrentUser(0x20006u, &phkResult);
  v5 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids, v5);
LABEL_12:
      if ( phkResult )
        RegCloseKey(phkResult);
      goto LABEL_40;
    }
  }
  hKey = 0;
  Key = CommonUtil::UtilRegCreateKey(
          (CommonUtil *)&hKey,
          (HKEY *)phkResult,
          (const WCHAR *)&stru_1800FD210,
          (const unsigned __int16 *)0x20006,
          0,
          v13);
  v5 = Key;
  if ( Key < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        168,
        WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
        (unsigned int)Key);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_12;
  }
  LODWORD(v17) = a2 != 0;
  v8 = hKey;
  v9 = CommonUtil::UtilRegSetValueInternal(
         (CommonUtil *)hKey,
         &word_1800F4E78,
         (const unsigned __int16 *)4,
         4,
         (BYTE *)&v17);
  v10 = v9;
  if ( v9 >= 0 )
  {
    if ( a2 )
    {
      if ( (unsigned __int8)ShieldProvider::IsWarningStateDismissed(48) )
      {
        v11 = ShieldProvider::SetOrRemoveWarningStateDismissal(0x30u, 1);
        if ( v11 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            170,
            WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
            (unsigned int)v11);
      }
    }
    v18 = 0;
    (*(void (__fastcall **)(ShieldProvider::AppAndBrowserShield *, int *))(*(_QWORD *)this + 88LL))(this, &v18);
    if ( v8 )
      RegCloseKey(v8);
    if ( phkResult )
      RegCloseKey(phkResult);
    v5 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        169,
        WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
        (unsigned int)v9);
    if ( v8 )
      RegCloseKey(v8);
    if ( phkResult )
      RegCloseKey(phkResult);
    v5 = v10;
  }
LABEL_40:
  CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(v16);
  return v5;
}

```

## disassembly

```asm
0x180073390  mov     [rsp-18h+arg_0], rbx
0x180073395  mov     [rsp-18h+arg_8], rsi
0x18007339a  push    rbp
0x18007339b  push    rdi
0x18007339c  push    r14
0x18007339e  mov     rbp, rsp
0x1800733a1  sub     rsp, 50h
0x1800733a5  mov     esi, edx
0x1800733a7  mov     r14, rcx
0x1800733aa  mov     [rbp+var_10], 0
0x1800733b2  lea     rcx, [rbp+var_10]
0x1800733b6  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x1800733bb  mov     ebx, eax
0x1800733bd  test    eax, eax
0x1800733bf  jns     short loc_1800733FF
0x1800733c1  lea     rdx, WPP_GLOBAL_Control
0x1800733c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800733cf  cmp     rcx, rdx
0x1800733d2  jz      loc_180073606
0x1800733d8  test    byte ptr [rcx+1Ch], 1
0x1800733dc  jz      loc_180073606
0x1800733e2  mov     edx, 0A6h
0x1800733e7  mov     r9d, eax
0x1800733ea  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x1800733f1  mov     rcx, [rcx+10h]
0x1800733f5  call    WPP_SF_d
0x1800733fa  jmp     loc_180073606
0x1800733ff  mov     [rbp+phkResult], 0
0x180073407  lea     rdx, [rbp+phkResult]; phkResult
0x18007340b  mov     edi, 20006h
0x180073410  mov     ecx, edi; samDesired
0x180073412  call    cs:__imp_RegOpenCurrentUser
0x180073418  mov     ebx, eax
0x18007341a  test    eax, eax
0x18007341c  jz      short loc_180073477
0x18007341e  jle     short loc_180073429
0x180073420  movzx   ebx, ax
0x180073423  or      ebx, 80070000h
0x180073429  test    ebx, ebx
0x18007342b  jns     short loc_180073477
0x18007342d  lea     rdx, WPP_GLOBAL_Control
0x180073434  mov     rcx, cs:WPP_GLOBAL_Control
0x18007343b  cmp     rcx, rdx
0x18007343e  jz      short loc_18007345F
0x180073440  test    byte ptr [rcx+1Ch], 1
0x180073444  jz      short loc_18007345F
0x180073446  mov     edx, 0A7h
0x18007344b  mov     r9d, ebx
0x18007344e  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x180073455  mov     rcx, [rcx+10h]
0x180073459  call    WPP_SF_d
0x18007345e  nop
0x18007345f  mov     rcx, [rbp+phkResult]; hKey
0x180073463  test    rcx, rcx
0x180073466  jz      loc_180073606
0x18007346c  call    cs:__imp_RegCloseKey
0x180073472  jmp     loc_180073606
0x180073477  mov     [rbp+hKey], 0
0x18007347f  mov     qword ptr [rsp+50h+var_30], 0; unsigned int
0x180073488  mov     r9d, edi; unsigned __int16 *
0x18007348b  lea     r8, stru_1800FD210; HKEY
0x180073492  mov     rdx, [rbp+phkResult]; HKEY *
0x180073496  lea     rcx, [rbp+hKey]; this
0x18007349a  call    ?UtilRegCreateKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGKPEAU_SECURITY_ATTRIBUTES@@K@Z; CommonUtil::UtilRegCreateKey(HKEY__ * *,HKEY__ *,ushort const *,ulong,_SECURITY_ATTRIBUTES *,ulong)
0x18007349f  mov     ebx, eax
0x1800734a1  test    eax, eax
0x1800734a3  jns     short loc_1800734EF
0x1800734a5  lea     rdx, WPP_GLOBAL_Control
0x1800734ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800734b3  cmp     rcx, rdx
0x1800734b6  jz      short loc_1800734D7
0x1800734b8  test    byte ptr [rcx+1Ch], 1
0x1800734bc  jz      short loc_1800734D7
0x1800734be  mov     edx, 0A8h
0x1800734c3  mov     r9d, eax
0x1800734c6  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x1800734cd  mov     rcx, [rcx+10h]
0x1800734d1  call    WPP_SF_d
0x1800734d6  nop
0x1800734d7  mov     rcx, [rbp+hKey]; hKey
0x1800734db  test    rcx, rcx
0x1800734de  jz      loc_18007345F
0x1800734e4  call    cs:__imp_RegCloseKey
0x1800734ea  jmp     loc_18007345F
0x1800734ef  xor     eax, eax
0x1800734f1  test    esi, esi
0x1800734f3  setnz   al
0x1800734f6  mov     dword ptr [rbp+arg_10], eax
0x1800734f9  lea     rax, [rbp+arg_10]
0x1800734fd  mov     qword ptr [rsp+50h+var_30], rax; unsigned __int64
0x180073502  mov     r8d, 4; unsigned __int16 *
0x180073508  mov     r9d, r8d; unsigned int
0x18007350b  lea     rdx, word_1800F4E78; HKEY
0x180073512  mov     rbx, [rbp+hKey]
0x180073516  mov     rcx, rbx; this
0x180073519  call    ?UtilRegSetValueInternal@CommonUtil@@YAJPEAUHKEY__@@PEBGK_KPEBX@Z; CommonUtil::UtilRegSetValueInternal(HKEY__ *,ushort const *,ulong,unsigned __int64,void const *)
0x18007351e  mov     edi, eax
0x180073520  test    eax, eax
0x180073522  jns     short loc_18007357B
0x180073524  lea     rdx, WPP_GLOBAL_Control
0x18007352b  mov     rcx, cs:WPP_GLOBAL_Control
0x180073532  cmp     rcx, rdx
0x180073535  jz      short loc_180073556
0x180073537  test    byte ptr [rcx+1Ch], 1
0x18007353b  jz      short loc_180073556
0x18007353d  mov     edx, 0A9h
0x180073542  mov     r9d, eax
0x180073545  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18007354c  mov     rcx, [rcx+10h]
0x180073550  call    WPP_SF_d
0x180073555  nop
0x180073556  test    rbx, rbx
0x180073559  jz      short loc_180073565
0x18007355b  mov     rcx, rbx; hKey
0x18007355e  call    cs:__imp_RegCloseKey
0x180073564  nop
0x180073565  mov     rcx, [rbp+phkResult]; hKey
0x180073569  test    rcx, rcx
0x18007356c  jz      short loc_180073574
0x18007356e  call    cs:__imp_RegCloseKey
0x180073574  mov     ebx, edi
0x180073576  jmp     loc_180073606
0x18007357b  test    esi, esi
0x18007357d  jz      short loc_1800735CB
0x18007357f  mov     edi, 30h ; '0'
0x180073584  mov     ecx, edi
0x180073586  call    ?IsWarningStateDismissed@ShieldProvider@@YA_NW4PillarStatusFlag@@@Z; ShieldProvider::IsWarningStateDismissed(PillarStatusFlag)
0x18007358b  test    al, al
0x18007358d  jz      short loc_1800735CB
0x18007358f  mov     dl, 1
0x180073591  mov     ecx, edi
0x180073593  call    ShieldProvider__SetOrRemoveWarningStateDismissal
0x180073598  test    eax, eax
0x18007359a  jns     short loc_1800735CB
0x18007359c  lea     rdx, WPP_GLOBAL_Control
0x1800735a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800735aa  cmp     rcx, rdx
0x1800735ad  jz      short loc_1800735CB
0x1800735af  test    byte ptr [rcx+1Ch], 1
0x1800735b3  jz      short loc_1800735CB
0x1800735b5  lea     edx, [rdi+7Ah]
0x1800735b8  mov     r9d, eax
0x1800735bb  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x1800735c2  mov     rcx, [rcx+10h]
0x1800735c6  call    WPP_SF_d
0x1800735cb  mov     [rbp+arg_18], 0
0x1800735d2  mov     rax, [r14]
0x1800735d5  lea     rdx, [rbp+arg_18]
0x1800735d9  mov     rcx, r14
0x1800735dc  mov     rax, [rax+58h]
0x1800735e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800735e5  nop
0x1800735e6  test    rbx, rbx
0x1800735e9  jz      short loc_1800735F5
0x1800735eb  mov     rcx, rbx; hKey
0x1800735ee  call    cs:__imp_RegCloseKey
0x1800735f4  nop
0x1800735f5  mov     rcx, [rbp+phkResult]; hKey
0x1800735f9  test    rcx, rcx
0x1800735fc  jz      short loc_180073604
0x1800735fe  call    cs:__imp_RegCloseKey
0x180073604  xor     ebx, ebx
0x180073606  lea     rcx, [rbp+var_10]
0x18007360a  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18007360f  mov     eax, ebx
0x180073611  mov     rbx, [rsp+50h+arg_0]
0x180073616  mov     rsi, [rsp+50h+arg_8]
0x18007361b  add     rsp, 50h
0x18007361f  pop     r14
0x180073621  pop     rdi
0x180073622  pop     rbp
0x180073623  retn
```
