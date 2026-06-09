# POOMSortedAggregateDataSource::Initialize(IPOutlookApp3 *,tagSQLCESORTORDERSPEC *,IPOutlookAggregateCollection *)

- ea: `0x18001a6b4`
- end: `0x18001a900`
- name: `?Initialize@POOMSortedAggregateDataSource@@IEAAJPEAUIPOutlookApp3@@PEAUtagSQLCESORTORDERSPEC@@PEAUIPOutlookAggregateCollection@@@Z`
- size: `588`
- prototype: `__int64 __fastcall(POOMSortedAggregateDataSource *__hidden this, struct IPOutlookApp3 *, struct tagSQLCESORTORDERSPEC *, struct IPOutlookAggregateCollection *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a008`

## callees

- `0x18000133c`
- `0x180001348`
- `0x18000502c`
- `0x18000d180`
- `0x1800124a8`
- `0x180019d1c`
- `0x180019d54`
- `0x18001a6b4`
- `0x18001a908`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a6e6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001a6e6`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a82a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001a82a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a841`
- `OLEAUT32!__imp_SysFreeString` at `0x18001a841`

## pseudocode

```c
__int64 __fastcall POOMSortedAggregateDataSource::Initialize(
        POOMSortedAggregateDataSource *this,
        struct IPOutlookApp3 *a2,
        struct tagSQLCESORTORDERSPEC *a3,
        struct IPOutlookAggregateCollection *a4)
{
  unsigned int Instance; // ebx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned __int64 v11; // rsi
  __int64 v12; // rax
  bool v13; // cf
  unsigned __int64 v14; // rax
  unsigned __int64 *v15; // rax
  _QWORD *v16; // rbx
  _QWORD *v17; // rax
  void *v18; // rax
  void *v19; // rcx
  void *v20; // rbx
  __int16 v21; // cx
  unsigned int v22; // r14d
  __int64 v23; // rsi
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // rbx
  BSTR v27; // rax
  OLECHAR *v28; // rcx
  BSTR v29; // r15
  __int16 v30; // cx
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // r9
  OLECHAR *psz[2]; // [rsp+30h] [rbp-58h] BYREF
  _WORD v36[36]; // [rsp+40h] [rbp-48h] BYREF

  Instance = CoCreateInstance(
               &GUID_05058f23_20be_11d2_8f18_0000f87a4335,
               0,
               0x17u,
               &GUID_a65ccaeb_6558_4656_ad3d_eccc00d00f0d,
               (LPVOID *)this + 4);
  if ( (Instance & 0x80000000) != 0 )
  {
    v8 = 1;
    v9 = 139;
LABEL_3:
    Log_HREvent_5(Instance, v8, v7, v9);
    return Instance;
  }
  if ( a3 && *((_WORD *)a3 + 1) )
  {
    v11 = *((unsigned __int16 *)a3 + 1);
    v12 = 8 * v11;
    if ( !is_mul_ok(v11, 8u) )
      v12 = -1;
    v13 = __CFADD__(v12, 8);
    v14 = v12 + 8;
    if ( v13 )
      v14 = -1;
    v15 = (unsigned __int64 *)operator new[](v14);
    if ( v15 )
    {
      v16 = v15 + 1;
      *v15 = v11;
      `vector constructor iterator'(
        v15 + 1,
        8u,
        (unsigned int)v11,
        tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>);
    }
    else
    {
      v16 = 0;
    }
    v17 = (_QWORD *)*((_QWORD *)this + 5);
    if ( v16 == v17 )
    {
      v16 = (_QWORD *)*((_QWORD *)this + 5);
    }
    else
    {
      if ( v17 )
        tlx::_delete_array<tlx::auto_xxx<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),0>>(*((_QWORD *)this + 5));
      *((_QWORD *)this + 5) = v16;
    }
    if ( !v16 )
    {
      v8 = 0;
      Instance = -2147024882;
      v9 = 144;
      goto LABEL_3;
    }
    v18 = operator new[](saturated_mul(*((unsigned __int16 *)a3 + 1), 2u));
    v19 = (void *)*((_QWORD *)this + 6);
    v20 = v18;
    if ( v18 == v19 )
    {
      v20 = (void *)*((_QWORD *)this + 6);
    }
    else
    {
      if ( v19 )
        operator delete(v19);
      *((_QWORD *)this + 6) = v20;
    }
    if ( !v20 )
    {
      v8 = 0;
      Instance = -2147024882;
      v9 = 145;
      goto LABEL_3;
    }
    v21 = *((_WORD *)a3 + 1);
    psz[0] = v36;
    psz[1] = v36;
    v22 = 0;
    v36[0] = 0;
    if ( v21 )
    {
      while ( 1 )
      {
        v23 = v22;
        v24 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                psz,
                L"[0x%1x]",
                *((unsigned int *)a3 + v22 + 2));
        Instance = v24;
        if ( v24 < 0 )
          break;
        v26 = *((_QWORD *)this + 5);
        v27 = SysAllocString(psz[0]);
        v28 = *(OLECHAR **)(v26 + 8LL * v22);
        v29 = v27;
        if ( v27 != v28 )
        {
          if ( v28 )
            SysFreeString(v28);
          *(_QWORD *)(v26 + 8LL * v22) = v29;
        }
        if ( !*(_QWORD *)(*((_QWORD *)this + 5) + 8LL * v22) )
        {
          Instance = -2147024882;
          v32 = 0;
          v33 = 2147942414LL;
          v34 = 154;
          goto LABEL_37;
        }
        v30 = -((*((_DWORD *)a3 + v22++ + 18) & 1) != 0);
        *(_WORD *)(*((_QWORD *)this + 6) + 2 * v23) = v30;
        v31 = *((unsigned __int16 *)a3 + 1);
        if ( v22 >= v31 )
          goto LABEL_39;
      }
      v32 = 1;
      v34 = 150;
      v33 = (unsigned int)v24;
