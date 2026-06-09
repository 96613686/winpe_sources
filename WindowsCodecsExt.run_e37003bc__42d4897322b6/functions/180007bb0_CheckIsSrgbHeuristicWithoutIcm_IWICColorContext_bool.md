# CheckIsSrgbHeuristicWithoutIcm(IWICColorContext *,bool *)

- ea: `0x180007bb0`
- end: `0x180008237`
- name: `?CheckIsSrgbHeuristicWithoutIcm@@YAJPEAUIWICColorContext@@PEA_N@Z`
- size: `1671`
- prototype: `__int64 __fastcall(struct IWICColorContext *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007670`

## callees

- `0x180007bb0`
- `0x18000f204`
- `0x180012bec`
- `0x1800171c4`
- `0x180021628`
- `0x180021634`
- `0x180032db5`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800081fa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000820c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008221`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000822c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800081fa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000820c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008221`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000822c`

## pseudocode

```c
__int64 __fastcall CheckIsSrgbHeuristicWithoutIcm(struct IWICColorContext *a1, bool *a2)
{
  struct IWICColorContextVtbl *lpVtbl; // rax
  unsigned int *v4; // rdi
  HRESULT (__stdcall *GetType)(IWICColorContext *, WICColorContextType *); // rax
  void *v7; // r12
  _DWORD *v8; // r14
  int v9; // eax
  unsigned int v10; // ebx
  struct IWICColorContextVtbl *v11; // rax
  int v12; // eax
  struct IWICColorContextVtbl *v13; // rax
  int ColorProfileElement; // eax
  unsigned int v15; // esi
  int v17; // ecx
  bool v18; // zf
  struct IWICColorContextVtbl *v19; // rax
  unsigned int v20; // esi
  int v21; // r10d
  unsigned int v22; // edx
  unsigned int v23; // ecx
  unsigned int v24; // edx
  __int64 v25; // rcx
  unsigned int v26; // r9d
  char v27; // r13
  __int64 i; // rax
  __int64 v29; // r8
  unsigned int j; // esi
  int v31; // edx
  int v32; // ecx
  unsigned int v33; // eax
  unsigned int v34; // ecx
  unsigned int v35; // eax
  _DWORD *v36; // rax
  int v37; // ecx
  _DWORD *v38; // rax
  unsigned int v39; // esi
  int v40; // [rsp+30h] [rbp-39h] BYREF
  int v41; // [rsp+34h] [rbp-35h]
  unsigned __int64 v42; // [rsp+38h] [rbp-31h]
  void *Block[4]; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v44; // [rsp+60h] [rbp-9h]
  _DWORD *v45; // [rsp+68h] [rbp-1h]
  __int64 v46; // [rsp+70h] [rbp+7h]
  _BYTE v47[8]; // [rsp+D0h] [rbp+67h] BYREF
  size_t v48; // [rsp+D8h] [rbp+6Fh] BYREF
  size_t Size; // [rsp+E0h] [rbp+77h] BYREF
  int v50; // [rsp+E8h] [rbp+7Fh] BYREF

  lpVtbl = a1->lpVtbl;
  Block[0] = 0;
  v4 = 0;
  Block[1] = 0;
  *a2 = 0;
  GetType = lpVtbl->GetType;
  v7 = 0;
  Block[3] = 0;
  v44 = 0;
  v8 = 0;
  v45 = 0;
  v46 = 0;
  v50 = 0;
  v9 = ((__int64 (__fastcall *)(struct IWICColorContext *, int *))GetType)(a1, &v50);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_20;
    v17 = v9;
    goto LABEL_28;
  }
  if ( v50 != 2 )
  {
    if ( v50 == 1 )
    {
      v11 = a1->lpVtbl;
      LODWORD(v48) = 0;
      v12 = ((__int64 (__fastcall *)(struct IWICColorContext *, _QWORD, _QWORD, size_t *))v11->GetProfileBytes)(
              a1,
              0,
              0,
              &v48);
      v10 = v12;
      if ( v12 < 0 )
      {
        if ( !g_doStackCaptures )
          goto LABEL_20;
        goto LABEL_8;
      }
      if ( (unsigned int)v48 < 0x90 )
      {
        v18 = g_doStackCaptures == 0;
        goto LABEL_30;
      }
      v4 = (unsigned int *)operator new[]((unsigned int)v48);
      if ( v4 )
      {
        v13 = a1->lpVtbl;
        v40 = 0;
        ColorProfileElement = ((__int64 (__fastcall *)(struct IWICColorContext *, _QWORD, unsigned int *, int *))v13->GetProfileBytes)(
                                a1,
                                (unsigned int)v48,
                                v4,
                                &v40);
        v10 = ColorProfileElement;
        if ( ColorProfileElement < 0 )
        {
          if ( g_doStackCaptures )
LABEL_33:
            DoStackCapture(ColorProfileElement);
          goto LABEL_20;
        }
        v15 = v48;
        if ( (_DWORD)v48 == v40 )
        {
          if ( (_DWORD)v48 == 3144 )
          {
            if ( _byteswap_ulong(v4[13]) == 1934772034
              && _byteswap_ulong(v4[20]) != 1464292425
              && _byteswap_ulong(v4[12]) != 1464292425 )
            {
              *a2 = 1;
              goto LABEL_20;
            }
          }
          else if ( (_DWORD)v48 == 524 && !memcmp_0(v4, qword_18003A4D0, 0x20Cu) )
          {
            *a2 = 1;
            goto LABEL_20;
          }
          if ( *a2 )
            goto LABEL_20;
          if ( (int)ColorProfileParser::InitProfile((ColorProfileParser *)Block, v4, v15) < 0
            || _byteswap_ulong(v4[2]) >= 0x4000000
            || _byteswap_ulong(v4[4]) != 1380401696 )
          {
            v8 = v45;
            goto LABEL_20;
          }
          v8 = v45;
          v20 = 0;
          v21 = g_doStackCaptures;
          qmemcpy(v47, "0B2A0A2B", sizeof(v47));
          while ( v20 < 2 )
          {
            v22 = v8[32];
            v23 = 0;
            if ( v22 )
            {
              while ( *(_DWORD *)&v47[4 * v20] != v8[3 * v23 + 33] )
              {
                if ( ++v23 >= v22 )
                  goto LABEL_49;
              }
LABEL_109:
              v36 = &v8[3 * v23];
              v37 = v36[35];
              if ( !v37 )
              {
                if ( v21 )
                  DoStackCapture(-2147024809);
                goto LABEL_20;
              }
              v33 = v36[34];
              v34 = v33 + v37;
              if ( v34 >= v33 )
              {
                if ( v34 > v44 )
                {
                  if ( v21 )
                    DoStackCapture(-2147022885);
                }
                else if ( v21 )
                {
                  DoStackCapture(-2147024774);
                }
                goto LABEL_20;
              }
              if ( !v21 )
                goto LABEL_20;
              v17 = -2147024362;
LABEL_28:
              DoStackCapture(v17);
              goto LABEL_20;
            }
LABEL_49:
            if ( v23 < v22 )
              goto LABEL_109;
            if ( v21 )
            {
              DoStackCapture(-2147022884);
              v21 = g_doStackCaptures;
            }
            ++v20;
          }
          v26 = 0;
          v27 = 1;
          LODWORD(Size) = 0;
          v47[0] = 1;
          for ( i = 0; ; i = (unsigned int)(v41 + 1) )
          {
            v41 = i;
            if ( (unsigned int)i >= 6 )
            {
              if ( v27 )
              {
                v7 = operator new[](v26);
                if ( v7 )
                {
                  for ( j = 0; ; ++j )
                  {
                    if ( j >= 6 )
                    {
                      if ( v27 )
                        *a2 = 1;
                      goto LABEL_20;
                    }
                    if ( !v27 )
                      goto LABEL_20;
                    v31 = *((_DWORD *)&off_180040010 + 4 * j + 3);
                    LODWORD(Size) = (&off_180040010)[2 * j + 1];
                    ColorProfileElement = ColorProfileParser::GetColorProfileElement(
                                            (__int64)Block,
                                            v31,
                                            v29,
                                            v7,
                                            (unsigned int *)&Size);
                    v10 = ColorProfileElement;
                    if ( ColorProfileElement < 0 )
                      break;
                    if ( (_DWORD)Size == LODWORD((&off_180040010)[2 * j + 1])
                      && !memcmp_0(v7, (&off_180040010)[2 * j], (unsigned int)Size) )
                    {
                      v27 = v47[0];
                    }
                    else
                    {
                      v27 = 0;
                      v47[0] = 0;
                    }
                  }
                  if ( g_doStackCaptures )
                    goto LABEL_33;
                }
                else
                {
                  v10 = -2147024882;
                  if ( g_doStackCaptures )
                    DoStackCapture(-2147024882);
                }
              }
              goto LABEL_20;
            }
            if ( !v27 )
              goto LABEL_20;
            v24 = v8[32];
            v42 = 16 * i;
            v25 = 0;
            if ( v24 )
            {
              while ( *((_DWORD *)&off_180040010 + 4 * i + 3) != v8[3 * (unsigned int)v25 + 33] )
              {
                v25 = (unsigned int)(v25 + 1);
                if ( (unsigned int)v25 >= v24 )
                  goto LABEL_58;
              }
            }
            else
            {
LABEL_58:
              if ( (unsigned int)v25 >= v24 )
              {
                if ( v21 )
                {
                  v32 = -2147022884;
                  goto LABEL_73;
                }
LABEL_60:
                v26 = Size;
                v27 = 0;
                v47[0] = 0;
                continue;
              }
            }
            v38 = &v8[3 * v25];
            v39 = v38[35];
            if ( !v39 )
            {
              if ( v21 )
              {
                DoStackCapture(-2147024809);
                v21 = g_doStackCaptures;
              }
              goto LABEL_60;
            }
            v35 = v38[34];
            if ( v35 + v39 < v35 )
            {
              if ( v21 )
              {
                v32 = -2147024362;
LABEL_73:
                DoStackCapture(v32);
                v21 = g_doStackCaptures;
              }
              goto LABEL_60;
            }
            if ( v35 + v39 > v44 )
            {
              if ( v21 )
              {
                DoStackCapture(-2147022885);
                v21 = g_doStackCaptures;
              }
              goto LABEL_60;
            }
            if ( v21 )
            {
              DoStackCapture(-2147024774);
              v21 = g_doStackCaptures;
              v26 = Size;
            }
            if ( v39 != LODWORD((&off_180040010)[v42 / 8 + 1]) )
              goto LABEL_60;
            if ( v26 <= v39 )
              v26 = v39;
            LODWORD(Size) = v26;
          }
        }
        v18 = g_doStackCaptures == 0;
LABEL_30:
        if ( !v18 )
          DoStackCapture(-2147022885);
        v10 = -2147022885;
        goto LABEL_20;
      }
      v10 = -2147024882;
      if ( !g_doStackCaptures )
        goto LABEL_20;
    }
    else
    {
      if ( v50 )
        goto LABEL_20;
      v10 = -2003292412;
      if ( !g_doStackCaptures )
        goto LABEL_20;
    }
    v17 = v10;
    goto LABEL_28;
  }
  v19 = a1->lpVtbl;
  *(_DWORD *)v47 = 0;
  v12 = ((__int64 (__fastcall *)(struct IWICColorContext *, _BYTE *))v19->GetExifColorSpace)(a1, v47);
  v10 = v12;
  if ( v12 >= 0 )
  {
    *a2 = *(_DWORD *)v47 != 2;
    goto LABEL_20;
  }
  if ( g_doStackCaptures )
