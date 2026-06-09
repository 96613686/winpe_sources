# IISTypeToVarTypeCopy(IIsSchema *,ushort *,_iistype *,tagVARIANT *,int,ushort const *)

- ea: `0x180018518`
- end: `0x1800186c8`
- name: `?IISTypeToVarTypeCopy@@YAJPEAVIIsSchema@@PEAGPEAU_iistype@@PEAUtagVARIANT@@HPEBG@Z`
- size: `432`
- prototype: `int(struct IIsSchema *, unsigned __int16 *, struct _iistype *, struct tagVARIANT *, int, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180002ed0`
- `0x180005a90`
- `0x180010104`
- `0x1800186d0`

## callees

- `0x18000de1c`
- `0x18000de94`
- `0x18000e490`
- `0x18000e7e0`
- `0x180012574`
- `0x180018518`
- `0x18001883c`
- `0x1800189bc`
- `0x18001b3a8`
- `0x18001beb8`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall IISTypeToVarTypeCopy(
        struct IIsSchema *a1,
        unsigned __int16 *a2,
        struct _iistype *a3,
        struct tagVARIANT *a4,
        int a5,
        unsigned __int16 *a6)
{
  int v6; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  unsigned int v14; // ebx
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // r8d
  HRESULT IPSecurity; // r14d
  int MimeType; // ecx
  CMimeType *v22; // [rsp+50h] [rbp+30h] BYREF

  v6 = *(_DWORD *)a3;
  if ( *(_DWORD *)a3 <= 6u )
  {
    if ( v6 == 6 )
    {
      a4->vt = 11;
      a4->iVal = -(*((_DWORD *)a3 + 2) != 0);
    }
    else
    {
      v9 = v6 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( !v10 || (v11 = v10 - 1) == 0 || (v12 = v11 - 1) == 0 )
        {
          a4->vt = 8;
          return (unsigned int)ADsAllocString(*((_QWORD *)a3 + 1), &a4->decVal.Lo32);
        }
        if ( v12 == 1 )
          return (unsigned int)IISTypeToVarTypeCopyIISSynIdBinary(a3, a4, a5);
        return (unsigned int)-2147467259;
      }
      a4->vt = 3;
      a4->lVal = *((_DWORD *)a3 + 2);
    }
    return 0;
  }
  v15 = v6 - 7;
  if ( !v15 )
  {
    v14 = 0;
    LODWORD(v22) = 0;
    IIsSchema::LookupBitMask(a1, a2, (unsigned int *)&v22);
    a4->vt = 11;
    a4->iVal = -(((unsigned int)v22 & *((_DWORD *)a3 + 2)) != 0);
    return v14;
  }
  v16 = v15 - 1;
  if ( v16 )
  {
    v17 = v16 - 1;
    if ( v17 )
    {
      if ( v17 == 1 )
      {
        v18 = a5;
        a4->vt = 9;
        return (unsigned int)ConvertSecDescriptorToVariant(*((PSECURITY_DESCRIPTOR *)a3 + 2), a4, v18, a6);
      }
      return (unsigned int)-2147467259;
    }
    v22 = 0;
    IPSecurity = CIPSecurity::CreateIPSecurity(&IID_IISIPSecurity, (void **)&v22);
    if ( IPSecurity >= 0 )
    {
      IPSecurity = CIPSecurity::InitFromBinaryBlob(v22, *((unsigned __int8 **)a3 + 2), *((_DWORD *)a3 + 2));
      if ( IPSecurity >= 0 )
      {
        a4->llVal = (LONGLONG)v22;
        a4->vt = 9;
        if ( a5 )
        {
          IPSecurity = VariantToVariantArray(a4);
          (*(void (__fastcall **)(CMimeType *))(*(_QWORD *)v22 + 16LL))(v22);
        }
      }
    }
    return (unsigned int)IPSecurity;
  }
  else
  {
    v22 = 0;
    MimeType = CMimeType::CreateMimeType(&IID_IISMimeType, (void **)&v22);
    if ( MimeType >= 0 )
    {
      MimeType = CMimeType::InitFromIISString(v22, *((unsigned __int16 **)a3 + 1));
      a4->vt = 9;
      a4->llVal = (LONGLONG)v22;
    }
    return (unsigned int)MimeType;
  }
}

