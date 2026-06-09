# CExec::MakeContainerVirtualAccountToken(bool)

- ea: `0x1400188cc`
- end: `0x140018bbb`
- name: `?MakeContainerVirtualAccountToken@CExec@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@Z`
- size: `751`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140017de8`

## callees

- `0x140002310`
- `0x140002ecc`
- `0x140008160`
- `0x14000e828`
- `0x140015410`
- `0x140015494`
- `0x1400188cc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x140018937`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x140018937`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400189ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400189ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018ac4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018ad4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018af6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018b1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018b43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018ac4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018ad4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018af6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018b1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140018b43`
- `SspiCli!LogonUserExExW` at `0x140018aac`
- `SspiCli!LogonUserExExW` at `0x140018aac`

## string_xrefs

- `0x140018b85`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140018b97`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`
- `0x140018ba9`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
_QWORD *__fastcall CExec::MakeContainerVirtualAccountToken(_QWORD *a1, char a2)
{
  const char *v4; // r9
  _DWORD *v5; // rax
  const char *v6; // r9
  void *v7; // rbx
  const WCHAR *v8; // rcx
  const char *v9; // r9
  struct _SID_IDENTIFIER_AUTHORITY v11; // [rsp+60h] [rbp-A0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v12; // [rsp+68h] [rbp-98h] BYREF
  int v13; // [rsp+70h] [rbp-90h]
  _QWORD *v14; // [rsp+78h] [rbp-88h]
  __int128 v15; // [rsp+80h] [rbp-80h]
  HLOCAL hMem[2]; // [rsp+90h] [rbp-70h] BYREF
  char *v17; // [rsp+A0h] [rbp-60h] BYREF
  char *v18; // [rsp+C0h] [rbp-40h] BYREF
  HLOCAL v19[2]; // [rsp+E0h] [rbp-20h] BYREF
  char *v20; // [rsp+F0h] [rbp-10h] BYREF
  char *v21; // [rsp+110h] [rbp+10h] BYREF
  struct _LUID Luid; // [rsp+130h] [rbp+30h] BYREF
  HLOCAL v23[2]; // [rsp+140h] [rbp+40h] BYREF
  char *v24; // [rsp+150h] [rbp+50h] BYREF
  char *v25; // [rsp+170h] [rbp+70h] BYREF
  HLOCAL v26[2]; // [rsp+190h] [rbp+90h] BYREF
  char *v27; // [rsp+1A0h] [rbp+A0h] BYREF
  char *v28; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v14 = a1;
  v13 = 0;
  memset_0(v19, 0, 0x50u);
  Vml::VmSid::VmSid((Vml::VmSid *)v19, WinLocalSid, 0);
  Luid = 0;
  if ( !AllocateLocallyUniqueId(&Luid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x46D,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v4);
  memset_0(v26, 0, 0x50u);
  *(_DWORD *)v11.Value = 0;
  *(_WORD *)&v11.Value[4] = 1280;
  Vml::VmSid::VmSid((Vml::VmSid *)v26, &v11, 3u, 5, Luid.HighPart, Luid.LowPart);
  memset_0(v23, 0, 0x50u);
  *(_DWORD *)v12.Value = 0;
  *(_WORD *)&v12.Value[4] = 1280;
  Vml::VmSid::VmSid((Vml::VmSid *)v23, &v12, 1u, 32);
  memset_0(hMem, 0, 0x50u);
  Vml::VmSid::VmSid((Vml::VmSid *)hMem, WinBuiltinAdministratorsSid, v23[0]);
  v15 = 0;
  v5 = LocalAlloc(0x40u, 0x38u);
  v7 = v5;
  *(_QWORD *)&v15 = v5;
  if ( !v5 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x47C,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v6);
  *v5 = 2;
  *((HLOCAL *)v5 + 1) = v26[0];
  v5[4] = -1073741809;
  *((HLOCAL *)v5 + 3) = v19[0];
  v5[8] = 7;
  if ( a2 )
  {
    *((HLOCAL *)v5 + 5) = hMem[0];
    v5[12] = 15;
    ++*v5;
  }
  v13 = 1;
  *a1 = 0;
  v8 = L"ContainerAdministrator";
  if ( !a2 )
    v8 = L"ContainerUser";
  if ( !(unsigned int)LogonUserExExW(v8, L"User Manager", &szPassword, a2 != 0 ? 5 : 2, 4, v5, a1, 0, 0, 0, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x49B,
      (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
      v9);
  LocalFree(v7);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  std::wstring::~wstring(&v18);
  std::wstring::~wstring(&v17);
  if ( v23[0] )
    LocalFree(v23[0]);
  std::wstring::~wstring(&v25);
  std::wstring::~wstring(&v24);
  if ( v26[0] )
    LocalFree(v26[0]);
  std::wstring::~wstring(&v28);
  std::wstring::~wstring(&v27);
  if ( v19[0] )
    LocalFree(v19[0]);
  std::wstring::~wstring(&v21);
  std::wstring::~wstring(&v20);
  return a1;
}

```

