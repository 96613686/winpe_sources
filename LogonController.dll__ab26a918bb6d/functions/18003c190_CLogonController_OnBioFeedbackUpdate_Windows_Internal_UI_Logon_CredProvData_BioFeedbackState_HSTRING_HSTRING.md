# CLogonController::OnBioFeedbackUpdate(Windows::Internal::UI::Logon::CredProvData::BioFeedbackState,HSTRING__ *,HSTRING__ *)

- ea: `0x18003c190`
- end: `0x18003c564`
- name: `?OnBioFeedbackUpdate@CLogonController@@UEAAJW4BioFeedbackState@CredProvData@Logon@UI@Internal@Windows@@PEAUHSTRING__@@1@Z`
- size: `980`
- prototype: `int __high(enum Windows::Internal::UI::Logon::CredProvData::BioFeedbackState, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18000df10`
- `0x18003c190`
- `0x18003c56c`
- `0x18003c5d0`
- `0x18005d488`
- `0x18006f0d8`
- `0x180073aac`
- `0x180074374`
- `0x180074530`
- `0x18009d010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x18003c1d6`
- `KERNEL32!ReleaseSRWLockShared` at `0x18003c1d6`
- `KERNEL32!AcquireSRWLockShared` at `0x18003c1c1`
- `KERNEL32!AcquireSRWLockShared` at `0x18003c1c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003c2c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003c2fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003c2c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003c2fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c31a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c2e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c31a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLogonController::OnBioFeedbackUpdate(__int64 a1, unsigned int a2, HSTRING a3, HSTRING a4)
{
  RTL_SRWLOCK *v8; // rbx
  char v9; // r14
  int v10; // eax
  unsigned int v11; // ebx
  struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *v12; // rcx
  _QWORD *v14; // rax
  _QWORD *v15; // rbx
  HRESULT v16; // eax
  unsigned int v17; // edi
  HSTRING v18; // rcx
  HRESULT v19; // eax
  HSTRING v20; // rdi
  HSTRING v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  unsigned int v24; // esi
  int v25; // eax
  struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *v26; // rcx
  struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *v27; // rcx
  struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *v28; // rcx
  int v29; // [rsp+20h] [rbp-50h]
  int v30; // [rsp+20h] [rbp-50h]
  struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *v31; // [rsp+30h] [rbp-40h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-38h] BYREF
  HSTRING v33; // [rsp+40h] [rbp-30h] BYREF
  _QWORD *v34; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v35[32]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v37; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int v38; // [rsp+B8h] [rbp+48h] BYREF

  v38 = a2;
  v8 = (RTL_SRWLOCK *)(a1 + 168);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 168));
  v9 = *(_BYTE *)(a1 + 192);
  if ( v8 )
    ReleaseSRWLockShared(v8);
  v37 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 32LL) + 48LL))(
          *(_QWORD *)(a1 + 64) + 32LL,
          &v37);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93A,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v10,
      v29);
    return v11;
  }
  if ( (v37 & 4) == 0 )
    return 0;
  if ( !v9 )
  {
    v31 = 0;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v31);
    if ( (int)CLogonController::_EnsureBioFeedbackUX((RTL_SRWLOCK *)(a1 - 80), &v31) >= 0 )
    {
      if ( v31 )
      {
        v25 = (*(__int64 (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *, _QWORD, HSTRING, HSTRING))(*(_QWORD *)v31 + 56LL))(
                v31,
                a2,
                a3,
                a4);
        v11 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x95D,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
            (const char *)(unsigned int)v25,
            v29);
          v26 = v31;
          if ( v31 )
          {
            v31 = 0;
            (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *))(*(_QWORD *)v26 + 16LL))(v26);
          }
          return v11;
        }
      }
    }
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v31);
    return 0;
  }
  v31 = 0;
  if ( (***(int (__fastcall ****)(_QWORD, GUID *, struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX **))(a1 + 320))(
         *(_QWORD *)(a1 + 320),
         &GUID_963ffa57_1043_4961_8bf0_d3966cd5b833,
         &v31) < 0 )
  {
LABEL_7:
    v12 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return 0;
  }
  v14 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v15 = v14;
  if ( v14 )
  {
    v14[1] = 0;
    *v14 = &CRefCountedObject<Windows::Internal::String>::`vftable';
    *((_DWORD *)v14 + 4) = 0;
  }
  else
  {
    v15 = 0;
  }
  v34 = v15;
  if ( v15 )
    (*(void (__fastcall **)(_QWORD *))(*v15 + 8LL))(v15);
  newString = 0;
  v16 = WindowsDuplicateString(a3, &newString);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x94C,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v16,
      v29);
    if ( v15 )
      (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
    v28 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *))(*(_QWORD *)v28 + 16LL))(v28);
    }
    return v17;
  }
  v18 = (HSTRING)v15[1];
  v15[1] = newString;
  WindowsDeleteString(v18);
  CreateRefCountedObj<Windows::Internal::String,>(&newString);
  v33 = 0;
  v19 = WindowsDuplicateString(a4, &v33);
  v17 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x94E,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v19,
      v29);
    if ( newString )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)newString + 16LL))(newString);
    if ( v15 )
      (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v31);
    return v17;
  }
  v20 = newString;
  v21 = (HSTRING)*((_QWORD *)newString + 1);
  *((_QWORD *)newString + 1) = v33;
  WindowsDeleteString(v21);
  lambda_5b9d562f47ffd18fb7fa4c1718717f87_::_lambda_5b9d562f47ffd18fb7fa4c1718717f87_(
    (unsigned int)v35,
    (unsigned int)&v31,
    (unsigned int)&v38,
    (unsigned int)&v34,
    (__int64)&newString);
  v23 = Windows::Internal::ComTaskPool::QueueTask__lambda_5b9d562f47ffd18fb7fa4c1718717f87____(
          v22,
          258,
          *(unsigned int *)(a1 + 128),
          v35);
  v24 = v23;
  if ( v23 >= 0 )
  {
    lambda_5b9d562f47ffd18fb7fa4c1718717f87_::__lambda_5b9d562f47ffd18fb7fa4c1718717f87_(v35);
    if ( v20 )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v20 + 16LL))(v20);
    if ( v15 )
      (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
    goto LABEL_7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x954,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
    (const char *)(unsigned int)v23,
    v30);
  lambda_5b9d562f47ffd18fb7fa4c1718717f87_::__lambda_5b9d562f47ffd18fb7fa4c1718717f87_(v35);
  if ( v20 )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v15 )
    (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
  v27 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *))(*(_QWORD *)v27 + 16LL))(v27);
  }
  return v24;
}

