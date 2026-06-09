# GetCleanupJobsFromRegistry(UnBCL::String *)

- ea: `0x18000940c`
- end: `0x18000974e`
- name: `?GetCleanupJobsFromRegistry@@YAPEAV?$ArrayList@PEAVISetupCleanupJob@@@UnBCL@@PEAVString@2@@Z`
- size: `834`
- prototype: `__int64 __fastcall(const struct UnBCL::String *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180006838`

## callees

- `0x1800043e0`
- `0x18000464c`
- `0x1800046a8`
- `0x1800047a8`
- `0x180004bc4`
- `0x180005e98`
- `0x18000638c`
- `0x1800066dc`
- `0x180006744`
- `0x18000940c`
- `0x18000f3bc`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000965e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800095a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000965e`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x180009580`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x1800096f1`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x180009580`
- `unbcl!?DecRef@Object@UnBCL@@QEAAHXZ` at `0x1800096f1`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1800094b9`
- `unbcl!??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ` at `0x1800094b9`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180009656`
- `unbcl!??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180009656`
- `unbcl!?GetSubKeyNames@RegistryKey@UnBCL@@QEAAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x1800094a1`
- `unbcl!?GetSubKeyNames@RegistryKey@UnBCL@@QEAAPEAV?$Array@PEAVString@UnBCL@@@2@XZ` at `0x1800094a1`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x1800094ae`
- `unbcl!??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z` at `0x1800094ae`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x180009474`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z` at `0x180009474`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800095b7`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800095b7`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180009432`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x180009432`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@@Z` at `0x180009524`
- `unbcl!?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@@Z` at `0x180009524`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x180009457`
- `unbcl!?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ` at `0x180009457`
- `WDSCORE!CurrentIP` at `0x1800095aa`
- `WDSCORE!CurrentIP` at `0x180009666`
- `WDSCORE!CurrentIP` at `0x1800095aa`
- `WDSCORE!CurrentIP` at `0x180009666`
- `WDSCORE!WdsSetupLogMessageW` at `0x180009613`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800096d0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180009613`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800096d0`

## string_xrefs

- `0x1800095f0`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x1800096ad`: `base\ntsetup\setup\tools\setupcleanuptask\lib\src\setupcleanuptaskimpl.cpp`
- `0x18000966f`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Setup\CleanupTask`
- `0x1800094ea`: `GetCleanupJobsFromRegistry`
- `0x1800096a1`: `GetCleanupJobsFromRegistry`
- `0x180009676`: `The registry key HKLM\%s doesn't exist. No cleanup jobs were defined?`

## pseudocode

