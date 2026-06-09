# VarTypeToIISTypeCopy(ulong,tagVARIANT *,_iistype *,int,ushort const *)

- ea: `0x180018a44`
- end: `0x180018c01`
- name: `?VarTypeToIISTypeCopy@@YAJKPEAUtagVARIANT@@PEAU_iistype@@HPEBG@Z`
- size: `445`
- prototype: `int(unsigned int, struct tagVARIANT *, struct _iistype *, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180018c08`

## callees

- `0x180018a44`
- `0x180018cbc`
- `0x180018f20`
- `0x180018fb4`
- `0x18001908c`

## import_xrefs

- `OLEAUT32!__imp_VariantChangeType` at `0x180018aa8`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018adc`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018afc`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018b2f`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018b66`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018bcf`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018aa8`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018adc`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018afc`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018b2f`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018b66`
- `OLEAUT32!__imp_VariantChangeType` at `0x180018bcf`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180018b12`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180018b12`

## pseudocode

```c
HRESULT __fastcall VarTypeToIISTypeCopy(
        unsigned int a1,
        struct tagVARIANT *a2,
        struct _iistype *a3,
        int a4,
        unsigned __int16 *a5)
{
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  HRESULT result; // eax
  HRESULT v12; // esi
  bool v13; // zf
  HRESULT v14; // edx
  int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx

  if ( a1 <= 6 )
  {
    if ( a1 != 6 )
    {
      v7 = a1 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( v10 )
            {
              if ( v10 == 1 )
                return VarTypeToIISTypeCopyIISSynIdBinary(a2, a3, a4);
              return -2147467259;
            }
            v12 = VariantChangeType(a2, a2, 0, 8u);
            if ( v12 < 0 )
              goto LABEL_10;
            *(_DWORD *)a3 = 4;
LABEL_19:
            *((_QWORD *)a3 + 1) = AllocADsStr(a2->bstrVal);
            return v12;
          }
          v12 = VariantChangeType(a2, a2, 0, 8u);
          if ( v12 >= 0 )
          {
            *(_DWORD *)a3 = 3;
            goto LABEL_19;
          }
        }
        else
        {
          v12 = VariantChangeType(a2, a2, 0, 8u);
          if ( v12 >= 0 )
          {
            *(_DWORD *)a3 = 2;
            goto LABEL_19;
          }
        }
LABEL_10:
        v13 = v12 == -2147024882;
        goto LABEL_11;
      }
      v14 = VariantChangeType(a2, a2, 0, 0x13u);
      if ( v14 >= 0 )
      {
        *(_DWORD *)a3 = 1;
        *((_DWORD *)a3 + 2) = a2->lVal;
        return v14;
      }
LABEL_21:
      v13 = v14 == -2147024882;
LABEL_11:
      result = -2147463156;
      if ( v13 )
        return -2147024882;
      return result;
    }
    result = VariantChangeType(a2, a2, 0, 0xBu);
    v15 = 0;
    v14 = result;
    if ( result < 0 )
      goto LABEL_21;
    *(_DWORD *)a3 = 6;
LABEL_35:
    LOBYTE(v15) = a2->iVal != 0;
    *((_DWORD *)a3 + 2) = v15;
    return result;
  }
  v16 = a1 - 7;
  if ( !v16 )
  {
    result = VariantChangeType(a2, a2, 0, 0xBu);
    v15 = 0;
    v14 = result;
    if ( result < 0 )
      goto LABEL_21;
    *(_DWORD *)a3 = 7;
    goto LABEL_35;
  }
  v17 = v16 - 1;
  if ( !v17 )
    return VarTypeToIISTypeCopyIISSynIdMIMEMAP(a2, a3);
  v18 = v17 - 1;
  if ( !v18 )
    return VarTypeToIISTypeCopyIISSynIdIPSECLIST(a2, a3);
  if ( v18 != 1 )
    return -2147467259;
  return VarTypeToIISTypeCopyIISSynIdNTACL(a2, a3, a5);
}

```

## disassembly

