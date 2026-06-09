# ZtValidateTrustedServers

- ea: `0x1800072b0`
- end: `0x1800073cc`
- name: `ZtValidateTrustedServers`
- size: `284`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180004f98`
- `0x1800054bc`
- `0x180005924`

## callees

- `0x180006b28`
- `0x180006bcc`
- `0x1800072b0`
- `0x180015008`
- `0x180015268`
- `0x1800152b0`
- `0x180015618`

## pseudocode

```c
__int64 __fastcall ZtValidateTrustedServers(unsigned int a1, __int64 a2, __int64 a3, __int64 a4)
{
  _BOOL8 v6; // rcx
  unsigned int v7; // ebx
  unsigned int i; // edi
  _DWORD *v9; // r14
  __int64 v11; // [rsp+20h] [rbp-38h]

  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_dq(1026, 0x1Eu, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, a1, a2);
  v6 = a1 == 0;
  if ( (a2 == 0) == v6 )
  {
    v7 = 0;
    for ( i = 0; i < a1; ++i )
    {
      v9 = (_DWORD *)(a2 + ((unsigned __int64)i << 6));
      if ( (xmmword_18001F260 & 4) != 0 )
        WPP_SF__SOCKADDR_(v6, 32, a3, v9 + 4);
      if ( *v9 != 1 )
      {
        v7 = 87;
        if ( (xmmword_18001F260 & 4) == 0 )
          return v7;
        LODWORD(v11) = *v9;
        WPP_SF_Dd(1026, 0x21u, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, a4, v11);
        break;
      }
      v7 = ZtValidateTrustedServerAddress(v9 + 4);
      if ( v7 )
        break;
      v7 = ZtValidateTrustedServerConfigInfo(a2 + ((unsigned __int64)i << 6));
      if ( v7 )
        break;
    }
  }
  else
  {
    v7 = 87;
    if ( (xmmword_18001F260 & 4) == 0 )
      return v7;
    WPP_SF_d(1026, 0x1Fu, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, 87);
  }
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0x22u, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x1800072b0  push    rbx
0x1800072b2  push    rbp
0x1800072b3  push    rsi
0x1800072b4  push    rdi
0x1800072b5  push    r14
0x1800072b7  sub     rsp, 30h
0x1800072bb  mov     rbp, rdx
0x1800072be  mov     esi, ecx
0x1800072c0  test    byte ptr cs:xmmword_18001F260, 4
0x1800072c7  jz      short loc_1800072E7
0x1800072c9  mov     edx, 1Eh
0x1800072ce  mov     [rsp+58h+var_38], rbp
0x1800072d3  mov     ecx, 402h
0x1800072d8  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x1800072df  mov     r9d, esi
0x1800072e2  call    WPP_SF_dq
0x1800072e7  xor     ecx, ecx
0x1800072e9  test    esi, esi
0x1800072eb  setz    cl
0x1800072ee  xor     eax, eax
0x1800072f0  test    rbp, rbp
0x1800072f3  setz    al
0x1800072f6  cmp     eax, ecx
0x1800072f8  jnz     short loc_180007378
0x1800072fa  xor     ebx, ebx
0x1800072fc  xor     edi, edi
0x1800072fe  cmp     edi, esi
0x180007300  jnb     loc_18000739D
0x180007306  mov     r14d, edi
0x180007309  shl     r14, 6
0x18000730d  add     r14, rbp
0x180007310  test    byte ptr cs:xmmword_18001F260, 4
0x180007317  jz      short loc_180007327
0x180007319  mov     edx, 20h ; ' '
0x18000731e  lea     r9, [r14+10h]
0x180007322  call    WPP_SF__SOCKADDR_
0x180007327  mov     eax, [r14]
0x18000732a  cmp     eax, 1
0x18000732d  jnz     short loc_180007350
0x18000732f  lea     rcx, [r14+10h]
0x180007333  call    ZtValidateTrustedServerAddress
0x180007338  mov     ebx, eax
0x18000733a  test    eax, eax
0x18000733c  jnz     short loc_18000739D
0x18000733e  mov     rcx, r14
0x180007341  call    ZtValidateTrustedServerConfigInfo
0x180007346  mov     ebx, eax
0x180007348  test    eax, eax
0x18000734a  jnz     short loc_18000739D
0x18000734c  inc     edi
0x18000734e  jmp     short loc_1800072FE
0x180007350  mov     ebx, 57h ; 'W'
0x180007355  test    byte ptr cs:xmmword_18001F260, 4
0x18000735c  jz      short loc_1800073BF
0x18000735e  lea     edx, [rbx-36h]
0x180007361  mov     dword ptr [rsp+58h+var_38], eax
0x180007365  mov     ecx, 402h
0x18000736a  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x180007371  call    WPP_SF_Dd
0x180007376  jmp     short loc_18000739D
0x180007378  mov     ebx, 57h ; 'W'
0x18000737d  test    byte ptr cs:xmmword_18001F260, 4
0x180007384  jz      short loc_1800073BF
0x180007386  lea     edx, [rbx-38h]
0x180007389  mov     ecx, 402h
0x18000738e  mov     r9d, ebx
0x180007391  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x180007398  call    WPP_SF_d
0x18000739d  test    byte ptr cs:xmmword_18001F260, 4
0x1800073a4  jz      short loc_1800073BF
0x1800073a6  mov     edx, 22h ; '"'
0x1800073ab  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x1800073b2  mov     ecx, 402h
0x1800073b7  mov     r9d, ebx
0x1800073ba  call    WPP_SF_d
0x1800073bf  mov     eax, ebx
0x1800073c1  add     rsp, 30h
0x1800073c5  pop     r14
0x1800073c7  pop     rdi
0x1800073c8  pop     rsi
0x1800073c9  pop     rbp
0x1800073ca  pop     rbx
0x1800073cb  retn
```