LABEL_37:
      Log_HREvent_5(v33, v32, v25, v34);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(psz);
      return Instance;
    }
    LOWORD(v31) = 0;
LABEL_39:
    *((_DWORD *)this + 14) = (unsigned __int16)v31;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(psz);
  }
  if ( *((_QWORD *)this + 3) )
    ATL::AtlComPtrAssign((struct IUnknown **)this + 3, 0);
  return 0;
}

```

## disassembly

```asm
0x18001a6b4  push    rbx
0x18001a6b6  push    rbp
0x18001a6b7  push    rsi
0x18001a6b8  push    rdi
0x18001a6b9  push    r12
0x18001a6bb  push    r14
0x18001a6bd  push    r15
0x18001a6bf  sub     rsp, 50h
0x18001a6c3  lea     rax, [rcx+20h]
0x18001a6c7  xor     edx, edx; pUnkOuter
0x18001a6c9  mov     rbp, r8
0x18001a6cc  mov     [rsp+88h+ppv], rax; ppv
0x18001a6d1  mov     rdi, rcx
0x18001a6d4  lea     r9, _GUID_a65ccaeb_6558_4656_ad3d_eccc00d00f0d; riid
0x18001a6db  lea     rcx, _GUID_05058f23_20be_11d2_8f18_0000f87a4335; rclsid
0x18001a6e2  lea     r8d, [rdx+17h]; dwClsContext
0x18001a6e6  call    cs:__imp_CoCreateInstance
0x18001a6ec  xor     r12d, r12d
0x18001a6ef  mov     ebx, eax
0x18001a6f1  test    eax, eax
0x18001a6f3  jns     short loc_18001A70E
0x18001a6f5  lea     edx, [r12+1]
0x18001a6fa  mov     r9d, 8Bh
0x18001a700  mov     ecx, ebx
0x18001a702  call    Log_HREvent_5
0x18001a707  mov     eax, ebx
0x18001a709  jmp     loc_18001A8CD
0x18001a70e  test    rbp, rbp
0x18001a711  jz      loc_18001A8BB
0x18001a717  cmp     [rbp+2], r12w
0x18001a71c  jz      loc_18001A8BB
0x18001a722  movzx   esi, word ptr [rbp+2]
0x18001a726  mov     r14d, 8
0x18001a72c  mov     eax, r14d
0x18001a72f  mul     rsi
0x18001a732  lea     r15, [r14-9]
0x18001a736  cmovb   rax, r15
0x18001a73a  add     rax, r14
0x18001a73d  cmovb   rax, r15
0x18001a741  mov     rcx, rax; unsigned __int64
0x18001a744  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a749  test    rax, rax
0x18001a74c  jz      short loc_18001A76C
0x18001a74e  lea     rbx, [rax+8]
0x18001a752  mov     [rax], rsi
0x18001a755  mov     rcx, rbx; void *
0x18001a758  lea     r9, ??0?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@QEAA@XZ; void *(*)(void *)
0x18001a75f  mov     r8d, esi; unsigned __int64
0x18001a762  mov     edx, r14d; unsigned __int64
0x18001a765  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18001a76a  jmp     short loc_18001A76F
0x18001a76c  mov     rbx, r12
0x18001a76f  mov     rax, [rdi+28h]
0x18001a773  cmp     rbx, rax
0x18001a776  jz      short loc_18001A78B
0x18001a778  test    rax, rax
0x18001a77b  jz      short loc_18001A785
0x18001a77d  mov     rcx, rax
0x18001a780  call    ??$_delete_array@V?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@tlx@@@tlx@@YAXPEAV?$auto_xxx@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@Z$0A@@0@@Z; tlx::_delete_array<tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0>>(tlx::auto_xxx<ushort *,void (*)(ushort *),&SysFreeString(ushort *),0> *)
0x18001a785  mov     [rdi+28h], rbx
0x18001a789  jmp     short loc_18001A78E
0x18001a78b  mov     rbx, rax
0x18001a78e  test    rbx, rbx
0x18001a791  jz      loc_18001A8EE
0x18001a797  movzx   ecx, word ptr [rbp+2]
0x18001a79b  mov     eax, 2
0x18001a7a0  mul     rcx
0x18001a7a3  cmovb   rax, r15
0x18001a7a7  mov     rcx, rax; unsigned __int64
0x18001a7aa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001a7af  mov     rcx, [rdi+30h]; Block
0x18001a7b3  mov     rbx, rax
0x18001a7b6  cmp     rax, rcx
0x18001a7b9  jz      short loc_18001A7CB
0x18001a7bb  test    rcx, rcx
0x18001a7be  jz      short loc_18001A7C5
0x18001a7c0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a7c5  mov     [rdi+30h], rbx
0x18001a7c9  jmp     short loc_18001A7CE
0x18001a7cb  mov     rbx, rcx
0x18001a7ce  test    rbx, rbx
0x18001a7d1  jz      loc_18001A8DC
0x18001a7d7  movzx   ecx, word ptr [rbp+2]
0x18001a7db  lea     rax, [rsp+88h+var_48]
0x18001a7e0  mov     [rsp+88h+psz], rax
0x18001a7e5  lea     rax, [rsp+88h+var_48]
0x18001a7ea  mov     [rsp+88h+var_50], rax
0x18001a7ef  mov     r14d, r12d
0x18001a7f2  mov     [rsp+88h+var_48], r12w
0x18001a7f8  cmp     r12w, cx
0x18001a7fc  jnb     loc_18001A8A8
0x18001a802  mov     esi, r14d
0x18001a805  lea     rdx, a0x1x; "[0x%1x]"
0x18001a80c  lea     rcx, [rsp+88h+psz]
0x18001a811  mov     r8d, [rbp+rsi*4+8]
0x18001a816  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x18001a81b  mov     ebx, eax
0x18001a81d  test    eax, eax
0x18001a81f  js      short loc_18001A887
0x18001a821  mov     rcx, [rsp+88h+psz]; psz
0x18001a826  mov     rbx, [rdi+28h]
0x18001a82a  call    cs:__imp_SysAllocString
0x18001a830  mov     rcx, [rbx+rsi*8]; bstrString
0x18001a834  mov     r15, rax
0x18001a837  cmp     rax, rcx
0x18001a83a  jz      short loc_18001A84B
0x18001a83c  test    rcx, rcx
0x18001a83f  jz      short loc_18001A847
0x18001a841  call    cs:__imp_SysFreeString
0x18001a847  mov     [rbx+rsi*8], r15
0x18001a84b  mov     rax, [rdi+28h]
0x18001a84f  cmp     [rax+rsi*8], r12
0x18001a853  jz      short loc_18001A876
0x18001a855  mov     eax, [rbp+rsi*4+48h]
0x18001a859  and     al, 1
0x18001a85b  neg     al
0x18001a85d  mov     rax, [rdi+30h]
0x18001a861  sbb     cx, cx
0x18001a864  inc     r14d
0x18001a867  mov     [rax+rsi*2], cx
0x18001a86b  movzx   eax, word ptr [rbp+2]
0x18001a86f  cmp     r14d, eax
0x18001a872  jb      short loc_18001A802
0x18001a874  jmp     short loc_18001A8AB
0x18001a876  mov     ebx, 8007000Eh
0x18001a87b  xor     edx, edx
0x18001a87d  mov     ecx, ebx
0x18001a87f  mov     r9d, 9Ah
0x18001a885  jmp     short loc_18001A894
0x18001a887  mov     edx, 1
0x18001a88c  mov     r9d, 96h
0x18001a892  mov     ecx, eax
0x18001a894  call    Log_HREvent_5
0x18001a899  lea     rcx, [rsp+88h+psz]
0x18001a89e  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001a8a3  jmp     loc_18001A707
0x18001a8a8  movzx   eax, cx
0x18001a8ab  movzx   eax, ax
0x18001a8ae  lea     rcx, [rsp+88h+psz]
0x18001a8b3  mov     [rdi+38h], eax
0x18001a8b6  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001a8bb  lea     rcx, [rdi+18h]; struct IUnknown **
0x18001a8bf  cmp     [rcx], r12
0x18001a8c2  jz      short loc_18001A8CB
0x18001a8c4  xor     edx, edx; struct IUnknown *
0x18001a8c6  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001a8cb  xor     eax, eax
0x18001a8cd  add     rsp, 50h
0x18001a8d1  pop     r15
0x18001a8d3  pop     r14
0x18001a8d5  pop     r12
0x18001a8d7  pop     rdi
0x18001a8d8  pop     rsi
0x18001a8d9  pop     rbp
0x18001a8da  pop     rbx
0x18001a8db  retn
0x18001a8dc  xor     edx, edx
0x18001a8de  mov     ebx, 8007000Eh
0x18001a8e3  mov     r9d, 91h
0x18001a8e9  jmp     loc_18001A700
0x18001a8ee  xor     edx, edx
0x18001a8f0  mov     ebx, 8007000Eh
0x18001a8f5  mov     r9d, 90h
0x18001a8fb  jmp     loc_18001A700
```
