# ListPackages(void)

- ea: `0x140006b70`
- end: `0x140006de8`
- name: `?ListPackages@@YAJXZ`
- size: `632`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x1400059ac`

## callees

- `0x140003a0c`
- `0x140003a90`
- `0x140006b70`
- `0x14000aa3c`
- `0x14000aae8`
- `0x14000ac60`
- `0x14000ad18`
- `0x14000b454`
- `0x14000ded0`
- `0x140010010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140006c88`
- `msvcrt!??3@YAXPEAX@Z` at `0x140006cd1`
- `msvcrt!??3@YAXPEAX@Z` at `0x140006d1b`
- `msvcrt!??3@YAXPEAX@Z` at `0x140006daf`
- `msvcrt!??3@YAXPEAX@Z` at `0x140006c88`
- `msvcrt!??3@YAXPEAX@Z` at `0x140006cd1`
- `msvcrt!??3@YAXPEAX@Z` at `0x140006d1b`
- `msvcrt!??3@YAXPEAX@Z` at `0x140006daf`
- `msvcrt!wprintf` at `0x140006c1c`
- `msvcrt!wprintf` at `0x140006c6f`
- `msvcrt!wprintf` at `0x140006cb8`
- `msvcrt!wprintf` at `0x140006d02`
- `msvcrt!wprintf` at `0x140006d3a`
- `msvcrt!wprintf` at `0x140006d63`
- `msvcrt!wprintf` at `0x140006d96`
- `msvcrt!wprintf` at `0x140006c1c`
- `msvcrt!wprintf` at `0x140006c6f`
- `msvcrt!wprintf` at `0x140006cb8`
- `msvcrt!wprintf` at `0x140006d02`
- `msvcrt!wprintf` at `0x140006d3a`
- `msvcrt!wprintf` at `0x140006d63`
- `msvcrt!wprintf` at `0x140006d96`

## string_xrefs

- `0x140006d5c`: `	Path: %s\n`

## pseudocode

```c
__int64 ListPackages(void)
{
  unsigned int v0; // esi
  wchar_t *v1; // rax
  _QWORD *i; // rbx
  _QWORD *v3; // rdi
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  __int64 v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  __int128 v11; // [rsp+28h] [rbp-90h] BYREF
  __int64 v12; // [rsp+38h] [rbp-80h]
  _BYTE v13[32]; // [rsp+40h] [rbp-78h] BYREF
  __int16 v14; // [rsp+60h] [rbp-58h]
  __int64 v15; // [rsp+70h] [rbp-48h]
  __int64 v16; // [rsp+78h] [rbp-40h]
  void *v17[3]; // [rsp+80h] [rbp-38h] BYREF
  unsigned __int64 v18; // [rsp+98h] [rbp-20h]

  v16 = 7;
  v0 = 0;
  v15 = 0;
  v14 = 0;
  PackageCollector::PackageCollector((PackageCollector *)v13);
  v11 = 0;
  v12 = 0;
  v1 = (wchar_t *)std::vector<std::wstring>::vector<std::wstring>(v17, &v11);
  PackageCollector::AddDefaultSearchPathsWithExclusions((__int64)v13, v1);
  std::vector<std::wstring>::_Tidy(&v11);
  PackageCollector::Search((__int64)v13, &v11);
  v3 = (_QWORD *)*((_QWORD *)&v11 + 1);
  for ( i = (_QWORD *)v11; i != v3; ++i )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*i + 72LL))(*i);
    v5 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)*i + 16LL))(*i, v17);
    if ( v5[3] >= 8u )
      v5 = (_QWORD *)*v5;
    wprintf(L"%s:\n", v5);
    if ( v18 >= 8 )
      operator delete(v17[0]);
    v6 = (_QWORD *)(**(__int64 (__fastcall ***)(_QWORD, void **))*i)(*i, v17);
    if ( v6[3] >= 8u )
      v6 = (_QWORD *)*v6;
    wprintf(L"\tName: %s\n", v6);
    if ( v18 >= 8 )
      operator delete(v17[0]);
    v7 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)*i + 24LL))(*i, v17);
    if ( v7[3] >= 8u )
      v7 = (_QWORD *)*v7;
    wprintf(L"\tVersion: %s\n", v7);
    if ( v18 >= 8 )
      operator delete(v17[0]);
    v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 40LL))(*i);
    wprintf(L"\tAltitude: %Iu\n", v8);
    v9 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 56LL))(*i);
    if ( v9[3] >= 8u )
      v9 = (_QWORD *)*v9;
    wprintf(L"\tPath: %s\n", v9);
    v10 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)*i + 8LL))(*i, v17);
    if ( v10[3] >= 8u )
      v10 = (_QWORD *)*v10;
    ++v0;
    wprintf(L"\tFilename: %s\n", v10);
    if ( v18 >= 8 )
      operator delete(v17[0]);
  }
  std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(&v11);
  wprintf(L"package count:%u\n", v0);
  PackageCollector::~PackageCollector((PackageCollector *)v13);
  return 0;
}

