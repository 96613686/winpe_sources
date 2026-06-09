# VFreeOemPluginInfoInternal

- ea: `0x180031a74`
- end: `0x180031b38`
- name: `VFreeOemPluginInfoInternal`
- size: `196`
- prototype: `HLOCAL __fastcall(_DWORD *, DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001fba4`
- `0x18003224c`

## callees

- `0x180031a74`
- `0x180031b40`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x180031ae4`
- `WINSPOOL!GetPrinterDataW` at `0x180031ae4`
- `KERNEL32!LocalFree` at `0x180031b2c`

## string_xrefs

- `0x180031add`: `DoNotUnloadPluginDLL`

## pseudocode

```c
HLOCAL __fastcall VFreeOemPluginInfoInternal(_DWORD *a1, DWORD a2)
{
  int v2; // esi
  _DWORD *v3; // rbx
  int v5; // eax
  bool v6; // zf
  int pData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbNeeded; // [rsp+58h] [rbp+10h] BYREF
  DWORD pType; // [rsp+60h] [rbp+18h] BYREF

  pcbNeeded = a2;
  v2 = a1[2];
  v3 = a1 + 6;
  while ( v2 )
  {
    v5 = a1[2];
    --v2;
    pType = 0;
    pcbNeeded = 0;
    pData = 0;
    if ( v5 && v2 == v5 - 1 )
    {
      if ( !*(_QWORD *)a1
        || GetPrinterDataW(
             *(HANDLE *)(*(_QWORD *)a1 + 24LL),
             (LPWSTR)L"DoNotUnloadPluginDLL",
             &pType,
             (LPBYTE)&pData,
             4u,
             &pcbNeeded)
        || pcbNeeded != 4 )
      {
        goto LABEL_11;
      }
      v6 = pData == 0;
    }
    else
    {
      v6 = (*(_BYTE *)(v3 - 32) & 0x10) == 0;
    }
    if ( !v6 )
      v3[12] |= 0x10u;
LABEL_11:
    VFreeSinglePluginEntry((__int64)v3);
    v3 += 44;
  }
  return LocalFree(a1);
}

```

## disassembly

```asm
0x180031a74  mov     [rsp+arg_8], edx
0x180031a78  push    rbx
0x180031a79  push    rsi
0x180031a7a  push    rdi
0x180031a7b  sub     rsp, 30h
0x180031a7f  mov     esi, [rcx+8]
0x180031a82  lea     rbx, [rcx+18h]
0x180031a86  mov     rdi, rcx
0x180031a89  jmp     loc_180031B1A
0x180031a8e  mov     eax, [rdi+8]
0x180031a91  dec     esi
0x180031a93  mov     [rsp+48h+pType], 0
0x180031a9b  mov     [rsp+48h+arg_8], 0
0x180031aa3  mov     [rsp+48h+pData], 0
0x180031aab  test    eax, eax
0x180031aad  jz      short loc_180031B01
0x180031aaf  dec     eax
0x180031ab1  cmp     esi, eax
0x180031ab3  jnz     short loc_180031B01
0x180031ab5  mov     rcx, [rdi]
0x180031ab8  test    rcx, rcx
0x180031abb  jz      short loc_180031B0B
0x180031abd  mov     rcx, [rcx+18h]; hPrinter
0x180031ac1  lea     rax, [rsp+48h+arg_8]
0x180031ac6  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x180031acb  lea     r9, [rsp+48h+pData]; pData
0x180031ad0  lea     r8, [rsp+48h+pType]; pType
0x180031ad5  mov     [rsp+48h+nSize], 4; nSize
0x180031add  lea     rdx, aDonotunloadplu; "DoNotUnloadPluginDLL"
0x180031ae4  call    cs:__imp_GetPrinterDataW
0x180031aeb  nop     dword ptr [rax+rax+00h]
0x180031af0  test    eax, eax
0x180031af2  jnz     short loc_180031B0B
0x180031af4  cmp     [rsp+48h+arg_8], 4
0x180031af9  jnz     short loc_180031B0B
0x180031afb  cmp     [rsp+48h+pData], eax
0x180031aff  jmp     short loc_180031B05
0x180031b01  test    byte ptr [rbx-80h], 10h
0x180031b05  jz      short loc_180031B0B
0x180031b07  or      dword ptr [rbx+30h], 10h
0x180031b0b  mov     rcx, rbx
0x180031b0e  call    ?VFreeSinglePluginEntry@@YAXPEAU_OEM_PLUGIN_ENTRY@@W4BPluginRequestType@@@Z; VFreeSinglePluginEntry(_OEM_PLUGIN_ENTRY *,BPluginRequestType)
0x180031b13  add     rbx, 0B0h
0x180031b1a  test    esi, esi
0x180031b1c  jnz     loc_180031A8E
0x180031b22  mov     rcx, rdi
0x180031b25  add     rsp, 30h
0x180031b29  pop     rdi
0x180031b2a  pop     rsi
0x180031b2b  pop     rbx
0x180031b2c  jmp     cs:__imp_LocalFree
```