```c
__int64 __fastcall GetCleanupJobsFromRegistry(const struct UnBCL::String *a1)
{
  void *v2; // rax
  __int64 LocalMachine; // rax
  struct UnBCL::RegistryKey *v4; // rax
  __int64 v5; // rsi
  __int64 SubKeyNames; // rax
  __int64 v7; // rax
  __int64 (__fastcall ***v8)(_QWORD); // rcx
  __int64 v9; // rax
  __int64 v10; // r14
  struct UnBCL::RegistryKey *v11; // rax
  struct ISetupCleanupJob *v12; // rax
  UnBCL::Object *v13; // r15
  __int64 v14; // rdi
  void (__fastcall *v15)(__int64, UnBCL::Object *); // rbx
  DWORD LastError; // edi
  __int64 v17; // rbx
  const char *CString; // rax
  struct tagLOG_PARTIAL_MSG *v19; // rax
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  void **v24; // [rsp+60h] [rbp-39h] BYREF
  UnBCL::Object *v25; // [rsp+68h] [rbp-31h]
  void **v26; // [rsp+70h] [rbp-29h] BYREF
  UnBCL::RegistryKey *v27; // [rsp+78h] [rbp-21h]
  void **v28; // [rsp+80h] [rbp-19h] BYREF
  __int64 v29; // [rsp+88h] [rbp-11h]
  _QWORD v30[2]; // [rsp+90h] [rbp-9h] BYREF
  _QWORD v31[2]; // [rsp+A0h] [rbp+7h] BYREF
  _QWORD v32[2]; // [rsp+B0h] [rbp+17h] BYREF
  _BYTE v33[16]; // [rsp+C0h] [rbp+27h] BYREF
  const struct UnBCL::String *v34; // [rsp+108h] [rbp+6Fh]

  v2 = UnBCL::Object::operator new(0x80u);
  if ( v2 )
    v2 = (void *)UnBCL::ArrayList<ISetupCleanupJob *>::ArrayList<ISetupCleanupJob *>(v2);
  UnBCL::SmartPtr<UnBCL::ArrayList<ISetupCleanupJob *>>::SmartPtr<UnBCL::ArrayList<ISetupCleanupJob *>>(&v28, v2);
  LocalMachine = UnBCL::Registry::GetLocalMachine();
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(v32, LocalMachine);
  v4 = UnBCL::RegistryKey::OpenSubKey((UnBCL::RegistryKey *)v32[1], a1, 0);
  UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(&v26, v4);
  v5 = v29;
  if ( v27 )
  {
    SubKeyNames = UnBCL::RegistryKey::GetSubKeyNames(v27);
    UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(v33, SubKeyNames);
    v7 = UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(v33);
    v8 = (__int64 (__fastcall ***)(_QWORD))(*(int *)(*(_QWORD *)(v7 + 8) + 8LL) + v7 + 8);
    v9 = (**v8)(v8);
    UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>(v31, v9);
    v10 = v31[1];
    while ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10) )
    {
      v34 = (const struct UnBCL::String *)(**(__int64 (__fastcall ***)(__int64))v10)(v10);
      v11 = UnBCL::RegistryKey::OpenSubKey(v27, v34);
      UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(v30, v11);
      v12 = CSetupCleanupJobFactory::CreateFromRegistryKey(v34, (struct UnBCL::RegistryKey *)v30[1]);
      v24 = &UnBCL::SmartPtr<ISetupCleanupJob>::`vftable';
      v25 = 0;
      UnBCL::SmartPtr<UnBCL::XmlNodeList>::Assign(&v24, v12);
      v13 = v25;
      if ( v25 )
      {
        v14 = *(int *)(*(_QWORD *)(v5 + 8) + 16LL);
        v15 = *(void (__fastcall **)(__int64, UnBCL::Object *))(*(_QWORD *)(v14 + v5 + 8) + 40LL);
        UnBCL::Object::DecRef(v25);
        v25 = 0;
        v15(v14 + v5 + 8, v13);
      }
      else
      {
        LastError = GetLastError();
        v17 = CurrentIP();
        CString = (const char *)UnBCL::String::get_CString(v34);
        v19 = ConstructPartialMsgW(0x2000000u, "Malformed cleanup job: %s. Ignore", CString);
        WdsSetupLogMessageW(
          v19,
          0,
          L"D",
          0,
          573,
          L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
          L"GetCleanupJobsFromRegistry",
          v17,
          LastError,
          0,
          0);
      }
      UnBCL::SmartPtr<ISetupCleanupJob>::~SmartPtr<ISetupCleanupJob>(&v24);
      v30[0] = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
      UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(v30);
    }
    v31[0] = &UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::`vftable';
    UnBCL::SmartPtr<UnBCL::IEnumerator<ISetupCleanupJob *>>::DeAssign(v31);
    UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(v33);
  }
  else
  {
    v20 = GetLastError();
    v21 = CurrentIP();
    v22 = ConstructPartialMsgW(
            0x3000000u,
            "The registry key HKLM\\%s doesn't exist. No cleanup jobs were defined?",
            (const char *)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\CleanupTask");
    WdsSetupLogMessageW(
      v22,
      0,
      L"D",
      0,
      579,
      L"base\\ntsetup\\setup\\tools\\setupcleanuptask\\lib\\src\\setupcleanuptaskimpl.cpp",
      L"GetCleanupJobsFromRegistry",
      v21,
      v20,
      0,
      0);
  }
  if ( v5 )
  {
    UnBCL::Object::DecRef((UnBCL::Object *)(v5 + *(int *)(*(_QWORD *)(v5 + 8) + 4LL) + 8LL));
    v29 = 0;
  }
  v26 = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(&v26);
  v32[0] = &UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable';
  UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(v32);
  v28 = &UnBCL::SmartPtr<UnBCL::ArrayList<ISetupCleanupJob *>>::`vftable';
  UnBCL::SmartPtr<UnBCL::IEnumerator<ISetupCleanupJob *>>::DeAssign(&v28);
  return v5;
}

