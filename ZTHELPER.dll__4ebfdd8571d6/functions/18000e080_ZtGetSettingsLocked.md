# ZtGetSettingsLocked

- ea: `0x18000e080`
- end: `0x18000e268`
- name: `ZtGetSettingsLocked`
- size: `488`
- prototype: `__int64 __fastcall(char, int, _QWORD *, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800044e4`
- `0x1800049b0`
- `0x18000df6c`

## callees

- `0x18000e080`
- `0x18000fde8`
- `0x180010908`
- `0x180011858`
- `0x180011ca4`
- `0x1800120f0`
- `0x180012564`
- `0x180015008`
- `0x180015398`

## import_xrefs

- `DNSAPI!DnsFreeZtSettings` at `0x18000e251`
- `DNSAPI!DnsFreeZtSettings` at `0x18000e251`

## pseudocode

```c
__int64 __fastcall ZtGetSettingsLocked(char a1, int a2, _QWORD *a3, __int64 a4)
{
  __int64 v5; // r14
  _QWORD *v8; // rdi
  __int64 v9; // rcx
  _BYTE *v10; // rax
  unsigned int ConfigLocked; // ebx
  _DWORD *v12; // rax
  LPVOID v13; // rax

  v5 = a2;
  v8 = 0;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_qq(1035, 0xEu, (ULONGLONG)WPP_8742bf61083c35ee7a1ca06b0a43eac6_Traceguids, a3, a4);
  if ( a3 )
    *a3 = 0;
  if ( a4 )
  {
    v9 = 20;
    v10 = (_BYTE *)a4;
    do
    {
      *v10++ = 0;
      --v9;
    }
    while ( v9 );
  }
  if ( !a3 )
    goto LABEL_9;
  if ( (unsigned int)v5 > 1 )
  {
    ConfigLocked = 87;
    if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
      goto LABEL_34;
    WPP_SF_d(1035, 0xFu, (ULONGLONG)WPP_8742bf61083c35ee7a1ca06b0a43eac6_Traceguids, 87);
    goto LABEL_32;
  }
  v12 = Dns_Allocate(0x48u);
  v8 = v12;
  if ( !v12 )
    goto LABEL_9;
  ConfigLocked = 0;
  *v12 = 1;
  if ( (a1 & 1) != 0 )
  {
    v13 = Dns_Allocate(0x38u);
    v8[2] = v13;
    if ( v13 )
    {
      ConfigLocked = ZtGetConfigLocked(v5, g_rgfZtConfigInitialized[v5], (__int64)v13);
      if ( ConfigLocked )
        goto LABEL_32;
      v8[1] |= 1uLL;
      goto LABEL_16;
    }
LABEL_9:
    ConfigLocked = 87;
    goto LABEL_32;
  }
LABEL_16:
  if ( (a1 & 2) != 0 )
  {
    ConfigLocked = ZtGetTrustedServersLocked((unsigned int)v5, v8 + 4, v8 + 3);
    if ( ConfigLocked )
      goto LABEL_32;
    v8[1] |= 2uLL;
  }
  if ( (a1 & 4) != 0 )
  {
    ConfigLocked = ZtGetRulesLocked((unsigned int)v5, v8 + 6, v8 + 5);
    if ( ConfigLocked )
      goto LABEL_32;
    v8[1] |= 4uLL;
  }
  if ( (a1 & 8) != 0 )
  {
    ConfigLocked = ZtGetClientCertConfigLocked(v5, v8 + 7);
    if ( ConfigLocked )
      goto LABEL_32;
    v8[1] |= 8uLL;
  }
  if ( (a1 & 0x10) == 0 )
    goto LABEL_28;
  ConfigLocked = ZtGetTrustedCaLocked((unsigned int)v5, v8 + 8);
  if ( !ConfigLocked )
  {
    v8[1] |= 0x10uLL;
LABEL_28:
    *a3 = v8;
    v8 = 0;
    if ( a4 )
    {
      *(_OWORD *)a4 = *(__int128 *)((char *)&g_rgZtHelperSettingsState + 20 * v5);
      *(_DWORD *)(a4 + 16) = dword_18001F360[5 * v5];
    }
  }
LABEL_32:
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 0x10u, (ULONGLONG)WPP_8742bf61083c35ee7a1ca06b0a43eac6_Traceguids, ConfigLocked);
LABEL_34:
  if ( v8 )
    DnsFreeZtSettings(v8);
  return ConfigLocked;
}

```

## disassembly

