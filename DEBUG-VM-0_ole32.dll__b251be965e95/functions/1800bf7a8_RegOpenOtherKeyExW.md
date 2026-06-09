# RegOpenOtherKeyExW

- ea: `0x1800bf7a8`
- end: `0x1800bf932`
- name: `RegOpenOtherKeyExW`
- size: `394`
- prototype: `int __fastcall(HKEY__ *hKey, const wchar_t *lpSubKey, unsigned int samDesired, unsigned int phkResult, HKEY__ **hKey, unsigned __int16 *lpSubKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180036488`

## callees

- `0x180052390`
- `0x180052a30`
- `0x1800bf7a8`

## import_xrefs

- `ntdll!NtQuerySystemInformationEx` at `0x1800bf829`
- `ntdll!NtQuerySystemInformationEx` at `0x1800bf882`
- `ntdll!NtQuerySystemInformationEx` at `0x1800bf829`
- `ntdll!NtQuerySystemInformationEx` at `0x1800bf882`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x1800bf8b0`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x1800bf8dc`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x1800bf8b0`
- `api-ms-win-core-wow64-l1-1-1!Wow64SetThreadDefaultGuestMachine` at `0x1800bf8dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bf8d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bf90b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bf8d1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bf90b`

## pseudocode

```c
__int64 __fastcall RegOpenOtherKeyExW(
        HKEY hKey,
        const wchar_t *lpSubKey,
        unsigned int samDesired,
        REGSAM phkResult,
        HKEY__ **phkResulta)
{
  int v5; // esi
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  unsigned int *p_ReturnLength; // rbx
  char v14; // r15
  unsigned int v15; // edi
  unsigned int v16; // ecx
  unsigned __int16 v17; // bx
  unsigned int ReturnLength; // [rsp+30h] [rbp+0h] BYREF
  void *Process; // [rsp+38h] [rbp+8h] BYREF
  unsigned int *v21; // [rsp+40h] [rbp+10h]

  v5 = 0;
  ReturnLength = 0;
  Process = 0;
  if ( (phkResult & 0x300) != 0x200
    || NtCurrentTeb()->WowTebOffset < 0
    || (unsigned int)NtQuerySystemInformationEx(230, &Process, 8, 0, 0, &ReturnLength) != -1073741789 )
  {
    return (unsigned int)RegOpenKeyExW(hKey, lpSubKey, 0, phkResult, phkResulta);
  }
  v9 = ReturnLength + 15LL;
  if ( v9 <= ReturnLength )
    v9 = 0xFFFFFFFFFFFFFF0LL;
  v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
  v11 = alloca(v10);
  v12 = alloca(v10);
  p_ReturnLength = &ReturnLength;
  v21 = &ReturnLength;
  if ( (int)NtQuerySystemInformationEx(230, &Process, 8, &ReturnLength, ReturnLength, &ReturnLength) < 0 )
    return (unsigned int)RegOpenKeyExW(hKey, lpSubKey, 0, phkResult, phkResulta);
  v14 = 0;
  v15 = 0;
  while ( 1 )
  {
    v16 = p_ReturnLength[v5];
    if ( !(_WORD)v16 )
      break;
    if ( (v16 & 0x160000) == 0x120000 )
    {
      v14 = 1;
      v17 = Wow64SetThreadDefaultGuestMachine(LOWORD(p_ReturnLength[v5]));
      v15 = RegOpenKeyExW(hKey, lpSubKey, 0, phkResult, phkResulta);
      Wow64SetThreadDefaultGuestMachine(v17);
      if ( !v15 )
        return v15;
      p_ReturnLength = v21;
    }
    ++v5;
  }
  if ( !v14 )
    return (unsigned int)RegOpenKeyExW(hKey, lpSubKey, 0, phkResult, phkResulta);
  return v15;
}

