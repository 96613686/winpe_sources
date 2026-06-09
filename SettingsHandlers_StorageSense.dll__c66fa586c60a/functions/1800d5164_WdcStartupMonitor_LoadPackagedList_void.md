# WdcStartupMonitor::LoadPackagedList(void)

- ea: `0x1800d5164`
- end: `0x1800d5538`
- name: `?LoadPackagedList@WdcStartupMonitor@@QEAAJXZ`
- size: `980`
- prototype: `__int64 __fastcall(WdcStartupMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d715c`

## callees

- `0x180006e50`
- `0x18000e6cc`
- `0x180012a70`
- `0x180018244`
- `0x180019fa8`
- `0x180044d90`
- `0x1800cff88`
- `0x1800d2548`
- `0x1800d4298`
- `0x1800d5164`
- `0x1800d5988`
- `0x1800d6964`
- `0x1800d77f4`
- `0x1800d782c`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5426`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d548c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d5426`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d548c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5299`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d52a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d52b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d52c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d52d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d52e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d539c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d5299`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d52a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d52b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d52c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d52d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d52e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d539c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d51f3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d5233`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d51f3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d5233`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall WdcStartupMonitor::LoadPackagedList(WdcStartupMonitor *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  unsigned int v3; // eax
  __int64 v4; // rbx
  int Item; // eax
  int v6; // edi
  HSTRING *v7; // rdi
  unsigned int StringRawBuffer; // r15d
  PCWSTR v9; // r14
  PCWSTR v10; // rsi
  PCWSTR v11; // rax
  WdcStartupMonitor *v12; // r15
  __int64 v13; // rdx
  _BYTE *v14; // r15
  __int64 v15; // r14
  int (__fastcall *v16)(__int64, _QWORD, _QWORD, _BYTE **); // rsi
  __int64 v17; // rax
  __int64 v18; // rdi
  int (__fastcall *v19)(__int64, _BYTE *, __int64 *); // rsi
  __int64 v20; // rcx
  __int64 v21; // rsi
  int (__fastcall *v22)(__int64, HSTRING *); // rdi
  int v24; // [rsp+20h] [rbp-B9h]
  _BYTE *v25; // [rsp+68h] [rbp-71h] BYREF
  __int64 v26; // [rsp+70h] [rbp-69h] BYREF
  HSTRING string; // [rsp+78h] [rbp-61h] BYREF
  __int64 v28; // [rsp+80h] [rbp-59h] BYREF
  int v29; // [rsp+88h] [rbp-51h] BYREF
  unsigned int v30; // [rsp+8Ch] [rbp-4Dh]
  HSTRING v31; // [rsp+90h] [rbp-49h] BYREF
  __int64 v32; // [rsp+98h] [rbp-41h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-39h] BYREF
  BOOL v34; // [rsp+A8h] [rbp-31h]
  BOOL v35; // [rsp+ACh] [rbp-2Dh]
  __int64 v36; // [rsp+B0h] [rbp-29h] BYREF
  WdcStartupMonitor *v37; // [rsp+B8h] [rbp-21h]
  HSTRING_HEADER hstringHeader; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v39; // [rsp+D8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v37 = this;
  v36 = 0;
  v1 = PackagedStartupTasks::Create(&v36);
  v2 = v1;
  if ( v1 >= 0 )
  {
    v33 = 0;
    v39 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.Application",
      0x2Du,
      0x2Cu);
    v34 = (int)RoGetActivationFactory(v39, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v33) >= 0;
    v32 = 0;
    v39 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.ApplicationResourceResolver",
      0x3Du,
      0x3Cu);
    v35 = (int)RoGetActivationFactory(v39, &GUID_84463b2a_c88e_4597_b41f_17d3bf6486e9, &v32) >= 0;
    v3 = 0;
    v4 = v36;
    while ( 1 )
    {
      v30 = v3;
      if ( v3 >= *(_DWORD *)(v4 + 16) )
        break;
      v25 = 0;
      v28 = 0;
      Item = PackagedStartupTasks::GetItem(v4, v3, &v28);
      v6 = Item;
      if ( Item < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C8,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
          (const char *)(unsigned int)Item,
          v24);
        wistd::unique_ptr<PackagedStartupTask,wistd::default_delete<PackagedStartupTask>>::reset(&v28);
        wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&v32);
        wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&v33);
        v2 = v6;
        goto LABEL_24;
      }
      v7 = (HSTRING *)v28;
      v31 = *(HSTRING *)(v28 + 76);
      LODWORD(v26) = 8 - (*(_BYTE *)(v28 + 72) != 0);
      WindowsGetStringRawBuffer(*(HSTRING *)(v28 + 56), 0);
      WindowsGetStringRawBuffer(v7[6], 0);
      StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(v7[4], 0);
      v9 = WindowsGetStringRawBuffer(v7[3], 0);
      v10 = WindowsGetStringRawBuffer(v7[2], 0);
      v11 = WindowsGetStringRawBuffer(v7[1], 0);
      v24 = StringRawBuffer;
      v12 = v37;
      if ( (int)WdcStartupMonitor::SetPackagedData(v37, v11, v10, v9) >= 0 )
      {
        if ( !IsWCOSPlatform() )
          WdcStartupMonitor::MapStartupProcesses(v12, v13, (__int64 *)&v25);
        v14 = v25;
        v25[577] = 1;
        *((_QWORD *)v14 + 4) = 0x400000000000000LL;
        if ( v34 && v35 )
        {
          v25 = 0;
          v26 = 0;
          v15 = v33;
          v16 = *(int (__fastcall **)(__int64, _QWORD, _QWORD, _BYTE **))(*(_QWORD *)v33 + 240LL);
          v25 = 0;
          v31 = (HSTRING)WindowsGetStringRawBuffer(v7[8], 0);
          v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v31);
          if ( v16(v15, 0, *(_QWORD *)(v17 + 24), &v25) >= 0 )
          {
            v18 = v32;
            v19 = *(int (__fastcall **)(__int64, _BYTE *, __int64 *))(*(_QWORD *)v32 + 48LL);
            v20 = v26;
            v26 = 0;
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            if ( v19(v18, v25, &v26) >= 0 )
            {
              string = 0;
              v21 = v26;
              v22 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v26 + 96LL);
              WindowsDeleteString(0);
              string = 0;
              if ( v22(v21, &string) >= 0 )
              {
                v31 = string;
                if ( (int)Microsoft::WRL::Wrappers::HString::Set((HSTRING *)v14 + 60, &v31) >= 0 )
                {
                  v29 = 0;
                  if ( (*(int (__fastcall **)(_BYTE *, int *))(*(_QWORD *)v25 + 344LL))(v25, &v29) >= 0 )
                    *((_DWORD *)v14 + 160) = v29;
                }
              }
              WindowsDeleteString(string);
              string = 0;
            }
          }
          wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&v26);
          wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&v25);
        }
      }
      wistd::unique_ptr<PackagedStartupTask,wistd::default_delete<PackagedStartupTask>>::reset(&v28);
      v3 = v30 + 1;
    }
    wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&v32);
    wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(&v33);
    v2 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5BA,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\startupshared\\startuphelper.cpp",
      (const char *)(unsigned int)v1,
      v24);
  }
