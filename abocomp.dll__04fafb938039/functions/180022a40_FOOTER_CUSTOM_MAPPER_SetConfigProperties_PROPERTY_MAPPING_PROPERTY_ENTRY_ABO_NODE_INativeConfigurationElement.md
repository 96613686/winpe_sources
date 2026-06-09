# FOOTER_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180022a40`
- end: `0x180022bfe`
- name: `?SetConfigProperties@FOOTER_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `446`
- prototype: `__int64 __fastcall(FOOTER_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180022a40`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180022b06`
- `msvcrt!_wcsnicmp` at `0x180022b2a`
- `msvcrt!_wcsnicmp` at `0x180022b06`
- `msvcrt!_wcsnicmp` at `0x180022b2a`
- `msvcrt!iswspace` at `0x180022aee`
- `msvcrt!iswspace` at `0x180022b4a`
- `msvcrt!iswspace` at `0x180022b6b`
- `msvcrt!iswspace` at `0x180022aee`
- `msvcrt!iswspace` at `0x180022b4a`
- `msvcrt!iswspace` at `0x180022b6b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022acb`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180022acb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022a9a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180022a9a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022bce`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180022bce`

## pseudocode

```c
__int64 __fastcall FOOTER_CUSTOM_MAPPER::SetConfigProperties(
        FOOTER_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  const wchar_t *v8; // rbx
  wint_t v9; // cx
  int v10; // edi
  unsigned int v11; // edi
  __int64 v12; // rax
  wint_t *i; // rbx
  wint_t *v14; // rbx
  _BYTE v16[64]; // [rsp+30h] [rbp-268h] BYREF
  unsigned __int16 v17[256]; // [rsp+70h] [rbp-228h] BYREF

  memset_0(v17, 0, sizeof(v17));
  STRU::STRU((STRU *)v16, v17, 0x100u);
  if ( !a2 || !a3 || !a4 || !a5 )
  {
    v10 = -2147024809;
    goto LABEL_25;
  }
  v8 = (const wchar_t *)*((_QWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16)) + 3);
  v9 = *v8;
  if ( !*v8 )
  {
    v10 = -2147024894;
    goto LABEL_25;
  }
  while ( iswspace(v9) )
    v9 = *++v8;
  if ( _wcsnicmp(v8, L"string", 6u) )
  {
    if ( _wcsnicmp(v8, L"file", 4u) )
    {
LABEL_23:
      v10 = -2147024883;
      goto LABEL_25;
    }
    v11 = 1;
    v12 = 4;
  }
  else
  {
    v11 = 0;
    v12 = 6;
  }
  for ( i = (wint_t *)&v8[v12]; iswspace(*i); ++i )
    ;
  if ( *i != 58 )
    goto LABEL_23;
  v14 = i + 1;
  if ( v11 )
  {
    while ( iswspace(*v14) )
      ++v14;
  }
  v10 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)a5 + 136LL))(
          a5,
          L"isDocFooterFileName",
          v11,
          0);
  if ( v10 >= 0 )
    v10 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wint_t *, _QWORD))(*(_QWORD *)a5 + 128LL))(
            a5,
            L"defaultDocFooter",
            v14,
            0);
LABEL_25:
  STRU::~STRU((STRU *)v16);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180022a40  mov     [rsp+arg_0], rbx
0x180022a45  mov     [rsp+arg_8], rbp
0x180022a4a  push    rsi
0x180022a4b  push    rdi
0x180022a4c  push    r14
0x180022a4e  sub     rsp, 280h
0x180022a55  mov     rax, cs:__security_cookie
0x180022a5c  xor     rax, rsp
0x180022a5f  mov     [rsp+298h+var_28], rax
0x180022a67  mov     rsi, [rsp+298h+arg_20]
0x180022a6f  lea     rcx, [rsp+298h+var_228]; void *
0x180022a74  mov     rdi, r8
0x180022a77  mov     rbx, rdx
0x180022a7a  xor     edx, edx; Val
0x180022a7c  mov     r8d, 200h; Size
0x180022a82  mov     rbp, r9
0x180022a85  call    memset_0
0x180022a8a  mov     r8d, 100h
0x180022a90  lea     rdx, [rsp+298h+var_228]
0x180022a95  lea     rcx, [rsp+298h+var_268]
0x180022a9a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180022aa0  xor     r14d, r14d
0x180022aa3  test    rbx, rbx
0x180022aa6  jz      loc_180022BC4
0x180022aac  test    rdi, rdi
0x180022aaf  jz      loc_180022BC4
0x180022ab5  test    rbp, rbp
0x180022ab8  jz      loc_180022BC4
0x180022abe  test    rsi, rsi
0x180022ac1  jz      loc_180022BC4
0x180022ac7  lea     rcx, [rdi+10h]
0x180022acb  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180022ad1  mov     rbx, [rax+18h]
0x180022ad5  movzx   ecx, word ptr [rbx]
0x180022ad8  test    cx, cx
0x180022adb  jnz     short loc_180022AEE
0x180022add  mov     edi, 80070002h
0x180022ae2  jmp     loc_180022BC9
0x180022ae7  add     rbx, 2
0x180022aeb  movzx   ecx, word ptr [rbx]; C
0x180022aee  call    cs:__imp_iswspace
0x180022af4  test    eax, eax
0x180022af6  jnz     short loc_180022AE7
0x180022af8  lea     r8d, [rax+6]; MaxCount
0x180022afc  mov     rcx, rbx; String1
0x180022aff  lea     rdx, aString_0; "string"
0x180022b06  call    cs:__imp__wcsnicmp
0x180022b0c  test    eax, eax
0x180022b0e  jnz     short loc_180022B1A
0x180022b10  mov     edi, r14d
0x180022b13  mov     eax, 0Ch
0x180022b18  jmp     short loc_180022B3E
0x180022b1a  mov     r8d, 4; MaxCount
0x180022b20  lea     rdx, aFile_0; "file"
0x180022b27  mov     rcx, rbx; String1
0x180022b2a  call    cs:__imp__wcsnicmp
0x180022b30  test    eax, eax
0x180022b32  jnz     loc_180022BBD
0x180022b38  lea     edi, [rax+1]
0x180022b3b  lea     eax, [rdi+7]
0x180022b3e  add     rbx, rax
0x180022b41  jmp     short loc_180022B47
0x180022b43  add     rbx, 2
0x180022b47  movzx   ecx, word ptr [rbx]; C
0x180022b4a  call    cs:__imp_iswspace
0x180022b50  test    eax, eax
0x180022b52  jnz     short loc_180022B43
0x180022b54  cmp     word ptr [rbx], 3Ah ; ':'
0x180022b58  jnz     short loc_180022BBD
0x180022b5a  add     rbx, 2
0x180022b5e  test    edi, edi
0x180022b60  jz      short loc_180022B75
0x180022b62  jmp     short loc_180022B68
0x180022b64  add     rbx, 2
0x180022b68  movzx   ecx, word ptr [rbx]; C
0x180022b6b  call    cs:__imp_iswspace
0x180022b71  test    eax, eax
0x180022b73  jnz     short loc_180022B64
0x180022b75  mov     rax, [rsi]
0x180022b78  lea     rdx, aIsdocfooterfil; "isDocFooterFileName"
0x180022b7f  xor     r9d, r9d
0x180022b82  mov     r8d, edi
0x180022b85  mov     rcx, rsi
0x180022b88  mov     rax, [rax+88h]
0x180022b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b94  mov     edi, eax
0x180022b96  test    eax, eax
0x180022b98  js      short loc_180022BC9
0x180022b9a  mov     rax, [rsi]
0x180022b9d  lea     rdx, aDefaultdocfoot; "defaultDocFooter"
0x180022ba4  xor     r9d, r9d
0x180022ba7  mov     r8, rbx
0x180022baa  mov     rcx, rsi
0x180022bad  mov     rax, [rax+80h]
0x180022bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bb9  mov     edi, eax
0x180022bbb  jmp     short loc_180022BC9
0x180022bbd  mov     edi, 8007000Dh
0x180022bc2  jmp     short loc_180022BC9
0x180022bc4  mov     edi, 80070057h
0x180022bc9  lea     rcx, [rsp+298h+var_268]
0x180022bce  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180022bd4  mov     eax, edi
0x180022bd6  mov     rcx, [rsp+298h+var_28]
0x180022bde  xor     rcx, rsp; StackCookie
0x180022be1  call    __security_check_cookie
0x180022be6  lea     r11, [rsp+298h+var_18]
0x180022bee  mov     rbx, [r11+20h]
0x180022bf2  mov     rbp, [r11+28h]
0x180022bf6  mov     rsp, r11
0x180022bf9  pop     r14
0x180022bfb  pop     rdi
0x180022bfc  pop     rsi
0x180022bfd  retn
```
