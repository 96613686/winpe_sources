# VFreeOemPluginInfoInternal

- ea: `0x180030480`
- end: `0x180030539`
- name: `VFreeOemPluginInfoInternal`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001f020`
- `0x180030c2c`

## callees

- `0x180030480`
- `0x180030540`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x1800304f0`
- `WINSPOOL!GetPrinterDataW` at `0x1800304f0`
- `KERNEL32!LocalFree` at `0x180030532`

## string_xrefs

- `0x1800304e9`: `DoNotUnloadPluginDLL`

## pseudocode

```c
HLOCAL __fastcall VFreeOemPluginInfoInternal(_DWORD *a1, DWORD a2)
{
  int v2; // esi
  __int64 v3; // rbx
  int v5; // eax
  bool v6; // zf
  int pData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbNeeded; // [rsp+58h] [rbp+10h] BYREF
  DWORD pType; // [rsp+60h] [rbp+18h] BYREF

  pcbNeeded = a2;
  v2 = a1[2];
  v3 = (__int64)(a1 + 6);
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
      v6 = (*(_BYTE *)(v3 - 128) & 0x10) == 0;
    }
    if ( !v6 )
      *(_DWORD *)(v3 + 48) |= 0x10u;
LABEL_11:
    VFreeSinglePluginEntry(v3);
    v3 += 176;
  }
  return LocalFree(a1);
}

```

## disassembly

```asm
0x180030480  mov     [rsp+arg_8], edx
0x180030484  push    rbx
0x180030485  push    rsi
0x180030486  push    rdi
0x180030487  sub     rsp, 30h
0x18003048b  mov     esi, [rcx+8]
0x18003048e  lea     rbx, [rcx+18h]
0x180030492  mov     rdi, rcx
0x180030495  jmp     loc_180030520
0x18003049a  mov     eax, [rdi+8]
0x18003049d  dec     esi
0x18003049f  mov     [rsp+48h+pType], 0
0x1800304a7  mov     [rsp+48h+arg_8], 0
0x1800304af  mov     [rsp+48h+pData], 0
0x1800304b7  test    eax, eax
0x1800304b9  jz      short loc_180030507
0x1800304bb  dec     eax
0x1800304bd  cmp     esi, eax
0x1800304bf  jnz     short loc_180030507
0x1800304c1  mov     rcx, [rdi]
0x1800304c4  test    rcx, rcx
0x1800304c7  jz      short loc_180030511
0x1800304c9  mov     rcx, [rcx+18h]; hPrinter
0x1800304cd  lea     rax, [rsp+48h+arg_8]
0x1800304d2  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x1800304d7  lea     r9, [rsp+48h+pData]; pData
0x1800304dc  lea     r8, [rsp+48h+pType]; pType
0x1800304e1  mov     [rsp+48h+nSize], 4; nSize
0x1800304e9  lea     rdx, aDonotunloadplu; "DoNotUnloadPluginDLL"
0x1800304f0  call    cs:__imp_GetPrinterDataW
0x1800304f6  test    eax, eax
0x1800304f8  jnz     short loc_180030511
0x1800304fa  cmp     [rsp+48h+arg_8], 4
0x1800304ff  jnz     short loc_180030511
0x180030501  cmp     [rsp+48h+pData], eax
0x180030505  jmp     short loc_18003050B
0x180030507  test    byte ptr [rbx-80h], 10h
0x18003050b  jz      short loc_180030511
0x18003050d  or      dword ptr [rbx+30h], 10h
0x180030511  mov     rcx, rbx
0x180030514  call    ?VFreeSinglePluginEntry@@YAXPEAU_OEM_PLUGIN_ENTRY@@W4BPluginRequestType@@@Z; VFreeSinglePluginEntry(_OEM_PLUGIN_ENTRY *,BPluginRequestType)
0x180030519  add     rbx, 0B0h
0x180030520  test    esi, esi
0x180030522  jnz     loc_18003049A
0x180030528  mov     rcx, rdi
0x18003052b  add     rsp, 30h
0x18003052f  pop     rdi
0x180030530  pop     rsi
0x180030531  pop     rbx
0x180030532  jmp     cs:__imp_LocalFree
```