```

## disassembly

```asm
0x1800bf7a8  push    rbp
0x1800bf7aa  push    rbx
0x1800bf7ab  push    rsi
0x1800bf7ac  push    rdi
0x1800bf7ad  push    r12
0x1800bf7af  push    r13
0x1800bf7b1  push    r14
0x1800bf7b3  push    r15
0x1800bf7b5  sub     rsp, 58h
0x1800bf7b9  lea     rbp, [rsp+30h]
0x1800bf7be  mov     rax, cs:__security_cookie
0x1800bf7c5  xor     rax, rbp
0x1800bf7c8  mov     [rbp+60h+var_48], rax
0x1800bf7cc  xor     esi, esi
0x1800bf7ce  mov     eax, samDesired
0x1800bf7d1  and     eax, 300h
0x1800bf7d6  mov     [rbp+60h+ReturnLength], esi
0x1800bf7d9  mov     [rbp+60h+Process], rsi
0x1800bf7dd  mov     r14d, samDesired
0x1800bf7e0  mov     r12, lpSubKey
0x1800bf7e3  mov     r13, hKey
0x1800bf7e6  cmp     eax, 200h
0x1800bf7eb  jnz     loc_1800BF8F3
0x1800bf7f1  mov     rax, gs:30h
0x1800bf7fa  cmp     [rax+180Ch], esi
0x1800bf800  jl      loc_1800BF8F3
0x1800bf806  lea     rax, [rbp+60h+ReturnLength]
0x1800bf80a  mov     r15d, 0E6h
0x1800bf810  mov     [rsp+90h+var_68], rax
0x1800bf815  lea     edi, [rsi+8]
0x1800bf818  mov     r8d, edi
0x1800bf81b  mov     dword ptr [rsp+90h+var_70], esi
0x1800bf81f  mov     ecx, r15d
0x1800bf822  lea     lpSubKey, [rbp+60h+Process]
0x1800bf826  xor     samDesired, samDesired
0x1800bf829  call    cs:__imp_NtQuerySystemInformationEx
0x1800bf82f  cmp     eax, 0C0000023h
0x1800bf834  jnz     loc_1800BF8F3
0x1800bf83a  mov     edx, [rbp+60h+ReturnLength]
0x1800bf83d  lea     hKey, [lpSubKey+0Fh]
0x1800bf841  cmp     hKey, lpSubKey
0x1800bf844  ja      short loc_1800BF850
0x1800bf846  mov     hKey, 0FFFFFFFFFFFFFF0h
0x1800bf850  and     hKey, 0FFFFFFFFFFFFFFF0h
0x1800bf854  mov     rax, hKey
0x1800bf857  call    _alloca_probe
0x1800bf85c  sub     rsp, hKey
0x1800bf85f  lea     rax, [rbp+60h+ReturnLength]
0x1800bf863  mov     r8d, edi
0x1800bf866  mov     ecx, r15d
0x1800bf869  lea     rbx, [rsp+90h+ReturnLength]
0x1800bf86e  mov     [rsp+90h+var_68], rax
0x1800bf873  mov     dword ptr [rsp+90h+var_70], edx
0x1800bf877  mov     r9, rbx
0x1800bf87a  lea     lpSubKey, [rbp+60h+Process]
0x1800bf87e  mov     [rbp+60h+var_50], rbx
0x1800bf882  call    cs:__imp_NtQuerySystemInformationEx
0x1800bf888  test    eax, eax
0x1800bf88a  js      short loc_1800BF8F3
0x1800bf88c  mov     r15b, sil
0x1800bf88f  mov     edi, esi
0x1800bf891  mov     edx, esi
0x1800bf893  mov     ecx, [rbx+lpSubKey*4]
0x1800bf896  test    cx, cx
0x1800bf899  jz      short loc_1800BF8EE
0x1800bf89b  and     ecx, 160000h
0x1800bf8a1  cmp     ecx, 120000h
0x1800bf8a7  jnz     short loc_1800BF8EA
0x1800bf8a9  movzx   ecx, word ptr [rbx+lpSubKey*4]
0x1800bf8ad  mov     r15b, 1
0x1800bf8b0  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x1800bf8b6  mov     samDesired, r14d; samDesired
0x1800bf8b9  xor     r8d, r8d; ulOptions
0x1800bf8bc  movzx   ebx, ax
0x1800bf8bf  mov     lpSubKey, r12; lpSubKey
0x1800bf8c2  mov     rax, [rbp+60h+phkResult]
0x1800bf8c9  mov     hKey, r13; hKey
0x1800bf8cc  mov     [rsp+90h+var_70], rax; phkResult
0x1800bf8d1  call    cs:__imp_RegOpenKeyExW
0x1800bf8d7  movzx   ecx, bx
0x1800bf8da  mov     edi, eax
0x1800bf8dc  call    cs:__imp_Wow64SetThreadDefaultGuestMachine
0x1800bf8e2  test    edi, edi
0x1800bf8e4  jz      short loc_1800BF913
0x1800bf8e6  mov     rbx, [rbp+60h+var_50]
0x1800bf8ea  inc     esi
0x1800bf8ec  jmp     short loc_1800BF891
0x1800bf8ee  test    r15b, r15b
0x1800bf8f1  jnz     short loc_1800BF913
0x1800bf8f3  mov     rax, [rbp+60h+phkResult]
0x1800bf8fa  mov     samDesired, r14d; samDesired
0x1800bf8fd  xor     r8d, r8d; ulOptions
0x1800bf900  mov     [rsp+90h+var_70], rax; phkResult
0x1800bf905  mov     lpSubKey, r12; lpSubKey
0x1800bf908  mov     hKey, r13; hKey
0x1800bf90b  call    cs:__imp_RegOpenKeyExW
0x1800bf911  mov     edi, eax
0x1800bf913  mov     eax, edi
0x1800bf915  mov     hKey, [rbp+60h+var_48]
0x1800bf919  xor     hKey, rbp; StackCookie
0x1800bf91c  call    __security_check_cookie
0x1800bf921  lea     rsp, [rbp+28h]
0x1800bf925  pop     r15
0x1800bf927  pop     r14
0x1800bf929  pop     r13
0x1800bf92b  pop     r12
0x1800bf92d  pop     rdi
0x1800bf92e  pop     rsi
0x1800bf92f  pop     rbx
0x1800bf930  pop     rbp
0x1800bf931  retn
```
