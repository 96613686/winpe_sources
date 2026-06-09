# RegistryFunctions::RegDeleteKeyValueW(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180016330`
- end: `0x1800163ac`
- name: `?RegDeleteKeyValueW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBG1@Z`
- size: `124`
- prototype: `int(RegistryFunctions *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180016330`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001637e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001637e`

## pseudocode

```c
__int64 __fastcall RegistryFunctions::RegDeleteKeyValueW(
        RegistryFunctions *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v4; // rax
  unsigned int v7; // ebx
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  v4 = *(_QWORD *)this;
  hKey = 0;
  v7 = (*(__int64 (__fastcall **)(RegistryFunctions *, HKEY, const unsigned __int16 *, _QWORD, int, HKEY *))(v4 + 80))(
         this,
         a2,
         a3,
         0,
         2,
         &hKey);
  if ( !v7 )
  {
    v7 = RegDeleteValueW(hKey, a4);
    (*(void (__fastcall **)(RegistryFunctions *, HKEY))(*(_QWORD *)this + 8LL))(this, hKey);
  }
  return v7;
}

```

## disassembly

```asm
0x180016330  mov     r11, rsp
0x180016333  mov     [r11+10h], rbx
0x180016337  mov     [r11+18h], rsi
0x18001633b  push    rdi
0x18001633c  sub     rsp, 40h
0x180016340  mov     rax, [rcx]
0x180016343  mov     rdi, rcx
0x180016346  lea     rcx, [r11+8]
0x18001634a  mov     qword ptr [r11+8], 0
0x180016352  mov     [r11-20h], rcx
0x180016356  mov     rsi, r9
0x180016359  xor     r9d, r9d
0x18001635c  mov     [rsp+48h+var_28], 2
0x180016364  mov     rax, [rax+50h]
0x180016368  mov     rcx, rdi
0x18001636b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016370  mov     ebx, eax
0x180016372  test    eax, eax
0x180016374  jnz     short loc_18001639A
0x180016376  mov     rcx, [rsp+48h+hKey]; hKey
0x18001637b  mov     rdx, rsi; lpValueName
0x18001637e  call    cs:__imp_RegDeleteValueW
0x180016384  mov     rdx, [rsp+48h+hKey]
0x180016389  mov     rcx, rdi
0x18001638c  mov     ebx, eax
0x18001638e  mov     rax, [rdi]
0x180016391  mov     rax, [rax+8]
0x180016395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001639a  mov     rsi, [rsp+48h+arg_10]
0x18001639f  mov     eax, ebx
0x1800163a1  mov     rbx, [rsp+48h+arg_8]
0x1800163a6  add     rsp, 40h
0x1800163aa  pop     rdi
0x1800163ab  retn
```
