# Windows::UI::Composition::Visual::SystemOnly::SetInputWindow(HWND__ *)

- ea: `0x180117640`
- end: `0x1801177f8`
- name: `?SetInputWindow@SystemOnly@Visual@Composition@UI@Windows@@UEAAJPEAUHWND__@@@Z`
- size: `440`
- prototype: `int(Windows::UI::Composition::Visual::SystemOnly *__hidden this, HWND)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180012da0`
- `0x18001358c`
- `0x180036f90`
- `0x18005509c`
- `0x1800ec4d8`
- `0x1800f6f10`
- `0x1801173c0`
- `0x180117640`

## import_xrefs

- `win32u!NtCreateCompositionInputSink` at `0x180117766`
- `win32u!NtCreateCompositionInputSink` at `0x180117766`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18011768e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18011768e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x1801176c3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindow` at `0x1801176c3`

## string_xrefs

- `0x180117683`: `The given object has already been closed / disposed and may no longer be used.`
- `0x1801176a7`: `onecoreuap\windows\dwm\dcomp\winrtnested\global\wrtvisualg.cpp`
- `0x180117774`: `onecoreuap\windows\dwm\dcomp\winrtnested\global\wrtvisualg.cpp`
- `0x1801177ad`: `onecoreuap\windows\dwm\dcomp\winrtnested\global\wrtvisualg.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::Visual::SystemOnly::SetInputWindow(
        Windows::UI::Composition::Visual::SystemOnly *this,
        HWND a2)
{
  Windows::UI::Composition::VisualCommon *v2; // rdi
  Microsoft::WRL2::ContextSession *v4; // rsi
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v7; // eax
  int v8; // eax
  void *v10; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v11; // [rsp+28h] [rbp-D8h]
  __int64 v12; // [rsp+60h] [rbp-A0h] BYREF
  int v13; // [rsp+68h] [rbp-98h]
  int v14; // [rsp+6Ch] [rbp-94h]
  HWND v15; // [rsp+70h] [rbp-90h]
  __int128 v16; // [rsp+78h] [rbp-88h]
  __int128 v17; // [rsp+88h] [rbp-78h]
  __int64 v18; // [rsp+98h] [rbp-68h]
  int v19; // [rsp+A0h] [rbp-60h]
  int v20; // [rsp+A4h] [rbp-5Ch]
  HWND v21; // [rsp+A8h] [rbp-58h]
  __int128 v22; // [rsp+B0h] [rbp-50h]
  __int128 v23; // [rsp+C0h] [rbp-40h]
  __int64 v24; // [rsp+D0h] [rbp-30h]
  int v25; // [rsp+D8h] [rbp-28h]
  int v26; // [rsp+DCh] [rbp-24h]
  HWND v27; // [rsp+E0h] [rbp-20h]
  __int128 v28; // [rsp+E8h] [rbp-18h]
  __int128 v29; // [rsp+F8h] [rbp-8h]
  __int64 v30; // [rsp+108h] [rbp+8h]
  int v31; // [rsp+110h] [rbp+10h]
  int v32; // [rsp+114h] [rbp+14h]
  HWND v33; // [rsp+118h] [rbp+18h]
  __int128 v34; // [rsp+120h] [rbp+20h]
  __int128 v35; // [rsp+130h] [rbp+30h]
  __int64 v36; // [rsp+140h] [rbp+40h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v2 = (Windows::UI::Composition::Visual::SystemOnly *)((char *)this - 304);
  v4 = (Microsoft::WRL2::ContextSession *)*((_QWORD *)this - 35);
  Microsoft::WRL2::ContextSession::BeginApiEntry(v4);
  if ( (*((_BYTE *)v2 + 48) & 2) == 0 )
  {
    v5 = -2147483629;
    RoOriginateErrorW(
      2147483667LL,
      0,
      L"The given object has already been closed / disposed and may no longer be used.");
    goto LABEL_14;
  }
  if ( !a2 )
  {
    v6 = 275;
LABEL_5:
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\global\\wrtvisualg.cpp",
      (const char *)0x80070057LL,
      (int)v10);
    goto LABEL_14;
  }
  if ( !IsWindow(a2) )
  {
    v6 = 276;
    goto LABEL_5;
  }
  v12 = 232;
  v25 = 2;
  v11 = 0;
  v30 = 0;
  v36 = 0;
  v18 = 0;
  v24 = 0;
  v10 = 0;
  v26 = 0;
  v32 = 0;
  v14 = 0;
  v20 = 0;
  v27 = a2;
  v28 = 0;
  v31 = 2;
  v29 = 0;
  v33 = a2;
  v34 = 0;
  v35 = 0;
  v13 = 2;
  v15 = a2;
  v16 = 0;
  v19 = 2;
  v17 = 0;
  v21 = a2;
  v22 = 0;
  v23 = 0;
  v7 = NtCreateCompositionInputSink(&v12, &v10);
  if ( v7 >= 0 )
  {
    v8 = Windows::UI::Composition::VisualCommon::SetInputSinkHandle(v2, v10);
    v5 = v8;
    if ( v8 >= 0 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>(&v10);
      v5 = 0;
      goto LABEL_14;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x127,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\global\\wrtvisualg.cpp",
      (const char *)(unsigned int)v8,
      (int)v10);
  }
  else
  {
    v5 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x125,
           (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\global\\wrtvisualg.cpp",
           (const char *)(unsigned int)v7,
           (int)v10);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&long NtCloseCompositionInputSink(void *)>>(&v10);
LABEL_14:
  Microsoft::WRL2::ContextSession::EndApiEntry(v4);
  return v5;
}

