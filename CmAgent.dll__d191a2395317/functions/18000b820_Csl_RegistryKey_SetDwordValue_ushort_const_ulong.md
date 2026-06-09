# Csl::RegistryKey::SetDwordValue(ushort const *,ulong)

- ea: `0x18000b820`
- end: `0x18000b88c`
- name: `?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z`
- size: `108`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005050`
- `0x1800200e4`
- `0x180022894`
- `0x180023090`

## callees

- `0x18000b7e0`
- `0x18000b820`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b847`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b847`

## string_xrefs

- `0x18000b868`: `onecore\base\gendrv\silos\csl\lib\cslregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::RegistryKey::SetDwordValue(HKEY *this, const unsigned __int16 *a2, int a3)
{
  unsigned int v4; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = a3;
  v4 = RegSetValueExW(*this, a2, 0, 4u, (const BYTE *)&v7, 4u);
  if ( v4 )
    return wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x21C,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslregistry.cpp",
             (const char *)v4,
             (unsigned int)"Failed to set dword value with name '%ws'",
             (const char *)a2);
  else
    return 0;
}

```

## disassembly

```asm
0x18000b820  mov     r11, rsp
0x18000b823  mov     [r11+18h], r8d
0x18000b827  push    rbx
0x18000b828  sub     rsp, 30h
0x18000b82c  mov     rcx, [rcx]; hKey
0x18000b82f  lea     rax, [r11+18h]
0x18000b833  mov     r9d, 4; dwType
0x18000b839  xor     r8d, r8d; Reserved
0x18000b83c  mov     [r11-10h], r9d
0x18000b840  mov     rbx, rdx
0x18000b843  mov     [r11-18h], rax
0x18000b847  call    cs:__imp_RegSetValueExW
0x18000b84e  nop     dword ptr [rax+rax+00h]
0x18000b853  test    eax, eax
0x18000b855  jz      short loc_18000B883
0x18000b857  mov     rcx, [rsp+38h]; this
0x18000b85c  lea     rdx, aFailedToSetDwo; "Failed to set dword value with name '%w"...
0x18000b863  mov     [rsp+38h+var_10], rbx; char *
0x18000b868  lea     r8, aOnecoreBaseGen_13; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000b86f  mov     qword ptr [rsp+38h+var_18], rdx; unsigned int
0x18000b874  mov     r9d, eax; char *
0x18000b877  mov     edx, 21Ch; void *
0x18000b87c  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000b881  jmp     short loc_18000B885
0x18000b883  xor     eax, eax
0x18000b885  add     rsp, 30h
0x18000b889  pop     rbx
0x18000b88a  retn
```
