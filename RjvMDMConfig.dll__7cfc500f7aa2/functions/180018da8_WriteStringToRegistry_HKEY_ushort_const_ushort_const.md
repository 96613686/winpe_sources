# WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)

- ea: `0x180018da8`
- end: `0x180018e53`
- name: `?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `171`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180019f60`

## callees

- `0x180006574`
- `0x18000feb4`
- `0x180018da8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018e21`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180018e21`

## pseudocode

```c
__int64 __fastcall WriteStringToRegistry(HKEY hKey, LPCWSTR lpValueName, const unsigned __int16 *a3)
{
  int v7; // ebx
  unsigned __int64 v8; // rcx
  LSTATUS v9; // eax
  unsigned __int64 cbData; // [rsp+70h] [rbp+18h] BYREF

  cbData = 0;
  if ( !a3 )
    return 0;
  v7 = StringCbLengthW(a3, (unsigned __int64)lpValueName, &cbData);
  if ( v7 >= 0 )
  {
    v8 = cbData + 2;
    if ( cbData + 2 < cbData )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      LODWORD(cbData) = 0;
      v7 = ULongLongToULong(v8, (unsigned int *)&cbData);
      if ( v7 >= 0 )
      {
        v9 = RegSetValueExW(hKey, lpValueName, 0, 1u, (const BYTE *)a3, cbData);
        if ( v9 )
        {
          if ( v9 > 0 )
            return (unsigned __int16)v9 | 0x80070000;
          else
            return (unsigned int)v9;
        }
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180018da8  push    rbx
0x180018daa  push    rbp
0x180018dab  push    rsi
0x180018dac  push    rdi
0x180018dad  sub     rsp, 38h
0x180018db1  mov     [rsp+58h+arg_10], 0
0x180018dba  mov     rdi, r8
0x180018dbd  mov     rsi, rdx
0x180018dc0  mov     rbp, rcx
0x180018dc3  test    r8, r8
0x180018dc6  jnz     short loc_180018DCC
0x180018dc8  xor     eax, eax
0x180018dca  jmp     short loc_180018E49
0x180018dcc  lea     r8, [rsp+58h+arg_10]; unsigned __int64 *
0x180018dd1  mov     rcx, rdi; unsigned __int16 *
0x180018dd4  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180018dd9  mov     ebx, eax
0x180018ddb  test    eax, eax
0x180018ddd  js      short loc_180018E47
0x180018ddf  mov     rax, [rsp+58h+arg_10]
0x180018de4  lea     rcx, [rax+2]; unsigned __int64
0x180018de8  cmp     rcx, rax
0x180018deb  jb      short loc_180018E42
0x180018ded  lea     rdx, [rsp+58h+arg_10]; unsigned int *
0x180018df2  mov     dword ptr [rsp+58h+arg_10], 0
0x180018dfa  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180018dff  mov     ebx, eax
0x180018e01  test    eax, eax
0x180018e03  js      short loc_180018E47
0x180018e05  mov     eax, dword ptr [rsp+58h+arg_10]
0x180018e09  mov     r9d, 1; dwType
0x180018e0f  mov     [rsp+58h+cbData], eax; cbData
0x180018e13  xor     r8d, r8d; Reserved
0x180018e16  mov     rdx, rsi; lpValueName
0x180018e19  mov     [rsp+58h+lpData], rdi; lpData
0x180018e1e  mov     rcx, rbp; hKey
0x180018e21  call    cs:__imp_RegSetValueExW
0x180018e28  nop     dword ptr [rax+rax+00h]
0x180018e2d  test    eax, eax
0x180018e2f  jz      short loc_180018E47
0x180018e31  jg      short loc_180018E37
0x180018e33  mov     ebx, eax
0x180018e35  jmp     short loc_180018E47
0x180018e37  movzx   ebx, ax
0x180018e3a  or      ebx, 80070000h
0x180018e40  jmp     short loc_180018E47
0x180018e42  mov     ebx, 80070216h
0x180018e47  mov     eax, ebx
0x180018e49  add     rsp, 38h
0x180018e4d  pop     rdi
0x180018e4e  pop     rsi
0x180018e4f  pop     rbp
0x180018e50  pop     rbx
0x180018e51  retn
```
