# WriteCharstrings

- ea: `0x18004a4f4`
- end: `0x18004a93c`
- name: `WriteCharstrings`
- size: `1096`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18004a4f4`
- `0x18004bb20`
- `0x18004c9d8`

## callees

- `0x180001ee0`
- `0x1800468bc`
- `0x180048774`
- `0x1800492ec`
- `0x180049e14`
- `0x180049e54`
- `0x180049e98`
- `0x18004a4f4`
- `0x18004e048`
- `0x18004e628`
- `0x18004ebec`
- `0x18005d010`

## pseudocode

```c
int __fastcall WriteCharstrings(__int64 a1, int a2, int a3, unsigned int *a4, __int64 a5, _DWORD *a6)
{
  unsigned int *v6; // rdi
  int v7; // r14d
  int v8; // r9d
  int v10; // r8d
  __int64 v11; // rax
  int v12; // r13d
  _DWORD *v13; // rbp
  unsigned int v14; // edi
  char v15; // r15
  __int64 v16; // rsi
  int v17; // edx
  bool v18; // zf
  __int64 v19; // rdx
  int v20; // edx
  unsigned int v21; // ecx
  __int64 v22; // r8
  int v23; // edx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rbp
  __int64 v27; // rdi
  unsigned __int16 v28; // di
  __int64 v29; // rbp
  __int64 v30; // rcx
  unsigned __int16 v31; // di
  int SeacGlyphID; // eax
  int v33; // ecx
  char v35; // [rsp+30h] [rbp-A8h]
  int v36; // [rsp+34h] [rbp-A4h]
  int v38; // [rsp+3Ch] [rbp-9Ch]
  unsigned __int16 v39; // [rsp+40h] [rbp-98h]
  unsigned int *v40; // [rsp+48h] [rbp-90h]
  _DWORD v41[2]; // [rsp+50h] [rbp-88h] BYREF
  __int64 v42; // [rsp+58h] [rbp-80h]
  _OWORD v43[3]; // [rsp+60h] [rbp-78h] BYREF
  __int16 v44; // [rsp+90h] [rbp-48h]

  v42 = a5;
  v6 = a4;
  v40 = a4;
  v38 = a3;
  v7 = a3;
  v8 = a2;
  v36 = 0;
  v10 = 0;
  memset(v43, 0, sizeof(v43));
  v44 = 0;
  v35 = *(_BYTE *)(a1 + 7988);
  if ( a6 && !a2 )
    *a6 = 0;
  if ( v7 == -1 )
  {
    v7 = *(_DWORD *)(a1 + 7908);
    v10 = 1;
    v38 = v7;
    v36 = 1;
  }
  LODWORD(v11) = *(unsigned __int16 *)(a1 + 7976);
  if ( (_WORD)v11 == 0xFFFF )
    v39 = 0;
  else
    v39 = *(_WORD *)(a1 + 7976);
  v12 = 0;
  if ( v7 > 0 )
  {
    v13 = (_DWORD *)(a1 + 7908);
    while ( 1 )
    {
      if ( v10 )
        v14 = v12;
      else
        v14 = *v6;
      if ( (signed int)v14 > *v13 )
        XCF_FatalErrorHandler(a1, 33);
      v15 = v14 & 7;
      v16 = (__int64)(int)v14 >> 3;
      v17 = 1 << (v14 & 7);
      if ( !v8 )
        break;
      if ( *(_DWORD *)(a1 + 7992) )
      {
        v18 = ((unsigned __int8)v17 & *(_BYTE *)(v16 + a1 + 26104)) == 0;
LABEL_19:
        LODWORD(v11) = v18;
        if ( !v18 )
          goto LABEL_23;
        goto LABEL_20;
      }
      v11 = *(_QWORD *)(a1 + 26096);
      if ( ((unsigned __int8)v17 & *(_BYTE *)(v16 + v11)) != 0 )
      {
LABEL_23:
        if ( v10 )
          goto LABEL_69;
        goto LABEL_67;
      }
LABEL_20:
      PutString(a1, "/");
      if ( v42 )
      {
        PutString(a1, *(const char **)(v42 + 8LL * (unsigned int)v12));
      }
      else
      {
        if ( v14 )
          v19 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 14936) + 2LL * (v14 - 1));
        else
          v19 = 0;
        PutStringID(a1, v19);
      }
      if ( *(_DWORD *)(a1 + 7972) && v35 != 2 )
      {
        ProcessOneCharString(a1, v14);
LABEL_32:
        v20 = *(_DWORD *)(a1 + 7972);
        v21 = v14;
        if ( v20 )
          v21 = 0;
        if ( v21 >= *(_DWORD *)(a1 + 14236) )
        {
          v22 = v14;
          if ( v20 )
            v22 = 0;
          xcf_da_Grow(a1 + 14224, 4, v22);
        }
        v23 = *(_DWORD *)(a1 + 7972);
        v24 = *(_QWORD *)(a1 + 14224);
        v25 = v14;
        if ( v23 )
          v25 = 0;
        v26 = *(unsigned int *)(v24 + 4 * v25);
        if ( v23 )
        {
          v28 = *(_WORD *)(a1 + 14184);
        }
        else
        {
          v27 = v14 + 1;
          if ( (unsigned int)v27 >= *(_DWORD *)(a1 + 14236) )
          {
            xcf_da_Grow(a1 + 14224, 4, (unsigned int)v27);
            v24 = *(_QWORD *)(a1 + 14224);
          }
          v28 = *(_WORD *)(v24 + 4 * v27) - v26;
        }
        if ( (unsigned int)v26 >= *(_DWORD *)(a1 + 14188) )
          xcf_da_Grow(a1 + 14176, 1, (unsigned int)v26);
        v29 = *(_QWORD *)(a1 + 14176) + v26;
        v7 = v38;
        goto LABEL_50;
      }
      CheckSeacCharString(a1, v14);
      if ( v35 != 2 )
        goto LABEL_32;
      XCF_LookUpTableEntry(a1, v13, v14);
      v28 = *(_WORD *)(a1 + 14172);
      v29 = *(_QWORD *)(a1 + 14144);
LABEL_50:
      (*(void (**)(_OWORD *, __int64, const char *, ...))(a1 + 360))(v43, 50, " %lu -| ", v28 + (unsigned int)v39);
      PutString(a1, (const char *)v43);
      PutType1CharString(a1, v29, v28);
      PutString(a1, " |-\r\n");
      v8 = a2;
      if ( a2 && *(_DWORD *)(a1 + 7992) )
      {
        LODWORD(v11) = *(unsigned __int8 *)(v16 + a1 + 26104) | (1 << v15);
        *(_BYTE *)(v16 + a1 + 26104) = v11;
      }
      else
      {
        v30 = *(_QWORD *)(a1 + 26096);
        LODWORD(v11) = *(unsigned __int8 *)(v30 + v16) | (1 << v15);
        *(_BYTE *)(v30 + v16) = v11;
      }
      if ( a6 )
        *a6 += v28;
      v10 = v36;
      if ( v36 )
      {
LABEL_69:
        v6 = v40;
        goto LABEL_70;
      }
      if ( !a2 )
      {
        v31 = 0;
        if ( *(_WORD *)(a1 + 21944) )
        {
          SeacGlyphID = GetSeacGlyphID(a1, *(unsigned __int16 *)(a1 + 21944));
          if ( SeacGlyphID != -1 )
          {
            v31 = 1;
            v41[0] = (unsigned __int16)SeacGlyphID;
          }
        }
        LODWORD(v11) = *(unsigned __int16 *)(a1 + 21946);
        if ( (_WORD)v11 )
        {
          LODWORD(v11) = GetSeacGlyphID(a1, *(unsigned __int16 *)(a1 + 21946));
          if ( (_DWORD)v11 != -1 )
          {
            v33 = (unsigned __int16)v11;
            v11 = v31++;
            v41[v11] = v33;
          }
        }
        if ( v31 )
          LODWORD(v11) = WriteCharstrings(a1, 1, v31, (unsigned int)v41, 0, (__int64)a6);
        v10 = 0;
        v8 = a2;
      }
LABEL_67:
      v6 = ++v40;
LABEL_70:
      ++v12;
      v13 = (_DWORD *)(a1 + 7908);
      if ( v12 >= v7 )
        return v11;
    }
    v18 = ((unsigned __int8)v17 & *(_BYTE *)(v16 + *(_QWORD *)(a1 + 26096))) == 0;
    goto LABEL_19;
  }
  return v11;
}