```

## disassembly

```asm
0x18003c190  mov     [rsp-38h+arg_10], rbx
0x18003c195  mov     [rsp-38h+arg_8], edx
0x18003c199  push    rbp
0x18003c19a  push    rsi
0x18003c19b  push    rdi
0x18003c19c  push    r12
0x18003c19e  push    r13
0x18003c1a0  push    r14
0x18003c1a2  push    r15
0x18003c1a4  mov     rbp, rsp
0x18003c1a7  sub     rsp, 70h
0x18003c1ab  mov     r13, r9
0x18003c1ae  mov     r12, r8
0x18003c1b1  mov     r15d, edx
0x18003c1b4  mov     rsi, rcx
0x18003c1b7  lea     rbx, [rcx+0A8h]
0x18003c1be  mov     rcx, rbx; SRWLock
0x18003c1c1  call    cs:__imp_AcquireSRWLockShared
0x18003c1c7  mov     r14b, [rsi+0C0h]
0x18003c1ce  test    rbx, rbx
0x18003c1d1  jz      short loc_18003C1DC
0x18003c1d3  mov     rcx, rbx; SRWLock
0x18003c1d6  call    cs:__imp_ReleaseSRWLockShared
0x18003c1dc  mov     [rbp+arg_0], 0
0x18003c1e3  mov     rcx, [rsi+40h]
0x18003c1e7  add     rcx, 20h ; ' '
0x18003c1eb  mov     rax, [rcx]
0x18003c1ee  lea     rdx, [rbp+arg_0]
0x18003c1f2  mov     rax, [rax+30h]
0x18003c1f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1fb  mov     ebx, eax
0x18003c1fd  test    eax, eax
0x18003c1ff  js      loc_18003C4A9
0x18003c205  test    byte ptr [rbp+arg_0], 4
0x18003c209  jz      short loc_18003C257
0x18003c20b  test    r14b, r14b
0x18003c20e  jz      loc_18003C39E
0x18003c214  xor     r14d, r14d
0x18003c217  mov     [rbp+var_40], r14
0x18003c21b  mov     rcx, [rsi+140h]
0x18003c222  mov     rax, [rcx]
0x18003c225  lea     r8, [rbp+var_40]
0x18003c229  lea     rdx, _GUID_963ffa57_1043_4961_8bf0_d3966cd5b833
0x18003c230  mov     rax, [rax]
0x18003c233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c238  nop
0x18003c239  test    eax, eax
0x18003c23b  jns     short loc_18003C271
0x18003c23d  mov     rcx, [rbp+var_40]
0x18003c241  test    rcx, rcx
0x18003c244  jz      short loc_18003C257
0x18003c246  mov     [rbp+var_40], r14
0x18003c24a  mov     rax, [rcx]
0x18003c24d  mov     rax, [rax+10h]
0x18003c251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c256  nop
0x18003c257  xor     eax, eax
0x18003c259  mov     rbx, [rsp+70h+arg_10]
0x18003c261  add     rsp, 70h
0x18003c265  pop     r15
0x18003c267  pop     r14
0x18003c269  pop     r13
0x18003c26b  pop     r12
0x18003c26d  pop     rdi
0x18003c26e  pop     rsi
0x18003c26f  pop     rbp
0x18003c270  retn
0x18003c271  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003c278  mov     ecx, 18h; unsigned __int64
0x18003c27d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003c282  mov     rbx, rax
0x18003c285  test    rax, rax
0x18003c288  jz      loc_18003C396
0x18003c28e  mov     [rax+8], r14
0x18003c292  lea     rax, ??_7?$CRefCountedObject@VString@Internal@Windows@@@@6B@; const CRefCountedObject<Windows::Internal::String>::`vftable'
0x18003c299  mov     [rbx], rax
0x18003c29c  mov     [rbx+10h], r14d
0x18003c2a0  mov     [rbp+var_28], rbx
0x18003c2a4  test    rbx, rbx
0x18003c2a7  jz      short loc_18003C2B9
0x18003c2a9  mov     rax, [rbx]
0x18003c2ac  mov     rcx, rbx
0x18003c2af  mov     rax, [rax+8]
0x18003c2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c2b8  nop
0x18003c2b9  mov     [rbp+newString], r14
0x18003c2bd  lea     rdx, [rbp+newString]; newString
0x18003c2c1  mov     rcx, r12; string
0x18003c2c4  call    cs:__imp_WindowsDuplicateString
0x18003c2ca  mov     edi, eax
0x18003c2cc  test    eax, eax
0x18003c2ce  js      loc_18003C4C6
0x18003c2d4  mov     rcx, [rbx+8]; string
0x18003c2d8  mov     rax, [rbp+newString]
0x18003c2dc  mov     [rbx+8], rax
0x18003c2e0  call    cs:__imp_WindowsDeleteString
0x18003c2e6  lea     rcx, [rbp+newString]
0x18003c2ea  call    ??$CreateRefCountedObj@VString@Internal@Windows@@$$V@@YA?AV?$ComPtr@V?$CRefCountedObject@VString@Internal@Windows@@@@@WRL@Microsoft@@XZ; CreateRefCountedObj<Windows::Internal::String,>(void)
0x18003c2ef  mov     [rbp+var_30], r14
0x18003c2f3  lea     rdx, [rbp+var_30]; newString
0x18003c2f7  mov     rcx, r13; string
0x18003c2fa  call    cs:__imp_WindowsDuplicateString
0x18003c300  mov     edi, eax
0x18003c302  test    eax, eax
0x18003c304  js      loc_18003C515
0x18003c30a  mov     rdi, [rbp+newString]
0x18003c30e  mov     rcx, [rdi+8]; string
0x18003c312  mov     rax, [rbp+var_30]
0x18003c316  mov     [rdi+8], rax
0x18003c31a  call    cs:__imp_WindowsDeleteString
0x18003c320  lea     rax, [rbp+newString]
0x18003c324  mov     qword ptr [rsp+70h+var_50], rax; int
0x18003c329  lea     r9, [rbp+var_28]
0x18003c32d  lea     r8, [rbp+arg_8]
0x18003c331  lea     rdx, [rbp+var_40]
0x18003c335  lea     rcx, [rbp+var_20]
0x18003c339  call    _lambda_5b9d562f47ffd18fb7fa4c1718717f87____lambda_5b9d562f47ffd18fb7fa4c1718717f87_
0x18003c33e  lea     r9, [rbp+var_20]
0x18003c342  mov     r8d, [rsi+80h]
0x18003c349  mov     edx, 102h
0x18003c34e  call    Windows__Internal__ComTaskPool__QueueTask__lambda_5b9d562f47ffd18fb7fa4c1718717f87____
0x18003c353  mov     esi, eax
0x18003c355  test    eax, eax
0x18003c357  js      loc_18003C42E
0x18003c35d  lea     rcx, [rbp+var_20]
0x18003c361  call    _lambda_5b9d562f47ffd18fb7fa4c1718717f87_____lambda_5b9d562f47ffd18fb7fa4c1718717f87_
0x18003c366  nop
0x18003c367  test    rdi, rdi
0x18003c36a  jz      short loc_18003C37C
0x18003c36c  mov     rax, [rdi]
0x18003c36f  mov     rcx, rdi
0x18003c372  mov     rax, [rax+10h]
0x18003c376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c37b  nop
0x18003c37c  test    rbx, rbx
0x18003c37f  jz      short loc_18003C391
0x18003c381  mov     rax, [rbx]
0x18003c384  mov     rcx, rbx
0x18003c387  mov     rax, [rax+10h]
0x18003c38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c390  nop
0x18003c391  jmp     loc_18003C23D
0x18003c396  mov     rbx, r14
0x18003c399  jmp     loc_18003C2A0
0x18003c39e  mov     [rbp+var_40], 0
0x18003c3a6  lea     rcx, [rbp+var_40]
0x18003c3aa  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18003c3af  lea     rdx, [rbp+var_40]; struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX **
0x18003c3b3  lea     rcx, [rsi-50h]; this
0x18003c3b7  call    ?_EnsureBioFeedbackUX@CLogonController@@AEAAJPEAPEAUIBioFeedbackUX@Controller@Logon@UI@Internal@Windows@@@Z; CLogonController::_EnsureBioFeedbackUX(Windows::Internal::UI::Logon::Controller::IBioFeedbackUX * *)
0x18003c3bc  test    eax, eax
0x18003c3be  js      loc_18003C49B
0x18003c3c4  mov     rcx, [rbp+var_40]
0x18003c3c8  test    rcx, rcx
0x18003c3cb  jz      loc_18003C49B
0x18003c3d1  mov     rax, [rcx]
0x18003c3d4  mov     r9, r13
0x18003c3d7  mov     r8, r12
0x18003c3da  mov     edx, r15d
0x18003c3dd  mov     rax, [rax+38h]
0x18003c3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3e6  mov     ebx, eax
0x18003c3e8  test    eax, eax
0x18003c3ea  jns     loc_18003C49B
0x18003c3f0  mov     rcx, [rbp+38h]; this
0x18003c3f4  mov     r9d, eax; char *
0x18003c3f7  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003c3fe  mov     edx, 95Dh; void *
0x18003c403  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c408  nop
0x18003c409  mov     rcx, [rbp+var_40]
0x18003c40d  test    rcx, rcx
0x18003c410  jz      short loc_18003C427
0x18003c412  mov     [rbp+var_40], 0
0x18003c41a  mov     rax, [rcx]
0x18003c41d  mov     rax, [rax+10h]
0x18003c421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c426  nop
0x18003c427  mov     eax, ebx
0x18003c429  jmp     loc_18003C259
0x18003c42e  mov     rcx, [rbp+38h]; this
0x18003c432  mov     r9d, esi; char *
0x18003c435  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003c43c  mov     edx, 954h; void *
0x18003c441  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c446  lea     rcx, [rbp+var_20]
0x18003c44a  call    _lambda_5b9d562f47ffd18fb7fa4c1718717f87_____lambda_5b9d562f47ffd18fb7fa4c1718717f87_
0x18003c44f  nop
0x18003c450  test    rdi, rdi
0x18003c453  jz      short loc_18003C465
0x18003c455  mov     rax, [rdi]
0x18003c458  mov     rcx, rdi
0x18003c45b  mov     rax, [rax+10h]
0x18003c45f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c464  nop
0x18003c465  test    rbx, rbx
0x18003c468  jz      short loc_18003C47A
0x18003c46a  mov     rax, [rbx]
0x18003c46d  mov     rcx, rbx
0x18003c470  mov     rax, [rax+10h]
0x18003c474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c479  nop
0x18003c47a  mov     rcx, [rbp+var_40]
0x18003c47e  test    rcx, rcx
0x18003c481  jz      short loc_18003C494
0x18003c483  mov     [rbp+var_40], r14
0x18003c487  mov     rax, [rcx]
0x18003c48a  mov     rax, [rax+10h]
0x18003c48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c493  nop
0x18003c494  mov     eax, esi
0x18003c496  jmp     loc_18003C259
0x18003c49b  lea     rcx, [rbp+var_40]
0x18003c49f  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18003c4a4  jmp     loc_18003C257
0x18003c4a9  mov     rcx, [rbp+38h]; this
0x18003c4ad  mov     r9d, ebx; char *
0x18003c4b0  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003c4b7  mov     edx, 93Ah; void *
0x18003c4bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c4c1  jmp     loc_18003C427
0x18003c4c6  mov     rcx, [rbp+38h]; this
0x18003c4ca  mov     r9d, edi; char *
0x18003c4cd  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003c4d4  mov     edx, 94Ch; void *
0x18003c4d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c4de  nop
0x18003c4df  test    rbx, rbx
0x18003c4e2  jz      short loc_18003C4F4
0x18003c4e4  mov     rax, [rbx]
0x18003c4e7  mov     rcx, rbx
0x18003c4ea  mov     rax, [rax+10h]
0x18003c4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4f3  nop
0x18003c4f4  mov     rcx, [rbp+var_40]
0x18003c4f8  test    rcx, rcx
0x18003c4fb  jz      short loc_18003C50E
0x18003c4fd  mov     [rbp+var_40], r14
0x18003c501  mov     rax, [rcx]
0x18003c504  mov     rax, [rax+10h]
0x18003c508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c50d  nop
0x18003c50e  mov     eax, edi
0x18003c510  jmp     loc_18003C259
0x18003c515  mov     rcx, [rbp+38h]; this
0x18003c519  mov     r9d, edi; char *
0x18003c51c  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003c523  mov     edx, 94Eh; void *
0x18003c528  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c52d  nop
0x18003c52e  mov     rcx, [rbp+newString]
0x18003c532  test    rcx, rcx
0x18003c535  jz      short loc_18003C544
0x18003c537  mov     rax, [rcx]
0x18003c53a  mov     rax, [rax+10h]
0x18003c53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c543  nop
0x18003c544  test    rbx, rbx
0x18003c547  jz      short loc_18003C559
0x18003c549  mov     rax, [rbx]
0x18003c54c  mov     rcx, rbx
0x18003c54f  mov     rax, [rax+10h]
0x18003c553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c558  nop
0x18003c559  lea     rcx, [rbp+var_40]
0x18003c55d  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18003c562  jmp     short loc_18003C50E
```
