# DllUnregisterServer

- ea: `0x180006c20`
- end: `0x180006d35`
- name: `DllUnregisterServer`
- size: `277`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003c7c`
- `0x180006c20`
- `0x18000c010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180006d01`
- `ADVAPI32!RegOpenKeyExW` at `0x180006d01`
- `ADVAPI32!RegCloseKey` at `0x180006d22`
- `ADVAPI32!RegCloseKey` at `0x180006d22`
- `ADVAPI32!RegDeleteValueW` at `0x180006d17`
- `ADVAPI32!RegDeleteValueW` at `0x180006d17`

## string_xrefs

- `0x180006cf3`: `Software\Microsoft\Windows\CurrentVersion\Shell Extensions\Approved`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HRESULT __stdcall DllUnregisterServer()
{
  __int64 v0; // rbx
  const struct ATL::_ATL_CATMAP_ENTRY *v1; // rax
  __int64 *v2; // rbx
  __int64 *v3; // rax
  __int64 v4; // rdi
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v0 = qword_180013A08;
  if ( qword_180013A08 )
  {
    while ( *(_QWORD *)v0 )
    {
      v1 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v0 + 56))();
      if ( (int)ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v0, v1, 0) < 0
        || (*(int (__fastcall **)(_QWORD))(v0 + 8))(0) < 0 )
      {
        goto LABEL_16;
      }
      v0 += 72;
    }
  }
  if ( !ATL::_pPerfUnRegFunc || ATL::_pPerfUnRegFunc() >= 0 )
  {
    v2 = (__int64 *)off_180013110[0];
    v3 = (__int64 *)off_180013118;
    while ( v2 < v3 )
    {
      v4 = *v2;
      if ( *v2 )
      {
        v5 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v4 + 56))();
        if ( (int)ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v4, v5, 0) < 0
          || (*(int (__fastcall **)(_QWORD))(v4 + 8))(0) < 0 )
        {
          break;
        }
        v3 = (__int64 *)off_180013118;
      }
      ++v2;
    }
  }
LABEL_16:
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell Extensions\\Approved",
          0,
          0xF003Fu,
          &hKey) )
  {
    RegDeleteValueW(hKey, L"{ECCDF543-45CC-11CE-B9BF-0080C87CDBA6}");
    RegCloseKey(hKey);
  }
  return 0;
}

```

## disassembly

```asm
0x180006c20  mov     [rsp+arg_8], rbx
0x180006c25  push    rdi
0x180006c26  sub     rsp, 30h
0x180006c2a  mov     rbx, cs:qword_180013A08
0x180006c31  test    rbx, rbx
0x180006c34  jz      short loc_180006C70
0x180006c36  jmp     short loc_180006C6A
0x180006c38  mov     rax, [rbx+38h]
0x180006c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c41  xor     r8d, r8d; int
0x180006c44  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180006c47  mov     rcx, [rbx]; rguid
0x180006c4a  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180006c4f  test    eax, eax
0x180006c51  js      loc_180006CD7
0x180006c57  xor     ecx, ecx
0x180006c59  mov     rax, [rbx+8]
0x180006c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c62  test    eax, eax
0x180006c64  js      short loc_180006CD7
0x180006c66  add     rbx, 48h ; 'H'
0x180006c6a  cmp     qword ptr [rbx], 0
0x180006c6e  jnz     short loc_180006C38
0x180006c70  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x180006c77  test    rax, rax
0x180006c7a  jz      short loc_180006C85
0x180006c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c81  test    eax, eax
0x180006c83  js      short loc_180006CD7
0x180006c85  mov     rbx, cs:off_180013110
0x180006c8c  mov     rax, cs:off_180013118
0x180006c93  jmp     short loc_180006CD2
0x180006c95  mov     rdi, [rbx]
0x180006c98  test    rdi, rdi
0x180006c9b  jz      short loc_180006CCE
0x180006c9d  mov     rax, [rdi+38h]
0x180006ca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ca6  xor     r8d, r8d; int
0x180006ca9  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180006cac  mov     rcx, [rdi]; rguid
0x180006caf  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180006cb4  test    eax, eax
0x180006cb6  js      short loc_180006CD7
0x180006cb8  xor     ecx, ecx
0x180006cba  mov     rax, [rdi+8]
0x180006cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cc3  test    eax, eax
0x180006cc5  js      short loc_180006CD7
0x180006cc7  mov     rax, cs:off_180013118
0x180006cce  add     rbx, 8
0x180006cd2  cmp     rbx, rax
0x180006cd5  jb      short loc_180006C95
0x180006cd7  mov     [rsp+38h+hKey], 0
0x180006ce0  lea     rax, [rsp+38h+hKey]
0x180006ce5  mov     [rsp+38h+phkResult], rax; phkResult
0x180006cea  mov     r9d, 0F003Fh; samDesired
0x180006cf0  xor     r8d, r8d; ulOptions
0x180006cf3  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180006cfa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006d01  call    cs:__imp_RegOpenKeyExW
0x180006d07  test    eax, eax
0x180006d09  jnz     short loc_180006D28
0x180006d0b  lea     rdx, ValueName; "{ECCDF543-45CC-11CE-B9BF-0080C87CDBA6}"
0x180006d12  mov     rcx, [rsp+38h+hKey]; hKey
0x180006d17  call    cs:__imp_RegDeleteValueW
0x180006d1d  mov     rcx, [rsp+38h+hKey]; hKey
0x180006d22  call    cs:__imp_RegCloseKey
0x180006d28  xor     eax, eax
0x180006d2a  mov     rbx, [rsp+38h+arg_8]
0x180006d2f  add     rsp, 30h
0x180006d33  pop     rdi
0x180006d34  retn
```
