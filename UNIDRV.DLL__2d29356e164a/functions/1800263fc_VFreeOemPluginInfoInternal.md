# VFreeOemPluginInfoInternal

- ea: `0x1800263fc`
- end: `0x1800264b5`
- name: `VFreeOemPluginInfoInternal`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180026234`
- `0x180027d9c`

## callees

- `0x1800263fc`
- `0x18003be38`

## import_xrefs

- `WINSPOOL!GetPrinterDataW` at `0x18002646c`
- `WINSPOOL!GetPrinterDataW` at `0x18002646c`
- `KERNEL32!LocalFree` at `0x1800264ae`

## string_xrefs

- `0x180026465`: `DoNotUnloadPluginDLL`

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
0x1800263fc  mov     [rsp+arg_8], edx
0x180026400  push    rbx
0x180026401  push    rsi
0x180026402  push    rdi
0x180026403  sub     rsp, 30h
0x180026407  mov     esi, [rcx+8]
0x18002640a  lea     rbx, [rcx+18h]
0x18002640e  mov     rdi, rcx
0x180026411  jmp     loc_18002649C
0x180026416  mov     eax, [rdi+8]
0x180026419  dec     esi
0x18002641b  mov     [rsp+48h+pType], 0
0x180026423  mov     [rsp+48h+arg_8], 0
0x18002642b  mov     [rsp+48h+pData], 0
0x180026433  test    eax, eax
0x180026435  jz      short loc_180026483
0x180026437  dec     eax
0x180026439  cmp     esi, eax
0x18002643b  jnz     short loc_180026483
0x18002643d  mov     rcx, [rdi]
0x180026440  test    rcx, rcx
0x180026443  jz      short loc_18002648D
0x180026445  mov     rcx, [rcx+18h]; hPrinter
0x180026449  lea     rax, [rsp+48h+arg_8]
0x18002644e  mov     [rsp+48h+pcbNeeded], rax; pcbNeeded
0x180026453  lea     r9, [rsp+48h+pData]; pData
0x180026458  lea     r8, [rsp+48h+pType]; pType
0x18002645d  mov     [rsp+48h+nSize], 4; nSize
0x180026465  lea     rdx, aDonotunloadplu; "DoNotUnloadPluginDLL"
0x18002646c  call    cs:__imp_GetPrinterDataW
0x180026472  test    eax, eax
0x180026474  jnz     short loc_18002648D
0x180026476  cmp     [rsp+48h+arg_8], 4
0x18002647b  jnz     short loc_18002648D
0x18002647d  cmp     [rsp+48h+pData], eax
0x180026481  jmp     short loc_180026487
0x180026483  test    byte ptr [rbx-80h], 10h
0x180026487  jz      short loc_18002648D
0x180026489  or      dword ptr [rbx+30h], 10h
0x18002648d  mov     rcx, rbx
0x180026490  call    ?VFreeSinglePluginEntry@@YAXPEAU_OEM_PLUGIN_ENTRY@@W4BPluginRequestType@@@Z; VFreeSinglePluginEntry(_OEM_PLUGIN_ENTRY *,BPluginRequestType)
0x180026495  add     rbx, 0B0h
0x18002649c  test    esi, esi
0x18002649e  jnz     loc_180026416
0x1800264a4  mov     rcx, rdi
0x1800264a7  add     rsp, 30h
0x1800264ab  pop     rdi
0x1800264ac  pop     rsi
0x1800264ad  pop     rbx
0x1800264ae  jmp     cs:__imp_LocalFree
```
