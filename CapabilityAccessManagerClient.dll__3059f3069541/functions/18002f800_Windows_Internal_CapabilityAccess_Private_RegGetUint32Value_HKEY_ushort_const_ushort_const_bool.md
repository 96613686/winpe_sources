# Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)

- ea: `0x18002f800`
- end: `0x18002f876`
- name: `?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z`
- size: `118`
- prototype: `unsigned int __fastcall(Windows::Internal::CapabilityAccess::Private *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002a1a8`
- `0x18002a1f4`
- `0x18002a438`
- `0x18002bb68`
- `0x18002ea0c`
- `0x18002ede4`
- `0x18002ee78`
- `0x180035308`

## callees

- `0x1800236ac`
- `0x18002f800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f839`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f839`

## string_xrefs

- `0x18002f84b`: `onecore\base\devices\cam\core\registryhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
        Windows::Internal::CapabilityAccess::Private *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned int ValueW; // eax
  unsigned int v7; // [rsp+20h] [rbp-38h]
  unsigned int v8; // [rsp+40h] [rbp-18h] BYREF
  DWORD v9[5]; // [rsp+44h] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v9[0] = 4;
  v8 = 0;
  ValueW = RegGetValueW((HKEY)this, a2, a3, 0x10010u, 0, &v8, v9);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\registryhelpers.cpp",
      (const char *)ValueW,
      v7);
  if ( a4 )
    *(_BYTE *)a4 = ValueW == 0;
  return v8;
}

```

## disassembly

```asm
0x18002f800  mov     r11, rsp
0x18002f803  push    rbx
0x18002f804  sub     rsp, 50h
0x18002f808  lea     rax, [r11-14h]
0x18002f80c  mov     [rsp+58h+var_14], 4
0x18002f814  mov     [r11-28h], rax
0x18002f818  mov     rbx, r9
0x18002f81b  lea     rax, [r11-18h]
0x18002f81f  mov     [rsp+58h+var_18], 0
0x18002f827  mov     [r11-30h], rax
0x18002f82b  mov     r9d, 10010h; dwFlags
0x18002f831  mov     qword ptr [r11-38h], 0
0x18002f839  call    cs:__imp_RegGetValueW
0x18002f83f  test    eax, 0FFFFFFFDh
0x18002f844  jz      short loc_18002F860
0x18002f846  mov     rcx, [rsp+58h]; this
0x18002f84b  lea     r8, aOnecoreBaseDev_7; "onecore\\base\\devices\\cam\\core\\regi"...
0x18002f852  mov     r9d, eax; char *
0x18002f855  mov     edx, 76h ; 'v'; void *
0x18002f85a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002f860  test    rbx, rbx
0x18002f863  jz      short loc_18002F86C
0x18002f865  test    eax, eax
0x18002f867  setz    al
0x18002f86a  mov     [rbx], al
0x18002f86c  mov     eax, [rsp+58h+var_18]
0x18002f870  add     rsp, 50h
0x18002f874  pop     rbx
0x18002f875  retn
```
