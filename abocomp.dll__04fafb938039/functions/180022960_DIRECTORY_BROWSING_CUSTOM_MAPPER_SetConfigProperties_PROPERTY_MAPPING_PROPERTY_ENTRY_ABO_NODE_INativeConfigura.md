# DIRECTORY_BROWSING_CUSTOM_MAPPER::SetConfigProperties(PROPERTY_MAPPING *,PROPERTY_ENTRY *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180022960`
- end: `0x180022a33`
- name: `?SetConfigProperties@DIRECTORY_BROWSING_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVPROPERTY_ENTRY@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(DIRECTORY_BROWSING_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180003426`
- `0x180022960`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800229af`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800229af`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002299f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002299f`

## string_xrefs

- `0x1800229b8`: `system.webServer/directoryBrowse`

## pseudocode

```c
__int64 __fastcall DIRECTORY_BROWSING_CUSTOM_MAPPER::SetConfigProperties(
        DIRECTORY_BROWSING_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct PROPERTY_ENTRY *a3,
        struct ABO_NODE *a4,
        struct INativeConfigurationElement *a5)
{
  unsigned int v6; // ebx
  const wchar_t *Str; // rax
  bool v8; // zf
  __int64 (__fastcall *v9)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD); // rax
  __int64 result; // rax

  if ( !a2 || !a3 || !a4 || !a5 )
    return 2147942487LL;
  v6 = **((_DWORD **)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a3 + 16)) + 3);
  Str = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)a2 + 32));
  v8 = wcscmp_0(Str, L"system.webServer/directoryBrowse") == 0;
  v9 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)a5 + 136LL);
  if ( !v8 )
    return v9(a5, L"enabled", (v6 >> 30) & 1, 0);
  result = v9(a5, L"enabled", v6 >> 31, 0);
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, _QWORD, _QWORD))(*(_QWORD *)a5 + 112LL))(
             a5,
             L"showFlags",
             v6 & 0x3FFFFFFF,
             0);
  return result;
}

```

## disassembly

```asm
0x180022960  mov     [rsp+arg_0], rbx
0x180022965  mov     [rsp+arg_8], rsi
0x18002296a  push    rdi
0x18002296b  sub     rsp, 30h
0x18002296f  mov     rsi, rdx
0x180022972  test    rdx, rdx
0x180022975  jz      loc_180022A1E
0x18002297b  test    r8, r8
0x18002297e  jz      loc_180022A1E
0x180022984  test    r9, r9
0x180022987  jz      loc_180022A1E
0x18002298d  mov     rdi, [rsp+38h+arg_20]
0x180022992  test    rdi, rdi
0x180022995  jz      loc_180022A1E
0x18002299b  lea     rcx, [r8+10h]
0x18002299f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800229a5  mov     rcx, [rax+18h]
0x1800229a9  mov     ebx, [rcx]
0x1800229ab  lea     rcx, [rsi+20h]
0x1800229af  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800229b5  mov     rcx, rax; String1
0x1800229b8  lea     rdx, aSystemWebserve_5; "system.webServer/directoryBrowse"
0x1800229bf  call    wcscmp_0
0x1800229c4  mov     rcx, [rdi]
0x1800229c7  lea     rdx, aEnabled; "enabled"
0x1800229ce  xor     r9d, r9d
0x1800229d1  test    eax, eax
0x1800229d3  mov     r10, [rcx+88h]
0x1800229da  mov     rcx, rdi
0x1800229dd  mov     rax, r10
0x1800229e0  jnz     short loc_180022A0E
0x1800229e2  mov     r8d, ebx
0x1800229e5  shr     r8d, 1Fh
0x1800229e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229ee  test    eax, eax
0x1800229f0  js      short loc_180022A23
0x1800229f2  mov     rax, [rdi]
0x1800229f5  lea     rdx, aShowflags; "showFlags"
0x1800229fc  and     ebx, 3FFFFFFFh
0x180022a02  mov     rcx, rdi
0x180022a05  xor     r9d, r9d
0x180022a08  mov     rax, [rax+70h]
0x180022a0c  jmp     short loc_180022A14
0x180022a0e  shr     ebx, 1Eh
0x180022a11  and     ebx, 1
0x180022a14  mov     r8d, ebx
0x180022a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a1c  jmp     short loc_180022A23
0x180022a1e  mov     eax, 80070057h
0x180022a23  mov     rbx, [rsp+38h+arg_0]
0x180022a28  mov     rsi, [rsp+38h+arg_8]
0x180022a2d  add     rsp, 30h
0x180022a31  pop     rdi
0x180022a32  retn
```
