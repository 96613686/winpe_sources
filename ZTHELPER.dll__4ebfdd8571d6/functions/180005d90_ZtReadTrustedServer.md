# ZtReadTrustedServer

- ea: `0x180005d90`
- end: `0x180006044`
- name: `ZtReadTrustedServer`
- size: `692`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, int *, _OWORD *, int *, _OWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000604c`

## callees

- `0x1800014b0`
- `0x18000206a`
- `0x18000549c`
- `0x1800054bc`
- `0x180005924`
- `0x180005d90`
- `0x18000c750`
- `0x180015008`
- `0x1800154c8`
- `0x180015720`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000601c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000601c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005e80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005e80`

## pseudocode

```c
__int64 __fastcall ZtReadTrustedServer(HKEY hKey, LPCWSTR lpSubKey, int *a3, _OWORD *a4, int *a5, _OWORD *a6)
{
  int v10; // edx
  int v11; // ecx
  int v12; // r8d
  ULONG TrustedDotServer; // ebx
  LSTATUS v14; // eax
  ULONG TrustedDohServer; // eax
  int v16; // r13d
  USHORT v17; // dx
  int v18; // r9d
  _BYTE *v19; // rax
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int64 v23; // r8
  __int64 v24; // rdx
  __int128 v25; // xmm0
  _BYTE *v26; // rax
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  int v31; // [rsp+50h] [rbp-99h]
  HKEY hKeya; // [rsp+58h] [rbp-91h] BYREF
  _OWORD v33[4]; // [rsp+60h] [rbp-89h] BYREF
  _OWORD v34[4]; // [rsp+A0h] [rbp-49h] BYREF

  hKeya = 0;
  memset_0(v33, 0, sizeof(v33));
  memset_0(v34, 0, sizeof(v34));
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_qSqqqq(v11, v10, v12, (_DWORD)hKey, (__int64)lpSubKey, (char)a3, (char)a4, (char)a5, (char)a6);
  WxZeroOut<_DNS_ZT_TRUSTED_SERVER>(a4);
  WxZeroOut<_DNS_ZT_TRUSTED_SERVER>(a6);
  if ( a3 )
    *a3 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !a3 || !a4 || !a5 || !a6 )
  {
    TrustedDotServer = 87;
    goto LABEL_36;
  }
  v14 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &hKeya);
  TrustedDotServer = v14;
  if ( v14 )
  {
    if ( (xmmword_18001F260 & 4) != 0 )
      WPP_SF_DS(1026, 0x44u, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v14, lpSubKey);
    goto LABEL_36;
  }
  v31 = 0;
  TrustedDohServer = ZtReadTrustedDohServer(hKeya, lpSubKey, v33);
  TrustedDotServer = TrustedDohServer;
  if ( TrustedDohServer != 2 )
  {
    if ( TrustedDohServer )
    {
      if ( (xmmword_18001F260 & 4) == 0 )
        goto LABEL_36;
      v17 = 69;
      goto LABEL_25;
    }
    v31 = 1;
  }
  v16 = 0;
  TrustedDotServer = ZtReadTrustedDotServer(hKeya, lpSubKey, v34);
  TrustedDohServer = 2;
  if ( TrustedDotServer != 2 )
  {
    if ( TrustedDotServer )
    {
      if ( (xmmword_18001F260 & 4) != 0 )
      {
        v17 = 70;
        v18 = TrustedDotServer;
        goto LABEL_26;
      }
      goto LABEL_36;
    }
    v16 = 1;
  }
  if ( !v31 && !v16 )
  {
    TrustedDotServer = 2;
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_36;
    v17 = 71;
LABEL_25:
    v18 = TrustedDohServer;
LABEL_26:
    WPP_SF_d(1026, v17, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v18);
    goto LABEL_36;
  }
  v19 = v33;
  v20 = v33[1];
  TrustedDotServer = 0;
  *a4 = v33[0];
  v21 = v33[2];
  a4[1] = v20;
  v22 = v33[3];
  v23 = 64;
  a4[2] = v21;
  v24 = 64;
  a4[3] = v22;
  do
  {
    *v19++ = 0;
    --v24;
  }
  while ( v24 );
  v25 = v34[0];
  v26 = v34;
  v27 = v34[1];
  *a3 = v31;
  *a6 = v25;
  v28 = v34[2];
  a6[1] = v27;
  v29 = v34[3];
  a6[2] = v28;
  a6[3] = v29;
  do
  {
    *v26++ = 0;
    --v23;
  }
  while ( v23 );
  *a5 = v16;
LABEL_36:
  DnsFreeZtTrustedServerMembers((__int64)v33);
  DnsFreeZtTrustedServerMembers((__int64)v34);
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0x48u, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, TrustedDotServer);
  if ( hKeya )
    RegCloseKey(hKeya);
  return TrustedDotServer;
}

```

## disassembly

