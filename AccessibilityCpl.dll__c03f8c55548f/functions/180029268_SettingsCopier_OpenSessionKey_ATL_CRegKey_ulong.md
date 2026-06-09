# SettingsCopier::OpenSessionKey(ATL::CRegKey &,ulong)

- ea: `0x180029268`
- end: `0x1800293bb`
- name: `?OpenSessionKey@SettingsCopier@@AEAAJAEAVCRegKey@ATL@@K@Z`
- size: `339`
- prototype: `int(SettingsCopier *__hidden this, struct ATL::CRegKey *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180029144`

## callees

- `0x1800057d4`
- `0x180014828`
- `0x180015780`
- `0x18001a6c0`
- `0x18001e984`
- `0x180021704`
- `0x180029268`
- `0x1800296b8`

## import_xrefs

- `msvcrt!free` at `0x18002936d`
- `msvcrt!free` at `0x180029389`
- `msvcrt!free` at `0x18002936d`
- `msvcrt!free` at `0x180029389`

## string_xrefs

- `0x1800292a1`: `%s\ATConfig`
- `0x180029302`: `%s\ATConfig`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SettingsCopier::OpenSessionKey(SettingsCopier *this, struct ATL::CRegKey *a2)
{
  unsigned int v3; // r11d
  char *v4; // rdi
  unsigned int v5; // edi
  unsigned __int16 *v6; // r9
  HKEY v8; // [rsp+30h] [rbp-20h]
  unsigned __int64 v9; // [rsp+40h] [rbp-10h] BYREF
  void *Block; // [rsp+70h] [rbp+20h] BYREF
  unsigned int v11; // [rsp+80h] [rbp+30h] BYREF
  unsigned __int16 *v12; // [rsp+88h] [rbp+38h] BYREF

  Block = this;
  CATUtils::SessionKeyString((__int64)&v12);
  Block = 0;
  v9 = 0;
  if ( (int)StringCchLengthW(SettingsCopier::_ATSessionConfigKeyString, 0x7FFFFFFFu, (unsigned __int64 *)&Block) < 0
    || (int)StringCchLengthW(v12, v3, &v9) < 0
    || (v4 = (char *)Block + v9, (char *)Block + v9 < Block) )
  {
    ATL::CStringData::Release((ATL::CStringData *)(v12 - 12));
    return 2147500037LL;
  }
  else
  {
    Block = 0;
    if ( !(unsigned __int8)ATL::CHeapPtr<unsigned short,ATL::CCRTAllocator>::Allocate(&Block, v4) )
    {
      v5 = -2147024882;
LABEL_10:
      free(Block);
      ATL::CStringData::Release((ATL::CStringData *)(v12 - 12));
      return v5;
    }
    if ( StringCchPrintfW(
           (unsigned __int16 *)Block,
           (unsigned __int64)v4,
           SettingsCopier::_ATSessionConfigKeyString,
           v12) < 0
      || (unsigned int)ATL::CRegKey::Open(a2, HKEY_LOCAL_MACHINE, (LPCWSTR)Block, 0x2001Fu)
      && (unsigned int)ATL::CRegKey::Create(a2, HKEY_LOCAL_MACHINE, (LPCWSTR)Block, v6, 1u, 0x2001Fu, v8, &v11) )
    {
      v5 = -2147467259;
      goto LABEL_10;
    }
    free(Block);
    ATL::CStringData::Release((ATL::CStringData *)(v12 - 12));
    return 0;
  }
}

