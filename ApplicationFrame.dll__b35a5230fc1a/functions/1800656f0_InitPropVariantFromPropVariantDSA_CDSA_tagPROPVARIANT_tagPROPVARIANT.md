# InitPropVariantFromPropVariantDSA(CDSA<tagPROPVARIANT> *,tagPROPVARIANT *)

- ea: `0x1800656f0`
- end: `0x18006593a`
- name: `?InitPropVariantFromPropVariantDSA@@YAJPEAV?$CDSA@UtagPROPVARIANT@@@@PEAUtagPROPVARIANT@@@Z`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180065050`

## callees

- `0x180062d74`
- `0x1800656f0`
- `0x18006afa0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065869`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065869`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006579a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006579a`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800658ca`
- `PROPSYS!PropVariantToStringAlloc` at `0x1800658ca`

## pseudocode

```c
__int64 __fastcall InitPropVariantFromPropVariantDSA(HDSA *a1, __int64 a2)
{
  int v2; // r14d
  HRESULT v5; // edi
  struct _DSA *v6; // rcx
  int v7; // ebx
  unsigned __int16 v8; // r15
  int v9; // eax
  int v10; // r9d
  int v11; // eax
  void *v12; // rsi
  int v13; // ebx
  const PROPVARIANT *ItemPtr; // rax
  _OWORD *v15; // rcx
  __int128 v17; // [rsp+20h] [rbp-20h]
  int v18; // [rsp+80h] [rbp+40h]
  PWSTR ppszOut; // [rsp+90h] [rbp+50h] BYREF

  v2 = 0;
  v5 = -2147024809;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  if ( a1 )
  {
    v6 = *a1;
    v5 = 0;
    if ( v6 )
    {
      v7 = *(_DWORD *)v6;
      v18 = *(_DWORD *)v6;
      if ( *(_DWORD *)v6 )
      {
        v5 = -2147286953;
        v8 = *(_WORD *)g_pfn_DSA_GetItemPtr(v6, 0);
        if ( v8 == 8 )
        {
          v8 = 31;
        }
        else if ( (v8 & 0x1000) != 0 )
        {
          return (unsigned int)v5;
        }
        v9 = CRGTypeSizes::operator[](8, v8);
        v11 = v10 & v9;
        if ( v11 )
        {
          v5 = -2147024882;
          v17 = 0;
          v12 = CoTaskMemAlloc((unsigned int)(v7 * v11));
          if ( v12 )
          {
            v13 = 0;
            DWORD2(v17) = 0;
            v5 = 0;
            while ( 1 )
            {
              if ( v2 >= v18 )
              {
                LOWORD(v17) = v8 | 0x1000;
                *(_OWORD *)a2 = v17;
                *(_QWORD *)(a2 + 16) = v12;
                return (unsigned int)v5;
              }
              ItemPtr = (const PROPVARIANT *)g_pfn_DSA_GetItemPtr(*a1, v2);
              if ( *(_WORD *)ItemPtr != v8 )
              {
                if ( *(_WORD *)ItemPtr == 8 )
                {
                  if ( v8 != 31 )
                    goto LABEL_26;
                }
                else if ( (*(_WORD *)ItemPtr || v8 != 1) && (*(_WORD *)ItemPtr != 1 || v8) )
                {
LABEL_26:
                  v5 = -2147286953;
LABEL_27:
                  CoTaskMemFree(v12);
                  return (unsigned int)v5;
                }
              }
              if ( v8 > 0x13u )
              {
                switch ( v8 )
                {
                  case 0x14u:
                  case 0x15u:
                    goto LABEL_39;
                  case 0x1Fu:
                    ppszOut = 0;
                    v5 = PropVariantToStringAlloc(ItemPtr, &ppszOut);
                    if ( v5 >= 0 )
                    {
                      *((_QWORD *)v12 + v2) = ppszOut;
                      DWORD2(v17) = ++v13;
                    }
                    goto LABEL_41;
                  case 0x40u:
LABEL_39:
                    *((PROPVARIANT *)v12 + v2) = ItemPtr[1];
                    goto LABEL_40;
                  case 0x48u:
                    v15 = (_OWORD *)*((_QWORD *)ItemPtr + 1);
                    if ( v15 )
                    {
                      v5 = 0;
                      *((_OWORD *)v12 + v2) = *v15;
                      goto LABEL_40;
                    }
                    break;
                }
              }
              else
              {
                switch ( v8 )
                {
                  case 0x13u:
                    goto LABEL_28;
                  case 2u:
                    goto LABEL_21;
                  case 3u:
LABEL_28:
                    *((_DWORD *)v12 + v2) = *((_DWORD *)ItemPtr + 2);
                    goto LABEL_40;
                  case 5u:
                    goto LABEL_39;
                  case 0xBu:
                  case 0x12u:
LABEL_21:
                    *((_WORD *)v12 + v2) = *((_WORD *)ItemPtr + 4);
LABEL_40:
                    DWORD2(v17) = ++v13;
                    goto LABEL_41;
                }
              }
              v5 = -2147286953;
LABEL_41:
              ++v2;
              if ( v5 < 0 )
                goto LABEL_27;
            }
          }
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800656f0  mov     [rsp-38h+arg_8], rbx
0x1800656f5  push    rbp
0x1800656f6  push    rsi
0x1800656f7  push    rdi
0x1800656f8  push    r12
0x1800656fa  push    r13
0x1800656fc  push    r14
0x1800656fe  push    r15
0x180065700  mov     rbp, rsp
0x180065703  sub     rsp, 40h
0x180065707  xor     eax, eax
0x180065709  xorps   xmm0, xmm0
0x18006570c  xor     r14d, r14d
0x18006570f  mov     r13, rdx
0x180065712  mov     r12, rcx
0x180065715  mov     edi, 80070057h
0x18006571a  movups  xmmword ptr [rdx], xmm0
0x18006571d  mov     [rdx+10h], rax
0x180065721  test    rcx, rcx
0x180065724  jz      loc_180065920
0x18006572a  mov     rcx, [rcx]; hdsa
0x18006572d  mov     edi, r14d
0x180065730  test    rcx, rcx
0x180065733  jz      loc_180065920
0x180065739  mov     ebx, [rcx]
0x18006573b  mov     [rbp+arg_0], ebx
0x18006573e  test    ebx, ebx
0x180065740  jz      loc_180065920
0x180065746  xor     edx, edx; i
0x180065748  mov     edi, 80030057h
0x18006574d  call    cs:g_pfn_DSA_GetItemPtr
0x180065753  lea     ecx, [r14+8]
0x180065757  lea     r9d, [r14+1Fh]
0x18006575b  movzx   r15d, word ptr [rax]
0x18006575f  cmp     r15w, cx
0x180065763  jnz     short loc_18006576B
0x180065765  movzx   r15d, r9w
0x180065769  jmp     short loc_180065777
0x18006576b  bt      r15w, 0Ch
0x180065771  jb      loc_180065920
0x180065777  movzx   edx, r15w
0x18006577b  call    ??ACRGTypeSizes@@QEAAGH@Z; CRGTypeSizes::operator[](int)
0x180065780  and     eax, r9d
0x180065783  jz      loc_180065920
0x180065789  imul    eax, ebx
0x18006578c  xorps   xmm0, xmm0
0x18006578f  mov     edi, 8007000Eh
0x180065794  movups  [rbp+var_20], xmm0
0x180065798  mov     ecx, eax; cb
0x18006579a  call    cs:__imp_CoTaskMemAlloc
0x1800657a0  mov     rsi, rax
0x1800657a3  test    rax, rax
0x1800657a6  jz      loc_180065920
0x1800657ac  movzx   eax, r15w
0x1800657b0  mov     ebx, r14d
0x1800657b3  or      ax, 1000h
0x1800657b7  mov     dword ptr [rbp+var_20+8], ebx
0x1800657ba  mov     word ptr [rbp+var_20], ax
0x1800657be  mov     edi, r14d
0x1800657c1  cmp     r14d, [rbp+arg_0]
0x1800657c5  jge     loc_180065913
0x1800657cb  mov     rcx, [r12]; hdsa
0x1800657cf  mov     edx, r14d; i
0x1800657d2  call    cs:g_pfn_DSA_GetItemPtr
0x1800657d8  mov     r8, rax
0x1800657db  mov     edx, 8
0x1800657e0  cmp     [rax], r15w
0x1800657e4  jz      short loc_1800657F4
0x1800657e6  cmp     [rax], dx
0x1800657e9  lea     eax, [rdx+17h]
0x1800657ec  jnz     short loc_180065836
0x1800657ee  cmp     r15w, ax
0x1800657f2  jnz     short loc_180065861
0x1800657f4  xor     r9d, r9d
0x1800657f7  lea     r10d, [r9+1]
0x1800657fb  cmp     r15w, 13h
0x180065800  ja      short loc_180065880
0x180065802  jz      short loc_180065874
0x180065804  movzx   ecx, r15w
0x180065808  sub     ecx, 2
0x18006580b  jz      short loc_180065825
0x18006580d  sub     ecx, 1
0x180065810  jz      short loc_180065874
0x180065812  sub     ecx, 2
0x180065815  jz      loc_1800658ED
0x18006581b  sub     ecx, 6
0x18006581e  jz      short loc_180065825
0x180065820  cmp     ecx, 7
0x180065823  jnz     short loc_18006589C
0x180065825  movzx   eax, word ptr [r8+8]
0x18006582a  movsxd  rcx, r14d
0x18006582d  mov     [rsi+rcx*2], ax
0x180065831  jmp     loc_1800658F8
0x180065836  cmp     [r8], ax
0x18006583a  jnz     short loc_180065842
0x18006583c  cmp     r15w, dx
0x180065840  jz      short loc_1800657F4
0x180065842  xor     r9d, r9d
0x180065845  lea     r10d, [r9+1]
0x180065849  cmp     [r8], r9w
0x18006584d  jnz     short loc_180065855
0x18006584f  cmp     r15w, r10w
0x180065853  jz      short loc_1800657FB
0x180065855  cmp     [r8], r10w
0x180065859  jnz     short loc_180065861
0x18006585b  test    r15w, r15w
0x18006585f  jz      short loc_1800657FB
0x180065861  mov     edi, 80030057h
0x180065866  mov     rcx, rsi; pv
0x180065869  call    cs:__imp_CoTaskMemFree
0x18006586f  jmp     loc_180065920
0x180065874  mov     eax, [r8+8]
0x180065878  movsxd  rcx, r14d
0x18006587b  mov     [rsi+rcx*4], eax
0x18006587e  jmp     short loc_1800658F8
0x180065880  movzx   ecx, r15w
0x180065884  sub     ecx, 14h
0x180065887  jz      short loc_1800658ED
0x180065889  sub     ecx, 1
0x18006588c  jz      short loc_1800658ED
0x18006588e  sub     ecx, 0Ah
0x180065891  jz      short loc_1800658BF
0x180065893  sub     ecx, 21h ; '!'
0x180065896  jz      short loc_1800658ED
0x180065898  cmp     ecx, edx
0x18006589a  jz      short loc_1800658A3
0x18006589c  mov     edi, 80030057h
0x1800658a1  jmp     short loc_1800658FE
0x1800658a3  mov     rcx, [r8+8]
0x1800658a7  test    rcx, rcx
0x1800658aa  jz      short loc_18006589C
0x1800658ac  movups  xmm0, xmmword ptr [rcx]
0x1800658af  movsxd  rax, r14d
0x1800658b2  mov     edi, r9d
0x1800658b5  add     rax, rax
0x1800658b8  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x1800658bd  jmp     short loc_1800658F8
0x1800658bf  lea     rdx, [rbp+ppszOut]; ppszOut
0x1800658c3  mov     [rbp+ppszOut], r9
0x1800658c7  mov     rcx, r8; propvar
0x1800658ca  call    cs:__imp_PropVariantToStringAlloc
0x1800658d0  mov     edi, eax
0x1800658d2  test    eax, eax
0x1800658d4  js      short loc_1800658FE
0x1800658d6  mov     rax, [rbp+ppszOut]
0x1800658da  movsxd  rcx, r14d
0x1800658dd  mov     [rsi+rcx*8], rax
0x1800658e1  mov     eax, 1
0x1800658e6  add     ebx, eax
0x1800658e8  mov     dword ptr [rbp+var_20+8], ebx
0x1800658eb  jmp     short loc_180065903
0x1800658ed  mov     rax, [r8+8]
0x1800658f1  movsxd  rcx, r14d
0x1800658f4  mov     [rsi+rcx*8], rax
0x1800658f8  add     ebx, r10d
0x1800658fb  mov     dword ptr [rbp+var_20+8], ebx
0x1800658fe  mov     eax, 1
0x180065903  add     r14d, eax
0x180065906  test    edi, edi
0x180065908  jns     loc_1800657C1
0x18006590e  jmp     loc_180065866
0x180065913  movups  xmm0, [rbp+var_20]
0x180065917  movups  xmmword ptr [r13+0], xmm0
0x18006591c  mov     [r13+10h], rsi
0x180065920  mov     rbx, [rsp+40h+arg_8]
0x180065928  mov     eax, edi
0x18006592a  add     rsp, 40h
0x18006592e  pop     r15
0x180065930  pop     r14
0x180065932  pop     r13
0x180065934  pop     r12
0x180065936  pop     rdi
0x180065937  pop     rsi
0x180065938  pop     rbp
0x180065939  retn
```
