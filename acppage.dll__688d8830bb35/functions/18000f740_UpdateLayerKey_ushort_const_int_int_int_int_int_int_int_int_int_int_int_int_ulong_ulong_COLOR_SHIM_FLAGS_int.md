# UpdateLayerKey(ushort const *,int,int,int,int,int,int,int,int,int,int,int,int,ulong,ulong,_COLOR_SHIM_FLAGS *,int)

- ea: `0x18000f740`
- end: `0x18000fb0e`
- name: `?UpdateLayerKey@@YAHPEBGHHHHHHHHHHHHKKPEAU_COLOR_SHIM_FLAGS@@H@Z`
- size: `974`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, int, int, int, int, int, int, int, int, int, int, int, unsigned int, unsigned int, struct _COLOR_SHIM_FLAGS *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000f4ac`

## callees

- `0x18000ec5c`
- `0x18000f740`
- `0x180017010`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x18000f765`
- `KERNEL32!DecodePointer` at `0x18000f765`

## pseudocode

```c
__int64 __fastcall UpdateLayerKey(
        const unsigned __int16 *a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12,
        int a13,
        unsigned int a14,
        unsigned int a15,
        struct _COLOR_SHIM_FLAGS *a16,
        unsigned int a17)
{
  __int64 v18; // rbx
  unsigned int v21; // r12d
  int (*v22)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, int); // rax
  int (*v23)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, int); // rsi
  unsigned int i; // ebx
  int v25; // ebx
  __int64 v26; // r8
  int v27; // edi
  __int64 v28; // rbx
  int v29; // ebx
  __int64 v30; // r8
  int v31; // ebx
  _WORD *v32; // rdx
  __int64 v33; // r8
  int v34; // ebx
  _WORD *v35; // rdx
  __int64 v36; // r8
  int v37; // ebx
  unsigned __int64 v38; // rdx
  unsigned int v39; // ecx

  v18 = a2;
  v21 = 0;
  v22 = (int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, int))DecodePointer(g_pfnSetPermLayerState);
  v23 = v22;
  if ( v22 )
  {
    if ( a3 )
    {
      if ( (_DWORD)v18 == -1 )
      {
        for ( i = 0; i < 0xA; ++i )
          ((void (__fastcall *)(const unsigned __int16 *, wchar_t *, _QWORD, _QWORD, _DWORD))v23)(
            a1,
            &aWin95[38 * i],
            0,
            a17,
            0);
      }
      else if ( !((unsigned int (__fastcall *)(const unsigned __int16 *, wchar_t *, __int64, _QWORD, int))v22)(
                   a1,
                   &aWin95[38 * v18],
                   8,
                   a17,
                   1) )
      {
        return v21;
      }
    }
    if ( a5 )
    {
      v25 = 0;
      while ( 1 )
      {
        v26 = 8;
        if ( v25 != a4 )
          v26 = 0;
        if ( !((unsigned int (__fastcall *)(const unsigned __int16 *, wchar_t *, __int64, _QWORD, bool))v23)(
                a1,
                &a256color[38 * v25],
                v26,
                a17,
                v25 == a4) )
          break;
        if ( (unsigned int)++v25 >= 2 )
          goto LABEL_14;
      }
    }
    else
    {
LABEL_14:
      if ( !a7 )
        goto LABEL_22;
      v27 = -1;
      v28 = 0;
      do
      {
        if ( dword_18001AA84[3 * v28] == a6 )
        {
          v27 = v28;
        }
        else if ( !(unsigned int)SetComplexPermLayerStates(v23, a1, dword_18001AA80[3 * v28], 0, a17, 0) )
        {
          return v21;
        }
        v28 = (unsigned int)(v28 + 1);
      }
      while ( (int)v28 < 3 );
      if ( v27 == -1 || (unsigned int)SetComplexPermLayerStates(v23, a1, dword_18001AA80[3 * v27], 8u, a17, 1) )
      {
LABEL_22:
        if ( a9 )
        {
          v29 = 0;
          while ( 1 )
          {
            v30 = 8;
            if ( v29 != a8 )
              v30 = 0;
            if ( !((unsigned int (__fastcall *)(const unsigned __int16 *, wchar_t *, __int64, _QWORD, bool))v23)(
                    a1,
                    &aPerprocesssyst[38 * v29],
                    v30,
                    a17,
                    v29 == a8) )
              break;
            if ( (unsigned int)++v29 >= 2 )
              goto LABEL_28;
          }
        }
        else
        {
LABEL_28:
          if ( a11 || a10 == -1 || a10 >= 0 && (unsigned __int64)a10 < 4 && !*((_WORD *)qword_18001A930 + 38 * a10) )
          {
            v31 = 0;
            while ( 1 )
            {
              v32 = (_WORD *)qword_18001A930 + 38 * v31;
              if ( *v32 )
              {
                v33 = 8;
                if ( v31 != a10 )
                  v33 = 0;
                if ( !((unsigned int (__fastcall *)(const unsigned __int16 *, _WORD *, __int64, _QWORD, bool))v23)(
                        a1,
                        v32,
                        v33,
                        a17,
                        v31 == a10) )
                  break;
              }
              if ( (unsigned int)++v31 >= 4 )
                goto LABEL_39;
            }
          }
          else
          {
LABEL_39:
            if ( a13 || a12 == -1 || a12 >= 0 && (unsigned __int64)a12 < 4 && !*((_WORD *)qword_18001A6B0 + 38 * a12) )
            {
              v34 = 0;
              while ( 1 )
              {
                v35 = (_WORD *)qword_18001A6B0 + 38 * v34;
                if ( *v35 )
                {
                  v36 = 8;
                  if ( v34 != a12 )
                    v36 = 0;
                  if ( !((unsigned int (__fastcall *)(const unsigned __int16 *, _WORD *, __int64, _QWORD, bool))v23)(
                          a1,
                          v35,
                          v36,
                          a17,
                          v34 == a12) )
                    break;
                }
                if ( (unsigned int)++v34 >= 4 )
                  goto LABEL_50;
              }
            }
            else
            {
LABEL_50:
              v37 = 0;
              while ( 1 )
              {
                v38 = 108LL * v37;
                v39 = a14 & *(_DWORD *)((_BYTE *)qword_18001A190 + v38);
                if ( ((*(_DWORD *)((_BYTE *)qword_18001A190 + v38) & a15) != 0 || !v39)
                  && !((unsigned int (__fastcall *)(const unsigned __int16 *, __int16 *, _QWORD, _QWORD, unsigned int))v23)(
                        a1,
                        &_ImageBase[v38 / 2 + 53400],
                        v39 != 0 ? 8 : 0,
                        a17,
                        v39) )
                {
                  break;
                }
                if ( (unsigned int)++v37 >= 0xD )
                {
                  if ( !a16
                    || ((unsigned int (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, _QWORD, _QWORD, int))v23)(
                         a1,
                         L"TRANSFORMLEGACYCOLORMANAGED",
                         (*(_DWORD *)a16 & 1) != 0 ? 8 : 0,
                         a17,
                         -(*(_DWORD *)a16 & 1))
                    && ((unsigned int (__fastcall *)(const unsigned __int16 *, const unsigned __int16 *, _QWORD, _QWORD, int))v23)(
                         a1,
                         L"DISABLETRANSFORMLEGACYCOLORMANAGED",
                         __CFSHR__(*(_DWORD *)a16, 2) ? 8 : 0,
                         a17,
                         -__CFSHR__(*(_DWORD *)a16, 2)) )
                  {
                    return 1;
                  }
                  return v21;
                }
              }
            }
          }
        }
      }
    }
  }
  return v21;
}

```