```

## disassembly

```asm
0x18000940c  mov     [rsp-8+arg_0], rbx
0x180009411  mov     [rsp-8+arg_10], rsi
0x180009416  push    rbp
0x180009417  push    rdi
0x180009418  push    r13
0x18000941a  push    r14
0x18000941c  push    r15
0x18000941e  lea     rbp, [rsp-37h]
0x180009423  sub     rsp, 0D0h
0x18000942a  mov     rbx, rcx
0x18000942d  mov     ecx, 80h
0x180009432  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x180009438  mov     [rbp+57h+arg_8], rax
0x18000943c  test    rax, rax
0x18000943f  jz      short loc_18000944A
0x180009441  mov     rcx, rax
0x180009444  call    ??0?$ArrayList@PEAVISetupCleanupJob@@@UnBCL@@QEAA@XZ; UnBCL::ArrayList<ISetupCleanupJob *>::ArrayList<ISetupCleanupJob *>(void)
0x180009449  nop
0x18000944a  mov     rdx, rax
0x18000944d  lea     rcx, [rbp+57h+var_70]
0x180009451  call    ??0?$SmartPtr@V?$ArrayList@PEAVISetupCleanupJob@@@UnBCL@@@UnBCL@@QEAA@PEAV?$ArrayList@PEAVISetupCleanupJob@@@1@@Z; UnBCL::SmartPtr<UnBCL::ArrayList<ISetupCleanupJob *>>::SmartPtr<UnBCL::ArrayList<ISetupCleanupJob *>>(UnBCL::ArrayList<ISetupCleanupJob *> *)
0x180009456  nop
0x180009457  call    cs:__imp_?GetLocalMachine@Registry@UnBCL@@SAPEAVRegistryKey@2@XZ; UnBCL::Registry::GetLocalMachine(void)
0x18000945d  mov     rdx, rax
0x180009460  lea     rcx, [rbp+57h+var_40]
0x180009464  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x180009469  nop
0x18000946a  xor     r8d, r8d
0x18000946d  mov     rdx, rbx
0x180009470  mov     rcx, [rbp+57h+var_38]
0x180009474  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@H@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *,int)
0x18000947a  mov     rdx, rax
0x18000947d  lea     rcx, [rbp+57h+var_80]
0x180009481  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x180009486  nop
0x180009487  lea     rbx, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18000948e  mov     rsi, [rbp+57h+var_68]
0x180009492  cmp     [rbp+57h+var_78], 0
0x180009497  jz      loc_18000965E
0x18000949d  mov     rcx, [rbp+57h+var_78]
0x1800094a1  call    cs:__imp_?GetSubKeyNames@RegistryKey@UnBCL@@QEAAPEAV?$Array@PEAVString@UnBCL@@@2@XZ; UnBCL::RegistryKey::GetSubKeyNames(void)
0x1800094a7  mov     rdx, rax
0x1800094aa  lea     rcx, [rbp+57h+var_30]
0x1800094ae  call    cs:__imp_??0?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAV?$Array@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::SmartPtr<UnBCL::Array<UnBCL::String *>>(UnBCL::Array<UnBCL::String *> *)
0x1800094b4  nop
0x1800094b5  lea     rcx, [rbp+57h+var_30]
0x1800094b9  call    cs:__imp_??C?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEBAPEAV?$Array@PEAVString@UnBCL@@@1@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::operator->(void)
0x1800094bf  mov     rcx, [rax+8]
0x1800094c3  movsxd  rdx, dword ptr [rcx+8]
0x1800094c7  lea     rcx, [rax+8]
0x1800094cb  add     rcx, rdx
0x1800094ce  mov     rax, [rcx]
0x1800094d1  mov     rax, [rax]
0x1800094d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094d9  mov     rdx, rax
0x1800094dc  lea     rcx, [rbp+57h+var_50]
0x1800094e0  call    ??0?$SmartPtr@U?$IEnumerator@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@QEAA@PEAU?$IEnumerator@PEAVString@UnBCL@@@1@@Z; UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>(UnBCL::IEnumerator<UnBCL::String *> *)
0x1800094e5  nop
0x1800094e6  mov     r14, [rbp+57h+var_48]
0x1800094ea  lea     r13, aGetcleanupjobs; "GetCleanupJobsFromRegistry"
0x1800094f1  mov     rax, [r14]
0x1800094f4  mov     rcx, r14
0x1800094f7  mov     rax, [rax+8]
0x1800094fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009500  test    eax, eax
0x180009502  jz      loc_18000963D
0x180009508  mov     rax, [r14]
0x18000950b  mov     rcx, r14
0x18000950e  mov     rax, [rax]
0x180009511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009516  mov     rbx, rax
0x180009519  mov     [rbp+57h+arg_8], rax
0x18000951d  mov     rdx, rax
0x180009520  mov     rcx, [rbp+57h+var_78]
0x180009524  call    cs:__imp_?OpenSubKey@RegistryKey@UnBCL@@QEAAPEAV12@PEBVString@2@@Z; UnBCL::RegistryKey::OpenSubKey(UnBCL::String const *)
0x18000952a  mov     rdx, rax
0x18000952d  lea     rcx, [rbp+57h+var_60]
0x180009531  call    ??0?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@QEAA@PEAVRegistryKey@1@@Z; UnBCL::SmartPtr<UnBCL::RegistryKey>::SmartPtr<UnBCL::RegistryKey>(UnBCL::RegistryKey *)
0x180009536  nop
0x180009537  mov     rdx, [rbp+57h+var_58]; struct UnBCL::RegistryKey *
0x18000953b  mov     rcx, rbx; struct UnBCL::String *
0x18000953e  call    ?CreateFromRegistryKey@CSetupCleanupJobFactory@@SAPEAVISetupCleanupJob@@PEAVString@UnBCL@@PEAVRegistryKey@4@@Z; CSetupCleanupJobFactory::CreateFromRegistryKey(UnBCL::String *,UnBCL::RegistryKey *)
0x180009543  lea     rcx, ??_7?$SmartPtr@VISetupCleanupJob@@@UnBCL@@6B@; const UnBCL::SmartPtr<ISetupCleanupJob>::`vftable'
0x18000954a  mov     [rbp+57h+var_90], rcx
0x18000954e  mov     [rbp+57h+var_88], 0
0x180009556  mov     rdx, rax
0x180009559  lea     rcx, [rbp+57h+var_90]
0x18000955d  call    ?Assign@?$SmartPtr@VXmlNodeList@UnBCL@@@UnBCL@@AEAAXPEAVXmlNodeList@2@@Z; UnBCL::SmartPtr<UnBCL::XmlNodeList>::Assign(UnBCL::XmlNodeList *)
0x180009562  nop
0x180009563  mov     r15, [rbp+57h+var_88]
0x180009567  test    r15, r15
0x18000956a  jz      short loc_1800095A2
0x18000956c  mov     rax, [rsi+8]
0x180009570  movsxd  rdi, dword ptr [rax+10h]
0x180009574  mov     rax, [rdi+rsi+8]
0x180009579  mov     rbx, [rax+28h]
0x18000957d  mov     rcx, r15
0x180009580  call    cs:__imp_?DecRef@Object@UnBCL@@QEAAHXZ; UnBCL::Object::DecRef(void)
0x180009586  mov     [rbp+57h+var_88], 0
0x18000958e  mov     rdx, r15
0x180009591  lea     rcx, [rsi+8]
0x180009595  add     rcx, rdi
0x180009598  mov     rax, rbx
0x18000959b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095a0  jmp     short loc_18000961A
0x1800095a2  call    cs:__imp_GetLastError
0x1800095a8  mov     edi, eax
0x1800095aa  call    cs:__imp_CurrentIP
0x1800095b0  mov     rbx, rax
0x1800095b3  mov     rcx, [rbp+57h+arg_8]
0x1800095b7  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800095bd  mov     r8, rax
0x1800095c0  lea     rdx, aMalformedClean; "Malformed cleanup job: %s. Ignore"
0x1800095c7  mov     ecx, 2000000h; unsigned int
0x1800095cc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800095d1  mov     [rsp+0F0h+var_A0], 0
0x1800095d9  mov     [rsp+0F0h+var_A8], 0
0x1800095e2  mov     [rsp+0F0h+var_B0], edi
0x1800095e6  mov     [rsp+0F0h+var_B8], rbx
0x1800095eb  mov     [rsp+0F0h+var_C0], r13
0x1800095f0  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x1800095f7  mov     [rsp+0F0h+var_C8], rcx
0x1800095fc  mov     [rsp+0F0h+var_D0], 23Dh
0x180009604  xor     r9d, r9d
0x180009607  lea     r8, aD_0; "D"
0x18000960e  xor     edx, edx
0x180009610  mov     rcx, rax
0x180009613  call    cs:__imp_WdsSetupLogMessageW
0x180009619  nop
0x18000961a  lea     rcx, [rbp+57h+var_90]
0x18000961e  call    ??1?$SmartPtr@VISetupCleanupJob@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<ISetupCleanupJob>::~SmartPtr<ISetupCleanupJob>(void)
0x180009623  nop
0x180009624  lea     rbx, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x18000962b  mov     [rbp+57h+var_60], rbx
0x18000962f  lea     rcx, [rbp+57h+var_60]
0x180009633  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x180009638  jmp     loc_1800094F1
0x18000963d  lea     rax, ??_7?$SmartPtr@U?$IEnumerator@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::IEnumerator<UnBCL::String *>>::`vftable'
0x180009644  mov     [rbp+57h+var_50], rax
0x180009648  lea     rcx, [rbp+57h+var_50]
0x18000964c  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVISetupCleanupJob@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ISetupCleanupJob *>>::DeAssign(void)
0x180009651  nop
0x180009652  lea     rcx, [rbp+57h+var_30]
0x180009656  call    cs:__imp_??1?$SmartPtr@V?$Array@PEAVString@UnBCL@@@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::Array<UnBCL::String *>>::~SmartPtr<UnBCL::Array<UnBCL::String *>>(void)
0x18000965c  jmp     short loc_1800096DD
0x18000965e  call    cs:__imp_GetLastError
0x180009664  mov     edi, eax
0x180009666  call    cs:__imp_CurrentIP
0x18000966c  mov     rbx, rax
0x18000966f  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180009676  lea     rdx, aTheRegistryKey; "The registry key HKLM\\%s doesn't exist"...
0x18000967d  mov     ecx, 3000000h; unsigned int
0x180009682  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180009687  mov     [rsp+0F0h+var_A0], 0
0x18000968f  mov     [rsp+0F0h+var_A8], 0
0x180009698  mov     [rsp+0F0h+var_B0], edi
0x18000969c  mov     [rsp+0F0h+var_B8], rbx
0x1800096a1  lea     r13, aGetcleanupjobs; "GetCleanupJobsFromRegistry"
0x1800096a8  mov     [rsp+0F0h+var_C0], r13
0x1800096ad  lea     rcx, aBaseNtsetupSet_4; "base\\ntsetup\\setup\\tools\\setupclean"...
0x1800096b4  mov     [rsp+0F0h+var_C8], rcx
0x1800096b9  mov     [rsp+0F0h+var_D0], 243h
0x1800096c1  xor     r9d, r9d
0x1800096c4  lea     r8, aD_0; "D"
0x1800096cb  xor     edx, edx
0x1800096cd  mov     rcx, rax
0x1800096d0  call    cs:__imp_WdsSetupLogMessageW
0x1800096d6  lea     rbx, ??_7?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::RegistryKey>::`vftable'
0x1800096dd  test    rsi, rsi
0x1800096e0  jz      short loc_1800096FF
0x1800096e2  mov     rax, [rsi+8]
0x1800096e6  movsxd  rcx, dword ptr [rax+4]
0x1800096ea  add     rcx, 8
0x1800096ee  add     rcx, rsi
0x1800096f1  call    cs:__imp_?DecRef@Object@UnBCL@@QEAAHXZ; UnBCL::Object::DecRef(void)
0x1800096f7  mov     [rbp+57h+var_68], 0
0x1800096ff  mov     [rbp+57h+var_80], rbx
0x180009703  lea     rcx, [rbp+57h+var_80]
0x180009707  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18000970c  nop
0x18000970d  mov     [rbp+57h+var_40], rbx
0x180009711  lea     rcx, [rbp+57h+var_40]
0x180009715  call    ?DeAssign@?$SmartPtr@VRegistryKey@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::RegistryKey>::DeAssign(void)
0x18000971a  nop
0x18000971b  lea     rax, ??_7?$SmartPtr@V?$ArrayList@PEAVISetupCleanupJob@@@UnBCL@@@UnBCL@@6B@; const UnBCL::SmartPtr<UnBCL::ArrayList<ISetupCleanupJob *>>::`vftable'
0x180009722  mov     [rbp+57h+var_70], rax
0x180009726  lea     rcx, [rbp+57h+var_70]
0x18000972a  call    ?DeAssign@?$SmartPtr@U?$IEnumerator@PEAVISetupCleanupJob@@@UnBCL@@@UnBCL@@AEAAXXZ; UnBCL::SmartPtr<UnBCL::IEnumerator<ISetupCleanupJob *>>::DeAssign(void)
0x18000972f  mov     rax, rsi
0x180009732  lea     r11, [rsp+0F0h+var_20]
0x18000973a  mov     rbx, [r11+30h]
0x18000973e  mov     rsi, [r11+40h]
0x180009742  mov     rsp, r11
0x180009745  pop     r15
0x180009747  pop     r14
0x180009749  pop     r13
0x18000974b  pop     rdi
0x18000974c  pop     rbp
0x18000974d  retn
```
