# DllRegisterServer

- ea: `0x1800013c0`
- end: `0x180001488`
- name: `DllRegisterServer`
- size: `200`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800013c0`
- `0x180001618`
- `0x180001a38`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x1800013e1`
- `KERNEL32!SetThreadLocale` at `0x18000146b`
- `KERNEL32!SetThreadLocale` at `0x1800013e1`
- `KERNEL32!SetThreadLocale` at `0x18000146b`
- `KERNEL32!GetThreadLocale` at `0x1800013d4`
- `KERNEL32!GetThreadLocale` at `0x1800013d4`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  LCID ThreadLocale; // ebp
  const unsigned __int16 *v1; // rdx
  const unsigned __int16 *v2; // rdi
  __int64 v3; // rsi
  HRESULT v4; // ebx
  const struct ATL::_ATL_CATMAP_ENTRY *v5; // rax

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v1 = qword_18003EF78;
  v2 = (const unsigned __int16 *)qword_18003EF70;
  if ( qword_18003EF70 < (unsigned __int64)qword_18003EF78 )
  {
    do
    {
      v3 = *(_QWORD *)v2;
      if ( *(_QWORD *)v2 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64))(v3 + 8))(1);
        if ( v4 < 0 )
          goto LABEL_8;
        v5 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v3 + 48))();
        v4 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v3, v5, 1);
        if ( v4 < 0 )
          goto LABEL_8;
        v1 = qword_18003EF78;
      }
      v2 += 4;
    }
    while ( v2 < v1 );
  }
  v4 = ATL::AtlRegisterTypeLib(qword_18003EF68, v1);
LABEL_8:
  if ( v4 >= 0 && ATL::_pPerfRegFunc )
    v4 = ATL::_pPerfRegFunc(hModule);
  SetThreadLocale(ThreadLocale);
  return v4;
}

```

## disassembly

```asm
0x1800013c0  mov     [rsp+arg_0], rbx
0x1800013c5  mov     [rsp+arg_8], rbp
0x1800013ca  mov     [rsp+arg_10], rsi
0x1800013cf  push    rdi
0x1800013d0  sub     rsp, 20h
0x1800013d4  call    cs:__imp_GetThreadLocale
0x1800013da  mov     ecx, 800h; Locale
0x1800013df  mov     ebp, eax
0x1800013e1  call    cs:__imp_SetThreadLocale
0x1800013e7  mov     rdx, cs:qword_18003EF78
0x1800013ee  xor     ebx, ebx
0x1800013f0  mov     rdi, cs:qword_18003EF70
0x1800013f7  cmp     rdi, rdx
0x1800013fa  jnb     short loc_180001440
0x1800013fc  mov     rsi, [rdi]
0x1800013ff  test    rsi, rsi
0x180001402  jz      short loc_180001433
0x180001404  mov     ecx, 1
0x180001409  call    qword ptr [rsi+8]
0x18000140c  mov     ebx, eax
0x18000140e  test    eax, eax
0x180001410  js      short loc_18000144E
0x180001412  call    qword ptr [rsi+30h]
0x180001415  mov     rcx, [rsi]; rguid
0x180001418  mov     r8d, 1; int
0x18000141e  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x180001421  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x180001426  mov     ebx, eax
0x180001428  test    eax, eax
0x18000142a  js      short loc_18000144E
0x18000142c  mov     rdx, cs:qword_18003EF78; unsigned __int16 *
0x180001433  add     rdi, 8
0x180001437  cmp     rdi, rdx
0x18000143a  jb      short loc_1800013FC
0x18000143c  test    ebx, ebx
0x18000143e  js      short loc_180001469
0x180001440  mov     rcx, cs:qword_18003EF68; HINSTANCE
0x180001447  call    ?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x18000144c  mov     ebx, eax
0x18000144e  test    ebx, ebx
0x180001450  js      short loc_180001469
0x180001452  mov     rax, cs:?_pPerfRegFunc@ATL@@3P6AJPEAUHINSTANCE__@@@ZEA; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180001459  test    rax, rax
0x18000145c  jz      short loc_180001469
0x18000145e  mov     rcx, cs:hModule
0x180001465  call    rax ; long (*ATL::_pPerfRegFunc)(HINSTANCE__ *)
0x180001467  mov     ebx, eax
0x180001469  mov     ecx, ebp; Locale
0x18000146b  call    cs:__imp_SetThreadLocale
0x180001471  mov     rbp, [rsp+28h+arg_8]
0x180001476  mov     eax, ebx
0x180001478  mov     rbx, [rsp+28h+arg_0]
0x18000147d  mov     rsi, [rsp+28h+arg_10]
0x180001482  add     rsp, 20h
0x180001486  pop     rdi
0x180001487  retn
```