## disassembly

```asm
0x18000f740  push    rbx
0x18000f742  push    rbp
0x18000f743  push    rsi
0x18000f744  push    rdi
0x18000f745  push    r12
0x18000f747  push    r14
0x18000f749  push    r15
0x18000f74b  sub     rsp, 30h
0x18000f74f  mov     r14, rcx
0x18000f752  movsxd  rbx, edx
0x18000f755  mov     rcx, cs:?g_pfnSetPermLayerState@@3P6AHPEBG0KHH@ZEA; Ptr
0x18000f75c  mov     r15d, r9d
0x18000f75f  mov     edi, r8d
0x18000f762  xor     r12d, r12d
0x18000f765  call    cs:__imp_DecodePointer
0x18000f76b  mov     rsi, rax
0x18000f76e  test    rax, rax
0x18000f771  jz      loc_18000FAFC
0x18000f777  mov     ebp, [rsp+68h+arg_80]
0x18000f77e  test    edi, edi
0x18000f780  jz      short loc_18000F7E0
0x18000f782  lea     rdi, aWin95; "WIN95"
0x18000f789  cmp     ebx, 0FFFFFFFFh
0x18000f78c  jz      short loc_18000F7B7
0x18000f78e  imul    rdx, rbx, 4Ch ; 'L'
0x18000f792  mov     r9d, ebp
0x18000f795  mov     [rsp+68h+var_48], 1
0x18000f79d  add     rdx, rdi
0x18000f7a0  lea     r8d, [r12+8]
0x18000f7a5  mov     rcx, r14
0x18000f7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7ad  test    eax, eax
0x18000f7af  jz      loc_18000FAFC
0x18000f7b5  jmp     short loc_18000F7E0
0x18000f7b7  xor     ebx, ebx
0x18000f7b9  movsxd  rax, ebx
0x18000f7bc  mov     r9d, ebp
0x18000f7bf  imul    rdx, rax, 4Ch ; 'L'
0x18000f7c3  xor     r8d, r8d
0x18000f7c6  mov     [rsp+68h+var_48], r12d
0x18000f7cb  add     rdx, rdi
0x18000f7ce  mov     rcx, r14
0x18000f7d1  mov     rax, rsi
0x18000f7d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7d9  inc     ebx
0x18000f7db  cmp     ebx, 0Ah
0x18000f7de  jb      short loc_18000F7B9
0x18000f7e0  cmp     [rsp+68h+arg_20], r12d
0x18000f7e8  jz      short loc_18000F833
0x18000f7ea  xor     ebx, ebx
0x18000f7ec  xor     ecx, ecx
0x18000f7ee  mov     r9d, ebp
0x18000f7f1  cmp     ebx, r15d
0x18000f7f4  setz    cl
0x18000f7f7  xor     eax, eax
0x18000f7f9  mov     [rsp+68h+var_48], ecx
0x18000f7fd  cmp     ebx, r15d
0x18000f800  mov     rcx, r14
0x18000f803  lea     r8d, [rax+8]
0x18000f807  cmovnz  r8d, eax
0x18000f80b  movsxd  rax, ebx
0x18000f80e  imul    rdx, rax, 4Ch ; 'L'
0x18000f812  lea     rax, a256color; "256COLOR"
0x18000f819  add     rdx, rax
0x18000f81c  mov     rax, rsi
0x18000f81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f824  test    eax, eax
0x18000f826  jz      loc_18000FAFC
0x18000f82c  inc     ebx
0x18000f82e  cmp     ebx, 2
0x18000f831  jb      short loc_18000F7EC
0x18000f833  lea     rcx, __ImageBase
0x18000f83a  cmp     [rsp+68h+arg_30], r12d
0x18000f842  jz      loc_18000F8D5
0x18000f848  mov     r15d, [rsp+68h+arg_28]
0x18000f850  or      edi, 0FFFFFFFFh
0x18000f853  xor     ebx, ebx
0x18000f855  lea     r8, [rbx+rbx*2]
0x18000f859  cmp     ds:rva dword_18001AA84[rcx+r8*4], r15d
0x18000f861  jnz     short loc_18000F867
0x18000f863  mov     edi, ebx
0x18000f865  jmp     short loc_18000F895
0x18000f867  mov     r8d, ds:rva dword_18001AA80[rcx+r8*4]; unsigned int
0x18000f86f  xor     r9d, r9d; unsigned int
0x18000f872  mov     rcx, rsi; int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, int)
0x18000f875  mov     [rsp+68h+var_40], r12d; int
0x18000f87a  mov     rdx, r14; unsigned __int16 *
0x18000f87d  mov     [rsp+68h+var_48], ebp; int
0x18000f881  call    ?SetComplexPermLayerStates@@YAHP6AHPEBG0KHH@Z0KKHH@Z; SetComplexPermLayerStates(int (*)(ushort const *,ushort const *,ulong,int,int),ushort const *,ulong,ulong,int,int)
0x18000f886  test    eax, eax
0x18000f888  jz      loc_18000FAFC
0x18000f88e  lea     rcx, __ImageBase
0x18000f895  inc     ebx
0x18000f897  cmp     ebx, 3
0x18000f89a  jl      short loc_18000F855
0x18000f89c  cmp     edi, 0FFFFFFFFh
0x18000f89f  jz      short loc_18000F8D5
0x18000f8a1  movsxd  rax, edi
0x18000f8a4  mov     r9d, 8; unsigned int
0x18000f8aa  mov     [rsp+68h+var_40], 1; int
0x18000f8b2  mov     rdx, r14; unsigned __int16 *
0x18000f8b5  mov     [rsp+68h+var_48], ebp; int
0x18000f8b9  lea     r8, [rax+rax*2]
0x18000f8bd  mov     r8d, ds:rva dword_18001AA80[rcx+r8*4]; unsigned int
0x18000f8c5  mov     rcx, rsi; int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, int)
0x18000f8c8  call    ?SetComplexPermLayerStates@@YAHP6AHPEBG0KHH@Z0KKHH@Z; SetComplexPermLayerStates(int (*)(ushort const *,ushort const *,ulong,int,int),ushort const *,ulong,ulong,int,int)
0x18000f8cd  test    eax, eax
0x18000f8cf  jz      loc_18000FAFC
0x18000f8d5  cmp     [rsp+68h+arg_40], r12d
0x18000f8dd  jz      short loc_18000F930
0x18000f8df  xor     ebx, ebx
0x18000f8e1  xor     ecx, ecx
0x18000f8e3  mov     r9d, ebp
0x18000f8e6  cmp     ebx, [rsp+68h+arg_38]
0x18000f8ed  setz    cl
0x18000f8f0  xor     eax, eax
0x18000f8f2  cmp     ebx, [rsp+68h+arg_38]
0x18000f8f9  mov     [rsp+68h+var_48], ecx
0x18000f8fd  mov     rcx, r14
0x18000f900  lea     r8d, [rax+8]
0x18000f904  cmovnz  r8d, eax
0x18000f908  movsxd  rax, ebx
0x18000f90b  imul    rdx, rax, 4Ch ; 'L'
0x18000f90f  lea     rax, aPerprocesssyst; "PERPROCESSSYSTEMDPIFORCEOFF"
0x18000f916  add     rdx, rax
0x18000f919  mov     rax, rsi
0x18000f91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f921  test    eax, eax
0x18000f923  jz      loc_18000FAFC
0x18000f929  inc     ebx
0x18000f92b  cmp     ebx, 2
0x18000f92e  jb      short loc_18000F8E1
0x18000f930  lea     r15, qword_18001A930
0x18000f937  movsxd  rdi, [rsp+68h+arg_48]
0x18000f93f  cmp     [rsp+68h+arg_50], r12d
0x18000f947  jnz     short loc_18000F968
0x18000f949  cmp     edi, 0FFFFFFFFh
0x18000f94c  jz      short loc_18000F968
0x18000f94e  test    edi, edi
0x18000f950  js      short loc_18000F9AD
0x18000f952  mov     rax, rdi
0x18000f955  cmp     rdi, 4
0x18000f959  jnb     short loc_18000F9AD
0x18000f95b  imul    rcx, rax, 4Ch ; 'L'
0x18000f95f  xor     eax, eax
0x18000f961  cmp     ax, [rcx+r15]
0x18000f966  jnz     short loc_18000F9AD
0x18000f968  xor     ebx, ebx
0x18000f96a  movsxd  rax, ebx
0x18000f96d  imul    rdx, rax, 4Ch ; 'L'
0x18000f971  xor     eax, eax
0x18000f973  add     rdx, r15
0x18000f976  cmp     ax, [rdx]
0x18000f979  jz      short loc_18000F9A6
0x18000f97b  xor     ecx, ecx
0x18000f97d  lea     r8d, [rax+8]
0x18000f981  cmp     ebx, edi
0x18000f983  mov     r9d, ebp
0x18000f986  setz    cl
0x18000f989  cmp     ebx, edi
0x18000f98b  mov     [rsp+68h+var_48], ecx
0x18000f98f  mov     rcx, r14
0x18000f992  cmovnz  r8d, eax
0x18000f996  mov     rax, rsi
0x18000f999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f99e  test    eax, eax
0x18000f9a0  jz      loc_18000FAFC
0x18000f9a6  inc     ebx
0x18000f9a8  cmp     ebx, 4
0x18000f9ab  jb      short loc_18000F96A
0x18000f9ad  lea     r15, qword_18001A6B0
0x18000f9b4  movsxd  rdi, [rsp+68h+arg_58]
0x18000f9bc  cmp     [rsp+68h+arg_60], r12d
0x18000f9c4  jnz     short loc_18000F9E5
0x18000f9c6  cmp     edi, 0FFFFFFFFh
0x18000f9c9  jz      short loc_18000F9E5
0x18000f9cb  test    edi, edi
0x18000f9cd  js      short loc_18000FA2A
0x18000f9cf  mov     rax, rdi
0x18000f9d2  cmp     rdi, 4
0x18000f9d6  jnb     short loc_18000FA2A
0x18000f9d8  imul    rcx, rax, 4Ch ; 'L'
0x18000f9dc  xor     eax, eax
0x18000f9de  cmp     ax, [rcx+r15]
0x18000f9e3  jnz     short loc_18000FA2A
0x18000f9e5  xor     ebx, ebx
0x18000f9e7  movsxd  rax, ebx
0x18000f9ea  imul    rdx, rax, 4Ch ; 'L'
0x18000f9ee  xor     eax, eax
0x18000f9f0  add     rdx, r15
0x18000f9f3  cmp     ax, [rdx]
0x18000f9f6  jz      short loc_18000FA23
0x18000f9f8  xor     ecx, ecx
0x18000f9fa  lea     r8d, [rax+8]
0x18000f9fe  cmp     ebx, edi
0x18000fa00  mov     r9d, ebp
0x18000fa03  setz    cl
0x18000fa06  cmp     ebx, edi
0x18000fa08  mov     [rsp+68h+var_48], ecx
0x18000fa0c  mov     rcx, r14
0x18000fa0f  cmovnz  r8d, eax
0x18000fa13  mov     rax, rsi
0x18000fa16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa1b  test    eax, eax
0x18000fa1d  jz      loc_18000FAFC
0x18000fa23  inc     ebx
0x18000fa25  cmp     ebx, 4
0x18000fa28  jb      short loc_18000F9E7
0x18000fa2a  mov     edi, [rsp+68h+arg_70]
0x18000fa31  lea     r15, __ImageBase
0x18000fa38  xor     ebx, ebx
0x18000fa3a  movsxd  rax, ebx
0x18000fa3d  imul    rdx, rax, 6Ch ; 'l'
0x18000fa41  mov     eax, [rdx+r15+1A190h]
0x18000fa49  mov     ecx, eax
0x18000fa4b  and     ecx, [rsp+68h+arg_68]
0x18000fa52  test    edi, eax
0x18000fa54  jnz     short loc_18000FA5A
0x18000fa56  test    ecx, ecx
0x18000fa58  jnz     short loc_18000FA85
0x18000fa5a  mov     eax, ecx
0x18000fa5c  mov     [rsp+68h+var_48], ecx
0x18000fa60  neg     eax
0x18000fa62  lea     rdx, [rdx+1A130h]
0x18000fa69  mov     r9d, ebp
0x18000fa6c  mov     rcx, r14
0x18000fa6f  sbb     r8d, r8d
0x18000fa72  mov     rax, rsi
0x18000fa75  and     r8d, 8
0x18000fa79  add     rdx, r15
0x18000fa7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa81  test    eax, eax
0x18000fa83  jz      short loc_18000FAFC
0x18000fa85  inc     ebx
0x18000fa87  cmp     ebx, 0Dh
0x18000fa8a  jb      short loc_18000FA3A
0x18000fa8c  mov     rbx, [rsp+68h+arg_78]
0x18000fa94  test    rbx, rbx
0x18000fa97  jz      short loc_18000FAF6
0x18000fa99  mov     ecx, [rbx]
0x18000fa9b  lea     rdx, aTransformlegac; "TRANSFORMLEGACYCOLORMANAGED"
0x18000faa2  shr     ecx, 1
0x18000faa4  mov     r9d, ebp
0x18000faa7  sbb     ecx, ecx
0x18000faa9  mov     eax, ecx
0x18000faab  mov     [rsp+68h+var_48], ecx
0x18000faaf  neg     eax
0x18000fab1  mov     rcx, r14
0x18000fab4  mov     rax, rsi
0x18000fab7  sbb     r8d, r8d
0x18000faba  and     r8d, 8
0x18000fabe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fac3  test    eax, eax
0x18000fac5  jz      short loc_18000FAFC
0x18000fac7  mov     ecx, [rbx]
0x18000fac9  lea     rdx, aDisabletransfo; "DISABLETRANSFORMLEGACYCOLORMANAGED"
0x18000fad0  shr     ecx, 2
0x18000fad3  mov     r9d, ebp
0x18000fad6  sbb     ecx, ecx
0x18000fad8  mov     eax, ecx
0x18000fada  mov     [rsp+68h+var_48], ecx
0x18000fade  neg     eax
0x18000fae0  mov     rcx, r14
0x18000fae3  mov     rax, rsi
0x18000fae6  sbb     r8d, r8d
0x18000fae9  and     r8d, 8
0x18000faed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faf2  test    eax, eax
0x18000faf4  jz      short loc_18000FAFC
0x18000faf6  mov     r12d, 1
0x18000fafc  mov     eax, r12d
0x18000faff  add     rsp, 30h
0x18000fb03  pop     r15
0x18000fb05  pop     r14
0x18000fb07  pop     r12
0x18000fb09  pop     rdi
0x18000fb0a  pop     rsi
0x18000fb0b  pop     rbp
0x18000fb0c  pop     rbx
0x18000fb0d  retn
```
