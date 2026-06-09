# IsAliasName(ushort const *,ushort const *)

- ea: `0x1800039d0`
- end: `0x180003bc2`
- name: `?IsAliasName@@YAHPEBG0@Z`
- size: `498`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, LPCWSTR lpValue)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003460`

## callees

- `0x1800039d0`
- `0x18000c380`
- `0x1800106c0`
- `0x1800207a4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003b1e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003b9b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003b1e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180003b9b`

## pseudocode

```c
_BOOL8 __fastcall IsAliasName(PCNZWCH lpString1, LPCWSTR lpValue)
{
  __int64 v4; // rbx
  unsigned __int16 v6[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !wcsncmp_0(lpValue, L"wave", 4u)
    || !wcsncmp_0(lpValue, L"midi", 4u)
    || !wcsncmp_0(lpValue, L"aux", 3u)
    || !wcsncmp_0(lpValue, L"mixer", 5u)
    || !wcsncmp_0(lpValue, L"msacm", 5u)
    || !wcsncmp_0(lpValue, L"vidc", 4u)
    || !wcsncmp_0(lpValue, L"midimapper", 0xAu)
    || !wcsncmp_0(lpValue, L"wavemapper", 0xAu)
    || !wcsncmp_0(lpValue, L"auxmapper", 9u) )
  {
    return 1;
  }
  v4 = -1;
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"MCI32", -1) == 2 )
  {
    do
      ++v4;
    while ( lpValue[v4] );
    if ( v4 )
    {
      while ( lpValue[v4 - 1] != 46 )
      {
        if ( !--v4 )
          return 1;
      }
      return 0;
    }
    return 1;
  }
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, wszDrivers, -1) == 2 )
    return mmRegQuerySystemIni(lpString1, lpValue, 0x104u, v6);
  return 0;
}

