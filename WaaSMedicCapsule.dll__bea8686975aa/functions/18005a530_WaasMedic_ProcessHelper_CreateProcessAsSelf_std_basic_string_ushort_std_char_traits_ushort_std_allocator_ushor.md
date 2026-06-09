# WaasMedic::ProcessHelper::CreateProcessAsSelf(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18005a530`
- end: `0x18005aae7`
- name: `?CreateProcessAsSelf@ProcessHelper@WaasMedic@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `1463`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004f550`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180007590`
- `0x180009a54`
- `0x18000ab48`
- `0x18000b308`
- `0x180026920`
- `0x18005a490`
- `0x18005a530`
- `0x18005aaf0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18005a829`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18005a8ba`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18005a829`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18005a8ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a619`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a63c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a6cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a6ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a7a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a7c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a87d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a8a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a917`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a93a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a9a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a9dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a9fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a619`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a63c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a6cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a6ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a7a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a7c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a87d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a8a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a917`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a93a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a9a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a9dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a9fc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18005a955`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!AllowSetForegroundWindow` at `0x18005a955`

## string_xrefs

- `0x18005a5ee`: `Failed to expand directory: %ws`
- `0x18005a966`: `CreateProcessAsSelf failed to AllowSetForegroundWindow`
- `0x18005a859`: `CreateProcessAsSelf failed to CreateProcess with application: %ws, cmdline: %ws`
- `0x18005a8f3`: `CreateProcessAsSelf failed to CreateProcess with application: {}, cmdline: {}`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::ProcessHelper::CreateProcessAsSelf(const WCHAR *a1, _QWORD *a2, const WCHAR *a3)
{
  const WCHAR *v6; // rcx
  unsigned int LastErrorMsg; // ebx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int v10; // r8d
  const char *v11; // r9
  const WCHAR *lpCurrentDirectory; // rsi
  const WCHAR *v13; // rcx
  unsigned int v14; // r8d
  const char *v15; // r9
  unsigned int v16; // r8d
  const char *v17; // r9
  char **v18; // rdi
  __int64 v19; // rax
  __int64 v20; // rdx
  WCHAR *v21; // r8
  WCHAR v22; // cx
  WCHAR *v23; // rcx
  unsigned int v24; // r8d
  const char *v25; // r9
  unsigned int v26; // r8d
  const char *v27; // r9
  const char *v28; // rax
  unsigned int v29; // r8d
  const char *v30; // r9
  unsigned int v31; // r8d
  const char *v32; // r9
  unsigned int v33; // r8d
  const char *v34; // r9
  unsigned int v35; // r8d
  const char *v36; // r9
  unsigned int v37; // r8d
  const char *v38; // r9
  unsigned int v39; // r8d
  const char *v40; // r9
  unsigned int v42; // r8d
  const char *v43; // r9
  unsigned int v44; // r8d
  const char *v45; // r9
  int bInheritHandles; // [rsp+20h] [rbp-E0h]
  const char *bInheritHandlesa; // [rsp+20h] [rbp-E0h]
  struct _PROCESS_INFORMATION hObject; // [rsp+50h] [rbp-B0h] BYREF
  char v49[16]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v50; // [rsp+80h] [rbp-80h]
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  char *v52[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v53; // [rsp+110h] [rbp+10h]
  __int128 v54; // [rsp+120h] [rbp+20h] BYREF
  __int64 v55; // [rsp+130h] [rbp+30h]
  unsigned __int64 v56; // [rsp+138h] [rbp+38h]
  WCHAR CommandLine[264]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+288h]

  v54 = 0;
  v55 = 0;
  v56 = 7;
  LOWORD(v54) = 0;
  *(_OWORD *)v52 = 0;
  *(_QWORD *)&v53 = 0;
  *((_QWORD *)&v53 + 1) = 7;
  LOWORD(v52[0]) = 0;
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  memset(&hObject, 0, sizeof(hObject));
  if ( *((_QWORD *)a3 + 3) <= 7u )
    v6 = a3;
  else
    v6 = *(const WCHAR **)a3;
  LastErrorMsg = WaasMedic::ProcessHelper::ExpandDirectory(v6);
  if ( (LastErrorMsg & 0x80000000) != 0 )
  {
    if ( *((_QWORD *)a3 + 3) > 7u )
      a3 = *(const WCHAR **)a3;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x39,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\processhelper.cpp",
      (const char *)LastErrorMsg,
      (int)"Failed to expand directory: %ws",
      (const char *)a3);
    if ( hObject.hProcess && !CloseHandle(hObject.hProcess) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
    if ( hObject.hThread )
    {
      if ( !CloseHandle(hObject.hThread) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
    }
LABEL_65:
    std::wstring::~wstring(v52);
    std::wstring::~wstring(&v54);
    return LastErrorMsg;
  }
  if ( v55 )
  {
    lpCurrentDirectory = (const WCHAR *)&v54;
    if ( v56 > 7 )
      lpCurrentDirectory = (const WCHAR *)v54;
  }
  else
  {
    lpCurrentDirectory = 0;
  }
  if ( *((_QWORD *)a1 + 3) <= 7u )
    v13 = a1;
  else
    v13 = *(const WCHAR **)a1;
  LastErrorMsg = WaasMedic::ProcessHelper::ExpandDirectory(v13);
  if ( (LastErrorMsg & 0x80000000) != 0 )
  {
    if ( *((_QWORD *)a1 + 3) > 7u )
      a1 = *(const WCHAR **)a1;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\processhelper.cpp",
      (const char *)LastErrorMsg,
      (int)"Failed to expand application: %ws",
      (const char *)a1);
    if ( hObject.hProcess && !CloseHandle(hObject.hProcess) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
    if ( hObject.hThread && !CloseHandle(hObject.hThread) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v16, v17);
    goto LABEL_65;
  }
  if ( (_QWORD)v53 )
  {
    v18 = v52;
    if ( *((_QWORD *)&v53 + 1) > 7u )
      v18 = (char **)v52[0];
  }
  else
  {
    v18 = 0;
  }
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  v19 = 2147483646;
  v20 = 260;
  v21 = CommandLine;
  do
  {
    if ( !v19 )
      break;
    v22 = *(_WORD *)a2;
    if ( !*(_WORD *)a2 )
      break;
    a2 = (_QWORD *)((char *)a2 + 2);
    *v21++ = v22;
    --v19;
    --v20;
  }
  while ( v20 );
  LastErrorMsg = v20 == 0 ? 0x8007007A : 0;
  v23 = v21 - 1;
  if ( v20 )
    v23 = v21;
  *v23 = 0;
  if ( !v20 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\processhelper.cpp",
      (const char *)LastErrorMsg,
      bInheritHandles);
    if ( hObject.hProcess && !CloseHandle(hObject.hProcess) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v24, v25);
    if ( hObject.hThread && !CloseHandle(hObject.hThread) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v26, v27);
    goto LABEL_65;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CanvasPluginBugFixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CanvasPluginBugFixes>::GetImpl'::`2'::impl) )
  {
    if ( !CreateProcessW((LPCWSTR)v18, CommandLine, 0, 0, 0, 0x4000400u, 0, lpCurrentDirectory, &StartupInfo, &hObject) )
    {
      v28 = (const char *)v52;
      if ( *((_QWORD *)&v53 + 1) > 7u )
        v28 = v52[0];
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x50,
                       (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\processhelper.cpp",
                       "CreateProcessAsSelf failed to CreateProcess with application: %ws, cmdline: %ws",
                       v28,
                       CommandLine);
      if ( hObject.hProcess && !CloseHandle(hObject.hProcess) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v29, v30);
      if ( hObject.hThread && !CloseHandle(hObject.hThread) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v31, v32);
      goto LABEL_65;
    }
  }
  else if ( !CreateProcessW(
               (LPCWSTR)v18,
               CommandLine,
               0,
               0,
               0,
               0x4000400u,
               0,
               lpCurrentDirectory,
               &StartupInfo,
               &hObject) )
  {
    *(_OWORD *)v49 = *(_OWORD *)v52;
    v50 = v53;
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x62,
                     (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\processhelper.cpp",
                     "CreateProcessAsSelf failed to CreateProcess with application: {}, cmdline: {}",
                     v49,
                     CommandLine);
    if ( hObject.hProcess && !CloseHandle(hObject.hProcess) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v33, v34);
    if ( hObject.hThread && !CloseHandle(hObject.hThread) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v35, v36);
    goto LABEL_65;
  }
  if ( !AllowSetForegroundWindow(hObject.dwProcessId) )
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0x65,
                     (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\processhelper.cpp",
                     "CreateProcessAsSelf failed to AllowSetForegroundWindow",
                     bInheritHandlesa);
    if ( hObject.hProcess && !CloseHandle(hObject.hProcess) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v37, v38);
    if ( hObject.hThread && !CloseHandle(hObject.hThread) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v39, v40);
    goto LABEL_65;
  }
  if ( hObject.hProcess && !CloseHandle(hObject.hProcess) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v42, v43);
  if ( hObject.hThread && !CloseHandle(hObject.hThread) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v44, v45);
  std::wstring::~wstring(v52);
  std::wstring::~wstring(&v54);
  return 0;
}

