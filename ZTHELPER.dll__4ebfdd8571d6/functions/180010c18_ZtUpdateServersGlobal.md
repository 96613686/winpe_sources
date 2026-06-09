# ZtUpdateServersGlobal

- ea: `0x180010c18`
- end: `0x180011076`
- name: `ZtUpdateServersGlobal`
- size: `1118`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, __int64, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006f9c`
- `0x18000ddec`

## callees

- `0x1800014b0`
- `0x18000dcb0`
- `0x180010274`
- `0x180010314`
- `0x180010480`
- `0x1800105c0`
- `0x180010790`
- `0x180010c18`
- `0x180012564`
- `0x1800132f0`
- `0x180015008`
- `0x180016544`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180010df0`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180010e96`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180010f9c`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180010df0`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180010e96`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180010f9c`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x18001100a`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x180011016`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x180011021`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x18001100a`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x180011016`
- `DNSAPI!DnsFreeZtTrustedServers` at `0x180011021`

## pseudocode

```c
__int64 __fastcall ZtUpdateServersGlobal(unsigned int a1, unsigned int a2, __int64 a3, int a4, __int64 a5, __int64 a6)
{
  _DWORD *v6; // r10
  unsigned int UniqueServers; // ebx
  size_t v9; // rsi
  _QWORD *v10; // r8
  unsigned int v11; // edx
  char *v12; // r14
  void *v13; // rbp
  unsigned int v14; // r13d
  unsigned int v15; // edi
  USHORT v16; // dx
  __int64 v17; // rcx
  void *v18; // rax
  __int64 v19; // r12
  char *v20; // rax
  unsigned int v21; // eax
  LPVOID v22; // rax
  unsigned int i; // ebx
  char *v24; // r15
  LPVOID v25; // rax
  int v27; // [rsp+60h] [rbp-68h]
  char *v29; // [rsp+68h] [rbp-60h]
  size_t NumOfElements; // [rsp+80h] [rbp-48h] BYREF

  v6 = (_DWORD *)a5;
  UniqueServers = 0;
  v9 = a2;
  v10 = (_QWORD *)a6;
  v11 = a1;
  v12 = 0;
  v27 = a4;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  LODWORD(NumOfElements) = 0;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
  {
    WPP_SF_ddqlqq(a1, a1, a6, a1, v9, a3, a4, a5, a6);
    v11 = a1;
    a4 = v27;
    v10 = (_QWORD *)a6;
    v6 = (_DWORD *)a5;
  }
  if ( v10 )
    *v10 = 0;
  if ( v6 )
    *v6 = 0;
  if ( ((_DWORD)v9 == 0) != (a3 == 0) )
  {
    UniqueServers = 87;
    if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
      goto LABEL_12;
    v16 = 20;
    goto LABEL_11;
  }
  if ( v11 > 1 )
  {
    UniqueServers = 87;
    if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
    {
LABEL_12:
      v17 = 0;
      v18 = 0;
      goto LABEL_13;
    }
    v16 = 21;
LABEL_11:
    WPP_SF_d(1035, v16, (ULONGLONG)WPP_cbd6223456ee357e6d251c3ed41b29e6_Traceguids, 87);
    goto LABEL_12;
  }
  v19 = (int)v11;
  if ( a4 )
    v14 = v9 + g_cDnsZtServers[v11];
  else
    v14 = v9;
  if ( v14 )
  {
    v20 = (char *)Dns_Allocate((unsigned __int64)v14 << 6);
    v12 = v20;
    if ( !v20 )
    {
      UniqueServers = 14;
      goto LABEL_12;
    }
    if ( g_fVelocitySortTrustedServers )
    {
      UniqueServers = ZtCopyTrustedServers(v9, a3, (__int64)v20);
      if ( UniqueServers )
        goto LABEL_12;
      qsort(v12, v9, 0x40u, (_CoreCrtNonSecureSearchSortCompareFunction)DnsZtServerSortCompare);
      for ( i = 1; i < (unsigned int)v9; ++i )
      {
        v24 = &v12[64 * (unsigned __int64)i];
        v29 = &v12[64 * (unsigned __int64)(i - 1)];
        if ( !DnsCompareSockaddrInet((_WORD *)v29 + 8, (_WORD *)v24 + 8) && *((_WORD *)v29 + 23) != *((_WORD *)v24 + 23) )
        {
          UniqueServers = 87;
          if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
            goto LABEL_12;
          v16 = 22;
          goto LABEL_11;
        }
        if ( !(unsigned int)DnsZtServerCompare(&v12[64 * (unsigned __int64)(i - 1)], v24, 0) )
        {
          UniqueServers = 87;
          if ( (BYTE1(xmmword_18001F260) & 8) == 0 )
            goto LABEL_12;
          v16 = 23;
          goto LABEL_11;
        }
      }
      if ( v27 )
      {
        ZtMergeExistingTrustedServers(a1, v14, v12, &NumOfElements);
        v15 = NumOfElements;
      }
      else
      {
        v15 = v9;
      }
      v25 = Dns_Allocate((unsigned __int64)v15 << 6);
      v13 = v25;
      if ( !v25 )
        goto LABEL_28;
      UniqueServers = ZtCopyTrustedServers(v15, (__int64)v12, (__int64)v25);
      if ( UniqueServers )
        goto LABEL_29;
    }
    else
    {
      if ( v27 )
        v21 = ZtMergeTrustedServers(
                (unsigned int)g_cDnsZtServers[v19],
                g_pDnsZtServers[v19],
                (unsigned int)v9,
                a3,
                v14,
                v20);
      else
        v21 = ZtCopyTrustedServers(v9, a3, (__int64)v20);
      UniqueServers = v21;
      if ( v21 )
        goto LABEL_12;
      qsort(v12, v14, 0x40u, (_CoreCrtNonSecureSearchSortCompareFunction)DnsZtServerSortCompare);
      UniqueServers = ZtGetUniqueServers(v14, v12, &NumOfElements, 0);
      if ( UniqueServers )
        goto LABEL_32;
      v15 = NumOfElements;
      v22 = Dns_Allocate((unsigned __int64)(unsigned int)NumOfElements << 6);
      v13 = v22;
      if ( !v22 )
      {
LABEL_28:
        UniqueServers = 14;
LABEL_29:
        v18 = 0;
        v17 = 0;
        goto LABEL_13;
      }
      UniqueServers = ZtGetUniqueServers(v14, v12, &NumOfElements, v22);
      if ( UniqueServers )
      {
LABEL_32:
        v15 = NumOfElements;
        goto LABEL_29;
      }
      v15 = NumOfElements;
    }
    qsort(v13, v15, 0x40u, (_CoreCrtNonSecureSearchSortCompareFunction)DnsZtServerSortCompareByPriority);
    v10 = (_QWORD *)a6;
    v6 = (_DWORD *)a5;
  }
  v18 = (void *)g_pDnsZtServers[v19];
  v17 = (unsigned int)g_cDnsZtServers[v19];
  if ( v10 )
  {
    *v10 = v18;
    v18 = 0;
    *v6 = v17;
    v17 = 0;
  }
  g_pDnsZtServers[v19] = (__int64)v13;
  v13 = 0;
  g_cDnsZtServers[v19] = v15;
  v15 = 0;
LABEL_13:
  if ( g_fVelocityZtdnsApiRefactor )
  {
    ZtFreeTrustedServers(v17, v18);
    ZtFreeTrustedServers(v14, v12);
    ZtFreeTrustedServers(v15, v13);
  }
  else
  {
    DnsFreeZtTrustedServers(v17, v18);
    DnsFreeZtTrustedServers(v14, v12);
    DnsFreeZtTrustedServers(v15, v13);
  }
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_d(1035, 0x18u, (ULONGLONG)WPP_cbd6223456ee357e6d251c3ed41b29e6_Traceguids, UniqueServers);
  return UniqueServers;
}

```

