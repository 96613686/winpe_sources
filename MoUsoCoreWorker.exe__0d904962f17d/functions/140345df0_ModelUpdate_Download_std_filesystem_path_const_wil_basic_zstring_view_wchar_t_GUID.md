# ModelUpdate::Download(std::filesystem::path const &,wil::basic_zstring_view<wchar_t>,_GUID *)

- ea: `0x140345df0`
- end: `0x140346340`
- name: `?Download@ModelUpdate@@AEAA?AV?$optional@J@std@@AEBVpath@filesystem@3@V?$basic_zstring_view@_W@wil@@PEAU_GUID@@@Z`
- size: `1360`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140345bb0`

## callees

- `0x1400413a8`
- `0x1400430dc`
- `0x140045404`
- `0x1400a593c`
- `0x1400b22e4`
- `0x1400c695c`
- `0x1400d697c`
- `0x14017d9b8`
- `0x1401a2e3c`
- `0x1401a2e84`
- `0x140345df0`
- `0x140346348`
- `0x140346458`
- `0x140379070`
- `0x1403790d8`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140345e4d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140345e4d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1403461d8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140346263`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1403461d8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140346263`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1403460f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1403461a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140346201`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1403460f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1403461a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140346201`

## string_xrefs

- `0x14034629d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x14034614a`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\ModelUpdate.cpp`
- `0x14034617f`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\ModelUpdate.cpp`
- `0x1403462ba`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\ModelUpdate.cpp`
- `0x1403462cf`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\ModelUpdate.cpp`
- `0x1403462eb`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\ModelUpdate.cpp`
- `0x1403462ff`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\ModelUpdate.cpp`
- `0x140346313`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\signalupdater\ModelUpdate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall ModelUpdate::Download(__int64 a1, __int64 a2, void *a3, __int64 a4, GUID *a5)
{
  __int64 v6; // r15
  __int64 v7; // r14
  HRESULT v8; // eax
  int v9; // eax
  _QWORD *v10; // rbx
  unsigned __int64 v11; // rsi
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  __int64 v17; // r13
  __int64 v18; // rbx
  _BYTE *v19; // r12
  int v20; // eax
  bool v21; // zf
  int v22; // eax
  int v24; // eax
  wil *v25; // rcx
  int v26; // [rsp+20h] [rbp-D8h]
  int v27; // [rsp+20h] [rbp-D8h]
  unsigned int v28; // [rsp+20h] [rbp-D8h]
  __int128 v30; // [rsp+40h] [rbp-B8h] BYREF
  __int128 v31; // [rsp+50h] [rbp-A8h]
  __int128 v32; // [rsp+60h] [rbp-98h] BYREF
  __int64 v33; // [rsp+70h] [rbp-88h]
  __int64 v34; // [rsp+78h] [rbp-80h]
  char v35; // [rsp+80h] [rbp-78h] BYREF
  _QWORD *v36; // [rsp+88h] [rbp-70h] BYREF
  int v37; // [rsp+90h] [rbp-68h] BYREF
  _BYTE Src[32]; // [rsp+98h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  *(_QWORD *)&v30 = a4;
  v6 = a2;
  v7 = a1;
  *(_QWORD *)&v31 = a1;
  v34 = 1;
  v33 = a1;
  v8 = CoInitializeEx(0, 0);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1284,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v8,
      v27);
  v36 = 0;
  ModelUpdate::CreateJob(retaddr, &v36);
  v35 = 0;
  v37 = 0;
  *a5 = GUID_NULL;
  std::filesystem::operator/(Src, (void *)(v7 + 488), a3);
  try
  {
    v9 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v36 + 232LL))(v36, 7200);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x201,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\ModelUpdate.cpp",
        (const char *)(unsigned int)v9,
        v27);
    v10 = operator new(0x30u);
    *v10 = &CNotifyInterface::`vftable';
    v10[1] = &v35;
    v10[2] = &v37;
    *((_DWORD *)v10 + 6) = 0;
    v10[4] = v7 + 112;
    v11 = v7 + 184;
    v10[5] = v7 + 184;
    *(_QWORD *)&v32 = v10;
    ((void (__fastcall *)(_QWORD *))_AddRef___implements_delegate_U__AsyncOperationCompletedHandler_UWisePredictor_MachineLearning_AI_WindowsUdk_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UWisePredictor_MachineLearning_AI_WindowsUdk_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UWisePredictor_MachineLearning_AI_WindowsUdk_winrt___234_I_Z__impl_winrt__UEAAIXZ)(v10);
    v12 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))(*v36 + 200LL))(v36, v10);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C3,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\ModelUpdate.cpp",
        (const char *)(unsigned int)v12,
        v27);
    v13 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(*v36 + 184LL))(v36, 3);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C6,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\ModelUpdate.cpp",
        (const char *)(unsigned int)v13,
        v27);
    v30 = *(_OWORD *)v30;
    v28 = (unsigned int)a3;
    ModelUpdate::AddFileWithRanges(v14, &v36, Src, &v30);
    v15 = (*(__int64 (__fastcall **)(_QWORD *, GUID *))(*v36 + 80LL))(v36, a5);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CB,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\ModelUpdate.cpp",
        (const char *)(unsigned int)v15,
        (int)a3);
    v16 = (*(__int64 (__fastcall **)(_QWORD *))(*v36 + 56LL))(v36);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CE,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\ModelUpdate.cpp",
        (const char *)(unsigned int)v16,
        (int)a3);
    (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
  }
  catch ( ... )
  {
    v24 = (*(__int64 (__fastcall **)(_QWORD *))(*v36 + 64LL))(v36);
    v25 = retaddr;
    if ( v24 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1D2,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\ModelUpdate.cpp",
        (const char *)(unsigned int)v24,
        v26);
    *(_DWORD *)a2 = wil::ResultFromCaughtException(v25);
    *(_BYTE *)(a2 + 4) = 1;
    std::wstring::~wstring(Src);
    if ( v36 )
      (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
    v7 = v31;
    v6 = a2;
    goto LABEL_40;
  }
  v30 = v11;
  if ( (unsigned int)mtx_do_lock(v11, 0) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(v11 + 76) == 0x7FFFFFFF )
  {
    *(_DWORD *)(v11 + 76) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  BYTE8(v30) = 1;
  *(_QWORD *)&v32 = &v35;
  *((_QWORD *)&v32 + 1) = v7;
  v31 = v32;
  v17 = std::_To_absolute_time<__int64,std::ratio<1,1>>(&v32, &ModelUpdate::sc_jobProgressTimeout);
  v18 = *((_QWORD *)&v31 + 1);
  v19 = (_BYTE *)v31;
  while ( !*v19
       && !*(_BYTE *)(v18 + 264)
       && !*(_BYTE *)(v18 + 265)
       && (unsigned int)std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
                          v7 + 112,
                          &v30,
                          v17) != 1 )
    ;
  if ( v35 )
  {
    v20 = v37;
    if ( v37 >= 0 )
    {
      UpdateDatabase::UpdateSignalState(*(_QWORD *)(v7 + 384), v7, 1);
      v20 = v37;
    }
    *(_DWORD *)v6 = v20;
    *(_BYTE *)(v6 + 4) = 1;
    v21 = (*(_DWORD *)(v11 + 76))-- == 1;
    if ( v21 )
    {
      *(_DWORD *)(v11 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v11 + 16));
    }
    std::wstring::~wstring(Src);
    if ( v36 )
      (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
  }
  else
  {
    v22 = (*(__int64 (__fastcall **)(_QWORD *))(*v36 + 64LL))(v36);
    if ( v22 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1E0,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\ModelUpdate.cpp",
        (const char *)(unsigned int)v22,
        v28);
    if ( *(_BYTE *)(v7 + 264) || *(_BYTE *)(v7 + 265) )
    {
      *(_BYTE *)(v6 + 4) = 0;
      v21 = (*(_DWORD *)(v11 + 76))-- == 1;
      if ( v21 )
      {
        *(_DWORD *)(v11 + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v11 + 16));
      }
      std::wstring::~wstring(Src);
      if ( v36 )
        (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
    }
    else
    {
      *(_DWORD *)v6 = wil::details::in1diag3::Return_Win32(
                        retaddr,
                        (void *)0x1E7,
                        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\signalupdater\\ModelUpdate.cpp",
                        (const char *)0x5B4,
                        v28);
      *(_BYTE *)(v6 + 4) = 1;
      v21 = (*(_DWORD *)(v11 + 76))-- == 1;
      if ( v21 )
      {
        *(_DWORD *)(v11 + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v11 + 16));
      }
      std::wstring::~wstring(Src);
      if ( v36 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v36 + 16LL))(v36, *v36);
    }
  }
