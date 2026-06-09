# VFreeOemPluginInfoInternal

- ea: `0x180026ae0`
- end: `0x180026ba4`
- name: `VFreeOemPluginInfoInternal`
- size: `196`
- prototype: `HLOCAL __fastcall(_DWORD *, DWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180026904`
- `0x180028534`

## callees

- `0x180026ae0`
- `0x18003d00c`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x180026b50`
- `WINSPOOL!GetPrinterDataW` at `0x180026b50`
- `KERNEL32!LocalFree` at `0x180026b98`

## string_xrefs

- `0x180026b49`: `DoNotUnloadPluginDLL`

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
0x180026ae0  mov     [rsp+arg_8], edx
0x180026ae4  push    rbx
0x180026ae5  push    rsi
0x180026ae6  push    rdi
0x180026ae7  sub     rsp, 30h
0x180026aeb  mov     esi, [rcx+8]
0x180026aee  lea     rbx, [rcx+18h]
0x180026af2  mov     rdi, rcx
0x180026af5  jmp     loc_180026B86
0x180026afa  mov     eax, [rdi+8]
0x180026afd  dec     esi
0x180026aff  mov     [rsp+48h+pType], 0
0x180026b07  mov     [rsp+48h+arg_8], 0
0x180026b0f  mov     [rsp+48h+pData], 0
0x180026b17  test    eax, eax
0x180026b19  jz      short loc_180026B6D
0x180026b1b  dec     eax
0x180026b1d  cmp     esi, eax
0x180026b1f  jnz     short loc_180026B6D
0x180026b21  mov     rcx, [rdi]
0x180026b24  test    rcx, rcx
0x180026b27  jz      short loc_180026B77
0x180026b29  mov     rcx, [rcx+18h]; hPrinter
0x180026b2d  lea     rax, [rsp+48h+arg_8]
0x180026b32  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x180026b37  lea     r9, [rsp+48h+pData]; pData
0x180026b3c  lea     r8, [rsp+48h+pType]; pType
0x180026b41  mov     [rsp+48h+nSize], 4; nSize
0x180026b49  lea     rdx, aDonotunloadplu; "DoNotUnloadPluginDLL"
0x180026b50  call    cs:__imp_GetPrinterDataW
0x180026b57  nop     dword ptr [rax+rax+00h]
0x180026b5c  test    eax, eax
0x180026b5e  jnz     short loc_180026B77
0x180026b60  cmp     [rsp+48h+arg_8], 4
0x180026b65  jnz     short loc_180026B77
0x180026b67  cmp     [rsp+48h+pData], eax
0x180026b6b  jmp     short loc_180026B71
0x180026b6d  test    byte ptr [rbx-80h], 10h
0x180026b71  jz      short loc_180026B77
0x180026b73  or      dword ptr [rbx+30h], 10h
0x180026b77  mov     rcx, rbx
0x180026b7a  call    ?VFreeSinglePluginEntry@@YAXPEAU_OEM_PLUGIN_ENTRY@@W4BPluginRequestType@@@Z; VFreeSinglePluginEntry(_OEM_PLUGIN_ENTRY *,BPluginRequestType)
0x180026b7f  add     rbx, 0B0h
0x180026b86  test    esi, esi
0x180026b88  jnz     loc_180026AFA
0x180026b8e  mov     rcx, rdi
0x180026b91  add     rsp, 30h
0x180026b95  pop     rdi
0x180026b96  pop     rsi
0x180026b97  pop     rbx
0x180026b98  jmp     cs:__imp_LocalFree
```
