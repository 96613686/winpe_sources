# Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180027018`
- end: `0x1800272e9`
- name: `?CreateFolderHierarchyWithAcls@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `721`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180027724`

## callees

- `0x1800045d0`
- `0x180010744`
- `0x180010764`
- `0x180013de4`
- `0x180017a20`
- `0x180026eec`
- `0x180027018`
- `0x1800272f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027219`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800270c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027102`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027276`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800272ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800270c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027102`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027276`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800272ac`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180027209`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180027209`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002709e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002709e`

## string_xrefs

- `0x1800270e0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18002724a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls(
        _QWORD *a1,
        __int64 a2)
{
  const WCHAR *v2; // rax
  int v4; // esi
  struct _SECURITY_ATTRIBUTES *v5; // r14
  BOOL v6; // ebx
  const char *v7; // r9
  void *v8; // rcx
  unsigned int LastError; // ebx
  HLOCAL v10; // rcx
  __int64 v12; // r15
  _QWORD *v13; // rcx
  _QWORD *v14; // rdx
  PSECURITY_DESCRIPTOR *v15; // rdx
  __int64 v16; // r8
  char v17; // bl
  PSECURITY_DESCRIPTOR *v18; // rcx
  signed int v19; // eax
  unsigned int v20; // ebx
  HLOCAL v21; // rcx
  HLOCAL v22; // rcx
  HLOCAL hMem; // [rsp+30h] [rbp-98h] BYREF
  __int128 v24; // [rsp+38h] [rbp-90h] BYREF
  __int64 v25; // [rsp+48h] [rbp-80h]
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+50h] [rbp-78h] BYREF
  __int128 v27; // [rsp+60h] [rbp-68h]
  _OWORD v28[2]; // [rsp+70h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v2 = (const WCHAR *)a2;
  v4 = 0;
  v24 = 0;
  v25 = 0;
  hMem = 0;
  if ( *(_QWORD *)(a2 + 16) )
  {
    SecurityDescriptor[0] = &hMem;
    SecurityDescriptor[1] = 0;
    LOBYTE(v27) = 1;
    if ( *(_QWORD *)(a2 + 24) > 7u )
      v2 = *(const WCHAR **)a2;
    v6 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v2, 1u, &SecurityDescriptor[1], 0);
    if ( (_BYTE)v27 )
    {
      v8 = *(void **)SecurityDescriptor[0];
      *(_QWORD *)SecurityDescriptor[0] = SecurityDescriptor[1];
      if ( v8 )
        LocalFree(v8);
    }
    if ( !v6 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x87,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
                    v7);
      v10 = hMem;
      hMem = 0;
      if ( v10 )
        LocalFree(v10);
      return LastError;
    }
    LODWORD(v24) = 24;
    *((_QWORD *)&v24 + 1) = hMem;
    LODWORD(v25) = 0;
    v5 = (struct _SECURITY_ATTRIBUTES *)&v24;
  }
  else
  {
    v5 = 0;
  }
  v12 = 0;
  do
  {
    if ( a1[3] <= 7u )
      v13 = a1;
    else
      v13 = (_QWORD *)*a1;
    v12 = std::_Traits_find_first_of<std::char_traits<unsigned short>>(v13, a1[2], v12 + 1, L"\\/");
    *(_OWORD *)SecurityDescriptor = 0;
    v27 = 0;
    if ( a1[3] <= 7u )
      v14 = a1;
    else
      v14 = (_QWORD *)*a1;
    std::wstring::_Construct<1,unsigned short const *>(SecurityDescriptor, v14);
    v15 = SecurityDescriptor;
    if ( *((_QWORD *)&v27 + 1) > 7u )
      v15 = (PSECURITY_DESCRIPTOR *)SecurityDescriptor[0];
    memset(v28, 0, sizeof(v28));
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v15 + v16) );
    std::wstring::_Construct<1,unsigned short const *>(v28, v15);
    v17 = Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(v28);
    std::wstring::_Tidy_deallocate(v28);
    if ( !v17 )
    {
      v18 = SecurityDescriptor;
      if ( *((_QWORD *)&v27 + 1) > 7u )
        v18 = (PSECURITY_DESCRIPTOR *)SecurityDescriptor[0];
      if ( !CreateDirectoryW((LPCWSTR)v18, v5) )
      {
        v19 = GetLastError();
        v20 = v19;
        if ( v19 != 183 )
        {
          if ( v19 > 0 )
            v20 = (unsigned __int16)v19 | 0x80070000;
          if ( (v20 & 0x80000000) != 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9C,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
              (const char *)v20,
              2);
          std::wstring::_Tidy_deallocate(SecurityDescriptor);
          v21 = hMem;
          hMem = 0;
          if ( v21 )
            LocalFree(v21);
          return v20;
        }
      }
    }
    v4 |= 1u;
    std::wstring::_Tidy_deallocate(SecurityDescriptor);
  }
  while ( v12 != -1 );
  v22 = hMem;
  hMem = 0;
  if ( v22 )
    LocalFree(v22);
  return 0;
}

```

