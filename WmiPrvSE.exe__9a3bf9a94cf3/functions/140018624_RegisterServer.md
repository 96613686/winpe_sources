# RegisterServer

- ea: `0x140018624`
- end: `0x14001891e`
- name: `RegisterServer`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001855c`

## callees

- `0x14000a0f0`
- `0x14000a530`
- `0x140016c58`
- `0x140018350`
- `0x140018624`
- `0x140029274`
- `0x14002e814`
- `0x14002eec8`
- `0x140046430`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14001868a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x14001868a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018797`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140018797`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140018817`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140018817`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400187a6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140018734`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140018734`

## string_xrefs

- `0x1400188be`: `ThreadingModel`
- `0x14001882b`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegisterServer(__int64 a1, __int64 a2, const GUID *a3, BYTE *a4, unsigned __int16 *a5, int a6)
{
  __int64 v8; // rax
  unsigned int v9; // ecx
  __int64 v10; // rax
  unsigned int v11; // ebx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rdi
  const unsigned __int16 *v14; // rdx
  unsigned int v16; // ebx
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v19[8]; // [rsp+40h] [rbp-C0h] BYREF
  LSTATUS (__stdcall *v20)(HKEY); // [rsp+48h] [rbp-B8h]
  HKEY v21; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v22; // [rsp+58h] [rbp-A8h]
  WCHAR SubKey[128]; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[128]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR Filename[264]; // [rsp+260h] [rbp+160h] BYREF

  Filename[0] = 0;
  Filename[260] = 0;
  if ( !GetModuleFileNameW(g_hInst, Filename, 0x104u) )
    return 2147500037LL;
  v8 = -1;
  do
    ++v8;
  while ( Filename[v8] );
  v9 = v8 + 1;
  if ( a5 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a5[v10] );
    v9 += v10 + 2;
  }
  v11 = v9;
  v12 = (unsigned __int16 *)operator new(saturated_mul(v9, 2u));
  v13 = v12;
  if ( !v12 )
    return 2147500037LL;
  v22 = v12;
  StringCchCopyW(v12, v11, Filename);
  if ( a5 )
  {
    StringCchCatW(v13, v11, L" ");
    StringCchCatW(v13, v11, a5);
  }
  StringFromGUID2(a3, sz, 128);
  StringCchCopyW(SubKey, 0x80u, L"APPID\\");
  StringCchCatW(SubKey, 0x80u, sz);
  if ( !(unsigned int)SetKeyAndValue(SubKey, 0, 0, a4)
    || (hKey = 0, RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2001Fu, &hKey)) )
  {
LABEL_15:
    operator delete(v13);
    return 2147746305LL;
  }
  v19[0] = 0;
  v20 = RegCloseKey;
  v21 = hKey;
  if ( (int)SetApplicationSecurity(hKey, v14) < 0
    || a6 && (*(_DWORD *)Data = 2, RegSetValueExW(hKey, L"AppIDFlags", 0, 4u, Data, 4u)) )
  {
    ScopeGuardImpl1<void * (*)(void *),void *>::~ScopeGuardImpl1<void * (*)(void *),void *>(v19);
    goto LABEL_15;
  }
  ScopeGuardImpl1<void * (*)(void *),void *>::~ScopeGuardImpl1<void * (*)(void *),void *>(v19);
  StringCchCopyW(SubKey, 0x80u, L"CLSID\\");
  StringCchCatW(SubKey, 0x80u, sz);
  if ( !(unsigned int)SetKeyAndValue(SubKey, 0, L"AppId", (BYTE *)sz)
    || !(unsigned int)SetKeyAndValue(SubKey, 0, 0, a4)
    || !(unsigned int)SetKeyAndValue(SubKey, L"NotInsertable", 0, 0)
    || !(unsigned int)SetKeyAndValue(SubKey, L"LocalServer32", 0, (BYTE *)v13)
    || (v16 = 0, !(unsigned int)SetKeyAndValue(SubKey, L"LocalServer32", L"ThreadingModel", (BYTE *)L"Both")) )
  {
    v16 = -2147220991;
  }
  operator delete(v13);
  return v16;
}

```