```asm
0x18000e080  push    rbx
0x18000e082  push    rbp
0x18000e083  push    rsi
0x18000e084  push    rdi
0x18000e085  push    r12
0x18000e087  push    r14
0x18000e089  push    r15
0x18000e08b  sub     rsp, 30h
0x18000e08f  mov     rbp, r9
0x18000e092  movsxd  r14, edx
0x18000e095  mov     rsi, r8
0x18000e098  mov     r15, rcx
0x18000e09b  xor     edi, edi
0x18000e09d  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000e0a4  jz      short loc_18000E0C2
0x18000e0a6  mov     [rsp+68h+var_48], r9
0x18000e0ab  lea     edx, [rdi+0Eh]
0x18000e0ae  mov     r9, r8
0x18000e0b1  mov     ecx, 40Bh
0x18000e0b6  lea     r8, WPP_8742bf61083c35ee7a1ca06b0a43eac6_Traceguids
0x18000e0bd  call    WPP_SF_qq
0x18000e0c2  test    rsi, rsi
0x18000e0c5  jz      short loc_18000E0CA
0x18000e0c7  mov     [rsi], rdi
0x18000e0ca  test    rbp, rbp
0x18000e0cd  jz      short loc_18000E0E3
0x18000e0cf  mov     ecx, 14h
0x18000e0d4  mov     rax, rbp
0x18000e0d7  mov     [rax], dil
0x18000e0da  inc     rax
0x18000e0dd  sub     rcx, 1
0x18000e0e1  jnz     short loc_18000E0D7
0x18000e0e3  test    rsi, rsi
0x18000e0e6  jnz     short loc_18000E0F2
0x18000e0e8  mov     ebx, 57h ; 'W'
0x18000e0ed  jmp     loc_18000E227
0x18000e0f2  cmp     r14d, 1
0x18000e0f6  ja      loc_18000E202
0x18000e0fc  mov     ecx, 48h ; 'H'
0x18000e101  call    Dns_Allocate
0x18000e106  mov     rdi, rax
0x18000e109  test    rax, rax
0x18000e10c  jz      short loc_18000E0E8
0x18000e10e  xor     ebx, ebx
0x18000e110  mov     dword ptr [rax], 1
0x18000e116  lea     r12, cs:180000000h
0x18000e11d  test    r15b, 1
0x18000e121  jz      short loc_18000E156
0x18000e123  lea     ecx, [rbx+38h]
0x18000e126  call    Dns_Allocate
0x18000e12b  mov     [rdi+10h], rax
0x18000e12f  test    rax, rax
0x18000e132  jz      short loc_18000E0E8
0x18000e134  mov     edx, rva g_rgfZtConfigInitialized[r12+r14*4]
0x18000e13c  mov     r8, rax
0x18000e13f  mov     ecx, r14d
0x18000e142  call    ZtGetConfigLocked
0x18000e147  mov     ebx, eax
0x18000e149  test    eax, eax
0x18000e14b  jnz     loc_18000E227
0x18000e151  or      qword ptr [rdi+8], 1
0x18000e156  test    r15b, 2
0x18000e15a  jz      short loc_18000E17B
0x18000e15c  lea     r8, [rdi+18h]
0x18000e160  mov     ecx, r14d
0x18000e163  lea     rdx, [rdi+20h]
0x18000e167  call    ZtGetTrustedServersLocked
0x18000e16c  mov     ebx, eax
0x18000e16e  test    eax, eax
0x18000e170  jnz     loc_18000E227
0x18000e176  or      qword ptr [rdi+8], 2
0x18000e17b  test    r15b, 4
0x18000e17f  jz      short loc_18000E1A0
0x18000e181  lea     r8, [rdi+28h]
0x18000e185  mov     ecx, r14d
0x18000e188  lea     rdx, [rdi+30h]
0x18000e18c  call    ZtGetRulesLocked
0x18000e191  mov     ebx, eax
0x18000e193  test    eax, eax
0x18000e195  jnz     loc_18000E227
0x18000e19b  or      qword ptr [rdi+8], 4
0x18000e1a0  test    r15b, 8
0x18000e1a4  jz      short loc_18000E1BD
0x18000e1a6  lea     rdx, [rdi+38h]
0x18000e1aa  mov     ecx, r14d
0x18000e1ad  call    ZtGetClientCertConfigLocked
0x18000e1b2  mov     ebx, eax
0x18000e1b4  test    eax, eax
0x18000e1b6  jnz     short loc_18000E227
0x18000e1b8  or      qword ptr [rdi+8], 8
0x18000e1bd  test    r15b, 10h
0x18000e1c1  jz      short loc_18000E1DA
0x18000e1c3  lea     rdx, [rdi+40h]
0x18000e1c7  mov     ecx, r14d
0x18000e1ca  call    ZtGetTrustedCaLocked
0x18000e1cf  mov     ebx, eax
0x18000e1d1  test    eax, eax
0x18000e1d3  jnz     short loc_18000E227
0x18000e1d5  or      qword ptr [rdi+8], 10h
0x18000e1da  mov     [rsi], rdi
0x18000e1dd  xor     edi, edi
0x18000e1df  test    rbp, rbp
0x18000e1e2  jz      short loc_18000E227
0x18000e1e4  lea     rax, [r14+r14*4]
0x18000e1e8  movups  xmm0, rva g_rgZtHelperSettingsState[r12+rax*4]
0x18000e1f1  movups  xmmword ptr [rbp+0], xmm0
0x18000e1f5  mov     eax, rva dword_18001F360[r12+rax*4]
0x18000e1fd  mov     [rbp+10h], eax
0x18000e200  jmp     short loc_18000E227
0x18000e202  mov     ebx, 57h ; 'W'
0x18000e207  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000e20e  jz      short loc_18000E249
0x18000e210  lea     edx, [rbx-48h]
0x18000e213  mov     ecx, 40Bh
0x18000e218  mov     r9d, ebx
0x18000e21b  lea     r8, WPP_8742bf61083c35ee7a1ca06b0a43eac6_Traceguids
0x18000e222  call    WPP_SF_d
0x18000e227  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000e22e  jz      short loc_18000E249
0x18000e230  mov     edx, 10h
0x18000e235  lea     r8, WPP_8742bf61083c35ee7a1ca06b0a43eac6_Traceguids
0x18000e23c  mov     ecx, 40Bh
0x18000e241  mov     r9d, ebx
0x18000e244  call    WPP_SF_d
0x18000e249  test    rdi, rdi
0x18000e24c  jz      short loc_18000E257
0x18000e24e  mov     rcx, rdi
0x18000e251  call    cs:__imp_DnsFreeZtSettings
0x18000e257  mov     eax, ebx
0x18000e259  add     rsp, 30h
0x18000e25d  pop     r15
0x18000e25f  pop     r14
0x18000e261  pop     r12
0x18000e263  pop     rdi
0x18000e264  pop     rsi
0x18000e265  pop     rbp
0x18000e266  pop     rbx
0x18000e267  retn
```
