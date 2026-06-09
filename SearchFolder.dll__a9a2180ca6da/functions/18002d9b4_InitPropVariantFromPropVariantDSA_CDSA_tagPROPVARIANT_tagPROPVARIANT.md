# InitPropVariantFromPropVariantDSA(CDSA<tagPROPVARIANT> *,tagPROPVARIANT *)

- ea: `0x18002d9b4`
- end: `0x18002dbfe`
- name: `?InitPropVariantFromPropVariantDSA@@YAJPEAV?$CDSA@UtagPROPVARIANT@@@@PEAUtagPROPVARIANT@@@Z`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d140`

## callees

- `0x18002852c`
- `0x18002d9b4`
- `0x18004a9e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002db2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002db2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002da5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002da5e`
- `PROPSYS!PropVariantToStringAlloc` at `0x18002db8e`
- `PROPSYS!PropVariantToStringAlloc` at `0x18002db8e`

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
0x18002d9b4  mov     [rsp-38h+arg_8], rbx
0x18002d9b9  push    rbp
0x18002d9ba  push    rsi
0x18002d9bb  push    rdi
0x18002d9bc  push    r12
0x18002d9be  push    r13
0x18002d9c0  push    r14
0x18002d9c2  push    r15
0x18002d9c4  mov     rbp, rsp
0x18002d9c7  sub     rsp, 40h
0x18002d9cb  xor     eax, eax
0x18002d9cd  xorps   xmm0, xmm0
0x18002d9d0  xor     r14d, r14d
0x18002d9d3  mov     r13, rdx
0x18002d9d6  mov     r12, rcx
0x18002d9d9  mov     edi, 80070057h
0x18002d9de  movups  xmmword ptr [rdx], xmm0
0x18002d9e1  mov     [rdx+10h], rax
0x18002d9e5  test    rcx, rcx
0x18002d9e8  jz      loc_18002DBE4
0x18002d9ee  mov     rcx, [rcx]; hdsa
0x18002d9f1  mov     edi, r14d
0x18002d9f4  test    rcx, rcx
0x18002d9f7  jz      loc_18002DBE4
0x18002d9fd  mov     ebx, [rcx]
0x18002d9ff  mov     [rbp+arg_0], ebx
0x18002da02  test    ebx, ebx
0x18002da04  jz      loc_18002DBE4
0x18002da0a  xor     edx, edx; i
0x18002da0c  mov     edi, 80030057h
0x18002da11  call    cs:g_pfn_DSA_GetItemPtr
0x18002da17  lea     ecx, [r14+8]
0x18002da1b  lea     r9d, [r14+1Fh]
0x18002da1f  movzx   r15d, word ptr [rax]
0x18002da23  cmp     r15w, cx
0x18002da27  jnz     short loc_18002DA2F
0x18002da29  movzx   r15d, r9w
0x18002da2d  jmp     short loc_18002DA3B
0x18002da2f  bt      r15w, 0Ch
0x18002da35  jb      loc_18002DBE4
0x18002da3b  movzx   edx, r15w
0x18002da3f  call    ??ACRGTypeSizes@@QEAAGH@Z; CRGTypeSizes::operator[](int)
0x18002da44  and     eax, r9d
0x18002da47  jz      loc_18002DBE4
0x18002da4d  imul    eax, ebx
0x18002da50  xorps   xmm0, xmm0
0x18002da53  mov     edi, 8007000Eh
0x18002da58  movups  [rbp+var_20], xmm0
0x18002da5c  mov     ecx, eax; cb
0x18002da5e  call    cs:__imp_CoTaskMemAlloc
0x18002da64  mov     rsi, rax
0x18002da67  test    rax, rax
0x18002da6a  jz      loc_18002DBE4
0x18002da70  movzx   eax, r15w
0x18002da74  mov     ebx, r14d
0x18002da77  or      ax, 1000h
0x18002da7b  mov     dword ptr [rbp+var_20+8], ebx
0x18002da7e  mov     word ptr [rbp+var_20], ax
0x18002da82  mov     edi, r14d
0x18002da85  cmp     r14d, [rbp+arg_0]
0x18002da89  jge     loc_18002DBD7
0x18002da8f  mov     rcx, [r12]; hdsa
0x18002da93  mov     edx, r14d; i
0x18002da96  call    cs:g_pfn_DSA_GetItemPtr
0x18002da9c  mov     r8, rax
0x18002da9f  mov     edx, 8
0x18002daa4  cmp     [rax], r15w
0x18002daa8  jz      short loc_18002DAB8
0x18002daaa  cmp     [rax], dx
0x18002daad  lea     eax, [rdx+17h]
0x18002dab0  jnz     short loc_18002DAFA
0x18002dab2  cmp     r15w, ax
0x18002dab6  jnz     short loc_18002DB25
0x18002dab8  xor     r9d, r9d
0x18002dabb  lea     r10d, [r9+1]
0x18002dabf  cmp     r15w, 13h
0x18002dac4  ja      short loc_18002DB44
0x18002dac6  jz      short loc_18002DB38
0x18002dac8  movzx   ecx, r15w
0x18002dacc  sub     ecx, 2
0x18002dacf  jz      short loc_18002DAE9
0x18002dad1  sub     ecx, 1
0x18002dad4  jz      short loc_18002DB38
0x18002dad6  sub     ecx, 2
0x18002dad9  jz      loc_18002DBB1
0x18002dadf  sub     ecx, 6
0x18002dae2  jz      short loc_18002DAE9
0x18002dae4  cmp     ecx, 7
0x18002dae7  jnz     short loc_18002DB60
0x18002dae9  movzx   eax, word ptr [r8+8]
0x18002daee  movsxd  rcx, r14d
0x18002daf1  mov     [rsi+rcx*2], ax
0x18002daf5  jmp     loc_18002DBBC
0x18002dafa  cmp     [r8], ax
0x18002dafe  jnz     short loc_18002DB06
0x18002db00  cmp     r15w, dx
0x18002db04  jz      short loc_18002DAB8
0x18002db06  xor     r9d, r9d
0x18002db09  lea     r10d, [r9+1]
0x18002db0d  cmp     [r8], r9w
0x18002db11  jnz     short loc_18002DB19
0x18002db13  cmp     r15w, r10w
0x18002db17  jz      short loc_18002DABF
0x18002db19  cmp     [r8], r10w
0x18002db1d  jnz     short loc_18002DB25
0x18002db1f  test    r15w, r15w
0x18002db23  jz      short loc_18002DABF
0x18002db25  mov     edi, 80030057h
0x18002db2a  mov     rcx, rsi; pv
0x18002db2d  call    cs:__imp_CoTaskMemFree
0x18002db33  jmp     loc_18002DBE4
0x18002db38  mov     eax, [r8+8]
0x18002db3c  movsxd  rcx, r14d
0x18002db3f  mov     [rsi+rcx*4], eax
0x18002db42  jmp     short loc_18002DBBC
0x18002db44  movzx   ecx, r15w
0x18002db48  sub     ecx, 14h
0x18002db4b  jz      short loc_18002DBB1
0x18002db4d  sub     ecx, 1
0x18002db50  jz      short loc_18002DBB1
0x18002db52  sub     ecx, 0Ah
0x18002db55  jz      short loc_18002DB83
0x18002db57  sub     ecx, 21h ; '!'
0x18002db5a  jz      short loc_18002DBB1
0x18002db5c  cmp     ecx, edx
0x18002db5e  jz      short loc_18002DB67
0x18002db60  mov     edi, 80030057h
0x18002db65  jmp     short loc_18002DBC2
0x18002db67  mov     rcx, [r8+8]
0x18002db6b  test    rcx, rcx
0x18002db6e  jz      short loc_18002DB60
0x18002db70  movups  xmm0, xmmword ptr [rcx]
0x18002db73  movsxd  rax, r14d
0x18002db76  mov     edi, r9d
0x18002db79  add     rax, rax
0x18002db7c  movdqu  xmmword ptr [rsi+rax*8], xmm0
0x18002db81  jmp     short loc_18002DBBC
0x18002db83  lea     rdx, [rbp+ppszOut]; ppszOut
0x18002db87  mov     [rbp+ppszOut], r9
0x18002db8b  mov     rcx, r8; propvar
0x18002db8e  call    cs:__imp_PropVariantToStringAlloc
0x18002db94  mov     edi, eax
0x18002db96  test    eax, eax
0x18002db98  js      short loc_18002DBC2
0x18002db9a  mov     rax, [rbp+ppszOut]
0x18002db9e  movsxd  rcx, r14d
0x18002dba1  mov     [rsi+rcx*8], rax
0x18002dba5  mov     eax, 1
0x18002dbaa  add     ebx, eax
0x18002dbac  mov     dword ptr [rbp+var_20+8], ebx
0x18002dbaf  jmp     short loc_18002DBC7
0x18002dbb1  mov     rax, [r8+8]
0x18002dbb5  movsxd  rcx, r14d
0x18002dbb8  mov     [rsi+rcx*8], rax
0x18002dbbc  add     ebx, r10d
0x18002dbbf  mov     dword ptr [rbp+var_20+8], ebx
0x18002dbc2  mov     eax, 1
0x18002dbc7  add     r14d, eax
0x18002dbca  test    edi, edi
0x18002dbcc  jns     loc_18002DA85
0x18002dbd2  jmp     loc_18002DB2A
0x18002dbd7  movups  xmm0, [rbp+var_20]
0x18002dbdb  movups  xmmword ptr [r13+0], xmm0
0x18002dbe0  mov     [r13+10h], rsi
0x18002dbe4  mov     rbx, [rsp+40h+arg_8]
0x18002dbec  mov     eax, edi
0x18002dbee  add     rsp, 40h
0x18002dbf2  pop     r15
0x18002dbf4  pop     r14
0x18002dbf6  pop     r13
0x18002dbf8  pop     r12
0x18002dbfa  pop     rdi
0x18002dbfb  pop     rsi
0x18002dbfc  pop     rbp
0x18002dbfd  retn
```