## disassembly

```asm
0x180027018  mov     [rsp+arg_10], rbx
0x18002701d  push    rsi
0x18002701e  push    rdi
0x18002701f  push    r12
0x180027021  push    r14
0x180027023  push    r15
0x180027025  sub     rsp, 0A0h
0x18002702c  mov     rax, cs:__security_cookie
0x180027033  xor     rax, rsp
0x180027036  mov     [rsp+0C8h+var_38], rax
0x18002703e  mov     rax, rdx
0x180027041  mov     rdi, rcx
0x180027044  xor     r12d, r12d
0x180027047  mov     esi, r12d
0x18002704a  mov     dword ptr [rsp+0C8h+hMem], r12d
0x18002704f  xorps   xmm0, xmm0
0x180027052  xor     ecx, ecx
0x180027054  movups  [rsp+0C8h+var_90], xmm0
0x180027059  mov     [rsp+0C8h+var_80], rcx
0x18002705e  mov     [rsp+0C8h+hMem], r12
0x180027063  cmp     [rdx+10h], r12
0x180027067  jnz     short loc_180027071
0x180027069  mov     r14d, r12d
0x18002706c  jmp     loc_180027131
0x180027071  lea     rcx, [rsp+0C8h+hMem]
0x180027076  mov     [rsp+0C8h+SecurityDescriptor], rcx
0x18002707b  mov     [rsp+0C8h+SecurityDescriptor+8], r12
0x180027080  mov     byte ptr [rsp+0C8h+var_68], 1
0x180027085  cmp     qword ptr [rdx+18h], 7
0x18002708a  jbe     short loc_18002708F
0x18002708c  mov     rax, [rdx]
0x18002708f  xor     r9d, r9d; SecurityDescriptorSize
0x180027092  lea     r8, [rsp+0C8h+SecurityDescriptor+8]; SecurityDescriptor
0x180027097  lea     edx, [r9+1]; StringSDRevision
0x18002709b  mov     rcx, rax; StringSecurityDescriptor
0x18002709e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800270a5  nop     dword ptr [rax+rax+00h]
0x1800270aa  mov     ebx, eax
0x1800270ac  cmp     byte ptr [rsp+0C8h+var_68], r12b
0x1800270b1  jz      short loc_1800270D4
0x1800270b3  mov     r8, [rsp+0C8h+SecurityDescriptor]
0x1800270b8  mov     rcx, [r8]; hMem
0x1800270bb  mov     rdx, [rsp+0C8h+SecurityDescriptor+8]
0x1800270c0  mov     [r8], rdx
0x1800270c3  test    rcx, rcx
0x1800270c6  jz      short loc_1800270D4
0x1800270c8  call    cs:__imp_LocalFree
0x1800270cf  nop     dword ptr [rax+rax+00h]
0x1800270d4  test    ebx, ebx
0x1800270d6  jnz     short loc_180027115
0x1800270d8  mov     rcx, [rsp+0C8h]; this
0x1800270e0  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800270e7  mov     edx, 87h; void *
0x1800270ec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800270f1  mov     ebx, eax
0x1800270f3  mov     rcx, [rsp+0C8h+hMem]; hMem
0x1800270f8  mov     [rsp+0C8h+hMem], r12
0x1800270fd  test    rcx, rcx
0x180027100  jz      short loc_18002710E
0x180027102  call    cs:__imp_LocalFree
0x180027109  nop     dword ptr [rax+rax+00h]
0x18002710e  mov     eax, ebx
0x180027110  jmp     loc_1800272C0
0x180027115  mov     dword ptr [rsp+0C8h+var_90], 18h
0x18002711d  mov     rax, [rsp+0C8h+hMem]
0x180027122  mov     qword ptr [rsp+0C8h+var_90+8], rax
0x180027127  mov     dword ptr [rsp+0C8h+var_80], r12d
0x18002712c  lea     r14, [rsp+0C8h+var_90]
0x180027131  mov     r15, r12
0x180027134  cmp     qword ptr [rdi+18h], 7
0x180027139  jbe     short loc_180027140
0x18002713b  mov     rcx, [rdi]
0x18002713e  jmp     short loc_180027143
0x180027140  mov     rcx, rdi
0x180027143  lea     r8, [r15+1]
0x180027147  mov     qword ptr [rsp+0C8h+var_A8], 2; int
0x180027150  lea     r9, asc_180037104; "\\/"
0x180027157  mov     rdx, [rdi+10h]
0x18002715b  call    ??$_Traits_find_first_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_first_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x180027160  mov     r15, rax
0x180027163  xorps   xmm0, xmm0
0x180027166  movups  xmmword ptr [rsp+0C8h+SecurityDescriptor], xmm0
0x18002716b  xorps   xmm1, xmm1
0x18002716e  movdqu  [rsp+0C8h+var_68], xmm1
0x180027174  mov     r8, rax
0x180027177  cmp     [rdi+10h], rax
0x18002717b  cmovb   r8, [rdi+10h]
0x180027180  cmp     qword ptr [rdi+18h], 7
0x180027185  jbe     short loc_18002718C
0x180027187  mov     rdx, [rdi]
0x18002718a  jmp     short loc_18002718F
0x18002718c  mov     rdx, rdi
0x18002718f  lea     rcx, [rsp+0C8h+SecurityDescriptor]
0x180027194  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180027199  nop
0x18002719a  lea     rdx, [rsp+0C8h+SecurityDescriptor]
0x18002719f  cmp     qword ptr [rsp+0C8h+var_68+8], 7
0x1800271a5  cmova   rdx, [rsp+0C8h+SecurityDescriptor]
0x1800271ab  xorps   xmm0, xmm0
0x1800271ae  movups  [rsp+0C8h+var_58], xmm0
0x1800271b3  xorps   xmm1, xmm1
0x1800271b6  movdqu  [rsp+0C8h+var_48], xmm1
0x1800271bf  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800271c3  inc     r8
0x1800271c6  cmp     [rdx+r8*2], r12w
0x1800271cb  jnz     short loc_1800271C3
0x1800271cd  lea     rcx, [rsp+0C8h+var_58]
0x1800271d2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800271d7  lea     rcx, [rsp+0C8h+var_58]
0x1800271dc  call    ?DirectoryExists@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::DirectoryExists(std::wstring const &)
0x1800271e1  mov     bl, al
0x1800271e3  lea     rcx, [rsp+0C8h+var_58]
0x1800271e8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800271ed  test    bl, bl
0x1800271ef  jnz     loc_180027286
0x1800271f5  lea     rcx, [rsp+0C8h+SecurityDescriptor]
0x1800271fa  cmp     qword ptr [rsp+0C8h+var_68+8], 7
0x180027200  cmova   rcx, [rsp+0C8h+SecurityDescriptor]; lpPathName
0x180027206  mov     rdx, r14; lpSecurityAttributes
0x180027209  call    cs:__imp_CreateDirectoryW
0x180027210  nop     dword ptr [rax+rax+00h]
0x180027215  test    eax, eax
0x180027217  jnz     short loc_180027286
0x180027219  call    cs:__imp_GetLastError
0x180027220  nop     dword ptr [rax+rax+00h]
0x180027225  mov     ebx, eax
0x180027227  cmp     eax, 0B7h
0x18002722c  jz      short loc_180027286
0x18002722e  test    eax, eax
0x180027230  jle     short loc_18002723B
0x180027232  movzx   ebx, ax
0x180027235  or      ebx, 80070000h
0x18002723b  test    ebx, ebx
0x18002723d  jns     short loc_18002725C
0x18002723f  mov     rcx, [rsp+0C8h]; this
0x180027247  mov     r9d, ebx; char *
0x18002724a  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027251  mov     edx, 9Ch; void *
0x180027256  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002725b  nop
0x18002725c  lea     rcx, [rsp+0C8h+SecurityDescriptor]
0x180027261  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027266  nop
0x180027267  mov     rcx, [rsp+0C8h+hMem]; hMem
0x18002726c  mov     [rsp+0C8h+hMem], r12
0x180027271  test    rcx, rcx
0x180027274  jz      short loc_180027282
0x180027276  call    cs:__imp_LocalFree
0x18002727d  nop     dword ptr [rax+rax+00h]
0x180027282  mov     eax, ebx
0x180027284  jmp     short loc_1800272C0
0x180027286  or      esi, 1
0x180027289  lea     rcx, [rsp+0C8h+SecurityDescriptor]
0x18002728e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027293  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180027297  jnz     loc_180027134
0x18002729d  mov     rcx, [rsp+0C8h+hMem]; hMem
0x1800272a2  mov     [rsp+0C8h+hMem], r12
0x1800272a7  test    rcx, rcx
0x1800272aa  jz      short loc_1800272B8
0x1800272ac  call    cs:__imp_LocalFree
0x1800272b3  nop     dword ptr [rax+rax+00h]
0x1800272b8  xor     eax, eax
0x1800272ba  jmp     short loc_1800272C0
0x1800272bc  mov     eax, dword ptr [rsp+0C8h+hMem]
0x1800272c0  mov     rcx, [rsp+0C8h+var_38]
0x1800272c8  xor     rcx, rsp; StackCookie
0x1800272cb  call    __security_check_cookie
0x1800272d0  mov     rbx, [rsp+0C8h+arg_10]
0x1800272d8  add     rsp, 0A0h
0x1800272df  pop     r15
0x1800272e1  pop     r14
0x1800272e3  pop     r12
0x1800272e5  pop     rdi
0x1800272e6  pop     rsi
0x1800272e7  retn
```
