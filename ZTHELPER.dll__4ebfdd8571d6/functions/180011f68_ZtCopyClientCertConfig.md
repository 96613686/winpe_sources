# ZtCopyClientCertConfig

- ea: `0x180011f68`
- end: `0x1800120e9`
- name: `ZtCopyClientCertConfig`
- size: `385`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800120f0`
- `0x180012284`

## callees

- `0x18000dbcc`
- `0x18000e3c8`
- `0x180011f68`
- `0x180012564`
- `0x180015008`
- `0x180015398`

## import_xrefs

- `DNSAPI!DnsFreeZtClientCertConfig` at `0x1800120b4`
- `DNSAPI!DnsFreeZtClientCertConfig` at `0x1800120b4`

## pseudocode

```c
__int64 __fastcall ZtCopyClientCertConfig(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rsi
  unsigned int v5; // ebx
  __int64 v6; // rax
  __int64 i; // r8
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 j; // rbp

  v4 = 0;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_qq(1035, 10, WPP_9def979debf939f6192d96d7c9b80830_Traceguids, a1, a2);
  if ( a2 && (*a2 = 0, a1) )
  {
    v4 = (_QWORD *)Dns_Allocate(48);
    if ( !v4 )
    {
LABEL_6:
      v5 = 14;
      goto LABEL_19;
    }
    if ( *(_QWORD *)(a1 + 16) )
    {
      v6 = Dns_Allocate(36LL * *(unsigned int *)(a1 + 24));
      v4[2] = v6;
      if ( !v6 )
        goto LABEL_6;
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 24); *(_DWORD *)(v10 + 4 * v9 + 32) = *(_DWORD *)(v8 + 4 * v9 + 32) )
      {
        v8 = *(_QWORD *)(a1 + 16);
        v9 = 9 * i;
        v10 = v4[2];
        i = (unsigned int)(i + 1);
        *(_OWORD *)(v10 + 4 * v9) = *(_OWORD *)(v8 + 4 * v9);
        *(_OWORD *)(v10 + 4 * v9 + 16) = *(_OWORD *)(v8 + 4 * v9 + 16);
      }
    }
    *((_DWORD *)v4 + 6) = *(_DWORD *)(a1 + 24);
    if ( *(_QWORD *)(a1 + 32) )
    {
      v11 = Dns_Allocate(8LL * *(unsigned int *)(a1 + 40));
      v4[4] = v11;
      if ( !v11 )
        goto LABEL_6;
      for ( j = 0; (unsigned int)j < *(_DWORD *)(a1 + 40); j = (unsigned int)(j + 1) )
      {
        *(_QWORD *)(v4[4] + 8 * j) = Dns_CreateStringCopy_W(*(void **)(*(_QWORD *)(a1 + 32) + 8 * j));
        if ( !*(_QWORD *)(v4[4] + 8 * j) )
          goto LABEL_6;
      }
    }
    *((_DWORD *)v4 + 10) = *(_DWORD *)(a1 + 40);
    *(_DWORD *)v4 = *(_DWORD *)a1;
    v4[1] = *(_QWORD *)(a1 + 8);
    *a2 = v4;
    v4 = 0;
    v5 = 0;
  }
  else
  {
    v5 = 87;
  }
