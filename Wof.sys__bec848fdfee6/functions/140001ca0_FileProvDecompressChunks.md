# FileProvDecompressChunks

- ea: `0x140001ca0`
- end: `0x140002293`
- name: `FileProvDecompressChunks`
- size: `1523`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001890`

## callees

- `0x140001ca0`
- `0x14000263c`
- `0x140003a28`
- `0x14000ca10`
- `0x14000d3b8`
- `0x14000fb60`
- `0x1400116c0`
- `0x1400119c0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000203b`
- `ntoskrnl!KeSetEvent` at `0x14000203b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002054`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140002054`
- `ntoskrnl!RtlDecompressBufferEx` at `0x140001f7e`
- `ntoskrnl!RtlDecompressBufferEx` at `0x140001f7e`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140001fc5`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140001fc5`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140001d23`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140001d23`

## pseudocode

```c
__int64 __fastcall FileProvDecompressChunks(PVOID Entry)
{
  unsigned int v1; // ebp
  __int64 v2; // rsi
  __int64 v4; // rbx
  char *v5; // rax
  unsigned int v6; // r10d
  int v7; // r11d
  char *v8; // rax
  bool v9; // zf
  __int64 v10; // r8
  char *v11; // r13
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r8
  int v15; // r10d
  int v16; // r11d
  __int64 v17; // rbx
  unsigned int v18; // r15d
  unsigned int v19; // edx
  __int64 v20; // r12
  __int64 v21; // r9
  __int64 v22; // rax
  __int64 v23; // rcx
  int v24; // r15d
  unsigned int v25; // r10d
  __int64 v26; // rdx
  unsigned int v27; // eax
  __int64 v28; // r9
  __int64 v29; // rcx
  unsigned int v30; // r15d
  unsigned int v31; // ebx
  unsigned int v32; // r12d
  unsigned int v33; // ecx
  __int64 v34; // rsi
  int v35; // eax
  int v36; // eax
  unsigned int v37; // ebp
  int v38; // eax
  __int64 v39; // rbx
  __int64 v40; // rcx
  __int64 result; // rax
  int v42; // eax
  int v43; // ecx
  __int64 v44; // rax
  __int64 v45; // rcx
  int *v46; // [rsp+28h] [rbp-B0h]
  __int64 v47; // [rsp+40h] [rbp-98h]
  int i; // [rsp+48h] [rbp-90h]
  int v49; // [rsp+50h] [rbp-88h]
  int v50; // [rsp+58h] [rbp-80h]
  __int64 v51; // [rsp+60h] [rbp-78h]
  PVOID Entrya; // [rsp+68h] [rbp-70h]
  __int64 v53; // [rsp+70h] [rbp-68h]
  __int64 v54; // [rsp+78h] [rbp-60h]
  struct _PAGED_LOOKASIDE_LIST *Lookaside; // [rsp+88h] [rbp-50h]
  int v56; // [rsp+E0h] [rbp+8h] BYREF
  __int64 v57; // [rsp+E8h] [rbp+10h] BYREF
  unsigned int v58; // [rsp+F0h] [rbp+18h]
  int v59; // [rsp+F8h] [rbp+20h]

  v1 = *((_DWORD *)Entry + 18);
  v2 = *((_QWORD *)Entry + 4);
  v51 = v2;
  v4 = 104LL * *(unsigned int *)(v2 + 4);
  v54 = v4 * 8;
  v58 = g_CompressionScheme[v4];
  v47 = *((_QWORD *)Entry + 7);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
  Lookaside = (struct _PAGED_LOOKASIDE_LIST *)&qword_140019290[v4 + 22];
  v5 = (char *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)&qword_140019290[v4 + 22]);
  Entrya = v5;
  if ( v5 )
  {
    v6 = v58;
    v7 = 0;
    v8 = &v5[v58];
    v9 = *(_DWORD *)(v2 + 4) == 1;
    v10 = v58;
    v59 = 0;
    v56 = 0;
    v53 = 0;
    v50 = 0;
    v57 = v58;
    if ( v9 )
    {
      v44 = LZX_DecodeInit(v8, HIDWORD(g_CompressionScheme[v4 + 1]), v58);
      v6 = v58;
      v7 = 0;
      v10 = v57;
      v53 = v44;
    }
    if ( *(_QWORD *)(v2 + 32) )
    {
      v7 = (v10 + *(_QWORD *)(v2 + 8) - 1LL) / v10 - 1;
      v50 = v7;
    }
    v11 = (char *)*((_QWORD *)Entry + 6);
    v12 = *((_QWORD *)Entry + 8) % v10;
    v49 = v12;
    v13 = *((_QWORD *)Entry + 8) / v10;
    for ( i = v13; ; ++i )
    {
      if ( !v1 )
      {
LABEL_35:
        v36 = v59;
        v37 = v56;
        *((_DWORD *)Entry + 19) = v56;
        *((_DWORD *)Entry + 20) = v36;
        ExFreeToPagedLookasideList(Lookaside, Entrya);
        goto LABEL_36;
      }
      v14 = *(_QWORD *)(v2 + 32);
      if ( v14 )
      {
        v15 = 0;
        v16 = 0;
        v17 = 16LL * (((int)v13 + 1) / 0xDu);
        v18 = ((int)v13 + 1) % 0xDu;
        v19 = 0;
        v20 = *(_QWORD *)(32LL * (((int)v13 + 1) / 0xDu) + v14);
        if ( v18 >= 2 )
        {
          v21 = v17 + 4;
          do
          {
            v22 = v21 + v19;
            v23 = v21 + v19 + 1;
            v19 += 2;
            v15 += *(unsigned __int16 *)(v14 + 2 * v22);
            v16 += *(unsigned __int16 *)(v14 + 2 * v23);
          }
          while ( v19 < v18 - 1 );
          LODWORD(v13) = i;
          v2 = v51;
        }
        if ( v19 < v18 )
          LODWORD(v20) = *(unsigned __int16 *)(v14 + 2 * (v17 + v19) + 8) + (_DWORD)v20;
        v24 = v20 + v16 + v15;
        v25 = (unsigned int)v13 % 0xD;
        v26 = *(_QWORD *)(32LL * ((unsigned int)v13 / 0xD) + v14);
        v27 = 0;
        if ( (unsigned int)v13 % 0xD )
        {
          v28 = 16LL * ((unsigned int)v13 / 0xD) + 4;
          do
          {
            v29 = v27++;
            LODWORD(v26) = *(unsigned __int16 *)(v14 + 2 * (v28 + v29)) + (_DWORD)v26;
          }
          while ( v27 < v25 );
          LODWORD(v13) = i;
        }
        LODWORD(v12) = v49;
        v30 = v24 - v26;
        v6 = v58;
        v7 = v50;
      }
      else
      {
        v30 = *(_DWORD *)(v2 + 16);
      }
      v31 = v6 - v12;
      LODWORD(v57) = v6 - v12;
      if ( v6 - (unsigned int)v12 <= v1 )
      {
        v32 = v6 - v12;
      }
      else
      {
        v31 = v1;
        v32 = v1;
        LODWORD(v57) = v1;
      }
      if ( v30 )
      {
        if ( v30 != v6 )
        {
          if ( (_DWORD)v13 != v7 )
          {
            v33 = v6;
            goto LABEL_27;
          }
          v45 = *(_QWORD *)(v2 + 8);
          if ( v30 != (unsigned int)(v45 % v6) )
          {
            v33 = v45 - i * v6;
LABEL_27:
            if ( *((_BYTE *)&g_CompressionScheme[2] + v54 + 1) )
            {
              if ( !(_DWORD)v12 && v32 == v33 && *((_BYTE *)Entry + 40) )
                goto LABEL_47;
LABEL_29:
              v34 = (__int64)Entrya;
              v31 = v33;
              LODWORD(v57) = v33;
            }
            else
            {
              if ( (_DWORD)v12 || v32 != v33 )
                goto LABEL_29;
LABEL_47:
              v34 = (__int64)v11;
            }
            v35 = *(_DWORD *)(v51 + 4);
            if ( (v35 & 0xFFFFFFFC) != 0 )
            {
              if ( v35 == 1 )
                goto LABEL_58;
            }
            else
            {
              if ( v35 != 1 )
              {
                v56 = 0;
                v46 = &v56;
                v56 = RtlDecompressBufferEx(4, v34, v31, v47, v30);
                goto LABEL_33;
              }
LABEL_58:
              v42 = LZX_Decode(v53, v31, v47, v30, v34, (_DWORD)v46, (__int64)&v57);
              v43 = v56;
              if ( v42 )
                v43 = -1073741823;
              v56 = v43;
              LZX_DecodeNewGroup(v53);
              v31 = v57;
LABEL_33:
              LODWORD(v12) = v49;
            }
            if ( v56 < 0 )
              goto LABEL_35;
            if ( (char *)v34 != v11 )
            {
              v31 = v32;
              memmove(v11, (const void *)(v34 + (unsigned int)v12), v32);
            }
            goto LABEL_44;
          }
        }
        memmove(v11, (const void *)(v47 + (unsigned int)v12), v32);
      }
      else
      {
        memset(v11, 0, v32);
      }
      if ( v56 < 0 )
        goto LABEL_35;
LABEL_44:
      v1 -= v31;
      v59 += v31;
      LODWORD(v12) = 0;
      v2 = v51;
      v6 = v58;
      v7 = v50;
      v11 += v31;
      v49 = 0;
      v47 += v30;
      LODWORD(v13) = i + 1;
    }
  }
  v37 = -1073741670;
  *((_DWORD *)Entry + 20) = 0;
  *((_DWORD *)Entry + 19) = -1073741670;
LABEL_36:
  v38 = *((_DWORD *)Entry + 19);
  v39 = 104LL * *(unsigned int *)(*((_QWORD *)Entry + 4) + 4LL);
  v40 = *((_QWORD *)Entry + 11);
  if ( v38 < 0 )
  {
    if ( *(int *)(v40 + 32) >= 0 )
      *(_DWORD *)(v40 + 32) = v38;
  }
  else
  {
    _InterlockedAdd((volatile signed __int32 *)(v40 + 36), *((_DWORD *)Entry + 20));
  }
  if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)Entry + 11), 0xFFFFFFFF) == 1 )
    KeSetEvent((PRKEVENT)(*((_QWORD *)Entry + 11) + 8LL), 0, 0);
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&g_CompressionScheme[v39 + 64], Entry);
  result = HIDWORD(WPP_GLOBAL_Control->Timer);
  if ( (result & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    return WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_3b099794e4b93327e327da255c047df6_Traceguids, v37);
  return result;
}

```

