# WaaS2::Device::ParseCpuMatchingCriteria

- ea: `0x18005feb4`
- end: `0x18005ff56`
- name: `WaaS2::Device::ParseCpuMatchingCriteria`
- size: `162`
- prototype: `__int64 __fastcall(PCNZWCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004be64`

## callees

- `0x18005feb4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005fef8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005ff38`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005fef8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005ff38`

## pseudocode

```c
__int64 __fastcall WaaS2::Device::ParseCpuMatchingCriteria(const WCHAR *lpString1)
{
  PCNZWCH v1; // rbx
  const WCHAR *v2; // r8
  int v4; // eax
  unsigned int v5; // ecx

  v1 = lpString1;
  if ( *((_QWORD *)lpString1 + 3) <= 7u )
    v2 = lpString1;
  else
    v2 = *(const WCHAR **)lpString1;
  if ( v2 && CompareStringW(0x7Fu, 1u, v2, -1, L"allOf", -1) == 2 )
    return 1;
  if ( *((_QWORD *)v1 + 3) > 7u )
    v1 = *(PCNZWCH *)v1;
  if ( !v1 )
    return 0;
  v4 = CompareStringW(0x7Fu, 1u, v1, -1, L"noneOf", -1);
  v5 = 0;
  if ( v4 == 2 )
    return 2;
  return v5;
}

```

## disassembly

```asm
0x18005feb4  mov     [rsp+arg_0], rbx
0x18005feb9  push    rbp
0x18005feba  sub     rsp, 30h
0x18005febe  cmp     qword ptr [rcx+18h], 7
0x18005fec3  mov     rbx, rcx
0x18005fec6  jbe     short loc_18005FECD
0x18005fec8  mov     r8, [rcx]
0x18005fecb  jmp     short loc_18005FED0
0x18005fecd  mov     r8, rbx; lpString1
0x18005fed0  mov     ebp, 2
0x18005fed5  test    r8, r8
0x18005fed8  jz      short loc_18005FF07
0x18005feda  lea     rcx, aAllof; "allOf"
0x18005fee1  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005fee9  mov     [rsp+38h+lpString2], rcx; lpString2
0x18005feee  lea     edx, [rbp-1]; dwCmpFlags
0x18005fef1  lea     ecx, [rbp+7Dh]; Locale
0x18005fef4  or      r9d, 0FFFFFFFFh; cchCount1
0x18005fef8  call    cs:__imp_CompareStringW
0x18005fefe  cmp     eax, ebp
0x18005ff00  jnz     short loc_18005FF07
0x18005ff02  lea     eax, [rbp-1]
0x18005ff05  jmp     short loc_18005FF4B
0x18005ff07  cmp     qword ptr [rbx+18h], 7
0x18005ff0c  jbe     short loc_18005FF11
0x18005ff0e  mov     rbx, [rbx]
0x18005ff11  test    rbx, rbx
0x18005ff14  jz      short loc_18005FF49
0x18005ff16  or      r9d, 0FFFFFFFFh; cchCount1
0x18005ff1a  mov     [rsp+38h+cchCount2], 0FFFFFFFFh; cchCount2
0x18005ff22  lea     rax, aNoneof; "noneOf"
0x18005ff29  mov     r8, rbx; lpString1
0x18005ff2c  mov     [rsp+38h+lpString2], rax; lpString2
0x18005ff31  lea     edx, [r9+2]; dwCmpFlags
0x18005ff35  lea     ecx, [rdx+7Eh]; Locale
0x18005ff38  call    cs:__imp_CompareStringW
0x18005ff3e  xor     ecx, ecx
0x18005ff40  cmp     eax, ebp
0x18005ff42  cmovz   ecx, ebp
0x18005ff45  mov     eax, ecx
0x18005ff47  jmp     short loc_18005FF4B
0x18005ff49  xor     eax, eax
0x18005ff4b  mov     rbx, [rsp+38h+arg_0]
0x18005ff50  add     rsp, 30h
0x18005ff54  pop     rbp
0x18005ff55  retn
```
