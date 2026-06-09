# Csl::RegistryKey::GetDwordValue(ushort const *,ulong &)

- ea: `0x18000b304`
- end: `0x18000b3a8`
- name: `?GetDwordValue@RegistryKey@Csl@@QEBAJPEBGAEAK@Z`
- size: `164`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800171d8`
- `0x180022c10`

## callees

- `0x18000b304`
- `0x18000b7e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b34c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b34c`

## string_xrefs

- `0x18000b372`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::RegistryKey::GetDwordValue(HKEY *this, const unsigned __int16 *a2, unsigned int *a3)
{
  HKEY v3; // rcx
  unsigned int ValueW; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v9; // [rsp+50h] [rbp+8h] BYREF
  DWORD v10; // [rsp+68h] [rbp+20h] BYREF

  v3 = *this;
  v9 = 0;
  v10 = 4;
  ValueW = RegGetValueW(v3, 0, a2, 0x10u, 0, &v9, &v10);
  if ( ValueW == 2 )
    return 2147942402LL;
  if ( ValueW )
    return wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x1FE,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
             (const char *)ValueW,
             (unsigned int)"Failed to get dword value with name '%ws'",
             (const char *)a2);
  *a3 = v9;
  return 0;
}

```

## disassembly

```asm
0x18000b304  mov     r11, rsp
0x18000b307  mov     [r11+10h], rbx
0x18000b30b  push    rdi
0x18000b30c  sub     rsp, 40h
0x18000b310  mov     rcx, [rcx]; hkey
0x18000b313  lea     rax, [r11+20h]
0x18000b317  mov     [r11-18h], rax
0x18000b31b  mov     rbx, r8
0x18000b31e  lea     rax, [r11+8]
0x18000b322  mov     [rsp+48h+arg_0], 0
0x18000b32a  mov     rdi, rdx
0x18000b32d  mov     [r11-20h], rax
0x18000b331  mov     r8, rdx; lpValue
0x18000b334  mov     qword ptr [r11-28h], 0
0x18000b33c  mov     r9d, 10h; dwFlags
0x18000b342  mov     [rsp+48h+arg_18], 4
0x18000b34a  xor     edx, edx; lpSubKey
0x18000b34c  call    cs:__imp_RegGetValueW
0x18000b353  nop     dword ptr [rax+rax+00h]
0x18000b358  cmp     eax, 2
0x18000b35b  jz      short loc_18000B397
0x18000b35d  test    eax, eax
0x18000b35f  jz      short loc_18000B38D
0x18000b361  mov     rcx, [rsp+48h]; this
0x18000b366  lea     rdx, aFailedToGetDwo; "Failed to get dword value with name '%w"...
0x18000b36d  mov     [rsp+48h+var_20], rdi; char *
0x18000b372  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000b379  mov     qword ptr [rsp+48h+var_28], rdx; unsigned int
0x18000b37e  mov     r9d, eax; char *
0x18000b381  mov     edx, 1FEh; void *
0x18000b386  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000b38b  jmp     short loc_18000B39C
0x18000b38d  mov     eax, [rsp+48h+arg_0]
0x18000b391  mov     [rbx], eax
0x18000b393  xor     eax, eax
0x18000b395  jmp     short loc_18000B39C
0x18000b397  mov     eax, 80070002h
0x18000b39c  mov     rbx, [rsp+48h+arg_8]
0x18000b3a1  add     rsp, 40h
0x18000b3a5  pop     rdi
0x18000b3a6  retn
```
