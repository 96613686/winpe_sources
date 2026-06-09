# CInkStorage::AppendMetaData(IStream *,tagVARIANT *,tagVARIANT *)

- ea: `0x180058c44`
- end: `0x180058d33`
- name: `?AppendMetaData@CInkStorage@@QEAAJPEAUIStream@@PEAUtagVARIANT@@1@Z`
- size: `239`
- prototype: `int(CInkStorage *__hidden this, struct IStream *, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180034120`

## callees

- `0x18001332c`
- `0x180058c44`
- `0x180059504`
- `0x1800b356c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180058cc1`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180058cc1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180058c8d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180058c8d`

## pseudocode

```c
__int64 __fastcall CInkStorage::AppendMetaData(
        CInkStorage *this,
        struct IStream *a2,
        struct tagVARIANT *a3,
        struct tagVARIANT *a4)
{
  SAFEARRAY *parray; // rdi
  int UBound; // ebx
  __int64 v8; // rdx
  CInkStorage *v10; // rcx
  int v11; // [rsp+20h] [rbp-20h]
  void *ppvData; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int8 *v13; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  CInkStorage *plUbound; // [rsp+60h] [rbp+20h] BYREF
  unsigned int v16; // [rsp+70h] [rbp+30h] BYREF

  plUbound = this;
  parray = a3->parray;
  LODWORD(plUbound) = 0;
  ppvData = 0;
  v13 = 0;
  v16 = 0;
  UBound = SafeArrayAccessData(parray, &ppvData);
  if ( UBound < 0 )
  {
    v8 = 97;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\inkstorage.cpp",
      (const char *)(unsigned int)UBound,
      v11);
    return (unsigned int)UBound;
  }
  UBound = SafeArrayGetUBound(parray, 1u, (LONG *)&plUbound);
  if ( UBound < 0 )
  {
    v8 = 99;
    goto LABEL_3;
  }
  LODWORD(plUbound) = (_DWORD)plUbound + 1;
  UBound = SaveISFMetaData((const unsigned __int8 *)ppvData, (unsigned int)plUbound, a2, &v13, &v16);
  if ( UBound < 0 )
  {
    v8 = 103;
    goto LABEL_3;
  }
  UBound = CInkStorage::WriteDataToSafeArray(v10, v16, v13, a4);
  if ( UBound < 0 )
  {
    v8 = 104;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180058c44  mov     [rsp-18h+arg_8], rbx
0x180058c49  mov     [rsp-18h+arg_18], rsi
0x180058c4e  mov     [rsp-18h+plUbound], rcx
0x180058c53  push    rbp
0x180058c54  push    rdi
0x180058c55  push    r14
0x180058c57  mov     rbp, rsp
0x180058c5a  sub     rsp, 40h
0x180058c5e  mov     rdi, [r8+8]
0x180058c62  mov     r14, rdx
0x180058c65  mov     rcx, rdi; psa
0x180058c68  mov     dword ptr [rbp+plUbound], 0
0x180058c6f  lea     rdx, [rbp+ppvData]; ppvData
0x180058c73  mov     [rbp+ppvData], 0
0x180058c7b  mov     rsi, r9
0x180058c7e  mov     [rbp+var_8], 0
0x180058c86  mov     [rbp+arg_10], 0
0x180058c8d  call    cs:__imp_SafeArrayAccessData
0x180058c93  mov     ebx, eax
0x180058c95  test    eax, eax
0x180058c97  jns     short loc_180058CB5
0x180058c99  mov     edx, 61h ; 'a'; void *
0x180058c9e  mov     rcx, [rbp+18h]; this
0x180058ca2  lea     r8, aOnecoreuapWind_62; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180058ca9  mov     r9d, ebx; char *
0x180058cac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058cb1  mov     eax, ebx
0x180058cb3  jmp     short loc_180058D20
0x180058cb5  lea     r8, [rbp+plUbound]; plUbound
0x180058cb9  mov     edx, 1; nDim
0x180058cbe  mov     rcx, rdi; psa
0x180058cc1  call    cs:__imp_SafeArrayGetUBound
0x180058cc7  mov     ebx, eax
0x180058cc9  test    eax, eax
0x180058ccb  jns     short loc_180058CD4
0x180058ccd  mov     edx, 63h ; 'c'
0x180058cd2  jmp     short loc_180058C9E
0x180058cd4  mov     edx, dword ptr [rbp+plUbound]
0x180058cd7  lea     rax, [rbp+arg_10]
0x180058cdb  mov     rcx, [rbp+ppvData]; unsigned __int8 *
0x180058cdf  lea     r9, [rbp+var_8]; unsigned __int8 **
0x180058ce3  inc     edx; unsigned int
0x180058ce5  mov     qword ptr [rsp+40h+var_20], rax; unsigned int *
0x180058cea  mov     r8, r14; struct IStream *
0x180058ced  mov     dword ptr [rbp+plUbound], edx
0x180058cf0  call    ?SaveISFMetaData@@YAJPEBEKPEAUIStream@@PEAPEAEAEAK@Z; SaveISFMetaData(uchar const *,ulong,IStream *,uchar * *,ulong &)
0x180058cf5  mov     ebx, eax
0x180058cf7  test    eax, eax
0x180058cf9  jns     short loc_180058D02
0x180058cfb  mov     edx, 67h ; 'g'
0x180058d00  jmp     short loc_180058C9E
0x180058d02  mov     r8, [rbp+var_8]; unsigned __int8 *
0x180058d06  mov     r9, rsi; struct tagVARIANT *
0x180058d09  mov     edx, [rbp+arg_10]; unsigned int
0x180058d0c  call    ?WriteDataToSafeArray@CInkStorage@@QEAAJKPEAEPEAUtagVARIANT@@@Z; CInkStorage::WriteDataToSafeArray(ulong,uchar *,tagVARIANT *)
0x180058d11  mov     ebx, eax
0x180058d13  test    eax, eax
0x180058d15  jns     short loc_180058D1E
0x180058d17  mov     edx, 68h ; 'h'
0x180058d1c  jmp     short loc_180058C9E
0x180058d1e  xor     eax, eax
0x180058d20  mov     rbx, [rsp+40h+arg_8]
0x180058d25  mov     rsi, [rsp+40h+arg_18]
0x180058d2a  add     rsp, 40h
0x180058d2e  pop     r14
0x180058d30  pop     rdi
0x180058d31  pop     rbp
0x180058d32  retn
```
