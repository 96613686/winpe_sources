# Windows::Payment::Mediator::Service::RpcCallManager::DetermineCallerIdentity(void)

- ea: `0x180080c9c`
- end: `0x180080fd5`
- name: `?DetermineCallerIdentity@RpcCallManager@Service@Mediator@Payment@Windows@@QEAAXXZ`
- size: `825`
- prototype: `void __fastcall(Windows::Payment::Mediator::Service::RpcCallManager *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007e710`
- `0x18007f750`
- `0x1800878a0`

## callees

- `0x1800049a0`
- `0x18000584c`
- `0x180007aac`
- `0x180013014`
- `0x180013274`
- `0x18002daa4`
- `0x180080c9c`
- `0x180081d88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180080d97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180080db8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180080d97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180080db8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180080dc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180080dc6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180080da5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180080da5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080d00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080d69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080e04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080d00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080d69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080e04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180080d13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180080e17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180080d13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180080e17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080d1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080d1c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180080d35`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180080d35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080d0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180080d0b`
- `ntdll!RtlQueryPackageIdentity` at `0x180080e7d`
- `ntdll!RtlQueryPackageIdentity` at `0x180080e7d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180080d5f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180080de3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180080d5f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180080de3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080e0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080e0f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180080e2a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180080e2a`

## string_xrefs

- `0x180080f54`: `onecoreuap\ds\nfc\product\payment\service\lib\rpccallmanager.cpp`
- `0x180080f7b`: `onecoreuap\ds\nfc\product\payment\service\lib\rpccallmanager.cpp`
- `0x180080f8d`: `onecoreuap\ds\nfc\product\payment\service\lib\rpccallmanager.cpp`
- `0x180080f9f`: `onecoreuap\ds\nfc\product\payment\service\lib\rpccallmanager.cpp`
- `0x180080fb1`: `onecoreuap\ds\nfc\product\payment\service\lib\rpccallmanager.cpp`
- `0x180080fc3`: `onecoreuap\ds\nfc\product\payment\service\lib\rpccallmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Payment::Mediator::Service::RpcCallManager::DetermineCallerIdentity(
        Windows::Payment::Mediator::Service::RpcCallManager *this)
{
  void **v2; // r15
  char *v3; // rsi
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  const char *v6; // r9
  signed int v7; // eax
  const char *v8; // r9
  DWORD v9; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v11; // rax
  void *v12; // rbx
  HANDLE v13; // rax
  const char *v14; // r9
  void *v15; // r14
  DWORD v16; // ebx
  const char *v17; // r9
  char *v18; // rdi
  int v19; // eax
  __int64 v20; // r8
  unsigned __int64 v21; // rdx
  char *v22; // rsi
  __int64 v23; // rbx
  const WCHAR *v24; // r9
  _WORD *v25; // rbx
  unsigned int v26; // eax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  int ReturnLengtha; // [rsp+20h] [rbp-E0h]
  DWORD TokenInformationLength; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v31[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD Src[128]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  TokenInformationLength = 0;
  v31[0] = 0;
  v31[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v31[0]) = 0;
  v2 = (void **)((char *)this + 24);
  v3 = (char *)*((_QWORD *)this + 3);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v3);
    SetLastError(LastError);
  }
  *v2 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, v2) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x106,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\rpccallmanager.cpp",
      v6);
  if ( !GetTokenInformation(*v2, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v7 = GetLastError();
    v8 = v7 > 0 ? (const char *)((unsigned __int16)v7 | 0x80070000) : (const char *)(unsigned int)v7;
    if ( v7 != 122 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x110,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\rpccallmanager.cpp",
        v8,
        ReturnLength);
  }
  v9 = TokenInformationLength;
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 0, v9);
  v12 = (void *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = v11;
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v12);
  }
  if ( !GetTokenInformation(*v2, TokenUser, *((LPVOID *)this + 4), TokenInformationLength, (PDWORD)this + 10) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x116,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\rpccallmanager.cpp",
      v14);
  v15 = (void *)*((_QWORD *)this + 6);
  if ( v15 )
  {
    v16 = GetLastError();
    LocalFree(v15);
    SetLastError(v16);
  }
  *((_QWORD *)this + 6) = 0;
  if ( !ConvertSidToStringSidW(**((PSID **)this + 4), (LPWSTR *)this + 6) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x117,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\rpccallmanager.cpp",
      v17);
  v18 = (char *)this + 56;
  if ( !v18 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\rpccallmanager.cpp",
      (const char *)0x80004003LL,
      ReturnLengtha);
  v30 = 256;
  v19 = RtlQueryPackageIdentity(*v2, Src, &v30, 0);
  if ( v19 < 0 )
  {
    if ( v19 != -1073741275 )
    {
      v26 = wil::verify_hresult<long>(v19 | 0x10000000u);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\payment\\service\\lib\\rpccallmanager.cpp",
        (const char *)v26,
        0);
    }
    v21 = 9;
    if ( *((_QWORD *)v18 + 3) >= 9u )
    {
      v25 = *(_WORD **)v18;
      *((_QWORD *)v18 + 2) = 9;
      memmove_0(v25, L"_desktop_", 0x12u);
      v25[9] = 0;
      goto LABEL_30;
    }
    v24 = L"_desktop_";
