# CDBPropSets::GetProperties(ulong,tagDBPROPIDSET const *,ulong *,tagDBPROPSET * *)

- ea: `0x18000c9f0`
- end: `0x18000ccd4`
- name: `?GetProperties@CDBPropSets@@QEAAJKPEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z`
- size: `740`
- prototype: `__int64 __fastcall(CDBPropSets *__hidden this, unsigned int, const struct tagDBPROPIDSET *, unsigned int *, struct tagDBPROPSET **)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c9e0`
- `0x18008e770`
- `0x18008e780`
- `0x1800d3b30`

## callees

- `0x18000b6d0`
- `0x18000c9f0`
- `0x180042b90`
- `0x180072cf4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cabc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ca48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000cabc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cbf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc86`
- `OLEAUT32!__imp_VariantClear` at `0x18000cc74`
- `OLEAUT32!__imp_VariantClear` at `0x18000cc74`
- `OLEAUT32!__imp_VariantCopy` at `0x18000cb9a`
- `OLEAUT32!__imp_VariantCopy` at `0x18000cb9a`

## pseudocode

```c
__int64 __fastcall CDBPropSets::GetProperties(
        struct _DSA **this,
        unsigned int a2,
        const struct tagDBPROPIDSET *a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5)
{
  const struct tagDBPROPIDSET *v5; // r14
  HRESULT v7; // ebx
  struct tagDBPROPSET *v8; // rax
  struct tagDBPROPSET *v9; // rdi
  int v10; // ebp
  unsigned int v11; // r15d
  __int64 v12; // r13
  struct tagDBPROPSET *v13; // rsi
  unsigned __int64 cPropertyIDs; // kr00_8
  DBPROP *v15; // rax
  ULONG v16; // eax
  __int64 v17; // r14
  __int64 p_vValue; // rcx
  int v19; // ebx
  struct _DSA *v20; // rcx
  int v21; // eax
  char *ItemPtr; // rax
  __int64 v23; // rcx
  size_t v25; // rax
  size_t v26; // rax
  unsigned int v27; // r14d
  __int64 v28; // r15
  __int64 v29; // rbp
  __int64 i; // rsi
  VARIANTARG *pvargDest; // [rsp+20h] [rbp-58h]
  DBPROPID dwPropertyID; // [rsp+88h] [rbp+10h]

  *a4 = 0;
  v5 = a3;
  v7 = -2147024809;
  *a5 = 0;
  if ( a2 )
  {
    if ( is_mul_ok(a2, 0x20u) )
    {
      v8 = (struct tagDBPROPSET *)CoTaskMemAlloc(32LL * a2);
      v9 = v8;
      if ( v8 )
      {
        v25 = CTCoAllocPolicy::_CoTaskMemSize(v8);
        memset_0(v9, 0, v25);
        v7 = 0;
      }
      else
      {
        v7 = -2147024882;
      }
      if ( v7 >= 0 )
      {
        v10 = 0;
        v11 = 0;
        if ( a2 )
        {
          while ( v7 >= 0 )
          {
            v12 = v11;
            v13 = &v9[v12];
            v13->guidPropertySet = v5[v12].guidPropertySet;
            cPropertyIDs = v5[v12].cPropertyIDs;
            v13->rgProperties = 0;
            if ( is_mul_ok(cPropertyIDs, 0x48u) )
            {
              v15 = (DBPROP *)CoTaskMemAlloc(72 * cPropertyIDs);
              v13->rgProperties = v15;
              if ( v15 )
              {
                v26 = CTCoAllocPolicy::_CoTaskMemSize(v15);
                memset_0(v13->rgProperties, 0, v26);
                v7 = 0;
              }
              else
              {
                v7 = -2147024882;
              }
              if ( v7 >= 0 )
              {
                v16 = v5[v12].cPropertyIDs;
                v17 = 0;
                for ( v13->cProperties = v16; (unsigned int)v17 < v13->cProperties; v17 = (unsigned int)(v17 + 1) )
                {
                  if ( v7 < 0 )
                    break;
                  v13->rgProperties[v17].dwPropertyID = a3[v11].rgPropertyIDs[v17];
                  p_vValue = (__int64)&v13->rgProperties[v17].vValue;
                  dwPropertyID = v13->rgProperties[v17].dwPropertyID;
                  *(_OWORD *)p_vValue = 0;
                  *(_QWORD *)(p_vValue + 16) = 0;
                  v19 = 0;
                  pvargDest = (VARIANTARG *)p_vValue;
                  while ( 1 )
                  {
                    v20 = *this;
                    v21 = *this ? *(_DWORD *)v20 : 0;
                    if ( v19 >= v21 )
                      break;
                    ItemPtr = (char *)g_pfn_DSA_GetItemPtr(v20, v19);
                    v23 = *(_QWORD *)ItemPtr - *(_QWORD *)&v13->guidPropertySet.Data1;
                    if ( *(_QWORD *)ItemPtr == *(_QWORD *)&v13->guidPropertySet.Data1 )
                      v23 = *((_QWORD *)ItemPtr + 1) - *(_QWORD *)v13->guidPropertySet.Data4;
                    if ( !v23 && *((_DWORD *)ItemPtr + 4) == dwPropertyID && !*((_DWORD *)ItemPtr + 6) )
                    {
                      v7 = VariantCopy(pvargDest, (const VARIANTARG *)(ItemPtr + 64));
                      if ( v7 != -2147023728 )
                        goto LABEL_25;
                      break;
                    }
                    ++v19;
                  }
                  v10 = 1;
                  v7 = 0;
                  v13->rgProperties[v17].dwStatus = 1;
LABEL_25:
                  ;
                }
                v5 = a3;
              }
            }
            else
            {
              v7 = -2147024362;
            }
            if ( ++v11 >= a2 )
            {
              if ( v7 >= 0 )
                goto LABEL_29;
              break;
            }
          }
          v27 = 0;
          v28 = 0;
          do
          {
            v29 = 0;
            for ( i = v28; (unsigned int)v29 < v9[i].cProperties; v29 = (unsigned int)(v29 + 1) )
              VariantClear((VARIANTARG *)((char *)&v9[i].rgProperties->vValue + 64 * v29 + 8 * v29));
            CoTaskMemFree(v9[i].rgProperties);
            ++v27;
            ++v28;
          }
          while ( v27 < a2 );
        }
        else
        {
LABEL_29:
          *a4 = a2;
          *a5 = v9;
          v9 = 0;
          v7 = v10 != 0 ? 0x40EDA : 0;
        }
        CoTaskMemFree(v9);
      }
    }
    else
    {
      return (unsigned int)-2147024362;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000c9f0  mov     r11, rsp
0x18000c9f3  mov     [r11+20h], r9
0x18000c9f7  mov     [r11+18h], r8
0x18000c9fb  mov     [r11+8], rcx
0x18000c9ff  push    rbx
0x18000ca00  push    rbp
0x18000ca01  push    rsi
0x18000ca02  push    rdi
0x18000ca03  push    r12
0x18000ca05  push    r13
0x18000ca07  push    r14
0x18000ca09  push    r15
0x18000ca0b  sub     rsp, 38h
0x18000ca0f  mov     rax, [rsp+78h+arg_20]
0x18000ca17  xor     ecx, ecx
0x18000ca19  mov     [r9], ecx
0x18000ca1c  mov     r14, r8
0x18000ca1f  mov     r12d, edx
0x18000ca22  mov     ebx, 80070057h
0x18000ca27  mov     [rax], rcx
0x18000ca2a  test    edx, edx
0x18000ca2c  jz      loc_18000CBFD
0x18000ca32  lea     eax, [rcx+20h]
0x18000ca35  mov     [r11-50h], rcx
0x18000ca39  mul     r12
0x18000ca3c  test    rdx, rdx
0x18000ca3f  jnz     loc_18000CC9D
0x18000ca45  mov     rcx, rax; cb
0x18000ca48  call    cs:__imp_CoTaskMemAlloc
0x18000ca4e  mov     rdi, rax
0x18000ca51  test    rax, rax
0x18000ca54  jnz     loc_18000CC10
0x18000ca5a  mov     ebx, 8007000Eh
0x18000ca5f  test    ebx, ebx
0x18000ca61  js      loc_18000CBFD
0x18000ca67  xor     ebp, ebp
0x18000ca69  xor     r15d, r15d
0x18000ca6c  test    r12d, r12d
0x18000ca6f  jz      loc_18000CBD2
0x18000ca75  test    ebx, ebx
0x18000ca77  js      loc_18000CC48
0x18000ca7d  mov     r13d, r15d
0x18000ca80  mov     eax, 48h ; 'H'
0x18000ca85  shl     r13, 5
0x18000ca89  mov     [rsp+78h+var_50], 0
0x18000ca92  movups  xmm0, xmmword ptr [r14+r13+0Ch]
0x18000ca98  lea     rsi, [rdi+r13]
0x18000ca9c  movdqu  xmmword ptr [rsi+0Ch], xmm0
0x18000caa1  mov     ecx, [r14+r13+8]
0x18000caa6  mul     rcx
0x18000caa9  mov     qword ptr [rsi], 0
0x18000cab0  test    rdx, rdx
0x18000cab3  jnz     loc_18000CCA7
0x18000cab9  mov     rcx, rax; cb
0x18000cabc  call    cs:__imp_CoTaskMemAlloc
0x18000cac2  mov     [rsi], rax
0x18000cac5  test    rax, rax
0x18000cac8  jnz     loc_18000CC2C
0x18000cace  mov     ebx, 8007000Eh
0x18000cad3  test    ebx, ebx
0x18000cad5  js      loc_18000CBC2
0x18000cadb  mov     eax, [r14+r13+8]
0x18000cae0  xor     r14d, r14d
0x18000cae3  mov     [rsi+8], eax
0x18000cae6  test    eax, eax
0x18000cae8  jz      loc_18000CBBA
0x18000caee  test    ebx, ebx
0x18000caf0  js      loc_18000CBBA
0x18000caf6  mov     rcx, [rsi]
0x18000caf9  lea     r8, [r14+r14*8]
0x18000cafd  mov     rax, [rsp+78h+arg_10]
0x18000cb05  xorps   xmm0, xmm0
0x18000cb08  mov     [rsp+78h+var_50], r8
0x18000cb0d  mov     rax, [rax+r13]
0x18000cb11  mov     eax, [rax+r14*4]
0x18000cb15  mov     [rcx+r8*8], eax
0x18000cb19  lea     rcx, [r8+6]
0x18000cb1d  mov     rax, [rsi]
0x18000cb20  lea     rcx, [rax+rcx*8]
0x18000cb24  mov     eax, [rax+r8*8]
0x18000cb28  mov     [rsp+78h+arg_8], eax
0x18000cb2f  xor     eax, eax
0x18000cb31  movups  xmmword ptr [rcx], xmm0
0x18000cb34  mov     [rcx+10h], rax
0x18000cb38  xor     ebx, ebx
0x18000cb3a  mov     [rsp+78h+pvargDest], rcx
0x18000cb3f  mov     rax, [rsp+78h+arg_0]
0x18000cb47  mov     rcx, [rax]; hdsa
0x18000cb4a  test    rcx, rcx
0x18000cb4d  jz      loc_18000CCB1
0x18000cb53  mov     eax, [rcx]
0x18000cb55  cmp     ebx, eax
0x18000cb57  jge     loc_18000CCB8
0x18000cb5d  mov     edx, ebx; i
0x18000cb5f  call    cs:g_pfn_DSA_GetItemPtr
0x18000cb65  mov     rcx, [rax]
0x18000cb68  sub     rcx, [rsi+0Ch]
0x18000cb6c  jnz     short loc_18000CB76
0x18000cb6e  mov     rcx, [rax+8]
0x18000cb72  sub     rcx, [rsi+14h]
0x18000cb76  test    rcx, rcx
0x18000cb79  jnz     short loc_18000CB87
0x18000cb7b  mov     ecx, [rsp+78h+arg_8]
0x18000cb82  cmp     [rax+10h], ecx
0x18000cb85  jz      short loc_18000CB8B
0x18000cb87  inc     ebx
0x18000cb89  jmp     short loc_18000CB3F
0x18000cb8b  cmp     dword ptr [rax+18h], 0
0x18000cb8f  jnz     short loc_18000CB87
0x18000cb91  mov     rcx, [rsp+78h+pvargDest]; pvargDest
0x18000cb96  lea     rdx, [rax+40h]; pvargSrc
0x18000cb9a  call    cs:__imp_VariantCopy
0x18000cba0  mov     ebx, eax
0x18000cba2  cmp     eax, 80070490h
0x18000cba7  jz      loc_18000CCB8
0x18000cbad  inc     r14d
0x18000cbb0  cmp     r14d, [rsi+8]
0x18000cbb4  jb      loc_18000CAEE
0x18000cbba  mov     r14, [rsp+78h+arg_10]
0x18000cbc2  inc     r15d
0x18000cbc5  cmp     r15d, r12d
0x18000cbc8  jb      loc_18000CA75
0x18000cbce  test    ebx, ebx
0x18000cbd0  js      short loc_18000CC48
0x18000cbd2  mov     rax, [rsp+78h+arg_18]
0x18000cbda  mov     [rax], r12d
0x18000cbdd  mov     rax, [rsp+78h+arg_20]
0x18000cbe5  mov     [rax], rdi
0x18000cbe8  xor     edi, edi
0x18000cbea  neg     ebp
0x18000cbec  sbb     ebx, ebx
0x18000cbee  and     ebx, 40EDAh
0x18000cbf4  mov     rcx, rdi; pv
0x18000cbf7  call    cs:__imp_CoTaskMemFree
0x18000cbfd  mov     eax, ebx
0x18000cbff  add     rsp, 38h
0x18000cc03  pop     r15
0x18000cc05  pop     r14
0x18000cc07  pop     r13
0x18000cc09  pop     r12
0x18000cc0b  pop     rdi
0x18000cc0c  pop     rsi
0x18000cc0d  pop     rbp
0x18000cc0e  pop     rbx
0x18000cc0f  retn
0x18000cc10  mov     rcx, rdi; void *
0x18000cc13  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000cc18  mov     r8, rax; Size
0x18000cc1b  xor     edx, edx; Val
0x18000cc1d  mov     rcx, rdi; void *
0x18000cc20  call    memset_0
0x18000cc25  xor     ebx, ebx
0x18000cc27  jmp     loc_18000CA5F
0x18000cc2c  mov     rcx, rax; void *
0x18000cc2f  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000cc34  mov     rcx, [rsi]; void *
0x18000cc37  mov     r8, rax; Size
0x18000cc3a  xor     edx, edx; Val
0x18000cc3c  call    memset_0
0x18000cc41  xor     ebx, ebx
0x18000cc43  jmp     loc_18000CAD3
0x18000cc48  xor     r14d, r14d
0x18000cc4b  xor     r15d, r15d
0x18000cc4e  mov     rsi, r15
0x18000cc51  xor     ebp, ebp
0x18000cc53  shl     rsi, 5
0x18000cc57  cmp     [rsi+rdi+8], ebp
0x18000cc5b  jbe     short loc_18000CC82
0x18000cc5d  mov     rax, [rsi+rdi]
0x18000cc61  lea     rcx, ds:0[rbp*8]
0x18000cc69  add     rcx, 6
0x18000cc6d  add     rcx, rbp
0x18000cc70  lea     rcx, [rax+rcx*8]; pvarg
0x18000cc74  call    cs:__imp_VariantClear
0x18000cc7a  inc     ebp
0x18000cc7c  cmp     ebp, [rsi+rdi+8]
0x18000cc80  jb      short loc_18000CC5D
0x18000cc82  mov     rcx, [rsi+rdi]; pv
0x18000cc86  call    cs:__imp_CoTaskMemFree
0x18000cc8c  inc     r14d
0x18000cc8f  inc     r15
0x18000cc92  cmp     r14d, r12d
0x18000cc95  jnb     loc_18000CBF4
0x18000cc9b  jmp     short loc_18000CC4E
0x18000cc9d  mov     ebx, 80070216h
0x18000cca2  jmp     loc_18000CBFD
0x18000cca7  mov     ebx, 80070216h
0x18000ccac  jmp     loc_18000CBC2
0x18000ccb1  xor     eax, eax
0x18000ccb3  jmp     loc_18000CB55
0x18000ccb8  mov     rax, [rsi]
0x18000ccbb  mov     ebp, 1
0x18000ccc0  mov     rcx, [rsp+78h+var_50]
0x18000ccc5  xor     ebx, ebx
0x18000ccc7  mov     dword ptr [rax+rcx*8+8], 1
0x18000cccf  jmp     loc_18000CBAD
```