LABEL_24:
  wistd::unique_ptr<PackagedStartupTasks,wistd::default_delete<PackagedStartupTasks>>::reset(&v36);
  return v2;
}

```

## disassembly

```asm
0x1800d5164  push    rbp
0x1800d5166  push    rbx
0x1800d5167  push    rsi
0x1800d5168  push    rdi
0x1800d5169  push    r12
0x1800d516b  push    r13
0x1800d516d  push    r14
0x1800d516f  push    r15
0x1800d5171  lea     rbp, [rsp-1Fh]
0x1800d5176  sub     rsp, 0F8h
0x1800d517d  mov     rax, cs:__security_cookie
0x1800d5184  xor     rax, rsp
0x1800d5187  mov     [rbp+57h+var_50], rax
0x1800d518b  mov     [rbp+57h+var_78], rcx
0x1800d518f  xor     r12d, r12d
0x1800d5192  mov     [rbp+57h+var_80], r12
0x1800d5196  lea     rcx, [rbp+57h+var_80]
0x1800d519a  call    ?Create@PackagedStartupTasks@@SAJAEAV?$unique_ptr@VPackagedStartupTasks@@U?$default_delete@VPackagedStartupTasks@@@wistd@@@wistd@@@Z; PackagedStartupTasks::Create(wistd::unique_ptr<PackagedStartupTasks,wistd::default_delete<PackagedStartupTasks>> &)
0x1800d519f  mov     ebx, eax
0x1800d51a1  test    eax, eax
0x1800d51a3  jns     short loc_1800D51C2
0x1800d51a5  mov     rcx, [rbp+5Fh]; this
0x1800d51a9  mov     r9d, eax; char *
0x1800d51ac  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d51b3  mov     edx, 5BAh; void *
0x1800d51b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d51bd  jmp     loc_1800D550D
0x1800d51c2  mov     [rbp+57h+var_90], r12
0x1800d51c6  mov     [rbp+57h+var_58], r12
0x1800d51ca  mov     r9d, 2Ch ; ','; unsigned int
0x1800d51d0  lea     r8d, [r9+1]; unsigned int
0x1800d51d4  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800d51db  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800d51df  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d51e4  lea     r8, [rbp+57h+var_90]
0x1800d51e8  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x1800d51ef  mov     rcx, [rbp+57h+var_58]
0x1800d51f3  call    cs:__imp_RoGetActivationFactory
0x1800d51f9  nop
0x1800d51fa  shr     eax, 1Fh
0x1800d51fd  xor     al, 1
0x1800d51ff  mov     [rbp+57h+var_88], eax
0x1800d5202  mov     [rbp+57h+var_98], r12
0x1800d5206  mov     [rbp+57h+var_58], r12
0x1800d520a  mov     r9d, 3Ch ; '<'; unsigned int
0x1800d5210  lea     r8d, [r9+1]; unsigned int
0x1800d5214  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationResourceResolver@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800d521b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800d521f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d5224  lea     r8, [rbp+57h+var_98]
0x1800d5228  lea     rdx, _GUID_84463b2a_c88e_4597_b41f_17d3bf6486e9
0x1800d522f  mov     rcx, [rbp+57h+var_58]
0x1800d5233  call    cs:__imp_RoGetActivationFactory
0x1800d5239  shr     eax, 1Fh
0x1800d523c  xor     al, 1
0x1800d523e  mov     [rbp+57h+var_84], eax
0x1800d5241  mov     eax, r12d
0x1800d5244  mov     rbx, [rbp+57h+var_80]
0x1800d5248  mov     [rbp+57h+var_A4], eax
0x1800d524b  cmp     eax, [rbx+10h]
0x1800d524e  jnb     loc_1800D54F7
0x1800d5254  mov     [rbp+57h+var_C8], r12
0x1800d5258  mov     [rbp+57h+var_B0], r12
0x1800d525c  lea     r8, [rbp+57h+var_B0]
0x1800d5260  mov     edx, eax
0x1800d5262  mov     rcx, rbx
0x1800d5265  call    ?GetItem@PackagedStartupTasks@@QEAAJIAEAV?$unique_ptr@VPackagedStartupTask@@U?$default_delete@VPackagedStartupTask@@@wistd@@@wistd@@@Z; PackagedStartupTasks::GetItem(uint,wistd::unique_ptr<PackagedStartupTask,wistd::default_delete<PackagedStartupTask>> &)
0x1800d526a  mov     edi, eax
0x1800d526c  test    eax, eax
0x1800d526e  js      loc_1800D54BD
0x1800d5274  mov     rdi, [rbp+57h+var_B0]
0x1800d5278  mov     rax, [rdi+4Ch]
0x1800d527c  mov     [rbp+57h+var_A0], rax
0x1800d5280  mov     al, [rdi+49h]
0x1800d5283  mov     [rbp+57h+var_D0], al
0x1800d5286  mov     al, [rdi+48h]
0x1800d5289  neg     al
0x1800d528b  sbb     eax, eax
0x1800d528d  add     eax, 8
0x1800d5290  mov     dword ptr [rbp+57h+var_C0], eax
0x1800d5293  xor     edx, edx; length
0x1800d5295  mov     rcx, [rdi+38h]; string
0x1800d5299  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d529f  mov     r13, rax
0x1800d52a2  xor     edx, edx; length
0x1800d52a4  mov     rcx, [rdi+30h]; string
0x1800d52a8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d52ae  mov     r12, rax
0x1800d52b1  xor     edx, edx; length
0x1800d52b3  mov     rcx, [rdi+20h]; string
0x1800d52b7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d52bd  mov     r15, rax
0x1800d52c0  xor     edx, edx; length
0x1800d52c2  mov     rcx, [rdi+18h]; string
0x1800d52c6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d52cc  mov     r14, rax
0x1800d52cf  xor     edx, edx; length
0x1800d52d1  mov     rcx, [rdi+10h]; string
0x1800d52d5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d52db  mov     rsi, rax
0x1800d52de  xor     edx, edx; length
0x1800d52e0  mov     rcx, [rdi+8]; string
0x1800d52e4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d52ea  lea     rcx, [rbp+57h+var_C8]
0x1800d52ee  mov     [rsp+130h+var_E0], rcx
0x1800d52f3  mov     cl, [rbp+57h+var_D0]
0x1800d52f6  mov     [rsp+130h+var_E8], cl
0x1800d52fa  mov     ecx, dword ptr [rbp+57h+var_C0]
0x1800d52fd  mov     [rsp+130h+var_F0], ecx
0x1800d5301  lea     rcx, [rbp+57h+var_A0]
0x1800d5305  mov     [rsp+130h+var_F8], rcx
0x1800d530a  mov     [rsp+130h+var_100], r13
0x1800d530f  mov     [rsp+130h+var_108], r12
0x1800d5314  mov     [rsp+130h+var_110], r15
0x1800d5319  mov     r9, r14
0x1800d531c  mov     r8, rsi
0x1800d531f  mov     rdx, rax
0x1800d5322  mov     r15, [rbp+57h+var_78]
0x1800d5326  mov     rcx, r15
0x1800d5329  call    ?SetPackagedData@WdcStartupMonitor@@QEAAJPEBG00000PEBU_FILETIME@@W4_tagTM_ITEMSTATUS@@_NPEAPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::SetPackagedData(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_FILETIME const *,_tagTM_ITEMSTATUS,bool,_WDC_STARTUP_INFO * *)
0x1800d532e  xor     r12d, r12d
0x1800d5331  test    eax, eax
0x1800d5333  js      loc_1800D54AA
0x1800d5339  call    ?IsWCOSPlatform@@YA_NXZ; IsWCOSPlatform(void)
0x1800d533e  test    al, al
0x1800d5340  jnz     short loc_1800D534E
0x1800d5342  lea     r8, [rbp+57h+var_C8]
0x1800d5346  mov     rcx, r15
0x1800d5349  call    ?MapStartupProcesses@WdcStartupMonitor@@QEAAJW4_STARTUP_LOCATION@@PEAPEAU_WDC_STARTUP_INFO@@@Z; WdcStartupMonitor::MapStartupProcesses(_STARTUP_LOCATION,_WDC_STARTUP_INFO * *)
0x1800d534e  mov     r15, [rbp+57h+var_C8]
0x1800d5352  mov     byte ptr [r15+241h], 1
0x1800d535a  mov     rax, 400000000000000h
0x1800d5364  mov     [r15+20h], rax
0x1800d5368  cmp     byte ptr [rbp+57h+var_88], r12b
0x1800d536c  jz      loc_1800D54AA
0x1800d5372  cmp     byte ptr [rbp+57h+var_84], r12b
0x1800d5376  jz      loc_1800D54AA
0x1800d537c  mov     [rbp+57h+var_C8], r12
0x1800d5380  mov     [rbp+57h+var_C0], r12
0x1800d5384  mov     r14, [rbp+57h+var_90]
0x1800d5388  mov     rax, [r14]
0x1800d538b  mov     rsi, [rax+0F0h]
0x1800d5392  mov     [rbp+57h+var_C8], r12
0x1800d5396  xor     edx, edx; length
0x1800d5398  mov     rcx, [rdi+40h]; string
0x1800d539c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d53a2  mov     [rbp+57h+var_A0], rax
0x1800d53a6  lea     rdx, [rbp+57h+var_A0]
0x1800d53aa  lea     rcx, [rbp+57h+hstringHeader]
0x1800d53ae  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800d53b3  nop
0x1800d53b4  lea     r9, [rbp+57h+var_C8]
0x1800d53b8  mov     r8, [rax+18h]
0x1800d53bc  xor     edx, edx
0x1800d53be  mov     rcx, r14
0x1800d53c1  mov     rax, rsi
0x1800d53c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d53c9  nop
0x1800d53ca  shr     eax, 1Fh
0x1800d53cd  test    al, al
0x1800d53cf  jnz     loc_1800D5496
0x1800d53d5  mov     rdi, [rbp+57h+var_98]
0x1800d53d9  mov     rax, [rdi]
0x1800d53dc  mov     rsi, [rax+30h]
0x1800d53e0  mov     rcx, [rbp+57h+var_C0]
0x1800d53e4  mov     [rbp+57h+var_C0], r12
0x1800d53e8  test    rcx, rcx
0x1800d53eb  jz      short loc_1800D53FA
0x1800d53ed  mov     rdx, [rcx]
0x1800d53f0  mov     rax, [rdx+10h]
0x1800d53f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d53f9  nop
0x1800d53fa  lea     r8, [rbp+57h+var_C0]
0x1800d53fe  mov     rdx, [rbp+57h+var_C8]
0x1800d5402  mov     rcx, rdi
0x1800d5405  mov     rax, rsi
0x1800d5408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d540d  test    eax, eax
0x1800d540f  js      loc_1800D5496
0x1800d5415  mov     [rbp+57h+string], r12
0x1800d5419  mov     rsi, [rbp+57h+var_C0]
0x1800d541d  mov     rax, [rsi]
0x1800d5420  mov     rdi, [rax+60h]
0x1800d5424  xor     ecx, ecx; string
0x1800d5426  call    cs:__imp_WindowsDeleteString
0x1800d542c  mov     [rbp+57h+string], r12
0x1800d5430  lea     rdx, [rbp+57h+string]
0x1800d5434  mov     rcx, rsi
0x1800d5437  mov     rax, rdi
0x1800d543a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d543f  test    eax, eax
0x1800d5441  js      short loc_1800D5488
0x1800d5443  mov     rax, [rbp+57h+string]
0x1800d5447  mov     [rbp+57h+var_A0], rax
0x1800d544b  lea     rcx, [r15+1E0h]; newString
0x1800d5452  lea     rdx, [rbp+57h+var_A0]; HSTRING *
0x1800d5456  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800d545b  test    eax, eax
0x1800d545d  js      short loc_1800D5488
0x1800d545f  mov     [rbp+57h+var_A8], r12d
0x1800d5463  mov     rcx, [rbp+57h+var_C8]
0x1800d5467  mov     rax, [rcx]
0x1800d546a  lea     rdx, [rbp+57h+var_A8]
0x1800d546e  mov     rax, [rax+158h]
0x1800d5475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d547a  test    eax, eax
0x1800d547c  js      short loc_1800D5488
0x1800d547e  mov     eax, [rbp+57h+var_A8]
0x1800d5481  mov     [r15+280h], eax
0x1800d5488  mov     rcx, [rbp+57h+string]; string
0x1800d548c  call    cs:__imp_WindowsDeleteString
0x1800d5492  mov     [rbp+57h+string], r12
0x1800d5496  lea     rcx, [rbp+57h+var_C0]
0x1800d549a  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x1800d549f  nop
0x1800d54a0  lea     rcx, [rbp+57h+var_C8]
0x1800d54a4  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x1800d54a9  nop
0x1800d54aa  lea     rcx, [rbp+57h+var_B0]
0x1800d54ae  call    ?reset@?$unique_ptr@VPackagedStartupTask@@U?$default_delete@VPackagedStartupTask@@@wistd@@@wistd@@QEAAXPEAVPackagedStartupTask@@@Z; wistd::unique_ptr<PackagedStartupTask,wistd::default_delete<PackagedStartupTask>>::reset(PackagedStartupTask *)
0x1800d54b3  mov     eax, [rbp+57h+var_A4]
0x1800d54b6  inc     eax
0x1800d54b8  jmp     loc_1800D5248
0x1800d54bd  mov     rcx, [rbp+5Fh]; this
0x1800d54c1  mov     r9d, edi; char *
0x1800d54c4  lea     r8, aOnecoreuapShel_6; "onecoreuap\\shell\\coresettinghandlers"...
0x1800d54cb  mov     edx, 5C8h; void *
0x1800d54d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d54d5  nop
0x1800d54d6  lea     rcx, [rbp+57h+var_B0]
0x1800d54da  call    ?reset@?$unique_ptr@VPackagedStartupTask@@U?$default_delete@VPackagedStartupTask@@@wistd@@@wistd@@QEAAXPEAVPackagedStartupTask@@@Z; wistd::unique_ptr<PackagedStartupTask,wistd::default_delete<PackagedStartupTask>>::reset(PackagedStartupTask *)
0x1800d54df  nop
0x1800d54e0  lea     rcx, [rbp+57h+var_98]
0x1800d54e4  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x1800d54e9  nop
0x1800d54ea  lea     rcx, [rbp+57h+var_90]
0x1800d54ee  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x1800d54f3  mov     ebx, edi
0x1800d54f5  jmp     short loc_1800D550D
0x1800d54f7  lea     rcx, [rbp+57h+var_98]
0x1800d54fb  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x1800d5500  nop
0x1800d5501  lea     rcx, [rbp+57h+var_90]
0x1800d5505  call    ??1?$com_ptr_t@UIApplicationStatics@StateRepository@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::StateRepository::IApplicationStatics,wil::err_exception_policy>(void)
0x1800d550a  mov     ebx, r12d
0x1800d550d  lea     rcx, [rbp+57h+var_80]
0x1800d5511  call    ?reset@?$unique_ptr@VPackagedStartupTasks@@U?$default_delete@VPackagedStartupTasks@@@wistd@@@wistd@@QEAAXPEAVPackagedStartupTasks@@@Z; wistd::unique_ptr<PackagedStartupTasks,wistd::default_delete<PackagedStartupTasks>>::reset(PackagedStartupTasks *)
0x1800d5516  mov     eax, ebx
0x1800d5518  mov     rcx, [rbp+57h+var_50]
0x1800d551c  xor     rcx, rsp; StackCookie
0x1800d551f  call    __security_check_cookie
0x1800d5524  add     rsp, 0F8h
0x1800d552b  pop     r15
0x1800d552d  pop     r14
0x1800d552f  pop     r13
0x1800d5531  pop     r12
0x1800d5533  pop     rdi
0x1800d5534  pop     rsi
0x1800d5535  pop     rbx
0x1800d5536  pop     rbp
0x1800d5537  retn
```