```asm
0x180018a44  mov     [rsp+arg_0], rbx
0x180018a49  mov     [rsp+arg_8], rsi
0x180018a4e  push    rdi
0x180018a4f  sub     rsp, 20h
0x180018a53  mov     rdi, r8
0x180018a56  mov     rbx, rdx
0x180018a59  cmp     ecx, 6
0x180018a5c  ja      loc_180018B7C
0x180018a62  jz      loc_180018B5A
0x180018a68  sub     ecx, 1
0x180018a6b  jz      loc_180018B23
0x180018a71  sub     ecx, 1
0x180018a74  jz      short loc_180018AF0
0x180018a76  sub     ecx, 1
0x180018a79  jz      short loc_180018AD0
0x180018a7b  sub     ecx, 1
0x180018a7e  jz      short loc_180018A9C
0x180018a80  cmp     ecx, 1
0x180018a83  jnz     loc_180018B90
0x180018a89  mov     r8d, r9d; int
0x180018a8c  mov     rdx, rdi; struct _iistype *
0x180018a8f  mov     rcx, rbx; pvarSrc
0x180018a92  call    ?VarTypeToIISTypeCopyIISSynIdBinary@@YAJPEAUtagVARIANT@@PEAU_iistype@@H@Z; VarTypeToIISTypeCopyIISSynIdBinary(tagVARIANT *,_iistype *,int)
0x180018a97  jmp     loc_180018BF1
0x180018a9c  mov     r9d, 8; vt
0x180018aa2  xor     r8d, r8d; wFlags
0x180018aa5  mov     rcx, rbx; pvargDest
0x180018aa8  call    cs:__imp_VariantChangeType
0x180018aae  mov     esi, eax
0x180018ab0  test    eax, eax
0x180018ab2  jns     short loc_180018AC8
0x180018ab4  mov     ecx, 8007000Eh
0x180018ab9  cmp     esi, ecx
0x180018abb  mov     eax, 8000500Ch
0x180018ac0  cmovz   eax, ecx
0x180018ac3  jmp     loc_180018BF1
0x180018ac8  mov     dword ptr [rdi], 4
0x180018ace  jmp     short loc_180018B0E
0x180018ad0  mov     r9d, 8; vt
0x180018ad6  xor     r8d, r8d; wFlags
0x180018ad9  mov     rcx, rbx; pvargDest
0x180018adc  call    cs:__imp_VariantChangeType
0x180018ae2  mov     esi, eax
0x180018ae4  test    eax, eax
0x180018ae6  js      short loc_180018AB4
0x180018ae8  mov     dword ptr [rdi], 3
0x180018aee  jmp     short loc_180018B0E
0x180018af0  mov     r9d, 8; vt
0x180018af6  xor     r8d, r8d; wFlags
0x180018af9  mov     rcx, rbx; pvargDest
0x180018afc  call    cs:__imp_VariantChangeType
0x180018b02  mov     esi, eax
0x180018b04  test    eax, eax
0x180018b06  js      short loc_180018AB4
0x180018b08  mov     dword ptr [rdi], 2
0x180018b0e  mov     rcx, [rbx+8]; pStr
0x180018b12  call    cs:__imp_AllocADsStr
0x180018b18  mov     [rdi+8], rax
0x180018b1c  mov     eax, esi
0x180018b1e  jmp     loc_180018BF1
0x180018b23  mov     r9d, 13h; vt
0x180018b29  xor     r8d, r8d; wFlags
0x180018b2c  mov     rcx, rbx; pvargDest
0x180018b2f  call    cs:__imp_VariantChangeType
0x180018b35  mov     edx, eax; pvarSrc
0x180018b37  test    eax, eax
0x180018b39  jns     short loc_180018B47
0x180018b3b  mov     ecx, 8007000Eh
0x180018b40  cmp     edx, ecx
0x180018b42  jmp     loc_180018ABB
0x180018b47  mov     dword ptr [rdi], 1
0x180018b4d  mov     eax, [rbx+8]
0x180018b50  mov     [rdi+8], eax
0x180018b53  mov     eax, edx
0x180018b55  jmp     loc_180018BF1
0x180018b5a  mov     r9d, 0Bh; vt
0x180018b60  xor     r8d, r8d; wFlags
0x180018b63  mov     rcx, rbx; pvargDest
0x180018b66  call    cs:__imp_VariantChangeType
0x180018b6c  xor     ecx, ecx
0x180018b6e  mov     edx, eax
0x180018b70  test    eax, eax
0x180018b72  js      short loc_180018B3B
0x180018b74  mov     dword ptr [rdi], 6
0x180018b7a  jmp     short loc_180018BE7
0x180018b7c  sub     ecx, 7
0x180018b7f  jz      short loc_180018BC3
0x180018b81  sub     ecx, 1
0x180018b84  jz      short loc_180018BB6
0x180018b86  sub     ecx, 1
0x180018b89  jz      short loc_180018BA9
0x180018b8b  cmp     ecx, 1
0x180018b8e  jz      short loc_180018B97
0x180018b90  mov     eax, 80004005h
0x180018b95  jmp     short loc_180018BF1
0x180018b97  mov     r8, [rsp+28h+arg_20]; unsigned __int16 *
0x180018b9c  mov     rdx, rdi; struct _iistype *
0x180018b9f  mov     rcx, rbx; struct tagVARIANT *
0x180018ba2  call    ?VarTypeToIISTypeCopyIISSynIdNTACL@@YAJPEAUtagVARIANT@@PEAU_iistype@@PEBG@Z; VarTypeToIISTypeCopyIISSynIdNTACL(tagVARIANT *,_iistype *,ushort const *)
0x180018ba7  jmp     short loc_180018BF1
0x180018ba9  mov     rdx, rdi; struct _iistype *
0x180018bac  mov     rcx, rbx; struct tagVARIANT *
0x180018baf  call    ?VarTypeToIISTypeCopyIISSynIdIPSECLIST@@YAJPEAUtagVARIANT@@PEAU_iistype@@@Z; VarTypeToIISTypeCopyIISSynIdIPSECLIST(tagVARIANT *,_iistype *)
0x180018bb4  jmp     short loc_180018BF1
0x180018bb6  mov     rdx, rdi; struct _iistype *
0x180018bb9  mov     rcx, rbx; struct tagVARIANT *
0x180018bbc  call    ?VarTypeToIISTypeCopyIISSynIdMIMEMAP@@YAJPEAUtagVARIANT@@PEAU_iistype@@@Z; VarTypeToIISTypeCopyIISSynIdMIMEMAP(tagVARIANT *,_iistype *)
0x180018bc1  jmp     short loc_180018BF1
0x180018bc3  mov     r9d, 0Bh; vt
0x180018bc9  xor     r8d, r8d; wFlags
0x180018bcc  mov     rcx, rbx; pvargDest
0x180018bcf  call    cs:__imp_VariantChangeType
0x180018bd5  xor     ecx, ecx
0x180018bd7  mov     edx, eax
0x180018bd9  test    eax, eax
0x180018bdb  js      loc_180018B3B
0x180018be1  mov     dword ptr [rdi], 7
0x180018be7  cmp     [rbx+8], cx
0x180018beb  setnz   cl
0x180018bee  mov     [rdi+8], ecx
0x180018bf1  mov     rbx, [rsp+28h+arg_0]
0x180018bf6  mov     rsi, [rsp+28h+arg_8]
0x180018bfb  add     rsp, 20h
0x180018bff  pop     rdi
0x180018c00  retn
```
