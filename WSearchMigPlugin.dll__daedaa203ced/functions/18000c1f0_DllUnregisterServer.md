# DllUnregisterServer

- ea: `0x18000c1f0`
- end: `0x18000c24f`
- name: `DllUnregisterServer`
- size: `95`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000be14`
- `0x18000c1f0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000c211`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000c23c`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000c211`
- `api-ms-win-core-localization-l1-2-0!SetThreadLocale` at `0x18000c23c`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000c204`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x18000c204`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // edi
  const wchar_t *v1; // rdx
  GUID *v2; // rcx
  struct ITypeLib *v3; // r8
  int v4; // eax
  HRESULT v5; // ebx

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  if ( !ATL::_pPerfUnRegFunc || (v4 = ATL::_pPerfUnRegFunc(), v4 >= 0) )
    v4 = ATL::CAtlComModule::UnregisterServer(v2, v1, v3);
  v5 = 0;
  if ( v4 < 0 )
    v5 = v4;
  SetThreadLocale(ThreadLocale);
  return v5;
}

```

## disassembly

```asm
0x18000c1f0  push    rdi
0x18000c1f2  sub     rsp, 30h
0x18000c1f6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000c1ff  mov     [rsp+38h+arg_0], rbx
0x18000c204  call    cs:__imp_GetThreadLocale
0x18000c20a  mov     edi, eax
0x18000c20c  mov     ecx, 800h; Locale
0x18000c211  call    cs:__imp_SetThreadLocale
0x18000c217  nop
0x18000c218  mov     rax, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x18000c21f  test    rax, rax
0x18000c222  jz      short loc_18000C22D
0x18000c224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c229  test    eax, eax
0x18000c22b  js      short loc_18000C233
0x18000c22d  call    ?UnregisterServer@CAtlComModule@ATL@@QEAAJHPEBU_GUID@@@Z; ATL::CAtlComModule::UnregisterServer(int,_GUID const *)
0x18000c232  nop
0x18000c233  xor     ebx, ebx
0x18000c235  test    eax, eax
0x18000c237  cmovs   ebx, eax
0x18000c23a  mov     ecx, edi; Locale
0x18000c23c  call    cs:__imp_SetThreadLocale
0x18000c242  mov     eax, ebx
0x18000c244  mov     rbx, [rsp+38h+arg_0]
0x18000c249  add     rsp, 30h
0x18000c24d  pop     rdi
0x18000c24e  retn
```
