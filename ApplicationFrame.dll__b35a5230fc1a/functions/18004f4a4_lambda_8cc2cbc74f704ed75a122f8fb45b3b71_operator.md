# _lambda_8cc2cbc74f704ed75a122f8fb45b3b71_::operator()

- ea: `0x18004f4a4`
- end: `0x18004f654`
- name: `_lambda_8cc2cbc74f704ed75a122f8fb45b3b71_::operator()`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180050eb0`

## callees

- `0x180003380`
- `0x18000d72c`
- `0x180012440`
- `0x1800177b8`
- `0x18001b8f8`
- `0x180035d00`
- `0x180040270`
- `0x180043c30`
- `0x18004bb84`
- `0x18004ccac`
- `0x18004f4a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f56d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f56d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f51e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f51e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004f4d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004f4d8`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18004f4e4`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18004f4e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_8cc2cbc74f704ed75a122f8fb45b3b71_::operator()(const WCHAR ***a1)
{
  const WCHAR ***v1; // rsi
  const WCHAR ***v2; // r13
  const WCHAR *v3; // rbx
  HANDLE CurrentThread; // rax
  CApplicationFrame **v5; // r15
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  int updated; // eax
  int v8; // eax
  const char *v9; // r9
  const WCHAR **v10; // r14
  __int64 v11; // rbx
  const WCHAR **v12; // rsi
  CApplicationFrame *v13; // rdi
  int v14; // eax
  unsigned int v15; // ebx
  int v17; // edx
  int v18; // [rsp+20h] [rbp-E8h]
  int v19; // [rsp+20h] [rbp-E8h]
  _BYTE v22[112]; // [rsp+50h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v1 = a1;
  v2 = a1;
  v3 = **a1;
  CurrentThread = GetCurrentThread();
  SetThreadDescription(CurrentThread, v3);
  try
  {
    SplashScreen::CSplashScreenConfiguration::CSplashScreenConfiguration(
      (SplashScreen::CSplashScreenConfiguration *)v22,
      **v2);
    v5 = (CApplicationFrame **)(v2 + 1);
    *((_DWORD *)v2[1] + 84) = SplashScreen::CSplashScreenConfiguration::GetBackgroundColor((SplashScreen::CSplashScreenConfiguration *)v22);
    v6 = (struct _RTL_CRITICAL_SECTION *)v2[1][15];
    EnterCriticalSection(v6);
    if ( v2[1][102] )
    {
      updated = CApplicationFrame::_UpdateBackgroundColor((CApplicationFrame *)v2[1]);
      if ( updated < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x377,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
          (const char *)(unsigned int)updated,
          v18);
      v8 = CApplicationFrame::UpdateBackground(*v5, 0);
      if ( v8 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x378,
          (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
          (const char *)(unsigned int)v8,
          v18);
    }
    if ( v6 )
      LeaveCriticalSection(v6);
    SplashScreen::CSplashScreenConfiguration::~CSplashScreenConfiguration((SplashScreen::CSplashScreenConfiguration *)v22);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x37B,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
      v9);
    v2 = a1;
    v5 = (CApplicationFrame **)(a1 + 1);
    v1 = a1;
  }
  v10 = v2[2];
  v11 = (__int64)v2[3];
  v12 = *v1;
  v13 = *v5;
  Microsoft::WRL::ComPtr<CSystemVisuals>::InternalRelease(v10);
  v14 = Microsoft::WRL::Details::MakeAndInitialize_CSystemVisuals_CSystemVisuals_HWND_______Windows::Internal::NativeString_Windows::Internal::CoTaskMemPolicy_unsigned_short______CApplicationFrame___const____lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2____(
          (_DWORD)v10,
          (int)v13 + 24,
          (_DWORD)v12,
          (_DWORD)v5,
          v11);
  v15 = v14;
  if ( v14 >= 0 )
  {
    v17 = *((_DWORD *)*v5 + 184);
    if ( v17 )
    {
      *((_DWORD *)*v2[2] + 47) = v17;
      *((_DWORD *)*v5 + 184) = 0;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37D,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\appframe.cpp",
      (const char *)(unsigned int)v14,
      v19);
    return v15;
  }
}

