# RegistryFunctions::RegDeleteKeyValueW(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180008520`
- end: `0x18000859c`
- name: `?RegDeleteKeyValueW@RegistryFunctions@@UEAAJPEAUHKEY__@@PEBG1@Z`
- size: `124`
- prototype: `__int64 __fastcall(RegistryFunctions *this, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180008520`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000856e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000856e`

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
0x180008520  mov     r11, rsp
0x180008523  mov     [r11+10h], rbx
0x180008527  mov     [r11+18h], rsi
0x18000852b  push    rdi
0x18000852c  sub     rsp, 40h
0x180008530  mov     rax, [rcx]
0x180008533  mov     rdi, rcx
0x180008536  lea     rcx, [r11+8]
0x18000853a  mov     qword ptr [r11+8], 0
0x180008542  mov     [r11-20h], rcx
0x180008546  mov     rsi, r9
0x180008549  xor     r9d, r9d
0x18000854c  mov     [rsp+48h+var_28], 2
0x180008554  mov     rax, [rax+50h]
0x180008558  mov     rcx, rdi
0x18000855b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008560  mov     ebx, eax
0x180008562  test    eax, eax
0x180008564  jnz     short loc_18000858A
0x180008566  mov     rcx, [rsp+48h+hKey]; hKey
0x18000856b  mov     rdx, rsi; lpValueName
0x18000856e  call    cs:__imp_RegDeleteValueW
0x180008574  mov     rdx, [rsp+48h+hKey]
0x180008579  mov     rcx, rdi
0x18000857c  mov     ebx, eax
0x18000857e  mov     rax, [rdi]
0x180008581  mov     rax, [rax+8]
0x180008585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000858a  mov     rsi, [rsp+48h+arg_10]
0x18000858f  mov     eax, ebx
0x180008591  mov     rbx, [rsp+48h+arg_8]
0x180008596  add     rsp, 40h
0x18000859a  pop     rdi
0x18000859b  retn
```
