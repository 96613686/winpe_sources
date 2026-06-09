# MSCryptKDF_TLS_PRF

- ea: `0x18007ef00`
- end: `0x18007f121`
- name: `MSCryptKDF_TLS_PRF`
- size: `545`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180012a80`
- `0x18007ef00`
- `0x18007f21c`

## string_xrefs

- `0x18007f0fa`: `onecore\ds\security\cryptoapi\ncrypt\kdf\tls1.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDF_TLS_PRF(__int64 a1, unsigned int a2, int a3, __int64 a4, __int64 a5, int a6, _DWORD *a7)
{
  unsigned int v7; // r15d
  __int64 v10; // r9
  int ParameterList; // eax
  __int64 v12; // rcx
  __int64 v13; // rdi
  int v14; // eax
  __int64 v15; // r11
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rdi
  int v19; // r13d
  unsigned __int64 v20; // rax
  __int64 v21; // rdx
  void *v22; // rdi
  void *Src; // r12
  int v24; // eax
  __int64 v25; // r11
  char *v26; // rbx
  int v27; // eax
  __int16 v28; // dx
  __int64 v29; // r11
  __int64 v30; // rbx
  __int64 v31; // rax
  unsigned int v32; // ecx
  __int64 v33; // rcx
  int v34; // eax
  unsigned int v35; // ebx
  __int64 v36; // rcx
  size_t Size; // [rsp+28h] [rbp-70h]
  size_t v39; // [rsp+38h] [rbp-60h]
  int v40; // [rsp+A0h] [rbp+8h]

  v7 = 0;
  if ( !a1 || !a2 )
  {
    v10 = 1022;
    goto LABEL_31;
  }
  if ( a3 != 196610 && (unsigned int)(a3 - 196615) > 3 )
  {
    v10 = 1035;
LABEL_31:
    v36 = 3221225485LL;
    v35 = -1073741811;
    goto LABEL_32;
  }
  if ( a5 && a6 )
  {
    ParameterList = QueryParameterList(a4, 5, 0);
    if ( ParameterList < 0 )
    {
      v10 = 1055;
      goto LABEL_31;
    }
    v13 = ParameterList;
    v14 = QueryParameterList(v12, 4, 0);
    v16 = v14;
    if ( v14 < 0 )
    {
      v10 = 1071;
      goto LABEL_31;
    }
    if ( a6 != 48
      || (v17 = *(_QWORD *)(v15 + 8),
          v18 = 2 * v13,
          v19 = *(_DWORD *)(v17 + 8 * v18),
          v20 = (unsigned int)(v19 - 32),
          (unsigned int)v20 > 0x20)
      || (v21 = 0x100010011LL, !_bittest64(&v21, v20)) )
    {
      v10 = 1089;
      goto LABEL_31;
    }
    v22 = *(void **)(v17 + 8 * v18 + 8);
    Src = *(void **)(v17 + 16 * v16 + 8);
    v40 = *(_DWORD *)(v17 + 16 * v16);
    v24 = QueryParameterList(v15, 7, 0);
    if ( v24 >= 0 )
    {
      if ( *(_DWORD *)(v17 + 16LL * v24) != 4 )
      {
        v10 = 1102;
        goto LABEL_31;
      }
      _mm_lfence();
      v7 = **(_DWORD **)(*(_QWORD *)(v25 + 8) + 16LL * v24 + 8);
    }
    v26 = 0;
    v27 = QueryParameterList(v25, 0, 0);
    if ( v27 >= 0 )
    {
      _mm_lfence();
      v30 = *(_QWORD *)(v29 + 8);
      v31 = 2LL * v27;
      v32 = *(_DWORD *)(v30 + 8 * v31);
      if ( v32 < 2 )
      {
LABEL_24:
        v10 = 1123;
        goto LABEL_31;
      }
      v26 = *(char **)(v30 + 8 * v31 + 8);
      LODWORD(v33) = v32 >> 1;
      while ( 1 )
      {
        v33 = (unsigned int)(v33 - 1);
        if ( *(_WORD *)&v26[2 * v33] == v28 )
          break;
        if ( !(_DWORD)v33 )
          goto LABEL_24;
      }
    }
    LODWORD(v39) = v19;
    LODWORD(Size) = v40;
    v34 = PRF(v7, v26, a1, a2, Src, Size, v22, v39, a5, 0x30u);
    v35 = v34;
    if ( v34 < 0 )
    {
      v10 = 1154;
      v36 = (unsigned int)v34;
LABEL_32:
      DebugTraceError(v36, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\tls1.c", v10);
      return v35;
    }
    *a7 = 48;
  }
  else
  {
    v35 = 0;
    *a7 = 48;
  }
  return v35;
}

```

## disassembly

```asm
0x18007ef00  push    rbx
0x18007ef02  push    rbp
0x18007ef03  push    rsi
0x18007ef04  push    rdi
0x18007ef05  push    r12
0x18007ef07  push    r13
0x18007ef09  push    r14
0x18007ef0b  push    r15
0x18007ef0d  sub     rsp, 58h
0x18007ef11  xor     r15d, r15d
0x18007ef14  mov     r11, r9
0x18007ef17  mov     ebp, edx
0x18007ef19  mov     r14, rcx
0x18007ef1c  test    rcx, rcx
0x18007ef1f  jz      loc_18007F0EA
0x18007ef25  test    edx, edx
0x18007ef27  jz      loc_18007F0EA
0x18007ef2d  cmp     r8d, 30002h
0x18007ef34  jz      short loc_18007EF4D
0x18007ef36  lea     eax, [r8-30007h]
0x18007ef3d  cmp     eax, 3
0x18007ef40  jbe     short loc_18007EF4D
0x18007ef42  mov     r9d, 40Bh
0x18007ef48  jmp     loc_18007F0F0
0x18007ef4d  mov     rsi, [rsp+98h+arg_20]
0x18007ef55  test    rsi, rsi
0x18007ef58  jz      loc_18007F0D7
0x18007ef5e  mov     ebx, [rsp+98h+arg_28]
0x18007ef65  test    ebx, ebx
0x18007ef67  jz      loc_18007F0D7
0x18007ef6d  xor     r8d, r8d
0x18007ef70  mov     rcx, r11
0x18007ef73  lea     edx, [r8+5]
0x18007ef77  call    QueryParameterList
0x18007ef7c  test    eax, eax
0x18007ef7e  jns     short loc_18007EF8B
0x18007ef80  mov     r9d, 41Fh
0x18007ef86  jmp     loc_18007F0F0
0x18007ef8b  xor     r8d, r8d
0x18007ef8e  movsxd  rdi, eax
0x18007ef91  lea     edx, [r8+4]
0x18007ef95  call    QueryParameterList
0x18007ef9a  movsxd  rcx, eax
0x18007ef9d  test    eax, eax
0x18007ef9f  jns     short loc_18007EFAC
0x18007efa1  mov     r9d, 42Fh
0x18007efa7  jmp     loc_18007F0F0
0x18007efac  cmp     ebx, 30h ; '0'
0x18007efaf  jnz     loc_18007F0CF
0x18007efb5  mov     rbx, [r11+8]
0x18007efb9  add     rdi, rdi
0x18007efbc  mov     r13d, [rbx+rdi*8]
0x18007efc0  lea     eax, [r13-20h]
0x18007efc4  cmp     eax, 20h ; ' '
0x18007efc7  ja      loc_18007F0CF
0x18007efcd  mov     rdx, 100010011h
0x18007efd7  bt      rdx, rax
0x18007efdb  jnb     loc_18007F0CF
0x18007efe1  mov     rdi, [rbx+rdi*8+8]
0x18007efe6  mov     rax, rcx
0x18007efe9  add     rax, rax
0x18007efec  xor     r8d, r8d
0x18007efef  mov     rcx, r11
0x18007eff2  mov     r12, [rbx+rax*8+8]
0x18007eff7  lea     edx, [r8+7]
0x18007effb  mov     eax, [rbx+rax*8]
0x18007effe  mov     dword ptr [rsp+98h+arg_0], eax
0x18007f005  call    QueryParameterList
0x18007f00a  xor     edx, edx
0x18007f00c  test    eax, eax
0x18007f00e  js      short loc_18007F036
0x18007f010  movsxd  rcx, eax
0x18007f013  add     rcx, rcx
0x18007f016  cmp     dword ptr [rbx+rcx*8], 4
0x18007f01a  jz      short loc_18007F027
0x18007f01c  mov     r9d, 44Eh
0x18007f022  jmp     loc_18007F0F0
0x18007f027  lfence
0x18007f02a  mov     rax, [r11+8]
0x18007f02e  mov     rcx, [rax+rcx*8+8]
0x18007f033  mov     r15d, [rcx]
0x18007f036  xor     r8d, r8d
0x18007f039  mov     rcx, r11
0x18007f03c  mov     rbx, rdx
0x18007f03f  call    QueryParameterList
0x18007f044  test    eax, eax
0x18007f046  js      short loc_18007F077
0x18007f048  lfence
0x18007f04b  mov     rbx, [r11+8]
0x18007f04f  cdqe
0x18007f051  add     rax, rax
0x18007f054  mov     ecx, [rbx+rax*8]
0x18007f057  cmp     ecx, 2
0x18007f05a  jb      short loc_18007F06F
0x18007f05c  mov     rbx, [rbx+rax*8+8]
0x18007f061  shr     ecx, 1
0x18007f063  dec     ecx
0x18007f065  cmp     [rbx+rcx*2], dx
0x18007f069  jz      short loc_18007F077
0x18007f06b  test    ecx, ecx
0x18007f06d  jnz     short loc_18007F063
0x18007f06f  mov     r9d, 463h
0x18007f075  jmp     short loc_18007F0F0
0x18007f077  mov     eax, dword ptr [rsp+98h+arg_0]
0x18007f07e  mov     r9d, ebp; int
0x18007f081  mov     [rsp+98h+var_50], 30h ; '0'; int
0x18007f089  mov     r8, r14; int
0x18007f08c  mov     [rsp+98h+var_58], rsi; __int64
0x18007f091  mov     rdx, rbx; int
0x18007f094  mov     dword ptr [rsp+98h+var_60], r13d; size_t
0x18007f099  mov     ecx, r15d; int
0x18007f09c  mov     [rsp+98h+var_68], rdi; void *
0x18007f0a1  mov     dword ptr [rsp+98h+Size], eax; Size
0x18007f0a5  mov     [rsp+98h+Src], r12; Src
0x18007f0aa  call    PRF
0x18007f0af  mov     ebx, eax
0x18007f0b1  test    eax, eax
0x18007f0b3  jns     short loc_18007F0BF
0x18007f0b5  mov     r9d, 482h
0x18007f0bb  mov     ecx, eax
0x18007f0bd  jmp     short loc_18007F0FA
0x18007f0bf  mov     rax, [rsp+98h+arg_30]
0x18007f0c7  mov     dword ptr [rax], 30h ; '0'
0x18007f0cd  jmp     short loc_18007F10D
0x18007f0cf  mov     r9d, 441h
0x18007f0d5  jmp     short loc_18007F0F0
0x18007f0d7  mov     rax, [rsp+98h+arg_30]
0x18007f0df  mov     ebx, r15d
0x18007f0e2  mov     dword ptr [rax], 30h ; '0'
0x18007f0e8  jmp     short loc_18007F10D
0x18007f0ea  mov     r9d, 3FEh
0x18007f0f0  mov     ecx, 0C000000Dh
0x18007f0f5  mov     ebx, 0C000000Dh
0x18007f0fa  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18007f101  lea     rdx, aStatus; "Status"
0x18007f108  call    DebugTraceError
0x18007f10d  mov     eax, ebx
0x18007f10f  add     rsp, 58h
0x18007f113  pop     r15
0x18007f115  pop     r14
0x18007f117  pop     r13
0x18007f119  pop     r12
0x18007f11b  pop     rdi
0x18007f11c  pop     rsi
0x18007f11d  pop     rbp
0x18007f11e  pop     rbx
0x18007f11f  retn
```
