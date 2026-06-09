# CIISGenObject::GetDataPaths(ushort *,long,tagVARIANT *)

- ea: `0x180005cd0`
- end: `0x180005e2e`
- name: `?GetDataPaths@CIISGenObject@@UEAAJPEAGJPEAUtagVARIANT@@@Z`
- size: `350`
- prototype: `int(CIISGenObject *__hidden this, unsigned __int16 *, int, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000474c`
- `0x180005cd0`
- `0x180012ffc`
- `0x180013b94`
- `0x180014270`
- `0x18001441c`
- `0x18001b444`
- `0x18001b4e4`

## import_xrefs

- `ACTIVEDS!__imp_FreeADsMem` at `0x180005df2`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180005df2`

## pseudocode

```c
__int64 __fastcall CIISGenObject::GetDataPaths(
        CIISGenObject *this,
        unsigned __int16 *a2,
        int a3,
        struct tagVARIANT *a4)
{
  unsigned int v4; // edi
  int VariantFromPathArray; // ebx
  int v10; // eax
  int DataPaths; // eax
  void *v12; // r14
  struct IMSAdminBaseW *v13; // rcx
  unsigned int v14; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+34h] [rbp-1Ch] BYREF
  unsigned int v16; // [rsp+38h] [rbp-18h] BYREF
  LPVOID pMem; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+88h] [rbp+38h] BYREF

  v4 = 0;
  v18 = 0;
  v15 = 0;
  v16 = 0;
  v14 = 0;
  pMem = 0;
  if ( !a2 || !a4 )
    return 2147500035LL;
  VariantFromPathArray = IIsSchema::LookupMetaID(*((IIsSchema **)this + 14), a2, &v18);
  if ( VariantFromPathArray >= 0 )
  {
    VariantFromPathArray = IIsSchema::LookupMDFlags(*((IIsSchema **)this + 14), v18, &v15, &v16);
    if ( VariantFromPathArray >= 0 )
    {
      if ( a3 )
      {
        if ( a3 != 1 )
          return 2147504136LL;
        if ( (v15 & 1) == 0 )
          return 2148321281LL;
      }
      VariantFromPathArray = CIISGenObject::CacheMetaDataPath((CIISGenObject *)((char *)this - 96));
      if ( VariantFromPathArray >= 0 )
      {
        v10 = OpenAdminBaseKey(
                (CIISGenObject *)((char *)this + 80),
                *((unsigned __int16 **)this + 5),
                *((unsigned __int16 **)this + 6),
                1u,
                (struct IMSAdminBaseW **)this + 13,
                &v14);
        v4 = v14;
        VariantFromPathArray = v10;
        if ( v10 >= 0 )
        {
          DataPaths = MetaBaseGetDataPaths(*((struct IMSAdminBaseW **)this + 13), v14, v18, (unsigned __int8 **)&pMem);
          v12 = pMem;
          VariantFromPathArray = DataPaths;
          if ( DataPaths >= 0 )
            VariantFromPathArray = MakeVariantFromPathArray(
                                     *((unsigned __int16 **)this - 9),
                                     (unsigned __int16 *)pMem,
                                     a4);
          if ( v12 )
            FreeADsMem(v12);
        }
      }
    }
  }
  v13 = (struct IMSAdminBaseW *)*((_QWORD *)this + 13);
  if ( v13 )
  {
    if ( v4 )
      CloseAdminBaseKey(v13, v4);
  }
  return (unsigned int)VariantFromPathArray;
}