## disassembly

```asm
0x180010c18  mov     r11, rsp
0x180010c1b  mov     [r11+20h], rbx
0x180010c1f  push    rbp
0x180010c20  push    rsi
0x180010c21  push    rdi
0x180010c22  push    r12
0x180010c24  push    r13
0x180010c26  push    r14
0x180010c28  push    r15
0x180010c2a  sub     rsp, 90h
0x180010c31  mov     rax, cs:__security_cookie
0x180010c38  xor     rax, rsp
0x180010c3b  mov     [rsp+0C8h+var_40], rax
0x180010c43  mov     r10, [rsp+0C8h+arg_20]
0x180010c4b  xor     ebx, ebx
0x180010c4d  mov     r15, r8
0x180010c50  mov     esi, edx
0x180010c52  mov     r8, [rsp+0C8h+arg_28]
0x180010c5a  mov     edx, ecx
0x180010c5c  mov     [rsp+0C8h+var_58], r8
0x180010c61  mov     r14d, ebx
0x180010c64  mov     [rsp+0C8h+var_68], r9d
0x180010c69  mov     ebp, ebx
0x180010c6b  mov     [rsp+0C8h+var_64], ecx
0x180010c6f  mov     r13d, ebx
0x180010c72  mov     [rsp+0C8h+var_50], r10
0x180010c77  mov     edi, ebx
0x180010c79  mov     [rsp+0C8h+var_70], rbx
0x180010c7e  mov     [r11-48h], ebx
0x180010c82  test    byte ptr cs:xmmword_18001F260+1, 8
0x180010c89  jz      short loc_180010CBE
0x180010c8b  mov     [rsp+0C8h+var_88], r8
0x180010c90  mov     [rsp+0C8h+var_90], r10
0x180010c95  mov     [rsp+0C8h+var_98], r9d
0x180010c9a  mov     r9d, ecx
0x180010c9d  mov     [rsp+0C8h+var_A0], r15
0x180010ca2  mov     [rsp+0C8h+var_A8], esi
0x180010ca6  call    WPP_SF_ddqlqq
0x180010cab  mov     edx, [rsp+0C8h+var_64]
0x180010caf  mov     r9d, [rsp+0C8h+var_68]
0x180010cb4  mov     r8, [rsp+0C8h+var_58]
0x180010cb9  mov     r10, [rsp+0C8h+var_50]
0x180010cbe  test    r8, r8
0x180010cc1  jz      short loc_180010CC6
0x180010cc3  mov     [r8], rbx
0x180010cc6  test    r10, r10
0x180010cc9  jz      short loc_180010CCE
0x180010ccb  mov     [r10], ebx
0x180010cce  test    r15, r15
0x180010cd1  mov     ecx, ebx
0x180010cd3  mov     eax, ebx
0x180010cd5  setz    cl
0x180010cd8  test    esi, esi
0x180010cda  setz    al
0x180010cdd  cmp     eax, ecx
0x180010cdf  jnz     loc_180010FEB
0x180010ce5  cmp     edx, 1
0x180010ce8  jbe     short loc_180010D45
0x180010cea  mov     r9d, 57h ; 'W'
0x180010cf0  mov     ebx, r9d
0x180010cf3  test    byte ptr cs:xmmword_18001F260+1, 8
0x180010cfa  jz      short loc_180010D11
0x180010cfc  lea     edx, [r9-42h]
0x180010d00  mov     ecx, 40Bh
0x180010d05  lea     r8, WPP_cbd6223456ee357e6d251c3ed41b29e6_Traceguids
0x180010d0c  call    WPP_SF_d
0x180010d11  mov     ecx, edi
0x180010d13  mov     rax, rdi
0x180010d16  cmp     cs:g_fVelocityZtdnsApiRefactor, 0
0x180010d1d  mov     rdx, rax
0x180010d20  jz      loc_18001100A
0x180010d26  call    ZtFreeTrustedServers
0x180010d2b  mov     rdx, r14
0x180010d2e  mov     ecx, r13d
0x180010d31  call    ZtFreeTrustedServers
0x180010d36  mov     rdx, rbp
0x180010d39  mov     ecx, edi
0x180010d3b  call    ZtFreeTrustedServers
0x180010d40  jmp     loc_180011027
0x180010d45  movsxd  r12, edx
0x180010d48  lea     r11, cs:180000000h
0x180010d4f  test    r9d, r9d
0x180010d52  jz      short loc_180010D61
0x180010d54  mov     r13d, rva g_cDnsZtServers[r11+r12*4]
0x180010d5c  add     r13d, esi
0x180010d5f  jmp     short loc_180010D64
0x180010d61  mov     r13d, esi
0x180010d64  test    r13d, r13d
0x180010d67  jz      loc_180010FB3
0x180010d6d  mov     ecx, r13d
0x180010d70  shl     rcx, 6
0x180010d74  call    Dns_Allocate
0x180010d79  mov     r14, rax
0x180010d7c  test    rax, rax
0x180010d7f  jnz     short loc_180010D86
0x180010d81  lea     ebx, [rax+0Eh]
0x180010d84  jmp     short loc_180010D11
0x180010d86  cmp     cs:g_fVelocitySortTrustedServers, ebx
0x180010d8c  jnz     loc_180010E6E
0x180010d92  cmp     [rsp+0C8h+var_68], ebx
0x180010d96  jz      short loc_180010DC6
0x180010d98  lea     rcx, cs:180000000h
0x180010d9f  mov     [rsp+0C8h+var_A0], r14
0x180010da4  mov     rdx, rva g_pDnsZtServers[rcx+r12*8]
0x180010dac  mov     r9, r15
0x180010daf  mov     ecx, rva g_cDnsZtServers[rcx+r12*4]
0x180010db7  mov     r8d, esi
0x180010dba  mov     [rsp+0C8h+var_A8], r13d
0x180010dbf  call    ZtMergeTrustedServers
0x180010dc4  jmp     short loc_180010DD3
0x180010dc6  mov     r8, r14
0x180010dc9  mov     rdx, r15
0x180010dcc  mov     ecx, esi
0x180010dce  call    ZtCopyTrustedServers
0x180010dd3  mov     ebx, eax
0x180010dd5  test    eax, eax
0x180010dd7  jnz     loc_180010D11
0x180010ddd  lea     r9, DnsZtServerSortCompare; CompareFunction
0x180010de4  mov     edx, r13d; NumOfElements
0x180010de7  mov     r8d, 40h ; '@'; SizeOfElements
0x180010ded  mov     rcx, r14; Base
0x180010df0  call    cs:__imp_qsort
0x180010df6  xor     r9d, r9d
0x180010df9  lea     r8, [rsp+0C8h+NumOfElements]
0x180010e01  mov     rdx, r14
0x180010e04  mov     ecx, r13d
0x180010e07  call    ZtGetUniqueServers
0x180010e0c  mov     ebx, eax
0x180010e0e  test    eax, eax
0x180010e10  jnz     short loc_180010E65
0x180010e12  mov     edi, dword ptr [rsp+0C8h+NumOfElements]
0x180010e19  mov     ecx, edi
0x180010e1b  shl     rcx, 6
0x180010e1f  call    Dns_Allocate
0x180010e24  mov     rbp, rax
0x180010e27  test    rax, rax
0x180010e2a  jnz     short loc_180010E3D
0x180010e2c  mov     ebx, 0Eh
0x180010e31  mov     rax, [rsp+0C8h+var_70]
0x180010e36  mov     ecx, eax
0x180010e38  jmp     loc_180010D16
0x180010e3d  mov     r9, rax
0x180010e40  lea     r8, [rsp+0C8h+NumOfElements]
0x180010e48  mov     rdx, r14
0x180010e4b  mov     ecx, r13d
0x180010e4e  call    ZtGetUniqueServers
0x180010e53  mov     ebx, eax
0x180010e55  test    eax, eax
0x180010e57  jnz     short loc_180010E65
0x180010e59  mov     edi, dword ptr [rsp+0C8h+NumOfElements]
0x180010e60  jmp     loc_180010F8A
0x180010e65  mov     edi, dword ptr [rsp+0C8h+NumOfElements]
0x180010e6c  jmp     short loc_180010E31
0x180010e6e  mov     r8, r14
0x180010e71  mov     rdx, r15
0x180010e74  mov     ecx, esi
0x180010e76  call    ZtCopyTrustedServers
0x180010e7b  mov     ebx, eax
0x180010e7d  test    eax, eax
0x180010e7f  jnz     loc_180010D11
0x180010e85  mov     rdx, rsi; NumOfElements
0x180010e88  lea     r9, DnsZtServerSortCompare; CompareFunction
0x180010e8f  lea     r8d, [rax+40h]; SizeOfElements
0x180010e93  mov     rcx, r14; Base
0x180010e96  call    cs:__imp_qsort
0x180010e9c  mov     ebx, 1
0x180010ea1  cmp     ebx, esi
0x180010ea3  jnb     loc_180010F34
0x180010ea9  mov     r15d, ebx
0x180010eac  lea     eax, [rbx-1]
0x180010eaf  shl     rax, 6
0x180010eb3  add     rax, r14
0x180010eb6  shl     r15, 6
0x180010eba  add     r15, r14
0x180010ebd  mov     [rsp+0C8h+var_60], rax
0x180010ec2  lea     rcx, [rax+10h]
0x180010ec6  lea     rdx, [r15+10h]
0x180010eca  call    DnsCompareSockaddrInet
0x180010ecf  mov     rcx, [rsp+0C8h+var_60]
0x180010ed4  test    eax, eax
0x180010ed6  jnz     short loc_180010EE3
0x180010ed8  movzx   eax, word ptr [r15+2Eh]
0x180010edd  cmp     [rcx+2Eh], ax
0x180010ee1  jnz     short loc_180010EF6
0x180010ee3  xor     r8d, r8d
0x180010ee6  mov     rdx, r15
0x180010ee9  call    DnsZtServerCompare
0x180010eee  test    eax, eax
0x180010ef0  jz      short loc_180010F15
0x180010ef2  inc     ebx
0x180010ef4  jmp     short loc_180010EA1
0x180010ef6  mov     r9d, 57h ; 'W'
0x180010efc  mov     ebx, r9d
0x180010eff  test    byte ptr cs:xmmword_18001F260+1, 8
0x180010f06  jz      loc_180010D11
0x180010f0c  lea     edx, [r9-41h]
0x180010f10  jmp     loc_180010D00
0x180010f15  mov     r9d, 57h ; 'W'
0x180010f1b  mov     ebx, r9d
0x180010f1e  test    byte ptr cs:xmmword_18001F260+1, 8
0x180010f25  jz      loc_180010D11
0x180010f2b  lea     edx, [r9-40h]
0x180010f2f  jmp     loc_180010D00
0x180010f34  cmp     [rsp+0C8h+var_68], edi
0x180010f38  jz      short loc_180010F5A
0x180010f3a  mov     ecx, [rsp+0C8h+var_64]
0x180010f3e  lea     r9, [rsp+0C8h+NumOfElements]
0x180010f46  mov     r8, r14
0x180010f49  mov     edx, r13d
0x180010f4c  call    ZtMergeExistingTrustedServers
0x180010f51  mov     edi, dword ptr [rsp+0C8h+NumOfElements]
0x180010f58  jmp     short loc_180010F5C
0x180010f5a  mov     edi, esi
0x180010f5c  mov     ecx, edi
0x180010f5e  shl     rcx, 6
0x180010f62  call    Dns_Allocate
0x180010f67  mov     rbp, rax
0x180010f6a  test    rax, rax
0x180010f6d  jz      loc_180010E2C
0x180010f73  mov     r8, rax
0x180010f76  mov     rdx, r14
0x180010f79  mov     ecx, edi
0x180010f7b  call    ZtCopyTrustedServers
0x180010f80  mov     ebx, eax
0x180010f82  test    eax, eax
0x180010f84  jnz     loc_180010E31
0x180010f8a  mov     edx, edi; NumOfElements
0x180010f8c  lea     r9, DnsZtServerSortCompareByPriority; CompareFunction
0x180010f93  mov     r8d, 40h ; '@'; SizeOfElements
0x180010f99  mov     rcx, rbp; Base
0x180010f9c  call    cs:__imp_qsort
0x180010fa2  mov     r8, [rsp+0C8h+var_58]
0x180010fa7  lea     r11, cs:180000000h
0x180010fae  mov     r10, [rsp+0C8h+var_50]
0x180010fb3  mov     rax, rva g_pDnsZtServers[r11+r12*8]
0x180010fbb  mov     ecx, rva g_cDnsZtServers[r11+r12*4]
0x180010fc3  test    r8, r8
0x180010fc6  jz      short loc_180010FD2
0x180010fc8  mov     [r8], rax
0x180010fcb  xor     eax, eax
0x180010fcd  mov     [r10], ecx
0x180010fd0  xor     ecx, ecx
0x180010fd2  mov     rva g_pDnsZtServers[r11+r12*8], rbp
0x180010fda  xor     ebp, ebp
0x180010fdc  mov     rva g_cDnsZtServers[r11+r12*4], edi
0x180010fe4  xor     edi, edi
0x180010fe6  jmp     loc_180010D16
0x180010feb  mov     r9d, 57h ; 'W'
0x180010ff1  mov     ebx, r9d
0x180010ff4  test    byte ptr cs:xmmword_18001F260+1, 8
0x180010ffb  jz      loc_180010D11
0x180011001  lea     edx, [r9-43h]
0x180011005  jmp     loc_180010D00
0x18001100a  call    cs:__imp_DnsFreeZtTrustedServers
0x180011010  mov     rdx, r14
0x180011013  mov     ecx, r13d
0x180011016  call    cs:__imp_DnsFreeZtTrustedServers
0x18001101c  mov     rdx, rbp
0x18001101f  mov     ecx, edi
0x180011021  call    cs:__imp_DnsFreeZtTrustedServers
0x180011027  test    byte ptr cs:xmmword_18001F260+1, 8
0x18001102e  jz      short loc_180011049
0x180011030  mov     edx, 18h
0x180011035  lea     r8, WPP_cbd6223456ee357e6d251c3ed41b29e6_Traceguids
0x18001103c  mov     ecx, 40Bh
0x180011041  mov     r9d, ebx
0x180011044  call    WPP_SF_d
0x180011049  mov     eax, ebx
0x18001104b  mov     rcx, [rsp+0C8h+var_40]
0x180011053  xor     rcx, rsp; StackCookie
0x180011056  call    __security_check_cookie
0x18001105b  mov     rbx, [rsp+0C8h+arg_18]
0x180011063  add     rsp, 90h
0x18001106a  pop     r15
0x18001106c  pop     r14
0x18001106e  pop     r13
0x180011070  pop     r12
0x180011072  pop     rdi
0x180011073  pop     rsi
0x180011074  pop     rbp
0x180011075  retn
```
