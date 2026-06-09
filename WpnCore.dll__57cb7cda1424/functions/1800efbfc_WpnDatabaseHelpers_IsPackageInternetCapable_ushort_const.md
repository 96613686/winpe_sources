# WpnDatabaseHelpers::IsPackageInternetCapable(ushort const *)

- ea: `0x1800efbfc`
- end: `0x1800efd8c`
- name: `?IsPackageInternetCapable@WpnDatabaseHelpers@@YA_NPEBG@Z`
- size: `400`
- prototype: `bool __fastcall(WpnDatabaseHelpers *__hidden this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024890`
- `0x180065224`
- `0x1800b0418`
- `0x1800c8768`
- `0x1800d8340`

## callees

- `0x1800b99f0`
- `0x1800efbfc`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800efce5`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800efd37`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800efce5`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x1800efd37`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800efd60`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800efd77`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800efd60`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800efd77`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x1800efc55`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x1800efc55`

## pseudocode

```c
char __fastcall WpnDatabaseHelpers::IsPackageInternetCapable(WpnDatabaseHelpers *this, const unsigned __int16 *a2)
{
  __int64 v2; // rbx
  const wchar_t *v3; // rax
  __int64 v4; // rcx
  const wchar_t *i; // rax
  __int16 v7; // bx
  unsigned int j; // ebx
  unsigned int v9; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v10; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v11; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v12; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pSid2[48]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v14[48]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v15[48]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v16[48]; // [rsp+110h] [rbp+10h] BYREF

  v10 = 0;
  v9 = 0;
  if ( (int)QueryApplicationCapabilities(this, &v10, &v9, 0, 0, 0, 0, 0, 0) >= 0 )
  {
    v2 = 0x7FFF;
    v3 = L"internetClient";
    v11 = 0;
    v4 = 0x7FFF;
    v12 = 0;
    while ( *v3 )
    {
      ++v3;
      if ( !--v4 )
        return 0;
    }
    *((_QWORD *)&v12 + 1) = L"internetClient";
    LOWORD(v12) = -2 - 2 * v4;
    WORD1(v12) = -2 * v4;
    if ( (int)RtlDeriveCapabilitySidsFromName(&v12, v15, pSid2) >= 0 )
    {
      v11 = 0;
      for ( i = L"internetClientServer"; *i; ++i )
      {
        if ( !--v2 )
          return 0;
      }
      *((_QWORD *)&v11 + 1) = L"internetClientServer";
      v7 = 2 * v2;
      LOWORD(v11) = -2 - v7;
      WORD1(v11) = -v7;
      if ( (int)RtlDeriveCapabilitySidsFromName(&v11, v16, v14) >= 0 )
      {
        for ( j = 0; j < v9; ++j )
        {
          if ( EqualSid(*(PSID *)(v10 + 8LL * j), pSid2) || EqualSid(*(PSID *)(v10 + 8LL * j), v14) )
            return 1;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800efbfc  mov     [rsp-8+arg_8], rbx
0x1800efc01  mov     [rsp-8+arg_10], rsi
0x1800efc06  push    rbp
0x1800efc07  push    rdi
0x1800efc08  push    r14
0x1800efc0a  lea     rbp, [rsp-50h]
0x1800efc0f  sub     rsp, 150h
0x1800efc16  mov     rax, cs:__security_cookie
0x1800efc1d  xor     rax, rsp
0x1800efc20  mov     [rbp+60h+var_20], rax
0x1800efc24  xor     esi, esi
0x1800efc26  lea     r8, [rsp+160h+var_110]
0x1800efc2b  mov     [rsp+160h+var_120], rsi
0x1800efc30  lea     rdx, [rsp+160h+var_108]
0x1800efc35  mov     [rsp+160h+var_128], rsi
0x1800efc3a  xor     r9d, r9d
0x1800efc3d  mov     [rsp+160h+var_130], rsi
0x1800efc42  mov     [rsp+160h+var_138], rsi
0x1800efc47  mov     [rsp+160h+var_140], rsi
0x1800efc4c  mov     [rsp+160h+var_108], rsi
0x1800efc51  mov     [rsp+160h+var_110], esi
0x1800efc55  call    cs:__imp_QueryApplicationCapabilities
0x1800efc5b  test    eax, eax
0x1800efc5d  js      short loc_1800EFC92
0x1800efc5f  xorps   xmm0, xmm0
0x1800efc62  lea     rdx, aInternetclient; "internetClient"
0x1800efc69  xorps   xmm1, xmm1
0x1800efc6c  lea     r14d, [rsi+2]
0x1800efc70  mov     ebx, 7FFFh
0x1800efc75  mov     rax, rdx
0x1800efc78  movups  [rsp+160h+var_100], xmm0
0x1800efc7d  mov     ecx, ebx
0x1800efc7f  movups  [rsp+160h+var_F0], xmm1
0x1800efc84  cmp     [rax], si
0x1800efc87  jz      short loc_1800EFCB8
0x1800efc89  add     rax, r14
0x1800efc8c  sub     rcx, 1
0x1800efc90  jnz     short loc_1800EFC84
0x1800efc92  xor     al, al
0x1800efc94  mov     rcx, [rbp+60h+var_20]
0x1800efc98  xor     rcx, rsp; StackCookie
0x1800efc9b  call    __security_check_cookie
0x1800efca0  lea     r11, [rsp+160h+var_10]
0x1800efca8  mov     rbx, [r11+28h]
0x1800efcac  mov     rsi, [r11+30h]
0x1800efcb0  mov     rsp, r11
0x1800efcb3  pop     r14
0x1800efcb5  pop     rdi
0x1800efcb6  pop     rbp
0x1800efcb7  retn
0x1800efcb8  add     cx, cx
0x1800efcbb  mov     qword ptr [rsp+160h+var_F0+8], rdx
0x1800efcc0  mov     edi, 0FFFEh
0x1800efcc5  lea     r8, [rbp+60h+pSid2]
0x1800efcc9  mov     eax, edi
0x1800efccb  lea     rdx, [rbp+60h+var_80]
0x1800efccf  sub     ax, cx
0x1800efcd2  lea     rcx, [rsp+160h+var_F0]
0x1800efcd7  mov     word ptr [rsp+160h+var_F0], ax
0x1800efcdc  add     ax, r14w
0x1800efce0  mov     word ptr [rsp+160h+var_F0+2], ax
0x1800efce5  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800efceb  test    eax, eax
0x1800efced  js      short loc_1800EFC92
0x1800efcef  xorps   xmm0, xmm0
0x1800efcf2  lea     rcx, aInternetclient_0; "internetClientServer"
0x1800efcf9  movups  [rsp+160h+var_100], xmm0
0x1800efcfe  mov     rax, rcx
0x1800efd01  cmp     [rax], si
0x1800efd04  jz      short loc_1800EFD11
0x1800efd06  add     rax, r14
0x1800efd09  sub     rbx, 1
0x1800efd0d  jnz     short loc_1800EFD01
0x1800efd0f  jmp     short loc_1800EFC92
0x1800efd11  mov     qword ptr [rsp+160h+var_100+8], rcx
0x1800efd16  lea     r8, [rbp+60h+var_B0]
0x1800efd1a  add     bx, bx
0x1800efd1d  lea     rdx, [rbp+60h+var_50]
0x1800efd21  sub     di, bx
0x1800efd24  lea     rcx, [rsp+160h+var_100]
0x1800efd29  mov     word ptr [rsp+160h+var_100], di
0x1800efd2e  add     di, r14w
0x1800efd32  mov     word ptr [rsp+160h+var_100+2], di
0x1800efd37  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x1800efd3d  test    eax, eax
0x1800efd3f  js      loc_1800EFC92
0x1800efd45  mov     ebx, esi
0x1800efd47  cmp     ebx, [rsp+160h+var_110]
0x1800efd4b  jnb     loc_1800EFC92
0x1800efd51  mov     rcx, [rsp+160h+var_108]
0x1800efd56  lea     rdx, [rbp+60h+pSid2]; pSid2
0x1800efd5a  mov     edi, ebx
0x1800efd5c  mov     rcx, [rcx+rdi*8]; pSid1
0x1800efd60  call    cs:__imp_EqualSid
0x1800efd66  test    eax, eax
0x1800efd68  jnz     short loc_1800EFD85
0x1800efd6a  mov     rcx, [rsp+160h+var_108]
0x1800efd6f  lea     rdx, [rbp+60h+var_B0]; pSid2
0x1800efd73  mov     rcx, [rcx+rdi*8]; pSid1
0x1800efd77  call    cs:__imp_EqualSid
0x1800efd7d  test    eax, eax
0x1800efd7f  jnz     short loc_1800EFD85
0x1800efd81  inc     ebx
0x1800efd83  jmp     short loc_1800EFD47
0x1800efd85  mov     al, 1
0x1800efd87  jmp     loc_1800EFC94
```