```

## disassembly

```asm
0x1800039d0  mov     [rsp+arg_10], rbx
0x1800039d5  mov     [rsp+arg_18], rsi
0x1800039da  push    rdi
0x1800039db  sub     rsp, 250h
0x1800039e2  mov     rax, cs:__security_cookie
0x1800039e9  xor     rax, rsp
0x1800039ec  mov     [rsp+258h+var_18], rax
0x1800039f4  mov     rdi, rdx
0x1800039f7  mov     rsi, rcx
0x1800039fa  mov     rcx, rdi; String1
0x1800039fd  lea     rdx, aWave; "wave"
0x180003a04  mov     r8d, 4; MaxCount
0x180003a0a  call    wcsncmp_0
0x180003a0f  test    eax, eax
0x180003a11  jz      loc_180003B51
0x180003a17  mov     r8d, 4; MaxCount
0x180003a1d  lea     rdx, aMidi; "midi"
0x180003a24  mov     rcx, rdi; String1
0x180003a27  call    wcsncmp_0
0x180003a2c  test    eax, eax
0x180003a2e  jz      loc_180003B51
0x180003a34  mov     r8d, 3; MaxCount
0x180003a3a  lea     rdx, aAux; "aux"
0x180003a41  mov     rcx, rdi; String1
0x180003a44  call    wcsncmp_0
0x180003a49  test    eax, eax
0x180003a4b  jz      loc_180003B51
0x180003a51  mov     r8d, 5; MaxCount
0x180003a57  lea     rdx, aMixer; "mixer"
0x180003a5e  mov     rcx, rdi; String1
0x180003a61  call    wcsncmp_0
0x180003a66  test    eax, eax
0x180003a68  jz      loc_180003B51
0x180003a6e  mov     r8d, 5; MaxCount
0x180003a74  lea     rdx, aMsacm; "msacm"
0x180003a7b  mov     rcx, rdi; String1
0x180003a7e  call    wcsncmp_0
0x180003a83  test    eax, eax
0x180003a85  jz      loc_180003B51
0x180003a8b  mov     r8d, 4; MaxCount
0x180003a91  lea     rdx, aVidc; "vidc"
0x180003a98  mov     rcx, rdi; String1
0x180003a9b  call    wcsncmp_0
0x180003aa0  test    eax, eax
0x180003aa2  jz      loc_180003B51
0x180003aa8  mov     r8d, 0Ah; MaxCount
0x180003aae  lea     rdx, aMidimapper; "midimapper"
0x180003ab5  mov     rcx, rdi; String1
0x180003ab8  call    wcsncmp_0
0x180003abd  test    eax, eax
0x180003abf  jz      loc_180003B51
0x180003ac5  mov     r8d, 0Ah; MaxCount
0x180003acb  lea     rdx, aWavemapper; "wavemapper"
0x180003ad2  mov     rcx, rdi; String1
0x180003ad5  call    wcsncmp_0
0x180003ada  test    eax, eax
0x180003adc  jz      short loc_180003B51
0x180003ade  mov     r8d, 9; MaxCount
0x180003ae4  lea     rdx, aAuxmapper; "auxmapper"
0x180003aeb  mov     rcx, rdi; String1
0x180003aee  call    wcsncmp_0
0x180003af3  test    eax, eax
0x180003af5  jz      short loc_180003B51
0x180003af7  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180003afe  lea     rax, aMci32; "MCI32"
0x180003b05  mov     [rsp+258h+cchCount2], ebx; cchCount2
0x180003b09  mov     r9d, ebx; cchCount1
0x180003b0c  mov     r8, rsi; lpString1
0x180003b0f  mov     [rsp+258h+lpString2], rax; lpString2
0x180003b14  mov     edx, 1; dwCmpFlags
0x180003b19  mov     ecx, 7Fh; Locale
0x180003b1e  call    cs:__imp_CompareStringW
0x180003b24  cmp     eax, 2
0x180003b27  jnz     short loc_180003B7B
0x180003b29  nop     dword ptr [rax+00000000h]
0x180003b30  inc     rbx
0x180003b33  cmp     word ptr [rdi+rbx*2], 0
0x180003b38  jnz     short loc_180003B30
0x180003b3a  test    rbx, rbx
0x180003b3d  jz      short loc_180003B51
0x180003b3f  mov     eax, 2Eh ; '.'
0x180003b44  cmp     ax, [rdi+rbx*2-2]
0x180003b49  jz      short loc_180003BBE
0x180003b4b  sub     rbx, 1
0x180003b4f  jnz     short loc_180003B44
0x180003b51  mov     eax, 1
0x180003b56  mov     rcx, [rsp+258h+var_18]
0x180003b5e  xor     rcx, rsp; StackCookie
0x180003b61  call    __security_check_cookie
0x180003b66  lea     r11, [rsp+258h+var_8]
0x180003b6e  mov     rbx, [r11+20h]
0x180003b72  mov     rsi, [r11+28h]
0x180003b76  mov     rsp, r11
0x180003b79  pop     rdi
0x180003b7a  retn
0x180003b7b  lea     rax, wszDrivers; "DRIVERS32"
0x180003b82  mov     [rsp+258h+cchCount2], ebx; cchCount2
0x180003b86  mov     r9d, ebx; cchCount1
0x180003b89  mov     [rsp+258h+lpString2], rax; lpString2
0x180003b8e  mov     r8, rsi; lpString1
0x180003b91  mov     edx, 1; dwCmpFlags
0x180003b96  mov     ecx, 7Fh; Locale
0x180003b9b  call    cs:__imp_CompareStringW
0x180003ba1  cmp     eax, 2
0x180003ba4  jnz     short loc_180003BBE
0x180003ba6  lea     r9, [rsp+258h+var_228]; unsigned __int16 *
0x180003bab  mov     r8d, 104h; unsigned int
0x180003bb1  mov     rdx, rdi; lpValue
0x180003bb4  mov     rcx, rsi; lpString1
0x180003bb7  call    ?mmRegQuerySystemIni@@YAHPEBG0KPEAG@Z; mmRegQuerySystemIni(ushort const *,ushort const *,ulong,ushort *)
0x180003bbc  jmp     short loc_180003B56
0x180003bbe  xor     eax, eax
0x180003bc0  jmp     short loc_180003B56
```
