# ReadStringValue(HKEY__ *,ushort const *,ushort * *)

- ea: `0x140007d00`
- end: `0x140007dac`
- name: `?ReadStringValue@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z`
- size: `172`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, BYTE **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140003330`
- `0x14000414c`

## callees

- `0x140007d00`
- `0x140008d30`
- `0x140008ef4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140007d62`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140007d62`

## pseudocode

```c
__int64 __fastcall ReadStringValue(HKEY hKey, LPCWSTR lpValueName, BYTE **a3)
{
  BYTE *lpData; // rbx
  LSTATUS v7; // eax
  unsigned int v8; // edi
  DWORD Type[10]; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+20h] BYREF

  Type[0] = 0;
  cbData = 512;
  lpData = 0;
  do
  {
    AiFree(lpData);
    lpData = (BYTE *)AiAlloc(cbData);
    if ( !lpData )
    {
      v8 = 8;
      goto LABEL_9;
    }
    v7 = RegQueryValueExW(hKey, lpValueName, 0, Type, lpData, &cbData);
    v8 = v7;
  }
  while ( v7 == 234 );
  if ( !v7 )
  {
    if ( Type[0] == 1 )
    {
      *a3 = lpData;
      lpData = 0;
    }
    else
    {
      v8 = 1804;
    }
  }
LABEL_9:
  AiFree(lpData);
  return v8;
}

```

## disassembly

```asm
0x140007d00  mov     rax, rsp
0x140007d03  mov     [rax+8], rbx
0x140007d07  mov     [rax+10h], rbp
0x140007d0b  push    rsi
0x140007d0c  push    rdi
0x140007d0d  push    r14
0x140007d0f  sub     rsp, 40h
0x140007d13  mov     rsi, r8
0x140007d16  mov     dword ptr [rax-28h], 0
0x140007d1d  mov     rbp, rdx
0x140007d20  mov     dword ptr [rax+20h], 200h
0x140007d27  mov     r14, rcx
0x140007d2a  xor     ebx, ebx
0x140007d2c  mov     rcx, rbx
0x140007d2f  call    AiFree
0x140007d34  mov     ecx, [rsp+58h+cbData]
0x140007d38  call    AiAlloc
0x140007d3d  mov     rbx, rax
0x140007d40  test    rax, rax
0x140007d43  jz      short loc_140007D8A
0x140007d45  lea     rax, [rsp+58h+cbData]
0x140007d4a  xor     r8d, r8d; lpReserved
0x140007d4d  mov     [rsp+58h+lpcbData], rax; lpcbData
0x140007d52  lea     r9, [rsp+58h+Type]; lpType
0x140007d57  mov     rdx, rbp; lpValueName
0x140007d5a  mov     [rsp+58h+lpData], rbx; lpData
0x140007d5f  mov     rcx, r14; hKey
0x140007d62  call    cs:__imp_RegQueryValueExW
0x140007d68  mov     edi, eax
0x140007d6a  cmp     eax, 0EAh
0x140007d6f  jz      short loc_140007D2C
0x140007d71  test    eax, eax
0x140007d73  jnz     short loc_140007D8F
0x140007d75  cmp     [rsp+58h+Type], 1
0x140007d7a  jz      short loc_140007D83
0x140007d7c  mov     edi, 70Ch
0x140007d81  jmp     short loc_140007D8F
0x140007d83  mov     [rsi], rbx
0x140007d86  xor     ebx, ebx
0x140007d88  jmp     short loc_140007D8F
0x140007d8a  mov     edi, 8
0x140007d8f  mov     rcx, rbx
0x140007d92  call    AiFree
0x140007d97  mov     rbx, [rsp+58h+arg_0]
0x140007d9c  mov     eax, edi
0x140007d9e  mov     rbp, [rsp+58h+arg_8]
0x140007da3  add     rsp, 40h
0x140007da7  pop     r14
0x140007da9  pop     rdi
0x140007daa  pop     rsi
0x140007dab  retn
```
