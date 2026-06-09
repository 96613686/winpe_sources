# ZtSetTrustedServer

- ea: `0x180006940`
- end: `0x180006b1f`
- name: `ZtSetTrustedServer`
- size: `479`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180007130`

## callees

- `0x1800014b0`
- `0x18000206a`
- `0x1800064ac`
- `0x1800066f4`
- `0x180006940`
- `0x18000ef10`
- `0x180015008`
- `0x180015478`
- `0x1800154c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006af0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006af0`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x180006a23`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x180006a23`

## pseudocode

```c
__int64 __fastcall ZtSetTrustedServer(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int Key; // ebx
  unsigned int v7; // eax
  __int64 v8; // rdx
  HKEY hKey[2]; // [rsp+50h] [rbp-D8h] BYREF
  _BYTE v11[144]; // [rsp+60h] [rbp-C8h] BYREF

  memset_0(v11, 0, 0x82u);
  hKey[0] = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qqq(1026, 49, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, a1, a2, a3);
  if ( !a1 || !a2 )
    goto LABEL_4;
  v7 = DnsConvertSockaddrToString(a1 + 16, v11);
  Key = v7;
  if ( v7 )
  {
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_23;
    v8 = 50;
  }
  else
  {
    Key = RegCreateKeyExInternalW(a2, v11, 0, 0, 0, 131078, 0, hKey, 0, a3);
    if ( Key )
    {
      if ( (xmmword_18001F260 & 4) == 0 )
        goto LABEL_23;
      WPP_SF_DS(1026, 51, (unsigned int)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, Key, (__int64)v11);
      goto LABEL_21;
    }
    if ( *(_DWORD *)(a1 + 48) != 1 )
    {
      if ( *(_DWORD *)(a1 + 48) == 2 )
      {
        v7 = ZtSetTrustedDotServer(a1, hKey[0]);
        Key = v7;
        if ( !v7 )
          goto LABEL_21;
        if ( (xmmword_18001F260 & 4) == 0 )
          goto LABEL_23;
        v8 = 53;
        goto LABEL_20;
      }
LABEL_4:
      Key = 87;
      goto LABEL_21;
    }
    v7 = ZtSetTrustedDohServer(a1, hKey[0]);
    Key = v7;
    if ( !v7 )
      goto LABEL_21;
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_23;
    v8 = 52;
  }
LABEL_20:
  WPP_SF_d(1026, v8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v7);
LABEL_21:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 54, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, Key);
LABEL_23:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return Key;
}

