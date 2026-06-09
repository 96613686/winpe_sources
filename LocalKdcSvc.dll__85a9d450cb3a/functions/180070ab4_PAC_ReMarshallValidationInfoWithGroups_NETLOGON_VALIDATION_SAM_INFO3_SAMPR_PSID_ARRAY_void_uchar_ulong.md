# PAC_ReMarshallValidationInfoWithGroups(_NETLOGON_VALIDATION_SAM_INFO3 *,_SAMPR_PSID_ARRAY *,void *,uchar * *,ulong *)

- ea: `0x180070ab4`
- end: `0x180070dec`
- name: `?PAC_ReMarshallValidationInfoWithGroups@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAU_SAMPR_PSID_ARRAY@@PEAXPEAPEAEPEAK@Z`
- size: `824`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *, struct _SAMPR_PSID_ARRAY *, void *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18006fcf4`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x18005a060`
- `0x18005a090`
- `0x18006f978`
- `0x180070ab4`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x180070c80`
- `ntdll!RtlEqualSid` at `0x180070c80`

## pseudocode

```c
__int64 __fastcall PAC_ReMarshallValidationInfoWithGroups(
        struct _NETLOGON_VALIDATION_SAM_INFO3 *a1,
        struct _SAMPR_PSID_ARRAY *a2,
        void *a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  struct _NETLOGON_VALIDATION_SAM_INFO3 *v7; // rax
  __int64 v8; // rcx
  _OWORD *v10; // r9
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  int v18; // edx
  unsigned int v19; // r13d
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int64 v22; // rax
  unsigned int v23; // edx
  size_t v24; // rsi
  char *v25; // rax
  char *v26; // rdi
  unsigned int v27; // ebx
  _DWORD *v28; // r14
  unsigned int v29; // ecx
  unsigned int v30; // esi
  __int64 v31; // r8
  __int64 v32; // rax
  _DWORD *v33; // rax
  unsigned int v34; // r15d
  _BYTE *v35; // r12
  __int64 v36; // rdx
  char v37; // al
  __int64 v38; // rdx
  int v39; // eax
  unsigned int v40; // r10d
  __int64 v41; // r8
  __int64 v42; // rax
  unsigned int i; // r11d
  __int64 v44; // r9
  __int64 v45; // rcx
  _BYTE v49[168]; // [rsp+40h] [rbp-C0h] BYREF
  int v50; // [rsp+E8h] [rbp-18h]
  unsigned int v51; // [rsp+150h] [rbp+50h]
  char *v52; // [rsp+158h] [rbp+58h]
  void *v53; // [rsp+160h] [rbp+60h]
  unsigned int v54; // [rsp+168h] [rbp+68h]
  _DWORD *v55; // [rsp+170h] [rbp+70h]

  v7 = a1;
  v8 = 2;
  v10 = v49;
  do
  {
    v11 = *((_OWORD *)v7 + 1);
    *v10 = *(_OWORD *)v7;
    v12 = *((_OWORD *)v7 + 2);
    v10[1] = v11;
    v13 = *((_OWORD *)v7 + 3);
    v10[2] = v12;
    v14 = *((_OWORD *)v7 + 4);
    v10[3] = v13;
    v15 = *((_OWORD *)v7 + 5);
    v10[4] = v14;
    v16 = *((_OWORD *)v7 + 6);
    v10[5] = v15;
    v17 = *((_OWORD *)v7 + 7);
    v7 = (struct _NETLOGON_VALIDATION_SAM_INFO3 *)((char *)v7 + 128);
    v10[6] = v16;
    v10[7] = v17;
    v10 += 8;
    --v8;
  }
  while ( v8 );
  v18 = *(_DWORD *)a2;
  v19 = 0;
  v20 = *((_OWORD *)v7 + 1);
  *v10 = *(_OWORD *)v7;
  v21 = *((_OWORD *)v7 + 2);
  v22 = *((_QWORD *)v7 + 6);
  v10[1] = v20;
  v10[2] = v21;
  *((_QWORD *)v10 + 6) = v22;
  v50 &= ~0x200u;
  v23 = v51 + v18;
  v53 = 0;
  v55 = 0;
  v54 = 0;
  if ( v23 < v51 )
    return (unsigned int)-1073741675;
  v24 = 16LL * v23;
  v25 = (char *)MIDL_user_allocate(v24);
  v26 = v25;
  if ( v25 )
  {
    v28 = 0;
    memset_0(v25, 0, v24);
    if ( !*(_DWORD *)a2 )
      goto LABEL_34;
    v29 = 0;
    if ( a3 )
    {
      v30 = 0;
      if ( *((_DWORD *)a1 + 68) )
      {
        do
        {
          v31 = *((_QWORD *)a1 + 35);
          if ( (*(_DWORD *)(v31 + 16LL * v29 + 8) & 0x20000000) == 0 )
          {
            v32 = 2LL * v30++;
            *(_OWORD *)&v26[8 * v32] = *(_OWORD *)(v31 + 16LL * v29);
          }
          ++v29;
        }
        while ( v29 < *((_DWORD *)a1 + 68) );
      }
      v33 = MIDL_user_allocate(8LL * *(unsigned int *)a2);
      v28 = v33;
      if ( !v33 )
      {
        v27 = -1073741801;
LABEL_36:
        MIDL_user_free(v26);
        return v27;
      }
      v34 = 0;
      memset_0(v33, 0, 8LL * *(unsigned int *)a2);
      if ( !*(_DWORD *)a2 )
        goto LABEL_23;
      do
      {
        v35 = *(_BYTE **)(*((_QWORD *)a2 + 1) + 8LL * v19);
        --v35[1];
        if ( RtlEqualSid(v35, a3) )
        {
          v36 = v34++;
          v37 = 1;
          v28[2 * v36] = *(_DWORD *)&v35[4 * (unsigned __int8)v35[1] + 8];
          v28[2 * v36 + 1] = 536870919;
        }
        else
        {
          v37 = 0;
        }
        ++v35[1];
        if ( !v37 )
        {
          v38 = 2LL * v30++;
          *(_QWORD *)&v26[8 * v38] = *(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL * v19);
          *(_DWORD *)&v26[8 * v38 + 8] = 536870919;
        }
        ++v19;
      }
      while ( v19 < *(_DWORD *)a2 );
      if ( v34 )
      {
        v39 = v50 | 0x200;
        v50 |= 0x200u;
        v53 = a3;
        v55 = v28;
        v54 = v34;
      }
      else
      {
LABEL_23:
        v39 = v50;
      }
      if ( !v30 )
      {
LABEL_34:
        v27 = PAC_EncodeValidationInformation((struct _NETLOGON_VALIDATION_SAM_INFO3 *)v49, a4, a5);
        if ( v28 )
          MIDL_user_free(v28);
        goto LABEL_36;
      }
      v51 = v30;
      v50 = v39 | 0x20;
    }
    else
    {
      v50 |= 0x20u;
      v40 = 0;
      if ( *((_DWORD *)a1 + 68) )
      {
        do
        {
          v41 = *((_QWORD *)a1 + 35);
          if ( (*(_DWORD *)(v41 + 16LL * v29 + 8) & 0x20000000) == 0 )
          {
            v42 = 2LL * v40++;
            *(_OWORD *)&v26[8 * v42] = *(_OWORD *)(v41 + 16LL * v29);
          }
          ++v29;
        }
        while ( v29 < *((_DWORD *)a1 + 68) );
      }
      for ( i = 0; i < *(_DWORD *)a2; *(_DWORD *)&v26[8 * v44 + 8] = 536870919 )
      {
        v44 = v40++;
        v44 *= 2;
        v45 = i++;
        *(_QWORD *)&v26[8 * v44] = *(_QWORD *)(*((_QWORD *)a2 + 1) + 8 * v45);
      }
      v51 = v40;
    }
    v52 = v26;
    goto LABEL_34;
  }
  return (unsigned int)-1073741801;
}

