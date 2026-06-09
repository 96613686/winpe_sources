# Windows::Compat::Inventory::InstallMonApi::StopInstallMonitoring(void)

- ea: `0x1800c7010`
- end: `0x1800c70c6`
- name: `?StopInstallMonitoring@InstallMonApi@Inventory@Compat@Windows@@QEAAJXZ`
- size: `182`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InstallMonApi *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800c688c`
- `0x1800c6e80`

## callees

- `0x180010b74`
- `0x1800152d0`
- `0x1800c7010`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c70a5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c70a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c70ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c70ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c709a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c709a`

## string_xrefs

- `0x1800c702c`: `Install Monitoring - Feature_InstallTracingV2 is not enabled.`
- `0x1800c7039`: `Windows::Compat::Inventory::InstallMonApi::StopInstallMonitoring`
- `0x1800c707d`: `Windows::Compat::Inventory::InstallMonApi::StopInstallMonitoring`
- `0x1800c7070`: `StopInstallMonitoring [%#x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::InstallMonApi::StopInstallMonitoring(
        Windows::Compat::Inventory::InstallMonApi *this)
{
  unsigned int v3; // esi
  __int64 (*v4)(void); // rax
  HMODULE v5; // rbp
  DWORD LastError; // ebx

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl'::`2'::impl) )
  {
    v3 = -2147467262;
    v4 = (__int64 (*)(void))*((_QWORD *)this + 4);
    if ( v4 && *((_BYTE *)this + 56) )
      v3 = v4();
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::InstallMonApi::StopInstallMonitoring",
      225,
      "StopInstallMonitoring [%#x]",
      v3);
    *((_BYTE *)this + 56) = 0;
    v5 = *(HMODULE *)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      FreeLibrary(v5);
      SetLastError(LastError);
    }
    *(_QWORD *)this = 0;
    return v3;
  }
  else
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::InstallMonApi::StopInstallMonitoring",
      215,
      "Install Monitoring - Feature_InstallTracingV2 is not enabled.");
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800c7010  push    rbx
0x1800c7012  push    rbp
0x1800c7013  push    rsi
0x1800c7014  push    rdi
0x1800c7015  sub     rsp, 38h
0x1800c7019  mov     rdi, rcx
0x1800c701c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstallTracingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2> `wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl(void)'::`2'::impl
0x1800c7023  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(void)
0x1800c7028  test    al, al
0x1800c702a  jnz     short loc_1800C7051
0x1800c702c  lea     r9, aInstallMonitor; "Install Monitoring - Feature_InstallTra"...
0x1800c7033  mov     r8d, 0D7h
0x1800c7039  lea     rdx, aWindowsCompatI_62; "Windows::Compat::Inventory::InstallMonA"...
0x1800c7040  mov     ecx, 3
0x1800c7045  call    AslLogCallPrintf
0x1800c704a  mov     eax, 80004001h
0x1800c704f  jmp     short loc_1800C70BD
0x1800c7051  mov     esi, 80004002h
0x1800c7056  mov     rax, [rdi+20h]
0x1800c705a  test    rax, rax
0x1800c705d  jz      short loc_1800C706C
0x1800c705f  cmp     byte ptr [rdi+38h], 0
0x1800c7063  jz      short loc_1800C706C
0x1800c7065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c706a  mov     esi, eax
0x1800c706c  mov     [rsp+58h+var_38], esi
0x1800c7070  lea     r9, aStopinstallmon_0; "StopInstallMonitoring [%#x]"
0x1800c7077  mov     r8d, 0E1h
0x1800c707d  lea     rdx, aWindowsCompatI_62; "Windows::Compat::Inventory::InstallMonA"...
0x1800c7084  mov     ecx, 3
0x1800c7089  call    AslLogCallPrintf
0x1800c708e  mov     byte ptr [rdi+38h], 0
0x1800c7092  mov     rbp, [rdi]
0x1800c7095  test    rbp, rbp
0x1800c7098  jz      short loc_1800C70B4
0x1800c709a  call    cs:__imp_GetLastError
0x1800c70a0  mov     ebx, eax
0x1800c70a2  mov     rcx, rbp; hLibModule
0x1800c70a5  call    cs:__imp_FreeLibrary
0x1800c70ab  mov     ecx, ebx; dwErrCode
0x1800c70ad  call    cs:__imp_SetLastError
0x1800c70b3  nop
0x1800c70b4  mov     qword ptr [rdi], 0
0x1800c70bb  mov     eax, esi
0x1800c70bd  add     rsp, 38h
0x1800c70c1  pop     rdi
0x1800c70c2  pop     rsi
0x1800c70c3  pop     rbp
0x1800c70c4  pop     rbx
0x1800c70c5  retn
```