```

## disassembly

```asm
0x18005a530  mov     [rsp-8+arg_8], rbx
0x18005a535  mov     [rsp-8+arg_18], rsi
0x18005a53a  push    rbp
0x18005a53b  push    rdi
0x18005a53c  push    r12
0x18005a53e  push    r14
0x18005a540  push    r15
0x18005a542  lea     rbp, [rsp-260h]
0x18005a54a  sub     rsp, 360h
0x18005a551  mov     rax, cs:__security_cookie
0x18005a558  xor     rax, rsp
0x18005a55b  mov     [rbp+280h+var_30], rax
0x18005a562  mov     rsi, r8
0x18005a565  mov     r14, rdx
0x18005a568  mov     rdi, rcx
0x18005a56b  xorps   xmm0, xmm0
0x18005a56e  movups  [rbp+280h+var_260], xmm0
0x18005a572  xor     r15d, r15d
0x18005a575  mov     [rbp+280h+var_250], r15
0x18005a579  lea     r12d, [r15+7]
0x18005a57d  mov     [rbp+280h+var_248], r12
0x18005a581  mov     word ptr [rbp+280h+var_260], r15w
0x18005a586  movups  xmmword ptr [rbp+280h+var_280], xmm0
0x18005a58a  mov     qword ptr [rbp+280h+var_270], r15
0x18005a58e  mov     qword ptr [rbp+280h+var_270+8], r12
0x18005a592  mov     word ptr [rbp+280h+var_280], r15w
0x18005a597  xor     edx, edx; Val
0x18005a599  lea     r8d, [r15+64h]; Size
0x18005a59d  lea     rcx, [rbp+280h+StartupInfo+4]; void *
0x18005a5a1  call    memset_0
0x18005a5a6  mov     [rbp+280h+StartupInfo.cb], 68h ; 'h'
0x18005a5ad  xorps   xmm0, xmm0
0x18005a5b0  xor     eax, eax
0x18005a5b2  movups  xmmword ptr [rsp+380h+hObject], xmm0
0x18005a5b7  mov     qword ptr [rsp+380h+dwProcessId], rax
0x18005a5bc  cmp     [rsi+18h], r12
0x18005a5c0  jbe     short loc_18005A5C7
0x18005a5c2  mov     rcx, [rsi]
0x18005a5c5  jmp     short loc_18005A5CA
0x18005a5c7  mov     rcx, rsi; lpSrc
0x18005a5ca  lea     rdx, [rbp+280h+var_260]
0x18005a5ce  call    ?ExpandDirectory@ProcessHelper@WaasMedic@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaasMedic::ProcessHelper::ExpandDirectory(ushort const *,std::wstring &)
0x18005a5d3  mov     ebx, eax
0x18005a5d5  test    eax, eax
0x18005a5d7  jns     short loc_18005A656
0x18005a5d9  cmp     [rsi+18h], r12
0x18005a5dd  jbe     short loc_18005A5E2
0x18005a5df  mov     rsi, [rsi]
0x18005a5e2  mov     rcx, [rbp+288h]; this
0x18005a5e9  mov     qword ptr [rsp+380h+dwCreationFlags], rsi; char *
0x18005a5ee  lea     rax, aFailedToExpand_5; "Failed to expand directory: %ws"
0x18005a5f5  mov     qword ptr [rsp+380h+bInheritHandles], rax; int
0x18005a5fa  mov     r9d, ebx; char *
0x18005a5fd  lea     r8, aOnecoreEnduser_35; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005a604  mov     edx, 39h ; '9'; void *
0x18005a609  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005a60e  nop
0x18005a60f  mov     rcx, [rsp+380h+hObject]; hObject
0x18005a614  test    rcx, rcx
0x18005a617  jz      short loc_18005A62E
0x18005a619  call    cs:__imp_CloseHandle
0x18005a61f  mov     rcx, [rbp+288h]; this
0x18005a626  test    eax, eax
0x18005a628  jz      loc_18005AA8F
0x18005a62e  mov     rcx, [rsp+380h+hObject+8]; hObject
0x18005a633  test    rcx, rcx
0x18005a636  jz      loc_18005A9BC
0x18005a63c  call    cs:__imp_CloseHandle
0x18005a642  mov     rcx, [rbp+288h]; this
0x18005a649  test    eax, eax
0x18005a64b  jz      loc_18005AA58
0x18005a651  jmp     loc_18005A9BC
0x18005a656  cmp     [rbp+280h+var_250], r15
0x18005a65a  jnz     short loc_18005A661
0x18005a65c  mov     rsi, r15
0x18005a65f  jmp     short loc_18005A66E
0x18005a661  lea     rsi, [rbp+280h+var_260]
0x18005a665  cmp     [rbp+280h+var_248], r12
0x18005a669  cmova   rsi, qword ptr [rbp+280h+var_260]
0x18005a66e  cmp     [rdi+18h], r12
0x18005a672  jbe     short loc_18005A679
0x18005a674  mov     rcx, [rdi]
0x18005a677  jmp     short loc_18005A67C
0x18005a679  mov     rcx, rdi; lpSrc
0x18005a67c  lea     rdx, [rbp+280h+var_280]
0x18005a680  call    ?ExpandDirectory@ProcessHelper@WaasMedic@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaasMedic::ProcessHelper::ExpandDirectory(ushort const *,std::wstring &)
0x18005a685  mov     ebx, eax
0x18005a687  test    eax, eax
0x18005a689  jns     short loc_18005A708
0x18005a68b  cmp     [rdi+18h], r12
0x18005a68f  jbe     short loc_18005A694
0x18005a691  mov     rdi, [rdi]
0x18005a694  mov     rcx, [rbp+288h]; this
0x18005a69b  mov     qword ptr [rsp+380h+dwCreationFlags], rdi; char *
0x18005a6a0  lea     rax, aFailedToExpand; "Failed to expand application: %ws"
0x18005a6a7  mov     qword ptr [rsp+380h+bInheritHandles], rax; int
0x18005a6ac  mov     r9d, ebx; char *
0x18005a6af  lea     r8, aOnecoreEnduser_35; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005a6b6  mov     edx, 3Bh ; ';'; void *
0x18005a6bb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005a6c0  nop
0x18005a6c1  mov     rcx, [rsp+380h+hObject]; hObject
0x18005a6c6  test    rcx, rcx
0x18005a6c9  jz      short loc_18005A6E0
0x18005a6cb  call    cs:__imp_CloseHandle
0x18005a6d1  mov     rcx, [rbp+288h]; this
0x18005a6d8  test    eax, eax
0x18005a6da  jz      loc_18005AA9A
0x18005a6e0  mov     rcx, [rsp+380h+hObject+8]; hObject
0x18005a6e5  test    rcx, rcx
0x18005a6e8  jz      loc_18005A9BC
0x18005a6ee  call    cs:__imp_CloseHandle
0x18005a6f4  mov     rcx, [rbp+288h]; this
0x18005a6fb  test    eax, eax
0x18005a6fd  jz      loc_18005AA63
0x18005a703  jmp     loc_18005A9BC
0x18005a708  cmp     qword ptr [rbp+280h+var_270], r15
0x18005a70c  jnz     short loc_18005A713
0x18005a70e  mov     rdi, r15
0x18005a711  jmp     short loc_18005A720
0x18005a713  lea     rdi, [rbp+280h+var_280]
0x18005a717  cmp     qword ptr [rbp+280h+var_270+8], r12
0x18005a71b  cmova   rdi, [rbp+280h+var_280]
0x18005a720  cmp     [r14+18h], r12
0x18005a724  jbe     short loc_18005A729
0x18005a726  mov     r14, [r14]
0x18005a729  mov     eax, 7FFFFFFEh
0x18005a72e  mov     edx, 104h
0x18005a733  lea     r8, [rbp+280h+CommandLine]
0x18005a737  test    rax, rax
0x18005a73a  jz      short loc_18005A75A
0x18005a73c  movzx   ecx, word ptr [r14]
0x18005a740  test    cx, cx
0x18005a743  jz      short loc_18005A75A
0x18005a745  add     r14, 2
0x18005a749  mov     [r8], cx
0x18005a74d  add     r8, 2
0x18005a751  dec     rax
0x18005a754  sub     rdx, 1
0x18005a758  jnz     short loc_18005A737
0x18005a75a  mov     rax, rdx
0x18005a75d  neg     rax
0x18005a760  sbb     ebx, ebx
0x18005a762  not     ebx
0x18005a764  and     ebx, 8007007Ah
0x18005a76a  lea     rcx, [r8-2]
0x18005a76e  test    rdx, rdx
0x18005a771  cmovnz  rcx, r8
0x18005a775  mov     [rcx], r15w
0x18005a779  jnz     short loc_18005A7DE
0x18005a77b  mov     rcx, [rbp+288h]; this
0x18005a782  mov     r9d, ebx; char *
0x18005a785  lea     r8, aOnecoreEnduser_35; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005a78c  mov     edx, 3Eh ; '>'; void *
0x18005a791  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005a796  nop
0x18005a797  mov     rcx, [rsp+380h+hObject]; hObject
0x18005a79c  test    rcx, rcx
0x18005a79f  jz      short loc_18005A7B6
0x18005a7a1  call    cs:__imp_CloseHandle
0x18005a7a7  mov     rcx, [rbp+288h]; this
0x18005a7ae  test    eax, eax
0x18005a7b0  jz      loc_18005AAA5
0x18005a7b6  mov     rcx, [rsp+380h+hObject+8]; hObject
0x18005a7bb  test    rcx, rcx
0x18005a7be  jz      loc_18005A9BC
0x18005a7c4  call    cs:__imp_CloseHandle
0x18005a7ca  mov     rcx, [rbp+288h]; this
0x18005a7d1  test    eax, eax
0x18005a7d3  jz      loc_18005AA6E
0x18005a7d9  jmp     loc_18005A9BC
0x18005a7de  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CanvasPluginBugFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CanvasPluginBugFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CanvasPluginBugFixes> `wil::Feature<__WilFeatureTraits_Feature_CanvasPluginBugFixes>::GetImpl(void)'::`2'::impl
0x18005a7e5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CanvasPluginBugFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CanvasPluginBugFixes>::__private_IsEnabled(void)
0x18005a7ea  xor     r9d, r9d; lpThreadAttributes
0x18005a7ed  xor     r8d, r8d; lpProcessAttributes
0x18005a7f0  lea     rdx, [rbp+280h+CommandLine]; lpCommandLine
0x18005a7f4  mov     rcx, rdi; lpApplicationName
0x18005a7f7  test    al, al
0x18005a7f9  lea     rax, [rsp+380h+hObject]
0x18005a7fe  mov     [rsp+380h+lpProcessInformation], rax; lpProcessInformation
0x18005a803  lea     rax, [rbp+280h+StartupInfo]
0x18005a807  mov     [rsp+380h+lpStartupInfo], rax; lpStartupInfo
0x18005a80c  mov     [rsp+380h+lpCurrentDirectory], rsi; lpCurrentDirectory
0x18005a811  mov     [rsp+380h+lpEnvironment], r15; lpEnvironment
0x18005a816  mov     [rsp+380h+dwCreationFlags], 4000400h; dwCreationFlags
0x18005a81e  mov     [rsp+380h+bInheritHandles], r15d; char *
0x18005a823  jz      loc_18005A8BA
0x18005a829  call    cs:__imp_CreateProcessW
0x18005a82f  test    eax, eax
0x18005a831  jnz     loc_18005A951
0x18005a837  lea     rax, [rbp+280h+var_280]
0x18005a83b  cmp     qword ptr [rbp+280h+var_270+8], r12
0x18005a83f  cmova   rax, [rbp+280h+var_280]
0x18005a844  mov     rcx, [rbp+288h]; this
0x18005a84b  lea     rdx, [rbp+280h+CommandLine]
0x18005a84f  mov     qword ptr [rsp+380h+dwCreationFlags], rdx
0x18005a854  mov     qword ptr [rsp+380h+bInheritHandles], rax; char *
0x18005a859  lea     r9, aCreateprocessa; "CreateProcessAsSelf failed to CreatePro"...
0x18005a860  lea     r8, aOnecoreEnduser_35; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005a867  mov     edx, 50h ; 'P'; void *
0x18005a86c  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18005a871  mov     ebx, eax
0x18005a873  mov     rcx, [rsp+380h+hObject]; hObject
0x18005a878  test    rcx, rcx
0x18005a87b  jz      short loc_18005A892
0x18005a87d  call    cs:__imp_CloseHandle
0x18005a883  mov     rcx, [rbp+288h]; this
0x18005a88a  test    eax, eax
0x18005a88c  jz      loc_18005AAB0
0x18005a892  mov     rcx, [rsp+380h+hObject+8]; hObject
0x18005a897  test    rcx, rcx
0x18005a89a  jz      loc_18005A9BC
0x18005a8a0  call    cs:__imp_CloseHandle
0x18005a8a6  mov     rcx, [rbp+288h]; this
0x18005a8ad  test    eax, eax
0x18005a8af  jz      loc_18005AA79
0x18005a8b5  jmp     loc_18005A9BC
0x18005a8ba  call    cs:__imp_CreateProcessW
0x18005a8c0  test    eax, eax
0x18005a8c2  jnz     loc_18005A951
0x18005a8c8  movups  xmm0, xmmword ptr [rbp+280h+var_280]
0x18005a8cc  movaps  xmmword ptr [rsp+380h+var_310], xmm0
0x18005a8d1  movups  xmm1, [rbp+280h+var_270]
0x18005a8d5  movaps  [rbp+280h+var_300], xmm1
0x18005a8d9  mov     rcx, [rbp+288h]; this
0x18005a8e0  lea     rax, [rbp+280h+CommandLine]
0x18005a8e4  mov     qword ptr [rsp+380h+dwCreationFlags], rax
0x18005a8e9  lea     rax, [rsp+380h+var_310]
0x18005a8ee  mov     qword ptr [rsp+380h+bInheritHandles], rax; char *
0x18005a8f3  lea     r9, aCreateprocessa_0; "CreateProcessAsSelf failed to CreatePro"...
0x18005a8fa  lea     r8, aOnecoreEnduser_35; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005a901  mov     edx, 62h ; 'b'; void *
0x18005a906  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18005a90b  mov     ebx, eax
0x18005a90d  mov     rcx, [rsp+380h+hObject]; hObject
0x18005a912  test    rcx, rcx
0x18005a915  jz      short loc_18005A92C
0x18005a917  call    cs:__imp_CloseHandle
0x18005a91d  mov     rcx, [rbp+288h]; this
0x18005a924  test    eax, eax
0x18005a926  jz      loc_18005AABB
0x18005a92c  mov     rcx, [rsp+380h+hObject+8]; hObject
0x18005a931  test    rcx, rcx
0x18005a934  jz      loc_18005A9BC
0x18005a93a  call    cs:__imp_CloseHandle
0x18005a940  mov     rcx, [rbp+288h]; this
0x18005a947  test    eax, eax
0x18005a949  jz      loc_18005AA84
0x18005a94f  jmp     short loc_18005A9BC
0x18005a951  mov     ecx, [rsp+380h+dwProcessId]; dwProcessId
0x18005a955  call    cs:__imp_AllowSetForegroundWindow
0x18005a95b  test    eax, eax
0x18005a95d  jnz     short loc_18005A9D3
0x18005a95f  mov     rcx, [rbp+288h]; this
0x18005a966  lea     r9, aCreateprocessa_1; "CreateProcessAsSelf failed to AllowSetF"...
0x18005a96d  lea     r8, aOnecoreEnduser_35; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005a974  lea     edx, [rax+65h]; void *
0x18005a977  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18005a97c  mov     ebx, eax
0x18005a97e  mov     rcx, [rsp+380h+hObject]; hObject
0x18005a983  test    rcx, rcx
0x18005a986  jz      short loc_18005A99D
0x18005a988  call    cs:__imp_CloseHandle
0x18005a98e  mov     rcx, [rbp+288h]; this
0x18005a995  test    eax, eax
0x18005a997  jz      loc_18005AAC6
0x18005a99d  mov     rcx, [rsp+380h+hObject+8]; hObject
0x18005a9a2  test    rcx, rcx
0x18005a9a5  jz      short loc_18005A9BC
0x18005a9a7  call    cs:__imp_CloseHandle
0x18005a9ad  mov     rcx, [rbp+288h]; this
0x18005a9b4  test    eax, eax
0x18005a9b6  jz      loc_18005AAD1
0x18005a9bc  lea     rcx, [rbp+280h+var_280]; void *
0x18005a9c0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005a9c5  nop
0x18005a9c6  lea     rcx, [rbp+280h+var_260]; void *
0x18005a9ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005a9cf  mov     eax, ebx
0x18005a9d1  jmp     short loc_18005AA22
0x18005a9d3  mov     rcx, [rsp+380h+hObject]; hObject
0x18005a9d8  test    rcx, rcx
0x18005a9db  jz      short loc_18005A9F2
0x18005a9dd  call    cs:__imp_CloseHandle
0x18005a9e3  mov     rcx, [rbp+288h]; this
0x18005a9ea  test    eax, eax
0x18005a9ec  jz      loc_18005AADC
0x18005a9f2  mov     rcx, [rsp+380h+hObject+8]; hObject
0x18005a9f7  test    rcx, rcx
0x18005a9fa  jz      short loc_18005AA0D
0x18005a9fc  call    cs:__imp_CloseHandle
0x18005aa02  mov     rcx, [rbp+288h]; this
0x18005aa09  test    eax, eax
0x18005aa0b  jz      short loc_18005AA4D
0x18005aa0d  lea     rcx, [rbp+280h+var_280]; void *
0x18005aa11  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005aa16  nop
0x18005aa17  lea     rcx, [rbp+280h+var_260]; void *
0x18005aa1b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005aa20  xor     eax, eax
  ... truncated ...
```
