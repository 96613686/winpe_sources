# ClientConnection2::CreateWorker(IUnknown *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180058654`
- end: `0x1800589bf`
- name: `?CreateWorker@ClientConnection2@@AEAAJPEAUIUnknown@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z`
- size: `875`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180056d90`

## callees

- `0x180002520`
- `0x1800050cd`
- `0x1800075e4`
- `0x18000a444`
- `0x18000a464`
- `0x180010148`
- `0x180013230`
- `0x180039fd8`
- `0x180058368`
- `0x180058654`
- `0x180058ef8`
- `0x18005c4a8`
- `0x18005ccf4`
- `0x180068010`

## import_xrefs

- `combase!__imp_CoGetCallContextOfObject` at `0x1800586be`
- `combase!__imp_CoGetCallContextOfObject` at `0x1800586be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058799`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800587ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800587ac`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180058836`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180058836`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800587a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800587a4`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180058857`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180058857`

## string_xrefs

- `0x180058803`: `onecoreuap\windows\core\isoenvbroker\lib\v2\clientconnection.cpp`
- `0x180058868`: `onecoreuap\windows\core\isoenvbroker\lib\v2\clientconnection.cpp`
- `0x1800588eb`: `onecoreuap\windows\core\isoenvbroker\lib\v2\clientconnection.cpp`
- `0x1800586d4`: `onecoreuap\windows\core\isoenvbroker\lib\v2\clientidentity.cpp`
- `0x180058727`: `onecoreuap\windows\core\isoenvbroker\lib\v2\clientidentity.cpp`
- `0x1800587d0`: `onecoreuap\windows\core\isoenvbroker\lib\v2\clientidentity.cpp`
- `0x1800589ad`: `onecoreuap\windows\core\isoenvbroker\lib\v2\clientidentity.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ClientConnection2::CreateWorker(_DWORD *Context, __int64 a2, char *a3, const char *a4)
{
  const char *v4; // r15
  char *v5; // r14
  int v7; // eax
  unsigned int v8; // esi
  __int64 v9; // rax
  HANDLE *v10; // r13
  void *v11; // r12
  void **v12; // r14
  void *v13; // r15
  DWORD LastError; // ebx
  __int64 v16; // r8
  const char *v17; // r9
  char **v18; // rcx
  unsigned __int64 v19; // rdx
  char *v20; // rsi
  __int64 v21; // rbx
  char *v22; // rsi
  int v23; // ebx
  __int64 v24; // rdx
  __int64 v25; // rcx
  _QWORD *v26; // rdx
  __int64 v27; // rcx
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  const char *v30; // [rsp+28h] [rbp-D8h]
  __int64 *v31; // [rsp+30h] [rbp-D0h] BYREF
  const char *v32; // [rsp+38h] [rbp-C8h] BYREF
  DWORD dwSize; // [rsp+40h] [rbp-C0h] BYREF
  void **v34; // [rsp+48h] [rbp-B8h]
  void *v35; // [rsp+50h] [rbp-B0h] BYREF
  char v36; // [rsp+58h] [rbp-A8h]
  char *v37; // [rsp+60h] [rbp-A0h]
  WCHAR ExeName[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v4 = a4;
  v32 = a4;
  v5 = a3;
  v37 = a3;
  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x167,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\clientidentity.cpp",
      a4);
  v31 = 0;
  v7 = CoGetCallContextOfObject(a2, &GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &v31);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\clientidentity.cpp",
      (const char *)(unsigned int)v7,
      v28);
    if ( v31 )
      (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\clientconnection.cpp",
      (const char *)v8,
      v29);
    return v8;
  }
  if ( !v31 )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x16F,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\clientidentity.cpp",
      (const char *)0x8000FFFFLL,
      (int)"Failed to get ICallingProcessInfo from call context.",
      v30);
    if ( v31 )
      (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
    goto LABEL_17;
  }
  v9 = *v31;
  v10 = (HANDLE *)(Context + 2);
  v34 = (void **)(Context + 2);
  v35 = 0;
  v36 = 1;
  v8 = (*(__int64 (__fastcall **)(__int64 *, __int64, void **))(v9 + 24))(v31, 1049600, &v35);
  if ( v36 )
  {
    v11 = v35;
    v12 = v34;
    v13 = *v34;
    if ( *v34 )
    {
      LastError = GetLastError();
      CloseHandle(v13);
      SetLastError(LastError);
    }
    *v12 = v11;
    v5 = v37;
    v4 = v32;
  }
  if ( (v8 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x176,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\clientidentity.cpp",
      (const char *)v8,
      v28);
    if ( v31 )
      (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
    goto LABEL_17;
  }
  if ( v31 )
    (*(void (__fastcall **)(__int64 *))(*v31 + 16))(v31);
  Context[12] = GetProcessId(*v10);
  dwSize = 260;
  if ( !QueryFullProcessImageNameW(*v10, 0, ExeName, &dwSize) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x5B,
             (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\clientconnection.cpp",
             v17);
  v18 = (char **)(Context + 4);
  v19 = -1;
  do
    ++v19;
  while ( ExeName[v19] );
  if ( v19 > *((_QWORD *)Context + 5) )
  {
    ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
      v18,
      v19,
      v16,
      ExeName);
  }
  else
  {
    if ( *((_QWORD *)Context + 5) <= 7u )
      v20 = (char *)(Context + 4);
    else
      v20 = *v18;
    *((_QWORD *)Context + 4) = v19;
    v21 = 2 * v19;
    memmove_0(v20, ExeName, 2 * v19);
    *(_WORD *)&v20[v21] = 0;
  }
  v22 = (char *)(Context + 26);
  v23 = OwningUser2::GetForUser(v5);
  if ( v23 < 0 )
  {
    v24 = 103;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\clientconnection.cpp",
      (const char *)(unsigned int)v23,
      v28);
    return (unsigned int)v23;
  }
  v32 = (const char *)Context;
  v25 = *(_QWORD *)v22 + 112LL;
  v26 = *(_QWORD **)(*(_QWORD *)v22 + 120LL);
  if ( v26 == *(_QWORD **)(*(_QWORD *)v22 + 128LL) )
  {
    std::vector<ClientConnection2 *>::_Emplace_reallocate<ClientConnection2 * const &>(v25, v26, &v32);
  }
  else
  {
    *v26 = Context;
    *(_QWORD *)(v25 + 8) += 8LL;
  }
  v23 = ClientIdentity2::FindAndRegisterConnection(Context + 26, v4, Context, Context + 18);
  if ( v23 < 0 )
  {
    v24 = 122;
    goto LABEL_32;
  }
  ClientConnection2::StartProcessTracking(Context);
  v32 = (const char *)Context;
  if ( qword_1800B93F8 == qword_1800B9400 )
  {
    std::vector<ClientConnection2 *>::_Emplace_reallocate<ClientConnection2 *>(v27, qword_1800B93F8, &v32);
  }
  else
  {
    *(_QWORD *)qword_1800B93F8 = Context;
    qword_1800B93F8 += 8;
  }
  *(_BYTE *)Context = 1;
  return 0;
}

