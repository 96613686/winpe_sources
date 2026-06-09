# VFreeSinglePluginEntry(_OEM_PLUGIN_ENTRY *,BPluginRequestType)

- ea: `0x18003be38`
- end: `0x18003bf00`
- name: `?VFreeSinglePluginEntry@@YAXPEAU_OEM_PLUGIN_ENTRY@@W4BPluginRequestType@@@Z`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800263fc`
- `0x18003664c`

## callees

- `0x18003be38`
- `0x18003bf08`
- `0x180075010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18003beb5`
- `KERNEL32!LocalFree` at `0x18003bec4`
- `KERNEL32!LocalFree` at `0x18003bed3`
- `KERNEL32!LocalFree` at `0x18003beb5`
- `KERNEL32!LocalFree` at `0x18003bec4`
- `KERNEL32!LocalFree` at `0x18003bed3`
- `KERNEL32!FreeLibrary` at `0x18003be9f`
- `KERNEL32!FreeLibrary` at `0x18003be9f`
- `KERNEL32!GetProcAddress` at `0x18003be7e`
- `KERNEL32!GetProcAddress` at `0x18003be7e`

## string_xrefs

- `0x18003be74`: `DllCanUnloadNow`

## pseudocode

```c
void __fastcall VFreeSinglePluginEntry(__int64 a1)
{
  HMODULE v2; // rcx
  int v3; // esi
  HMODULE v4; // rdi
  void (*ProcAddress)(void); // rax
  void *v6; // rcx
  void *v7; // rcx

  v2 = *(HMODULE *)(a1 + 32);
  if ( v2 )
  {
    if ( *(_QWORD *)(a1 + 72) )
    {
      ReleaseOemInterface(a1);
      v3 = *(_DWORD *)(a1 + 48);
      if ( (v3 & 0x10) != 0 )
        goto LABEL_11;
      v4 = *(HMODULE *)(a1 + 32);
      if ( !v4 )
        goto LABEL_11;
      ProcAddress = (void (*)(void))GetProcAddress(*(HMODULE *)(a1 + 32), "DllCanUnloadNow");
      if ( !ProcAddress )
        goto LABEL_11;
      if ( (v3 & 0x40) == 0 )
        ProcAddress();
      v2 = v4;
    }
    else if ( (*(_BYTE *)(a1 + 48) & 0x10) != 0 )
    {
LABEL_11:
      *(_QWORD *)(a1 + 32) = 0;
      goto LABEL_12;
    }
    FreeLibrary(v2);
    goto LABEL_11;
  }
LABEL_12:
  if ( *(_QWORD *)a1 )
    LocalFree(*(HLOCAL *)a1);
  v6 = *(void **)(a1 + 8);
  if ( v6 )
    LocalFree(v6);
  v7 = *(void **)(a1 + 16);
  if ( v7 )
    LocalFree(v7);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
}

```

## disassembly

```asm
0x18003be38  mov     [rsp+arg_0], rbx
0x18003be3d  mov     [rsp+arg_8], rsi
0x18003be42  push    rdi
0x18003be43  sub     rsp, 20h
0x18003be47  mov     rbx, rcx
0x18003be4a  mov     rcx, [rcx+20h]; hLibModule
0x18003be4e  test    rcx, rcx
0x18003be51  jz      short loc_18003BEAD
0x18003be53  cmp     qword ptr [rbx+48h], 0
0x18003be58  jz      short loc_18003BE99
0x18003be5a  mov     rcx, rbx
0x18003be5d  call    ReleaseOemInterface
0x18003be62  mov     esi, [rbx+30h]
0x18003be65  test    sil, 10h
0x18003be69  jnz     short loc_18003BEA5
0x18003be6b  mov     rdi, [rbx+20h]
0x18003be6f  test    rdi, rdi
0x18003be72  jz      short loc_18003BEA5
0x18003be74  lea     rdx, aDllcanunloadno; "DllCanUnloadNow"
0x18003be7b  mov     rcx, rdi; hModule
0x18003be7e  call    cs:__imp_GetProcAddress
0x18003be84  test    rax, rax
0x18003be87  jz      short loc_18003BEA5
0x18003be89  test    sil, 40h
0x18003be8d  jnz     short loc_18003BE94
0x18003be8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be94  mov     rcx, rdi
0x18003be97  jmp     short loc_18003BE9F
0x18003be99  test    byte ptr [rbx+30h], 10h
0x18003be9d  jnz     short loc_18003BEA5
0x18003be9f  call    cs:__imp_FreeLibrary
0x18003bea5  mov     qword ptr [rbx+20h], 0
0x18003bead  mov     rcx, [rbx]; hMem
0x18003beb0  test    rcx, rcx
0x18003beb3  jz      short loc_18003BEBB
0x18003beb5  call    cs:__imp_LocalFree
0x18003bebb  mov     rcx, [rbx+8]; hMem
0x18003bebf  test    rcx, rcx
0x18003bec2  jz      short loc_18003BECA
0x18003bec4  call    cs:__imp_LocalFree
0x18003beca  mov     rcx, [rbx+10h]; hMem
0x18003bece  test    rcx, rcx
0x18003bed1  jz      short loc_18003BED9
0x18003bed3  call    cs:__imp_LocalFree
0x18003bed9  mov     rsi, [rsp+28h+arg_8]
0x18003bede  mov     qword ptr [rbx], 0
0x18003bee5  mov     qword ptr [rbx+8], 0
0x18003beed  mov     qword ptr [rbx+10h], 0
0x18003bef5  mov     rbx, [rsp+28h+arg_0]
0x18003befa  add     rsp, 20h
0x18003befe  pop     rdi
0x18003beff  retn
```
