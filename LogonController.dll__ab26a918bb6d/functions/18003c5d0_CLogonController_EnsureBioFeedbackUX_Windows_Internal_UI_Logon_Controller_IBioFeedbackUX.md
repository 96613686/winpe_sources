# CLogonController::_EnsureBioFeedbackUX(Windows::Internal::UI::Logon::Controller::IBioFeedbackUX * *)

- ea: `0x18003c5d0`
- end: `0x18003c858`
- name: `?_EnsureBioFeedbackUX@CLogonController@@AEAAJPEAPEAUIBioFeedbackUX@Controller@Logon@UI@Internal@Windows@@@Z`
- size: `648`
- prototype: `__int64 __fastcall(CLogonController *__hidden this, struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003c190`

## callees

- `0x18000df10`
- `0x18003c5d0`
- `0x180044f68`
- `0x18005d488`
- `0x180061470`
- `0x18006c000`
- `0x180073320`
- `0x18009d010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003c648`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003c6eb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003c648`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18003c6eb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003c614`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003c614`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c76d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c7aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c7ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c76d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c7aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c7ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c827`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CLogonController::_EnsureBioFeedbackUX(
        RTL_SRWLOCK *this,
        struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX **a2)
{
  struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *v4; // rsi
  RTL_SRWLOCK *v5; // rbx
  char v7; // r12
  unsigned int v8; // eax
  struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *Ptr; // rdi
  int v10; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rdi
  __int64 (__fastcall *v13)(_QWORD *, HSTRING *); // rbx
  int v14; // eax
  int v15; // eax
  int v16; // [rsp+20h] [rbp-50h]
  unsigned __int16 v17; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *v19; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v21; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  *a2 = 0;
  v4 = 0;
  v19 = 0;
  v5 = this + 43;
  AcquireSRWLockExclusive(this + 43);
  if ( !LOBYTE(this[44].Ptr) )
  {
    v7 = 0;
    if ( !this[47].Ptr )
    {
      v21 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.UI.Logon.Controller.BioFeedbackUX",
        0x33u,
        0x32u);
      v8 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::IBioFeedbackUX>>(
             v21,
             &this[47]);
      if ( (int)(v8 + 0x80000000) < 0 || v8 == -2147221164 )
        v7 = 1;
      else
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0xA58,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)v8,
          v16);
    }
    Ptr = (struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *)this[47].Ptr;
    if ( Ptr )
    {
      (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *))(*(_QWORD *)Ptr + 8LL))(Ptr);
      v4 = Ptr;
      v19 = Ptr;
    }
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    if ( v7 )
    {
      v17 = 0;
      v10 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*((_QWORD *)this[18].Ptr + 2) + 72LL))(
              (__int64)this[18].Ptr + 16,
              &v17);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA69,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)(unsigned int)v10,
          v16);
        if ( v4 )
          (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *))(*(_QWORD *)v4 + 16LL))(v4);
        return v11;
      }
      string = 0;
      v12 = this[18].Ptr;
      v13 = *(__int64 (__fastcall **)(_QWORD *, HSTRING *))(v12[2] + 80LL);
      WindowsDeleteString(0);
      string = 0;
      v14 = v13(v12 + 2, &string);
      v11 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA6C,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)(unsigned int)v14,
          v16);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v19);
        return v11;
      }
      v15 = (*(__int64 (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *, __int64, _QWORD, HSTRING))(*(_QWORD *)v4 + 48LL))(
              v4,
              1,
              v17,
              string);
      v11 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA6E,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)(unsigned int)v15,
          v16);
        WindowsDeleteString(string);
        string = 0;
        if ( v4 )
          (*(void (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::IBioFeedbackUX *))(*(_QWORD *)v4 + 16LL))(v4);
        return v11;
      }
      WindowsDeleteString(string);
    }
    *a2 = v4;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA51,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
    (const char *)0x8000001ALL,
    v16);
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
  return 2147483674LL;
}