```

## disassembly

```asm
0x180029268  mov     [rsp-18h+Block], rcx
0x18002926d  push    rbp
0x18002926e  push    rsi
0x18002926f  push    rdi
0x180029270  mov     rbp, rsp
0x180029273  sub     rsp, 50h
0x180029277  mov     rsi, rdx
0x18002927a  lea     rcx, [rbp+arg_18]
0x18002927e  call    ?SessionKeyString@CATUtils@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CATUtils::SessionKeyString(void)
0x180029283  nop
0x180029284  mov     [rbp+Block], 0
0x18002928c  mov     [rbp+var_10], 0
0x180029294  lea     r8, [rbp+Block]; unsigned __int64 *
0x180029298  mov     r11d, 7FFFFFFFh
0x18002929e  mov     edx, r11d; unsigned __int64
0x1800292a1  lea     rcx, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x1800292a8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800292ad  test    eax, eax
0x1800292af  js      loc_1800293A1
0x1800292b5  lea     r8, [rbp+var_10]; unsigned __int64 *
0x1800292b9  mov     edx, r11d; unsigned __int64
0x1800292bc  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x1800292c0  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800292c5  test    eax, eax
0x1800292c7  js      loc_1800293A1
0x1800292cd  mov     rdi, [rbp+var_10]
0x1800292d1  add     rdi, [rbp+Block]
0x1800292d5  cmp     rdi, [rbp+Block]
0x1800292d9  jb      loc_1800293A1
0x1800292df  mov     [rbp+Block], 0
0x1800292e7  mov     rdx, rdi
0x1800292ea  lea     rcx, [rbp+Block]
0x1800292ee  call    ?Allocate@?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@QEAA_N_K@Z; ATL::CHeapPtr<ushort,ATL::CCRTAllocator>::Allocate(unsigned __int64)
0x1800292f3  test    al, al
0x1800292f5  jnz     short loc_1800292FE
0x1800292f7  mov     edi, 8007000Eh
0x1800292fc  jmp     short loc_180029369
0x1800292fe  mov     r9, [rbp+arg_18]
0x180029302  lea     r8, ?_ATSessionConfigKeyString@SettingsCopier@@0PAGA; "%s\\ATConfig"
0x180029309  mov     rdx, rdi; unsigned __int64
0x18002930c  mov     rcx, [rbp+Block]; unsigned __int16 *
0x180029310  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029315  test    eax, eax
0x180029317  js      short loc_180029364
0x180029319  mov     edi, 2001Fh
0x18002931e  mov     r9d, edi; unsigned int
0x180029321  mov     r8, [rbp+Block]; lpSubKey
0x180029325  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002932c  mov     rcx, rsi; this
0x18002932f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180029334  test    eax, eax
0x180029336  jz      short loc_180029385
0x180029338  lea     rax, [rbp+arg_10]
0x18002933c  mov     [rsp+50h+var_18], rax; unsigned int *
0x180029341  mov     [rsp+50h+var_28], edi; REGSAM
0x180029345  mov     [rsp+50h+var_30], 1; DWORD
0x18002934d  mov     r8, [rbp+Block]; lpSubKey
0x180029351  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180029358  mov     rcx, rsi; this
0x18002935b  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180029360  test    eax, eax
0x180029362  jz      short loc_180029385
0x180029364  mov     edi, 80004005h
0x180029369  mov     rcx, [rbp+Block]; Block
0x18002936d  call    cs:__imp_free
0x180029373  nop
0x180029374  mov     rcx, [rbp+arg_18]
0x180029378  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002937c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180029381  mov     eax, edi
0x180029383  jmp     short loc_1800293B3
0x180029385  mov     rcx, [rbp+Block]; Block
0x180029389  call    cs:__imp_free
0x18002938f  nop
0x180029390  mov     rcx, [rbp+arg_18]
0x180029394  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180029398  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002939d  xor     eax, eax
0x18002939f  jmp     short loc_1800293B3
0x1800293a1  mov     rcx, [rbp+arg_18]
0x1800293a5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800293a9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800293ae  mov     eax, 80004005h
0x1800293b3  add     rsp, 50h
0x1800293b7  pop     rdi
0x1800293b8  pop     rsi
0x1800293b9  pop     rbp
0x1800293ba  retn
```