LABEL_29:
    ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
      v18,
      v21,
      v20,
      v24);
    goto LABEL_30;
  }
  v21 = -1;
  do
    ++v21;
  while ( Src[v21] );
  if ( v21 > *((_QWORD *)v18 + 3) )
  {
    v24 = Src;
    goto LABEL_29;
  }
  if ( *((_QWORD *)v18 + 3) <= 7u )
    v22 = v18;
  else
    v22 = *(char **)v18;
  *((_QWORD *)v18 + 2) = v21;
  v23 = 2 * v21;
  memmove_0(v22, Src, 2 * v21);
  *(_WORD *)&v22[v23] = 0;
LABEL_30:
  std::wstring::~wstring(v31);
}

```

## disassembly

```asm
0x180080c9c  mov     [rsp-8+arg_8], rbx
0x180080ca1  mov     [rsp-8+arg_10], rsi
0x180080ca6  push    rbp
0x180080ca7  push    rdi
0x180080ca8  push    r12
0x180080caa  push    r14
0x180080cac  push    r15
0x180080cae  lea     rbp, [rsp-70h]
0x180080cb3  sub     rsp, 170h
0x180080cba  mov     rax, cs:__security_cookie
0x180080cc1  xor     rax, rsp
0x180080cc4  mov     [rbp+90h+var_30], rax
0x180080cc8  mov     rdi, rcx
0x180080ccb  xor     r12d, r12d
0x180080cce  mov     [rsp+190h+TokenInformationLength], r12d
0x180080cd3  xorps   xmm0, xmm0
0x180080cd6  movups  [rsp+190h+var_150], xmm0
0x180080cdb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180080ce3  movdqu  [rsp+190h+var_140], xmm1
0x180080ce9  mov     word ptr [rsp+190h+var_150], r12w
0x180080cef  lea     r15, [rcx+18h]
0x180080cf3  mov     rsi, [r15]
0x180080cf6  lea     rax, [rsi-1]
0x180080cfa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180080cfe  ja      short loc_180080D19
0x180080d00  call    cs:__imp_GetLastError
0x180080d06  mov     ebx, eax
0x180080d08  mov     rcx, rsi; hObject
0x180080d0b  call    cs:__imp_CloseHandle
0x180080d11  mov     ecx, ebx; dwErrCode
0x180080d13  call    cs:__imp_SetLastError
0x180080d19  mov     [r15], r12
0x180080d1c  call    cs:__imp_GetCurrentThread
0x180080d22  mov     r9, r15; TokenHandle
0x180080d25  mov     esi, 1
0x180080d2a  mov     r8d, esi; OpenAsSelf
0x180080d2d  mov     edx, 20008h; DesiredAccess
0x180080d32  mov     rcx, rax; ThreadHandle
0x180080d35  call    cs:__imp_OpenThreadToken
0x180080d3b  mov     rcx, [rbp+98h]; this
0x180080d42  test    eax, eax
0x180080d44  jz      loc_180080F8D
0x180080d4a  lea     rax, [rsp+190h+TokenInformationLength]
0x180080d4f  mov     [rsp+190h+ReturnLength], rax; int
0x180080d54  xor     r9d, r9d; TokenInformationLength
0x180080d57  xor     r8d, r8d; TokenInformation
0x180080d5a  mov     edx, esi; TokenInformationClass
0x180080d5c  mov     rcx, [r15]; TokenHandle
0x180080d5f  call    cs:__imp_GetTokenInformation
0x180080d65  test    eax, eax
0x180080d67  jnz     short loc_180080D93
0x180080d69  call    cs:__imp_GetLastError
0x180080d6f  test    eax, eax
0x180080d71  jg      short loc_180080D78
0x180080d73  mov     r9d, eax
0x180080d76  jmp     short loc_180080D83
0x180080d78  movzx   r9d, ax
0x180080d7c  or      r9d, 80070000h; char *
0x180080d83  mov     rcx, [rbp+98h]; this
0x180080d8a  cmp     eax, 7Ah ; 'z'
0x180080d8d  jnz     loc_180080F9F
0x180080d93  mov     ebx, [rsp+190h+TokenInformationLength]
0x180080d97  call    cs:__imp_GetProcessHeap
0x180080d9d  mov     r8d, ebx; dwBytes
0x180080da0  xor     edx, edx; dwFlags
0x180080da2  mov     rcx, rax; hHeap
0x180080da5  call    cs:__imp_HeapAlloc
0x180080dab  mov     rbx, [rdi+20h]
0x180080daf  mov     [rdi+20h], rax
0x180080db3  test    rbx, rbx
0x180080db6  jz      short loc_180080DCC
0x180080db8  call    cs:__imp_GetProcessHeap
0x180080dbe  mov     rcx, rax; hHeap
0x180080dc1  mov     r8, rbx; lpMem
0x180080dc4  xor     edx, edx; dwFlags
0x180080dc6  call    cs:__imp_HeapFree
0x180080dcc  lea     rax, [rdi+28h]
0x180080dd0  mov     [rsp+190h+ReturnLength], rax; int
0x180080dd5  mov     r9d, [rsp+190h+TokenInformationLength]; TokenInformationLength
0x180080dda  mov     r8, [rdi+20h]; TokenInformation
0x180080dde  mov     edx, esi; TokenInformationClass
0x180080de0  mov     rcx, [r15]; TokenHandle
0x180080de3  call    cs:__imp_GetTokenInformation
0x180080de9  mov     rcx, [rbp+98h]; this
0x180080df0  test    eax, eax
0x180080df2  jz      loc_180080FB1
0x180080df8  lea     rsi, [rdi+30h]
0x180080dfc  mov     r14, [rsi]
0x180080dff  test    r14, r14
0x180080e02  jz      short loc_180080E1D
0x180080e04  call    cs:__imp_GetLastError
0x180080e0a  mov     ebx, eax
0x180080e0c  mov     rcx, r14; hMem
0x180080e0f  call    cs:__imp_LocalFree
0x180080e15  mov     ecx, ebx; dwErrCode
0x180080e17  call    cs:__imp_SetLastError
0x180080e1d  mov     [rsi], r12
0x180080e20  mov     rcx, [rdi+20h]
0x180080e24  mov     rdx, rsi; StringSid
0x180080e27  mov     rcx, [rcx]; Sid
0x180080e2a  call    cs:__imp_ConvertSidToStringSidW
0x180080e30  mov     rcx, [rbp+98h]; this
0x180080e37  test    eax, eax
0x180080e39  jz      loc_180080FC3
0x180080e3f  mov     rcx, [rbp+98h]; this
0x180080e46  add     rdi, 38h ; '8'
0x180080e4a  jz      loc_180080F4E
0x180080e50  mov     [rsp+190h+var_158], 100h
0x180080e59  mov     [rsp+190h+var_160], r12b
0x180080e5e  lea     rax, [rsp+190h+var_160]
0x180080e63  mov     [rsp+190h+var_168], rax
0x180080e68  mov     [rsp+190h+ReturnLength], r12; int
0x180080e6d  xor     r9d, r9d
0x180080e70  lea     r8, [rsp+190h+var_158]
0x180080e75  lea     rdx, [rsp+190h+Src]
0x180080e7a  mov     rcx, [r15]
0x180080e7d  call    cs:__imp_RtlQueryPackageIdentity
0x180080e83  test    eax, eax
0x180080e85  js      short loc_180080ED5
0x180080e87  lea     rax, [rsp+190h+Src]
0x180080e8c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180080e90  inc     rdx
0x180080e93  cmp     [rax+rdx*2], r12w
0x180080e98  jnz     short loc_180080E90
0x180080e9a  cmp     rdx, [rdi+18h]
0x180080e9e  ja      short loc_180080ECE
0x180080ea0  cmp     qword ptr [rdi+18h], 7
0x180080ea5  jbe     short loc_180080EAC
0x180080ea7  mov     rsi, [rdi]
0x180080eaa  jmp     short loc_180080EAF
0x180080eac  mov     rsi, rdi
0x180080eaf  mov     [rdi+10h], rdx
0x180080eb3  lea     rbx, [rdx+rdx]
0x180080eb7  mov     r8, rbx; Size
0x180080eba  lea     rdx, [rsp+190h+Src]; Src
0x180080ebf  mov     rcx, rsi; void *
0x180080ec2  call    memmove_0
0x180080ec7  mov     [rbx+rsi], r12w
0x180080ecc  jmp     short loc_180080F1C
0x180080ece  lea     r9, [rsp+190h+Src]
0x180080ed3  jmp     short loc_180080F13
0x180080ed5  cmp     eax, 0C0000225h
0x180080eda  jnz     loc_180080F66
0x180080ee0  mov     edx, 9
0x180080ee5  cmp     [rdi+18h], rdx
0x180080ee9  jb      short loc_180080F0C
0x180080eeb  mov     rbx, [rdi]
0x180080eee  mov     [rdi+10h], rdx
0x180080ef2  lea     r8d, [rdx+9]; Size
0x180080ef6  lea     rdx, String1; "_desktop_"
0x180080efd  mov     rcx, rbx; void *
0x180080f00  call    memmove_0
0x180080f05  mov     [rbx+12h], r12w
0x180080f0a  jmp     short loc_180080F1C
0x180080f0c  lea     r9, String1; "_desktop_"
0x180080f13  mov     rcx, rdi
0x180080f16  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x180080f1b  nop
0x180080f1c  lea     rcx, [rsp+190h+var_150]
0x180080f21  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180080f26  mov     rcx, [rbp+90h+var_30]
0x180080f2a  xor     rcx, rsp; StackCookie
0x180080f2d  call    __security_check_cookie
0x180080f32  lea     r11, [rsp+190h+var_20]
0x180080f3a  mov     rbx, [r11+38h]
0x180080f3e  mov     rsi, [r11+40h]
0x180080f42  mov     rsp, r11
0x180080f45  pop     r15
0x180080f47  pop     r14
0x180080f49  pop     r12
0x180080f4b  pop     rdi
0x180080f4c  pop     rbp
0x180080f4d  retn
0x180080f4e  mov     r9d, 80004003h; char *
0x180080f54  lea     r8, aOnecoreuapDsNf_44; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x180080f5b  mov     edx, 15h; void *
0x180080f60  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080f66  bts     eax, 1Ch
0x180080f6a  mov     ecx, eax
0x180080f6c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180080f71  mov     r9d, eax; char *
0x180080f74  mov     rcx, [rbp+98h]; this
0x180080f7b  lea     r8, aOnecoreuapDsNf_44; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x180080f82  mov     edx, 25h ; '%'; void *
0x180080f87  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080f8d  lea     r8, aOnecoreuapDsNf_44; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x180080f94  mov     edx, 106h; void *
0x180080f99  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180080f9f  lea     r8, aOnecoreuapDsNf_44; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x180080fa6  mov     edx, 110h; void *
0x180080fab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180080fb1  lea     r8, aOnecoreuapDsNf_44; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x180080fb8  mov     edx, 116h; void *
0x180080fbd  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180080fc3  lea     r8, aOnecoreuapDsNf_44; "onecoreuap\\ds\\nfc\\product\\payment\\"...
0x180080fca  mov     edx, 117h; void *
0x180080fcf  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
