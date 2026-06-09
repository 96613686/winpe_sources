# DllUnregisterServer

- ea: `0x180001490`
- end: `0x18000154a`
- name: `DllUnregisterServer`
- size: `186`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001490`
- `0x180001a38`
- `0x18000214c`

## import_xrefs

- `KERNEL32!SetThreadLocale` at `0x1800014b1`
- `KERNEL32!SetThreadLocale` at `0x18000152d`
- `KERNEL32!SetThreadLocale` at `0x1800014b1`
- `KERNEL32!SetThreadLocale` at `0x18000152d`
- `KERNEL32!GetThreadLocale` at `0x1800014a4`
- `KERNEL32!GetThreadLocale` at `0x1800014a4`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  LCID ThreadLocale; // ebp
  const unsigned __int16 *v1; // rdx
  HRESULT v2; // ebx
  int v3; // eax
  bool v4; // sf
  unsigned __int16 *v5; // rdi
  unsigned __int16 *v6; // rcx
  __int64 v7; // rsi
  const struct ATL::_ATL_CATMAP_ENTRY *v8; // rax

  ThreadLocale = GetThreadLocale();
  SetThreadLocale(0x800u);
  v2 = 0;
  if ( !ATL::_pPerfUnRegFunc || (v3 = ATL::_pPerfUnRegFunc(), v4 = v3 < 0, v3 >= 0) )
  {
    v5 = (unsigned __int16 *)qword_18003EF70;
    v6 = qword_18003EF78;
    if ( qword_18003EF70 < (unsigned __int64)qword_18003EF78 )
    {
      do
      {
        v7 = *(_QWORD *)v5;
        if ( *(_QWORD *)v5 )
        {
          v8 = (const struct ATL::_ATL_CATMAP_ENTRY *)(*(__int64 (**)(void))(v7 + 48))();
          v3 = ATL::AtlRegisterClassCategoriesHelper(*(GUID **)v7, v8, 0);
          v4 = v3 < 0;
          if ( v3 < 0 )
            goto LABEL_10;
          v3 = (*(__int64 (__fastcall **)(_QWORD))(v7 + 8))(0);
          v4 = v3 < 0;
          if ( v3 < 0 )
            goto LABEL_10;
          v6 = qword_18003EF78;
        }
        v5 += 4;
      }
      while ( v5 < v6 );
    }
    v3 = ATL::AtlUnRegisterTypeLib(qword_18003EF68, v1);
    v4 = v3 < 0;
  }
LABEL_10:
  if ( v4 )
    v2 = v3;
  SetThreadLocale(ThreadLocale);
  return v2;
}

```

## disassembly

```asm
0x180001490  mov     [rsp+arg_0], rbx
0x180001495  mov     [rsp+arg_8], rbp
0x18000149a  mov     [rsp+arg_10], rsi
0x18000149f  push    rdi
0x1800014a0  sub     rsp, 20h
0x1800014a4  call    cs:__imp_GetThreadLocale
0x1800014aa  mov     ecx, 800h; Locale
0x1800014af  mov     ebp, eax
0x1800014b1  call    cs:__imp_SetThreadLocale
0x1800014b7  mov     rcx, cs:?_pPerfUnRegFunc@ATL@@3P6AJXZEA; long (*ATL::_pPerfUnRegFunc)(void)
0x1800014be  xor     ebx, ebx
0x1800014c0  test    rcx, rcx
0x1800014c3  jz      short loc_1800014CB
0x1800014c5  call    rcx ; long (*ATL::_pPerfUnRegFunc)(void)
0x1800014c7  test    eax, eax
0x1800014c9  js      short loc_180001528
0x1800014cb  mov     rdi, cs:qword_18003EF70
0x1800014d2  mov     eax, ebx
0x1800014d4  mov     rcx, cs:qword_18003EF78
0x1800014db  cmp     rdi, rcx
0x1800014de  jnb     short loc_18000151A
0x1800014e0  mov     rsi, [rdi]
0x1800014e3  test    rsi, rsi
0x1800014e6  jz      short loc_18000150D
0x1800014e8  call    qword ptr [rsi+30h]
0x1800014eb  mov     rcx, [rsi]; rguid
0x1800014ee  xor     r8d, r8d; int
0x1800014f1  mov     rdx, rax; struct ATL::_ATL_CATMAP_ENTRY *
0x1800014f4  call    ?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z; ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)
0x1800014f9  test    eax, eax
0x1800014fb  js      short loc_180001528
0x1800014fd  xor     ecx, ecx
0x1800014ff  call    qword ptr [rsi+8]
0x180001502  test    eax, eax
0x180001504  js      short loc_180001528
0x180001506  mov     rcx, cs:qword_18003EF78
0x18000150d  add     rdi, 8
0x180001511  cmp     rdi, rcx
0x180001514  jb      short loc_1800014E0
0x180001516  test    eax, eax
0x180001518  js      short loc_180001528
0x18000151a  mov     rcx, cs:qword_18003EF68; HINSTANCE
0x180001521  call    ?AtlUnRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z; ATL::AtlUnRegisterTypeLib(HINSTANCE__ *,ushort const *)
0x180001526  test    eax, eax
0x180001528  mov     ecx, ebp; Locale
0x18000152a  cmovs   ebx, eax
0x18000152d  call    cs:__imp_SetThreadLocale
0x180001533  mov     rbp, [rsp+28h+arg_8]
0x180001538  mov     eax, ebx
0x18000153a  mov     rbx, [rsp+28h+arg_0]
0x18000153f  mov     rsi, [rsp+28h+arg_10]
0x180001544  add     rsp, 20h
0x180001548  pop     rdi
0x180001549  retn
```