LABEL_19:
  if ( g_fVelocityZtdnsApiRefactor )
    ZtFreeClientCertConfig(v4);
  else
    DnsFreeZtClientCertConfig(v4);
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 11, WPP_9def979debf939f6192d96d7c9b80830_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180011f68  push    rbx
0x180011f6a  push    rbp
0x180011f6b  push    rsi
0x180011f6c  push    rdi
0x180011f6d  push    r14
0x180011f6f  sub     rsp, 30h
0x180011f73  mov     r14, rdx
0x180011f76  mov     rdi, rcx
0x180011f79  xor     esi, esi
0x180011f7b  test    byte ptr cs:xmmword_18001F260+1, 8
0x180011f82  jz      short loc_180011FA0
0x180011f84  lea     edx, [rsi+0Ah]
0x180011f87  mov     [rsp+58h+var_38], r14
0x180011f8c  mov     ecx, 40Bh
0x180011f91  lea     r8, WPP_9def979debf939f6192d96d7c9b80830_Traceguids
0x180011f98  mov     r9, rdi
0x180011f9b  call    WPP_SF_qq
0x180011fa0  test    r14, r14
0x180011fa3  jz      loc_18001209C
0x180011fa9  mov     [r14], rsi
0x180011fac  test    rdi, rdi
0x180011faf  jz      loc_18001209C
0x180011fb5  mov     ecx, 30h ; '0'
0x180011fba  call    Dns_Allocate
0x180011fbf  mov     rsi, rax
0x180011fc2  test    rax, rax
0x180011fc5  jnz     short loc_180011FD1
0x180011fc7  mov     ebx, 0Eh
0x180011fcc  jmp     loc_1800120A1
0x180011fd1  cmp     qword ptr [rdi+10h], 0
0x180011fd6  jz      short loc_180012029
0x180011fd8  mov     eax, [rdi+18h]
0x180011fdb  lea     rcx, [rax+rax*8]
0x180011fdf  shl     rcx, 2
0x180011fe3  call    Dns_Allocate
0x180011fe8  mov     [rsi+10h], rax
0x180011fec  test    rax, rax
0x180011fef  jz      short loc_180011FC7
0x180011ff1  xor     r8d, r8d
0x180011ff4  cmp     [rdi+18h], r8d
0x180011ff8  jbe     short loc_180012029
0x180011ffa  mov     rax, [rdi+10h]
0x180011ffe  lea     rdx, [r8+r8*8]
0x180012002  mov     rcx, [rsi+10h]
0x180012006  inc     r8d
0x180012009  movups  xmm0, xmmword ptr [rax+rdx*4]
0x18001200d  movups  xmmword ptr [rcx+rdx*4], xmm0
0x180012011  movups  xmm1, xmmword ptr [rax+rdx*4+10h]
0x180012016  movups  xmmword ptr [rcx+rdx*4+10h], xmm1
0x18001201b  mov     eax, [rax+rdx*4+20h]
0x18001201f  mov     [rcx+rdx*4+20h], eax
0x180012023  cmp     r8d, [rdi+18h]
0x180012027  jb      short loc_180011FFA
0x180012029  mov     eax, [rdi+18h]
0x18001202c  mov     [rsi+18h], eax
0x18001202f  cmp     qword ptr [rdi+20h], 0
0x180012034  jz      short loc_180012081
0x180012036  mov     ecx, [rdi+28h]
0x180012039  shl     rcx, 3
0x18001203d  call    Dns_Allocate
0x180012042  mov     [rsi+20h], rax
0x180012046  test    rax, rax
0x180012049  jz      loc_180011FC7
0x18001204f  xor     ebp, ebp
0x180012051  cmp     ebp, [rdi+28h]
0x180012054  jnb     short loc_180012081
0x180012056  mov     rcx, [rdi+20h]
0x18001205a  mov     rcx, [rcx+rbp*8]; Src
0x18001205e  call    Dns_CreateStringCopy_W
0x180012063  mov     rcx, rax
0x180012066  mov     rax, [rsi+20h]
0x18001206a  mov     [rax+rbp*8], rcx
0x18001206e  mov     rax, [rsi+20h]
0x180012072  cmp     qword ptr [rax+rbp*8], 0
0x180012077  jz      loc_180011FC7
0x18001207d  inc     ebp
0x18001207f  jmp     short loc_180012051
0x180012081  mov     eax, [rdi+28h]
0x180012084  mov     [rsi+28h], eax
0x180012087  mov     eax, [rdi]
0x180012089  mov     [rsi], eax
0x18001208b  mov     rax, [rdi+8]
0x18001208f  mov     [rsi+8], rax
0x180012093  mov     [r14], rsi
0x180012096  xor     esi, esi
0x180012098  xor     ebx, ebx
0x18001209a  jmp     short loc_1800120A1
0x18001209c  mov     ebx, 57h ; 'W'
0x1800120a1  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x1800120a8  mov     rcx, rsi; lpMem
0x1800120ab  jz      short loc_1800120B4
0x1800120ad  call    ZtFreeClientCertConfig
0x1800120b2  jmp     short loc_1800120BA
0x1800120b4  call    cs:__imp_DnsFreeZtClientCertConfig
0x1800120ba  test    byte ptr cs:xmmword_18001F260+1, 8
0x1800120c1  jz      short loc_1800120DC
0x1800120c3  mov     edx, 0Bh
0x1800120c8  lea     r8, WPP_9def979debf939f6192d96d7c9b80830_Traceguids
0x1800120cf  mov     ecx, 40Bh
0x1800120d4  mov     r9d, ebx
0x1800120d7  call    WPP_SF_d
0x1800120dc  mov     eax, ebx
0x1800120de  add     rsp, 30h
0x1800120e2  pop     r14
0x1800120e4  pop     rdi
0x1800120e5  pop     rsi
0x1800120e6  pop     rbp
0x1800120e7  pop     rbx
0x1800120e8  retn
```