## disassembly

```asm
0x1400188cc  mov     [rsp-8+arg_8], rbx
0x1400188d1  mov     [rsp-8+arg_10], rsi
0x1400188d6  push    rbp
0x1400188d7  push    rdi
0x1400188d8  push    r14
0x1400188da  lea     rbp, [rsp-0F0h]
0x1400188e2  sub     rsp, 1F0h
0x1400188e9  mov     rax, cs:__security_cookie
0x1400188f0  xor     rax, rsp
0x1400188f3  mov     [rbp+100h+var_20], rax
0x1400188fa  mov     sil, dl
0x1400188fd  mov     rdi, rcx
0x140018900  mov     [rsp+200h+var_188], rcx
0x140018905  xor     r14d, r14d
0x140018908  mov     [rsp+200h+var_190], r14d
0x14001890d  lea     ebx, [r14+50h]
0x140018911  mov     r8d, ebx; Size
0x140018914  xor     edx, edx; Val
0x140018916  lea     rcx, [rbp+100h+var_120]; void *
0x14001891a  call    memset_0
0x14001891f  xor     r8d, r8d; void *
0x140018922  lea     edx, [rbx-4Eh]; enum WELL_KNOWN_SID_TYPE
0x140018925  lea     rcx, [rbp+100h+var_120]; this
0x140018929  call    ??0VmSid@Vml@@QEAA@W4WELL_KNOWN_SID_TYPE@@PEAX@Z; Vml::VmSid::VmSid(WELL_KNOWN_SID_TYPE,void *)
0x14001892e  nop
0x14001892f  mov     qword ptr [rbp+100h+Luid.LowPart], r14
0x140018933  lea     rcx, [rbp+100h+Luid]; Luid
0x140018937  call    cs:__imp_AllocateLocallyUniqueId
0x14001893d  mov     rcx, [rbp+108h]; this
0x140018944  test    eax, eax
0x140018946  jz      loc_140018B97
0x14001894c  mov     r8d, ebx; Size
0x14001894f  xor     edx, edx; Val
0x140018951  lea     rcx, [rbp+100h+var_70]; void *
0x140018958  call    memset_0
0x14001895d  mov     dword ptr [rsp+200h+var_1A0.Value], r14d
0x140018962  mov     word ptr [rsp+200h+var_1A0.Value+4], 500h
0x140018969  mov     eax, [rbp+100h+Luid.LowPart]
0x14001896c  mov     dword ptr [rsp+200h+var_1D8], eax
0x140018970  mov     eax, [rbp+100h+Luid.HighPart]
0x140018973  mov     [rsp+200h+var_1E0], eax
0x140018977  lea     r9d, [r14+5]
0x14001897b  lea     r8d, [r14+3]; unsigned __int8
0x14001897f  lea     rdx, [rsp+200h+var_1A0]; struct _SID_IDENTIFIER_AUTHORITY *
0x140018984  lea     rcx, [rbp+100h+var_70]; this
0x14001898b  call    ??0VmSid@Vml@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; Vml::VmSid::VmSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x140018990  nop
0x140018991  mov     r8d, ebx; Size
0x140018994  xor     edx, edx; Val
0x140018996  lea     rcx, [rbp+100h+var_C0]; void *
0x14001899a  call    memset_0
0x14001899f  mov     dword ptr [rsp+200h+var_198.Value], r14d
0x1400189a4  mov     word ptr [rsp+200h+var_198.Value+4], 500h
0x1400189ab  lea     r9d, [r14+20h]
0x1400189af  lea     r8d, [r14+1]; unsigned __int8
0x1400189b3  lea     rdx, [rsp+200h+var_198]; struct _SID_IDENTIFIER_AUTHORITY *
0x1400189b8  lea     rcx, [rbp+100h+var_C0]; this
0x1400189bc  call    ??0VmSid@Vml@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; Vml::VmSid::VmSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x1400189c1  nop
0x1400189c2  mov     r8d, ebx; Size
0x1400189c5  xor     edx, edx; Val
0x1400189c7  lea     rcx, [rbp+100h+hMem]; void *
0x1400189cb  call    memset_0
0x1400189d0  mov     r8, [rbp+100h+var_C0]; void *
0x1400189d4  lea     edx, [rbx-36h]; enum WELL_KNOWN_SID_TYPE
0x1400189d7  lea     rcx, [rbp+100h+hMem]; this
0x1400189db  call    ??0VmSid@Vml@@QEAA@W4WELL_KNOWN_SID_TYPE@@PEAX@Z; Vml::VmSid::VmSid(WELL_KNOWN_SID_TYPE,void *)
0x1400189e0  nop
0x1400189e1  xorps   xmm0, xmm0
0x1400189e4  movups  [rbp+100h+var_180], xmm0
0x1400189e8  lea     edx, [rbx-18h]; uBytes
0x1400189eb  lea     ecx, [rbx-10h]; uFlags
0x1400189ee  call    cs:__imp_LocalAlloc
0x1400189f4  mov     rbx, rax
0x1400189f7  mov     qword ptr [rbp+100h+var_180], rax
0x1400189fb  mov     rcx, [rbp+108h]; this
0x140018a02  test    rax, rax
0x140018a05  jz      loc_140018BA9
0x140018a0b  mov     dword ptr [rax], 2
0x140018a11  mov     rax, [rbp+100h+var_70]
0x140018a18  mov     [rbx+8], rax
0x140018a1c  mov     dword ptr [rbx+10h], 0C000000Fh
0x140018a23  mov     rax, [rbp+100h+var_120]
0x140018a27  mov     [rbx+18h], rax
0x140018a2b  mov     dword ptr [rbx+20h], 7
0x140018a32  test    sil, sil
0x140018a35  jz      short loc_140018A48
0x140018a37  mov     rax, [rbp+100h+hMem]
0x140018a3b  mov     [rbx+28h], rax
0x140018a3f  mov     dword ptr [rbx+30h], 0Fh
0x140018a46  inc     dword ptr [rbx]
0x140018a48  mov     [rsp+200h+var_190], 1
0x140018a50  mov     [rdi], r14
0x140018a53  mov     al, sil
0x140018a56  neg     al
0x140018a58  sbb     r9d, r9d
0x140018a5b  and     r9d, 3
0x140018a5f  add     r9d, 2
0x140018a63  lea     rax, aContaineruser; "ContainerUser"
0x140018a6a  lea     rcx, aContaineradmin; "ContainerAdministrator"
0x140018a71  test    sil, sil
0x140018a74  cmovz   rcx, rax
0x140018a78  mov     [rsp+200h+var_1B0], r14
0x140018a7d  mov     [rsp+200h+var_1B8], r14
0x140018a82  mov     [rsp+200h+var_1C0], r14
0x140018a87  mov     [rsp+200h+var_1C8], r14
0x140018a8c  mov     [rsp+200h+var_1D0], rdi
0x140018a91  mov     [rsp+200h+var_1D8], rbx
0x140018a96  mov     [rsp+200h+var_1E0], 4
0x140018a9e  lea     r8, szPassword
0x140018aa5  lea     rdx, SourceString; "User Manager"
0x140018aac  call    cs:__imp_LogonUserExExW
0x140018ab2  mov     rcx, [rbp+108h]; this
0x140018ab9  test    eax, eax
0x140018abb  jz      loc_140018B85
0x140018ac1  mov     rcx, rbx; hMem
0x140018ac4  call    cs:__imp_LocalFree
0x140018aca  nop
0x140018acb  mov     rcx, [rbp+100h+hMem]; hMem
0x140018acf  test    rcx, rcx
0x140018ad2  jz      short loc_140018ADA
0x140018ad4  call    cs:__imp_LocalFree
0x140018ada  lea     rcx, [rbp+100h+var_140]
0x140018ade  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018ae3  lea     rcx, [rbp+100h+var_160]
0x140018ae7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018aec  nop
0x140018aed  mov     rcx, [rbp+100h+var_C0]; hMem
0x140018af1  test    rcx, rcx
0x140018af4  jz      short loc_140018AFC
0x140018af6  call    cs:__imp_LocalFree
0x140018afc  lea     rcx, [rbp+100h+var_90]
0x140018b00  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018b05  lea     rcx, [rbp+100h+var_B0]
0x140018b09  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018b0e  nop
0x140018b0f  mov     rcx, [rbp+100h+var_70]; hMem
0x140018b16  test    rcx, rcx
0x140018b19  jz      short loc_140018B21
0x140018b1b  call    cs:__imp_LocalFree
0x140018b21  lea     rcx, [rbp+100h+var_40]
0x140018b28  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018b2d  lea     rcx, [rbp+100h+var_60]
0x140018b34  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018b39  nop
0x140018b3a  mov     rcx, [rbp+100h+var_120]; hMem
0x140018b3e  test    rcx, rcx
0x140018b41  jz      short loc_140018B49
0x140018b43  call    cs:__imp_LocalFree
0x140018b49  lea     rcx, [rbp+100h+var_F0]
0x140018b4d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018b52  lea     rcx, [rbp+100h+var_110]
0x140018b56  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140018b5b  mov     rax, rdi
0x140018b5e  mov     rcx, [rbp+100h+var_20]
0x140018b65  xor     rcx, rsp; StackCookie
0x140018b68  call    __security_check_cookie
0x140018b6d  lea     r11, [rsp+200h+var_10]
0x140018b75  mov     rbx, [r11+28h]
0x140018b79  mov     rsi, [r11+30h]
0x140018b7d  mov     rsp, r11
0x140018b80  pop     r14
0x140018b82  pop     rdi
0x140018b83  pop     rbp
0x140018b84  retn
0x140018b85  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x140018b8c  mov     edx, 49Bh; void *
0x140018b91  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140018b97  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x140018b9e  mov     edx, 46Dh; void *
0x140018ba3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140018ba9  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x140018bb0  mov     edx, 47Ch; void *
0x140018bb5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
