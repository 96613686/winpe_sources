# AppReadiness::PackageInfo::GetMainPackageId(AppReadiness::User *)

- ea: `0x180017e74`
- end: `0x1800180f0`
- name: `?GetMainPackageId@PackageInfo@AppReadiness@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVUser@2@@Z`
- size: `636`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180017d98`
- `0x18006ca30`

## callees

- `0x180002958`
- `0x18000b488`
- `0x18000bb50`
- `0x18000c000`
- `0x18000e4a0`
- `0x180017e74`
- `0x1800180f8`
- `0x18001870c`
- `0x1800187c4`
- `0x180027a4c`
- `0x18002c40c`
- `0x18003235c`
- `0x180037528`
- `0x1800382e0`
- `0x180038f14`
- `0x18003e210`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001809d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800180ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001809d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800180ab`

## string_xrefs

- `0x180017fb1`: `onecoreuap\shell\appreadiness\src\core\packageinfo.cpp`
- `0x180017fbd`: `AppReadiness::PackageInfo::GetMainPackageId`
- `0x180017fc4`: `packageManager->FindPackagesByUserSecurityIdPackageFamilyNameWithPackageTypes(userSid.Get(), packageFamilyName.Get(), PackageTypes_Main, &packageIter)`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall AppReadiness::PackageInfo::GetMainPackageId(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v6; // rcx
  _OWORD *v7; // rdx
  _QWORD *v8; // rdx
  __int64 v9; // r8
  void *v10; // r14
  __int64 (__fastcall *v11)(void *, HSTRING, HSTRING, __int64, __int64 *); // rbx
  int v12; // eax
  __int64 PackageFullName; // rax
  char v14; // bl
  _OWORD *v15; // rdx
  char v16; // bl
  __int64 v17; // rcx
  __int64 v19; // [rsp+30h] [rbp-59h] BYREF
  HSTRING string; // [rsp+38h] [rbp-51h] BYREF
  HSTRING v21; // [rsp+40h] [rbp-49h] BYREF
  void *v22; // [rsp+48h] [rbp-41h] BYREF
  int v23; // [rsp+50h] [rbp-39h]
  _QWORD v24[3]; // [rsp+58h] [rbp-31h] BYREF
  WCHAR sourceString[8]; // [rsp+70h] [rbp-19h] BYREF
  __int128 v26; // [rsp+80h] [rbp-9h]
  _BYTE pExceptionObject[40]; // [rsp+90h] [rbp+7h] BYREF

  v22 = a2;
  v23 = 0;
  if ( AppReadiness::PackageInfo::IsBundle((AppReadiness::PackageInfo *)a1) || !*(_QWORD *)(a1 + 88) )
  {
    if ( !*(_QWORD *)(a1 + 56) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v6);
    AppReadiness::PackageInfo::GetPackageManager<Windows::Management::Deployment::IPackageManager2>(&v22);
    to_winstring(&v21, (PCNZWCH)(a1 + 40));
    v8 = (_QWORD *)(a3 + 64);
    if ( *(_QWORD *)(a3 + 88) > 7u )
      v8 = (_QWORD *)*v8;
    *(_OWORD *)sourceString = 0;
    v26 = 0;
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)v8 + v9) );
    std::wstring::_Construct<1,unsigned short const *>(sourceString);
    to_winstring(&string, sourceString);
    if ( *((_QWORD *)&v26 + 1) > 7u )
      std::_Deallocate<16>(*(void **)sourceString, 2LL * *((_QWORD *)&v26 + 1) + 2);
    v19 = 0;
    v10 = v22;
    v11 = *(__int64 (__fastcall **)(void *, HSTRING, HSTRING, __int64, __int64 *))(*(_QWORD *)v22 + 112LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
    v12 = v11(v10, string, v21, 1, &v19);
    if ( v12 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)pExceptionObject,
        v12,
        "packageManager->FindPackagesByUserSecurityIdPackageFamilyNameWithPackageTypes(userSid.Get(), packageFamilyName.G"
        "et(), PackageTypes_Main, &packageIter)",
        "AppReadiness::PackageInfo::GetMainPackageId",
        "onecoreuap\\shell\\appreadiness\\src\\core\\packageinfo.cpp",
        391);
      throw (Windows::HResultException *)pExceptionObject;
    }
    to_vector<Windows::ApplicationModel::IPackage,Windows::ApplicationModel::Package>(v24, &v19);
    if ( v24[0] == v24[1] )
    {
      v15 = (_OWORD *)(a1 + 72);
      *(_OWORD *)sourceString = 0;
      v26 = 0;
      if ( *(_QWORD *)(a1 + 96) > 7u )
        v15 = *(_OWORD **)v15;
      std::wstring::_Construct<2,unsigned short const *>(sourceString, v15, *(_QWORD *)(a1 + 88));
      PackageFullName = (__int64)sourceString;
      v14 = 2;
    }
    else
    {
      PackageFullName = AppReadiness::PackageInfo::GetPackageFullName((__int64)pExceptionObject, *(_QWORD *)v24[0]);
      v14 = 1;
    }
    std::wstring::wstring((__int64)a2, PackageFullName);
    v16 = v14 | 4;
    if ( (v16 & 2) != 0 )
    {
      v16 &= ~2u;
      std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(sourceString);
    }
    if ( (v16 & 1) != 0 )
      std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(pExceptionObject);
    std::vector<Microsoft::WRL::ComPtr<AppReadiness::ITask>>::_Tidy(v24);
    v17 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v21);
    v21 = 0;
    if ( v10 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  else
  {
    v7 = (_OWORD *)(a1 + 72);
    *(_OWORD *)a2 = 0;
    a2[2] = 0;
    a2[3] = 0;
    if ( *(_QWORD *)(a1 + 96) > 7u )
      v7 = *(_OWORD **)v7;
    std::wstring::_Construct<2,unsigned short const *>(a2, v7, *(_QWORD *)(a1 + 88));
  }
  return a2;
}

