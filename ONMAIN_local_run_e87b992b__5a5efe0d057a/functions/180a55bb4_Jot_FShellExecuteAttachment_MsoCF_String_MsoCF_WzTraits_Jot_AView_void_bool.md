# Jot::FShellExecuteAttachment(MsoCF::String<MsoCF::WzTraits>,Jot::AView *,void * *,bool)

- ea: `0x180a55bb4`
- end: `0x180a55e33`
- name: `?FShellExecuteAttachment@Jot@@YA_NV?$String@UWzTraits@MsoCF@@@MsoCF@@PEAUAView@1@PEAPEAX_N@Z`
- size: `639`
- prototype: `char __fastcall(const WCHAR *, __int64, HANDLE *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x180a55910`

## callees

- `0x18005ccc0`
- `0x18005cd08`
- `0x1802b02b4`
- `0x1802b1500`
- `0x1802e2251`
- `0x1802e5170`
- `0x1802e5190`
- `0x1803f5de0`
- `0x18072ef78`
- `0x1807c2248`
- `0x1808fa4a0`
- `0x180910218`
- `0x180a55bb4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180a55cb1`
- `KERNEL32!GetLastError` at `0x180a55ced`
- `KERNEL32!GetLastError` at `0x180a55d01`
- `KERNEL32!GetLastError` at `0x180a55cb1`
- `KERNEL32!GetLastError` at `0x180a55ced`
- `KERNEL32!GetLastError` at `0x180a55d01`
- `KERNEL32!GetCurrentProcessId` at `0x180a55c8d`
- `KERNEL32!GetCurrentProcessId` at `0x180a55c8d`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180a55d56`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180a55d56`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180a55dca`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180a55dca`
- `SHELL32!ShellExecuteExW` at `0x180a55ca3`
- `SHELL32!ShellExecuteExW` at `0x180a55cdf`
- `SHELL32!ShellExecuteExW` at `0x180a55ca3`
- `SHELL32!ShellExecuteExW` at `0x180a55cdf`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180a55c43`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180a55c43`
- `USER32!GetWindowThreadProcessId` at `0x180a55c87`
- `USER32!GetWindowThreadProcessId` at `0x180a55c87`
- `USER32!GetParent` at `0x180a55c74`
- `USER32!GetParent` at `0x180a55c74`
- `Mso98Win32Client!__imp_?MsoSystemPolicyAlert@@YAXXZ` at `0x180a55de7`
- `Mso98Win32Client!__imp_?MsoSystemPolicyAlert@@YAXXZ` at `0x180a55de7`

## string_xrefs

- `0x180a55cc5`: `openas`

## pseudocode

```c
char __fastcall Jot::FShellExecuteAttachment(const WCHAR *a1, __int64 a2, HANDLE *a3)
{
  char v7; // di
  WCHAR *v8; // rax
  HWND Parent; // rax
  HWND v10; // r14
  HWND v11; // rbx
  DWORD LastError; // eax
  unsigned int v13; // r9d
  __int128 v14; // xmm6
  struct MsoCF::IError *v15; // rbx
  DWORD dwProcessId[2]; // [rsp+48h] [rbp-C0h] BYREF
  struct MsoCF::IError *v17; // [rsp+50h] [rbp-B8h] BYREF
  _OWORD v18[2]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v19[6]; // [rsp+78h] [rbp-90h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v21[8]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v22[16]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v23[368]; // [rsp+168h] [rbp+60h] BYREF

  if ( !a2 )
    return 0;
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  pExecInfo.cbSize = 112;
  pExecInfo.fMask = 8389696;
  pExecInfo.lpVerb = 0;
  v7 = 1;
  pExecInfo.nShow = 1;
  pExecInfo.lpFile = a1;
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(
    v23,
    a1);
  v8 = (WCHAR *)Jot::CWzInBuffer::operator wchar_t *(v23);
  PathRemoveFileSpecW(v8);
  pExecInfo.lpDirectory = (LPCWSTR)Jot::CWzInBuffer::operator wchar_t *(v23);
  dwProcessId[0] = 0;
  Parent = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 24LL))(a2);
  v10 = Parent;
  do
  {
    v11 = Parent;
    Parent = GetParent(Parent);
  }
  while ( Parent );
  GetWindowThreadProcessId(v10, dwProcessId);
  if ( dwProcessId[0] != GetCurrentProcessId() )
    v11 = 0;
  pExecInfo.hwnd = v11;
  if ( !ShellExecuteExW(&pExecInfo) )
  {
    if ( GetLastError() != 1155
      || (pExecInfo.fMask = 8388609,
          pExecInfo.lpVerb = L"openas",
          pExecInfo.lpClass = L"Unknown",
          !ShellExecuteExW(&pExecInfo)) )
    {
      if ( GetLastError() == -1 )
      {
        MsoSystemPolicyAlert();
      }
      else
      {
        v17 = 0;
        LastError = GetLastError();
        MsoCF::CreateWin32ErrorTag((MsoCF *)LastError, (unsigned int)&v17, (struct MsoCF::IError **)0x1042660, v13);
        v19[4] = v21;
        v21[7] = 0;
        v14 = *(_OWORD *)Jot::CDialogButtonSet::CDialogButtonSet(v22, 1, 0, 0, 0);
        v15 = v17;
        if ( v17 )
        {
          MsoCF::CErrorException::CErrorException((MsoCF::CErrorException *)v19, v17);
          v19[0] = &`Jot::CreateException'::`2'::MyCErrorException::`vftable';
          std::exception_ptr::_Copy_exception(
            v18,
            v19,
            &TI4_AUMyCErrorException__1__CreateException_Jot__YA_AVexception_ptr_std__PEAUIError_MsoCF___Z_);
          MsoCF::CErrorException::~CErrorException((MsoCF::CErrorException *)v19);
        }
        else
        {
          v18[0] = 0;
          __ExceptionPtrCreate(v18);
        }
        v18[1] = v14;
        Jot::DisplayErrorDialogForError((Jot *)v18, 0, 0, (__int64)v21);
        __ExceptionPtrDestroy(v18);
        if ( v15 )
          (*(void (__fastcall **)(struct MsoCF::IError *))(*(_QWORD *)v15 + 16LL))(v15);
      }
      v7 = 0;
    }
  }
  if ( a3 )
    *a3 = pExecInfo.hProcess;
  Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2597>>,2596>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2597>>,2596>(v23);
  return v7;
}

```

