# CGenerate::GenerateRegistry(ushort const *,ushort const *,int)

- ea: `0x14000b2e4`
- end: `0x14000b956`
- name: `?GenerateRegistry@CGenerate@@QEAAJPEBG0H@Z`
- size: `1650`
- prototype: `__int64 __fastcall(CGenerate *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140007c10`

## callees

- `0x14000661c`
- `0x1400068c0`
- `0x1400073fc`
- `0x140008b28`
- `0x14000af24`
- `0x14000af6c`
- `0x14000aff8`
- `0x14000b070`
- `0x14000b0c8`
- `0x14000b170`
- `0x14000b218`
- `0x14000b2c0`
- `0x14000b2e4`

## import_xrefs

- `msvcrt!free` at `0x14000b50a`
- `msvcrt!free` at `0x14000b671`
- `msvcrt!free` at `0x14000b797`
- `msvcrt!free` at `0x14000b80d`
- `msvcrt!free` at `0x14000b8ad`
- `msvcrt!free` at `0x14000b931`
- `msvcrt!free` at `0x14000b50a`
- `msvcrt!free` at `0x14000b671`
- `msvcrt!free` at `0x14000b797`
- `msvcrt!free` at `0x14000b80d`
- `msvcrt!free` at `0x14000b8ad`
- `msvcrt!free` at `0x14000b931`
- `msvcrt!wcslen` at `0x14000b57a`
- `msvcrt!wcslen` at `0x14000b57a`
- `msvcrt!memcpy` at `0x14000b5ec`
- `msvcrt!memcpy` at `0x14000b635`
- `msvcrt!memcpy` at `0x14000b5ec`
- `msvcrt!memcpy` at `0x14000b635`
- `msvcrt!malloc` at `0x14000b5b0`
- `msvcrt!malloc` at `0x14000b5b0`
- `wbemcomn!Throttle` at `0x14000b856`
- `wbemcomn!Throttle` at `0x14000b856`

## pseudocode