LABEL_8:
    DoStackCapture(v12);
LABEL_20:
  operator delete(v4);
  operator delete(v7);
  if ( Block[0] )
  {
    free(Block[0]);
    Block[0] = 0;
  }
  if ( v8 )
    free(v8);
  if ( Block[0] )
    free(Block[0]);
  return v10;
}

```

## disassembly

```asm
0x180007bb0  push    rbp
0x180007bb2  push    rbx
0x180007bb3  push    rsi
0x180007bb4  push    rdi
0x180007bb5  push    r12
0x180007bb7  push    r13
0x180007bb9  push    r14
0x180007bbb  push    r15
0x180007bbd  lea     rbp, [rsp-1Fh]
0x180007bc2  sub     rsp, 88h
0x180007bc9  mov     rax, [rcx]
0x180007bcc  xor     r13d, r13d
0x180007bcf  mov     r15, rdx
0x180007bd2  mov     [rbp+57h+Block], r13
0x180007bd6  mov     edi, r13d
0x180007bd9  mov     [rbp+57h+var_78], r13
0x180007bdd  mov     [rdx], dil
0x180007be0  mov     rsi, rcx
0x180007be3  mov     rax, [rax+30h]
0x180007be7  lea     rdx, [rbp+57h+arg_18]
0x180007beb  mov     r12d, r13d
0x180007bee  mov     [rbp+57h+var_68], r13
0x180007bf2  mov     [rbp+57h+var_60], r13d
0x180007bf6  mov     r14d, r13d
0x180007bf9  mov     [rbp+57h+var_58], r13
0x180007bfd  mov     [rbp+57h+var_50], r13
0x180007c01  mov     [rbp+57h+arg_18], r13d
0x180007c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c0a  mov     ecx, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180007c10  mov     ebx, eax
0x180007c12  test    eax, eax
0x180007c14  jns     short loc_180007C26
0x180007c16  test    ecx, ecx
0x180007c18  jnz     loc_180007D5F
0x180007c1e  test    eax, eax
0x180007c20  js      loc_180007D16
0x180007c26  mov     eax, [rbp+57h+arg_18]
0x180007c29  cmp     eax, 2
0x180007c2c  jz      loc_180007D84
0x180007c32  cmp     eax, 1
0x180007c35  jnz     loc_1800081ED
0x180007c3b  mov     rax, [rsi]
0x180007c3e  lea     r9, [rbp+57h+arg_8]
0x180007c42  xor     r8d, r8d
0x180007c45  mov     dword ptr [rbp+57h+arg_8], r13d
0x180007c49  xor     edx, edx
0x180007c4b  mov     rcx, rsi
0x180007c4e  mov     rax, [rax+38h]
0x180007c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c57  mov     ebx, eax
0x180007c59  test    eax, eax
0x180007c5b  jns     short loc_180007C75
0x180007c5d  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180007c63  jz      loc_180007D16
0x180007c69  mov     ecx, eax; int
0x180007c6b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007c70  jmp     loc_180007D16
0x180007c75  mov     eax, dword ptr [rbp+57h+arg_8]
0x180007c78  cmp     eax, 90h
0x180007c7d  jb      loc_180007D68
0x180007c83  mov     ecx, eax; unsigned __int64
0x180007c85  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007c8a  mov     rdi, rax
0x180007c8d  test    rax, rax
0x180007c90  jz      loc_180007FDD
0x180007c96  mov     rax, [rsi]
0x180007c99  lea     r9, [rbp+57h+var_90]
0x180007c9d  mov     edx, dword ptr [rbp+57h+arg_8]
0x180007ca0  mov     r8, rdi
0x180007ca3  mov     rcx, rsi
0x180007ca6  mov     [rbp+57h+var_90], r13d
0x180007caa  mov     rax, [rax+38h]
0x180007cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cb3  mov     ebx, eax
0x180007cb5  test    eax, eax
0x180007cb7  jns     short loc_180007CCA
0x180007cb9  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180007cc0  jnz     loc_180007D7B
0x180007cc6  test    eax, eax
0x180007cc8  js      short loc_180007D16
0x180007cca  mov     esi, dword ptr [rbp+57h+arg_8]
0x180007ccd  cmp     esi, [rbp+57h+var_90]
0x180007cd0  jnz     loc_180008127
0x180007cd6  cmp     esi, 0C48h
0x180007cdc  jnz     loc_180007DC4
0x180007ce2  mov     eax, [rdi+34h]
0x180007ce5  bswap   eax
0x180007ce7  cmp     eax, 73524742h
0x180007cec  jnz     loc_180007DD0
0x180007cf2  mov     eax, [rdi+50h]
0x180007cf5  bswap   eax
0x180007cf7  cmp     eax, 57475449h
0x180007cfc  jz      loc_180007DD0
0x180007d02  mov     eax, [rdi+30h]
0x180007d05  bswap   eax
0x180007d07  cmp     eax, 57475449h
0x180007d0c  jz      loc_180007DD0
0x180007d12  mov     byte ptr [r15], 1
0x180007d16  mov     rcx, rdi; Block
0x180007d19  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007d1e  mov     rcx, r12; Block
0x180007d21  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007d26  mov     rcx, [rbp+57h+Block]; Block
0x180007d2a  test    rcx, rcx
0x180007d2d  jnz     loc_1800081FA
0x180007d33  test    r14, r14
0x180007d36  jnz     loc_180008209
0x180007d3c  mov     rcx, [rbp+57h+Block]; Block
0x180007d40  test    rcx, rcx
0x180007d43  jnz     loc_18000822C
0x180007d49  mov     eax, ebx
0x180007d4b  add     rsp, 88h
0x180007d52  pop     r15
0x180007d54  pop     r14
0x180007d56  pop     r13
0x180007d58  pop     r12
0x180007d5a  pop     rdi
0x180007d5b  pop     rsi
0x180007d5c  pop     rbx
0x180007d5d  pop     rbp
0x180007d5e  retn
0x180007d5f  mov     ecx, eax; int
0x180007d61  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007d66  jmp     short loc_180007D16
0x180007d68  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180007d6e  jnz     loc_180007E7B
0x180007d74  mov     ebx, 800707DBh
0x180007d79  jmp     short loc_180007D16
0x180007d7b  mov     ecx, eax; int
0x180007d7d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007d82  jmp     short loc_180007D16
0x180007d84  mov     rax, [rsi]
0x180007d87  lea     rdx, [rbp+57h+arg_0]
0x180007d8b  mov     rcx, rsi
0x180007d8e  mov     [rbp+57h+arg_0], r13d
0x180007d92  mov     rax, [rax+40h]
0x180007d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d9b  mov     ebx, eax
0x180007d9d  test    eax, eax
0x180007d9f  jns     short loc_180007DB5
0x180007da1  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x180007da7  jnz     loc_180007E9D
0x180007dad  test    eax, eax
0x180007daf  js      loc_180007D16
0x180007db5  cmp     [rbp+57h+arg_0], 2
0x180007db9  setnz   al
0x180007dbc  mov     [r15], al
0x180007dbf  jmp     loc_180007D16
0x180007dc4  cmp     esi, 20Ch
0x180007dca  jz      loc_180008133
0x180007dd0  cmp     [r15], r12b
0x180007dd3  jnz     loc_180007D16
0x180007dd9  mov     r8d, esi; Size
0x180007ddc  lea     rcx, [rbp+57h+Block]; this
0x180007de0  mov     rdx, rdi; Src
0x180007de3  call    ?InitProfile@ColorProfileParser@@QEAAJPEBXI@Z; ColorProfileParser::InitProfile(void const *,uint)
0x180007de8  test    eax, eax
0x180007dea  js      short loc_180007DF8
0x180007dec  mov     eax, [rdi+8]
0x180007def  bswap   eax
0x180007df1  cmp     eax, 4000000h
0x180007df6  jb      short loc_180007E01
0x180007df8  mov     r14, [rbp+57h+var_58]
0x180007dfc  jmp     loc_180007D16
0x180007e01  mov     eax, [rdi+10h]
0x180007e04  bswap   eax
0x180007e06  cmp     eax, 52474220h
0x180007e0b  jnz     short loc_180007DF8
0x180007e0d  mov     r14, [rbp+57h+var_58]
0x180007e11  mov     esi, r13d
0x180007e14  mov     r10d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180007e1b  mov     [rbp+57h+arg_0], 41324230h
0x180007e22  mov     [rbp+57h+arg_4], 42324130h
0x180007e29  cmp     esi, 2
0x180007e2c  jnb     loc_180008176
0x180007e32  mov     edx, [r14+80h]
0x180007e39  mov     ecx, r13d
0x180007e3c  mov     eax, esi
0x180007e3e  mov     r8d, [rbp+rax*4+57h+arg_0]
0x180007e43  test    edx, edx
0x180007e45  jz      short loc_180007E6A
0x180007e47  nop     word ptr [rax+rax+00000000h]
0x180007e50  mov     eax, ecx
0x180007e52  add     rax, 0Bh
0x180007e56  lea     rax, [rax+rax*2]
0x180007e5a  cmp     r8d, [r14+rax*4]
0x180007e5e  jz      loc_180008159
0x180007e64  inc     ecx
0x180007e66  cmp     ecx, edx
0x180007e68  jb      short loc_180007E50
0x180007e6a  cmp     ecx, edx
0x180007e6c  jb      loc_180008159
0x180007e72  test    r10d, r10d
0x180007e75  jnz     short loc_180007E8A
0x180007e77  inc     esi
0x180007e79  jmp     short loc_180007E29
0x180007e7b  mov     ecx, 800707DBh; int
0x180007e80  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007e85  jmp     loc_180007D74
0x180007e8a  mov     ecx, 800707DCh; int
0x180007e8f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007e94  mov     r10d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180007e9b  jmp     short loc_180007E77
0x180007e9d  mov     ecx, eax; int
0x180007e9f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007ea4  jmp     loc_180007D16
0x180007ea9  test    r13b, r13b
0x180007eac  jz      loc_180007F8D
0x180007eb2  mov     edx, [r14+80h]
0x180007eb9  shl     rax, 4
0x180007ebd  mov     [rbp+57h+var_88], rax
0x180007ec1  mov     r8d, [rax+rcx+0Ch]
0x180007ec6  xor     ecx, ecx
0x180007ec8  test    edx, edx
0x180007eca  jz      short loc_180007EEA
0x180007ecc  nop     dword ptr [rax+00h]
0x180007ed0  mov     eax, ecx
0x180007ed2  add     rax, 0Bh
0x180007ed6  lea     rax, [rax+rax*2]
0x180007eda  cmp     r8d, [r14+rax*4]
0x180007ede  jz      loc_180008192
0x180007ee4  inc     ecx
0x180007ee6  cmp     ecx, edx
0x180007ee8  jb      short loc_180007ED0
0x180007eea  cmp     ecx, edx
0x180007eec  jb      loc_180008192
0x180007ef2  test    r10d, r10d
0x180007ef5  jnz     loc_180007FA4
0x180007efb  lea     rcx, off_180040010; "XYZ "
0x180007f02  mov     r9d, dword ptr [rbp+57h+Size]
0x180007f06  xor     r13b, r13b
0x180007f09  mov     byte ptr [rbp+57h+arg_0], r13b
0x180007f0d  mov     eax, [rbp+57h+var_8C]
0x180007f10  inc     eax
0x180007f12  mov     [rbp+57h+var_8C], eax
0x180007f15  cmp     eax, 6
0x180007f18  jb      short loc_180007EA9
0x180007f1a  test    r13b, r13b
0x180007f1d  jz      short loc_180007F8D
0x180007f1f  mov     ecx, r9d; unsigned __int64
0x180007f22  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007f27  mov     r12, rax
0x180007f2a  test    rax, rax
0x180007f2d  jz      loc_1800080E2
0x180007f33  xor     esi, esi
0x180007f35  lea     rcx, off_180040010; "XYZ "
0x180007f3c  cmp     esi, 6
0x180007f3f  jnb     loc_180008112
0x180007f45  test    r13b, r13b
0x180007f48  jz      short loc_180007F8D
0x180007f4a  mov     r13d, esi
0x180007f4d  mov     r9, r12
0x180007f50  add     r13, r13
0x180007f53  mov     eax, [rcx+r13*8+8]
0x180007f58  mov     edx, [rcx+r13*8+0Ch]
0x180007f5d  lea     rcx, [rbp+57h+Block]
0x180007f61  mov     dword ptr [rbp+57h+Size], eax
0x180007f64  lea     rax, [rbp+57h+Size]
0x180007f68  mov     [rsp+0C0h+var_A0], rax
0x180007f6d  call    ?GetColorProfileElement@ColorProfileParser@@QEAAJW4icTagSignature@@IPEAEPEAI@Z; ColorProfileParser::GetColorProfileElement(icTagSignature,uint,uchar *,uint *)
0x180007f72  mov     ebx, eax
0x180007f74  test    eax, eax
0x180007f76  jns     loc_1800081AD
0x180007f7c  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180007f83  jnz     short loc_180007F95
0x180007f85  test    eax, eax
0x180007f87  jns     loc_1800081AD
0x180007f8d  xor     r13d, r13d
0x180007f90  jmp     loc_180007D16
0x180007f95  mov     ecx, eax; int
0x180007f97  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007f9c  xor     r13d, r13d
0x180007f9f  jmp     loc_180007D16
0x180007fa4  mov     ecx, 800707DCh; int
0x180007fa9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180007fae  mov     r10d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180007fb5  jmp     loc_180007EFB
0x180007fba  test    r10d, r10d
0x180007fbd  jz      loc_180007D16
0x180007fc3  mov     ecx, 80070216h
0x180007fc8  jmp     loc_180007D61
0x180007fcd  test    r10d, r10d
0x180007fd0  jz      loc_180007EFB
0x180007fd6  mov     ecx, 80070216h
0x180007fdb  jmp     short loc_180007FA9
0x180007fdd  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180007fe4  mov     ebx, 8007000Eh
0x180007fe9  jz      loc_180007D16
0x180007fef  mov     ecx, ebx
0x180007ff1  jmp     loc_180007D61
0x180007ff6  test    r10d, r10d
0x180007ff9  jz      loc_180007D16
0x180007fff  mov     ecx, 80070057h; int
0x180008004  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180008009  jmp     loc_180007D16
0x18000800e  mov     eax, [rax+88h]
0x180008014  add     ecx, eax
0x180008016  cmp     ecx, eax
0x180008018  jb      short loc_180007FBA
0x18000801a  cmp     ecx, [rbp+57h+var_60]
  ... truncated ...
```
