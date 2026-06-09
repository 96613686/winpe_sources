# CDBPropSets::SetProperties(ulong,tagDBPROPSET *)

- ea: `0x180048a90`
- end: `0x180048cc4`
- name: `?SetProperties@CDBPropSets@@QEAAJKPEAUtagDBPROPSET@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(CDBPropSets *__hidden this, unsigned int, struct tagDBPROPSET *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180048a70`
- `0x180048a80`
- `0x1800d4010`

## callees

- `0x180042a50`
- `0x180042b90`
- `0x180048a90`
- `0x180071dc0`
- `0x180072cf4`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180048c24`
- `OLEAUT32!__imp_VariantClear` at `0x180048c83`
- `OLEAUT32!__imp_VariantClear` at `0x180048c24`
- `OLEAUT32!__imp_VariantClear` at `0x180048c83`
- `OLEAUT32!__imp_VariantCopy` at `0x180048be6`
- `OLEAUT32!__imp_VariantCopy` at `0x180048c91`
- `OLEAUT32!__imp_VariantCopy` at `0x180048be6`
- `OLEAUT32!__imp_VariantCopy` at `0x180048c91`

## pseudocode

```c
__int64 __fastcall CDBPropSets::SetProperties(HDSA *this, unsigned int a2, struct tagDBPROPSET *a3)
{
  unsigned int v3; // eax
  HRESULT v4; // ebx
  unsigned int v5; // r14d
  struct _DSA **i; // rdx
  __int64 v8; // r15
  __int64 v9; // r13
  int v10; // r12d
  DBPROP *rgProperties; // rax
  struct _DSA *v12; // rcx
  int v13; // eax
  char *ItemPtr; // rdi
  __int64 v15; // rax
  GUID guidPropertySet; // xmm0
  DBPROPID dwPropertyID; // [rsp+20h] [rbp-69h]
  DBPROPOPTIONS dwOptions; // [rsp+24h] [rbp-65h]
  VARIANTARG *pvargSrc; // [rsp+38h] [rbp-51h]
  GUID pitem; // [rsp+40h] [rbp-49h] BYREF
  DBPROPID v24; // [rsp+50h] [rbp-39h]
  DBPROPOPTIONS v25; // [rsp+54h] [rbp-35h]
  int v26; // [rsp+58h] [rbp-31h]
  DBID v27; // [rsp+60h] [rbp-29h]
  VARIANTARG pvargDest; // [rsp+80h] [rbp-9h] BYREF

  v3 = a2;
  v4 = 0;
  v5 = 0;
  for ( i = this; v5 < v3; ++v5 )
  {
    if ( v4 < 0 )
      break;
    v8 = 0;
    if ( a3->cProperties )
    {
      do
      {
        if ( v4 < 0 )
          break;
        v9 = v5;
        v4 = -2147023728;
        v10 = 0;
        rgProperties = a3[v9].rgProperties;
        pvargSrc = &rgProperties[v8].vValue;
        dwPropertyID = rgProperties[v8].dwPropertyID;
        dwOptions = rgProperties[v8].dwOptions;
        while ( 1 )
        {
          v12 = *i;
          v13 = *i ? *(_DWORD *)v12 : 0;
          if ( v10 >= v13 )
            break;
          if ( v4 != -2147023728 )
            goto LABEL_21;
          ItemPtr = (char *)g_pfn_DSA_GetItemPtr(v12, v10);
          v15 = *(_QWORD *)ItemPtr - *(_QWORD *)&a3[v9].guidPropertySet.Data1;
          if ( !v15 )
            v15 = *((_QWORD *)ItemPtr + 1) - *(_QWORD *)a3[v9].guidPropertySet.Data4;
          if ( !v15 && *((_DWORD *)ItemPtr + 4) == dwPropertyID )
          {
            VariantClear((VARIANTARG *)(ItemPtr + 64));
            v4 = VariantCopy((VARIANTARG *)(ItemPtr + 64), pvargSrc);
            if ( v4 >= 0 )
              *(_QWORD *)(ItemPtr + 20) = dwOptions;
          }
          i = this;
          ++v10;
        }
        if ( v4 == -2147023728 && pvargSrc->vt != 10 )
        {
          memset_0(&pitem, 0, 0x58u);
          guidPropertySet = a3[v9].guidPropertySet;
          v24 = dwPropertyID;
          pitem = guidPropertySet;
          v25 = dwOptions;
          v26 = 0;
          v27 = DB_NULLID;
          memset(&pvargDest, 0, sizeof(pvargDest));
          v4 = VariantCopy(&pvargDest, pvargSrc);
          if ( v4 >= 0 )
          {
            if ( DSA_InsertItem(*this, 0x7FFFFFFF, &pitem) == -1 )
            {
              v4 = -2147024882;
            }
            else
            {
              v4 = 0;
              memset(&pvargDest, 0, sizeof(pvargDest));
            }
            VariantClear(&pvargDest);
          }
          i = this;
        }
LABEL_21:
        v8 = (unsigned int)(v8 + 1);
      }
      while ( (unsigned int)v8 < a3->cProperties );
      v3 = a2;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180048a90  mov     [rsp-8+arg_8], rbx
0x180048a95  push    rbp
0x180048a96  push    rsi
0x180048a97  push    rdi
0x180048a98  push    r12
0x180048a9a  push    r13
0x180048a9c  push    r14
0x180048a9e  push    r15
0x180048aa0  lea     rbp, [rsp-27h]
0x180048aa5  sub     rsp, 0B0h
0x180048aac  mov     rax, cs:__security_cookie
0x180048ab3  xor     rax, rsp
0x180048ab6  mov     [rbp+57h+var_40], rax
0x180048aba  mov     eax, edx
0x180048abc  mov     [rbp+57h+var_B0], edx
0x180048abf  xor     ebx, ebx
0x180048ac1  mov     [rbp+57h+var_B8], rcx
0x180048ac5  xor     r14d, r14d
0x180048ac8  mov     rsi, r8
0x180048acb  mov     rdx, rcx
0x180048ace  test    eax, eax
0x180048ad0  jz      loc_180048C4A
0x180048ad6  test    ebx, ebx
0x180048ad8  js      loc_180048C4A
0x180048ade  xor     r15d, r15d
0x180048ae1  cmp     [rsi+8], r15d
0x180048ae5  jbe     loc_180048C3E
0x180048aeb  test    ebx, ebx
0x180048aed  js      loc_180048C3B
0x180048af3  lea     rcx, [r15+r15*8]
0x180048af7  mov     r13d, r14d
0x180048afa  shl     r13, 5
0x180048afe  lea     rdi, [rcx+6]
0x180048b02  mov     ebx, 80070490h
0x180048b07  xor     r12d, r12d
0x180048b0a  mov     rax, [rsi+r13]
0x180048b0e  mov     r8d, [rax+rcx*8+4]
0x180048b13  lea     rdi, [rax+rdi*8]
0x180048b17  mov     eax, [rax+rcx*8]
0x180048b1a  mov     [rbp+57h+pvargSrc], rdi
0x180048b1e  mov     [rbp+57h+var_C0], eax
0x180048b21  mov     [rbp+57h+var_BC], r8d
0x180048b25  mov     rcx, [rdx]; hdsa
0x180048b28  test    rcx, rcx
0x180048b2b  jz      loc_180048CBD
0x180048b31  mov     eax, [rcx]
0x180048b33  cmp     r12d, eax
0x180048b36  jge     short loc_180048B75
0x180048b38  cmp     ebx, 80070490h
0x180048b3e  jnz     loc_180048C2E
0x180048b44  mov     edx, r12d; i
0x180048b47  call    cs:g_pfn_DSA_GetItemPtr
0x180048b4d  mov     rdi, rax
0x180048b50  mov     rax, [rax]
0x180048b53  sub     rax, [rsi+r13+0Ch]
0x180048b58  jnz     short loc_180048B63
0x180048b5a  mov     rax, [rdi+8]
0x180048b5e  sub     rax, [rsi+r13+14h]
0x180048b63  test    rax, rax
0x180048b66  jz      loc_180048C73
0x180048b6c  mov     rdx, [rbp+57h+var_B8]
0x180048b70  inc     r12d
0x180048b73  jmp     short loc_180048B25
0x180048b75  cmp     ebx, 80070490h
0x180048b7b  jnz     loc_180048C2E
0x180048b81  mov     rdi, [rbp+57h+pvargSrc]
0x180048b85  cmp     word ptr [rdi], 0Ah
0x180048b89  jz      loc_180048C2E
0x180048b8f  xor     edx, edx; Val
0x180048b91  lea     rcx, [rbp+57h+pitem]; void *
0x180048b95  lea     r8d, [rdx+58h]; Size
0x180048b99  call    memset_0
0x180048b9e  movups  xmm0, xmmword ptr [rsi+r13+0Ch]
0x180048ba4  mov     eax, [rbp+57h+var_C0]
0x180048ba7  lea     rcx, [rbp+57h+pvargDest]; pvargDest
0x180048bab  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x180048bb2  mov     [rbp+57h+var_90], eax
0x180048bb5  mov     rdx, rdi; pvargSrc
0x180048bb8  mov     eax, [rbp+57h+var_BC]
0x180048bbb  movdqu  [rbp+57h+pitem], xmm0
0x180048bc0  mov     [rbp+57h+var_8C], eax
0x180048bc3  xor     eax, eax
0x180048bc5  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x180048bcc  mov     [rbp+57h+var_88], 0
0x180048bd3  movaps  [rbp+57h+var_70], xmm1
0x180048bd7  movaps  [rbp+57h+var_80], xmm0
0x180048bdb  xorps   xmm0, xmm0
0x180048bde  movups  xmmword ptr [rbp+57h+pvargDest], xmm0
0x180048be2  mov     qword ptr [rbp+57h+pvargDest+10h], rax
0x180048be6  call    cs:__imp_VariantCopy
0x180048bec  mov     ebx, eax
0x180048bee  test    eax, eax
0x180048bf0  js      short loc_180048C2A
0x180048bf2  mov     rcx, [rbp+57h+var_B8]
0x180048bf6  lea     r8, [rbp+57h+pitem]; pitem
0x180048bfa  mov     edx, 7FFFFFFFh; i
0x180048bff  mov     rcx, [rcx]; hdsa
0x180048c02  call    cs:__imp_DSA_InsertItem
0x180048c08  cmp     eax, 0FFFFFFFFh
0x180048c0b  jz      loc_180048CB3
0x180048c11  xor     ebx, ebx
0x180048c13  xorps   xmm0, xmm0
0x180048c16  xor     eax, eax
0x180048c18  mov     qword ptr [rbp+57h+pvargDest+10h], rax
0x180048c1c  movups  xmmword ptr [rbp+57h+pvargDest], xmm0
0x180048c20  lea     rcx, [rbp+57h+pvargDest]; pvarg
0x180048c24  call    cs:__imp_VariantClear
0x180048c2a  mov     rdx, [rbp+57h+var_B8]
0x180048c2e  inc     r15d
0x180048c31  cmp     r15d, [rsi+8]
0x180048c35  jb      loc_180048AEB
0x180048c3b  mov     eax, [rbp+57h+var_B0]
0x180048c3e  inc     r14d
0x180048c41  cmp     r14d, eax
0x180048c44  jb      loc_180048AD6
0x180048c4a  mov     eax, ebx
0x180048c4c  mov     rcx, [rbp+57h+var_40]
0x180048c50  xor     rcx, rsp; StackCookie
0x180048c53  call    __security_check_cookie
0x180048c58  mov     rbx, [rsp+0E0h+arg_8]
0x180048c60  add     rsp, 0B0h
0x180048c67  pop     r15
0x180048c69  pop     r14
0x180048c6b  pop     r13
0x180048c6d  pop     r12
0x180048c6f  pop     rdi
0x180048c70  pop     rsi
0x180048c71  pop     rbp
0x180048c72  retn
0x180048c73  mov     eax, [rbp+57h+var_C0]
0x180048c76  cmp     [rdi+10h], eax
0x180048c79  jnz     loc_180048B6C
0x180048c7f  lea     rcx, [rdi+40h]; pvarg
0x180048c83  call    cs:__imp_VariantClear
0x180048c89  mov     rdx, [rbp+57h+pvargSrc]; pvargSrc
0x180048c8d  lea     rcx, [rdi+40h]; pvargDest
0x180048c91  call    cs:__imp_VariantCopy
0x180048c97  mov     ebx, eax
0x180048c99  test    eax, eax
0x180048c9b  js      loc_180048B6C
0x180048ca1  mov     eax, [rbp+57h+var_BC]
0x180048ca4  mov     [rdi+14h], eax
0x180048ca7  mov     dword ptr [rdi+18h], 0
0x180048cae  jmp     loc_180048B6C
0x180048cb3  mov     ebx, 8007000Eh
0x180048cb8  jmp     loc_180048C20
0x180048cbd  xor     eax, eax
0x180048cbf  jmp     loc_180048B33
```