```c
__int64 __fastcall CGenerate::GenerateRegistry(
        CGenerate *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  int appended; // r12d
  __int64 *v5; // rdx
  __int64 i; // rbx
  CGenerate *v7; // rcx
  _DWORD *Structure; // rsi
  unsigned int v9; // r13d
  __int64 v10; // rdi
  __int64 v11; // r13
  _DWORD *v12; // rbx
  __int64 v13; // rax
  CGenerate *v14; // rcx
  __int64 v15; // r12
  __int64 v16; // r8
  __int64 v17; // rax
  _DWORD *v18; // r14
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // rax
  unsigned int j; // eax
  __int64 v23; // rcx
  const wchar_t *v24; // rcx
  size_t v25; // rax
  unsigned int *v26; // rax
  unsigned int *v27; // r14
  unsigned int *v28; // rax
  CGenerate *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // r12
  __int64 v32; // r8
  __int64 v33; // rax
  _DWORD *v34; // r14
  __int64 v35; // rax
  __int64 v36; // r8
  __int64 v37; // rax
  __int64 k; // rax
  const unsigned __int16 *v39; // rdx
  const unsigned __int16 *v40; // rcx
  unsigned __int8 *v41; // r8
  unsigned int v42; // r9d
  __int64 v44; // [rsp+0h] [rbp-E8h] BYREF
  _DWORD *v45; // [rsp+30h] [rbp-B8h] BYREF
  unsigned int IndexRegistry; // [rsp+38h] [rbp-B0h]
  size_t v47; // [rsp+40h] [rbp-A8h]
  unsigned int v48; // [rsp+48h] [rbp-A0h]
  _DWORD *v49; // [rsp+50h] [rbp-98h] BYREF
  __int64 v50; // [rsp+58h] [rbp-90h]
  void *Block[2]; // [rsp+60h] [rbp-88h] BYREF
  __int64 **v52; // [rsp+70h] [rbp-78h]
  __int64 v53; // [rsp+78h] [rbp-70h]
  unsigned int *v54; // [rsp+80h] [rbp-68h]
  char v55[8]; // [rsp+88h] [rbp-60h] BYREF
  struct _SECURITY_ATTRIBUTES *v56; // [rsp+90h] [rbp-58h]
  int v58; // [rsp+F8h] [rbp+10h]
  int v59; // [rsp+100h] [rbp+18h]
  unsigned int v60; // [rsp+100h] [rbp+18h]
  int v61; // [rsp+100h] [rbp+18h]

  appended = 1;
  Block[0] = (void *)CPerformanceStructureManipulator<_WMI_PERFORMANCE,_WMI_PERFORMANCE,_WMI_PERF_NAMESPACE>::CreateStructure();
  if ( !Block[0] )
  {
    appended = -2147024882;
    goto LABEL_83;
  }
  dword_140024FB8 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v58 = i;
    if ( (unsigned int)i >= *((_DWORD *)this + 20) || appended < 0 )
      break;
    if ( !*((_QWORD *)this + 5 * i + 4) )
      continue;
    appended = 0;
    Structure = (_DWORD *)CPerformanceStructureManipulator<_WMI_PERF_NAMESPACE,_WMI_PERFORMANCE,_WMI_PERF_OBJECT>::CreateStructure(*((void **)this + 5 * i + 1));
    v49 = Structure;
    if ( Structure )
    {
      v9 = 0;
      v52 = (__int64 **)((char *)this + 40 * i + 24);
      v10 = **v52;
      v50 = v10;
      while ( 1 )
      {
        if ( (__int64 *)v10 == *v52 )
        {
          if ( appended >= 0 )
          {
            Structure[2] = v9;
            Structure[3] = i;
            appended = CPerformanceStructureManipulator<_WMI_PERF_NAMESPACE,_WMI_PERFORMANCE,_WMI_PERF_OBJECT>::AppendAlloc(
                         Block,
                         Structure);
          }
          goto LABEL_72;
        }
        if ( appended < 0 )
          goto LABEL_72;
        IndexRegistry = CGenerate::GenerateIndexRegistry(v7, 0);
        v11 = v10 + 40;
        v12 = (_DWORD *)CPerformanceStructureManipulator<_WMI_PERF_OBJECT,_WMI_PERF_NAMESPACE,_WMI_PERF_PROPERTY>::CreateStructure(*(void **)(*(_QWORD *)(v10 + 40) + 8LL));
        v45 = v12;
        if ( !v12 )
        {
          appended = -2147024882;
          goto LABEL_61;
        }
        Block[1] = (void *)(v10 + 40);
        v13 = *(_QWORD *)v11;
        if ( !*(_QWORD *)(*(_QWORD *)v11 + 72LL) )
        {
          if ( *(_DWORD *)(v13 + 56) )
          {
            v14 = 0;
            LODWORD(v47) = 0;
            v59 = 0;
            while ( 1 )
            {
              if ( appended < 0 )
                goto LABEL_61;
              v15 = (unsigned int)v14;
              v16 = *(_QWORD *)(*(_QWORD *)(v13 + 48) + 8LL * (_QWORD)v14);
              if ( *(_QWORD *)(v16 + 32) )
              {
                LODWORD(v47) = CGenerate::GenerateIndexRegistry(v14, 0);
                v21 = CPerformanceStructureManipulator<_WMI_PERF_PROPERTY,_WMI_PERF_OBJECT,_WMI_PERF_PROPERTY>::CreateStructure(*(void **)(v20 + 8));
                v18 = (_DWORD *)v21;
                if ( !v21 )
                {
LABEL_23:
                  appended = -2147024882;
                  goto LABEL_24;
                }
                *(_DWORD *)(v21 + 16) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 48LL) + 8 * v15) + 48LL);
                v19 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 48LL) + 8 * v15);
              }
              else
              {
                v17 = CPerformanceStructureManipulator<_WMI_PERF_PROPERTY,_WMI_PERF_OBJECT,_WMI_PERF_PROPERTY>::CreateStructure(*(void **)(v16 + 8));
                v18 = (_DWORD *)v17;
                if ( !v17 )
                  goto LABEL_23;
                *(_DWORD *)(v17 + 16) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 48LL) + 8 * v15) + 48LL);
                v19 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 48LL) + 8 * v15);
              }
              v18[5] = *(_DWORD *)(v19 + 52);
              v18[6] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 48LL) + 8 * v15) + 56LL);
              v18[3] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 48LL) + 8 * v15) + 16LL);
              v18[1] = v12[4];
              appended = CPerformanceStructureManipulator<_WMI_PERF_OBJECT,_WMI_PERF_NAMESPACE,_WMI_PERF_PROPERTY>::AppendAlloc(
                           &v45,
                           v18);
              v12 = v45;
LABEL_24:
              free(v18);
              v14 = (CGenerate *)(unsigned int)(v59 + 1);
              v59 = (int)v14;
              v13 = *(_QWORD *)v11;
              if ( (unsigned int)v14 >= *(_DWORD *)(*(_QWORD *)v11 + 56LL) )
              {
                if ( appended < 0 )
                  goto LABEL_61;
                if ( (_DWORD)v47 )
                  v12[2] = v47;
                goto LABEL_59;
              }
            }
          }
          goto LABEL_59;
        }
        for ( j = 0; ; j = v48 + 1 )
        {
          v48 = j;
          v23 = *(_QWORD *)v11;
          if ( j >= *(_DWORD *)(*(_QWORD *)v11 + 80LL) )
            break;
          if ( appended < 0 )
            goto LABEL_61;
          v53 = j;
          v24 = *(const wchar_t **)(*(_QWORD *)(v23 + 72) + 8LL * j);
          if ( v24 )
            v25 = wcslen(v24);
          else
            v25 = 0;
          v47 = v25;
          v60 = 2 * v25 + 18 + (((2 * (_BYTE)v25 + 2) & 7) != 0 ? 8 - ((2 * (_BYTE)v25 + 2) & 7) : 0);
          v26 = (unsigned int *)malloc(v60);
          v27 = v26;
          v54 = v26;
          if ( v26 )
          {
            memcpy(v26 + 2, *(const void **)(*(_QWORD *)(*(_QWORD *)v11 + 72LL) + 8 * v53), (unsigned int)(2 * v47 + 2));
            v27[1] = 2 * v47 + 2;
            *v27 = v60;
            if ( v12 && (v28 = (unsigned int *)_RA_realloc<_WMI_PERF_OBJECT>(v12), v12 = v28, (v45 = v28) != 0) )
            {
              memcpy((char *)v28 + *v28, v27, *v27);
              *v12 += *v27;
            }
            else
            {
              appended = -2147024882;
            }
            free(v27);
          }
          else
          {
            appended = -2147024882;
          }
          v29 = 0;
          LODWORD(v47) = 0;
          v30 = *(_QWORD *)v11;
          if ( *(_DWORD *)(*(_QWORD *)v11 + 56LL) )
          {
            v61 = 0;
            while ( 1 )
            {
              if ( appended < 0 )
                goto LABEL_56;
              v31 = (unsigned int)v29;
              v32 = *(_QWORD *)(*(_QWORD *)(v30 + 48) + 8LL * (_QWORD)v29);
              if ( *(_QWORD *)(v32 + 32) )
              {
                LODWORD(v47) = CGenerate::GenerateIndexRegistry(v29, 0);
                v37 = CPerformanceStructureManipulator<_WMI_PERF_PROPERTY,_WMI_PERF_OBJECT,_WMI_PERF_PROPERTY>::CreateStructure(*(void **)(v36 + 8));
                v34 = (_DWORD *)v37;
                if ( !v37 )
                {
LABEL_50:
                  appended = -2147024882;
                  goto LABEL_51;
                }
                *(_DWORD *)(v37 + 16) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 48LL) + 8 * v31) + 48LL);
                v35 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 48LL) + 8 * v31);
              }
              else
              {
                v33 = CPerformanceStructureManipulator<_WMI_PERF_PROPERTY,_WMI_PERF_OBJECT,_WMI_PERF_PROPERTY>::CreateStructure(*(void **)(v32 + 8));
                v34 = (_DWORD *)v33;
                if ( !v33 )
                  goto LABEL_50;
                *(_DWORD *)(v33 + 16) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 48LL) + 8 * v31) + 48LL);
                v35 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 48LL) + 8 * v31);
              }
              v34[5] = *(_DWORD *)(v35 + 52);
              v34[6] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 48LL) + 8 * v31) + 56LL);
              v34[3] = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)v11 + 48LL) + 8 * v31) + 16LL);
              v34[1] = v12[4];
              appended = CPerformanceStructureManipulator<_WMI_PERF_OBJECT,_WMI_PERF_NAMESPACE,_WMI_PERF_PROPERTY>::AppendAlloc(
                           &v45,
                           v34);
              v12 = v45;
LABEL_51:
              free(v34);
              v29 = (CGenerate *)(unsigned int)(v61 + 1);
              v61 = (int)v29;
              v30 = *(_QWORD *)v11;
              if ( (unsigned int)v29 >= *(_DWORD *)(*(_QWORD *)v11 + 56LL) )
              {
                LODWORD(v29) = v47;
                break;
              }
            }
          }
          if ( appended >= 0 && (_DWORD)v29 )
            v12[2] = (_DWORD)v29;
LABEL_56:
          ;
        }
        if ( appended >= 0 )
        {
          v12[5] = j;
LABEL_59:
          v12[6] = *(_DWORD *)(*(_QWORD *)v11 + 88LL);
          v12[3] = Structure[4];
          appended = CPerformanceStructureManipulator<_WMI_PERF_NAMESPACE,_WMI_PERFORMANCE,_WMI_PERF_OBJECT>::AppendAlloc(
                       &v49,
                       v12);
          Structure = v49;
        }
LABEL_61:
        free(v12);
        v9 = IndexRegistry;
        if ( a4 && appended >= 0 )
        {
          try
          {
            Throttle(3u, 0x3E8u, 0x64u, 0xAu, 0xBB8u);
          }
          catch ( ... )
          {
            v5 = &v44;
            appended = -2147467259;
            LODWORD(i) = v58;
            goto LABEL_73;
          }
        }
        LODWORD(i) = v58;
        if ( !*(_BYTE *)(v10 + 25) )
        {
          v7 = *(CGenerate **)(v10 + 16);
          if ( *((_BYTE *)v7 + 25) )
          {
            for ( k = *(_QWORD *)(v10 + 8); !*(_BYTE *)(k + 25) && v10 == *(_QWORD *)(k + 16); k = *(_QWORD *)(k + 8) )
              v10 = k;
          }
          else
          {
            k = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short * const,CObject *>>>::_Min();
          }
          v10 = k;
          v50 = k;
        }
      }
    }
    appended = -2147024882;
LABEL_72:
    free(Structure);
LABEL_73:
    ;
  }
  WmiSecurityAttributes::WmiSecurityAttributes((WmiSecurityAttributes *)v55, (int)v5);
  if ( !v56 )
  {
    appended = -2147467259;
    goto LABEL_81;
  }
  if ( !appended )
  {
    v41 = (unsigned __int8 *)Block[0];
    v42 = *(_DWORD *)Block[0];
LABEL_79:
    appended = SetRegistry(v40, v39, v41, v42, v56);
    goto LABEL_81;
  }
  if ( appended == 1 )
  {
    v42 = 0;
    v41 = 0;
    goto LABEL_79;
  }
LABEL_81:
  WmiSecurityAttributes::~WmiSecurityAttributes((WmiSecurityAttributes *)v55);
LABEL_83:
  free(Block[0]);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14000b2e4  mov     rax, rsp
0x14000b2e7  mov     [rax+20h], r9d
0x14000b2eb  mov     [rax+18h], r8
0x14000b2ef  mov     [rax+10h], rdx
0x14000b2f3  mov     [rax+8], rcx
0x14000b2f7  push    rbx
0x14000b2f8  push    rsi
0x14000b2f9  push    rdi
0x14000b2fa  push    r12
0x14000b2fc  push    r13
0x14000b2fe  push    r14
0x14000b300  sub     rsp, 0B8h
0x14000b307  mov     r12d, 1
0x14000b30d  call    ?CreateStructure@?$CPerformanceStructureManipulator@U_WMI_PERFORMANCE@@U1@U_WMI_PERF_NAMESPACE@@@@CAPEAU_WMI_PERFORMANCE@@K@Z; CPerformanceStructureManipulator<_WMI_PERFORMANCE,_WMI_PERFORMANCE,_WMI_PERF_NAMESPACE>::CreateStructure(ulong)
0x14000b312  mov     [rsp+0E8h+Block], rax
0x14000b317  test    rax, rax
0x14000b31a  jz      loc_14000B926
0x14000b320  mov     cs:dword_140024FB8, 0
0x14000b32a  xor     ebx, ebx
0x14000b32c  mov     [rsp+0E8h+arg_8], ebx
0x14000b333  mov     rdi, [rsp+0E8h+arg_0]
0x14000b33b  cmp     ebx, [rdi+50h]
0x14000b33e  jnb     loc_14000B8CC
0x14000b344  test    r12d, r12d
0x14000b347  js      loc_14000B8CC
0x14000b34d  lea     r14, [rbx+rbx*4]
0x14000b351  cmp     qword ptr [rdi+r14*8+20h], 0
0x14000b357  jz      loc_14000B8C5
0x14000b35d  xor     r12d, r12d
0x14000b360  mov     edx, ebx
0x14000b362  mov     rcx, [rdi+r14*8+8]; Src
0x14000b367  call    ?CreateStructure@?$CPerformanceStructureManipulator@U_WMI_PERF_NAMESPACE@@U_WMI_PERFORMANCE@@U_WMI_PERF_OBJECT@@@@CAPEAU_WMI_PERF_NAMESPACE@@PEAGK@Z; CPerformanceStructureManipulator<_WMI_PERF_NAMESPACE,_WMI_PERFORMANCE,_WMI_PERF_OBJECT>::CreateStructure(ushort *,ulong)
0x14000b36c  mov     rsi, rax
0x14000b36f  mov     [rsp+0E8h+var_98], rax
0x14000b374  test    rax, rax
0x14000b377  jz      loc_14000B8A4
0x14000b37d  xor     r13d, r13d
0x14000b380  lea     rdi, [rdi+r14*8]
0x14000b384  add     rdi, 18h
0x14000b388  mov     [rsp+0E8h+var_78], rdi
0x14000b38d  mov     rdi, [rdi]
0x14000b390  mov     rdi, [rdi]
0x14000b393  mov     [rsp+0E8h+var_90], rdi
0x14000b398  mov     rax, [rsp+0E8h+var_78]
0x14000b39d  cmp     rdi, [rax]
0x14000b3a0  jnz     short loc_14000B3C7
0x14000b3a2  test    r12d, r12d
0x14000b3a5  js      loc_14000B8AA
0x14000b3ab  mov     [rsi+8], r13d
0x14000b3af  mov     [rsi+0Ch], ebx
0x14000b3b2  mov     rdx, rsi
0x14000b3b5  lea     rcx, [rsp+0E8h+Block]
0x14000b3ba  call    ?AppendAlloc@?$CPerformanceStructureManipulator@U_WMI_PERF_NAMESPACE@@U_WMI_PERFORMANCE@@U_WMI_PERF_OBJECT@@@@QEAAJPEAU_WMI_PERF_OBJECT@@@Z; CPerformanceStructureManipulator<_WMI_PERF_NAMESPACE,_WMI_PERFORMANCE,_WMI_PERF_OBJECT>::AppendAlloc(_WMI_PERF_OBJECT *)
0x14000b3bf  mov     r12d, eax
0x14000b3c2  jmp     loc_14000B8AA
0x14000b3c7  test    r12d, r12d
0x14000b3ca  js      loc_14000B8AA
0x14000b3d0  xor     edx, edx; int
0x14000b3d2  call    ?GenerateIndexRegistry@CGenerate@@AEAAKH@Z; CGenerate::GenerateIndexRegistry(int)
0x14000b3d7  mov     [rsp+0E8h+var_B0], eax
0x14000b3db  lea     r13, [rdi+28h]
0x14000b3df  mov     rcx, [r13+0]
0x14000b3e3  mov     edx, eax
0x14000b3e5  mov     rcx, [rcx+8]; Src
0x14000b3e9  call    ?CreateStructure@?$CPerformanceStructureManipulator@U_WMI_PERF_OBJECT@@U_WMI_PERF_NAMESPACE@@U_WMI_PERF_PROPERTY@@@@CAPEAU_WMI_PERF_OBJECT@@PEAGK@Z; CPerformanceStructureManipulator<_WMI_PERF_OBJECT,_WMI_PERF_NAMESPACE,_WMI_PERF_PROPERTY>::CreateStructure(ushort *,ulong)
0x14000b3ee  mov     rbx, rax
0x14000b3f1  mov     [rsp+0E8h+var_B8], rax
0x14000b3f6  test    rax, rax
0x14000b3f9  jz      loc_14000B804
0x14000b3ff  mov     [rsp+0E8h+var_80], r13
0x14000b404  mov     rax, [r13+0]
0x14000b408  cmp     qword ptr [rax+48h], 0
0x14000b40d  jnz     loc_14000B54A
0x14000b413  cmp     dword ptr [rax+38h], 0
0x14000b417  jbe     loc_14000B7DD
0x14000b41d  xor     ecx, ecx; this
0x14000b41f  mov     dword ptr [rsp+0E8h+var_A8], ecx
0x14000b423  mov     [rsp+0E8h+arg_10], ecx
0x14000b42a  test    r12d, r12d
0x14000b42d  js      loc_14000B80A
0x14000b433  mov     r12d, ecx
0x14000b436  mov     rax, [rax+30h]
0x14000b43a  mov     r8, [rax+rcx*8]
0x14000b43e  xor     edx, edx; int
0x14000b440  cmp     [r8+20h], rdx
0x14000b444  jnz     short loc_14000B47C
0x14000b446  mov     rcx, [r8+8]; Src
0x14000b44a  call    ?CreateStructure@?$CPerformanceStructureManipulator@U_WMI_PERF_PROPERTY@@U_WMI_PERF_OBJECT@@U1@@@CAPEAU_WMI_PERF_PROPERTY@@PEAGK@Z; CPerformanceStructureManipulator<_WMI_PERF_PROPERTY,_WMI_PERF_OBJECT,_WMI_PERF_PROPERTY>::CreateStructure(ushort *,ulong)
0x14000b44f  mov     r14, rax
0x14000b452  test    rax, rax
0x14000b455  jz      loc_14000B501
0x14000b45b  mov     rax, [r13+0]
0x14000b45f  mov     rcx, [rax+30h]
0x14000b463  mov     rax, [rcx+r12*8]
0x14000b467  mov     ecx, [rax+30h]
0x14000b46a  mov     [r14+10h], ecx
0x14000b46e  mov     rax, [r13+0]
0x14000b472  mov     rcx, [rax+30h]
0x14000b476  mov     rax, [rcx+r12*8]
0x14000b47a  jmp     short loc_14000B4B6
0x14000b47c  call    ?GenerateIndexRegistry@CGenerate@@AEAAKH@Z; CGenerate::GenerateIndexRegistry(int)
0x14000b481  mov     dword ptr [rsp+0E8h+var_A8], eax
0x14000b485  mov     edx, eax
0x14000b487  mov     rcx, [r8+8]; Src
0x14000b48b  call    ?CreateStructure@?$CPerformanceStructureManipulator@U_WMI_PERF_PROPERTY@@U_WMI_PERF_OBJECT@@U1@@@CAPEAU_WMI_PERF_PROPERTY@@PEAGK@Z; CPerformanceStructureManipulator<_WMI_PERF_PROPERTY,_WMI_PERF_OBJECT,_WMI_PERF_PROPERTY>::CreateStructure(ushort *,ulong)
0x14000b490  mov     r14, rax
0x14000b493  test    rax, rax
0x14000b496  jz      short loc_14000B501
0x14000b498  mov     rcx, [r13+0]
0x14000b49c  mov     rdx, [rcx+30h]
0x14000b4a0  mov     rcx, [rdx+r12*8]
0x14000b4a4  mov     edx, [rcx+30h]
0x14000b4a7  mov     [rax+10h], edx
0x14000b4aa  mov     rcx, [r13+0]
0x14000b4ae  mov     rdx, [rcx+30h]
0x14000b4b2  mov     rax, [rdx+r12*8]
0x14000b4b6  mov     ecx, [rax+34h]
0x14000b4b9  mov     [r14+14h], ecx
0x14000b4bd  mov     rax, [r13+0]
0x14000b4c1  mov     rcx, [rax+30h]
0x14000b4c5  mov     rax, [rcx+r12*8]
0x14000b4c9  mov     ecx, [rax+38h]
0x14000b4cc  mov     [r14+18h], ecx
0x14000b4d0  mov     rax, [r13+0]
0x14000b4d4  mov     rcx, [rax+30h]
0x14000b4d8  mov     rax, [rcx+r12*8]
0x14000b4dc  mov     ecx, [rax+10h]
0x14000b4df  mov     [r14+0Ch], ecx
0x14000b4e3  mov     eax, [rbx+10h]
0x14000b4e6  mov     [r14+4], eax
0x14000b4ea  mov     rdx, r14
0x14000b4ed  lea     rcx, [rsp+0E8h+var_B8]
0x14000b4f2  call    ?AppendAlloc@?$CPerformanceStructureManipulator@U_WMI_PERF_OBJECT@@U_WMI_PERF_NAMESPACE@@U_WMI_PERF_PROPERTY@@@@QEAAJPEAU_WMI_PERF_PROPERTY@@@Z; CPerformanceStructureManipulator<_WMI_PERF_OBJECT,_WMI_PERF_NAMESPACE,_WMI_PERF_PROPERTY>::AppendAlloc(_WMI_PERF_PROPERTY *)
0x14000b4f7  mov     r12d, eax
0x14000b4fa  mov     rbx, [rsp+0E8h+var_B8]
0x14000b4ff  jmp     short loc_14000B507
0x14000b501  mov     r12d, 8007000Eh
0x14000b507  mov     rcx, r14; Block
0x14000b50a  call    cs:__imp_free
0x14000b510  mov     ecx, [rsp+0E8h+arg_10]
0x14000b517  inc     ecx
0x14000b519  mov     [rsp+0E8h+arg_10], ecx
0x14000b520  mov     rax, [r13+0]
0x14000b524  cmp     ecx, [rax+38h]
0x14000b527  jb      loc_14000B42A
0x14000b52d  test    r12d, r12d
0x14000b530  js      loc_14000B80A
0x14000b536  mov     ecx, dword ptr [rsp+0E8h+var_A8]
0x14000b53a  test    ecx, ecx
0x14000b53c  jz      loc_14000B7DD
0x14000b542  mov     [rbx+8], ecx
0x14000b545  jmp     loc_14000B7DD
0x14000b54a  xor     eax, eax
0x14000b54c  mov     [rsp+0E8h+var_A0], eax
0x14000b550  mov     rcx, [r13+0]
0x14000b554  cmp     eax, [rcx+50h]
0x14000b557  jnb     loc_14000B7D5
0x14000b55d  test    r12d, r12d
0x14000b560  js      loc_14000B80A
0x14000b566  mov     edx, eax
0x14000b568  mov     [rsp+0E8h+var_70], rdx
0x14000b56d  mov     rax, [rcx+48h]
0x14000b571  mov     rcx, [rax+rdx*8]; String
0x14000b575  test    rcx, rcx
0x14000b578  jz      short loc_14000B582
0x14000b57a  call    cs:__imp_wcslen
0x14000b580  jmp     short loc_14000B584
0x14000b582  xor     eax, eax
0x14000b584  mov     [rsp+0E8h+var_A8], rax
0x14000b589  lea     edx, ds:2[rax*2]
0x14000b590  mov     eax, edx
0x14000b592  and     eax, 7
0x14000b595  mov     ecx, 8
0x14000b59a  sub     ecx, eax
0x14000b59c  neg     eax
0x14000b59e  sbb     eax, eax
0x14000b5a0  and     eax, ecx
0x14000b5a2  add     edx, 10h
0x14000b5a5  add     eax, edx
0x14000b5a7  mov     [rsp+0E8h+arg_10], eax
0x14000b5ae  mov     ecx, eax; Size
0x14000b5b0  call    cs:__imp_malloc
0x14000b5b6  mov     r14, rax
0x14000b5b9  mov     [rsp+0E8h+var_68], rax
0x14000b5c1  test    rax, rax
0x14000b5c4  jz      loc_14000B679
0x14000b5ca  mov     rcx, [rsp+0E8h+var_A8]
0x14000b5cf  lea     r8d, ds:2[rcx*2]; Size
0x14000b5d7  mov     rax, [r13+0]
0x14000b5db  mov     rdx, [rax+48h]
0x14000b5df  lea     rcx, [r14+8]; void *
0x14000b5e3  mov     rax, [rsp+0E8h+var_70]
0x14000b5e8  mov     rdx, [rdx+rax*8]; Src
0x14000b5ec  call    cs:__imp_memcpy
0x14000b5f2  mov     rcx, [rsp+0E8h+var_A8]
0x14000b5f7  lea     eax, ds:2[rcx*2]
0x14000b5fe  mov     [r14+4], eax
0x14000b602  mov     ecx, [rsp+0E8h+arg_10]
0x14000b609  mov     [r14], ecx
0x14000b60c  test    rbx, rbx
0x14000b60f  jz      short loc_14000B642
0x14000b611  mov     edx, [rbx]
0x14000b613  add     edx, ecx
0x14000b615  mov     rcx, rbx; Block
0x14000b618  call    ??$_RA_realloc@U_WMI_PERF_OBJECT@@@@YAPEAU_WMI_PERF_OBJECT@@PEAU0@_K@Z; _RA_realloc<_WMI_PERF_OBJECT>(_WMI_PERF_OBJECT *,unsigned __int64)
0x14000b61d  mov     rbx, rax
0x14000b620  mov     [rsp+0E8h+var_B8], rax
0x14000b625  test    rax, rax
0x14000b628  jz      short loc_14000B642
0x14000b62a  mov     r8d, [r14]; Size
0x14000b62d  mov     ecx, [rax]
0x14000b62f  add     rcx, rax; void *
0x14000b632  mov     rdx, r14; Src
0x14000b635  call    cs:__imp_memcpy
0x14000b63b  mov     eax, [r14]
0x14000b63e  add     [rbx], eax
0x14000b640  jmp     short loc_14000B648
0x14000b642  mov     r12d, 8007000Eh
0x14000b648  jmp     short loc_14000B66E
0x14000b64a  mov     r12d, [rsp+0E8h+arg_10]
0x14000b652  mov     rsi, [rsp+0E8h+var_98]
0x14000b657  mov     rdi, [rsp+0E8h+var_90]
0x14000b65c  mov     rbx, [rsp+0E8h+var_B8]
0x14000b661  mov     r14, [rsp+0E8h+var_68]
0x14000b669  mov     r13, [rsp+0E8h+var_80]
0x14000b66e  mov     rcx, r14; Block
0x14000b671  call    cs:__imp_free
0x14000b677  jmp     short loc_14000B67F
0x14000b679  mov     r12d, 8007000Eh
0x14000b67f  jmp     short loc_14000B69D
0x14000b681  mov     r12d, [rsp+0E8h+arg_10]
0x14000b689  mov     rsi, [rsp+0E8h+var_98]
0x14000b68e  mov     rdi, [rsp+0E8h+var_90]
0x14000b693  mov     rbx, [rsp+0E8h+var_B8]
0x14000b698  mov     r13, [rsp+0E8h+var_80]
0x14000b69d  xor     ecx, ecx; this
0x14000b69f  mov     dword ptr [rsp+0E8h+var_A8], ecx
0x14000b6a3  mov     rax, [r13+0]
0x14000b6a7  cmp     [rax+38h], ecx
0x14000b6aa  jbe     loc_14000B7BE
0x14000b6b0  mov     [rsp+0E8h+arg_10], ecx
0x14000b6b7  test    r12d, r12d
0x14000b6ba  js      loc_14000B7CA
0x14000b6c0  mov     r12d, ecx
0x14000b6c3  mov     rax, [rax+30h]
0x14000b6c7  mov     r8, [rax+rcx*8]
0x14000b6cb  xor     edx, edx; int
0x14000b6cd  cmp     [r8+20h], rdx
0x14000b6d1  jnz     short loc_14000B709
0x14000b6d3  mov     rcx, [r8+8]; Src
0x14000b6d7  call    ?CreateStructure@?$CPerformanceStructureManipulator@U_WMI_PERF_PROPERTY@@U_WMI_PERF_OBJECT@@U1@@@CAPEAU_WMI_PERF_PROPERTY@@PEAGK@Z; CPerformanceStructureManipulator<_WMI_PERF_PROPERTY,_WMI_PERF_OBJECT,_WMI_PERF_PROPERTY>::CreateStructure(ushort *,ulong)
0x14000b6dc  mov     r14, rax
0x14000b6df  test    rax, rax
0x14000b6e2  jz      loc_14000B78E
0x14000b6e8  mov     rax, [r13+0]
0x14000b6ec  mov     rcx, [rax+30h]
0x14000b6f0  mov     rax, [rcx+r12*8]
0x14000b6f4  mov     ecx, [rax+30h]
0x14000b6f7  mov     [r14+10h], ecx
0x14000b6fb  mov     rax, [r13+0]
0x14000b6ff  mov     rcx, [rax+30h]
0x14000b703  mov     rax, [rcx+r12*8]
0x14000b707  jmp     short loc_14000B743
0x14000b709  call    ?GenerateIndexRegistry@CGenerate@@AEAAKH@Z; CGenerate::GenerateIndexRegistry(int)
0x14000b70e  mov     dword ptr [rsp+0E8h+var_A8], eax
0x14000b712  mov     edx, eax
0x14000b714  mov     rcx, [r8+8]; Src
0x14000b718  call    ?CreateStructure@?$CPerformanceStructureManipulator@U_WMI_PERF_PROPERTY@@U_WMI_PERF_OBJECT@@U1@@@CAPEAU_WMI_PERF_PROPERTY@@PEAGK@Z; CPerformanceStructureManipulator<_WMI_PERF_PROPERTY,_WMI_PERF_OBJECT,_WMI_PERF_PROPERTY>::CreateStructure(ushort *,ulong)
0x14000b71d  mov     r14, rax
0x14000b720  test    rax, rax
0x14000b723  jz      short loc_14000B78E
0x14000b725  mov     rcx, [r13+0]
0x14000b729  mov     rdx, [rcx+30h]
0x14000b72d  mov     rcx, [rdx+r12*8]
0x14000b731  mov     edx, [rcx+30h]
0x14000b734  mov     [rax+10h], edx
0x14000b737  mov     rcx, [r13+0]
0x14000b73b  mov     rdx, [rcx+30h]
0x14000b73f  mov     rax, [rdx+r12*8]
0x14000b743  mov     ecx, [rax+34h]
0x14000b746  mov     [r14+14h], ecx
0x14000b74a  mov     rax, [r13+0]
0x14000b74e  mov     rcx, [rax+30h]
0x14000b752  mov     rax, [rcx+r12*8]
0x14000b756  mov     ecx, [rax+38h]
0x14000b759  mov     [r14+18h], ecx
0x14000b75d  mov     rax, [r13+0]
0x14000b761  mov     rcx, [rax+30h]
0x14000b765  mov     rax, [rcx+r12*8]
0x14000b769  mov     ecx, [rax+10h]
0x14000b76c  mov     [r14+0Ch], ecx
0x14000b770  mov     eax, [rbx+10h]
0x14000b773  mov     [r14+4], eax
0x14000b777  mov     rdx, r14
0x14000b77a  lea     rcx, [rsp+0E8h+var_B8]
0x14000b77f  call    ?AppendAlloc@?$CPerformanceStructureManipulator@U_WMI_PERF_OBJECT@@U_WMI_PERF_NAMESPACE@@U_WMI_PERF_PROPERTY@@@@QEAAJPEAU_WMI_PERF_PROPERTY@@@Z; CPerformanceStructureManipulator<_WMI_PERF_OBJECT,_WMI_PERF_NAMESPACE,_WMI_PERF_PROPERTY>::AppendAlloc(_WMI_PERF_PROPERTY *)
0x14000b784  mov     r12d, eax
0x14000b787  mov     rbx, [rsp+0E8h+var_B8]
0x14000b78c  jmp     short loc_14000B794
0x14000b78e  mov     r12d, 8007000Eh
  ... truncated ...
```
