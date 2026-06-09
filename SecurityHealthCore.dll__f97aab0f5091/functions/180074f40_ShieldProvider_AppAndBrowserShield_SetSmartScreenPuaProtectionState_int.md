# ShieldProvider::AppAndBrowserShield::SetSmartScreenPuaProtectionState(int)

- ea: `0x180074f40`
- end: `0x18007520c`
- name: `?SetSmartScreenPuaProtectionState@AppAndBrowserShield@ShieldProvider@@UEAAJH@Z`
- size: `716`
- prototype: `__int64 __fastcall(ShieldProvider::AppAndBrowserShield *__hidden this, int)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180075220`
- `0x180075230`
- `0x180075240`
- `0x180075250`

## callees

- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x18003499c`
- `0x18006df60`
- `0x180074f40`
- `0x1800d0180`
- `0x1800d0c14`
- `0x1800dd3e8`
- `0x1800de1bc`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007501c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075094`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007510e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007511e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800751d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800751e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007501c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180075094`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007510e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007511e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800751d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800751e6`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180074fc2`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180074fc2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ShieldProvider::AppAndBrowserShield::SetSmartScreenPuaProtectionState(
        ShieldProvider::AppAndBrowserShield *this,
        int a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  int Key; // eax
  HKEY v8; // rbx
  ShieldProvider *v9; // rcx
  int v10; // edi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  struct _SECURITY_ATTRIBUTES *v15; // [rsp+28h] [rbp-28h]
  HKEY phkResult; // [rsp+30h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v18[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v19; // [rsp+80h] [rbp+30h] BYREF
  int v20; // [rsp+88h] [rbp+38h] BYREF

  v18[0] = 0;
  v4 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(v18);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        106,
        WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
        (unsigned int)v4);
    goto LABEL_46;
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids, v5);
LABEL_12:
      if ( phkResult )
        RegCloseKey(phkResult);
      goto LABEL_46;
    }
  }
  hKey = 0;
  Key = CommonUtil::UtilRegCreateKey(
          (CommonUtil *)&hKey,
          (HKEY *)phkResult,
          (const WCHAR *)&stru_1800FCEA0,
          (const unsigned __int16 *)0x20006,
          0,
          v15);
  v5 = Key;
  if ( Key < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        108,
        WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
        (unsigned int)Key);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_12;
  }
  LODWORD(v19) = a2 != 0;
  v8 = hKey;
  v10 = CommonUtil::UtilRegSetValueInternal(
          (CommonUtil *)hKey,
          &word_1800F4E78,
          (const unsigned __int16 *)4,
          4,
          (BYTE *)&v19);
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_25;
    v12 = 109;
LABEL_24:
    WPP_SF_d(v11[2], v12, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids, (unsigned int)v10);
LABEL_25:
    if ( v8 )
      RegCloseKey(v8);
    if ( phkResult )
      RegCloseKey(phkResult);
    v5 = v10;
    goto LABEL_46;
  }
  if ( a2 )
  {
    if ( ShieldProvider::IsWithinSetupGracePeriod(v9) )
    {
      v10 = ShieldProvider::AppAndBrowserShield::ChangePuaGracePeriod();
      if ( v10 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_25;
        v12 = 110;
        goto LABEL_24;
      }
    }
    if ( (unsigned __int8)ShieldProvider::IsWarningStateDismissed(47) )
    {
      v13 = ShieldProvider::SetOrRemoveWarningStateDismissal(0x2Fu, 1);
      if ( v13 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          111,
          WPP_b76957825b443fb7aa70a51c66c39000_Traceguids,
          (unsigned int)v13);
    }
  }
  v20 = 0;
  (*(void (__fastcall **)(ShieldProvider::AppAndBrowserShield *, int *))(*(_QWORD *)this + 88LL))(this, &v20);
  if ( v8 )
    RegCloseKey(v8);
  if ( phkResult )
    RegCloseKey(phkResult);
  v5 = 0;
LABEL_46:
  CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(v18);
  return v5;
}

```

## disassembly

