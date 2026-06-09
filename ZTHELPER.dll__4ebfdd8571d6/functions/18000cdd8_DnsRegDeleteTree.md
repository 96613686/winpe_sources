# DnsRegDeleteTree

- ea: `0x18000cdd8`
- end: `0x18000ce59`
- name: `DnsRegDeleteTree`
- size: `129`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800048f0`
- `0x180007130`
- `0x180008a60`
- `0x180009554`
- `0x180009adc`

## callees

- `0x18000cdd8`
- `0x180015008`
- `0x180015ad8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000ce1c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000ce1c`

## pseudocode

```c
__int64 __fastcall DnsRegDeleteTree(HKEY hKey, LPCWSTR lpSubKey)
{
  unsigned int v4; // ebx
  LSTATUS v5; // eax

  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_qS(
      (_DWORD)hKey,
      44,
      (unsigned int)WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids,
      (_DWORD)hKey,
      (__int64)lpSubKey);
  if ( hKey )
  {
    v5 = RegDeleteTreeW(hKey, lpSubKey);
    v4 = 0;
    if ( v5 != 2 )
      v4 = v5;
  }
  else
  {
    v4 = 87;
  }
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 45, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18000cdd8  mov     [rsp+arg_0], rbx
0x18000cddd  push    rdi
0x18000cdde  sub     rsp, 30h
0x18000cde2  mov     rdi, rdx
0x18000cde5  mov     rbx, rcx
0x18000cde8  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000cdef  jz      short loc_18000CE0A
0x18000cdf1  mov     edx, 2Ch ; ','
0x18000cdf6  mov     [rsp+38h+var_18], rdi
0x18000cdfb  mov     r9, rcx
0x18000cdfe  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000ce05  call    WPP_SF_qS
0x18000ce0a  test    rbx, rbx
0x18000ce0d  jnz     short loc_18000CE16
0x18000ce0f  mov     ebx, 57h ; 'W'
0x18000ce14  jmp     short loc_18000CE2A
0x18000ce16  mov     rdx, rdi; lpSubKey
0x18000ce19  mov     rcx, rbx; hKey
0x18000ce1c  call    cs:__imp_RegDeleteTreeW
0x18000ce22  xor     ebx, ebx
0x18000ce24  cmp     eax, 2
0x18000ce27  cmovnz  ebx, eax
0x18000ce2a  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000ce31  jz      short loc_18000CE4C
0x18000ce33  mov     edx, 2Dh ; '-'
0x18000ce38  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18000ce3f  mov     ecx, 40Bh
0x18000ce44  mov     r9d, ebx
0x18000ce47  call    WPP_SF_d
0x18000ce4c  mov     eax, ebx
0x18000ce4e  mov     rbx, [rsp+38h+arg_0]
0x18000ce53  add     rsp, 30h
0x18000ce57  pop     rdi
0x18000ce58  retn
```