```asm
0x180005d90  push    rbp
0x180005d92  push    rbx
0x180005d93  push    rsi
0x180005d94  push    rdi
0x180005d95  push    r12
0x180005d97  push    r13
0x180005d99  push    r14
0x180005d9b  push    r15
0x180005d9d  lea     rbp, [rsp-0Fh]
0x180005da2  sub     rsp, 0F8h
0x180005da9  mov     rax, cs:__security_cookie
0x180005db0  xor     rax, rsp
0x180005db3  mov     [rbp+47h+var_50], rax
0x180005db7  mov     rsi, [rbp+47h+arg_20]
0x180005dbb  mov     r12, r8
0x180005dbe  mov     r14, [rbp+47h+arg_28]
0x180005dc2  mov     r15, rdx
0x180005dc5  mov     rbx, rcx
0x180005dc8  mov     [rsp+130h+hKey], 0
0x180005dd1  mov     r13d, 40h ; '@'
0x180005dd7  lea     rcx, [rsp+130h+var_D0]; void *
0x180005ddc  mov     r8d, r13d; Size
0x180005ddf  xor     edx, edx; Val
0x180005de1  mov     rdi, r9
0x180005de4  call    memset_0
0x180005de9  mov     r8d, r13d; Size
0x180005dec  lea     rcx, [rbp+47h+var_90]; void *
0x180005df0  xor     edx, edx; Val
0x180005df2  call    memset_0
0x180005df7  test    byte ptr cs:xmmword_18001F260, 4
0x180005dfe  jz      short loc_180005E21
0x180005e00  mov     [rsp+130h+var_F0], r14
0x180005e05  mov     r9, rbx
0x180005e08  mov     [rsp+130h+var_F8], rsi
0x180005e0d  mov     [rsp+130h+var_100], rdi
0x180005e12  mov     [rsp+130h+var_108], r12
0x180005e17  mov     [rsp+130h+phkResult], r15
0x180005e1c  call    WPP_SF_qSqqqq
0x180005e21  mov     rcx, rdi
0x180005e24  call    ??$WxZeroOut@U_DNS_ZT_TRUSTED_SERVER@@@@YAXPEAU_DNS_ZT_TRUSTED_SERVER@@@Z; WxZeroOut<_DNS_ZT_TRUSTED_SERVER>(_DNS_ZT_TRUSTED_SERVER *)
0x180005e29  mov     rcx, r14
0x180005e2c  call    ??$WxZeroOut@U_DNS_ZT_TRUSTED_SERVER@@@@YAXPEAU_DNS_ZT_TRUSTED_SERVER@@@Z; WxZeroOut<_DNS_ZT_TRUSTED_SERVER>(_DNS_ZT_TRUSTED_SERVER *)
0x180005e31  test    r12, r12
0x180005e34  jz      short loc_180005E3E
0x180005e36  mov     dword ptr [r12], 0
0x180005e3e  test    rsi, rsi
0x180005e41  jz      short loc_180005E49
0x180005e43  mov     dword ptr [rsi], 0
0x180005e49  test    r12, r12
0x180005e4c  jnz     short loc_180005E58
0x180005e4e  mov     ebx, 57h ; 'W'
0x180005e53  jmp     loc_180005FDD
0x180005e58  test    rdi, rdi
0x180005e5b  jz      short loc_180005E4E
0x180005e5d  test    rsi, rsi
0x180005e60  jz      short loc_180005E4E
0x180005e62  test    r14, r14
0x180005e65  jz      short loc_180005E4E
0x180005e67  lea     rax, [rsp+130h+hKey]
0x180005e6c  mov     r9d, 20019h; samDesired
0x180005e72  xor     r8d, r8d; ulOptions
0x180005e75  mov     [rsp+130h+phkResult], rax; phkResult
0x180005e7a  mov     rdx, r15; lpSubKey
0x180005e7d  mov     rcx, rbx; hKey
0x180005e80  call    cs:__imp_RegOpenKeyExW
0x180005e86  mov     ebx, eax
0x180005e88  test    eax, eax
0x180005e8a  jnz     loc_180005FB6
0x180005e90  mov     rcx, [rsp+130h+hKey]; hKey
0x180005e95  lea     r8, [rsp+130h+var_D0]
0x180005e9a  mov     rdx, r15
0x180005e9d  mov     [rsp+130h+var_E0], eax
0x180005ea1  call    ZtReadTrustedDohServer
0x180005ea6  mov     ebx, eax
0x180005ea8  cmp     eax, 2
0x180005eab  jz      short loc_180005EB9
0x180005ead  test    eax, eax
0x180005eaf  jnz     short loc_180005F00
0x180005eb1  mov     [rsp+130h+var_E0], 1
0x180005eb9  mov     rcx, [rsp+130h+hKey]; hKey
0x180005ebe  lea     r8, [rbp+47h+var_90]
0x180005ec2  mov     rdx, r15
0x180005ec5  xor     r13d, r13d
0x180005ec8  call    ZtReadTrustedDotServer
0x180005ecd  mov     ebx, eax
0x180005ecf  lea     eax, [r13+2]
0x180005ed3  cmp     ebx, eax
0x180005ed5  jz      short loc_180005EDF
0x180005ed7  test    ebx, ebx
0x180005ed9  jnz     short loc_180005F2B
0x180005edb  lea     r13d, [rax-1]
0x180005edf  mov     ecx, [rsp+130h+var_E0]
0x180005ee3  test    ecx, ecx
0x180005ee5  jnz     short loc_180005F42
0x180005ee7  test    r13d, r13d
0x180005eea  jnz     short loc_180005F42
0x180005eec  mov     ebx, eax
0x180005eee  test    byte ptr cs:xmmword_18001F260, 4
0x180005ef5  jz      loc_180005FDD
0x180005efb  lea     edx, [rcx+47h]
0x180005efe  jmp     short loc_180005F12
0x180005f00  test    byte ptr cs:xmmword_18001F260, 4
0x180005f07  jz      loc_180005FDD
0x180005f0d  mov     edx, 45h ; 'E'
0x180005f12  mov     r9d, eax
0x180005f15  mov     ecx, 402h
0x180005f1a  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x180005f21  call    WPP_SF_d
0x180005f26  jmp     loc_180005FDD
0x180005f2b  test    byte ptr cs:xmmword_18001F260, 4
0x180005f32  jz      loc_180005FDD
0x180005f38  mov     edx, 46h ; 'F'
0x180005f3d  mov     r9d, ebx
0x180005f40  jmp     short loc_180005F15
0x180005f42  movaps  xmm0, [rsp+130h+var_D0]
0x180005f47  lea     rax, [rsp+130h+var_D0]
0x180005f4c  movaps  xmm1, [rbp+47h+var_C0]
0x180005f50  xor     ebx, ebx
0x180005f52  movaps  xmmword ptr [rdi], xmm0
0x180005f55  movaps  xmm0, [rbp+47h+var_B0]
0x180005f59  movaps  xmmword ptr [rdi+10h], xmm1
0x180005f5d  movaps  xmm1, [rbp+47h+var_A0]
0x180005f61  lea     r8d, [rbx+40h]
0x180005f65  movaps  xmmword ptr [rdi+20h], xmm0
0x180005f69  mov     edx, r8d
0x180005f6c  movaps  xmmword ptr [rdi+30h], xmm1
0x180005f70  mov     [rax], bl
0x180005f72  inc     rax
0x180005f75  sub     rdx, 1
0x180005f79  jnz     short loc_180005F70
0x180005f7b  movaps  xmm0, [rbp+47h+var_90]
0x180005f7f  lea     rax, [rbp+47h+var_90]
0x180005f83  movaps  xmm1, [rbp+47h+var_80]
0x180005f87  mov     [r12], ecx
0x180005f8b  movaps  xmmword ptr [r14], xmm0
0x180005f8f  movaps  xmm0, [rbp+47h+var_70]
0x180005f93  movaps  xmmword ptr [r14+10h], xmm1
0x180005f98  movaps  xmm1, [rbp+47h+var_60]
0x180005f9c  movaps  xmmword ptr [r14+20h], xmm0
0x180005fa1  movaps  xmmword ptr [r14+30h], xmm1
0x180005fa6  mov     [rax], bl
0x180005fa8  inc     rax
0x180005fab  sub     r8, 1
0x180005faf  jnz     short loc_180005FA6
0x180005fb1  mov     [rsi], r13d
0x180005fb4  jmp     short loc_180005FDD
0x180005fb6  test    byte ptr cs:xmmword_18001F260, 4
0x180005fbd  jz      short loc_180005FDD
0x180005fbf  mov     edx, 44h ; 'D'
0x180005fc4  mov     [rsp+130h+phkResult], r15
0x180005fc9  mov     ecx, 402h
0x180005fce  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x180005fd5  mov     r9d, eax
0x180005fd8  call    WPP_SF_DS
0x180005fdd  lea     rcx, [rsp+130h+var_D0]
0x180005fe2  call    DnsFreeZtTrustedServerMembers
0x180005fe7  lea     rcx, [rbp+47h+var_90]
0x180005feb  call    DnsFreeZtTrustedServerMembers
0x180005ff0  test    byte ptr cs:xmmword_18001F260, 4
0x180005ff7  jz      short loc_180006012
0x180005ff9  mov     edx, 48h ; 'H'
0x180005ffe  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x180006005  mov     ecx, 402h
0x18000600a  mov     r9d, ebx
0x18000600d  call    WPP_SF_d
0x180006012  mov     rcx, [rsp+130h+hKey]; hKey
0x180006017  test    rcx, rcx
0x18000601a  jz      short loc_180006022
0x18000601c  call    cs:__imp_RegCloseKey
0x180006022  mov     eax, ebx
0x180006024  mov     rcx, [rbp+47h+var_50]
0x180006028  xor     rcx, rsp; StackCookie
0x18000602b  call    __security_check_cookie
0x180006030  add     rsp, 0F8h
0x180006037  pop     r15
0x180006039  pop     r14
0x18000603b  pop     r13
0x18000603d  pop     r12
0x18000603f  pop     rdi
0x180006040  pop     rsi
0x180006041  pop     rbx
0x180006042  pop     rbp
0x180006043  retn
```