```asm
0x180074f40  mov     [rsp-18h+arg_0], rbx
0x180074f45  mov     [rsp-18h+arg_8], rsi
0x180074f4a  push    rbp
0x180074f4b  push    rdi
0x180074f4c  push    r14
0x180074f4e  mov     rbp, rsp
0x180074f51  sub     rsp, 50h
0x180074f55  mov     esi, edx
0x180074f57  mov     r14, rcx
0x180074f5a  mov     [rbp+var_10], 0
0x180074f62  lea     rcx, [rbp+var_10]
0x180074f66  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x180074f6b  mov     ebx, eax
0x180074f6d  test    eax, eax
0x180074f6f  jns     short loc_180074FAF
0x180074f71  lea     rdx, WPP_GLOBAL_Control
0x180074f78  mov     rcx, cs:WPP_GLOBAL_Control
0x180074f7f  cmp     rcx, rdx
0x180074f82  jz      loc_1800751EE
0x180074f88  test    byte ptr [rcx+1Ch], 1
0x180074f8c  jz      loc_1800751EE
0x180074f92  mov     edx, 6Ah ; 'j'
0x180074f97  mov     r9d, eax
0x180074f9a  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x180074fa1  mov     rcx, [rcx+10h]
0x180074fa5  call    WPP_SF_d
0x180074faa  jmp     loc_1800751EE
0x180074faf  mov     [rbp+phkResult], 0
0x180074fb7  lea     rdx, [rbp+phkResult]; phkResult
0x180074fbb  mov     edi, 20006h
0x180074fc0  mov     ecx, edi; samDesired
0x180074fc2  call    cs:__imp_RegOpenCurrentUser
0x180074fc8  mov     ebx, eax
0x180074fca  test    eax, eax
0x180074fcc  jz      short loc_180075027
0x180074fce  jle     short loc_180074FD9
0x180074fd0  movzx   ebx, ax
0x180074fd3  or      ebx, 80070000h
0x180074fd9  test    ebx, ebx
0x180074fdb  jns     short loc_180075027
0x180074fdd  lea     rdx, WPP_GLOBAL_Control
0x180074fe4  mov     rcx, cs:WPP_GLOBAL_Control
0x180074feb  cmp     rcx, rdx
0x180074fee  jz      short loc_18007500F
0x180074ff0  test    byte ptr [rcx+1Ch], 1
0x180074ff4  jz      short loc_18007500F
0x180074ff6  mov     edx, 6Bh ; 'k'
0x180074ffb  mov     r9d, ebx
0x180074ffe  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x180075005  mov     rcx, [rcx+10h]
0x180075009  call    WPP_SF_d
0x18007500e  nop
0x18007500f  mov     rcx, [rbp+phkResult]; hKey
0x180075013  test    rcx, rcx
0x180075016  jz      loc_1800751EE
0x18007501c  call    cs:__imp_RegCloseKey
0x180075022  jmp     loc_1800751EE
0x180075027  mov     [rbp+hKey], 0
0x18007502f  mov     qword ptr [rsp+50h+var_30], 0; unsigned int
0x180075038  mov     r9d, edi; unsigned __int16 *
0x18007503b  lea     r8, stru_1800FCEA0; HKEY
0x180075042  mov     rdx, [rbp+phkResult]; HKEY *
0x180075046  lea     rcx, [rbp+hKey]; this
0x18007504a  call    ?UtilRegCreateKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGKPEAU_SECURITY_ATTRIBUTES@@K@Z; CommonUtil::UtilRegCreateKey(HKEY__ * *,HKEY__ *,ushort const *,ulong,_SECURITY_ATTRIBUTES *,ulong)
0x18007504f  mov     ebx, eax
0x180075051  test    eax, eax
0x180075053  jns     short loc_18007509F
0x180075055  lea     rdx, WPP_GLOBAL_Control
0x18007505c  mov     rcx, cs:WPP_GLOBAL_Control
0x180075063  cmp     rcx, rdx
0x180075066  jz      short loc_180075087
0x180075068  test    byte ptr [rcx+1Ch], 1
0x18007506c  jz      short loc_180075087
0x18007506e  mov     edx, 6Ch ; 'l'
0x180075073  mov     r9d, eax
0x180075076  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x18007507d  mov     rcx, [rcx+10h]
0x180075081  call    WPP_SF_d
0x180075086  nop
0x180075087  mov     rcx, [rbp+hKey]; hKey
0x18007508b  test    rcx, rcx
0x18007508e  jz      loc_18007500F
0x180075094  call    cs:__imp_RegCloseKey
0x18007509a  jmp     loc_18007500F
0x18007509f  xor     eax, eax
0x1800750a1  test    esi, esi
0x1800750a3  setnz   al
0x1800750a6  mov     dword ptr [rbp+arg_10], eax
0x1800750a9  lea     rax, [rbp+arg_10]
0x1800750ad  mov     qword ptr [rsp+50h+var_30], rax; unsigned __int64
0x1800750b2  mov     r8d, 4; unsigned __int16 *
0x1800750b8  mov     r9d, r8d; unsigned int
0x1800750bb  lea     rdx, word_1800F4E78; HKEY
0x1800750c2  mov     rbx, [rbp+hKey]
0x1800750c6  mov     rcx, rbx; this
0x1800750c9  call    ?UtilRegSetValueInternal@CommonUtil@@YAJPEAUHKEY__@@PEBGK_KPEBX@Z; CommonUtil::UtilRegSetValueInternal(HKEY__ *,ushort const *,ulong,unsigned __int64,void const *)
0x1800750ce  mov     edi, eax
0x1800750d0  test    eax, eax
0x1800750d2  jns     short loc_18007512B
0x1800750d4  lea     rdx, WPP_GLOBAL_Control
0x1800750db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800750e2  cmp     rcx, rdx
0x1800750e5  jz      short loc_180075106
0x1800750e7  test    byte ptr [rcx+1Ch], 1
0x1800750eb  jz      short loc_180075106
0x1800750ed  mov     edx, 6Dh ; 'm'
0x1800750f2  mov     r9d, edi
0x1800750f5  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x1800750fc  mov     rcx, [rcx+10h]
0x180075100  call    WPP_SF_d
0x180075105  nop
0x180075106  test    rbx, rbx
0x180075109  jz      short loc_180075115
0x18007510b  mov     rcx, rbx; hKey
0x18007510e  call    cs:__imp_RegCloseKey
0x180075114  nop
0x180075115  mov     rcx, [rbp+phkResult]; hKey
0x180075119  test    rcx, rcx
0x18007511c  jz      short loc_180075124
0x18007511e  call    cs:__imp_RegCloseKey
0x180075124  mov     ebx, edi
0x180075126  jmp     loc_1800751EE
0x18007512b  test    esi, esi
0x18007512d  jz      loc_1800751B3
0x180075133  call    ?IsWithinSetupGracePeriod@ShieldProvider@@YA_NXZ; ShieldProvider::IsWithinSetupGracePeriod(void)
0x180075138  test    al, al
0x18007513a  jz      short loc_180075167
0x18007513c  call    ?ChangePuaGracePeriod@AppAndBrowserShield@ShieldProvider@@AEAAJW4PillarStatusFlag@@_N@Z; ShieldProvider::AppAndBrowserShield::ChangePuaGracePeriod(PillarStatusFlag,bool)
0x180075141  mov     edi, eax
0x180075143  test    eax, eax
0x180075145  jns     short loc_180075167
0x180075147  lea     rdx, WPP_GLOBAL_Control
0x18007514e  mov     rcx, cs:WPP_GLOBAL_Control
0x180075155  cmp     rcx, rdx
0x180075158  jz      short loc_180075106
0x18007515a  test    byte ptr [rcx+1Ch], 1
0x18007515e  jz      short loc_180075106
0x180075160  mov     edx, 6Eh ; 'n'
0x180075165  jmp     short loc_1800750F2
0x180075167  mov     edi, 2Fh ; '/'
0x18007516c  mov     ecx, edi
0x18007516e  call    ?IsWarningStateDismissed@ShieldProvider@@YA_NW4PillarStatusFlag@@@Z; ShieldProvider::IsWarningStateDismissed(PillarStatusFlag)
0x180075173  test    al, al
0x180075175  jz      short loc_1800751B3
0x180075177  mov     dl, 1
0x180075179  mov     ecx, edi
0x18007517b  call    ShieldProvider__SetOrRemoveWarningStateDismissal
0x180075180  test    eax, eax
0x180075182  jns     short loc_1800751B3
0x180075184  lea     rdx, WPP_GLOBAL_Control
0x18007518b  mov     rcx, cs:WPP_GLOBAL_Control
0x180075192  cmp     rcx, rdx
0x180075195  jz      short loc_1800751B3
0x180075197  test    byte ptr [rcx+1Ch], 1
0x18007519b  jz      short loc_1800751B3
0x18007519d  lea     edx, [rdi+40h]
0x1800751a0  mov     r9d, eax
0x1800751a3  lea     r8, WPP_b76957825b443fb7aa70a51c66c39000_Traceguids
0x1800751aa  mov     rcx, [rcx+10h]
0x1800751ae  call    WPP_SF_d
0x1800751b3  mov     [rbp+arg_18], 0
0x1800751ba  mov     rax, [r14]
0x1800751bd  lea     rdx, [rbp+arg_18]
0x1800751c1  mov     rcx, r14
0x1800751c4  mov     rax, [rax+58h]
0x1800751c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800751cd  nop
0x1800751ce  test    rbx, rbx
0x1800751d1  jz      short loc_1800751DD
0x1800751d3  mov     rcx, rbx; hKey
0x1800751d6  call    cs:__imp_RegCloseKey
0x1800751dc  nop
0x1800751dd  mov     rcx, [rbp+phkResult]; hKey
0x1800751e1  test    rcx, rcx
0x1800751e4  jz      short loc_1800751EC
0x1800751e6  call    cs:__imp_RegCloseKey
0x1800751ec  xor     ebx, ebx
0x1800751ee  lea     rcx, [rbp+var_10]
0x1800751f2  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x1800751f7  mov     eax, ebx
0x1800751f9  mov     rbx, [rsp+50h+arg_0]
0x1800751fe  mov     rsi, [rsp+50h+arg_8]
0x180075203  add     rsp, 50h
0x180075207  pop     r14
0x180075209  pop     rdi
0x18007520a  pop     rbp
0x18007520b  retn
```