```

## disassembly

```asm
0x180070ab4  push    rbp
0x180070ab6  push    rbx
0x180070ab7  push    rsi
0x180070ab8  push    rdi
0x180070ab9  push    r12
0x180070abb  push    r13
0x180070abd  push    r14
0x180070abf  push    r15
0x180070ac1  lea     rbp, [rsp-98h]
0x180070ac9  sub     rsp, 198h
0x180070ad0  mov     rax, cs:__security_cookie
0x180070ad7  xor     rax, rsp
0x180070ada  mov     [rbp+0D0h+var_50], rax
0x180070ae1  mov     rax, [rbp+0D0h+arg_20]
0x180070ae8  mov     r15, rcx
0x180070aeb  mov     [rsp+1D0h+var_1A0], rax
0x180070af0  mov     rbx, rdx
0x180070af3  mov     rax, rcx
0x180070af6  mov     [rsp+1D0h+var_198], r9
0x180070afb  mov     ecx, 2
0x180070b00  mov     [rsp+1D0h+Sid2], r8
0x180070b05  mov     r12, r8
0x180070b08  lea     r9, [rsp+1D0h+var_190]
0x180070b0d  lea     edx, [rcx+7Eh]
0x180070b10  movups  xmm0, xmmword ptr [rax]
0x180070b13  movups  xmm1, xmmword ptr [rax+10h]
0x180070b17  movups  xmmword ptr [r9], xmm0
0x180070b1b  movups  xmm0, xmmword ptr [rax+20h]
0x180070b1f  movups  xmmword ptr [r9+10h], xmm1
0x180070b24  movups  xmm1, xmmword ptr [rax+30h]
0x180070b28  movups  xmmword ptr [r9+20h], xmm0
0x180070b2d  movups  xmm0, xmmword ptr [rax+40h]
0x180070b31  movups  xmmword ptr [r9+30h], xmm1
0x180070b36  movups  xmm1, xmmword ptr [rax+50h]
0x180070b3a  movups  xmmword ptr [r9+40h], xmm0
0x180070b3f  movups  xmm0, xmmword ptr [rax+60h]
0x180070b43  movups  xmmword ptr [r9+50h], xmm1
0x180070b48  movups  xmm1, xmmword ptr [rax+70h]
0x180070b4c  add     rax, rdx
0x180070b4f  movups  xmmword ptr [r9+60h], xmm0
0x180070b54  movups  xmmword ptr [r9+70h], xmm1
0x180070b59  add     r9, rdx
0x180070b5c  sub     rcx, 1
0x180070b60  jnz     short loc_180070B10
0x180070b62  movups  xmm0, xmmword ptr [rax]
0x180070b65  mov     edx, [rbx]
0x180070b67  xor     r13d, r13d
0x180070b6a  movups  xmm1, xmmword ptr [rax+10h]
0x180070b6e  movups  xmmword ptr [r9], xmm0
0x180070b72  movups  xmm0, xmmword ptr [rax+20h]
0x180070b76  mov     rax, [rax+30h]
0x180070b7a  movups  xmmword ptr [r9+10h], xmm1
0x180070b7f  movups  xmmword ptr [r9+20h], xmm0
0x180070b84  mov     [r9+30h], rax
0x180070b88  btr     [rbp+0D0h+var_E8], 9
0x180070b8d  add     edx, [rbp+0D0h+var_80]
0x180070b90  mov     [rbp+0D0h+var_70], r13
0x180070b94  mov     [rbp+0D0h+var_60], r13
0x180070b98  mov     [rbp+0D0h+var_68], r13d
0x180070b9c  cmp     edx, [rbp+0D0h+var_80]
0x180070b9f  jb      loc_180070DC2
0x180070ba5  mov     esi, edx
0x180070ba7  shl     rsi, 4
0x180070bab  mov     rcx, rsi; size
0x180070bae  call    MIDL_user_allocate
0x180070bb3  mov     rdi, rax
0x180070bb6  test    rax, rax
0x180070bb9  jnz     short loc_180070BC5
0x180070bbb  mov     ebx, 0C0000017h
0x180070bc0  jmp     loc_180070DC7
0x180070bc5  mov     r8, rsi; Size
0x180070bc8  xor     edx, edx; Val
0x180070bca  mov     rcx, rdi; void *
0x180070bcd  mov     r14, r13
0x180070bd0  call    memset_0
0x180070bd5  cmp     [rbx], r13d
0x180070bd8  jz      loc_180070D95
0x180070bde  mov     ecx, r13d
0x180070be1  test    r12, r12
0x180070be4  jz      loc_180070D17
0x180070bea  mov     esi, r13d
0x180070bed  cmp     [r15+110h], r13d
0x180070bf4  jbe     short loc_180070C29
0x180070bf6  mov     r8, [r15+118h]
0x180070bfd  mov     edx, ecx
0x180070bff  add     rdx, rdx
0x180070c02  test    dword ptr [r8+rdx*8+8], 20000000h
0x180070c0b  jnz     short loc_180070C1E
0x180070c0d  movups  xmm0, xmmword ptr [r8+rdx*8]
0x180070c12  mov     eax, esi
0x180070c14  add     rax, rax
0x180070c17  inc     esi
0x180070c19  movdqu  xmmword ptr [rdi+rax*8], xmm0
0x180070c1e  inc     ecx
0x180070c20  cmp     ecx, [r15+110h]
0x180070c27  jb      short loc_180070BF6
0x180070c29  mov     ecx, [rbx]
0x180070c2b  shl     rcx, 3; size
0x180070c2f  call    MIDL_user_allocate
0x180070c34  mov     r14, rax
0x180070c37  test    rax, rax
0x180070c3a  jnz     short loc_180070C46
0x180070c3c  mov     ebx, 0C0000017h
0x180070c41  jmp     loc_180070DB8
0x180070c46  mov     r8d, [rbx]
0x180070c49  xor     edx, edx; Val
0x180070c4b  shl     r8, 3; Size
0x180070c4f  mov     rcx, r14; void *
0x180070c52  mov     r15d, r13d
0x180070c55  call    memset_0
0x180070c5a  cmp     [rbx], r13d
0x180070c5d  jbe     loc_180070D01
0x180070c63  mov     rax, [rbx+8]
0x180070c67  mov     rdx, [rsp+1D0h+Sid2]; Sid2
0x180070c6c  mov     ecx, r13d
0x180070c6f  mov     [rsp+1D0h+var_1B0], 0
0x180070c74  mov     r12, [rax+rcx*8]
0x180070c78  mov     rcx, r12; Sid1
0x180070c7b  dec     byte ptr [r12+1]
0x180070c80  call    cs:__imp_RtlEqualSid
0x180070c86  test    al, al
0x180070c88  jz      short loc_180070CAC
0x180070c8a  movzx   eax, byte ptr [r12+1]
0x180070c90  mov     edx, r15d
0x180070c93  inc     r15d
0x180070c96  mov     ecx, [r12+rax*4+8]
0x180070c9b  mov     al, 1
0x180070c9d  mov     [r14+rdx*8], ecx
0x180070ca1  mov     dword ptr [r14+rdx*8+4], 20000007h
0x180070caa  jmp     short loc_180070CB0
0x180070cac  mov     al, [rsp+1D0h+var_1B0]
0x180070cb0  inc     byte ptr [r12+1]
0x180070cb5  test    al, al
0x180070cb7  jnz     short loc_180070CD7
0x180070cb9  mov     rax, [rbx+8]
0x180070cbd  mov     edx, esi
0x180070cbf  add     rdx, rdx
0x180070cc2  mov     ecx, r13d
0x180070cc5  inc     esi
0x180070cc7  mov     rcx, [rax+rcx*8]
0x180070ccb  mov     [rdi+rdx*8], rcx
0x180070ccf  mov     dword ptr [rdi+rdx*8+8], 20000007h
0x180070cd7  inc     r13d
0x180070cda  cmp     r13d, [rbx]
0x180070cdd  jb      short loc_180070C63
0x180070cdf  test    r15d, r15d
0x180070ce2  jz      short loc_180070D01
0x180070ce4  mov     eax, [rbp+0D0h+var_E8]
0x180070ce7  mov     rcx, [rsp+1D0h+Sid2]
0x180070cec  bts     eax, 9
0x180070cf0  mov     [rbp+0D0h+var_E8], eax
0x180070cf3  mov     [rbp+0D0h+var_70], rcx
0x180070cf7  mov     [rbp+0D0h+var_60], r14
0x180070cfb  mov     [rbp+0D0h+var_68], r15d
0x180070cff  jmp     short loc_180070D04
0x180070d01  mov     eax, [rbp+0D0h+var_E8]
0x180070d04  test    esi, esi
0x180070d06  jz      loc_180070D95
0x180070d0c  or      eax, 20h
0x180070d0f  mov     [rbp+0D0h+var_80], esi
0x180070d12  mov     [rbp+0D0h+var_E8], eax
0x180070d15  jmp     short loc_180070D91
0x180070d17  or      [rbp+0D0h+var_E8], 20h
0x180070d1b  mov     r10d, r13d
0x180070d1e  cmp     [r15+110h], r13d
0x180070d25  jbe     short loc_180070D5C
0x180070d27  mov     r8, [r15+118h]
0x180070d2e  mov     edx, ecx
0x180070d30  add     rdx, rdx
0x180070d33  test    dword ptr [r8+rdx*8+8], 20000000h
0x180070d3c  jnz     short loc_180070D51
0x180070d3e  movups  xmm0, xmmword ptr [r8+rdx*8]
0x180070d43  mov     eax, r10d
0x180070d46  add     rax, rax
0x180070d49  inc     r10d
0x180070d4c  movdqu  xmmword ptr [rdi+rax*8], xmm0
0x180070d51  inc     ecx
0x180070d53  cmp     ecx, [r15+110h]
0x180070d5a  jb      short loc_180070D27
0x180070d5c  mov     r11d, r13d
0x180070d5f  cmp     [rbx], r13d
0x180070d62  jbe     short loc_180070D8D
0x180070d64  mov     rax, [rbx+8]
0x180070d68  mov     r9d, r10d
0x180070d6b  inc     r10d
0x180070d6e  add     r9, r9
0x180070d71  mov     ecx, r11d
0x180070d74  inc     r11d
0x180070d77  mov     rcx, [rax+rcx*8]
0x180070d7b  mov     [rdi+r9*8], rcx
0x180070d7f  mov     dword ptr [rdi+r9*8+8], 20000007h
0x180070d88  cmp     r11d, [rbx]
0x180070d8b  jb      short loc_180070D64
0x180070d8d  mov     [rbp+0D0h+var_80], r10d
0x180070d91  mov     [rbp+0D0h+var_78], rdi
0x180070d95  mov     r8, [rsp+1D0h+var_1A0]; unsigned int *
0x180070d9a  lea     rcx, [rsp+1D0h+var_190]; struct _NETLOGON_VALIDATION_SAM_INFO3 *
0x180070d9f  mov     rdx, [rsp+1D0h+var_198]; unsigned __int8 **
0x180070da4  call    ?PAC_EncodeValidationInformation@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO3@@PEAPEAEPEAK@Z; PAC_EncodeValidationInformation(_NETLOGON_VALIDATION_SAM_INFO3 *,uchar * *,ulong *)
0x180070da9  mov     ebx, eax
0x180070dab  test    r14, r14
0x180070dae  jz      short loc_180070DB8
0x180070db0  mov     rcx, r14; void *
0x180070db3  call    MIDL_user_free
0x180070db8  mov     rcx, rdi; void *
0x180070dbb  call    MIDL_user_free
0x180070dc0  jmp     short loc_180070DC7
0x180070dc2  mov     ebx, 0C0000095h
0x180070dc7  mov     eax, ebx
0x180070dc9  mov     rcx, [rbp+0D0h+var_50]
0x180070dd0  xor     rcx, rsp; StackCookie
0x180070dd3  call    __security_check_cookie
0x180070dd8  add     rsp, 198h
0x180070ddf  pop     r15
0x180070de1  pop     r14
0x180070de3  pop     r13
0x180070de5  pop     r12
0x180070de7  pop     rdi
0x180070de8  pop     rsi
0x180070de9  pop     rbx
0x180070dea  pop     rbp
0x180070deb  retn
```