```

## disassembly

```asm
0x180018518  mov     [rsp-18h+arg_0], rbx
0x18001851d  mov     [rsp-18h+arg_8], rsi
0x180018522  push    rbp
0x180018523  push    rdi
0x180018524  push    r14
0x180018526  mov     rbp, rsp
0x180018529  sub     rsp, 20h
0x18001852d  mov     eax, [r8]
0x180018530  mov     rdi, r9
0x180018533  mov     rsi, r8
0x180018536  cmp     eax, 6
0x180018539  ja      short loc_1800185AC
0x18001853b  jz      short loc_180018596
0x18001853d  sub     eax, 1
0x180018540  jz      short loc_180018581
0x180018542  sub     eax, 1
0x180018545  jz      short loc_180018567
0x180018547  sub     eax, 1
0x18001854a  jz      short loc_180018567
0x18001854c  sub     eax, 1
0x18001854f  jz      short loc_180018567
0x180018551  cmp     eax, 1
0x180018554  jnz     short loc_1800185C8
0x180018556  mov     r8d, [rbp+arg_20]; int
0x18001855a  mov     rdx, r9; struct tagVARIANT *
0x18001855d  mov     rcx, rsi; struct _iistype *
0x180018560  call    ?IISTypeToVarTypeCopyIISSynIdBinary@@YAJPEAU_iistype@@PEAUtagVARIANT@@H@Z; IISTypeToVarTypeCopyIISSynIdBinary(_iistype *,tagVARIANT *,int)
0x180018565  jmp     short loc_18001857A
0x180018567  mov     word ptr [r9], 8
0x18001856d  lea     rdx, [r9+8]
0x180018571  mov     rcx, [r8+8]
0x180018575  call    ADsAllocString
0x18001857a  mov     ebx, eax
0x18001857c  jmp     loc_1800186B3
0x180018581  mov     word ptr [r9], 3
0x180018587  mov     eax, [r8+8]
0x18001858b  mov     [r9+8], eax
0x18001858f  xor     ebx, ebx
0x180018591  jmp     loc_1800186B3
0x180018596  mov     word ptr [r9], 0Bh
0x18001859c  mov     eax, [r8+8]
0x1800185a0  neg     eax
0x1800185a2  sbb     cx, cx
0x1800185a5  mov     [r9+8], cx
0x1800185aa  jmp     short loc_18001858F
0x1800185ac  sub     eax, 7
0x1800185af  jz      loc_180018691
0x1800185b5  sub     eax, 1
0x1800185b8  jz      loc_180018655
0x1800185be  sub     eax, 1
0x1800185c1  jz      short loc_1800185EE
0x1800185c3  cmp     eax, 1
0x1800185c6  jz      short loc_1800185D2
0x1800185c8  mov     ebx, 80004005h
0x1800185cd  jmp     loc_1800186B3
0x1800185d2  mov     r8d, [rbp+arg_20]; int
0x1800185d6  mov     rdx, rdi; pvarg
0x1800185d9  mov     word ptr [r9], 9
0x1800185df  mov     r9, [rbp+arg_28]; unsigned __int16 *
0x1800185e3  mov     rcx, [rsi+10h]; pSecurityDescriptor
0x1800185e7  call    ?ConvertSecDescriptorToVariant@@YAJPEAXPEAUtagVARIANT@@HPEBG@Z; ConvertSecDescriptorToVariant(void *,tagVARIANT *,int,ushort const *)
0x1800185ec  jmp     short loc_18001857A
0x1800185ee  xor     ebx, ebx
0x1800185f0  lea     rdx, [rbp+arg_10]; void **
0x1800185f4  lea     rcx, IID_IISIPSecurity; struct _GUID *
0x1800185fb  mov     [rbp+arg_10], rbx
0x1800185ff  call    ?CreateIPSecurity@CIPSecurity@@SAJAEBU_GUID@@PEAPEAX@Z; CIPSecurity::CreateIPSecurity(_GUID const &,void * *)
0x180018604  mov     r14d, eax
0x180018607  test    eax, eax
0x180018609  js      short loc_180018650
0x18001860b  mov     r8d, [rsi+8]; unsigned int
0x18001860f  mov     rdx, [rsi+10h]; unsigned __int8 *
0x180018613  mov     rcx, [rbp+arg_10]; this
0x180018617  call    ?InitFromBinaryBlob@CIPSecurity@@QEAAJPEAEK@Z; CIPSecurity::InitFromBinaryBlob(uchar *,ulong)
0x18001861c  mov     r14d, eax
0x18001861f  test    eax, eax
0x180018621  js      short loc_180018650
0x180018623  mov     rax, [rbp+arg_10]
0x180018627  mov     [rdi+8], rax
0x18001862b  mov     word ptr [rdi], 9
0x180018630  cmp     [rbp+arg_20], ebx
0x180018633  jz      short loc_180018650
0x180018635  mov     rcx, rdi; pv
0x180018638  call    ?VariantToVariantArray@@YAJPEAUtagVARIANT@@@Z; VariantToVariantArray(tagVARIANT *)
0x18001863d  mov     rcx, [rbp+arg_10]
0x180018641  mov     r14d, eax
0x180018644  mov     rax, [rcx]
0x180018647  mov     rax, [rax+10h]
0x18001864b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018650  mov     ebx, r14d
0x180018653  jmp     short loc_1800186B3
0x180018655  xor     ebx, ebx
0x180018657  lea     rdx, [rbp+arg_10]; void **
0x18001865b  lea     rcx, IID_IISMimeType; struct _GUID *
0x180018662  mov     [rbp+arg_10], rbx
0x180018666  call    ?CreateMimeType@CMimeType@@SAJAEBU_GUID@@PEAPEAX@Z; CMimeType::CreateMimeType(_GUID const &,void * *)
0x18001866b  mov     ecx, eax
0x18001866d  test    eax, eax
0x18001866f  js      short loc_18001868D
0x180018671  mov     rdx, [rsi+8]; unsigned __int16 *
0x180018675  mov     rcx, [rbp+arg_10]; this
0x180018679  call    ?InitFromIISString@CMimeType@@QEAAJPEAG@Z; CMimeType::InitFromIISString(ushort *)
0x18001867e  mov     ecx, eax; this
0x180018680  mov     word ptr [rdi], 9
0x180018685  mov     rax, [rbp+arg_10]
0x180018689  mov     [rdi+8], rax
0x18001868d  mov     ebx, ecx
0x18001868f  jmp     short loc_1800186B3
0x180018691  xor     ebx, ebx
0x180018693  lea     r8, [rbp+arg_10]; unsigned int *
0x180018697  mov     dword ptr [rbp+arg_10], ebx
0x18001869a  call    ?LookupBitMask@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::LookupBitMask(ushort const *,ulong *)
0x18001869f  mov     word ptr [rdi], 0Bh
0x1800186a4  mov     eax, [rsi+8]
0x1800186a7  and     eax, dword ptr [rbp+arg_10]
0x1800186aa  neg     eax
0x1800186ac  sbb     ax, ax
0x1800186af  mov     [rdi+8], ax
0x1800186b3  mov     rsi, [rsp+20h+arg_8]
0x1800186b8  mov     eax, ebx
0x1800186ba  mov     rbx, [rsp+20h+arg_0]
0x1800186bf  add     rsp, 20h
0x1800186c3  pop     r14
0x1800186c5  pop     rdi
0x1800186c6  pop     rbp
0x1800186c7  retn
```