LABEL_40:
  CoUninitialize();
  *(_WORD *)(v7 + 264) = 0;
  return v6;
}

```

## disassembly

```asm
0x140345df0  push    rbx
0x140345df2  push    rsi
0x140345df3  push    rdi
0x140345df4  push    r12
0x140345df6  push    r13
0x140345df8  push    r14
0x140345dfa  push    r15
0x140345dfc  sub     rsp, 0C0h
0x140345e03  mov     rax, cs:__security_cookie
0x140345e0a  xor     rax, rsp
0x140345e0d  mov     [rsp+0F8h+var_40], rax
0x140345e15  mov     qword ptr [rsp+0F8h+var_B8], r9
0x140345e1a  mov     r12, r8
0x140345e1d  mov     r15, rdx
0x140345e20  mov     r14, rcx
0x140345e23  mov     qword ptr [rsp+0F8h+var_A8], rcx
0x140345e28  mov     [rsp+0F8h+var_C0], rdx
0x140345e2d  mov     r13, [rsp+0F8h+arg_20]
0x140345e35  xor     edi, edi
0x140345e37  xorps   xmm0, xmm0
0x140345e3a  movups  [rsp+0F8h+var_88], xmm0
0x140345e3f  mov     qword ptr [rsp+0F8h+var_88], rcx
0x140345e44  mov     byte ptr [rsp+0F8h+var_88+8], 1
0x140345e49  xor     edx, edx; dwCoInit
0x140345e4b  xor     ecx, ecx; pvReserved
0x140345e4d  call    cs:__imp_CoInitializeEx
0x140345e53  mov     rcx, [rsp+0F8h]; this
0x140345e5b  test    eax, eax
0x140345e5d  js      loc_14034629A
0x140345e63  mov     [rsp+0F8h+var_C8], 1
0x140345e68  mov     [rsp+0F8h+var_70], rdi
0x140345e70  lea     rdx, [rsp+0F8h+var_70]
0x140345e78  call    ?CreateJob@ModelUpdate@@AEAA?AV?$com_ptr_t@UIBackgroundCopyJob@@Uerr_exception_policy@wil@@@wil@@XZ; ModelUpdate::CreateJob(void)
0x140345e7d  nop
0x140345e7e  mov     [rsp+0F8h+var_78], dil
0x140345e86  mov     [rsp+0F8h+var_68], edi
0x140345e8d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140345e94  movdqu  xmmword ptr [r13+0], xmm0
0x140345e9a  lea     rdx, [r14+1E8h]; void *
0x140345ea1  mov     r8, r12; void *
0x140345ea4  lea     rcx, [rsp+0F8h+Src]; Src
0x140345eac  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x140345eb1  nop
0x140345eb2  mov     rcx, [rsp+0F8h+var_70]
0x140345eba  mov     rax, [rcx]
0x140345ebd  mov     edx, 1C20h
0x140345ec2  mov     rax, [rax+0E8h]
0x140345ec9  call    _guard_dispatch_icall
0x140345ece  test    eax, eax
0x140345ed0  js      loc_1403462AF
0x140345ed6  mov     ecx, 30h ; '0'; Size
0x140345edb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140345ee0  mov     rbx, rax
0x140345ee3  lea     rax, ??_7CNotifyInterface@@6B@; const CNotifyInterface::`vftable'
0x140345eea  mov     [rbx], rax
0x140345eed  lea     rax, [rsp+0F8h+var_78]
0x140345ef5  mov     [rbx+8], rax
0x140345ef9  lea     rax, [rsp+0F8h+var_68]
0x140345f01  mov     [rbx+10h], rax
0x140345f05  mov     [rbx+18h], edi
0x140345f08  lea     rax, [r14+70h]
0x140345f0c  mov     [rbx+20h], rax
0x140345f10  lea     rsi, [r14+0B8h]
0x140345f17  mov     [rbx+28h], rsi
0x140345f1b  mov     qword ptr [rsp+0F8h+var_98], rbx
0x140345f20  mov     rcx, rbx
0x140345f23  mov     rax, cs:off_1403DB128
0x140345f2a  call    _guard_dispatch_icall
0x140345f2f  nop
0x140345f30  mov     rcx, [rsp+0F8h+var_70]
0x140345f38  mov     rax, [rcx]
0x140345f3b  mov     rdx, rbx
0x140345f3e  mov     rax, [rax+0C8h]
0x140345f45  call    _guard_dispatch_icall
0x140345f4a  mov     rcx, [rsp+0F8h]; this
0x140345f52  test    eax, eax
0x140345f54  js      loc_1403462CC
0x140345f5a  mov     rcx, [rsp+0F8h+var_70]
0x140345f62  mov     rax, [rcx]
0x140345f65  mov     edx, 3
0x140345f6a  mov     rax, [rax+0B8h]
0x140345f71  call    _guard_dispatch_icall
0x140345f76  test    eax, eax
0x140345f78  js      loc_1403462E0
0x140345f7e  mov     rax, qword ptr [rsp+0F8h+var_B8]
0x140345f83  movaps  xmm0, xmmword ptr [rax]
0x140345f86  movdqa  [rsp+0F8h+var_B8], xmm0
0x140345f8c  mov     qword ptr [rsp+0F8h+var_D8], r12; int
0x140345f91  lea     r9, [rsp+0F8h+var_B8]
0x140345f96  lea     r8, [rsp+0F8h+Src]
0x140345f9e  lea     rdx, [rsp+0F8h+var_70]
0x140345fa6  call    ?AddFileWithRanges@ModelUpdate@@AEAAXAEAV?$com_ptr_t@UIBackgroundCopyJob@@Uerr_exception_policy@wil@@@wil@@AEBVpath@filesystem@std@@V?$basic_zstring_view@_W@3@1@Z; ModelUpdate::AddFileWithRanges(wil::com_ptr_t<IBackgroundCopyJob,wil::err_exception_policy> &,std::filesystem::path const &,wil::basic_zstring_view<wchar_t>,std::filesystem::path const &)
0x140345fab  mov     rcx, [rsp+0F8h+var_70]
0x140345fb3  mov     rax, [rcx]
0x140345fb6  mov     rdx, r13
0x140345fb9  mov     rax, [rax+50h]
0x140345fbd  call    _guard_dispatch_icall
0x140345fc2  mov     rcx, [rsp+0F8h]; this
0x140345fca  test    eax, eax
0x140345fcc  js      loc_1403462FC
0x140345fd2  mov     rcx, [rsp+0F8h+var_70]
0x140345fda  mov     rax, [rcx]
0x140345fdd  mov     rax, [rax+38h]
0x140345fe1  call    _guard_dispatch_icall
0x140345fe6  mov     rcx, [rsp+0F8h]; this
0x140345fee  test    eax, eax
0x140345ff0  js      loc_140346310
0x140345ff6  mov     rax, [rbx]
0x140345ff9  mov     rcx, rbx
0x140345ffc  mov     rax, [rax+10h]
0x140346000  call    _guard_dispatch_icall
0x140346005  nop
0x140346006  xorps   xmm0, xmm0
0x140346009  movups  [rsp+0F8h+var_B8], xmm0
0x14034600e  mov     qword ptr [rsp+0F8h+var_B8], rsi
0x140346013  mov     byte ptr [rsp+0F8h+var_B8+8], dil
0x140346018  xor     edx, edx
0x14034601a  mov     rcx, rsi
0x14034601d  call    mtx_do_lock
0x140346022  test    eax, eax
0x140346024  jnz     loc_140346325
0x14034602a  mov     eax, [rsi+4Ch]
0x14034602d  cmp     eax, 7FFFFFFFh
0x140346032  jz      loc_140346330
0x140346038  mov     byte ptr [rsp+0F8h+var_B8+8], 1
0x14034603d  lea     rax, [rsp+0F8h+var_78]
0x140346045  mov     qword ptr [rsp+0F8h+var_98], rax
0x14034604a  mov     qword ptr [rsp+0F8h+var_98+8], r14
0x14034604f  movaps  xmm0, [rsp+0F8h+var_98]
0x140346054  movdqa  [rsp+0F8h+var_A8], xmm0
0x14034605a  lea     rdx, ?sc_jobProgressTimeout@ModelUpdate@@0V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@B; std::chrono::duration<__int64,std::ratio<1,1>> const ModelUpdate::sc_jobProgressTimeout
0x140346061  lea     rcx, [rsp+0F8h+var_98]
0x140346066  call    ??$_To_absolute_time@_JU?$ratio@$00$00@std@@@std@@YA?A_PAEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@0@@Z
0x14034606b  mov     r13, rax
0x14034606e  mov     rbx, qword ptr [rsp+0F8h+var_A8+8]
0x140346073  mov     r12, qword ptr [rsp+0F8h+var_A8]
0x140346078  cmp     [r12], dil
0x14034607c  jnz     short loc_1403460A6
0x14034607e  cmp     [rbx+108h], dil
0x140346085  jnz     short loc_1403460A6
0x140346087  cmp     [rbx+109h], dil
0x14034608e  jnz     short loc_1403460A6
0x140346090  mov     r8, r13
0x140346093  lea     rdx, [rsp+0F8h+var_B8]
0x140346098  lea     rcx, [r14+70h]
0x14034609c  call    ??$wait_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@condition_variable@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vmutex@std@@@1@AEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z; std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::unique_lock<std::mutex> &,std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)
0x1403460a1  cmp     eax, 1
0x1403460a4  jnz     short loc_140346078
0x1403460a6  cmp     [rsp+0F8h+var_78], dil
0x1403460ae  jz      short loc_140346127
0x1403460b0  mov     eax, [rsp+0F8h+var_68]
0x1403460b7  test    eax, eax
0x1403460b9  js      short loc_1403460D7
0x1403460bb  mov     r8d, 1
0x1403460c1  mov     rdx, r14
0x1403460c4  mov     rcx, [r14+180h]
0x1403460cb  call    ?UpdateSignalState@UpdateDatabase@@QEAAXAEBVUpdate@@W4SignalUpdateState@SystemInterface@@@Z; UpdateDatabase::UpdateSignalState(Update const &,SystemInterface::SignalUpdateState)
0x1403460d0  mov     eax, [rsp+0F8h+var_68]
0x1403460d7  mov     [r15], eax
0x1403460da  mov     byte ptr [r15+4], 1
0x1403460df  sub     dword ptr [rsi+4Ch], 1
0x1403460e3  jnz     short loc_1403460F7
0x1403460e5  mov     dword ptr [rsi+48h], 0FFFFFFFFh
0x1403460ec  lea     rcx, [rsi+10h]; SRWLock
0x1403460f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1403460f6  nop
0x1403460f7  lea     rcx, [rsp+0F8h+Src]
0x1403460ff  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140346104  nop
0x140346105  mov     rcx, [rsp+0F8h+var_70]
0x14034610d  test    rcx, rcx
0x140346110  jz      loc_140346263
0x140346116  mov     rax, [rcx]
0x140346119  mov     rax, [rax+10h]
0x14034611d  call    _guard_dispatch_icall
0x140346122  jmp     loc_140346263
0x140346127  mov     rcx, [rsp+0F8h+var_70]
0x14034612f  mov     rax, [rcx]
0x140346132  mov     rax, [rax+40h]
0x140346136  call    _guard_dispatch_icall
0x14034613b  mov     rcx, [rsp+0F8h]; this
0x140346143  test    eax, eax
0x140346145  jns     short loc_14034615B
0x140346147  mov     r9d, eax; char *
0x14034614a  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140346151  mov     edx, 1E0h; void *
0x140346156  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14034615b  cmp     [r14+108h], dil
0x140346162  jnz     loc_1403461EC
0x140346168  cmp     [r14+109h], dil
0x14034616f  jnz     short loc_1403461EC
0x140346171  mov     rcx, [rsp+0F8h]; this
0x140346179  mov     r9d, 5B4h; char *
0x14034617f  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140346186  mov     edx, 1E7h; void *
0x14034618b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140346190  mov     [r15], eax
0x140346193  mov     byte ptr [r15+4], 1
0x140346198  sub     dword ptr [rsi+4Ch], 1
0x14034619c  jnz     short loc_1403461B0
0x14034619e  mov     dword ptr [rsi+48h], 0FFFFFFFFh
0x1403461a5  lea     rcx, [rsi+10h]; SRWLock
0x1403461a9  call    cs:__imp_ReleaseSRWLockExclusive
0x1403461af  nop
0x1403461b0  lea     rcx, [rsp+0F8h+Src]
0x1403461b8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403461bd  nop
0x1403461be  mov     rcx, [rsp+0F8h+var_70]
0x1403461c6  test    rcx, rcx
0x1403461c9  jz      short loc_1403461D8
0x1403461cb  mov     rdx, [rcx]
0x1403461ce  mov     rax, [rdx+10h]
0x1403461d2  call    _guard_dispatch_icall
0x1403461d7  nop
0x1403461d8  call    cs:__imp_CoUninitialize
0x1403461de  nop
0x1403461df  mov     [r14+108h], di
0x1403461e7  jmp     loc_140346274
0x1403461ec  mov     [r15+4], dil
0x1403461f0  sub     dword ptr [rsi+4Ch], 1
0x1403461f4  jnz     short loc_140346208
0x1403461f6  mov     dword ptr [rsi+48h], 0FFFFFFFFh
0x1403461fd  lea     rcx, [rsi+10h]; SRWLock
0x140346201  call    cs:__imp_ReleaseSRWLockExclusive
0x140346207  nop
0x140346208  lea     rcx, [rsp+0F8h+Src]
0x140346210  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140346215  nop
0x140346216  mov     rcx, [rsp+0F8h+var_70]
0x14034621e  test    rcx, rcx
0x140346221  jz      short loc_140346230
0x140346223  mov     rax, [rcx]
0x140346226  mov     rax, [rax+10h]
0x14034622a  call    _guard_dispatch_icall
0x14034622f  nop
0x140346230  jmp     short loc_1403461D8
0x140346232  lea     rcx, [rsp+0F8h+Src]
0x14034623a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14034623f  nop
0x140346240  mov     rcx, [rsp+0F8h+var_70]
0x140346248  test    rcx, rcx
0x14034624b  jz      short loc_140346259
0x14034624d  mov     rax, [rcx]
0x140346250  mov     rax, [rax+10h]
0x140346254  call    _guard_dispatch_icall
0x140346259  mov     r14, qword ptr [rsp+0F8h+var_A8]
0x14034625e  mov     r15, [rsp+0F8h+var_C0]
0x140346263  call    cs:__imp_CoUninitialize
0x140346269  nop
0x14034626a  mov     word ptr [r14+108h], 0
0x140346274  mov     rax, r15
0x140346277  mov     rcx, [rsp+0F8h+var_40]
0x14034627f  xor     rcx, rsp; StackCookie
0x140346282  call    __security_check_cookie
0x140346287  add     rsp, 0C0h
0x14034628e  pop     r15
0x140346290  pop     r14
0x140346292  pop     r13
0x140346294  pop     r12
0x140346296  pop     rdi
0x140346297  pop     rsi
0x140346298  pop     rbx
0x140346299  retn
0x14034629a  mov     r9d, eax; char *
0x14034629d  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1403462a4  mov     edx, 1284h; void *
0x1403462a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1403462af  mov     rcx, [rsp+0F8h]; this
0x1403462b7  mov     r9d, eax; char *
0x1403462ba  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403462c1  mov     edx, 201h; void *
0x1403462c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1403462cc  mov     r9d, eax; char *
0x1403462cf  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403462d6  mov     edx, 1C3h; void *
0x1403462db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1403462e0  mov     rcx, [rsp+0F8h]; this
0x1403462e8  mov     r9d, eax; char *
0x1403462eb  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403462f2  mov     edx, 1C6h; void *
0x1403462f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1403462fc  mov     r9d, eax; char *
0x1403462ff  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140346306  mov     edx, 1CBh; void *
0x14034630b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140346310  mov     r9d, eax; char *
0x140346313  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14034631a  mov     edx, 1CEh; void *
0x14034631f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140346325  mov     ecx, 5; int
0x14034632a  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x140346330  dec     eax
0x140346332  mov     [rsi+4Ch], eax
0x140346335  mov     ecx, 6; int
0x14034633a  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
