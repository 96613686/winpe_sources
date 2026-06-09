# Microsoft::Windows::Autopilot::AutopilotServiceStateSeparation::CreateFolderHierarchyWithAcls(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180026100`
- end: `0x1800263bf`
- name: `?CreateFolderHierarchyWithAcls@AutopilotServiceStateSeparation@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `703`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180026794`

## callees

- `0x1800045b0`
- `0x1800105d4`
- `0x1800105f4`
- `0x180013a40`
- `0x1800174f0`
- `0x180025fdc`
- `0x180026100`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026301`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026301`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800261aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800261de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026358`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026388`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800261aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800261de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026358`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026388`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800262c1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800262c1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800262f7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800262f7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180026186`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180026186`

## string_xrefs

- `0x1800261bc`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`
- `0x18002632c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotstateseparation.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  unsigned __int64 v12; // r15
  _QWORD *v13; // rcx
  unsigned __int64 v14; // r8
  _QWORD *v15; // rdx
  PSECURITY_DESCRIPTOR *v16; // rdx
  __int64 v17; // r8
  const WCHAR *v18; // rcx
  DWORD FileAttributesW; // eax
  char v20; // bl
  PSECURITY_DESCRIPTOR *v21; // rcx
  signed int v22; // eax
  unsigned int v23; // ebx
  HLOCAL v24; // rcx
  HLOCAL v25; // rcx
  HLOCAL hMem; // [rsp+30h] [rbp-98h] BYREF
  __int128 v27; // [rsp+38h] [rbp-90h] BYREF
  __int64 v28; // [rsp+48h] [rbp-80h]
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+50h] [rbp-78h] BYREF
  __int128 v30; // [rsp+60h] [rbp-68h]
  LPCWSTR lpFileName[2]; // [rsp+70h] [rbp-58h] BYREF
  __int128 v32; // [rsp+80h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v2 = (const WCHAR *)a2;
  v4 = 0;
  v27 = 0;
  v28 = 0;
  hMem = 0;
  if ( *(_QWORD *)(a2 + 16) )
  {
    SecurityDescriptor[0] = &hMem;
    SecurityDescriptor[1] = 0;
    LOBYTE(v30) = 1;
    if ( *(_QWORD *)(a2 + 24) > 7u )
      v2 = *(const WCHAR **)a2;
    v6 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v2, 1u, &SecurityDescriptor[1], 0);
    if ( (_BYTE)v30 )
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
    LODWORD(v27) = 24;
    *((_QWORD *)&v27 + 1) = hMem;
    LODWORD(v28) = 0;
    v5 = (struct _SECURITY_ATTRIBUTES *)&v27;
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
    v30 = 0;
    v14 = v12;
    if ( a1[2] < v12 )
      v14 = a1[2];
    if ( a1[3] <= 7u )
      v15 = a1;
    else
      v15 = (_QWORD *)*a1;
    std::wstring::_Construct<1,unsigned short const *>(SecurityDescriptor, v15, v14);
    v16 = SecurityDescriptor;
    if ( *((_QWORD *)&v30 + 1) > 7u )
      v16 = (PSECURITY_DESCRIPTOR *)SecurityDescriptor[0];
    *(_OWORD *)lpFileName = 0;
    v32 = 0;
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)v16 + v17) );
    std::wstring::_Construct<1,unsigned short const *>(lpFileName, v16, v17);
    v18 = (const WCHAR *)lpFileName;
    if ( *((_QWORD *)&v32 + 1) > 7u )
      v18 = lpFileName[0];
    FileAttributesW = GetFileAttributesW(v18);
    if ( FileAttributesW == -1 || (v20 = 0, (FileAttributesW & 0x10) == 0) )
      v20 = 1;
    std::wstring::_Tidy_deallocate(lpFileName);
    if ( v20 )
    {
      v21 = SecurityDescriptor;
      if ( *((_QWORD *)&v30 + 1) > 7u )
        v21 = (PSECURITY_DESCRIPTOR *)SecurityDescriptor[0];
      if ( !CreateDirectoryW((LPCWSTR)v21, v5) )
      {
        v22 = GetLastError();
        v23 = v22;
        if ( v22 != 183 )
        {
          if ( v22 > 0 )
            v23 = (unsigned __int16)v22 | 0x80070000;
          if ( (v23 & 0x80000000) != 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x9C,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotstateseparation.cpp",
              (const char *)v23,
              2);
          std::wstring::_Tidy_deallocate(SecurityDescriptor);
          v24 = hMem;
          hMem = 0;
          if ( v24 )
            LocalFree(v24);
          return v23;
        }
      }
    }
    v4 |= 1u;
    std::wstring::_Tidy_deallocate(SecurityDescriptor);
  }
  while ( v12 != -1 );
  v25 = hMem;
  hMem = 0;
  if ( v25 )
    LocalFree(v25);
  return 0;
}