```

## disassembly

```asm
0x18003c5d0  mov     [rsp-28h+arg_10], rbx
0x18003c5d5  mov     [rsp-28h+arg_18], rsi
0x18003c5da  push    rbp
0x18003c5db  push    rdi
0x18003c5dc  push    r12
0x18003c5de  push    r13
0x18003c5e0  push    r15
0x18003c5e2  mov     rbp, rsp
0x18003c5e5  sub     rsp, 70h
0x18003c5e9  mov     rax, cs:__security_cookie
0x18003c5f0  xor     rax, rsp
0x18003c5f3  mov     [rbp+var_8], rax
0x18003c5f7  mov     r13, rdx
0x18003c5fa  mov     r15, rcx
0x18003c5fd  mov     qword ptr [rdx], 0
0x18003c604  xor     esi, esi
0x18003c606  mov     [rbp+var_30], rsi
0x18003c60a  lea     rbx, [rcx+158h]
0x18003c611  mov     rcx, rbx; SRWLock
0x18003c614  call    cs:__imp_AcquireSRWLockExclusive
0x18003c61a  cmp     [r15+160h], sil
0x18003c621  jz      short loc_18003C656
0x18003c623  mov     rcx, [rbp+28h]; this
0x18003c627  mov     edi, 8000001Ah
0x18003c62c  mov     r9d, edi; char *
0x18003c62f  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003c636  mov     edx, 0A51h; void *
0x18003c63b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c640  test    rbx, rbx
0x18003c643  jz      short loc_18003C64F
0x18003c645  mov     rcx, rbx; SRWLock
0x18003c648  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c64e  nop
0x18003c64f  mov     eax, edi
0x18003c651  jmp     loc_18003C833
0x18003c656  xor     r12b, r12b
0x18003c659  lea     rdi, [r15+178h]
0x18003c660  cmp     qword ptr [rdi], 0
0x18003c664  jnz     short loc_18003C6C4
0x18003c666  mov     [rbp+var_10], 0
0x18003c66e  mov     r9d, 32h ; '2'; unsigned int
0x18003c674  lea     r8d, [r9+1]; unsigned int
0x18003c678  lea     rdx, ?RuntimeClass_Windows_Internal_UI_Logon_Controller_BioFeedbackUX@@3QBGB; "Windows.Internal.UI.Logon.Controller.Bi"...
0x18003c67f  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18003c683  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003c688  mov     rdx, rdi
0x18003c68b  mov     rcx, [rbp+var_10]
0x18003c68f  call    ??$ActivateInstance@V?$ComPtr@UIBioFeedbackUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIBioFeedbackUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::IBioFeedbackUX>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::IBioFeedbackUX>>)
0x18003c694  mov     edx, 80000000h
0x18003c699  lea     ecx, [rax+rdx]
0x18003c69c  test    edx, ecx
0x18003c69e  jnz     short loc_18003C6C1
0x18003c6a0  cmp     eax, 80040154h
0x18003c6a5  jz      short loc_18003C6C1
0x18003c6a7  mov     rcx, [rbp+28h]; this
0x18003c6ab  mov     r9d, eax; char *
0x18003c6ae  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003c6b5  mov     edx, 0A58h; void *
0x18003c6ba  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18003c6bf  jmp     short loc_18003C6C4
0x18003c6c1  mov     r12b, 1
0x18003c6c4  mov     rdi, [rdi]
0x18003c6c7  test    rdi, rdi
0x18003c6ca  jz      short loc_18003C6E3
0x18003c6cc  mov     rax, [rdi]
0x18003c6cf  mov     rcx, rdi
0x18003c6d2  mov     rax, [rax+8]
0x18003c6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c6db  nop
0x18003c6dc  mov     rsi, rdi
0x18003c6df  mov     [rbp+var_30], rdi
0x18003c6e3  test    rbx, rbx
0x18003c6e6  jz      short loc_18003C6F1
0x18003c6e8  mov     rcx, rbx; SRWLock
0x18003c6eb  call    cs:__imp_ReleaseSRWLockExclusive
0x18003c6f1  test    r12b, r12b
0x18003c6f4  jz      loc_18003C82D
0x18003c6fa  xor     r12d, r12d
0x18003c6fd  mov     [rbp+var_40], r12w
0x18003c702  mov     rcx, [r15+90h]
0x18003c709  add     rcx, 10h
0x18003c70d  mov     rax, [rcx]
0x18003c710  lea     rdx, [rbp+var_40]
0x18003c714  mov     rax, [rax+48h]
0x18003c718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c71d  mov     ebx, eax
0x18003c71f  test    eax, eax
0x18003c721  jns     short loc_18003C758
0x18003c723  mov     rcx, [rbp+28h]; this
0x18003c727  mov     r9d, eax; char *
0x18003c72a  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003c731  mov     edx, 0A69h; void *
0x18003c736  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c73b  nop
0x18003c73c  test    rsi, rsi
0x18003c73f  jz      short loc_18003C751
0x18003c741  mov     rax, [rsi]
0x18003c744  mov     rcx, rsi
0x18003c747  mov     rax, [rax+10h]
0x18003c74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c750  nop
0x18003c751  mov     eax, ebx
0x18003c753  jmp     loc_18003C833
0x18003c758  mov     [rbp+string], r12
0x18003c75c  mov     rdi, [r15+90h]
0x18003c763  mov     rax, [rdi+10h]
0x18003c767  mov     rbx, [rax+50h]
0x18003c76b  xor     ecx, ecx; string
0x18003c76d  call    cs:__imp_WindowsDeleteString
0x18003c773  mov     [rbp+string], r12
0x18003c777  lea     rdx, [rbp+string]
0x18003c77b  lea     rcx, [rdi+10h]
0x18003c77f  mov     rax, rbx
0x18003c782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c787  mov     ebx, eax
0x18003c789  test    eax, eax
0x18003c78b  jns     short loc_18003C7BF
0x18003c78d  mov     rcx, [rbp+28h]; this
0x18003c791  mov     r9d, eax; char *
0x18003c794  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003c79b  mov     edx, 0A6Ch; void *
0x18003c7a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c7a5  nop
0x18003c7a6  mov     rcx, [rbp+string]; string
0x18003c7aa  call    cs:__imp_WindowsDeleteString
0x18003c7b0  mov     [rbp+string], r12
0x18003c7b4  lea     rcx, [rbp+var_30]
0x18003c7b8  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18003c7bd  jmp     short loc_18003C751
0x18003c7bf  mov     rax, [rsi]
0x18003c7c2  mov     r9, [rbp+string]
0x18003c7c6  movzx   r8d, [rbp+var_40]
0x18003c7cb  mov     edx, 1
0x18003c7d0  mov     rcx, rsi
0x18003c7d3  mov     rax, [rax+30h]
0x18003c7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7dc  mov     ebx, eax
0x18003c7de  test    eax, eax
0x18003c7e0  jns     short loc_18003C823
0x18003c7e2  mov     rcx, [rbp+28h]; this
0x18003c7e6  mov     r9d, eax; char *
0x18003c7e9  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003c7f0  mov     edx, 0A6Eh; void *
0x18003c7f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c7fa  nop
0x18003c7fb  mov     rcx, [rbp+string]; string
0x18003c7ff  call    cs:__imp_WindowsDeleteString
0x18003c805  mov     [rbp+string], r12
0x18003c809  test    rsi, rsi
0x18003c80c  jz      short loc_18003C81E
0x18003c80e  mov     rax, [rsi]
0x18003c811  mov     rcx, rsi
0x18003c814  mov     rax, [rax+10h]
0x18003c818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c81d  nop
0x18003c81e  jmp     loc_18003C751
0x18003c823  mov     rcx, [rbp+string]; string
0x18003c827  call    cs:__imp_WindowsDeleteString
0x18003c82d  mov     [r13+0], rsi
0x18003c831  xor     eax, eax
0x18003c833  mov     rcx, [rbp+var_8]
0x18003c837  xor     rcx, rsp; StackCookie
0x18003c83a  call    __security_check_cookie
0x18003c83f  lea     r11, [rsp+70h+var_s0]
0x18003c844  mov     rbx, [r11+40h]
0x18003c848  mov     rsi, [r11+48h]
0x18003c84c  mov     rsp, r11
0x18003c84f  pop     r15
0x18003c851  pop     r13
0x18003c853  pop     r12
0x18003c855  pop     rdi
0x18003c856  pop     rbp
0x18003c857  retn
```