```

## disassembly

```asm
0x140006b70  mov     r11, rsp
0x140006b73  mov     [r11+8], rbx
0x140006b77  mov     [r11+10h], rsi
0x140006b7b  push    rdi
0x140006b7c  sub     rsp, 0B0h
0x140006b83  mov     rax, cs:__security_cookie
0x140006b8a  xor     rax, rsp
0x140006b8d  mov     [rsp+0B8h+var_18], rax
0x140006b95  mov     qword ptr [r11-40h], 7
0x140006b9d  xor     esi, esi
0x140006b9f  mov     [r11-48h], rsi
0x140006ba3  mov     [rsp+0B8h+var_58], si
0x140006ba8  lea     rcx, [r11-78h]; this
0x140006bac  call    ??0PackageCollector@@QEAA@XZ; PackageCollector::PackageCollector(void)
0x140006bb1  nop
0x140006bb2  xorps   xmm0, xmm0
0x140006bb5  movdqu  [rsp+0B8h+var_90], xmm0
0x140006bbb  mov     [rsp+0B8h+var_80], rsi
0x140006bc0  lea     rdx, [rsp+0B8h+var_90]
0x140006bc5  lea     rcx, [rsp+0B8h+var_38]
0x140006bcd  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x140006bd2  mov     rdx, rax
0x140006bd5  lea     rcx, [rsp+0B8h+var_78]
0x140006bda  call    ?AddDefaultSearchPathsWithExclusions@PackageCollector@@QEAAXV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; PackageCollector::AddDefaultSearchPathsWithExclusions(std::vector<std::wstring>)
0x140006bdf  nop
0x140006be0  lea     rcx, [rsp+0B8h+var_90]
0x140006be5  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x140006bea  lea     rdx, [rsp+0B8h+var_90]
0x140006bef  lea     rcx, [rsp+0B8h+var_78]
0x140006bf4  call    ?Search@PackageCollector@@QEAA?AV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@XZ; PackageCollector::Search(void)
0x140006bf9  nop
0x140006bfa  mov     rbx, qword ptr [rsp+0B8h+var_90]
0x140006bff  mov     rdi, qword ptr [rsp+0B8h+var_90+8]
0x140006c04  cmp     rbx, rdi
0x140006c07  jnz     short loc_140006C35
0x140006c09  lea     rcx, [rsp+0B8h+var_90]
0x140006c0e  call    ??1?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<ProvPackage>>::~vector<std::unique_ptr<ProvPackage>>(void)
0x140006c13  mov     edx, esi
0x140006c15  lea     rcx, aPackageCountU; "package count:%u\n"
0x140006c1c  call    cs:__imp_wprintf
0x140006c22  nop
0x140006c23  lea     rcx, [rsp+0B8h+var_78]; this
0x140006c28  call    ??1PackageCollector@@UEAA@XZ; PackageCollector::~PackageCollector(void)
0x140006c2d  nop
0x140006c2e  xor     eax, eax
0x140006c30  jmp     loc_140006DC2
0x140006c35  mov     rcx, [rbx]
0x140006c38  mov     rax, [rcx]
0x140006c3b  mov     rax, [rax+48h]
0x140006c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c44  mov     rcx, [rbx]
0x140006c47  mov     rax, [rcx]
0x140006c4a  lea     rdx, [rsp+0B8h+var_38]
0x140006c52  mov     rax, [rax+10h]
0x140006c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c5b  cmp     qword ptr [rax+18h], 8
0x140006c60  jb      short loc_140006C65
0x140006c62  mov     rax, [rax]
0x140006c65  mov     rdx, rax
0x140006c68  lea     rcx, aS; "%s:\n"
0x140006c6f  call    cs:__imp_wprintf
0x140006c75  cmp     [rsp+0B8h+var_20], 8
0x140006c7e  jb      short loc_140006C8E
0x140006c80  mov     rcx, [rsp+0B8h+var_38]
0x140006c88  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140006c8e  mov     rcx, [rbx]
0x140006c91  mov     rax, [rcx]
0x140006c94  lea     rdx, [rsp+0B8h+var_38]
0x140006c9c  mov     rax, [rax]
0x140006c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ca4  cmp     qword ptr [rax+18h], 8
0x140006ca9  jb      short loc_140006CAE
0x140006cab  mov     rax, [rax]
0x140006cae  mov     rdx, rax
0x140006cb1  lea     rcx, aNameS; "\tName: %s\n"
0x140006cb8  call    cs:__imp_wprintf
0x140006cbe  cmp     [rsp+0B8h+var_20], 8
0x140006cc7  jb      short loc_140006CD7
0x140006cc9  mov     rcx, [rsp+0B8h+var_38]
0x140006cd1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140006cd7  mov     rcx, [rbx]
0x140006cda  mov     rax, [rcx]
0x140006cdd  lea     rdx, [rsp+0B8h+var_38]
0x140006ce5  mov     rax, [rax+18h]
0x140006ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cee  cmp     qword ptr [rax+18h], 8
0x140006cf3  jb      short loc_140006CF8
0x140006cf5  mov     rax, [rax]
0x140006cf8  mov     rdx, rax
0x140006cfb  lea     rcx, aVersionS; "\tVersion: %s\n"
0x140006d02  call    cs:__imp_wprintf
0x140006d08  cmp     [rsp+0B8h+var_20], 8
0x140006d11  jb      short loc_140006D21
0x140006d13  mov     rcx, [rsp+0B8h+var_38]
0x140006d1b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140006d21  mov     rcx, [rbx]
0x140006d24  mov     rax, [rcx]
0x140006d27  mov     rax, [rax+28h]
0x140006d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d30  mov     rdx, rax
0x140006d33  lea     rcx, aAltitudeIu; "\tAltitude: %Iu\n"
0x140006d3a  call    cs:__imp_wprintf
0x140006d40  mov     rcx, [rbx]
0x140006d43  mov     rax, [rcx]
0x140006d46  mov     rax, [rax+38h]
0x140006d4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d4f  cmp     qword ptr [rax+18h], 8
0x140006d54  jb      short loc_140006D59
0x140006d56  mov     rax, [rax]
0x140006d59  mov     rdx, rax
0x140006d5c  lea     rcx, aPathS; "\tPath: %s\n"
0x140006d63  call    cs:__imp_wprintf
0x140006d69  mov     rcx, [rbx]
0x140006d6c  mov     rax, [rcx]
0x140006d6f  lea     rdx, [rsp+0B8h+var_38]
0x140006d77  mov     rax, [rax+8]
0x140006d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d80  cmp     qword ptr [rax+18h], 8
0x140006d85  jb      short loc_140006D8A
0x140006d87  mov     rax, [rax]
0x140006d8a  inc     esi
0x140006d8c  mov     rdx, rax
0x140006d8f  lea     rcx, aFilenameS; "\tFilename: %s\n"
0x140006d96  call    cs:__imp_wprintf
0x140006d9c  cmp     [rsp+0B8h+var_20], 8
0x140006da5  jb      short loc_140006DB5
0x140006da7  mov     rcx, [rsp+0B8h+var_38]
0x140006daf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140006db5  add     rbx, 8
0x140006db9  jmp     loc_140006C04
0x140006dbe  mov     eax, [rsp+0B8h+var_98]
0x140006dc2  mov     rcx, [rsp+0B8h+var_18]
0x140006dca  xor     rcx, rsp; StackCookie
0x140006dcd  call    __security_check_cookie
0x140006dd2  lea     r11, [rsp+0B8h+var_8]
0x140006dda  mov     rbx, [r11+10h]
0x140006dde  mov     rsi, [r11+18h]
0x140006de2  mov     rsp, r11
0x140006de5  pop     rdi
0x140006de6  retn
```