```

## disassembly

```asm
0x180026100  mov     [rsp+arg_10], rbx
0x180026105  push    rsi
0x180026106  push    rdi
0x180026107  push    r12
0x180026109  push    r14
0x18002610b  push    r15
0x18002610d  sub     rsp, 0A0h
0x180026114  mov     rax, cs:__security_cookie
0x18002611b  xor     rax, rsp
0x18002611e  mov     [rsp+0C8h+var_38], rax
0x180026126  mov     rax, rdx
0x180026129  mov     rdi, rcx
0x18002612c  xor     r12d, r12d
0x18002612f  mov     esi, r12d
0x180026132  mov     dword ptr [rsp+0C8h+hMem], r12d
0x180026137  xorps   xmm0, xmm0
0x18002613a  xor     ecx, ecx
0x18002613c  movups  [rsp+0C8h+var_90], xmm0
0x180026141  mov     [rsp+0C8h+var_80], rcx
0x180026146  mov     [rsp+0C8h+hMem], r12
0x18002614b  cmp     [rdx+10h], r12
0x18002614f  jnz     short loc_180026159
0x180026151  mov     r14d, r12d
0x180026154  jmp     loc_180026207
0x180026159  lea     rcx, [rsp+0C8h+hMem]
0x18002615e  mov     [rsp+0C8h+SecurityDescriptor], rcx
0x180026163  mov     [rsp+0C8h+SecurityDescriptor+8], r12
0x180026168  mov     byte ptr [rsp+0C8h+var_68], 1
0x18002616d  cmp     qword ptr [rdx+18h], 7
0x180026172  jbe     short loc_180026177
0x180026174  mov     rax, [rdx]
0x180026177  xor     r9d, r9d; SecurityDescriptorSize
0x18002617a  lea     r8, [rsp+0C8h+SecurityDescriptor+8]; SecurityDescriptor
0x18002617f  lea     edx, [r9+1]; StringSDRevision
0x180026183  mov     rcx, rax; StringSecurityDescriptor
0x180026186  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002618c  mov     ebx, eax
0x18002618e  cmp     byte ptr [rsp+0C8h+var_68], r12b
0x180026193  jz      short loc_1800261B0
0x180026195  mov     r8, [rsp+0C8h+SecurityDescriptor]
0x18002619a  mov     rcx, [r8]; hMem
0x18002619d  mov     rdx, [rsp+0C8h+SecurityDescriptor+8]
0x1800261a2  mov     [r8], rdx
0x1800261a5  test    rcx, rcx
0x1800261a8  jz      short loc_1800261B0
0x1800261aa  call    cs:__imp_LocalFree
0x1800261b0  test    ebx, ebx
0x1800261b2  jnz     short loc_1800261EB
0x1800261b4  mov     rcx, [rsp+0C8h]; this
0x1800261bc  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800261c3  mov     edx, 87h; void *
0x1800261c8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800261cd  mov     ebx, eax
0x1800261cf  mov     rcx, [rsp+0C8h+hMem]; hMem
0x1800261d4  mov     [rsp+0C8h+hMem], r12
0x1800261d9  test    rcx, rcx
0x1800261dc  jz      short loc_1800261E4
0x1800261de  call    cs:__imp_LocalFree
0x1800261e4  mov     eax, ebx
0x1800261e6  jmp     loc_180026396
0x1800261eb  mov     dword ptr [rsp+0C8h+var_90], 18h
0x1800261f3  mov     rax, [rsp+0C8h+hMem]
0x1800261f8  mov     qword ptr [rsp+0C8h+var_90+8], rax
0x1800261fd  mov     dword ptr [rsp+0C8h+var_80], r12d
0x180026202  lea     r14, [rsp+0C8h+var_90]
0x180026207  mov     r15, r12
0x18002620a  cmp     qword ptr [rdi+18h], 7
0x18002620f  jbe     short loc_180026216
0x180026211  mov     rcx, [rdi]
0x180026214  jmp     short loc_180026219
0x180026216  mov     rcx, rdi
0x180026219  lea     r8, [r15+1]
0x18002621d  mov     qword ptr [rsp+0C8h+var_A8], 2; int
0x180026226  lea     r9, asc_1800360E4; "\\/"
0x18002622d  mov     rdx, [rdi+10h]
0x180026231  call    ??$_Traits_find_first_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_first_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x180026236  mov     r15, rax
0x180026239  xorps   xmm0, xmm0
0x18002623c  movups  xmmword ptr [rsp+0C8h+SecurityDescriptor], xmm0
0x180026241  xorps   xmm1, xmm1
0x180026244  movdqu  [rsp+0C8h+var_68], xmm1
0x18002624a  mov     r8, rax
0x18002624d  cmp     [rdi+10h], rax
0x180026251  cmovb   r8, [rdi+10h]
0x180026256  cmp     qword ptr [rdi+18h], 7
0x18002625b  jbe     short loc_180026262
0x18002625d  mov     rdx, [rdi]
0x180026260  jmp     short loc_180026265
0x180026262  mov     rdx, rdi
0x180026265  lea     rcx, [rsp+0C8h+SecurityDescriptor]
0x18002626a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002626f  nop
0x180026270  lea     rdx, [rsp+0C8h+SecurityDescriptor]
0x180026275  cmp     qword ptr [rsp+0C8h+var_68+8], 7
0x18002627b  cmova   rdx, [rsp+0C8h+SecurityDescriptor]
0x180026281  xorps   xmm0, xmm0
0x180026284  movups  xmmword ptr [rsp+0C8h+lpFileName], xmm0
0x180026289  xorps   xmm1, xmm1
0x18002628c  movdqu  [rsp+0C8h+var_48], xmm1
0x180026295  or      r8, 0FFFFFFFFFFFFFFFFh
0x180026299  inc     r8
0x18002629c  cmp     [rdx+r8*2], r12w
0x1800262a1  jnz     short loc_180026299
0x1800262a3  lea     rcx, [rsp+0C8h+lpFileName]
0x1800262a8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800262ad  lea     rcx, [rsp+0C8h+lpFileName]
0x1800262b2  cmp     qword ptr [rsp+0C8h+var_48+8], 7
0x1800262bb  cmova   rcx, [rsp+0C8h+lpFileName]; lpFileName
0x1800262c1  call    cs:__imp_GetFileAttributesW
0x1800262c7  cmp     eax, 0FFFFFFFFh
0x1800262ca  jz      short loc_1800262D3
0x1800262cc  test    al, 10h
0x1800262ce  mov     bl, r12b
0x1800262d1  jnz     short loc_1800262D5
0x1800262d3  mov     bl, 1
0x1800262d5  lea     rcx, [rsp+0C8h+lpFileName]
0x1800262da  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800262df  test    bl, bl
0x1800262e1  jz      short loc_180026362
0x1800262e3  lea     rcx, [rsp+0C8h+SecurityDescriptor]
0x1800262e8  cmp     qword ptr [rsp+0C8h+var_68+8], 7
0x1800262ee  cmova   rcx, [rsp+0C8h+SecurityDescriptor]; lpPathName
0x1800262f4  mov     rdx, r14; lpSecurityAttributes
0x1800262f7  call    cs:__imp_CreateDirectoryW
0x1800262fd  test    eax, eax
0x1800262ff  jnz     short loc_180026362
0x180026301  call    cs:__imp_GetLastError
0x180026307  mov     ebx, eax
0x180026309  cmp     eax, 0B7h
0x18002630e  jz      short loc_180026362
0x180026310  test    eax, eax
0x180026312  jle     short loc_18002631D
0x180026314  movzx   ebx, ax
0x180026317  or      ebx, 80070000h
0x18002631d  test    ebx, ebx
0x18002631f  jns     short loc_18002633E
0x180026321  mov     rcx, [rsp+0C8h]; this
0x180026329  mov     r9d, ebx; char *
0x18002632c  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\moderndeployment\\au"...
0x180026333  mov     edx, 9Ch; void *
0x180026338  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002633d  nop
0x18002633e  lea     rcx, [rsp+0C8h+SecurityDescriptor]
0x180026343  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026348  nop
0x180026349  mov     rcx, [rsp+0C8h+hMem]; hMem
0x18002634e  mov     [rsp+0C8h+hMem], r12
0x180026353  test    rcx, rcx
0x180026356  jz      short loc_18002635E
0x180026358  call    cs:__imp_LocalFree
0x18002635e  mov     eax, ebx
0x180026360  jmp     short loc_180026396
0x180026362  or      esi, 1
0x180026365  lea     rcx, [rsp+0C8h+SecurityDescriptor]
0x18002636a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002636f  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180026373  jnz     loc_18002620A
0x180026379  mov     rcx, [rsp+0C8h+hMem]; hMem
0x18002637e  mov     [rsp+0C8h+hMem], r12
0x180026383  test    rcx, rcx
0x180026386  jz      short loc_18002638E
0x180026388  call    cs:__imp_LocalFree
0x18002638e  xor     eax, eax
0x180026390  jmp     short loc_180026396
0x180026392  mov     eax, dword ptr [rsp+0C8h+hMem]
0x180026396  mov     rcx, [rsp+0C8h+var_38]
0x18002639e  xor     rcx, rsp; StackCookie
0x1800263a1  call    __security_check_cookie
0x1800263a6  mov     rbx, [rsp+0C8h+arg_10]
0x1800263ae  add     rsp, 0A0h
0x1800263b5  pop     r15
0x1800263b7  pop     r14
0x1800263b9  pop     r12
0x1800263bb  pop     rdi
0x1800263bc  pop     rsi
0x1800263bd  retn
```
