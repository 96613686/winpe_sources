# WriteCharstrings

- ea: `0x18004bd74`
- end: `0x18004c1bd`
- name: `WriteCharstrings`
- size: `1097`
- prototype: `int __fastcall(__int64, int, int, unsigned int *, __int64, _DWORD *)`
- caller_count: `3`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18004bd74`
- `0x18004d3a8`
- `0x18004e268`

## callees

- `0x180001f20`
- `0x1800481e4`
- `0x180049fe4`
- `0x18004ab60`
- `0x18004b690`
- `0x18004b6d0`
- `0x18004b714`
- `0x18004bd74`
- `0x18004f8e4`
- `0x18004ff84`
- `0x18005054c`
- `0x18005f010`

## pseudocode

```c
int __fastcall WriteCharstrings(__int64 a1, int a2, int a3, unsigned int *a4, __int64 a5, _DWORD *a6)
{
  signed int *v6; // rdi
  int v7; // r14d
  int v8; // r9d
  int v10; // r8d
  __int64 v11; // rax
  signed int v12; // r13d
  signed int *v13; // rbp
  signed int v14; // edi
  char v15; // r15
  __int64 v16; // rsi
  int v17; // edx
  bool v18; // zf
  unsigned __int16 v19; // dx
  int v20; // edx
  unsigned int v21; // ecx
  unsigned int v22; // r8d
  int v23; // edx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rbp
  __int64 v27; // rdi
  unsigned __int16 v28; // di
  unsigned __int8 *v29; // rbp
  __int64 v30; // rcx
  unsigned __int16 v31; // di
  int SeacGlyphID; // eax
  unsigned int v33; // ecx
  char v35; // [rsp+30h] [rbp-A8h]
  int v36; // [rsp+34h] [rbp-A4h]
  int v38; // [rsp+3Ch] [rbp-9Ch]
  unsigned __int16 v39; // [rsp+40h] [rbp-98h]
  unsigned int *v40; // [rsp+48h] [rbp-90h]
  unsigned int v41[2]; // [rsp+50h] [rbp-88h] BYREF
  __int64 v42; // [rsp+58h] [rbp-80h]
  _OWORD v43[3]; // [rsp+60h] [rbp-78h] BYREF
  __int16 v44; // [rsp+90h] [rbp-48h]

  v42 = a5;
  v6 = (signed int *)a4;
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
    v13 = (signed int *)(a1 + 7908);
    while ( 1 )
    {
      if ( v10 )
        v14 = v12;
      else
        v14 = *v6;
      if ( v14 > *v13 )
        XCF_FatalErrorHandler((_JBTYPE *)a1, 33);
      v15 = v14 & 7;
      v16 = (__int64)v14 >> 3;
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
      PutString(a1, (__int64)"/");
      if ( v42 )
      {
        PutString(a1, *(_QWORD *)(v42 + 8LL * (unsigned int)v12));
      }
      else
      {
        if ( v14 )
          v19 = *(_WORD *)(*(_QWORD *)(a1 + 14936) + 2LL * (unsigned int)(v14 - 1));
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
        v25 = (unsigned int)v14;
        if ( v23 )
          v25 = 0;
        v26 = *(unsigned int *)(v24 + 4 * v25);
        if ( v23 )
        {
          v28 = *(_WORD *)(a1 + 14184);
        }
        else
        {
          v27 = (unsigned int)(v14 + 1);
          if ( (unsigned int)v27 >= *(_DWORD *)(a1 + 14236) )
          {
            xcf_da_Grow(a1 + 14224, 4, v27);
            v24 = *(_QWORD *)(a1 + 14224);
          }
          v28 = *(_WORD *)(v24 + 4 * v27) - v26;
        }
        if ( (unsigned int)v26 >= *(_DWORD *)(a1 + 14188) )
          xcf_da_Grow(a1 + 14176, 1, v26);
        v29 = (unsigned __int8 *)(*(_QWORD *)(a1 + 14176) + v26);
        v7 = v38;
        goto LABEL_50;
      }
      CheckSeacCharString(a1, v14);
      if ( v35 != 2 )
        goto LABEL_32;
      XCF_LookUpTableEntry(a1, v13, v14);
      v28 = *(_WORD *)(a1 + 14172);
      v29 = *(unsigned __int8 **)(a1 + 14144);
LABEL_50:
      (*(void (**)(_OWORD *, __int64, const char *, ...))(a1 + 360))(v43, 50, " %lu -| ", v28 + (unsigned int)v39);
      PutString(a1, (__int64)v43);
      PutType1CharString(a1, v29, v28);
      PutString(a1, (__int64)" |-\r\n");
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
        v6 = (signed int *)v40;
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
          LODWORD(v11) = WriteCharstrings(a1, 1, v31, v41, 0, a6);
        v10 = 0;
        v8 = a2;
      }
LABEL_67:
      v6 = (signed int *)++v40;
LABEL_70:
      ++v12;
      v13 = (signed int *)(a1 + 7908);
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
0x18004bd74  mov     r11, rsp
0x18004bd77  mov     [r11+10h], rbx
0x18004bd7b  push    rbp
0x18004bd7c  push    rsi
0x18004bd7d  push    rdi
0x18004bd7e  push    r12
0x18004bd80  push    r13
0x18004bd82  push    r14
0x18004bd84  push    r15
0x18004bd86  sub     rsp, 0A0h
0x18004bd8d  mov     rax, cs:__security_cookie
0x18004bd94  xor     rax, rsp
0x18004bd97  mov     [rsp+0D8h+var_40], rax
0x18004bd9f  mov     rax, [rsp+0D8h+arg_20]
0x18004bda7  xorps   xmm0, xmm0
0x18004bdaa  mov     r12, [rsp+0D8h+arg_28]
0x18004bdb2  xor     r10d, r10d
0x18004bdb5  mov     [rsp+0D8h+var_80], rax
0x18004bdba  mov     rdi, r9
0x18004bdbd  xor     eax, eax
0x18004bdbf  mov     [rsp+0D8h+var_90], r9
0x18004bdc4  mov     [rsp+0D8h+var_9C], r8d
0x18004bdc9  mov     r14d, r8d
0x18004bdcc  mov     [rsp+0D8h+var_A0], edx
0x18004bdd0  mov     r9d, edx
0x18004bdd3  mov     [rsp+0D8h+var_A4], r10d
0x18004bdd8  mov     rbx, rcx
0x18004bddb  mov     r8d, r10d
0x18004bdde  movups  [rsp+0D8h+var_78], xmm0
0x18004bde3  movups  [rsp+0D8h+var_68], xmm0
0x18004bde8  mov     [r11-48h], ax
0x18004bded  mov     al, [rcx+1F34h]
0x18004bdf3  mov     [rsp+0D8h+var_A8], al
0x18004bdf7  movups  xmmword ptr [r11-58h], xmm0
0x18004bdfc  test    r12, r12
0x18004bdff  jz      short loc_18004BE09
0x18004be01  test    edx, edx
0x18004be03  jnz     short loc_18004BE09
0x18004be05  mov     [r12], r10d
0x18004be09  or      ecx, 0FFFFFFFFh
0x18004be0c  mov     r11d, 1
0x18004be12  cmp     r14d, ecx
0x18004be15  jnz     short loc_18004BE2B
0x18004be17  mov     r14d, [rbx+1EE4h]
0x18004be1e  mov     r8d, r11d
0x18004be21  mov     [rsp+0D8h+var_9C], r14d
0x18004be26  mov     [rsp+0D8h+var_A4], r11d
0x18004be2b  movzx   eax, word ptr [rbx+1F28h]
0x18004be32  cmp     ax, cx
0x18004be35  jnz     short loc_18004BE3E
0x18004be37  mov     dword ptr [rsp+0D8h+var_98], r10d
0x18004be3c  jmp     short loc_18004BE43
0x18004be3e  mov     [rsp+0D8h+var_98], ax
0x18004be43  mov     r13d, r10d
0x18004be46  test    r14d, r14d
0x18004be49  jle     loc_18004C183
0x18004be4f  lea     rbp, [rbx+1EE4h]
0x18004be56  test    r8d, r8d
0x18004be59  jz      short loc_18004BE60
0x18004be5b  mov     edi, r13d
0x18004be5e  jmp     short loc_18004BE62
0x18004be60  mov     edi, [rdi]
0x18004be62  cmp     edi, [rbp+0]
0x18004be65  jg      loc_18004C1AF
0x18004be6b  mov     r15d, edi
0x18004be6e  movsxd  rsi, edi
0x18004be71  and     r15d, 7
0x18004be75  sar     rsi, 3
0x18004be79  mov     ecx, r15d
0x18004be7c  mov     edx, r11d
0x18004be7f  shl     edx, cl
0x18004be81  test    r9d, r9d
0x18004be84  jnz     short loc_18004BE92
0x18004be86  mov     rax, [rbx+65F0h]
0x18004be8d  test    [rsi+rax], dl
0x18004be90  jmp     short loc_18004BEA2
0x18004be92  cmp     [rbx+1F38h], r10d
0x18004be99  jz      short loc_18004BED6
0x18004be9b  test    [rsi+rbx+65F8h], dl
0x18004bea2  mov     eax, r10d
0x18004bea5  setz    al
0x18004bea8  test    eax, eax
0x18004beaa  jz      short loc_18004BEE2
0x18004beac  lea     rdx, asc_1800667DC; "/"
0x18004beb3  mov     rcx, rbx
0x18004beb6  call    PutString
0x18004bebb  mov     rax, [rsp+0D8h+var_80]
0x18004bec0  mov     rcx, rbx
0x18004bec3  test    rax, rax
0x18004bec6  jz      short loc_18004BEF0
0x18004bec8  mov     edx, r13d
0x18004becb  mov     rdx, [rax+rdx*8]
0x18004becf  call    PutString
0x18004bed4  jmp     short loc_18004BF0B
0x18004bed6  mov     rax, [rbx+65F0h]
0x18004bedd  test    [rsi+rax], dl
0x18004bee0  jz      short loc_18004BEAC
0x18004bee2  test    r8d, r8d
0x18004bee5  jnz     loc_18004C16B
0x18004beeb  jmp     loc_18004C149
0x18004bef0  test    edi, edi
0x18004bef2  jz      short loc_18004BF04
0x18004bef4  mov     rdx, [rbx+3A58h]
0x18004befb  lea     eax, [rdi-1]
0x18004befe  movzx   edx, word ptr [rdx+rax*2]
0x18004bf02  jmp     short loc_18004BF06
0x18004bf04  xor     edx, edx
0x18004bf06  call    PutStringID
0x18004bf0b  cmp     dword ptr [rbx+1F24h], 0
0x18004bf12  jz      loc_18004BF9C
0x18004bf18  cmp     [rsp+0D8h+var_A8], 2
0x18004bf1d  jz      short loc_18004BF9C
0x18004bf1f  mov     edx, edi
0x18004bf21  mov     rcx, rbx
0x18004bf24  call    ProcessOneCharString
0x18004bf29  mov     edx, [rbx+1F24h]
0x18004bf2f  xor     eax, eax
0x18004bf31  test    edx, edx
0x18004bf33  mov     ecx, edi
0x18004bf35  cmovnz  ecx, eax
0x18004bf38  cmp     ecx, [rbx+379Ch]
0x18004bf3e  jb      short loc_18004BF58
0x18004bf40  test    edx, edx
0x18004bf42  lea     rcx, [rbx+3790h]
0x18004bf49  mov     r8d, edi
0x18004bf4c  lea     edx, [rax+4]
0x18004bf4f  cmovnz  r8d, eax
0x18004bf53  call    xcf_da_Grow
0x18004bf58  mov     edx, [rbx+1F24h]
0x18004bf5e  lea     r14, [rbx+3790h]
0x18004bf65  mov     r8, [r14]
0x18004bf68  xor     eax, eax
0x18004bf6a  mov     ecx, edi
0x18004bf6c  test    edx, edx
0x18004bf6e  cmovnz  ecx, eax
0x18004bf71  mov     ebp, [r8+rcx*4]
0x18004bf75  jnz     short loc_18004BFCF
0x18004bf77  inc     edi
0x18004bf79  cmp     edi, [rbx+379Ch]
0x18004bf7f  jb      short loc_18004BF92
0x18004bf81  mov     r8d, edi
0x18004bf84  lea     edx, [rax+4]
0x18004bf87  mov     rcx, r14
0x18004bf8a  call    xcf_da_Grow
0x18004bf8f  mov     r8, [r14]
0x18004bf92  movzx   edi, word ptr [r8+rdi*4]
0x18004bf97  sub     di, bp
0x18004bf9a  jmp     short loc_18004BFD6
0x18004bf9c  mov     edx, edi
0x18004bf9e  mov     rcx, rbx
0x18004bfa1  call    CheckSeacCharString
0x18004bfa6  cmp     [rsp+0D8h+var_A8], 2
0x18004bfab  jnz     loc_18004BF29
0x18004bfb1  mov     r8d, edi
0x18004bfb4  mov     rdx, rbp
0x18004bfb7  mov     rcx, rbx
0x18004bfba  call    XCF_LookUpTableEntry
0x18004bfbf  movzx   edi, word ptr [rbx+375Ch]
0x18004bfc6  mov     rbp, [rbx+3740h]
0x18004bfcd  jmp     short loc_18004BFFD
0x18004bfcf  movzx   edi, word ptr [rbx+3768h]
0x18004bfd6  lea     r14, [rbx+3760h]
0x18004bfdd  cmp     ebp, [rbx+376Ch]
0x18004bfe3  jb      short loc_18004BFF5
0x18004bfe5  mov     r8d, ebp
0x18004bfe8  mov     edx, 1
0x18004bfed  mov     rcx, r14
0x18004bff0  call    xcf_da_Grow
0x18004bff5  add     rbp, [r14]
0x18004bff8  mov     r14d, [rsp+0D8h+var_9C]
0x18004bffd  movzx   r9d, [rsp+0D8h+var_98]
0x18004c003  lea     r8, aLu; " %lu -| "
0x18004c00a  mov     rax, [rbx+168h]
0x18004c011  lea     rcx, [rsp+0D8h+var_78]
0x18004c016  movzx   edi, di
0x18004c019  mov     edx, 32h ; '2'
0x18004c01e  add     r9d, edi
0x18004c021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c026  lea     rdx, [rsp+0D8h+var_78]
0x18004c02b  mov     rcx, rbx
0x18004c02e  call    PutString
0x18004c033  mov     r8d, edi
0x18004c036  mov     rdx, rbp
0x18004c039  mov     rcx, rbx
0x18004c03c  call    PutType1CharString
0x18004c041  lea     rdx, asc_18006CA8C; " |-\r\n"
0x18004c048  mov     rcx, rbx
0x18004c04b  call    PutString
0x18004c050  mov     r9d, [rsp+0D8h+var_A0]
0x18004c055  xor     r10d, r10d
0x18004c058  test    r9d, r9d
0x18004c05b  jz      short loc_18004C07B
0x18004c05d  cmp     [rbx+1F38h], r10d
0x18004c064  jz      short loc_18004C07B
0x18004c066  movzx   eax, byte ptr [rsi+rbx+65F8h]
0x18004c06e  bts     eax, r15d
0x18004c072  mov     [rsi+rbx+65F8h], al
0x18004c079  jmp     short loc_18004C08D
0x18004c07b  mov     rcx, [rbx+65F0h]
0x18004c082  movzx   eax, byte ptr [rcx+rsi]
0x18004c086  bts     eax, r15d
0x18004c08a  mov     [rcx+rsi], al
0x18004c08d  test    r12, r12
0x18004c090  jz      short loc_18004C096
0x18004c092  add     [r12], edi
0x18004c096  mov     r8d, [rsp+0D8h+var_A4]
0x18004c09b  test    r8d, r8d
0x18004c09e  jnz     loc_18004C165
0x18004c0a4  test    r9d, r9d
0x18004c0a7  jnz     loc_18004C143
0x18004c0ad  movzx   eax, word ptr [rbx+55B8h]
0x18004c0b4  mov     edi, r10d
0x18004c0b7  test    ax, ax
0x18004c0ba  jz      short loc_18004C0D9
0x18004c0bc  mov     edx, eax
0x18004c0be  mov     rcx, rbx
0x18004c0c1  call    GetSeacGlyphID
0x18004c0c6  xor     r10d, r10d
0x18004c0c9  cmp     eax, 0FFFFFFFFh
0x18004c0cc  jz      short loc_18004C0D9
0x18004c0ce  movzx   eax, ax
0x18004c0d1  lea     edi, [r10+1]
0x18004c0d5  mov     [rsp+0D8h+var_88], eax
0x18004c0d9  movzx   eax, word ptr [rbx+55BAh]
0x18004c0e0  test    ax, ax
0x18004c0e3  jz      short loc_18004C10D
0x18004c0e5  mov     edx, eax
0x18004c0e7  mov     rcx, rbx
0x18004c0ea  call    GetSeacGlyphID
0x18004c0ef  mov     r11d, 1
0x18004c0f5  cmp     eax, 0FFFFFFFFh
0x18004c0f8  jz      short loc_18004C108
0x18004c0fa  movzx   ecx, ax
0x18004c0fd  movzx   eax, di
0x18004c100  add     di, r11w
0x18004c104  mov     [rsp+rax*4+0D8h+var_88], ecx
0x18004c108  xor     r10d, r10d
0x18004c10b  jmp     short loc_18004C113
0x18004c10d  mov     r11d, 1
0x18004c113  test    di, di
0x18004c116  jz      short loc_18004C159
0x18004c118  movzx   r8d, di
0x18004c11c  lea     r9, [rsp+0D8h+var_88]
0x18004c121  mov     [rsp+0D8h+var_B0], r12
0x18004c126  mov     edx, r11d
0x18004c129  mov     rcx, rbx
0x18004c12c  mov     [rsp+0D8h+var_B8], r10
0x18004c131  call    WriteCharstrings
0x18004c136  mov     r8d, [rsp+0D8h+var_A4]
0x18004c13b  xor     r10d, r10d
0x18004c13e  mov     r9d, [rsp+0D8h+var_A0]
0x18004c143  mov     r11d, 1
0x18004c149  mov     rdi, [rsp+0D8h+var_90]
0x18004c14e  add     rdi, 4
0x18004c152  mov     [rsp+0D8h+var_90], rdi
0x18004c157  jmp     short loc_18004C170
0x18004c159  mov     r8d, [rsp+0D8h+var_A4]
0x18004c15e  mov     r9d, [rsp+0D8h+var_A0]
0x18004c163  jmp     short loc_18004C149
0x18004c165  mov     r11d, 1
0x18004c16b  mov     rdi, [rsp+0D8h+var_90]
0x18004c170  add     r13d, r11d
0x18004c173  lea     rbp, [rbx+1EE4h]
0x18004c17a  cmp     r13d, r14d
0x18004c17d  jl      loc_18004BE56
0x18004c183  mov     rcx, [rsp+0D8h+var_40]
0x18004c18b  xor     rcx, rsp; StackCookie
0x18004c18e  call    __security_check_cookie
0x18004c193  mov     rbx, [rsp+0D8h+arg_8]
0x18004c19b  add     rsp, 0A0h
0x18004c1a2  pop     r15
0x18004c1a4  pop     r14
0x18004c1a6  pop     r13
0x18004c1a8  pop     r12
0x18004c1aa  pop     rdi
0x18004c1ab  pop     rsi
0x18004c1ac  pop     rbp
0x18004c1ad  retn
0x18004c1af  mov     edx, 21h ; '!'
0x18004c1b4  mov     rcx, rbx
0x18004c1b7  call    XCF_FatalErrorHandler
```
