# ZtValidateTrustedServerConfigInfo

- ea: `0x180006bcc`
- end: `0x180006d80`
- name: `ZtValidateTrustedServerConfigInfo`
- size: `436`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800072b0`

## callees

- `0x180006bcc`
- `0x18000f470`
- `0x180012614`
- `0x180015008`
- `0x180015094`

## import_xrefs

- `DNSAPI!DnsValidateName_W` at `0x180006c44`
- `DNSAPI!DnsValidateName_W` at `0x180006c44`

## pseudocode

```c
__int64 __fastcall ZtValidateTrustedServerConfigInfo(__int64 a1)
{
  unsigned int v2; // ebx
  USHORT v3; // dx
  const WCHAR *v4; // rcx
  unsigned int v5; // eax
  int v6; // r9d
  const WCHAR *v7; // rdx
  __int16 *v8; // rbx
  __int16 v9; // ax
  __int64 v10; // xmm0_8
  _OWORD v12[4]; // [rsp+20h] [rbp-48h] BYREF

  memset(v12, 0, 24);
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_q(1026, 0x17u, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, a1, v12[0], *(_QWORD *)&v12[1]);
  if ( *(_DWORD *)(a1 + 48) == 1 )
  {
    v7 = *(const WCHAR **)(a1 + 56);
    if ( !v7 )
    {
      v2 = 87;
      if ( (xmmword_18001F260 & 4) == 0 )
        return v2;
      v3 = 24;
LABEL_29:
      v6 = 87;
      goto LABEL_30;
    }
    memset(v12, 0, 24);
    v8 = (__int16 *)(a1 + 16);
    if ( v8 )
    {
      v9 = *v8;
      LOWORD(v12[0]) = v9;
      if ( v9 == 2 )
      {
        DWORD2(v12[0]) = *((_DWORD *)v8 + 1);
      }
      else
      {
        if ( v9 != 23 )
        {
          if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
            WPP_SF_d(1035, 0xFu, (ULONGLONG)WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids, 87);
          goto LABEL_21;
        }
        v10 = *(_QWORD *)(v8 + 6);
        DWORD2(v12[0]) = *((_DWORD *)v8 + 2);
        DWORD1(v12[1]) = *((_DWORD *)v8 + 5);
        *(_QWORD *)((char *)v12 + 12) = v10;
      }
      v5 = ValidateDohUriTemplate(v12, v7);
      v2 = v5;
      if ( !v5 )
        goto LABEL_31;
      if ( (xmmword_18001F260 & 4) == 0 )
        return v2;
      v3 = 25;
      goto LABEL_14;
    }
LABEL_21:
    v2 = 87;
    goto LABEL_31;
  }
  if ( *(_DWORD *)(a1 + 48) != 2 )
  {
    v2 = 87;
    if ( (xmmword_18001F260 & 4) == 0 )
      return v2;
    v3 = 28;
    goto LABEL_29;
  }
  v4 = *(const WCHAR **)(a1 + 56);
  if ( v4 && DnsValidateName_W(v4, DnsNameDomain) )
  {
    v2 = 87;
    if ( (xmmword_18001F260 & 4) == 0 )
      return v2;
    v3 = 26;
    goto LABEL_29;
  }
  v5 = DnsValidateDotPort(*(unsigned __int16 *)(a1 + 44));
  v2 = v5;
  if ( !v5 )
    goto LABEL_31;
  if ( (xmmword_18001F260 & 4) == 0 )
    return v2;
  v3 = 27;
LABEL_14:
  v6 = v5;
LABEL_30:
  WPP_SF_d(1026, v3, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v6);
LABEL_31:
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 0x1Du, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180006bcc  push    rbx
0x180006bce  push    rbp
0x180006bcf  push    r14
0x180006bd1  push    r15
0x180006bd3  sub     rsp, 48h
0x180006bd7  xorps   xmm0, xmm0
0x180006bda  xor     eax, eax
0x180006bdc  movups  [rsp+68h+var_48], xmm0
0x180006be1  mov     [rsp+68h+var_38], rax
0x180006be6  mov     rbx, rcx
0x180006be9  test    byte ptr cs:xmmword_18001F260, 4
0x180006bf0  lea     r15d, [rax+17h]
0x180006bf4  mov     ebp, 402h
0x180006bf9  lea     r14, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x180006c00  jz      short loc_180006C12
0x180006c02  mov     edx, r15d
0x180006c05  mov     ecx, ebp
0x180006c07  mov     r9, rbx
0x180006c0a  mov     r8, r14
0x180006c0d  call    WPP_SF_q
0x180006c12  mov     ecx, [rbx+30h]
0x180006c15  sub     ecx, 1
0x180006c18  jz      short loc_180006C95
0x180006c1a  cmp     ecx, 1
0x180006c1d  jz      short loc_180006C39
0x180006c1f  mov     ebx, 57h ; 'W'
0x180006c24  test    byte ptr cs:xmmword_18001F260, 4
0x180006c2b  jz      loc_180006D73
0x180006c31  lea     edx, [rbx-3Bh]
0x180006c34  jmp     loc_180006D4B
0x180006c39  mov     rcx, [rbx+38h]; pszName
0x180006c3d  test    rcx, rcx
0x180006c40  jz      short loc_180006C68
0x180006c42  xor     edx, edx; Format
0x180006c44  call    cs:__imp_DnsValidateName_W
0x180006c4a  test    eax, eax
0x180006c4c  jz      short loc_180006C68
0x180006c4e  mov     ebx, 57h ; 'W'
0x180006c53  test    byte ptr cs:xmmword_18001F260, 4
0x180006c5a  jz      loc_180006D73
0x180006c60  lea     edx, [rbx-3Dh]
0x180006c63  jmp     loc_180006D4B
0x180006c68  movzx   ecx, word ptr [rbx+2Ch]
0x180006c6c  call    DnsValidateDotPort
0x180006c71  mov     ebx, eax
0x180006c73  test    eax, eax
0x180006c75  jz      loc_180006D58
0x180006c7b  test    byte ptr cs:xmmword_18001F260, 4
0x180006c82  jz      loc_180006D73
0x180006c88  mov     edx, 1Bh
0x180006c8d  mov     r9d, eax
0x180006c90  jmp     loc_180006D4E
0x180006c95  mov     rdx, [rbx+38h]
0x180006c99  test    rdx, rdx
0x180006c9c  jz      loc_180006D3A
0x180006ca2  xor     eax, eax
0x180006ca4  xorps   xmm0, xmm0
0x180006ca7  mov     [rsp+68h+var_38], rax
0x180006cac  movups  [rsp+68h+var_48], xmm0
0x180006cb1  add     rbx, 10h
0x180006cb5  jz      short loc_180006CEE
0x180006cb7  movzx   eax, word ptr [rbx]
0x180006cba  mov     word ptr [rsp+68h+var_48], ax
0x180006cbf  cmp     ax, 2
0x180006cc3  jz      short loc_180006D10
0x180006cc5  cmp     ax, r15w
0x180006cc9  jz      short loc_180006CF5
0x180006ccb  test    byte ptr cs:xmmword_18001F260+1, 8
0x180006cd2  jz      short loc_180006CEE
0x180006cd4  mov     edx, 0Fh
0x180006cd9  lea     r8, WPP_40375b7da6503ec0d2901a6efbf6c2e2_Traceguids
0x180006ce0  mov     ecx, 40Bh
0x180006ce5  lea     r9d, [rdx+48h]
0x180006ce9  call    WPP_SF_d
0x180006cee  mov     ebx, 57h ; 'W'
0x180006cf3  jmp     short loc_180006D58
0x180006cf5  mov     eax, [rbx+8]
0x180006cf8  movsd   xmm0, qword ptr [rbx+0Ch]
0x180006cfd  mov     dword ptr [rsp+68h+var_48+8], eax
0x180006d01  mov     eax, [rbx+14h]
0x180006d04  mov     dword ptr [rsp+68h+var_38+4], eax
0x180006d08  movsd   qword ptr [rsp+68h+var_48+0Ch], xmm0
0x180006d0e  jmp     short loc_180006D17
0x180006d10  mov     eax, [rbx+4]
0x180006d13  mov     dword ptr [rsp+68h+var_48+8], eax
0x180006d17  lea     rcx, [rsp+68h+var_48]
0x180006d1c  call    ValidateDohUriTemplate
0x180006d21  mov     ebx, eax
0x180006d23  test    eax, eax
0x180006d25  jz      short loc_180006D58
0x180006d27  test    byte ptr cs:xmmword_18001F260, 4
0x180006d2e  jz      short loc_180006D73
0x180006d30  mov     edx, 19h
0x180006d35  jmp     loc_180006C8D
0x180006d3a  mov     ebx, 57h ; 'W'
0x180006d3f  test    byte ptr cs:xmmword_18001F260, 4
0x180006d46  jz      short loc_180006D73
0x180006d48  lea     edx, [rbx-3Fh]
0x180006d4b  mov     r9d, ebx
0x180006d4e  mov     r8, r14
0x180006d51  mov     ecx, ebp
0x180006d53  call    WPP_SF_d
0x180006d58  test    byte ptr cs:xmmword_18001F260, 4
0x180006d5f  jz      short loc_180006D73
0x180006d61  mov     edx, 1Dh
0x180006d66  mov     ecx, ebp
0x180006d68  mov     r9d, ebx
0x180006d6b  mov     r8, r14
0x180006d6e  call    WPP_SF_d
0x180006d73  mov     eax, ebx
0x180006d75  add     rsp, 48h
0x180006d79  pop     r15
0x180006d7b  pop     r14
0x180006d7d  pop     rbp
0x180006d7e  pop     rbx
0x180006d7f  retn
```