```

## disassembly

```asm
0x180005cd0  mov     [rsp-28h+arg_0], rbx
0x180005cd5  mov     [rsp-28h+arg_10], rsi
0x180005cda  push    rbp
0x180005cdb  push    rdi
0x180005cdc  push    r13
0x180005cde  push    r14
0x180005ce0  push    r15
0x180005ce2  mov     rbp, rsp
0x180005ce5  sub     rsp, 50h
0x180005ce9  xor     edi, edi
0x180005ceb  mov     [rbp+arg_8], 0
0x180005cf2  mov     [rbp+var_1C], 0
0x180005cf9  mov     r15, r9
0x180005cfc  mov     [rbp+var_18], 0
0x180005d03  mov     r14d, r8d
0x180005d06  mov     [rbp+var_20], edi
0x180005d09  mov     rsi, rcx
0x180005d0c  mov     [rbp+pMem], rdi
0x180005d10  test    rdx, rdx
0x180005d13  jz      loc_180005E10
0x180005d19  test    r9, r9
0x180005d1c  jz      loc_180005E10
0x180005d22  mov     rcx, [rcx+70h]; this
0x180005d26  lea     r8, [rbp+arg_8]; unsigned int *
0x180005d2a  call    ?LookupMetaID@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::LookupMetaID(ushort const *,ulong *)
0x180005d2f  mov     ebx, eax
0x180005d31  test    eax, eax
0x180005d33  js      loc_180005DF8
0x180005d39  mov     edx, [rbp+arg_8]; unsigned int
0x180005d3c  lea     r9, [rbp+var_18]; unsigned int *
0x180005d40  mov     rcx, [rsi+70h]; this
0x180005d44  lea     r8, [rbp+var_1C]; unsigned int *
0x180005d48  call    ?LookupMDFlags@IIsSchema@@QEAAJKPEAK0@Z; IIsSchema::LookupMDFlags(ulong,ulong *,ulong *)
0x180005d4d  mov     ebx, eax
0x180005d4f  test    eax, eax
0x180005d51  js      loc_180005DF8
0x180005d57  test    r14d, r14d
0x180005d5a  jz      short loc_180005D7C
0x180005d5c  cmp     r14d, 1
0x180005d60  jz      short loc_180005D6C
0x180005d62  mov     eax, 80005008h
0x180005d67  jmp     loc_180005E15
0x180005d6c  test    byte ptr [rbp+var_1C], 1
0x180005d70  jnz     short loc_180005D7C
0x180005d72  mov     eax, 800CC801h
0x180005d77  jmp     loc_180005E15
0x180005d7c  lea     rcx, [rsi-60h]; this
0x180005d80  call    ?CacheMetaDataPath@CIISGenObject@@QEAAJXZ; CIISGenObject::CacheMetaDataPath(void)
0x180005d85  mov     ebx, eax
0x180005d87  test    eax, eax
0x180005d89  js      short loc_180005DF8
0x180005d8b  mov     r8, [rsi+30h]; unsigned __int16 *
0x180005d8f  lea     rax, [rbp+var_20]
0x180005d93  mov     rdx, [rsi+28h]; unsigned __int16 *
0x180005d97  lea     r14, [rsi+68h]
0x180005d9b  mov     [rsp+50h+var_28], rax; unsigned int *
0x180005da0  lea     rcx, [rsi+50h]; this
0x180005da4  mov     r9d, 1; unsigned int
0x180005daa  mov     [rsp+50h+var_30], r14; struct IMSAdminBaseW **
0x180005daf  call    ?OpenAdminBaseKey@@YAJAEAVCCredentials@@PEAG1KPEAPEAUIMSAdminBaseW@@PEAK@Z; OpenAdminBaseKey(CCredentials &,ushort *,ushort *,ulong,IMSAdminBaseW * *,ulong *)
0x180005db4  mov     edi, [rbp+var_20]
0x180005db7  mov     ebx, eax
0x180005db9  test    eax, eax
0x180005dbb  js      short loc_180005DF8
0x180005dbd  mov     r8d, [rbp+arg_8]; unsigned int
0x180005dc1  lea     r9, [rbp+pMem]; unsigned __int8 **
0x180005dc5  mov     rcx, [r14]; struct IMSAdminBaseW *
0x180005dc8  mov     edx, edi; unsigned int
0x180005dca  call    ?MetaBaseGetDataPaths@@YAJPEAUIMSAdminBaseW@@KKPEAPEAE@Z; MetaBaseGetDataPaths(IMSAdminBaseW *,ulong,ulong,uchar * *)
0x180005dcf  mov     r14, [rbp+pMem]
0x180005dd3  mov     ebx, eax
0x180005dd5  test    eax, eax
0x180005dd7  js      short loc_180005DEA
0x180005dd9  mov     rcx, [rsi-48h]; unsigned __int16 *
0x180005ddd  mov     r8, r15; struct tagVARIANT *
0x180005de0  mov     rdx, r14; unsigned __int16 *
0x180005de3  call    ?MakeVariantFromPathArray@@YAJPEAG0PEAUtagVARIANT@@@Z; MakeVariantFromPathArray(ushort *,ushort *,tagVARIANT *)
0x180005de8  mov     ebx, eax
0x180005dea  test    r14, r14
0x180005ded  jz      short loc_180005DF8
0x180005def  mov     rcx, r14; pMem
0x180005df2  call    cs:__imp_FreeADsMem
0x180005df8  mov     rcx, [rsi+68h]; struct IMSAdminBaseW *
0x180005dfc  test    rcx, rcx
0x180005dff  jz      short loc_180005E0C
0x180005e01  test    edi, edi
0x180005e03  jz      short loc_180005E0C
0x180005e05  mov     edx, edi; unsigned int
0x180005e07  call    ?CloseAdminBaseKey@@YAXPEAUIMSAdminBaseW@@K@Z; CloseAdminBaseKey(IMSAdminBaseW *,ulong)
0x180005e0c  mov     eax, ebx
0x180005e0e  jmp     short loc_180005E15
0x180005e10  mov     eax, 80004003h
0x180005e15  lea     r11, [rsp+50h+var_s0]
0x180005e1a  mov     rbx, [r11+30h]
0x180005e1e  mov     rsi, [r11+40h]
0x180005e22  mov     rsp, r11
0x180005e25  pop     r15
0x180005e27  pop     r14
0x180005e29  pop     r13
0x180005e2b  pop     rdi
0x180005e2c  pop     rbp
0x180005e2d  retn
```
