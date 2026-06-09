# Csl::RegistryKey::SetStringValue(ushort const *,ushort const *,ulong)

- ea: `0x18000b894`
- end: `0x18000b8fb`
- name: `?SetStringValue@RegistryKey@Csl@@QEAAJPEBG0K@Z`
- size: `103`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, const BYTE *lpData, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800178e0`
- `0x180022894`
- `0x180023090`

## callees

- `0x18000b7e0`
- `0x18000b894`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b8b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b8b6`

## string_xrefs

- `0x18000b8d7`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::RegistryKey::SetStringValue(HKEY *this, const unsigned __int16 *a2, const BYTE *lpData, int a4)
{
  unsigned int v5; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = RegSetValueExW(*this, a2, 0, 1u, lpData, 2 * a4);
  if ( v5 )
    return wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x32D,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
             (const char *)v5,
             (unsigned int)"Failed to set string value with name '%ws'",
             (const char *)a2);
  else
    return 0;
}

```

## disassembly

```asm
0x18000b894  push    rbx
0x18000b896  sub     rsp, 30h
0x18000b89a  mov     rcx, [rcx]; hKey
0x18000b89d  lea     eax, [r9+r9]
0x18000b8a1  mov     [rsp+38h+cbData], eax; cbData
0x18000b8a5  mov     r9d, 1; dwType
0x18000b8ab  mov     [rsp+38h+lpData], r8; lpData
0x18000b8b0  mov     rbx, rdx
0x18000b8b3  xor     r8d, r8d; Reserved
0x18000b8b6  call    cs:__imp_RegSetValueExW
0x18000b8bd  nop     dword ptr [rax+rax+00h]
0x18000b8c2  test    eax, eax
0x18000b8c4  jz      short loc_18000B8F2
0x18000b8c6  mov     rcx, [rsp+38h]; this
0x18000b8cb  lea     rdx, aFailedToSetStr; "Failed to set string value with name '%"...
0x18000b8d2  mov     qword ptr [rsp+38h+cbData], rbx; char *
0x18000b8d7  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000b8de  mov     [rsp+38h+lpData], rdx; unsigned int
0x18000b8e3  mov     r9d, eax; char *
0x18000b8e6  mov     edx, 32Dh; void *
0x18000b8eb  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000b8f0  jmp     short loc_18000B8F4
0x18000b8f2  xor     eax, eax
0x18000b8f4  add     rsp, 30h
0x18000b8f8  pop     rbx
0x18000b8f9  retn
```