```

## disassembly

```asm
0x18004f4a4  push    rbx
0x18004f4a6  push    rsi
0x18004f4a7  push    rdi
0x18004f4a8  push    r13
0x18004f4aa  push    r14
0x18004f4ac  push    r15
0x18004f4ae  sub     rsp, 0D8h
0x18004f4b5  mov     rax, cs:__security_cookie
0x18004f4bc  xor     rax, rsp
0x18004f4bf  mov     [rsp+108h+var_48], rax
0x18004f4c7  mov     rsi, rcx
0x18004f4ca  mov     r13, rcx
0x18004f4cd  mov     [rsp+108h+var_D8], rcx
0x18004f4d2  mov     rax, [rcx]
0x18004f4d5  mov     rbx, [rax]
0x18004f4d8  call    cs:__imp_GetCurrentThread
0x18004f4de  mov     rdx, rbx; lpThreadDescription
0x18004f4e1  mov     rcx, rax; hThread
0x18004f4e4  call    cs:__imp_SetThreadDescription
0x18004f4ea  nop
0x18004f4eb  mov     rdx, [r13+0]
0x18004f4ef  mov     rdx, [rdx]; lpSubKey
0x18004f4f2  lea     rcx, [rsp+108h+var_B8]; this
0x18004f4f7  call    ??0CSplashScreenConfiguration@SplashScreen@@QEAA@PEBG@Z; SplashScreen::CSplashScreenConfiguration::CSplashScreenConfiguration(ushort const *)
0x18004f4fc  nop
0x18004f4fd  lea     rcx, [rsp+108h+var_B8]; this
0x18004f502  call    ?GetBackgroundColor@CSplashScreenConfiguration@SplashScreen@@UEAAKXZ; SplashScreen::CSplashScreenConfiguration::GetBackgroundColor(void)
0x18004f507  lea     r15, [r13+8]
0x18004f50b  mov     rcx, [r15]
0x18004f50e  mov     [rcx+150h], eax
0x18004f514  mov     rax, [r15]
0x18004f517  mov     rbx, [rax+78h]
0x18004f51b  mov     rcx, rbx; lpCriticalSection
0x18004f51e  call    cs:__imp_EnterCriticalSection
0x18004f524  mov     [rsp+108h+var_C8], rbx
0x18004f529  mov     rcx, [r15]; this
0x18004f52c  cmp     qword ptr [rcx+330h], 0
0x18004f534  jz      short loc_18004F565
0x18004f536  call    ?_UpdateBackgroundColor@CApplicationFrame@@AEAAJXZ; CApplicationFrame::_UpdateBackgroundColor(void)
0x18004f53b  mov     rcx, [rsp+108h]; this
0x18004f543  test    eax, eax
0x18004f545  js      loc_18004F62A
0x18004f54b  xor     edx, edx; void *
0x18004f54d  mov     rcx, [r15]; this
0x18004f550  call    ?UpdateBackground@CApplicationFrame@@AEAAJPEAX@Z; CApplicationFrame::UpdateBackground(void *)
0x18004f555  mov     rcx, [rsp+108h]; this
0x18004f55d  test    eax, eax
0x18004f55f  js      loc_18004F63E
0x18004f565  test    rbx, rbx
0x18004f568  jz      short loc_18004F574
0x18004f56a  mov     rcx, rbx; lpCriticalSection
0x18004f56d  call    cs:__imp_LeaveCriticalSection
0x18004f573  nop
0x18004f574  lea     rcx, [rsp+108h+var_B8]; this
0x18004f579  call    ??1CSplashScreenConfiguration@SplashScreen@@QEAA@XZ; SplashScreen::CSplashScreenConfiguration::~CSplashScreenConfiguration(void)
0x18004f57e  nop
0x18004f57f  jmp     short loc_18004F58D
0x18004f581  mov     r13, [rsp+108h+var_D8]
0x18004f586  lea     r15, [r13+8]
0x18004f58a  mov     rsi, r13
0x18004f58d  mov     r14, [r13+10h]
0x18004f591  mov     rbx, [r13+18h]
0x18004f595  mov     rsi, [rsi]
0x18004f598  mov     rdi, [r15]
0x18004f59b  mov     rcx, r14
0x18004f59e  call    ?InternalRelease@?$ComPtr@VCSystemVisuals@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSystemVisuals>::InternalRelease(void)
0x18004f5a3  mov     qword ptr [rsp+108h+var_E8], rbx; int
0x18004f5a8  mov     r9, r15
0x18004f5ab  mov     r8, rsi
0x18004f5ae  lea     rdx, [rdi+18h]
0x18004f5b2  mov     rcx, r14
0x18004f5b5  call    Microsoft__WRL__Details__MakeAndInitialize_CSystemVisuals_CSystemVisuals_HWND_______Windows__Internal__NativeString_Windows__Internal__CoTaskMemPolicy_unsigned_short______CApplicationFrame___const____lambda_11d5a433bb8c6cf8b6eaae2d2d88a5b2____
0x18004f5ba  mov     ebx, eax
0x18004f5bc  test    eax, eax
0x18004f5be  jns     short loc_18004F5E0
0x18004f5c0  mov     rcx, [rsp+108h]; this
0x18004f5c8  mov     r9d, eax; char *
0x18004f5cb  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x18004f5d2  mov     edx, 37Dh; void *
0x18004f5d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f5dc  mov     eax, ebx
0x18004f5de  jmp     short loc_18004F609
0x18004f5e0  mov     rax, [r15]
0x18004f5e3  mov     edx, [rax+2E0h]
0x18004f5e9  test    edx, edx
0x18004f5eb  jz      short loc_18004F607
0x18004f5ed  mov     rax, [r13+10h]
0x18004f5f1  mov     rcx, [rax]
0x18004f5f4  mov     [rcx+0BCh], edx
0x18004f5fa  mov     rax, [r15]
0x18004f5fd  mov     dword ptr [rax+2E0h], 0
0x18004f607  xor     eax, eax
0x18004f609  mov     rcx, [rsp+108h+var_48]
0x18004f611  xor     rcx, rsp; StackCookie
0x18004f614  call    __security_check_cookie
0x18004f619  add     rsp, 0D8h
0x18004f620  pop     r15
0x18004f622  pop     r14
0x18004f624  pop     r13
0x18004f626  pop     rdi
0x18004f627  pop     rsi
0x18004f628  pop     rbx
0x18004f629  retn
0x18004f62a  mov     r9d, eax; char *
0x18004f62d  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x18004f634  mov     edx, 377h; void *
0x18004f639  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004f63e  mov     r9d, eax; char *
0x18004f641  lea     r8, aPcshellShellAp_1; "pcshell\\shell\\applicationframe\\frame"...
0x18004f648  mov     edx, 378h; void *
0x18004f64d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
