# ZtRegWriteBool

- ea: `0x180003cb8`
- end: `0x180003d82`
- name: `ZtRegWriteBool`
- size: `202`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003f58`

## callees

- `0x180003cb8`
- `0x180015008`
- `0x1800152f8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003d0f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180003d0f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003d46`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003d46`

## pseudocode

```c
__int64 __fastcall ZtRegWriteBool(HKEY hKey, LPCWSTR lpValueName, int a3)
{
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  int Data; // [rsp+40h] [rbp+8h] BYREF

  Data = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qSd((_DWORD)hKey, (_DWORD)lpValueName, a3, (_DWORD)hKey, (__int64)lpValueName, 0);
  if ( hKey && lpValueName )
  {
    if ( a3 )
    {
      Data = 1;
      v6 = RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
    }
    else
    {
      v7 = RegDeleteValueW(hKey, lpValueName);
      v6 = 0;
      if ( v7 != 2 )
        v6 = v7;
    }
  }
  else
  {
    v6 = 87;
  }
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0xDu, (ULONGLONG)WPP_3241f1bf244939c0c0359531c6639c66_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180003cb8  mov     rax, rsp
0x180003cbb  mov     [rax+10h], rbx
0x180003cbf  mov     [rax+18h], rsi
0x180003cc3  push    rdi
0x180003cc4  sub     rsp, 30h
0x180003cc8  mov     esi, r8d
0x180003ccb  mov     dword ptr [rax+8], 0
0x180003cd2  mov     rbx, rdx
0x180003cd5  mov     rdi, rcx
0x180003cd8  test    byte ptr cs:xmmword_18001F260, 4
0x180003cdf  jz      short loc_180003CF4
0x180003ce1  mov     dword ptr [rax-10h], 0
0x180003ce8  mov     r9, rcx
0x180003ceb  mov     [rax-18h], rdx
0x180003cef  call    WPP_SF_qSd
0x180003cf4  test    rdi, rdi
0x180003cf7  jnz     short loc_180003D00
0x180003cf9  mov     ebx, 57h ; 'W'
0x180003cfe  jmp     short loc_180003D4E
0x180003d00  test    rbx, rbx
0x180003d03  jz      short loc_180003CF9
0x180003d05  mov     rdx, rbx; lpValueName
0x180003d08  mov     rcx, rdi; hKey
0x180003d0b  test    esi, esi
0x180003d0d  jnz     short loc_180003D23
0x180003d0f  call    cs:__imp_RegDeleteValueW
0x180003d15  xor     ebx, ebx
0x180003d17  cmp     eax, 2
0x180003d1a  cmovnz  ebx, eax
0x180003d1d  test    ebx, ebx
0x180003d1f  jnz     short loc_180003D4E
0x180003d21  jmp     short loc_180003D4E
0x180003d23  lea     rax, [rsp+38h+Data]
0x180003d28  mov     [rsp+38h+cbData], 4; cbData
0x180003d30  mov     r9d, 4; dwType
0x180003d36  mov     [rsp+38h+lpData], rax; lpData
0x180003d3b  xor     r8d, r8d; Reserved
0x180003d3e  mov     [rsp+38h+Data], 1
0x180003d46  call    cs:__imp_RegSetValueExW
0x180003d4c  mov     ebx, eax
0x180003d4e  test    byte ptr cs:xmmword_18001F260, 4
0x180003d55  jz      short loc_180003D70
0x180003d57  mov     edx, 0Dh
0x180003d5c  lea     r8, WPP_3241f1bf244939c0c0359531c6639c66_Traceguids
0x180003d63  mov     ecx, 402h
0x180003d68  mov     r9d, ebx
0x180003d6b  call    WPP_SF_d
0x180003d70  mov     rsi, [rsp+38h+arg_10]
0x180003d75  mov     eax, ebx
0x180003d77  mov     rbx, [rsp+38h+arg_8]
0x180003d7c  add     rsp, 30h
0x180003d80  pop     rdi
0x180003d81  retn
```