## disassembly

```asm
0x140001ca0  mov     rax, rsp
0x140001ca3  push    rbp
0x140001ca4  sub     rsp, 0D0h
0x140001cab  mov     ebp, [rcx+48h]
0x140001cae  mov     [rax-10h], rbx
0x140001cb2  mov     [rax-18h], rsi
0x140001cb6  mov     rsi, [rcx+20h]
0x140001cba  mov     [rax-20h], rdi
0x140001cbe  mov     rdi, rcx
0x140001cc1  mov     [rax-40h], r15
0x140001cc5  lea     r15, g_CompressionScheme
0x140001ccc  mov     [rsp+0D8h+var_78], rsi
0x140001cd1  mov     eax, [rsi+4]
0x140001cd4  imul    rbx, rax, 340h
0x140001cdb  mov     [rsp+0D8h+var_60], rbx
0x140001ce0  mov     eax, [rbx+r15]
0x140001ce4  mov     [rsp+0D8h+arg_10], eax
0x140001ceb  mov     rax, [rcx+38h]
0x140001cef  mov     [rsp+0D8h+var_98], rax
0x140001cf4  mov     rcx, cs:WPP_GLOBAL_Control
0x140001cfb  mov     eax, [rcx+2Ch]
0x140001cfe  test    al, 20h
0x140001d00  jnz     loc_140002236
0x140001d06  lea     rax, [r15+0C0h]
0x140001d0d  mov     [rsp+0D8h+var_38], r14
0x140001d15  add     rax, rbx
0x140001d18  mov     rcx, rax; Lookaside
0x140001d1b  mov     [rsp+0D8h+Lookaside], rax
0x140001d23  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140001d2a  nop     dword ptr [rax+rax+00h]
0x140001d2f  xor     r14d, r14d
0x140001d32  mov     [rsp+0D8h+Entry], rax
0x140001d37  test    rax, rax
0x140001d3a  jz      loc_140002139
0x140001d40  mov     r10d, [rsp+0D8h+arg_10]
0x140001d48  mov     r11d, r14d
0x140001d4b  add     rax, r10
0x140001d4e  mov     [rsp+0D8h+var_30], r13
0x140001d56  cmp     dword ptr [rsi+4], 1
0x140001d5a  mov     r8d, r10d
0x140001d5d  mov     [rsp+0D8h+arg_18], r14d
0x140001d65  mov     [rsp+0D8h+arg_0], r14d
0x140001d6d  mov     [rsp+0D8h+var_68], r14
0x140001d72  mov     [rsp+0D8h+var_80], r11
0x140001d77  mov     [rsp+0D8h+arg_8], r10
0x140001d7f  mov     [rsp+0D8h+var_58], rax
0x140001d87  jz      loc_1400021E3
0x140001d8d  cmp     [rsi+20h], r14
0x140001d91  jz      short loc_140001DAB
0x140001d93  mov     rax, [rsi+8]
0x140001d97  dec     rax
0x140001d9a  add     rax, r8
0x140001d9d  cqo
0x140001d9f  idiv    r8
0x140001da2  lea     r11d, [rax-1]
0x140001da6  mov     [rsp+0D8h+var_80], r11
0x140001dab  mov     rax, [rdi+40h]
0x140001daf  mov     r13, [rdi+30h]
0x140001db3  cqo
0x140001db5  idiv    r8
0x140001db8  mov     [rsp+0D8h+var_28], r12
0x140001dc0  mov     r9, rdx
0x140001dc3  mov     [rsp+0D8h+var_88], rdx
0x140001dc8  mov     rcx, rax
0x140001dcb  mov     [rsp+0D8h+var_90], rax
0x140001dd0  test    ebp, ebp
0x140001dd2  jz      loc_140001FA4
0x140001dd8  mov     r8, [rsi+20h]
0x140001ddc  test    r8, r8
0x140001ddf  jz      loc_140002162
0x140001de5  lea     r15d, [rcx+1]
0x140001de9  mov     eax, 4EC4EC4Fh
0x140001dee  mul     r15d
0x140001df1  mov     r10, r14
0x140001df4  mov     r11, r14
0x140001df7  shr     edx, 2
0x140001dfa  imul    eax, edx, 0Dh
0x140001dfd  mov     ebx, edx
0x140001dff  shl     rbx, 4
0x140001e03  sub     r15d, eax
0x140001e06  mov     eax, edx
0x140001e08  shl     rax, 5
0x140001e0c  mov     edx, r14d
0x140001e0f  mov     r12, [rax+r8]
0x140001e13  cmp     r15d, 2
0x140001e17  jb      short loc_140001E4D
0x140001e19  lea     r9, [rbx+4]
0x140001e1d  lea     esi, [r15-1]
0x140001e21  mov     eax, edx
0x140001e23  lea     ecx, [rdx+1]
0x140001e26  add     rax, r9
0x140001e29  add     rcx, r9
0x140001e2c  add     edx, 2
0x140001e2f  movzx   eax, word ptr [r8+rax*2]
0x140001e34  add     r10, rax
0x140001e37  movzx   eax, word ptr [r8+rcx*2]
0x140001e3c  add     r11, rax
0x140001e3f  cmp     edx, esi
0x140001e41  jb      short loc_140001E21
0x140001e43  mov     rcx, [rsp+0D8h+var_90]
0x140001e48  mov     rsi, [rsp+0D8h+var_78]
0x140001e4d  cmp     edx, r15d
0x140001e50  jb      loc_140002094
0x140001e56  lea     r15, [r11+r10]
0x140001e5a  mov     eax, 4EC4EC4Fh
0x140001e5f  mul     ecx
0x140001e61  mov     r10d, ecx
0x140001e64  add     r15, r12
0x140001e67  shr     edx, 2
0x140001e6a  imul    eax, edx, 0Dh
0x140001e6d  mov     r9d, edx
0x140001e70  sub     r10d, eax
0x140001e73  mov     eax, edx
0x140001e75  shl     rax, 5
0x140001e79  mov     rdx, [rax+r8]
0x140001e7d  mov     eax, r14d
0x140001e80  test    r10d, r10d
0x140001e83  jz      short loc_140001EA9
0x140001e85  shl     r9, 4
0x140001e89  add     r9, 4
0x140001e8d  nop     dword ptr [rax]
0x140001e90  mov     ecx, eax
0x140001e92  inc     eax
0x140001e94  add     rcx, r9
0x140001e97  movzx   ecx, word ptr [r8+rcx*2]
0x140001e9c  add     rdx, rcx
0x140001e9f  cmp     eax, r10d
0x140001ea2  jb      short loc_140001E90
0x140001ea4  mov     rcx, [rsp+0D8h+var_90]
0x140001ea9  mov     r9, [rsp+0D8h+var_88]
0x140001eae  sub     r15d, edx
0x140001eb1  mov     r10d, [rsp+0D8h+arg_10]
0x140001eb9  mov     r11, [rsp+0D8h+var_80]
0x140001ebe  mov     ebx, r10d
0x140001ec1  sub     ebx, r9d
0x140001ec4  mov     dword ptr [rsp+0D8h+arg_8], ebx
0x140001ecb  cmp     ebx, ebp
0x140001ecd  jbe     loc_14000216B
0x140001ed3  mov     ebx, ebp
0x140001ed5  mov     r12d, ebp
0x140001ed8  mov     dword ptr [rsp+0D8h+arg_8], ebx
0x140001edf  test    r15d, r15d
0x140001ee2  jz      loc_1400020A7
0x140001ee8  cmp     r15d, r10d
0x140001eeb  jz      loc_14000214A
0x140001ef1  cmp     ecx, r11d
0x140001ef4  jz      loc_14000220F
0x140001efa  mov     ecx, r10d
0x140001efd  mov     rax, [rsp+0D8h+var_60]
0x140001f02  lea     rdx, g_CompressionScheme
0x140001f09  cmp     [rax+rdx+11h], r14b
0x140001f0e  jz      loc_140002173
0x140001f14  test    r9d, r9d
0x140001f17  jz      loc_140002103
0x140001f1d  mov     rsi, [rsp+0D8h+Entry]
0x140001f22  mov     ebx, ecx
0x140001f24  mov     dword ptr [rsp+0D8h+arg_8], ecx
0x140001f2b  mov     rax, [rsp+0D8h+var_78]
0x140001f30  mov     eax, [rax+4]
0x140001f33  test    eax, 0FFFFFFFCh
0x140001f38  jnz     loc_140002186
0x140001f3e  cmp     eax, 1
0x140001f41  jz      loc_14000218F
0x140001f47  mov     rax, [rsp+0D8h+var_58]
0x140001f4f  mov     ecx, 4
0x140001f54  mov     r9, [rsp+0D8h+var_98]
0x140001f59  mov     r8d, ebx
0x140001f5c  mov     [rsp+0D8h+var_A8], rax
0x140001f61  mov     rdx, rsi
0x140001f64  lea     rax, [rsp+0D8h+arg_0]
0x140001f6c  mov     [rsp+0D8h+arg_0], r14d
0x140001f74  mov     [rsp+0D8h+var_B0], rax
0x140001f79  mov     dword ptr [rsp+0D8h+var_B8], r15d
0x140001f7e  call    cs:__imp_RtlDecompressBufferEx
0x140001f85  nop     dword ptr [rax+rax+00h]
0x140001f8a  mov     [rsp+0D8h+arg_0], eax
0x140001f91  mov     r9, [rsp+0D8h+var_88]
0x140001f96  cmp     [rsp+0D8h+arg_0], r14d
0x140001f9e  jge     loc_14000211E
0x140001fa4  mov     eax, [rsp+0D8h+arg_18]
0x140001fab  mov     ebp, [rsp+0D8h+arg_0]
0x140001fb2  mov     rdx, [rsp+0D8h+Entry]; Entry
0x140001fb7  mov     rcx, [rsp+0D8h+Lookaside]; Lookaside
0x140001fbf  mov     [rdi+4Ch], ebp
0x140001fc2  mov     [rdi+50h], eax
0x140001fc5  call    cs:__imp_ExFreeToPagedLookasideList
0x140001fcc  nop     dword ptr [rax+rax+00h]
0x140001fd1  mov     r13, [rsp+0D8h+var_30]
0x140001fd9  lea     r15, g_CompressionScheme
0x140001fe0  mov     r12, [rsp+0D8h+var_28]
0x140001fe8  mov     rax, [rdi+20h]
0x140001fec  mov     r14, [rsp+0D8h+var_38]
0x140001ff4  mov     rsi, [rsp+0D8h+var_18]
0x140001ffc  mov     ecx, [rax+4]
0x140001fff  mov     eax, [rdi+4Ch]
0x140002002  imul    rbx, rcx, 340h
0x140002009  mov     rcx, [rdi+58h]
0x14000200d  test    eax, eax
0x14000200f  js      loc_14000225A
0x140002015  mov     eax, [rdi+50h]
0x140002018  lock add [rcx+24h], eax
0x14000201c  mov     rax, [rdi+58h]
0x140002020  mov     ecx, 0FFFFFFFFh
0x140002025  lock xadd [rax], ecx
0x140002029  cmp     ecx, 1
0x14000202c  jnz     short loc_140002047
0x14000202e  mov     rcx, [rdi+58h]
0x140002032  xor     r8d, r8d; Wait
0x140002035  add     rcx, 8; Event
0x140002039  xor     edx, edx; Increment
0x14000203b  call    cs:__imp_KeSetEvent
0x140002042  nop     dword ptr [rax+rax+00h]
0x140002047  lea     rcx, [rbx+200h]
0x14000204e  mov     rdx, rdi; Entry
0x140002051  add     rcx, r15; Lookaside
0x140002054  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000205b  nop     dword ptr [rax+rax+00h]
0x140002060  mov     rcx, cs:WPP_GLOBAL_Control
0x140002067  mov     r15, [rsp+0D8h+var_40]
0x14000206f  mov     rdi, [rsp+0D8h+var_20]
0x140002077  mov     rbx, [rsp+0D8h+var_10]
0x14000207f  mov     eax, [rcx+2Ch]
0x140002082  test    al, 20h
0x140002084  jnz     loc_14000226C
0x14000208a  add     rsp, 0D0h
0x140002091  pop     rbp
0x140002092  retn
0x140002094  mov     eax, edx
0x140002096  add     rax, rbx
0x140002099  movzx   eax, word ptr [r8+rax*2+8]
0x14000209f  add     r12, rax
0x1400020a2  jmp     loc_140001E56
0x1400020a7  mov     r8d, r12d; Size
0x1400020aa  xor     edx, edx; Val
0x1400020ac  mov     rcx, r13; void *
0x1400020af  call    memset
0x1400020b4  cmp     [rsp+0D8h+arg_0], r14d
0x1400020bc  jl      loc_140001FA4
0x1400020c2  mov     rcx, [rsp+0D8h+var_90]
0x1400020c7  sub     ebp, ebx
0x1400020c9  add     [rsp+0D8h+arg_18], ebx
0x1400020d0  mov     r9d, r14d
0x1400020d3  mov     rsi, [rsp+0D8h+var_78]
0x1400020d8  mov     r10d, [rsp+0D8h+arg_10]
0x1400020e0  mov     r11, [rsp+0D8h+var_80]
0x1400020e5  mov     eax, ebx
0x1400020e7  add     r13, rax
0x1400020ea  mov     [rsp+0D8h+var_88], r9
0x1400020ef  mov     eax, r15d
0x1400020f2  add     [rsp+0D8h+var_98], rax
0x1400020f7  inc     ecx
0x1400020f9  mov     [rsp+0D8h+var_90], rcx
0x1400020fe  jmp     loc_140001DD0
0x140002103  cmp     r12d, ecx
0x140002106  jnz     loc_140001F1D
0x14000210c  cmp     [rdi+28h], r14b
0x140002110  jz      loc_140001F1D
0x140002116  mov     rsi, r13
0x140002119  jmp     loc_140001F2B
0x14000211e  cmp     rsi, r13
0x140002121  jz      short loc_1400020C2
0x140002123  mov     edx, r9d
0x140002126  mov     rcx, r13; void *
0x140002129  add     rdx, rsi; Src
0x14000212c  mov     r8d, r12d; Size
0x14000212f  mov     ebx, r12d
0x140002132  call    memmove
0x140002137  jmp     short loc_1400020C2
0x140002139  mov     ebp, 0C000009Ah
0x14000213e  mov     [rdi+50h], r14d
0x140002142  mov     [rdi+4Ch], ebp
0x140002145  jmp     loc_140001FE8
0x14000214a  mov     edx, r9d
0x14000214d  mov     rcx, r13; void *
0x140002150  add     rdx, [rsp+0D8h+var_98]; Src
0x140002155  mov     r8d, r12d; Size
0x140002158  call    memmove
0x14000215d  jmp     loc_1400020B4
0x140002162  mov     r15d, [rsi+10h]
0x140002166  jmp     loc_140001EBE
0x14000216b  mov     r12d, ebx
0x14000216e  jmp     loc_140001EDF
0x140002173  test    r9d, r9d
0x140002176  jnz     loc_140001F1D
0x14000217c  cmp     r12d, ecx
0x14000217f  jz      short loc_140002116
0x140002181  jmp     loc_140001F1D
0x140002186  cmp     eax, 1
0x140002189  jnz     loc_140001F96
0x14000218f  mov     r8, [rsp+0D8h+var_98]
0x140002194  lea     rax, [rsp+0D8h+arg_8]
0x14000219c  mov     rcx, [rsp+0D8h+var_68]
0x1400021a1  mov     r9d, r15d
0x1400021a4  mov     [rsp+0D8h+var_A8], rax
0x1400021a9  mov     edx, ebx
0x1400021ab  mov     [rsp+0D8h+var_B8], rsi
0x1400021b0  call    LZX_Decode
0x1400021b5  mov     ecx, [rsp+0D8h+arg_0]
0x1400021bc  test    eax, eax
0x1400021be  mov     eax, 0C0000001h
  ... truncated ...
```
