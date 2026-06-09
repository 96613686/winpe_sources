# Windows::Internal::CapabilityAccess::Private::RegGetUint64Value(HKEY__ *,ushort const *,ushort const *,bool *)

- ea: `0x18002f87c`
- end: `0x18002f8f3`
- name: `?RegGetUint64Value@Private@CapabilityAccess@Internal@Windows@@YA_KPEAUHKEY__@@PEBG1PEA_N@Z`
- size: `119`
- prototype: `unsigned __int64 __fastcall(Windows::Internal::CapabilityAccess::Private *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002a438`

## callees

- `0x1800236ac`
- `0x18002f87c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f8b5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002f8b5`

## string_xrefs

- `0x18002f8c7`: `onecore\base\devices\cam\core\registryhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::RegGetUint64Value(
        Windows::Internal::CapabilityAccess::Private *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned int ValueW; // eax
  unsigned int v7; // [rsp+20h] [rbp-38h]
  DWORD v8; // [rsp+40h] [rbp-18h] BYREF
  __int64 v9; // [rsp+48h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = 8;
  v9 = 0;
  ValueW = RegGetValueW((HKEY)this, a2, a3, 0x10048u, 0, &v9, &v8);
  if ( (ValueW & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\registryhelpers.cpp",
      (const char *)ValueW,
      v7);
  if ( a4 )
    *(_BYTE *)a4 = ValueW == 0;
  return v9;
}

```

## disassembly

```asm
0x18002f87c  mov     r11, rsp
0x18002f87f  push    rbx
0x18002f880  sub     rsp, 50h
0x18002f884  lea     rax, [r11-18h]
0x18002f888  mov     [rsp+58h+var_18], 8
0x18002f890  mov     [r11-28h], rax
0x18002f894  mov     rbx, r9
0x18002f897  lea     rax, [r11-10h]
0x18002f89b  mov     qword ptr [r11-10h], 0
0x18002f8a3  mov     [r11-30h], rax
0x18002f8a7  mov     r9d, 10048h; dwFlags
0x18002f8ad  mov     qword ptr [r11-38h], 0
0x18002f8b5  call    cs:__imp_RegGetValueW
0x18002f8bb  test    eax, 0FFFFFFFDh
0x18002f8c0  jz      short loc_18002F8DC
0x18002f8c2  mov     rcx, [rsp+58h]; this
0x18002f8c7  lea     r8, aOnecoreBaseDev_7; "onecore\\base\\devices\\cam\\core\\regi"...
0x18002f8ce  mov     r9d, eax; char *
0x18002f8d1  mov     edx, 0A3h; void *
0x18002f8d6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002f8dc  test    rbx, rbx
0x18002f8df  jz      short loc_18002F8E8
0x18002f8e1  test    eax, eax
0x18002f8e3  setz    al
0x18002f8e6  mov     [rbx], al
0x18002f8e8  mov     rax, [rsp+58h+var_10]
0x18002f8ed  add     rsp, 50h
0x18002f8f1  pop     rbx
0x18002f8f2  retn
```