```

## disassembly

```asm
0x180006940  mov     [rsp+arg_18], rbx
0x180006945  push    rbp
0x180006946  push    rsi
0x180006947  push    rdi
0x180006948  push    r12
0x18000694a  push    r13
0x18000694c  sub     rsp, 100h
0x180006953  mov     rax, cs:__security_cookie
0x18000695a  xor     rax, rsp
0x18000695d  mov     [rsp+128h+var_38], rax
0x180006965  mov     rbp, r8
0x180006968  mov     rsi, rdx
0x18000696b  mov     rdi, rcx
0x18000696e  xor     edx, edx; Val
0x180006970  mov     r8d, 82h; Size
0x180006976  lea     rcx, [rsp+128h+var_C8]; void *
0x18000697b  call    memset_0
0x180006980  mov     [rsp+128h+hKey], 0
0x180006989  test    byte ptr cs:xmmword_18001F260, 4
0x180006990  lea     r13, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x180006997  mov     r12d, 402h
0x18000699d  jz      short loc_1800069BC
0x18000699f  mov     edx, 31h ; '1'
0x1800069a4  mov     [rsp+128h+var_100], rbp
0x1800069a9  mov     ecx, r12d
0x1800069ac  mov     [rsp+128h+var_108], rsi
0x1800069b1  mov     r9, rdi
0x1800069b4  mov     r8, r13
0x1800069b7  call    WPP_SF_qqq
0x1800069bc  test    rdi, rdi
0x1800069bf  jnz     short loc_1800069CB
0x1800069c1  mov     ebx, 57h ; 'W'
0x1800069c6  jmp     loc_180006ACA
0x1800069cb  test    rsi, rsi
0x1800069ce  jz      short loc_1800069C1
0x1800069d0  lea     rcx, [rdi+10h]
0x1800069d4  lea     rdx, [rsp+128h+var_C8]
0x1800069d9  call    DnsConvertSockaddrToString
0x1800069de  mov     ebx, eax
0x1800069e0  test    eax, eax
0x1800069e2  jnz     loc_180006AAE
0x1800069e8  mov     [rsp+128h+var_E0], rbp
0x1800069ed  lea     rax, [rsp+128h+hKey]
0x1800069f2  mov     [rsp+128h+var_E8], 0
0x1800069fb  lea     rdx, [rsp+128h+var_C8]
0x180006a00  mov     [rsp+128h+var_F0], rax
0x180006a05  xor     r9d, r9d
0x180006a08  mov     [rsp+128h+var_F8], 0
0x180006a11  xor     r8d, r8d
0x180006a14  mov     dword ptr [rsp+128h+var_100], 20006h
0x180006a1c  mov     rcx, rsi
0x180006a1f  mov     dword ptr [rsp+128h+var_108], ebx
0x180006a23  call    cs:__imp_RegCreateKeyExInternalW
0x180006a29  mov     ebx, eax
0x180006a2b  test    eax, eax
0x180006a2d  jnz     short loc_180006A86
0x180006a2f  mov     ecx, [rdi+30h]
0x180006a32  sub     ecx, 1
0x180006a35  jz      short loc_180006A63
0x180006a37  cmp     ecx, 1
0x180006a3a  jnz     short loc_1800069C1
0x180006a3c  mov     rdx, [rsp+128h+hKey]
0x180006a41  mov     rcx, rdi
0x180006a44  call    ZtSetTrustedDotServer
0x180006a49  mov     ebx, eax
0x180006a4b  test    eax, eax
0x180006a4d  jz      short loc_180006ACA
0x180006a4f  test    byte ptr cs:xmmword_18001F260, 4
0x180006a56  jz      loc_180006AE6
0x180006a5c  mov     edx, 35h ; '5'
0x180006a61  jmp     short loc_180006ABC
0x180006a63  mov     rdx, [rsp+128h+hKey]
0x180006a68  mov     rcx, rdi
0x180006a6b  call    ZtSetTrustedDohServer
0x180006a70  mov     ebx, eax
0x180006a72  test    eax, eax
0x180006a74  jz      short loc_180006ACA
0x180006a76  test    byte ptr cs:xmmword_18001F260, 4
0x180006a7d  jz      short loc_180006AE6
0x180006a7f  mov     edx, 34h ; '4'
0x180006a84  jmp     short loc_180006ABC
0x180006a86  test    byte ptr cs:xmmword_18001F260, 4
0x180006a8d  jz      short loc_180006AE6
0x180006a8f  lea     rax, [rsp+128h+var_C8]
0x180006a94  mov     edx, 33h ; '3'
0x180006a99  mov     ecx, r12d
0x180006a9c  mov     [rsp+128h+var_108], rax
0x180006aa1  mov     r9d, ebx
0x180006aa4  mov     r8, r13
0x180006aa7  call    WPP_SF_DS
0x180006aac  jmp     short loc_180006ACA
0x180006aae  test    byte ptr cs:xmmword_18001F260, 4
0x180006ab5  jz      short loc_180006AE6
0x180006ab7  mov     edx, 32h ; '2'
0x180006abc  mov     r9d, eax
0x180006abf  mov     r8, r13
0x180006ac2  mov     ecx, r12d
0x180006ac5  call    WPP_SF_d
0x180006aca  test    byte ptr cs:xmmword_18001F260, 4
0x180006ad1  jz      short loc_180006AE6
0x180006ad3  mov     edx, 36h ; '6'
0x180006ad8  mov     ecx, r12d
0x180006adb  mov     r9d, ebx
0x180006ade  mov     r8, r13
0x180006ae1  call    WPP_SF_d
0x180006ae6  mov     rcx, [rsp+128h+hKey]; hKey
0x180006aeb  test    rcx, rcx
0x180006aee  jz      short loc_180006AF6
0x180006af0  call    cs:__imp_RegCloseKey
0x180006af6  mov     eax, ebx
0x180006af8  mov     rcx, [rsp+128h+var_38]
0x180006b00  xor     rcx, rsp; StackCookie
0x180006b03  call    __security_check_cookie
0x180006b08  mov     rbx, [rsp+128h+arg_18]
0x180006b10  add     rsp, 100h
0x180006b17  pop     r13
0x180006b19  pop     r12
0x180006b1b  pop     rdi
0x180006b1c  pop     rsi
0x180006b1d  pop     rbp
0x180006b1e  retn
```