```

## disassembly

```asm
0x18004a4f4  mov     r11, rsp
0x18004a4f7  mov     [r11+10h], rbx
0x18004a4fb  push    rbp
0x18004a4fc  push    rsi
0x18004a4fd  push    rdi
0x18004a4fe  push    r12
0x18004a500  push    r13
0x18004a502  push    r14
0x18004a504  push    r15
0x18004a506  sub     rsp, 0A0h
0x18004a50d  mov     rax, cs:__security_cookie
0x18004a514  xor     rax, rsp
0x18004a517  mov     [rsp+0D8h+var_40], rax
0x18004a51f  mov     rax, [rsp+0D8h+arg_20]
0x18004a527  xorps   xmm0, xmm0
0x18004a52a  mov     r12, [rsp+0D8h+arg_28]
0x18004a532  xor     r10d, r10d
0x18004a535  mov     [rsp+0D8h+var_80], rax
0x18004a53a  mov     rdi, r9
0x18004a53d  xor     eax, eax
0x18004a53f  mov     [rsp+0D8h+var_90], r9
0x18004a544  mov     [rsp+0D8h+var_9C], r8d
0x18004a549  mov     r14d, r8d
0x18004a54c  mov     [rsp+0D8h+var_A0], edx
0x18004a550  mov     r9d, edx
0x18004a553  mov     [rsp+0D8h+var_A4], r10d
0x18004a558  mov     rbx, rcx
0x18004a55b  mov     r8d, r10d
0x18004a55e  movups  [rsp+0D8h+var_78], xmm0
0x18004a563  movups  [rsp+0D8h+var_68], xmm0
0x18004a568  mov     [r11-48h], ax
0x18004a56d  mov     al, [rcx+1F34h]
0x18004a573  mov     [rsp+0D8h+var_A8], al
0x18004a577  movups  xmmword ptr [r11-58h], xmm0
0x18004a57c  test    r12, r12
0x18004a57f  jz      short loc_18004A589
0x18004a581  test    edx, edx
0x18004a583  jnz     short loc_18004A589
0x18004a585  mov     [r12], r10d
0x18004a589  or      ecx, 0FFFFFFFFh
0x18004a58c  mov     r11d, 1
0x18004a592  cmp     r14d, ecx
0x18004a595  jnz     short loc_18004A5AB
0x18004a597  mov     r14d, [rbx+1EE4h]
0x18004a59e  mov     r8d, r11d
0x18004a5a1  mov     [rsp+0D8h+var_9C], r14d
0x18004a5a6  mov     [rsp+0D8h+var_A4], r11d
0x18004a5ab  movzx   eax, word ptr [rbx+1F28h]
0x18004a5b2  cmp     ax, cx
0x18004a5b5  jnz     short loc_18004A5BE
0x18004a5b7  mov     dword ptr [rsp+0D8h+var_98], r10d
0x18004a5bc  jmp     short loc_18004A5C3
0x18004a5be  mov     [rsp+0D8h+var_98], ax
0x18004a5c3  mov     r13d, r10d
0x18004a5c6  test    r14d, r14d
0x18004a5c9  jle     loc_18004A903
0x18004a5cf  lea     rbp, [rbx+1EE4h]
0x18004a5d6  test    r8d, r8d
0x18004a5d9  jz      short loc_18004A5E0
0x18004a5db  mov     edi, r13d
0x18004a5de  jmp     short loc_18004A5E2
0x18004a5e0  mov     edi, [rdi]
0x18004a5e2  cmp     edi, [rbp+0]
0x18004a5e5  jg      loc_18004A92E
0x18004a5eb  mov     r15d, edi
0x18004a5ee  movsxd  rsi, edi
0x18004a5f1  and     r15d, 7
0x18004a5f5  sar     rsi, 3
0x18004a5f9  mov     ecx, r15d
0x18004a5fc  mov     edx, r11d
0x18004a5ff  shl     edx, cl
0x18004a601  test    r9d, r9d
0x18004a604  jnz     short loc_18004A612
0x18004a606  mov     rax, [rbx+65F0h]
0x18004a60d  test    [rsi+rax], dl
0x18004a610  jmp     short loc_18004A622
0x18004a612  cmp     [rbx+1F38h], r10d
0x18004a619  jz      short loc_18004A656
0x18004a61b  test    [rsi+rbx+65F8h], dl
0x18004a622  mov     eax, r10d
0x18004a625  setz    al
0x18004a628  test    eax, eax
0x18004a62a  jz      short loc_18004A662
0x18004a62c  lea     rdx, asc_1800647FC; "/"
0x18004a633  mov     rcx, rbx
0x18004a636  call    PutString
0x18004a63b  mov     rax, [rsp+0D8h+var_80]
0x18004a640  mov     rcx, rbx
0x18004a643  test    rax, rax
0x18004a646  jz      short loc_18004A670
0x18004a648  mov     edx, r13d
0x18004a64b  mov     rdx, [rax+rdx*8]
0x18004a64f  call    PutString
0x18004a654  jmp     short loc_18004A68B
0x18004a656  mov     rax, [rbx+65F0h]
0x18004a65d  test    [rsi+rax], dl
0x18004a660  jz      short loc_18004A62C
0x18004a662  test    r8d, r8d
0x18004a665  jnz     loc_18004A8EB
0x18004a66b  jmp     loc_18004A8C9
0x18004a670  test    edi, edi
0x18004a672  jz      short loc_18004A684
0x18004a674  mov     rdx, [rbx+3A58h]
0x18004a67b  lea     eax, [rdi-1]
0x18004a67e  movzx   edx, word ptr [rdx+rax*2]
0x18004a682  jmp     short loc_18004A686
0x18004a684  xor     edx, edx
0x18004a686  call    PutStringID
0x18004a68b  cmp     dword ptr [rbx+1F24h], 0
0x18004a692  jz      loc_18004A71C
0x18004a698  cmp     [rsp+0D8h+var_A8], 2
0x18004a69d  jz      short loc_18004A71C
0x18004a69f  mov     edx, edi
0x18004a6a1  mov     rcx, rbx
0x18004a6a4  call    ProcessOneCharString
0x18004a6a9  mov     edx, [rbx+1F24h]
0x18004a6af  xor     eax, eax
0x18004a6b1  test    edx, edx
0x18004a6b3  mov     ecx, edi
0x18004a6b5  cmovnz  ecx, eax
0x18004a6b8  cmp     ecx, [rbx+379Ch]
0x18004a6be  jb      short loc_18004A6D8
0x18004a6c0  test    edx, edx
0x18004a6c2  lea     rcx, [rbx+3790h]
0x18004a6c9  mov     r8d, edi
0x18004a6cc  lea     edx, [rax+4]
0x18004a6cf  cmovnz  r8d, eax
0x18004a6d3  call    xcf_da_Grow
0x18004a6d8  mov     edx, [rbx+1F24h]
0x18004a6de  lea     r14, [rbx+3790h]
0x18004a6e5  mov     r8, [r14]
0x18004a6e8  xor     eax, eax
0x18004a6ea  mov     ecx, edi
0x18004a6ec  test    edx, edx
0x18004a6ee  cmovnz  ecx, eax
0x18004a6f1  mov     ebp, [r8+rcx*4]
0x18004a6f5  jnz     short loc_18004A74F
0x18004a6f7  inc     edi
0x18004a6f9  cmp     edi, [rbx+379Ch]
0x18004a6ff  jb      short loc_18004A712
0x18004a701  mov     r8d, edi
0x18004a704  lea     edx, [rax+4]
0x18004a707  mov     rcx, r14
0x18004a70a  call    xcf_da_Grow
0x18004a70f  mov     r8, [r14]
0x18004a712  movzx   edi, word ptr [r8+rdi*4]
0x18004a717  sub     di, bp
0x18004a71a  jmp     short loc_18004A756
0x18004a71c  mov     edx, edi
0x18004a71e  mov     rcx, rbx
0x18004a721  call    CheckSeacCharString
0x18004a726  cmp     [rsp+0D8h+var_A8], 2
0x18004a72b  jnz     loc_18004A6A9
0x18004a731  mov     r8d, edi
0x18004a734  mov     rdx, rbp
0x18004a737  mov     rcx, rbx
0x18004a73a  call    XCF_LookUpTableEntry
0x18004a73f  movzx   edi, word ptr [rbx+375Ch]
0x18004a746  mov     rbp, [rbx+3740h]
0x18004a74d  jmp     short loc_18004A77D
0x18004a74f  movzx   edi, word ptr [rbx+3768h]
0x18004a756  lea     r14, [rbx+3760h]
0x18004a75d  cmp     ebp, [rbx+376Ch]
0x18004a763  jb      short loc_18004A775
0x18004a765  mov     r8d, ebp
0x18004a768  mov     edx, 1
0x18004a76d  mov     rcx, r14
0x18004a770  call    xcf_da_Grow
0x18004a775  add     rbp, [r14]
0x18004a778  mov     r14d, [rsp+0D8h+var_9C]
0x18004a77d  movzx   r9d, [rsp+0D8h+var_98]
0x18004a783  lea     r8, aLu; " %lu -| "
0x18004a78a  mov     rax, [rbx+168h]
0x18004a791  lea     rcx, [rsp+0D8h+var_78]
0x18004a796  movzx   edi, di
0x18004a799  mov     edx, 32h ; '2'
0x18004a79e  add     r9d, edi
0x18004a7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7a6  lea     rdx, [rsp+0D8h+var_78]
0x18004a7ab  mov     rcx, rbx
0x18004a7ae  call    PutString
0x18004a7b3  mov     r8d, edi
0x18004a7b6  mov     rdx, rbp
0x18004a7b9  mov     rcx, rbx
0x18004a7bc  call    PutType1CharString
0x18004a7c1  lea     rdx, asc_18006AACC; " |-\r\n"
0x18004a7c8  mov     rcx, rbx
0x18004a7cb  call    PutString
0x18004a7d0  mov     r9d, [rsp+0D8h+var_A0]
0x18004a7d5  xor     r10d, r10d
0x18004a7d8  test    r9d, r9d
0x18004a7db  jz      short loc_18004A7FB
0x18004a7dd  cmp     [rbx+1F38h], r10d
0x18004a7e4  jz      short loc_18004A7FB
0x18004a7e6  movzx   eax, byte ptr [rsi+rbx+65F8h]
0x18004a7ee  bts     eax, r15d
0x18004a7f2  mov     [rsi+rbx+65F8h], al
0x18004a7f9  jmp     short loc_18004A80D
0x18004a7fb  mov     rcx, [rbx+65F0h]
0x18004a802  movzx   eax, byte ptr [rcx+rsi]
0x18004a806  bts     eax, r15d
0x18004a80a  mov     [rcx+rsi], al
0x18004a80d  test    r12, r12
0x18004a810  jz      short loc_18004A816
0x18004a812  add     [r12], edi
0x18004a816  mov     r8d, [rsp+0D8h+var_A4]
0x18004a81b  test    r8d, r8d
0x18004a81e  jnz     loc_18004A8E5
0x18004a824  test    r9d, r9d
0x18004a827  jnz     loc_18004A8C3
0x18004a82d  movzx   eax, word ptr [rbx+55B8h]
0x18004a834  mov     edi, r10d
0x18004a837  test    ax, ax
0x18004a83a  jz      short loc_18004A859
0x18004a83c  mov     edx, eax
0x18004a83e  mov     rcx, rbx
0x18004a841  call    GetSeacGlyphID
0x18004a846  xor     r10d, r10d
0x18004a849  cmp     eax, 0FFFFFFFFh
0x18004a84c  jz      short loc_18004A859
0x18004a84e  movzx   eax, ax
0x18004a851  lea     edi, [r10+1]
0x18004a855  mov     [rsp+0D8h+var_88], eax
0x18004a859  movzx   eax, word ptr [rbx+55BAh]
0x18004a860  test    ax, ax
0x18004a863  jz      short loc_18004A88D
0x18004a865  mov     edx, eax
0x18004a867  mov     rcx, rbx
0x18004a86a  call    GetSeacGlyphID
0x18004a86f  mov     r11d, 1
0x18004a875  cmp     eax, 0FFFFFFFFh
0x18004a878  jz      short loc_18004A888
0x18004a87a  movzx   ecx, ax
0x18004a87d  movzx   eax, di
0x18004a880  add     di, r11w
0x18004a884  mov     [rsp+rax*4+0D8h+var_88], ecx
0x18004a888  xor     r10d, r10d
0x18004a88b  jmp     short loc_18004A893
0x18004a88d  mov     r11d, 1
0x18004a893  test    di, di
0x18004a896  jz      short loc_18004A8D9
0x18004a898  movzx   r8d, di
0x18004a89c  lea     r9, [rsp+0D8h+var_88]
0x18004a8a1  mov     [rsp+0D8h+var_B0], r12
0x18004a8a6  mov     edx, r11d
0x18004a8a9  mov     rcx, rbx
0x18004a8ac  mov     [rsp+0D8h+var_B8], r10
0x18004a8b1  call    WriteCharstrings
0x18004a8b6  mov     r8d, [rsp+0D8h+var_A4]
0x18004a8bb  xor     r10d, r10d
0x18004a8be  mov     r9d, [rsp+0D8h+var_A0]
0x18004a8c3  mov     r11d, 1
0x18004a8c9  mov     rdi, [rsp+0D8h+var_90]
0x18004a8ce  add     rdi, 4
0x18004a8d2  mov     [rsp+0D8h+var_90], rdi
0x18004a8d7  jmp     short loc_18004A8F0
0x18004a8d9  mov     r8d, [rsp+0D8h+var_A4]
0x18004a8de  mov     r9d, [rsp+0D8h+var_A0]
0x18004a8e3  jmp     short loc_18004A8C9
0x18004a8e5  mov     r11d, 1
0x18004a8eb  mov     rdi, [rsp+0D8h+var_90]
0x18004a8f0  add     r13d, r11d
0x18004a8f3  lea     rbp, [rbx+1EE4h]
0x18004a8fa  cmp     r13d, r14d
0x18004a8fd  jl      loc_18004A5D6
0x18004a903  mov     rcx, [rsp+0D8h+var_40]
0x18004a90b  xor     rcx, rsp; StackCookie
0x18004a90e  call    __security_check_cookie
0x18004a913  mov     rbx, [rsp+0D8h+arg_8]
0x18004a91b  add     rsp, 0A0h
0x18004a922  pop     r15
0x18004a924  pop     r14
0x18004a926  pop     r13
0x18004a928  pop     r12
0x18004a92a  pop     rdi
0x18004a92b  pop     rsi
0x18004a92c  pop     rbp
0x18004a92d  retn
0x18004a92e  mov     edx, 21h ; '!'
0x18004a933  mov     rcx, rbx
0x18004a936  call    XCF_FatalErrorHandler
```
