# SetRegistryString

- ea: `0x18000f78c`
- end: `0x18000f843`
- name: `SetRegistryString`
- size: `183`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008190`
- `0x180008360`

## callees

- `0x18000f78c`
- `0x18000f84c`
- `0x180015008`
- `0x1800161ac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f800`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f800`

## pseudocode

```c
__int64 __fastcall SetRegistryString(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData)
{
  unsigned int v6; // ebx
  size_t pcbLength; // [rsp+40h] [rbp+8h] BYREF

  pcbLength = 0;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_qSS((_DWORD)hKey, (_DWORD)lpValueName, (_DWORD)lpData, (_DWORD)hKey, (__int64)lpValueName, (__int64)lpData);
  if ( hKey && lpData && StringCbLengthW((STRSAFE_PCNZWCH)lpData, (size_t)lpValueName, &pcbLength) >= 0 )
    v6 = RegSetValueExW(hKey, lpValueName, 0, 1u, lpData, pcbLength + 2);
  else
    v6 = 87;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 18, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000f78c  mov     rax, rsp
0x18000f78f  mov     [rax+10h], rbx
0x18000f793  mov     [rax+18h], rsi
0x18000f797  push    rdi
0x18000f798  sub     rsp, 30h
0x18000f79c  mov     rbx, r8
0x18000f79f  mov     qword ptr [rax+8], 0
0x18000f7a7  mov     rsi, rdx
0x18000f7aa  mov     rdi, rcx
0x18000f7ad  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000f7b4  jz      short loc_18000F7C6
0x18000f7b6  mov     [rax-10h], rbx
0x18000f7ba  mov     r9, rcx
0x18000f7bd  mov     [rax-18h], rdx
0x18000f7c1  call    WPP_SF_qSS
0x18000f7c6  test    rdi, rdi
0x18000f7c9  jz      short loc_18000F80A
0x18000f7cb  test    rbx, rbx
0x18000f7ce  jz      short loc_18000F80A
0x18000f7d0  lea     r8, [rsp+38h+pcbLength]; pcbLength
0x18000f7d5  mov     rcx, rbx; psz
0x18000f7d8  call    StringCbLengthW
0x18000f7dd  test    eax, eax
0x18000f7df  js      short loc_18000F80A
0x18000f7e1  mov     eax, dword ptr [rsp+38h+pcbLength]
0x18000f7e5  mov     r9d, 1; dwType
0x18000f7eb  add     eax, 2
0x18000f7ee  xor     r8d, r8d; Reserved
0x18000f7f1  mov     [rsp+38h+cbData], eax; cbData
0x18000f7f5  mov     rdx, rsi; lpValueName
0x18000f7f8  mov     rcx, rdi; hKey
0x18000f7fb  mov     [rsp+38h+lpData], rbx; lpData
0x18000f800  call    cs:__imp_RegSetValueExW
0x18000f806  mov     ebx, eax
0x18000f808  jmp     short loc_18000F80F
0x18000f80a  mov     ebx, 57h ; 'W'
0x18000f80f  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000f816  jz      short loc_18000F831
0x18000f818  mov     edx, 12h
0x18000f81d  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x18000f824  mov     ecx, 40Bh
0x18000f829  mov     r9d, ebx
0x18000f82c  call    WPP_SF_d
0x18000f831  mov     rsi, [rsp+38h+arg_10]
0x18000f836  mov     eax, ebx
0x18000f838  mov     rbx, [rsp+38h+arg_8]
0x18000f83d  add     rsp, 30h
0x18000f841  pop     rdi
0x18000f842  retn
```
