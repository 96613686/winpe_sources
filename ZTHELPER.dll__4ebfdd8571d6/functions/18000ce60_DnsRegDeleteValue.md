# DnsRegDeleteValue

- ea: `0x18000ce60`
- end: `0x18000cee1`
- name: `DnsRegDeleteValue`
- size: `129`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003f58`

## callees

- `0x18000ce60`
- `0x180015008`
- `0x180015ad8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000cea4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000cea4`

## pseudocode

```c
__int64 __fastcall DnsRegDeleteValue(HKEY hKey, LPCWSTR lpValueName)
{
  unsigned int v4; // ebx
  LSTATUS v5; // eax

  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_qS(
      (_DWORD)hKey,
      46,
      (unsigned int)WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids,
      (_DWORD)hKey,
      (__int64)lpValueName);
  if ( hKey )
  {
    v5 = RegDeleteValueW(hKey, lpValueName);
    v4 = 0;
    if ( v5 != 2 )
      v4 = v5;
  }
  else
  {
    v4 = 87;
  }
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 47, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18000ce60  mov     [rsp+arg_0], rbx
0x18000ce65  push    rdi
0x18000ce66  sub     rsp, 30h
0x18000ce6a  mov     rdi, rdx
0x18000ce6d  mov     rbx, rcx
0x18000ce70  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000ce77  jz      short loc_18000CE92
0x18000ce79  mov     edx, 2Eh ; '.'
0x18000ce7e  mov     [rsp+38h+var_18], rdi
0x18000ce83  mov     r9, rcx
0x18000ce86  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000ce8d  call    WPP_SF_qS
0x18000ce92  test    rbx, rbx
0x18000ce95  jnz     short loc_18000CE9E
0x18000ce97  mov     ebx, 57h ; 'W'
0x18000ce9c  jmp     short loc_18000CEB2
0x18000ce9e  mov     rdx, rdi; lpValueName
0x18000cea1  mov     rcx, rbx; hKey
0x18000cea4  call    cs:__imp_RegDeleteValueW
0x18000ceaa  xor     ebx, ebx
0x18000ceac  cmp     eax, 2
0x18000ceaf  cmovnz  ebx, eax
0x18000ceb2  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000ceb9  jz      short loc_18000CED4
0x18000cebb  mov     edx, 2Fh ; '/'
0x18000cec0  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000cec7  mov     ecx, 40Bh
0x18000cecc  mov     r9d, ebx
0x18000cecf  call    WPP_SF_d
0x18000ced4  mov     eax, ebx
0x18000ced6  mov     rbx, [rsp+38h+arg_0]
0x18000cedb  add     rsp, 30h
0x18000cedf  pop     rdi
0x18000cee0  retn
```