## disassembly

```asm
0x180a55bb4  mov     rax, rsp
0x180a55bb7  mov     [rax+8], rbx
0x180a55bbb  push    rbp
0x180a55bbc  push    rsi
0x180a55bbd  push    rdi
0x180a55bbe  push    r14
0x180a55bc0  push    r15
0x180a55bc2  lea     rbp, [rax-218h]
0x180a55bc9  sub     rsp, 2F0h
0x180a55bd0  movaps  xmmword ptr [rax-38h], xmm6
0x180a55bd4  mov     rax, cs:__security_cookie
0x180a55bdb  xor     rax, rsp
0x180a55bde  mov     [rbp+210h+var_40], rax
0x180a55be5  mov     rsi, r8
0x180a55be8  mov     r14, rdx
0x180a55beb  mov     rbx, rcx
0x180a55bee  xor     r15d, r15d
0x180a55bf1  test    rdx, rdx
0x180a55bf4  jnz     short loc_180A55BFD
0x180a55bf6  xor     al, al
0x180a55bf8  jmp     loc_180A55E08
0x180a55bfd  mov     edi, 70h ; 'p'
0x180a55c02  mov     r8d, edi; Size
0x180a55c05  xor     edx, edx; Val
0x180a55c07  lea     rcx, [rbp+210h+pExecInfo]; void *
0x180a55c0b  call    memset_0
0x180a55c10  mov     [rbp+210h+pExecInfo.cbSize], edi
0x180a55c13  mov     [rbp+210h+pExecInfo.fMask], 800440h
0x180a55c1a  mov     [rbp+210h+pExecInfo.lpVerb], r15
0x180a55c1e  mov     edi, 1
0x180a55c23  mov     [rbp+210h+pExecInfo.nShow], edi
0x180a55c26  mov     [rbp+210h+pExecInfo.lpFile], rbx
0x180a55c2a  mov     rdx, rbx
0x180a55c2d  lea     rcx, [rbp+210h+var_1B0]
0x180a55c31  call    ??0?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0IB@@2@@MsoCF@@$0IA@@Jot@@QEAA@V?$String@UWzTraits@MsoCF@@@MsoCF@@@Z; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,129>>,128>(MsoCF::String<MsoCF::WzTraits>)
0x180a55c36  lea     rcx, [rbp+210h+var_1B0]
0x180a55c3a  call    ??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x180a55c3f  nop
0x180a55c40  mov     rcx, rax; pszPath
0x180a55c43  call    cs:__imp_PathRemoveFileSpecW
0x180a55c49  lea     rcx, [rbp+210h+var_1B0]
0x180a55c4d  call    ??BCWzInBuffer@Jot@@QEAAPEA_WXZ; Jot::CWzInBuffer::operator wchar_t *(void)
0x180a55c52  mov     [rbp+210h+pExecInfo.lpDirectory], rax
0x180a55c56  mov     [rsp+310h+dwProcessId], r15d
0x180a55c5b  mov     rax, [r14]
0x180a55c5e  mov     rcx, r14
0x180a55c61  mov     rax, [rax+18h]
0x180a55c65  call    cs:__guard_dispatch_icall_fptr
0x180a55c6b  mov     r14, rax
0x180a55c6e  mov     rbx, rax
0x180a55c71  mov     rcx, rax; hWnd
0x180a55c74  call    cs:__imp_GetParent
0x180a55c7a  test    rax, rax
0x180a55c7d  jnz     short loc_180A55C6E
0x180a55c7f  lea     rdx, [rsp+310h+dwProcessId]; lpdwProcessId
0x180a55c84  mov     rcx, r14; hWnd
0x180a55c87  call    cs:__imp_GetWindowThreadProcessId
0x180a55c8d  call    cs:__imp_GetCurrentProcessId
0x180a55c93  cmp     [rsp+310h+dwProcessId], eax
0x180a55c97  cmovnz  rbx, r15
0x180a55c9b  mov     [rbp+210h+pExecInfo.hwnd], rbx
0x180a55c9f  lea     rcx, [rbp+210h+pExecInfo]; pExecInfo
0x180a55ca3  call    cs:__imp_ShellExecuteExW
0x180a55ca9  test    eax, eax
0x180a55cab  jnz     loc_180A55DF0
0x180a55cb1  call    cs:__imp_GetLastError
0x180a55cb7  cmp     eax, 483h
0x180a55cbc  jnz     short loc_180A55CED
0x180a55cbe  mov     [rbp+210h+pExecInfo.fMask], 800001h
0x180a55cc5  lea     rax, aOpenas; "openas"
0x180a55ccc  mov     [rbp+210h+pExecInfo.lpVerb], rax
0x180a55cd0  lea     rax, aUnknown_2; "Unknown"
0x180a55cd7  mov     [rbp+210h+pExecInfo.lpClass], rax
0x180a55cdb  lea     rcx, [rbp+210h+pExecInfo]; pExecInfo
0x180a55cdf  call    cs:__imp_ShellExecuteExW
0x180a55ce5  test    eax, eax
0x180a55ce7  jnz     loc_180A55DF0
0x180a55ced  call    cs:__imp_GetLastError
0x180a55cf3  cmp     eax, 0FFFFFFFFh
0x180a55cf6  jz      loc_180A55DE7
0x180a55cfc  mov     [rsp+310h+var_2C8], r15
0x180a55d01  call    cs:__imp_GetLastError
0x180a55d07  mov     r8d, 1042660h; struct MsoCF::IError **
0x180a55d0d  lea     rdx, [rsp+310h+var_2C8]; unsigned int
0x180a55d12  mov     ecx, eax; this
0x180a55d14  call    ?CreateWin32ErrorTag@MsoCF@@YAXKPEAPEAUIError@1@K@Z; MsoCF::CreateWin32ErrorTag(ulong,MsoCF::IError * *,ulong)
0x180a55d19  lea     rax, [rbp+210h+var_200]
0x180a55d1d  mov     [rbp+210h+var_280], rax
0x180a55d21  mov     [rbp+210h+var_1C8], r15
0x180a55d25  mov     [rsp+310h+var_2F0], r15d
0x180a55d2a  xor     r9d, r9d
0x180a55d2d  xor     r8d, r8d
0x180a55d30  mov     edx, edi
0x180a55d32  lea     rcx, [rbp+210h+var_1C0]
0x180a55d36  call    ??0CDialogButtonSet@Jot@@QEAA@W4DisplayErrorResponse@1@000@Z; Jot::CDialogButtonSet::CDialogButtonSet(Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse,Jot::DisplayErrorResponse)
0x180a55d3b  movups  xmm6, xmmword ptr [rax]
0x180a55d3e  mov     rbx, [rsp+310h+var_2C8]
0x180a55d43  test    rbx, rbx
0x180a55d46  jnz     short loc_180A55D5E
0x180a55d48  xorps   xmm0, xmm0
0x180a55d4b  movdqu  xmmword ptr [rsp+310h+var_2C8+8], xmm0
0x180a55d51  lea     rcx, [rsp+310h+var_2C8+8]
0x180a55d56  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180a55d5c  jmp     short loc_180A55D98
0x180a55d5e  mov     rdx, rbx; struct MsoCF::IError *
0x180a55d61  lea     rcx, [rsp+310h+var_2A0]; this
0x180a55d66  call    ??0CErrorException@MsoCF@@IEAA@PEAUIError@1@@Z; MsoCF::CErrorException::CErrorException(MsoCF::IError *)
0x180a55d6b  lea     rax, ??_7MyCErrorException@?1??CreateException@Jot@@YA?AVexception_ptr@std@@PEAUIError@MsoCF@@@Z@6B@; const `Jot::CreateException(MsoCF::IError *)'::`2'::MyCErrorException::`vftable'
0x180a55d72  mov     [rsp+310h+var_2A0], rax
0x180a55d77  lea     r8, _TI4?AUMyCErrorException@?1??CreateException@Jot@@YA?AVexception_ptr@std@@PEAUIError@MsoCF@@@Z@; throw info for 'struct `class std::exception_ptr Jot::CreateException(struct MsoCF::IError *)'::`2'::MyCErrorException'
0x180a55d7e  lea     rdx, [rsp+310h+var_2A0]
0x180a55d83  lea     rcx, [rsp+310h+var_2C8+8]
0x180a55d88  call    ?_Copy_exception@exception_ptr@std@@SA?AV12@PEAXPEBX@Z; std::exception_ptr::_Copy_exception(void *,void const *)
0x180a55d8d  lea     rcx, [rsp+310h+var_2A0]; this
0x180a55d92  call    ??1CErrorException@MsoCF@@IEAA@XZ; MsoCF::CErrorException::~CErrorException(void)
0x180a55d97  nop
0x180a55d98  movdqu  [rsp+310h+var_2B8+8], xmm6
0x180a55d9e  lea     rax, [rbp+210h+var_200]
0x180a55da2  mov     [rsp+310h+var_2E0], rax; __int64
0x180a55da7  mov     [rsp+310h+var_2E8], r15b; char
0x180a55dac  mov     [rsp+310h+var_2F0], r15d; int
0x180a55db1  xor     r9d, r9d
0x180a55db4  lea     r8, [rsp+310h+var_2B8+8]
0x180a55db9  xor     edx, edx
0x180a55dbb  lea     rcx, [rsp+310h+var_2C8+8]; this
0x180a55dc0  call    ?DisplayErrorDialogForError@Jot@@YA?AW4DisplayErrorResponse@1@AEBVexception_ptr@std@@W4DisplayErrorContext@1@VCDialogButtonSet@1@_N13V?$function@$$A6AXXZ@4@@Z; Jot::DisplayErrorDialogForError(std::exception_ptr const &,Jot::DisplayErrorContext,Jot::CDialogButtonSet,bool,Jot::DisplayErrorContext,bool,std::function<void (void)>)
0x180a55dc5  lea     rcx, [rsp+310h+var_2C8+8]
0x180a55dca  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180a55dd0  test    rbx, rbx
0x180a55dd3  jz      short loc_180A55DED
0x180a55dd5  mov     rax, [rbx]
0x180a55dd8  mov     rcx, rbx
0x180a55ddb  mov     rax, [rax+10h]
0x180a55ddf  call    cs:__guard_dispatch_icall_fptr
0x180a55de5  jmp     short loc_180A55DED
0x180a55de7  call    cs:__imp_?MsoSystemPolicyAlert@@YAXXZ; MsoSystemPolicyAlert(void)
0x180a55ded  mov     dil, r15b
0x180a55df0  test    rsi, rsi
0x180a55df3  jz      short loc_180A55DFC
0x180a55df5  mov     rax, [rbp+210h+pExecInfo.hProcess]
0x180a55df9  mov     [rsi], rax
0x180a55dfc  lea     rcx, [rbp+210h+var_1B0]
0x180a55e00  call    ??1?$CWzInBuffer_T@V?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CFastBuffer@_W$0KCF@@2@@MsoCF@@$0KCE@@Jot@@QEAA@XZ; Jot::CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2597>>,2596>::~CWzInBuffer_T<MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CFastBuffer<wchar_t,2597>>,2596>(void)
0x180a55e05  mov     al, dil
0x180a55e08  mov     rcx, [rbp+210h+var_40]
0x180a55e0f  xor     rcx, rsp; StackCookie
0x180a55e12  call    __security_check_cookie
0x180a55e17  lea     r11, [rsp+310h+var_20]
0x180a55e1f  mov     rbx, [r11+30h]
0x180a55e23  movaps  xmm6, xmmword ptr [r11-10h]
0x180a55e28  mov     rsp, r11
0x180a55e2b  pop     r15
0x180a55e2d  pop     r14
0x180a55e2f  pop     rdi
0x180a55e30  pop     rsi
0x180a55e31  pop     rbp
0x180a55e32  retn
```