```

## disassembly

```asm
0x180017e74  mov     [rsp-8+arg_18], rbx
0x180017e79  push    rbp
0x180017e7a  push    rsi
0x180017e7b  push    rdi
0x180017e7c  push    r14
0x180017e7e  push    r15
0x180017e80  lea     rbp, [rsp-37h]
0x180017e85  sub     rsp, 0C0h
0x180017e8c  mov     rax, cs:__security_cookie
0x180017e93  xor     rax, rsp
0x180017e96  mov     [rbp+57h+var_28], rax
0x180017e9a  mov     r14, r8
0x180017e9d  mov     rdi, rdx
0x180017ea0  mov     rsi, rcx
0x180017ea3  mov     [rbp+57h+var_98], rdx
0x180017ea7  xor     r15d, r15d
0x180017eaa  mov     [rbp+57h+var_90], r15d
0x180017eae  call    ?IsBundle@PackageInfo@AppReadiness@@QEAA_NXZ; AppReadiness::PackageInfo::IsBundle(void)
0x180017eb3  test    al, al
0x180017eb5  jnz     short loc_180017EEA
0x180017eb7  cmp     [rsi+58h], r15
0x180017ebb  jz      short loc_180017EEA
0x180017ebd  lea     rdx, [rsi+48h]
0x180017ec1  xorps   xmm0, xmm0
0x180017ec4  movups  xmmword ptr [rdi], xmm0
0x180017ec7  mov     [rdi+10h], r15
0x180017ecb  mov     [rdi+18h], r15
0x180017ecf  mov     r8, [rdx+10h]
0x180017ed3  cmp     qword ptr [rdx+18h], 7
0x180017ed8  jbe     short loc_180017EDD
0x180017eda  mov     rdx, [rdx]
0x180017edd  mov     rcx, rdi
0x180017ee0  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180017ee5  jmp     loc_1800180CA
0x180017eea  cmp     [rsi+38h], r15
0x180017eee  jnz     short loc_180017EF5
0x180017ef0  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!m_packageFamilyName.empty()", "All package infos are expected to have a valid package familyname")
0x180017ef5  lea     rcx, [rbp+57h+var_98]
0x180017ef9  call    ??$GetPackageManager@UIPackageManager2@Deployment@Management@Windows@@@PackageInfo@AppReadiness@@SA?AV?$ComPtr@UIPackageManager2@Deployment@Management@Windows@@@WRL@Microsoft@@XZ; AppReadiness::PackageInfo::GetPackageManager<Windows::Management::Deployment::IPackageManager2>(void)
0x180017efe  nop
0x180017eff  lea     rdx, [rsi+28h]; sourceString
0x180017f03  lea     rcx, [rbp+57h+var_A0]; string
0x180017f07  call    ?to_winstring@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; to_winstring(std::wstring const &)
0x180017f0c  nop
0x180017f0d  lea     rdx, [r14+40h]
0x180017f11  cmp     qword ptr [rdx+18h], 7
0x180017f16  jbe     short loc_180017F1B
0x180017f18  mov     rdx, [rdx]
0x180017f1b  xorps   xmm0, xmm0
0x180017f1e  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x180017f22  xorps   xmm1, xmm1
0x180017f25  movdqu  [rbp+57h+var_60], xmm1
0x180017f2a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180017f2e  inc     r8
0x180017f31  cmp     [rdx+r8*2], r15w
0x180017f36  jnz     short loc_180017F2E
0x180017f38  lea     rcx, [rbp+57h+sourceString]
0x180017f3c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017f41  nop
0x180017f42  lea     rdx, [rbp+57h+sourceString]; sourceString
0x180017f46  lea     rcx, [rbp+57h+string]; string
0x180017f4a  call    ?to_winstring@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; to_winstring(std::wstring const &)
0x180017f4f  nop
0x180017f50  mov     rdx, qword ptr [rbp+57h+var_60+8]
0x180017f54  cmp     rdx, 7
0x180017f58  jbe     short loc_180017F6B
0x180017f5a  lea     rdx, ds:2[rdx*2]
0x180017f62  mov     rcx, qword ptr [rbp+57h+sourceString]
0x180017f66  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180017f6b  mov     [rbp+57h+var_B0], r15
0x180017f6f  mov     r14, [rbp+57h+var_98]
0x180017f73  mov     rax, [r14]
0x180017f76  mov     rbx, [rax+70h]
0x180017f7a  lea     rcx, [rbp+57h+var_B0]
0x180017f7e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017f83  lea     rax, [rbp+57h+var_B0]
0x180017f87  mov     [rsp+0E0h+var_C0], rax
0x180017f8c  mov     r9d, 1
0x180017f92  mov     r8, [rbp+57h+var_A0]
0x180017f96  mov     rdx, [rbp+57h+string]
0x180017f9a  mov     rcx, r14
0x180017f9d  mov     rax, rbx
0x180017fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fa5  test    eax, eax
0x180017fa7  jns     short loc_180017FE7
0x180017fa9  mov     [rsp+0E0h+var_B8], 187h; int
0x180017fb1  lea     rcx, aOnecoreuapShel; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180017fb8  mov     [rsp+0E0h+var_C0], rcx; char *
0x180017fbd  lea     r9, aAppreadinessPa_1; "AppReadiness::PackageInfo::GetMainPacka"...
0x180017fc4  lea     r8, aPackagemanager_8; "packageManager->FindPackagesByUserSecur"...
0x180017fcb  mov     edx, eax; int
0x180017fcd  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180017fd1  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180017fd6  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180017fdd  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180017fe1  call    _CxxThrowException_0
0x180017fe7  lea     rdx, [rbp+57h+var_B0]
0x180017feb  lea     rcx, [rbp+57h+var_88]
0x180017fef  call    ??$to_vector@UIPackage@ApplicationModel@Windows@@VPackage@23@@@YA?AV?$vector@V?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@@std@@@std@@AEBV?$ComPtr@U?$IIterable@PEAVPackage@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; to_vector<Windows::ApplicationModel::IPackage,Windows::ApplicationModel::Package>(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::ApplicationModel::Package *>> const &)
0x180017ff4  nop
0x180017ff5  mov     rdx, [rbp+57h+var_88]
0x180017ff9  cmp     rdx, [rbp+57h+var_80]
0x180017ffd  jz      short loc_180018013
0x180017fff  mov     rdx, [rdx]
0x180018002  lea     rcx, [rbp+57h+pExceptionObject]
0x180018006  call    ?GetPackageFullName@PackageInfo@AppReadiness@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIPackage@ApplicationModel@Windows@@@Z; AppReadiness::PackageInfo::GetPackageFullName(Windows::ApplicationModel::IPackage *)
0x18001800b  nop
0x18001800c  mov     ebx, 1
0x180018011  jmp     short loc_180018046
0x180018013  lea     rdx, [rsi+48h]
0x180018017  xorps   xmm0, xmm0
0x18001801a  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x18001801e  xorps   xmm1, xmm1
0x180018021  movdqu  [rbp+57h+var_60], xmm1
0x180018026  mov     r8, [rdx+10h]
0x18001802a  cmp     qword ptr [rdx+18h], 7
0x18001802f  jbe     short loc_180018034
0x180018031  mov     rdx, [rdx]
0x180018034  lea     rcx, [rbp+57h+sourceString]
0x180018038  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18001803d  lea     rax, [rbp+57h+sourceString]
0x180018041  mov     ebx, 2
0x180018046  mov     rdx, rax
0x180018049  mov     rcx, rdi
0x18001804c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180018051  or      ebx, 4
0x180018054  test    bl, 2
0x180018057  jz      short loc_180018066
0x180018059  and     ebx, 0FFFFFFFDh
0x18001805c  lea     rcx, [rbp+57h+sourceString]
0x180018060  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x180018065  nop
0x180018066  test    bl, 1
0x180018069  jz      short loc_180018075
0x18001806b  lea     rcx, [rbp+57h+pExceptionObject]
0x18001806f  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x180018074  nop
0x180018075  lea     rcx, [rbp+57h+var_88]
0x180018079  call    ?_Tidy@?$vector@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<AppReadiness::ITask>>::_Tidy(void)
0x18001807e  nop
0x18001807f  mov     rcx, [rbp+57h+var_B0]
0x180018083  test    rcx, rcx
0x180018086  jz      short loc_180018099
0x180018088  mov     [rbp+57h+var_B0], r15
0x18001808c  mov     rax, [rcx]
0x18001808f  mov     rax, [rax+10h]
0x180018093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018098  nop
0x180018099  mov     rcx, [rbp+57h+string]; string
0x18001809d  call    cs:__imp_WindowsDeleteString
0x1800180a3  mov     [rbp+57h+string], r15
0x1800180a7  mov     rcx, [rbp+57h+var_A0]; string
0x1800180ab  call    cs:__imp_WindowsDeleteString
0x1800180b1  mov     [rbp+57h+var_A0], r15
0x1800180b5  test    r14, r14
0x1800180b8  jz      short loc_1800180CA
0x1800180ba  mov     rax, [r14]
0x1800180bd  mov     rcx, r14
0x1800180c0  mov     rax, [rax+10h]
0x1800180c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180c9  nop
0x1800180ca  mov     rax, rdi
0x1800180cd  mov     rcx, [rbp+57h+var_28]
0x1800180d1  xor     rcx, rsp; StackCookie
0x1800180d4  call    __security_check_cookie
0x1800180d9  mov     rbx, [rsp+0E0h+arg_18]
0x1800180e1  add     rsp, 0C0h
0x1800180e8  pop     r15
0x1800180ea  pop     r14
0x1800180ec  pop     rdi
0x1800180ed  pop     rsi
0x1800180ee  pop     rbp
0x1800180ef  retn
```
