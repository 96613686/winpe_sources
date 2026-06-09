# LogonSoundHelpers::LogonSoundPlayer::_InitializeAudioPlayer(void)

- ea: `0x18002c268`
- end: `0x18002c62a`
- name: `?_InitializeAudioPlayer@LogonSoundPlayer@LogonSoundHelpers@@AEAAJXZ`
- size: `962`
- prototype: `__int64 __fastcall(LogonSoundHelpers::LogonSoundPlayer *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180043d7c`

## callees

- `0x18000df10`
- `0x18002c268`
- `0x1800440d0`
- `0x18005d488`
- `0x18006c000`
- `0x18006cad0`
- `0x18009d010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18002c2a3`
- `KERNEL32!LoadLibraryExW` at `0x18002c2a3`
- `KERNEL32!FreeLibrary` at `0x18002c4ca`
- `KERNEL32!FreeLibrary` at `0x18002c5ad`
- `KERNEL32!FreeLibrary` at `0x18002c4ca`
- `KERNEL32!FreeLibrary` at `0x18002c5ad`
- `KERNEL32!GetProcAddress` at `0x18002c2e0`
- `KERNEL32!GetProcAddress` at `0x18002c2e0`

## string_xrefs

- `0x18002c29c`: `audioses.dll`
- `0x18002c2d6`: `DllGetClassObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall LogonSoundHelpers::LogonSoundPlayer::_InitializeAudioPlayer(
        LogonSoundHelpers::LogonSoundPlayer *this)
{
  HMODULE Library; // rbx
  FARPROC ProcAddress; // rax
  int v4; // edi
  _OWORD *v5; // rax
  __int64 *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, GUID *, __int64 *, _BYTE *); // rdi
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rdi
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // [rsp+20h] [rbp-E0h]
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  HMODULE v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+5Ch] [rbp-A4h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  int v30; // [rsp+68h] [rbp-98h]
  int v31; // [rsp+6Ch] [rbp-94h]
  int v32; // [rsp+70h] [rbp-90h]
  int v33; // [rsp+74h] [rbp-8Ch]
  int v34; // [rsp+78h] [rbp-88h]
  int v35; // [rsp+7Ch] [rbp-84h]
  _BYTE v36[256]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v37[4]; // [rsp+180h] [rbp+80h] BYREF
  int v38; // [rsp+184h] [rbp+84h]
  int v39; // [rsp+1A4h] [rbp+A4h]
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  Library = LoadLibraryExW(L"audioses.dll", 0, 0x800u);
  v24 = Library;
  if ( !Library )
    goto LABEL_27;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v21);
  v21 = 0;
  v23 = 0;
  ProcAddress = GetProcAddress(Library, "DllGetClassObject");
  if ( !ProcAddress )
  {
    v4 = -2147418113;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\logonsoundhelpers.cpp",
      (const char *)(unsigned int)v4,
      v20);
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v21);
LABEL_13:
    FreeLibrary(Library);
    return (unsigned int)v4;
  }
  v4 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
         &CLSID_AudioPlayerFacade,
         &IID_IClassFactory,
         &v23);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v23 + 24LL))(
           v23,
           0,
           &GUID_4d19ad40_4049_4c52_aa2a_84e4e52e9ec2,
           &v21);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  if ( v4 < 0 )
    goto LABEL_34;
  v25 = 304;
  v26 = -1443938343;
  v27 = 1163805248;
  v28 = -1275931228;
  v29 = -1299769296;
  v30 = 0x10000;
  v31 = 40;
  v32 = 500;
  v33 = 10000;
  v34 = 250;
  v35 = 5;
  memset_0(v36, 0, sizeof(v36));
  v5 = v37;
  v6 = &v25;
  v7 = 2;
  do
  {
    *v5 = *(_OWORD *)v6;
    v5[1] = *((_OWORD *)v6 + 1);
    v5[2] = *((_OWORD *)v6 + 2);
    v5[3] = *((_OWORD *)v6 + 3);
    v5[4] = *((_OWORD *)v6 + 4);
    v5[5] = *((_OWORD *)v6 + 5);
    v5[6] = *((_OWORD *)v6 + 6);
    v5[7] = *((_OWORD *)v6 + 7);
    v5 += 8;
    v6 += 16;
    --v7;
  }
  while ( v7 );
  *v5 = *(_OWORD *)v6;
  v5[1] = *((_OWORD *)v6 + 1);
  v5[2] = *((_OWORD *)v6 + 2);
  v38 = 0;
  v39 = 0;
  v22 = 0;
  v8 = v21;
  v9 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *, _BYTE *))(*(_QWORD *)v21 + 24LL);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v22);
  v10 = v9(v8, &GUID_81ef556b_a13d_4f0c_b88e_5eded83750f7, &v22, v37);
  v4 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\logonsoundhelpers.cpp",
      (const char *)(unsigned int)v10,
      v20);
    v11 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_13;
  }
  *((_BYTE *)this + 40) = 1;
  v14 = v21;
  if ( *((_QWORD *)this + 3) != v21 )
  {
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    v15 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v14;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v16 = v22;
  if ( *((_QWORD *)this + 4) != v22 )
  {
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
    v23 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = v16;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v23);
  }
  v17 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  if ( (HMODULE *)((char *)this + 16) != &v24 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      (char *)this + 16,
      Library);
    v24 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    &v24,
    v17);
  v18 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v19 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  Library = v24;
LABEL_27:
  if ( Library )
    FreeLibrary(Library);
  return 0;
}

```