```

## disassembly

```asm
0x180058654  push    rbp
0x180058656  push    rbx
0x180058657  push    rsi
0x180058658  push    rdi
0x180058659  push    r12
0x18005865b  push    r13
0x18005865d  push    r14
0x18005865f  push    r15
0x180058661  lea     rbp, [rsp-198h]
0x180058669  sub     rsp, 298h
0x180058670  mov     rax, cs:__security_cookie
0x180058677  xor     rax, rsp
0x18005867a  mov     [rbp+1D0h+var_50], rax
0x180058681  mov     r15, r9
0x180058684  mov     [rsp+2D0h+var_298], r9
0x180058689  mov     r14, r8
0x18005868c  mov     [rsp+2D0h+var_270], r8
0x180058691  mov     rax, rdx
0x180058694  mov     rdi, rcx
0x180058697  mov     rcx, [rbp+1D8h]; this
0x18005869e  xor     r12d, r12d
0x1800586a1  test    rdx, rdx
0x1800586a4  jz      loc_1800589AD
0x1800586aa  mov     [rsp+2D0h+var_2A0], r12
0x1800586af  lea     r8, [rsp+2D0h+var_2A0]
0x1800586b4  lea     rdx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541
0x1800586bb  mov     rcx, rax
0x1800586be  call    cs:__imp_CoGetCallContextOfObject
0x1800586c4  mov     esi, eax
0x1800586c6  test    eax, eax
0x1800586c8  jns     short loc_180058702
0x1800586ca  mov     rcx, [rbp+1D8h]; this
0x1800586d1  mov     r9d, eax; char *
0x1800586d4  lea     r8, aOnecoreuapWind_29; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800586db  mov     edx, 16Ah; void *
0x1800586e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800586e5  nop
0x1800586e6  mov     rcx, [rsp+2D0h+var_2A0]
0x1800586eb  test    rcx, rcx
0x1800586ee  jz      short loc_1800586FD
0x1800586f0  mov     rax, [rcx]
0x1800586f3  mov     rax, [rax+10h]
0x1800586f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586fc  nop
0x1800586fd  jmp     loc_1800587F9
0x180058702  mov     rcx, [rsp+2D0h+var_2A0]
0x180058707  test    rcx, rcx
0x18005870a  jnz     short loc_180058755
0x18005870c  mov     rcx, [rbp+1D8h]; this
0x180058713  lea     rax, aFailedToGetIca; "Failed to get ICallingProcessInfo from "...
0x18005871a  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x18005871f  mov     esi, 8000FFFFh
0x180058724  mov     r9d, esi; char *
0x180058727  lea     r8, aOnecoreuapWind_29; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005872e  mov     edx, 16Fh; void *
0x180058733  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180058738  nop
0x180058739  mov     rcx, [rsp+2D0h+var_2A0]
0x18005873e  test    rcx, rcx
0x180058741  jz      short loc_180058750
0x180058743  mov     rax, [rcx]
0x180058746  mov     rax, [rax+10h]
0x18005874a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005874f  nop
0x180058750  jmp     loc_1800587F9
0x180058755  mov     rax, [rcx]
0x180058758  lea     r13, [rdi+8]
0x18005875c  mov     [rsp+2D0h+var_288], r13
0x180058761  mov     [rsp+2D0h+var_280], r12
0x180058766  mov     [rsp+2D0h+var_278], 1
0x18005876b  lea     r8, [rsp+2D0h+var_280]
0x180058770  mov     edx, 100400h
0x180058775  mov     rax, [rax+18h]
0x180058779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005877e  mov     esi, eax
0x180058780  cmp     [rsp+2D0h+var_278], r12b
0x180058785  jz      short loc_1800587C2
0x180058787  mov     r12, [rsp+2D0h+var_280]
0x18005878c  mov     r14, [rsp+2D0h+var_288]
0x180058791  mov     r15, [r14]
0x180058794  test    r15, r15
0x180058797  jz      short loc_1800587B2
0x180058799  call    cs:__imp_GetLastError
0x18005879f  mov     ebx, eax
0x1800587a1  mov     rcx, r15; hObject
0x1800587a4  call    cs:__imp_CloseHandle
0x1800587aa  mov     ecx, ebx; dwErrCode
0x1800587ac  call    cs:__imp_SetLastError
0x1800587b2  mov     [r14], r12
0x1800587b5  mov     r14, [rsp+2D0h+var_270]
0x1800587ba  mov     r15, [rsp+2D0h+var_298]
0x1800587bf  xor     r12d, r12d
0x1800587c2  test    esi, esi
0x1800587c4  jns     short loc_18005881B
0x1800587c6  mov     rcx, [rbp+1D8h]; this
0x1800587cd  mov     r9d, esi; char *
0x1800587d0  lea     r8, aOnecoreuapWind_29; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800587d7  mov     edx, 176h; void *
0x1800587dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800587e1  nop
0x1800587e2  mov     rcx, [rsp+2D0h+var_2A0]
0x1800587e7  test    rcx, rcx
0x1800587ea  jz      short loc_1800587F9
0x1800587ec  mov     rax, [rcx]
0x1800587ef  mov     rax, [rax+10h]
0x1800587f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587f8  nop
0x1800587f9  mov     rcx, [rbp+1D8h]; this
0x180058800  mov     r9d, esi; char *
0x180058803  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005880a  mov     edx, 51h ; 'Q'; void *
0x18005880f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058814  mov     eax, esi
0x180058816  jmp     loc_18005898A
0x18005881b  mov     rcx, [rsp+2D0h+var_2A0]
0x180058820  test    rcx, rcx
0x180058823  jz      short loc_180058832
0x180058825  mov     rax, [rcx]
0x180058828  mov     rax, [rax+10h]
0x18005882c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058831  nop
0x180058832  mov     rcx, [r13+0]; Process
0x180058836  call    cs:__imp_GetProcessId
0x18005883c  mov     [rdi+30h], eax
0x18005883f  mov     [rsp+2D0h+dwSize], 104h
0x180058847  lea     r9, [rsp+2D0h+dwSize]; lpdwSize
0x18005884c  lea     r8, [rsp+2D0h+ExeName]; lpExeName
0x180058851  xor     edx, edx; dwFlags
0x180058853  mov     rcx, [r13+0]; hProcess
0x180058857  call    cs:__imp_QueryFullProcessImageNameW
0x18005885d  test    eax, eax
0x18005885f  jnz     short loc_18005887C
0x180058861  mov     rcx, [rbp+1D8h]; this
0x180058868  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005886f  lea     edx, [rax+5Bh]; void *
0x180058872  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180058877  jmp     loc_18005898A
0x18005887c  lea     rcx, [rdi+10h]
0x180058880  lea     rax, [rsp+2D0h+ExeName]
0x180058885  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180058889  inc     rdx
0x18005888c  cmp     [rax+rdx*2], r12w
0x180058891  jnz     short loc_180058889
0x180058893  cmp     rdx, [rcx+18h]
0x180058897  ja      short loc_1800588C7
0x180058899  cmp     qword ptr [rcx+18h], 7
0x18005889e  jbe     short loc_1800588A5
0x1800588a0  mov     rsi, [rcx]
0x1800588a3  jmp     short loc_1800588A8
0x1800588a5  mov     rsi, rcx
0x1800588a8  mov     [rcx+10h], rdx
0x1800588ac  lea     rbx, [rdx+rdx]
0x1800588b0  mov     r8, rbx; Size
0x1800588b3  lea     rdx, [rsp+2D0h+ExeName]; Src
0x1800588b8  mov     rcx, rsi; void *
0x1800588bb  call    memmove_0
0x1800588c0  mov     [rbx+rsi], r12w
0x1800588c5  jmp     short loc_1800588D1
0x1800588c7  lea     r9, [rsp+2D0h+ExeName]
0x1800588cc  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV23@QEB_W_K@Z@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@_W@01@AEAAAEAV01@QEB_W0@Z@PEB_W@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *>(unsigned __int64,`std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)'::`2'::_lambda_1_,wchar_t const *)
0x1800588d1  lea     rsi, [rdi+68h]
0x1800588d5  mov     rdx, rsi
0x1800588d8  mov     rcx, r14; char *
0x1800588db  call    ?GetForUser@OwningUser2@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$shared_ptr@VOwningUser2@@@3@@Z; OwningUser2::GetForUser(std::wstring const &,std::shared_ptr<OwningUser2> &)
0x1800588e0  mov     ebx, eax
0x1800588e2  test    eax, eax
0x1800588e4  jns     short loc_180058908
0x1800588e6  mov     edx, 67h ; 'g'; void *
0x1800588eb  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800588f2  mov     r9d, ebx; char *
0x1800588f5  mov     rcx, [rbp+1D8h]; this
0x1800588fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058901  mov     eax, ebx
0x180058903  jmp     loc_18005898A
0x180058908  mov     [rsp+2D0h+var_298], rdi
0x18005890d  mov     rcx, [rsi]
0x180058910  add     rcx, 70h ; 'p'
0x180058914  mov     rdx, [rcx+8]
0x180058918  cmp     rdx, [rcx+10h]
0x18005891c  jz      short loc_180058928
0x18005891e  mov     [rdx], rdi
0x180058921  add     qword ptr [rcx+8], 8
0x180058926  jmp     short loc_180058932
0x180058928  lea     r8, [rsp+2D0h+var_298]
0x18005892d  call    ??$_Emplace_reallocate@AEBQEAVClientConnection2@@@?$vector@PEAVClientConnection2@@V?$allocator@PEAVClientConnection2@@@std@@@std@@AEAAPEAPEAVClientConnection2@@QEAPEAV2@AEBQEAV2@@Z; std::vector<ClientConnection2 *>::_Emplace_reallocate<ClientConnection2 * const &>(ClientConnection2 * * const,ClientConnection2 * const &)
0x180058932  lea     r9, [rdi+48h]
0x180058936  mov     r8, rdi
0x180058939  mov     rdx, r15
0x18005893c  mov     rcx, rsi
0x18005893f  call    ?FindAndRegisterConnection@ClientIdentity2@@SAJAEAV?$shared_ptr@VOwningUser2@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@PEAVClientConnection2@@AEAV?$shared_ptr@VClientIdentity2@@@3@@Z; ClientIdentity2::FindAndRegisterConnection(std::shared_ptr<OwningUser2> &,std::wstring const &,ClientConnection2 *,std::shared_ptr<ClientIdentity2> &)
0x180058944  mov     ebx, eax
0x180058946  test    eax, eax
0x180058948  jns     short loc_180058951
0x18005894a  mov     edx, 7Ah ; 'z'
0x18005894f  jmp     short loc_1800588EB
0x180058951  mov     rcx, rdi; Context
0x180058954  call    ?StartProcessTracking@ClientConnection2@@AEAAJXZ; ClientConnection2::StartProcessTracking(void)
0x180058959  mov     [rsp+2D0h+var_298], rdi
0x18005895e  mov     rdx, cs:qword_1800B93F8
0x180058965  cmp     rdx, cs:qword_1800B9400
0x18005896c  jz      short loc_18005897B
0x18005896e  mov     [rdx], rdi
0x180058971  add     cs:qword_1800B93F8, 8
0x180058979  jmp     short loc_180058985
0x18005897b  lea     r8, [rsp+2D0h+var_298]
0x180058980  call    ??$_Emplace_reallocate@PEAVClientConnection2@@@?$vector@PEAVClientConnection2@@V?$allocator@PEAVClientConnection2@@@std@@@std@@AEAAPEAPEAVClientConnection2@@QEAPEAV2@$$QEAPEAV2@@Z; std::vector<ClientConnection2 *>::_Emplace_reallocate<ClientConnection2 *>(ClientConnection2 * * const,ClientConnection2 * &&)
0x180058985  mov     byte ptr [rdi], 1
0x180058988  xor     eax, eax
0x18005898a  mov     rcx, [rbp+1D0h+var_50]
0x180058991  xor     rcx, rsp; StackCookie
0x180058994  call    __security_check_cookie
0x180058999  add     rsp, 298h
0x1800589a0  pop     r15
0x1800589a2  pop     r14
0x1800589a4  pop     r13
0x1800589a6  pop     r12
0x1800589a8  pop     rdi
0x1800589a9  pop     rsi
0x1800589aa  pop     rbx
0x1800589ab  pop     rbp
0x1800589ac  retn
0x1800589ad  lea     r8, aOnecoreuapWind_29; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800589b4  mov     edx, 167h; void *
0x1800589b9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