## disassembly

```asm
0x140018624  mov     [rsp-8+arg_0], rbx
0x140018629  mov     [rsp-8+arg_8], rsi
0x14001862e  push    rbp
0x14001862f  push    rdi
0x140018630  push    r12
0x140018632  push    r14
0x140018634  push    r15
0x140018636  lea     rbp, [rsp-380h]
0x14001863e  sub     rsp, 480h
0x140018645  mov     rax, cs:__security_cookie
0x14001864c  xor     rax, rsp
0x14001864f  mov     [rbp+3A0h+var_30], rax
0x140018656  mov     r14, r9
0x140018659  mov     r15, r8
0x14001865c  mov     rsi, [rbp+3A0h+arg_20]
0x140018663  xor     r12d, r12d
0x140018666  mov     [rbp+3A0h+Filename], r12w
0x14001866e  mov     [rbp+3A0h+var_38], r12w
0x140018676  mov     r8d, 104h; nSize
0x14001867c  lea     rdx, [rbp+3A0h+Filename]; lpFilename
0x140018683  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x14001868a  call    cs:__imp_GetModuleFileNameW
0x140018690  test    eax, eax
0x140018692  jz      loc_1400188EE
0x140018698  lea     rcx, [rbp+3A0h+Filename]
0x14001869f  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400186a3  mov     rax, r8
0x1400186a6  inc     rax
0x1400186a9  cmp     [rcx+rax*2], r12w
0x1400186ae  jnz     short loc_1400186A6
0x1400186b0  lea     ecx, [rax+1]
0x1400186b3  test    rsi, rsi
0x1400186b6  jz      short loc_1400186CA
0x1400186b8  mov     rax, r8
0x1400186bb  inc     rax
0x1400186be  cmp     [rsi+rax*2], r12w
0x1400186c3  jnz     short loc_1400186BB
0x1400186c5  add     ecx, 2
0x1400186c8  add     ecx, eax
0x1400186ca  mov     ebx, ecx
0x1400186cc  mov     eax, 2
0x1400186d1  mul     rbx
0x1400186d4  cmovb   rax, r8
0x1400186d8  mov     rcx, rax; dwBytes
0x1400186db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400186e0  mov     rdi, rax
0x1400186e3  test    rax, rax
0x1400186e6  jz      loc_1400188EE
0x1400186ec  mov     [rsp+4A0h+var_448], rax
0x1400186f1  lea     r8, [rbp+3A0h+Filename]; unsigned __int16 *
0x1400186f8  mov     edx, ebx; unsigned __int64
0x1400186fa  mov     rcx, rax; unsigned __int16 *
0x1400186fd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140018702  test    rsi, rsi
0x140018705  jz      short loc_140018725
0x140018707  lea     r8, asc_1400502A0; " "
0x14001870e  mov     edx, ebx; unsigned __int64
0x140018710  mov     rcx, rdi; unsigned __int16 *
0x140018713  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140018718  mov     r8, rsi; unsigned __int16 *
0x14001871b  mov     edx, ebx; unsigned __int64
0x14001871d  mov     rcx, rdi; unsigned __int16 *
0x140018720  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140018725  mov     ebx, 80h
0x14001872a  mov     r8d, ebx; cchMax
0x14001872d  lea     rdx, [rbp+3A0h+sz]; lpsz
0x140018731  mov     rcx, r15; rguid
0x140018734  call    cs:__imp_StringFromGUID2
0x14001873a  lea     r8, aAppid_0; "APPID\\"
0x140018741  mov     edx, ebx; unsigned __int64
0x140018743  lea     rcx, [rsp+4A0h+SubKey]; unsigned __int16 *
0x140018748  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001874d  lea     r8, [rbp+3A0h+sz]; unsigned __int16 *
0x140018751  mov     edx, ebx; unsigned __int64
0x140018753  lea     rcx, [rsp+4A0h+SubKey]; unsigned __int16 *
0x140018758  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14001875d  mov     r9, r14; lpData
0x140018760  xor     r8d, r8d; lpValueName
0x140018763  xor     edx, edx; unsigned __int16 *
0x140018765  lea     rcx, [rsp+4A0h+SubKey]; unsigned __int16 *
0x14001876a  call    ?SetKeyAndValue@@YAHPEAGPEBG11@Z; SetKeyAndValue(ushort *,ushort const *,ushort const *,ushort const *)
0x14001876f  test    eax, eax
0x140018771  jz      short loc_1400187D0
0x140018773  mov     [rsp+4A0h+hKey], r12
0x140018778  lea     rax, [rsp+4A0h+hKey]
0x14001877d  mov     [rsp+4A0h+phkResult], rax; phkResult
0x140018782  mov     r9d, 2001Fh; samDesired
0x140018788  xor     r8d, r8d; ulOptions
0x14001878b  lea     rdx, [rsp+4A0h+SubKey]; lpSubKey
0x140018790  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140018797  call    cs:__imp_RegOpenKeyExW
0x14001879d  test    eax, eax
0x14001879f  jnz     short loc_1400187D0
0x1400187a1  mov     rcx, [rsp+4A0h+hKey]; HKEY
0x1400187a6  mov     rax, cs:__imp_RegCloseKey
0x1400187ad  mov     [rsp+4A0h+var_460], r12b
0x1400187b2  mov     [rsp+4A0h+var_458], rax
0x1400187b7  mov     [rsp+4A0h+var_450], rcx
0x1400187bc  call    ?SetApplicationSecurity@@YAJPEAUHKEY__@@PEBGK@Z; SetApplicationSecurity(HKEY__ *,ushort const *,ulong)
0x1400187c1  test    eax, eax
0x1400187c3  jns     short loc_1400187E2
0x1400187c5  lea     rcx, [rsp+4A0h+var_460]
0x1400187ca  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAX@@QEAA@XZ; ScopeGuardImpl1<void * (*)(void *),void *>::~ScopeGuardImpl1<void * (*)(void *),void *>(void)
0x1400187cf  nop
0x1400187d0  mov     rcx, rdi; lpMem
0x1400187d3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400187d8  mov     eax, 80040201h
0x1400187dd  jmp     loc_1400188F3
0x1400187e2  cmp     [rbp+3A0h+arg_28], r12d
0x1400187e9  jz      short loc_140018821
0x1400187eb  mov     dword ptr [rsp+4A0h+Data], 2
0x1400187f3  mov     r9d, 4; dwType
0x1400187f9  mov     [rsp+4A0h+cbData], r9d; cbData
0x1400187fe  lea     rax, [rsp+4A0h+Data]
0x140018803  mov     [rsp+4A0h+phkResult], rax; lpData
0x140018808  xor     r8d, r8d; Reserved
0x14001880b  lea     rdx, aAppidflags; "AppIDFlags"
0x140018812  mov     rcx, [rsp+4A0h+hKey]; hKey
0x140018817  call    cs:__imp_RegSetValueExW
0x14001881d  test    eax, eax
0x14001881f  jnz     short loc_1400187C5
0x140018821  lea     rcx, [rsp+4A0h+var_460]
0x140018826  call    ??1?$ScopeGuardImpl1@P6APEAXPEAX@ZPEAX@@QEAA@XZ; ScopeGuardImpl1<void * (*)(void *),void *>::~ScopeGuardImpl1<void * (*)(void *),void *>(void)
0x14001882b  lea     r8, aClsid; "CLSID\\"
0x140018832  mov     rdx, rbx; unsigned __int64
0x140018835  lea     rcx, [rsp+4A0h+SubKey]; unsigned __int16 *
0x14001883a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14001883f  lea     r8, [rbp+3A0h+sz]; unsigned __int16 *
0x140018843  mov     rdx, rbx; unsigned __int64
0x140018846  lea     rcx, [rsp+4A0h+SubKey]; unsigned __int16 *
0x14001884b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140018850  lea     r9, [rbp+3A0h+sz]; lpData
0x140018854  lea     r8, aAppid; "AppId"
0x14001885b  xor     edx, edx; unsigned __int16 *
0x14001885d  lea     rcx, [rsp+4A0h+SubKey]; unsigned __int16 *
0x140018862  call    ?SetKeyAndValue@@YAHPEAGPEBG11@Z; SetKeyAndValue(ushort *,ushort const *,ushort const *,ushort const *)
0x140018867  test    eax, eax
0x140018869  jz      short loc_1400188DD
0x14001886b  mov     r9, r14; lpData
0x14001886e  xor     r8d, r8d; lpValueName
0x140018871  xor     edx, edx; unsigned __int16 *
0x140018873  lea     rcx, [rsp+4A0h+SubKey]; unsigned __int16 *
0x140018878  call    ?SetKeyAndValue@@YAHPEAGPEBG11@Z; SetKeyAndValue(ushort *,ushort const *,ushort const *,ushort const *)
0x14001887d  test    eax, eax
0x14001887f  jz      short loc_1400188DD
0x140018881  xor     r9d, r9d; lpData
0x140018884  xor     r8d, r8d; lpValueName
0x140018887  lea     rdx, aNotinsertable; "NotInsertable"
0x14001888e  lea     rcx, [rsp+4A0h+SubKey]; unsigned __int16 *
0x140018893  call    ?SetKeyAndValue@@YAHPEAGPEBG11@Z; SetKeyAndValue(ushort *,ushort const *,ushort const *,ushort const *)
0x140018898  test    eax, eax
0x14001889a  jz      short loc_1400188DD
0x14001889c  mov     r9, rdi; lpData
0x14001889f  xor     r8d, r8d; lpValueName
0x1400188a2  lea     rdx, aLocalserver32; "LocalServer32"
0x1400188a9  lea     rcx, [rsp+4A0h+SubKey]; unsigned __int16 *
0x1400188ae  call    ?SetKeyAndValue@@YAHPEAGPEBG11@Z; SetKeyAndValue(ushort *,ushort const *,ushort const *,ushort const *)
0x1400188b3  test    eax, eax
0x1400188b5  jz      short loc_1400188DD
0x1400188b7  lea     r9, Data; "Both"
0x1400188be  lea     r8, aThreadingmodel; "ThreadingModel"
0x1400188c5  lea     rdx, aLocalserver32; "LocalServer32"
0x1400188cc  lea     rcx, [rsp+4A0h+SubKey]; unsigned __int16 *
0x1400188d1  call    ?SetKeyAndValue@@YAHPEAGPEBG11@Z; SetKeyAndValue(ushort *,ushort const *,ushort const *,ushort const *)
0x1400188d6  test    eax, eax
0x1400188d8  mov     ebx, r12d
0x1400188db  jnz     short loc_1400188E2
0x1400188dd  mov     ebx, 80040201h
0x1400188e2  mov     rcx, rdi; lpMem
0x1400188e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400188ea  mov     eax, ebx
0x1400188ec  jmp     short loc_1400188F3
0x1400188ee  mov     eax, 80004005h
0x1400188f3  mov     rcx, [rbp+3A0h+var_30]
0x1400188fa  xor     rcx, rsp; StackCookie
0x1400188fd  call    __security_check_cookie
0x140018902  lea     r11, [rsp+4A0h+var_20]
0x14001890a  mov     rbx, [r11+30h]
0x14001890e  mov     rsi, [r11+38h]
0x140018912  mov     rsp, r11
0x140018915  pop     r15
0x140018917  pop     r14
0x140018919  pop     r12
0x14001891b  pop     rdi
0x14001891c  pop     rbp
0x14001891d  retn
```