## disassembly

```asm
0x18002c268  push    rbp
0x18002c26a  push    rbx
0x18002c26b  push    rsi
0x18002c26c  push    rdi
0x18002c26d  push    r14
0x18002c26f  push    r15
0x18002c271  lea     rbp, [rsp-1C8h]
0x18002c279  sub     rsp, 2C8h
0x18002c280  mov     rax, cs:__security_cookie
0x18002c287  xor     rax, rsp
0x18002c28a  mov     [rbp+1F0h+var_40], rax
0x18002c291  mov     r14, rcx
0x18002c294  xor     edx, edx; hFile
0x18002c296  mov     r8d, 800h; dwFlags
0x18002c29c  lea     rcx, aAudiosesDll; "audioses.dll"
0x18002c2a3  call    cs:__imp_LoadLibraryExW
0x18002c2a9  mov     rbx, rax
0x18002c2ac  mov     [rsp+2F0h+var_2A8], rax
0x18002c2b1  xor     r15d, r15d
0x18002c2b4  test    rax, rax
0x18002c2b7  jz      loc_18002C59E
0x18002c2bd  mov     [rsp+2F0h+var_2C0], r15
0x18002c2c2  lea     rcx, [rsp+2F0h+var_2C0]
0x18002c2c7  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18002c2cc  mov     [rsp+2F0h+var_2C0], r15
0x18002c2d1  mov     [rsp+2F0h+var_2B0], r15
0x18002c2d6  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18002c2dd  mov     rcx, rbx; hModule
0x18002c2e0  call    cs:__imp_GetProcAddress
0x18002c2e6  test    rax, rax
0x18002c2e9  jz      loc_18002C5D6
0x18002c2ef  lea     r8, [rsp+2F0h+var_2B0]
0x18002c2f4  lea     rdx, IID_IClassFactory
0x18002c2fb  lea     rcx, CLSID_AudioPlayerFacade
0x18002c302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c307  mov     edi, eax
0x18002c309  test    eax, eax
0x18002c30b  js      short loc_18002C33F
0x18002c30d  mov     rcx, [rsp+2F0h+var_2B0]
0x18002c312  mov     rax, [rcx]
0x18002c315  lea     r9, [rsp+2F0h+var_2C0]
0x18002c31a  lea     r8, _GUID_4d19ad40_4049_4c52_aa2a_84e4e52e9ec2
0x18002c321  xor     edx, edx
0x18002c323  mov     rax, [rax+18h]
0x18002c327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c32c  mov     edi, eax
0x18002c32e  mov     rcx, [rsp+2F0h+var_2B0]
0x18002c333  mov     rax, [rcx]
0x18002c336  mov     rax, [rax+10h]
0x18002c33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c33f  test    edi, edi
0x18002c341  js      loc_18002C5DB
0x18002c347  mov     [rsp+2F0h+var_2A0], 130h
0x18002c350  mov     [rsp+2F0h+var_298], 0A9EF3FD9h
0x18002c358  mov     [rsp+2F0h+var_294], 455E4240h
0x18002c360  mov     [rsp+2F0h+var_290], 0B3F2D5A4h
0x18002c368  mov     [rsp+2F0h+var_28C], 0B2871830h
0x18002c370  mov     [rsp+2F0h+var_288], 10000h
0x18002c378  mov     [rsp+2F0h+var_284], 28h ; '('
0x18002c380  mov     [rsp+2F0h+var_280], 1F4h
0x18002c388  mov     [rsp+2F0h+var_27C], 2710h
0x18002c390  mov     [rsp+2F0h+var_278], 0FAh
0x18002c398  mov     [rsp+2F0h+var_274], 5
0x18002c3a0  xor     edx, edx; Val
0x18002c3a2  mov     r8d, 100h; Size
0x18002c3a8  lea     rcx, [rbp+1F0h+var_270]; void *
0x18002c3ac  call    memset_0
0x18002c3b1  lea     rax, [rbp+1F0h+var_170]
0x18002c3b8  lea     rcx, [rsp+2F0h+var_2A0]
0x18002c3bd  mov     edx, 2
0x18002c3c2  lea     r8d, [rdx+7Eh]
0x18002c3c6  movups  xmm0, xmmword ptr [rcx]
0x18002c3c9  movups  xmmword ptr [rax], xmm0
0x18002c3cc  movups  xmm1, xmmword ptr [rcx+10h]
0x18002c3d0  movups  xmmword ptr [rax+10h], xmm1
0x18002c3d4  movups  xmm0, xmmword ptr [rcx+20h]
0x18002c3d8  movups  xmmword ptr [rax+20h], xmm0
0x18002c3dc  movups  xmm1, xmmword ptr [rcx+30h]
0x18002c3e0  movups  xmmword ptr [rax+30h], xmm1
0x18002c3e4  movups  xmm0, xmmword ptr [rcx+40h]
0x18002c3e8  movups  xmmword ptr [rax+40h], xmm0
0x18002c3ec  movups  xmm1, xmmword ptr [rcx+50h]
0x18002c3f0  movups  xmmword ptr [rax+50h], xmm1
0x18002c3f4  movups  xmm0, xmmword ptr [rcx+60h]
0x18002c3f8  movups  xmmword ptr [rax+60h], xmm0
0x18002c3fc  movups  xmm1, xmmword ptr [rcx+70h]
0x18002c400  movups  xmmword ptr [rax+70h], xmm1
0x18002c404  add     rax, r8
0x18002c407  add     rcx, r8
0x18002c40a  sub     rdx, 1
0x18002c40e  jnz     short loc_18002C3C6
0x18002c410  movups  xmm0, xmmword ptr [rcx]
0x18002c413  movups  xmmword ptr [rax], xmm0
0x18002c416  movups  xmm1, xmmword ptr [rcx+10h]
0x18002c41a  movups  xmmword ptr [rax+10h], xmm1
0x18002c41e  movups  xmm0, xmmword ptr [rcx+20h]
0x18002c422  movups  xmmword ptr [rax+20h], xmm0
0x18002c426  mov     [rbp+1F0h+var_16C], r15d
0x18002c42d  mov     [rbp+1F0h+var_14C], r15d
0x18002c434  mov     [rsp+2F0h+var_2B8], r15
0x18002c439  mov     rsi, [rsp+2F0h+var_2C0]
0x18002c43e  mov     rax, [rsi]
0x18002c441  mov     rdi, [rax+18h]
0x18002c445  lea     rcx, [rsp+2F0h+var_2B8]
0x18002c44a  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18002c44f  lea     r9, [rbp+1F0h+var_170]
0x18002c456  lea     r8, [rsp+2F0h+var_2B8]
0x18002c45b  lea     rdx, _GUID_81ef556b_a13d_4f0c_b88e_5eded83750f7
0x18002c462  mov     rcx, rsi
0x18002c465  mov     rax, rdi
0x18002c468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c46d  mov     edi, eax
0x18002c46f  test    eax, eax
0x18002c471  jns     short loc_18002C4F1
0x18002c473  mov     rcx, [rbp+1F8h]; this
0x18002c47a  mov     r9d, eax; char *
0x18002c47d  lea     r8, aPcshellShellAu_18; "pcshell\\shell\\auth\\authux\\controlle"...
0x18002c484  mov     edx, 1EFh; void *
0x18002c489  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c48e  nop
0x18002c48f  mov     rcx, [rsp+2F0h+var_2B8]
0x18002c494  test    rcx, rcx
0x18002c497  jz      short loc_18002C4AB
0x18002c499  mov     [rsp+2F0h+var_2B8], r15
0x18002c49e  mov     rax, [rcx]
0x18002c4a1  mov     rax, [rax+10h]
0x18002c4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4aa  nop
0x18002c4ab  mov     rcx, [rsp+2F0h+var_2C0]
0x18002c4b0  test    rcx, rcx
0x18002c4b3  jz      short loc_18002C4C7
0x18002c4b5  mov     [rsp+2F0h+var_2C0], r15
0x18002c4ba  mov     rax, [rcx]
0x18002c4bd  mov     rax, [rax+10h]
0x18002c4c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4c6  nop
0x18002c4c7  mov     rcx, rbx; hLibModule
0x18002c4ca  call    cs:__imp_FreeLibrary
0x18002c4d0  mov     eax, edi
0x18002c4d2  mov     rcx, [rbp+1F0h+var_40]
0x18002c4d9  xor     rcx, rsp; StackCookie
0x18002c4dc  call    __security_check_cookie
0x18002c4e1  add     rsp, 2C8h
0x18002c4e8  pop     r15
0x18002c4ea  pop     r14
0x18002c4ec  pop     rdi
0x18002c4ed  pop     rsi
0x18002c4ee  pop     rbx
0x18002c4ef  pop     rbp
0x18002c4f0  retn
0x18002c4f1  mov     byte ptr [r14+28h], 1
0x18002c4f6  mov     rdi, [rsp+2F0h+var_2C0]
0x18002c4fb  cmp     [r14+18h], rdi
0x18002c4ff  jz      short loc_18002C530
0x18002c501  test    rdi, rdi
0x18002c504  jz      short loc_18002C516
0x18002c506  mov     rax, [rdi]
0x18002c509  mov     rcx, rdi
0x18002c50c  mov     rax, [rax+8]
0x18002c510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c515  nop
0x18002c516  mov     rcx, [r14+18h]
0x18002c51a  mov     [r14+18h], rdi
0x18002c51e  test    rcx, rcx
0x18002c521  jz      short loc_18002C530
0x18002c523  mov     rax, [rcx]
0x18002c526  mov     rax, [rax+10h]
0x18002c52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c52f  nop
0x18002c530  mov     rdi, [rsp+2F0h+var_2B8]
0x18002c535  cmp     [r14+20h], rdi
0x18002c539  jnz     short loc_18002C5B5
0x18002c53b  lea     rcx, [r14+10h]
0x18002c53f  mov     rdi, [rcx]
0x18002c542  mov     [rcx], r15
0x18002c545  lea     rax, [rsp+2F0h+var_2A8]
0x18002c54a  cmp     rcx, rax
0x18002c54d  jnz     loc_18002C617
0x18002c553  mov     rdx, rdi
0x18002c556  lea     rcx, [rsp+2F0h+var_2A8]
0x18002c55b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18002c560  nop
0x18002c561  mov     rcx, [rsp+2F0h+var_2B8]
0x18002c566  test    rcx, rcx
0x18002c569  jz      short loc_18002C57D
0x18002c56b  mov     [rsp+2F0h+var_2B8], r15
0x18002c570  mov     rax, [rcx]
0x18002c573  mov     rax, [rax+10h]
0x18002c577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c57c  nop
0x18002c57d  mov     rcx, [rsp+2F0h+var_2C0]
0x18002c582  test    rcx, rcx
0x18002c585  jz      short loc_18002C599
0x18002c587  mov     [rsp+2F0h+var_2C0], r15
0x18002c58c  mov     rax, [rcx]
0x18002c58f  mov     rax, [rax+10h]
0x18002c593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c598  nop
0x18002c599  mov     rbx, [rsp+2F0h+var_2A8]
0x18002c59e  test    rbx, rbx
0x18002c5a1  jnz     short loc_18002C5AA
0x18002c5a3  xor     eax, eax
0x18002c5a5  jmp     loc_18002C4D2
0x18002c5aa  mov     rcx, rbx; hLibModule
0x18002c5ad  call    cs:__imp_FreeLibrary
0x18002c5b3  jmp     short loc_18002C5A3
0x18002c5b5  test    rdi, rdi
0x18002c5b8  jnz     short loc_18002C606
0x18002c5ba  mov     rax, [r14+20h]
0x18002c5be  mov     [rsp+2F0h+var_2B0], rax
0x18002c5c3  mov     [r14+20h], rdi
0x18002c5c7  lea     rcx, [rsp+2F0h+var_2B0]
0x18002c5cc  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18002c5d1  jmp     loc_18002C53B
0x18002c5d6  mov     edi, 8000FFFFh
0x18002c5db  mov     rcx, [rbp+1F8h]; this
0x18002c5e2  mov     r9d, edi; char *
0x18002c5e5  lea     r8, aPcshellShellAu_18; "pcshell\\shell\\auth\\authux\\controlle"...
0x18002c5ec  mov     edx, 1E7h; void *
0x18002c5f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c5f6  nop
0x18002c5f7  lea     rcx, [rsp+2F0h+var_2C0]
0x18002c5fc  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18002c601  jmp     loc_18002C4C7
0x18002c606  mov     rax, [rdi]
0x18002c609  mov     rcx, rdi
0x18002c60c  mov     rax, [rax+8]
0x18002c610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c615  jmp     short loc_18002C5BA
0x18002c617  mov     rdx, rbx
0x18002c61a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18002c61f  mov     [rsp+2F0h+var_2A8], r15
0x18002c624  jmp     loc_18002C553
```