```

## disassembly

```asm
0x180117640  mov     [rsp-8+arg_10], rbx
0x180117645  push    rbp
0x180117646  push    rsi
0x180117647  push    rdi
0x180117648  lea     rbp, [rsp-60h]
0x18011764d  sub     rsp, 160h
0x180117654  mov     rax, cs:__security_cookie
0x18011765b  xor     rax, rsp
0x18011765e  mov     [rbp+70h+var_20], rax
0x180117662  lea     rdi, [rcx-130h]
0x180117669  mov     rbx, rdx
0x18011766c  mov     rsi, [rdi+18h]
0x180117670  mov     rcx, rsi; this
0x180117673  call    ?BeginApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::BeginApiEntry(void)
0x180117678  test    byte ptr [rdi+30h], 2
0x18011767c  jnz     short loc_180117699
0x18011767e  mov     ebx, 80000013h
0x180117683  lea     r8, aTheGivenObject; "The given object has already been close"...
0x18011768a  mov     ecx, ebx
0x18011768c  xor     edx, edx
0x18011768e  call    cs:__imp_RoOriginateErrorW
0x180117694  jmp     loc_1801177CF
0x180117699  test    rbx, rbx
0x18011769c  jnz     short loc_1801176C0
0x18011769e  mov     edx, 113h; void *
0x1801176a3  mov     rcx, [rbp+78h]; this
0x1801176a7  lea     r8, aOnecoreuapWind_156; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1801176ae  mov     ebx, 80070057h
0x1801176b3  mov     r9d, ebx; char *
0x1801176b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801176bb  jmp     loc_1801177CF
0x1801176c0  mov     rcx, rbx; hWnd
0x1801176c3  call    cs:__imp_IsWindow
0x1801176c9  test    eax, eax
0x1801176cb  jnz     short loc_1801176D4
0x1801176cd  mov     edx, 114h
0x1801176d2  jmp     short loc_1801176A3
0x1801176d4  xorps   xmm1, xmm1
0x1801176d7  mov     [rsp+170h+var_110], 0E8h
0x1801176e0  xor     ecx, ecx
0x1801176e2  mov     [rbp+70h+var_98], 2
0x1801176e9  movups  [rsp+170h+var_148], xmm1
0x1801176ee  mov     eax, dword ptr [rsp+170h+var_148+4]
0x1801176f2  lea     rdx, [rsp+170h+var_150]
0x1801176f7  mov     [rbp+70h+var_68], rcx
0x1801176fb  mov     [rbp+70h+var_30], rcx
0x1801176ff  mov     [rbp+70h+var_D8], rcx
0x180117703  mov     [rbp+70h+var_A0], rcx
0x180117707  mov     [rsp+170h+var_150], rcx; int
0x18011770c  lea     rcx, [rsp+170h+var_110]
0x180117711  mov     [rbp+70h+var_94], eax
0x180117714  mov     [rbp+70h+var_5C], eax
0x180117717  mov     [rsp+170h+var_104], eax
0x18011771b  mov     [rbp+70h+var_CC], eax
0x18011771e  mov     [rbp+70h+var_90], rbx
0x180117722  movups  [rbp+70h+var_88], xmm1
0x180117726  mov     [rbp+70h+var_60], 2
0x18011772d  movups  [rbp+70h+var_78], xmm1
0x180117731  mov     [rbp+70h+var_58], rbx
0x180117735  movaps  [rbp+70h+var_50], xmm1
0x180117739  movaps  [rbp+70h+var_40], xmm1
0x18011773d  mov     [rsp+170h+var_108], 2
0x180117745  mov     [rsp+170h+var_100], rbx
0x18011774a  movups  [rsp+170h+var_F8], xmm1
0x18011774f  mov     [rbp+70h+var_D0], 2
0x180117756  movups  [rbp+70h+var_E8], xmm1
0x18011775a  mov     [rbp+70h+var_C8], rbx
0x18011775e  movaps  [rbp+70h+var_C0], xmm1
0x180117762  movaps  [rbp+70h+var_B0], xmm1
0x180117766  call    cs:__imp_NtCreateCompositionInputSink
0x18011776c  test    eax, eax
0x18011776e  jns     short loc_180117796
0x180117770  mov     rcx, [rbp+78h]; this
0x180117774  lea     r8, aOnecoreuapWind_156; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18011777b  mov     r9d, eax; char *
0x18011777e  mov     edx, 125h; void *
0x180117783  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180117788  mov     ebx, eax
0x18011778a  lea     rcx, [rsp+170h+var_150]
0x18011778f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AJPEAX@Z$1?NtCloseCompositionInputSink@@YAJ0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&NtCloseCompositionInputSink(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&NtCloseCompositionInputSink(void *)>>(void)
0x180117794  jmp     short loc_1801177CF
0x180117796  mov     rdx, [rsp+170h+var_150]; void *
0x18011779b  mov     rcx, rdi; this
0x18011779e  call    ?SetInputSinkHandle@VisualCommon@Composition@UI@Windows@@QEAAJPEAX@Z; Windows::UI::Composition::VisualCommon::SetInputSinkHandle(void *)
0x1801177a3  mov     ebx, eax
0x1801177a5  test    eax, eax
0x1801177a7  jns     short loc_1801177C3
0x1801177a9  mov     rcx, [rbp+78h]; this
0x1801177ad  lea     r8, aOnecoreuapWind_156; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1801177b4  mov     r9d, eax; char *
0x1801177b7  mov     edx, 127h; void *
0x1801177bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801177c1  jmp     short loc_18011778A
0x1801177c3  lea     rcx, [rsp+170h+var_150]
0x1801177c8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AJPEAX@Z$1?NtCloseCompositionInputSink@@YAJ0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&NtCloseCompositionInputSink(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<long (*)(void *),&NtCloseCompositionInputSink(void *)>>(void)
0x1801177cd  xor     ebx, ebx
0x1801177cf  mov     rcx, rsi; this
0x1801177d2  call    ?EndApiEntry@ContextSession@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextSession::EndApiEntry(void)
0x1801177d7  mov     eax, ebx
0x1801177d9  mov     rcx, [rbp+70h+var_20]
0x1801177dd  xor     rcx, rsp; StackCookie
0x1801177e0  call    __security_check_cookie
0x1801177e5  mov     rbx, [rsp+170h+arg_10]
0x1801177ed  add     rsp, 160h
0x1801177f4  pop     rdi
0x1801177f5  pop     rsi
0x1801177f6  pop     rbp
0x1801177f7  retn
```
