# HrRegDeleteValueW

- ea: `0x18000b9e0`
- end: `0x18000ba51`
- name: `HrRegDeleteValueW`
- size: `113`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000b9e0`
- `0x18000bba0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000ba3e`
- `ADVAPI32!RegCloseKey` at `0x18000ba3e`
- `ADVAPI32!RegDeleteValueW` at `0x18000ba24`
- `ADVAPI32!RegDeleteValueW` at `0x18000ba24`

## pseudocode

```c
__int64 __fastcall HrRegDeleteValueW(int a1, __int64 a2, const WCHAR *a3)
{
  HKEY v5; // rcx
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v5 = 0;
  hKey = 0;
  if ( a2 )
  {
    v6 = HrRegOpenKeyExW(a1, a2, 0, 131078, &hKey);
    if ( (v6 & 0x80000000) != 0 )
      return v6;
    v5 = hKey;
  }
  v7 = RegDeleteValueW(v5, a3);
  v6 = v7;
  if ( v7 > 0 )
    v6 = (unsigned __int16)v7 | 0x80070000;
  RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18000b9e0  mov     r11, rsp
0x18000b9e3  mov     [r11+8], rbx
0x18000b9e7  push    rdi
0x18000b9e8  sub     rsp, 30h
0x18000b9ec  mov     rax, rcx
0x18000b9ef  mov     rdi, r8
0x18000b9f2  xor     ecx, ecx
0x18000b9f4  mov     [r11+10h], rcx
0x18000b9f8  test    rdx, rdx
0x18000b9fb  jz      short loc_18000BA21
0x18000b9fd  lea     rcx, [r11+10h]
0x18000ba01  mov     r9d, 20006h; int
0x18000ba07  mov     [r11-18h], rcx
0x18000ba0b  xor     r8d, r8d; int
0x18000ba0e  mov     rcx, rax; int
0x18000ba11  call    HrRegOpenKeyExW
0x18000ba16  mov     ebx, eax
0x18000ba18  test    eax, eax
0x18000ba1a  js      short loc_18000BA44
0x18000ba1c  mov     rcx, [rsp+38h+hKey]; hKey
0x18000ba21  mov     rdx, rdi; lpValueName
0x18000ba24  call    cs:__imp_RegDeleteValueW
0x18000ba2a  mov     ebx, eax
0x18000ba2c  test    eax, eax
0x18000ba2e  jle     short loc_18000BA39
0x18000ba30  movzx   ebx, ax
0x18000ba33  or      ebx, 80070000h
0x18000ba39  mov     rcx, [rsp+38h+hKey]; hKey
0x18000ba3e  call    cs:__imp_RegCloseKey
0x18000ba44  mov     eax, ebx
0x18000ba46  mov     rbx, [rsp+38h+arg_0]
0x18000ba4b  add     rsp, 30h
0x18000ba4f  pop     rdi
0x18000ba50  retn
```
