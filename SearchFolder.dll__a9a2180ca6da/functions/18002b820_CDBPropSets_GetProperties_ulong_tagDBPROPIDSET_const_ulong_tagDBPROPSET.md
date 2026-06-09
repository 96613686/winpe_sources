# CDBPropSets::GetProperties(ulong,tagDBPROPIDSET const *,ulong *,tagDBPROPSET * *)

- ea: `0x18002b820`
- end: `0x18002ba81`
- name: `?GetProperties@CDBPropSets@@QEAAJKPEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z`
- size: `609`
- prototype: `int(CDBPropSets *__hidden this, unsigned int, const struct tagDBPROPIDSET *, unsigned int *, struct tagDBPROPSET **)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ba90`
- `0x18002baa0`
- `0x18002bab0`
- `0x18002bb10`
- `0x1800421f0`
- `0x180042200`
- `0x180042210`

## callees

- `0x180009d00`
- `0x18000f718`
- `0x18002b820`
- `0x18002bb8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ba2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ba68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ba2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002ba68`
- `OLEAUT32!__imp_VariantClear` at `0x18002ba1a`
- `OLEAUT32!__imp_VariantClear` at `0x18002ba1a`

## pseudocode

```c
__int64 __fastcall CDBPropSets::GetProperties(
        CDBPropSets *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5)
{
  unsigned int v5; // ebp
  int Property; // ebx
  struct tagDBPROPSET *v7; // rdi
  void *v8; // rcx
  const struct tagDBPROPIDSET *v9; // r9
  int v10; // eax
  unsigned int v11; // r15d
  int v12; // esi
  __int64 v13; // r13
  struct tagDBPROPSET *v14; // r14
  unsigned __int64 cPropertyIDs; // rcx
  void *v16; // rcx
  const struct tagDBPROPIDSET *v17; // r9
  int v18; // eax
  ULONG v19; // eax
  __int64 v20; // r12
  DBPROPID *rgPropertyIDs; // rax
  DBPROP *rgProperties; // rcx
  unsigned int v23; // r15d
  __int64 v24; // r13
  __int64 v25; // r14
  __int64 i; // rsi
  unsigned __int64 v28; // [rsp+20h] [rbp-68h] BYREF
  void *v29; // [rsp+28h] [rbp-60h] BYREF
  struct tagDBPROPSET *v30; // [rsp+30h] [rbp-58h]

  v5 = a2;
  Property = -2147024809;
  *a4 = 0;
  *a5 = 0;
  if ( a2 )
  {
    v7 = 0;
    v30 = 0;
    v29 = 0;
    v28 = 0;
    Property = ULongLongMult(a2, 0x20u, &v28);
    if ( Property >= 0 )
    {
      v10 = CTCoAllocPolicy::Alloc(v8, 1u, v28, &v29);
      v7 = (struct tagDBPROPSET *)v29;
      Property = v10;
      v9 = a3;
      v30 = (struct tagDBPROPSET *)v29;
    }
    if ( Property >= 0 )
    {
      v11 = 0;
      v12 = 0;
      LODWORD(v28) = 0;
      if ( v5 )
      {
        while ( Property >= 0 )
        {
          v13 = v11;
          v29 = 0;
          v14 = &v7[v13];
          v14->guidPropertySet = v9[v13].guidPropertySet;
          cPropertyIDs = v9[v13].cPropertyIDs;
          v14->rgProperties = 0;
          Property = ULongLongMult(cPropertyIDs, 0x48u, (unsigned __int64 *)&v29);
          if ( Property >= 0 )
          {
            v18 = CTCoAllocPolicy::Alloc(v16, 1u, (unsigned __int64)v29, (void **)&v7[v13].rgProperties);
            v17 = a3;
            Property = v18;
          }
          if ( Property >= 0 )
          {
            v19 = v17[v13].cPropertyIDs;
            v20 = 0;
            v14->cProperties = v19;
            if ( v19 )
            {
              do
              {
                if ( Property < 0 )
                  break;
                rgPropertyIDs = a3[v11].rgPropertyIDs;
                rgProperties = v14->rgProperties;
                v29 = (void *)(9 * v20);
                *(&rgProperties->dwPropertyID + 2 * (_QWORD)v29) = rgPropertyIDs[v20];
                Property = CDBPropSets::GetProperty(
                             this,
                             &v14->guidPropertySet,
                             v14->rgProperties[v20].dwPropertyID,
                             &v14->rgProperties[v20].vValue);
                if ( Property == -2147023728 )
                {
                  v12 = 1;
                  Property = 0;
                  *(&v14->rgProperties->dwStatus + 2 * (_QWORD)v29) = 1;
                }
                v20 = (unsigned int)(v20 + 1);
              }
              while ( (unsigned int)v20 < v14->cProperties );
              v7 = v30;
              v5 = a2;
              v11 = v28;
            }
          }
          v9 = a3;
          LODWORD(v28) = ++v11;
          if ( v11 >= v5 )
          {
            if ( Property >= 0 )
              goto LABEL_23;
            break;
          }
        }
        v23 = 0;
        v24 = 0;
        do
        {
          v25 = 0;
          for ( i = v24; (unsigned int)v25 < v7[i].cProperties; v25 = (unsigned int)(v25 + 1) )
            VariantClear((VARIANTARG *)((char *)&v7[i].rgProperties->vValue + 64 * v25 + 8 * v25));
          CoTaskMemFree(v7[i].rgProperties);
          ++v23;
          ++v24;
        }
        while ( v23 < v5 );
      }
      else
      {
LABEL_23:
        *a4 = v5;
        *a5 = v7;
        v7 = 0;
        if ( v12 )
          Property = 265946;
        else
          Property = 0;
      }
      CoTaskMemFree(v7);
    }
  }
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18002b820  mov     r11, rsp
0x18002b823  mov     [r11+20h], r9
0x18002b827  mov     [r11+18h], r8
0x18002b82b  mov     [rsp+arg_8], edx
0x18002b82f  mov     [r11+8], rcx
0x18002b833  push    rbx
0x18002b834  push    rbp
0x18002b835  push    rsi
0x18002b836  push    rdi
0x18002b837  push    r12
0x18002b839  push    r13
0x18002b83b  push    r14
0x18002b83d  push    r15
0x18002b83f  sub     rsp, 48h
0x18002b843  mov     ebp, edx
0x18002b845  mov     rax, r9
0x18002b848  mov     r9, r8
0x18002b84b  mov     ebx, 80070057h
0x18002b850  mov     dword ptr [rax], 0
0x18002b856  mov     rax, [rsp+88h+arg_20]
0x18002b85e  mov     qword ptr [rax], 0
0x18002b865  test    edx, edx
0x18002b867  jz      loc_18002BA6E
0x18002b86d  xor     edi, edi
0x18002b86f  lea     r8, [r11-68h]; unsigned __int64 *
0x18002b873  mov     ecx, ebp; unsigned __int64
0x18002b875  mov     [rsp+88h+var_58], rdi
0x18002b87a  mov     [r11-60h], rdi
0x18002b87e  mov     [r11-68h], rdi
0x18002b882  lea     edx, [rdi+20h]; unsigned __int64
0x18002b885  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002b88a  mov     ebx, eax
0x18002b88c  test    eax, eax
0x18002b88e  js      short loc_18002B8B6
0x18002b890  mov     r8, [rsp+88h+var_68]; unsigned __int64
0x18002b895  lea     r9, [rsp+88h+var_60]; void **
0x18002b89a  lea     edx, [rdi+1]; unsigned int
0x18002b89d  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002b8a2  mov     rdi, [rsp+88h+var_60]
0x18002b8a7  mov     ebx, eax
0x18002b8a9  mov     r9, [rsp+88h+arg_10]
0x18002b8b1  mov     [rsp+88h+var_58], rdi
0x18002b8b6  test    ebx, ebx
0x18002b8b8  js      loc_18002BA6E
0x18002b8be  xor     r15d, r15d
0x18002b8c1  xor     esi, esi
0x18002b8c3  mov     dword ptr [rsp+88h+var_68], r15d
0x18002b8c8  test    ebp, ebp
0x18002b8ca  jz      loc_18002BA41
0x18002b8d0  test    ebx, ebx
0x18002b8d2  js      loc_18002B9F0
0x18002b8d8  mov     r13d, r15d
0x18002b8db  lea     r8, [rsp+88h+var_60]; unsigned __int64 *
0x18002b8e0  shl     r13, 5
0x18002b8e4  mov     edx, 48h ; 'H'; unsigned __int64
0x18002b8e9  mov     [rsp+88h+var_60], 0
0x18002b8f2  movups  xmm0, xmmword ptr [r9+r13+0Ch]
0x18002b8f8  lea     r14, [rdi+r13]
0x18002b8fc  movdqu  xmmword ptr [r14+0Ch], xmm0
0x18002b902  mov     ecx, [r9+r13+8]; unsigned __int64
0x18002b907  mov     qword ptr [r14], 0
0x18002b90e  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002b913  mov     ebx, eax
0x18002b915  test    eax, eax
0x18002b917  js      short loc_18002B935
0x18002b919  mov     r8, [rsp+88h+var_60]; unsigned __int64
0x18002b91e  mov     r9, r14; void **
0x18002b921  mov     edx, 1; unsigned int
0x18002b926  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18002b92b  mov     r9, [rsp+88h+arg_10]
0x18002b933  mov     ebx, eax
0x18002b935  test    ebx, ebx
0x18002b937  js      loc_18002B9D3
0x18002b93d  mov     eax, [r9+r13+8]
0x18002b942  xor     r12d, r12d
0x18002b945  mov     [r14+8], eax
0x18002b949  test    eax, eax
0x18002b94b  jz      loc_18002B9D3
0x18002b951  mov     rbp, [rsp+88h+arg_10]
0x18002b959  mov     r15, [rsp+88h+arg_0]
0x18002b961  test    ebx, ebx
0x18002b963  js      short loc_18002B9C2
0x18002b965  mov     rax, [rbp+r13+0]
0x18002b96a  lea     r10, [r12+r12*8]
0x18002b96e  mov     rcx, [r14]
0x18002b971  lea     r9, [r10+6]
0x18002b975  lea     rdx, [r14+0Ch]; struct _GUID *
0x18002b979  mov     [rsp+88h+var_60], r10
0x18002b97e  mov     eax, [rax+r12*4]
0x18002b982  mov     [rcx+r10*8], eax
0x18002b986  mov     rcx, r15; this
0x18002b989  mov     r8, [r14]
0x18002b98c  lea     r9, [r8+r9*8]; struct tagVARIANT *
0x18002b990  mov     r8d, [r8+r10*8]; unsigned int
0x18002b994  call    ?GetProperty@CDBPropSets@@QEAAJAEBU_GUID@@KPEAUtagVARIANT@@@Z; CDBPropSets::GetProperty(_GUID const &,ulong,tagVARIANT *)
0x18002b999  mov     ebx, eax
0x18002b99b  cmp     eax, 80070490h
0x18002b9a0  jnz     short loc_18002B9B9
0x18002b9a2  mov     rax, [r14]
0x18002b9a5  mov     esi, 1
0x18002b9aa  mov     rcx, [rsp+88h+var_60]
0x18002b9af  xor     ebx, ebx
0x18002b9b1  mov     dword ptr [rax+rcx*8+8], 1
0x18002b9b9  inc     r12d
0x18002b9bc  cmp     r12d, [r14+8]
0x18002b9c0  jb      short loc_18002B961
0x18002b9c2  mov     rdi, [rsp+88h+var_58]
0x18002b9c7  mov     ebp, [rsp+88h+arg_8]
0x18002b9ce  mov     r15d, dword ptr [rsp+88h+var_68]
0x18002b9d3  mov     r9, [rsp+88h+arg_10]
0x18002b9db  inc     r15d
0x18002b9de  mov     dword ptr [rsp+88h+var_68], r15d
0x18002b9e3  cmp     r15d, ebp
0x18002b9e6  jb      loc_18002B8D0
0x18002b9ec  test    ebx, ebx
0x18002b9ee  jns     short loc_18002BA41
0x18002b9f0  xor     r15d, r15d
0x18002b9f3  xor     r13d, r13d
0x18002b9f6  mov     rsi, r13
0x18002b9f9  xor     r14d, r14d
0x18002b9fc  shl     rsi, 5
0x18002ba00  cmp     [rsi+rdi+8], r14d
0x18002ba05  jbe     short loc_18002BA2A
0x18002ba07  mov     rax, [rsi+rdi]
0x18002ba0b  lea     rcx, ds:6[r14*8]
0x18002ba13  add     rcx, r14
0x18002ba16  lea     rcx, [rax+rcx*8]; pvarg
0x18002ba1a  call    cs:__imp_VariantClear
0x18002ba20  inc     r14d
0x18002ba23  cmp     r14d, [rsi+rdi+8]
0x18002ba28  jb      short loc_18002BA07
0x18002ba2a  mov     rcx, [rsi+rdi]; pv
0x18002ba2e  call    cs:__imp_CoTaskMemFree
0x18002ba34  inc     r15d
0x18002ba37  inc     r13
0x18002ba3a  cmp     r15d, ebp
0x18002ba3d  jb      short loc_18002B9F6
0x18002ba3f  jmp     short loc_18002BA65
0x18002ba41  mov     rax, [rsp+88h+arg_18]
0x18002ba49  mov     [rax], ebp
0x18002ba4b  mov     rax, [rsp+88h+arg_20]
0x18002ba53  mov     [rax], rdi
0x18002ba56  xor     edi, edi
0x18002ba58  test    esi, esi
0x18002ba5a  jz      short loc_18002BA63
0x18002ba5c  mov     ebx, 40EDAh
0x18002ba61  jmp     short loc_18002BA65
0x18002ba63  xor     ebx, ebx
0x18002ba65  mov     rcx, rdi; pv
0x18002ba68  call    cs:__imp_CoTaskMemFree
0x18002ba6e  mov     eax, ebx
0x18002ba70  add     rsp, 48h
0x18002ba74  pop     r15
0x18002ba76  pop     r14
0x18002ba78  pop     r13
0x18002ba7a  pop     r12
0x18002ba7c  pop     rdi
0x18002ba7d  pop     rsi
0x18002ba7e  pop     rbp
0x18002ba7f  pop     rbx
0x18002ba80  retn
```
