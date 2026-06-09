# CADTGRowset::arInit(IStream *)

- ea: `0x18000f2f8`
- end: `0x18000f74f`
- name: `?arInit@CADTGRowset@@QEAAJPEAUIStream@@@Z`
- size: `1111`
- prototype: `__int64 __fastcall(CADTGRowset *__hidden this, struct IStream *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000bf00`
- `0x18000e5ec`

## callees

- `0x180001d94`
- `0x1800027c0`
- `0x18000e5ec`
- `0x18000f2f8`
- `0x18001a6c8`
- `0x18002010c`
- `0x18002058c`
- `0x18002cd54`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x18000f329`
- `KERNEL32!GetSystemInfo` at `0x18000f329`
- `ole32!CoTaskMemAlloc` at `0x18000f44f`
- `ole32!CoTaskMemAlloc` at `0x18000f44f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CADTGRowset::arInit(CADTGRowset *this, struct IStream *a2)
{
  unsigned int v4; // r14d
  unsigned __int8 *v5; // rax
  unsigned __int8 *v6; // rbx
  int MetaData; // ebx
  DBID *v8; // rax
  int v9; // ebx
  unsigned int v11; // [rsp+30h] [rbp-68h] BYREF
  struct _SYSTEM_INFO v12[2]; // [rsp+38h] [rbp-60h] BYREF

  v4 = 0;
  memset(v12, 0, 48);
  if ( !g_dwPageSize )
  {
    GetSystemInfo(v12);
    g_dwPageSize = v12[0].dwPageSize;
  }
  try
  {
    if ( !*((_DWORD *)this + 172) )
    {
      *((_DWORD *)this + 150) = 1;
      if ( !a2 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800488D8[0] )
            bidTraceW(off_1800481C8[0], 146432, off_1800488D8[0], 2147942487LL, 143);
        }
        ThrowHR(-2147024809);
      }
      v5 = MMMAlloc(0x18u, (unsigned int)a2);
      v6 = v5;
      if ( v5 )
      {
        *(_QWORD *)v5 = a2;
        ((void (__fastcall *)(struct IStream *))a2->lpVtbl->AddRef)(a2);
        v6[8] = 0;
        *((_DWORD *)v6 + 3) = 0;
        *((_DWORD *)v6 + 4) = 1;
      }
      else
      {
        v6 = 0;
      }
      *((_QWORD *)this + 68) = v6;
      OnNullThrowOOM(v6);
    }
    CRowset::CheckThreadModel(this, **((struct IUnknown ***)this + 68));
    MetaData = CADTGRowset::arGetMetaData(this);
    if ( MetaData < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1800488D0[0] )
        bidTraceW(off_1800481C8[0], 153600, off_1800488D0[0], (unsigned int)MetaData, 150);
      ThrowHR(MetaData);
    }
    v8 = (DBID *)CoTaskMemAlloc(0x2A0u);
    if ( !v8 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1800488C8[0] )
        bidTraceW(off_1800481C8[0], 157696, off_1800488C8[0], 2147942414LL, 154);
      ThrowHR(-2147024882);
    }
    *v8 = DBCOLUMN_BASECOLUMNNAME;
    v8[1] = DBCOLUMN_BASETABLENAME;
    v8[2] = DBCOLUMN_COLLATINGSEQUENCE;
    v8[3] = DBCOLUMN_COMPUTEMODE;
    v8[4] = DBCOLUMN_DEFAULTVALUE;
    v8[5] = DBCOLUMN_DOMAINNAME;
    v8[6] = DBCOLUMN_HASDEFAULT;
    v8[7] = DBCOLUMN_ISAUTOINCREMENT;
    v8[8] = DBCOLUMN_ISCASESENSITIVE;
    v8[9] = DBCOLUMN_ISSEARCHABLE;
    v8[10] = DBCOLUMN_ISUNIQUE;
    v8[11] = DBCOLUMN_BASECATALOGNAME;
    v8[12] = DBCOLUMN_BASESCHEMANAME;
    v8[13] = DBCOLUMN_DOMAINCATALOG;
    v8[14] = DBCOLUMN_DOMAINSCHEMA;
    v8[15] = DBCOLUMN_DATETIMEPRECISION;
    v8[16] = DBCOLUMN_OCTETLENGTH;
    v8[17] = DBCOLUMN_CLSID;
    v8[18].uGuid = (union tagDBID::$8A6F84EEDBA9444E5F3B3798E7B3D46D)xmmword_1800375C0;
    *(_OWORD *)&v8[18].eKind = xmmword_1800375D0;
    v8[19].uGuid = (union tagDBID::$8A6F84EEDBA9444E5F3B3798E7B3D46D)xmmword_1800375A0;
    *(_OWORD *)&v8[19].eKind = xmmword_1800375B0;
    v8[20].uGuid = (union tagDBID::$8A6F84EEDBA9444E5F3B3798E7B3D46D)xmmword_180037580;
    *(_OWORD *)&v8[20].eKind = xmmword_180037590;
    *((_DWORD *)this + 92) = 21;
    *((_QWORD *)this + 47) = v8;
    v9 = CRowset::Init(this);
    if ( v9 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1800488C0[0] )
        bidTraceW(off_1800481C8[0], 187392, off_1800488C0[0], (unsigned int)v9, 183);
      ThrowHR(v9);
    }
  }
  catch ( long v11 )
  {
    return v11;
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
  return v4;
}

```

## disassembly

```asm
0x18000f2f8  mov     rax, rsp
0x18000f2fb  push    rbx
0x18000f2fc  push    rsi
0x18000f2fd  push    rdi
0x18000f2fe  push    r14
0x18000f300  sub     rsp, 78h
0x18000f304  mov     rsi, rdx
0x18000f307  mov     rdi, rcx
0x18000f30a  xor     r14d, r14d
0x18000f30d  xorps   xmm0, xmm0
0x18000f310  movups  xmmword ptr [rax-60h], xmm0
0x18000f314  movups  xmmword ptr [rax-50h], xmm0
0x18000f318  movups  xmmword ptr [rax-40h], xmm0
0x18000f31c  cmp     cs:?g_dwPageSize@@3KA, r14d; ulong g_dwPageSize
0x18000f323  jnz     short loc_18000F339
0x18000f325  lea     rcx, [rax-60h]; lpSystemInfo
0x18000f329  call    cs:__imp_GetSystemInfo
0x18000f32f  mov     eax, [rsp+98h+var_5C]
0x18000f333  mov     cs:?g_dwPageSize@@3KA, eax; ulong g_dwPageSize
0x18000f339  cmp     dword ptr [rdi+2B0h], 0
0x18000f340  jnz     loc_18000F3EB
0x18000f346  mov     dword ptr [rdi+258h], 1
0x18000f350  test    rsi, rsi
0x18000f353  jnz     short loc_18000F39A
0x18000f355  test    byte ptr cs:_bidGblFlags, 2
0x18000f35c  jz      short loc_18000F390
0x18000f35e  mov     rax, cs:off_1800488D8; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f365  test    rax, rax
0x18000f368  jz      short loc_18000F390
0x18000f36a  mov     [rsp+98h+var_78], 8Fh
0x18000f372  mov     r9d, 80070057h
0x18000f378  mov     r8, cs:off_1800488D8; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f37f  mov     edx, 23C00h
0x18000f384  mov     rcx, cs:off_1800481C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000f38b  call    _bidTraceW
0x18000f390  mov     ecx, 80070057h; int
0x18000f395  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000f39a  mov     ecx, 18h; unsigned int
0x18000f39f  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000f3a4  mov     rbx, rax
0x18000f3a7  mov     [rsp+98h+arg_0], rax
0x18000f3af  test    rax, rax
0x18000f3b2  jz      short loc_18000F3DA
0x18000f3b4  mov     [rax], rsi
0x18000f3b7  mov     rax, [rsi]
0x18000f3ba  mov     rcx, rsi
0x18000f3bd  mov     rax, [rax+8]
0x18000f3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3c6  mov     byte ptr [rbx+8], 0
0x18000f3ca  mov     dword ptr [rbx+0Ch], 0
0x18000f3d1  mov     dword ptr [rbx+10h], 1
0x18000f3d8  jmp     short loc_18000F3DC
0x18000f3da  xor     ebx, ebx
0x18000f3dc  mov     [rdi+220h], rbx
0x18000f3e3  mov     rcx, rbx; void *
0x18000f3e6  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18000f3eb  mov     rdx, [rdi+220h]
0x18000f3f2  mov     rdx, [rdx]; struct IUnknown *
0x18000f3f5  mov     rcx, rdi; this
0x18000f3f8  call    ?CheckThreadModel@CRowset@@QEAAXPEAUIUnknown@@@Z; CRowset::CheckThreadModel(IUnknown *)
0x18000f3fd  mov     rcx, rdi; this
0x18000f400  call    ?arGetMetaData@CADTGRowset@@AEAAJXZ; CADTGRowset::arGetMetaData(void)
0x18000f405  mov     ebx, eax
0x18000f407  test    eax, eax
0x18000f409  jns     short loc_18000F44A
0x18000f40b  test    byte ptr cs:_bidGblFlags, 2
0x18000f412  jz      short loc_18000F443
0x18000f414  mov     rax, cs:off_1800488D0; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f41b  test    rax, rax
0x18000f41e  jz      short loc_18000F443
0x18000f420  mov     [rsp+98h+var_78], 96h
0x18000f428  mov     r9d, ebx
0x18000f42b  mov     r8, cs:off_1800488D0; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f432  mov     edx, 25800h
0x18000f437  mov     rcx, cs:off_1800481C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000f43e  call    _bidTraceW
0x18000f443  mov     ecx, ebx; int
0x18000f445  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000f44a  mov     ecx, 2A0h; cb
0x18000f44f  call    cs:__imp_CoTaskMemAlloc
0x18000f455  test    rax, rax
0x18000f458  jnz     short loc_18000F49F
0x18000f45a  test    byte ptr cs:_bidGblFlags, 2
0x18000f461  jz      short loc_18000F495
0x18000f463  mov     rax, cs:off_1800488C8; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f46a  test    rax, rax
0x18000f46d  jz      short loc_18000F495
0x18000f46f  mov     [rsp+98h+var_78], 9Ah
0x18000f477  mov     r9d, 8007000Eh
0x18000f47d  mov     r8, cs:off_1800488C8; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f484  mov     edx, 26800h
0x18000f489  mov     rcx, cs:off_1800481C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000f490  call    _bidTraceW
0x18000f495  mov     ecx, 8007000Eh; int
0x18000f49a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000f49f  movups  xmm0, xmmword ptr cs:DBCOLUMN_BASECOLUMNNAME.uGuid
0x18000f4a6  movups  xmmword ptr [rax], xmm0
0x18000f4a9  movups  xmm1, xmmword ptr cs:DBCOLUMN_BASECOLUMNNAME.eKind
0x18000f4b0  movups  xmmword ptr [rax+10h], xmm1
0x18000f4b4  movups  xmm0, xmmword ptr cs:DBCOLUMN_BASETABLENAME.uGuid
0x18000f4bb  movups  xmmword ptr [rax+20h], xmm0
0x18000f4bf  movups  xmm1, xmmword ptr cs:DBCOLUMN_BASETABLENAME.eKind
0x18000f4c6  movups  xmmword ptr [rax+30h], xmm1
0x18000f4ca  movups  xmm0, xmmword ptr cs:DBCOLUMN_COLLATINGSEQUENCE.uGuid
0x18000f4d1  movups  xmmword ptr [rax+40h], xmm0
0x18000f4d5  movups  xmm1, xmmword ptr cs:DBCOLUMN_COLLATINGSEQUENCE.eKind
0x18000f4dc  movups  xmmword ptr [rax+50h], xmm1
0x18000f4e0  movups  xmm0, xmmword ptr cs:DBCOLUMN_COMPUTEMODE.uGuid
0x18000f4e7  movups  xmmword ptr [rax+60h], xmm0
0x18000f4eb  movups  xmm1, xmmword ptr cs:DBCOLUMN_COMPUTEMODE.eKind
0x18000f4f2  movups  xmmword ptr [rax+70h], xmm1
0x18000f4f6  movups  xmm0, xmmword ptr cs:DBCOLUMN_DEFAULTVALUE.uGuid
0x18000f4fd  movups  xmmword ptr [rax+80h], xmm0
0x18000f504  movups  xmm1, xmmword ptr cs:DBCOLUMN_DEFAULTVALUE.eKind
0x18000f50b  movups  xmmword ptr [rax+90h], xmm1
0x18000f512  movups  xmm0, xmmword ptr cs:DBCOLUMN_DOMAINNAME.uGuid
0x18000f519  movups  xmmword ptr [rax+0A0h], xmm0
0x18000f520  movups  xmm1, xmmword ptr cs:DBCOLUMN_DOMAINNAME.eKind
0x18000f527  movups  xmmword ptr [rax+0B0h], xmm1
0x18000f52e  movups  xmm0, xmmword ptr cs:DBCOLUMN_HASDEFAULT.uGuid
0x18000f535  movups  xmmword ptr [rax+0C0h], xmm0
0x18000f53c  movups  xmm1, xmmword ptr cs:DBCOLUMN_HASDEFAULT.eKind
0x18000f543  movups  xmmword ptr [rax+0D0h], xmm1
0x18000f54a  movups  xmm0, xmmword ptr cs:DBCOLUMN_ISAUTOINCREMENT.uGuid
0x18000f551  movups  xmmword ptr [rax+0E0h], xmm0
0x18000f558  movups  xmm1, xmmword ptr cs:DBCOLUMN_ISAUTOINCREMENT.eKind
0x18000f55f  movups  xmmword ptr [rax+0F0h], xmm1
0x18000f566  movups  xmm0, xmmword ptr cs:DBCOLUMN_ISCASESENSITIVE.uGuid
0x18000f56d  movups  xmmword ptr [rax+100h], xmm0
0x18000f574  movups  xmm1, xmmword ptr cs:DBCOLUMN_ISCASESENSITIVE.eKind
0x18000f57b  movups  xmmword ptr [rax+110h], xmm1
0x18000f582  movups  xmm0, xmmword ptr cs:DBCOLUMN_ISSEARCHABLE.uGuid
0x18000f589  movups  xmmword ptr [rax+120h], xmm0
0x18000f590  movups  xmm1, xmmword ptr cs:DBCOLUMN_ISSEARCHABLE.eKind
0x18000f597  movups  xmmword ptr [rax+130h], xmm1
0x18000f59e  movups  xmm0, xmmword ptr cs:DBCOLUMN_ISUNIQUE.uGuid
0x18000f5a5  movups  xmmword ptr [rax+140h], xmm0
0x18000f5ac  movups  xmm1, xmmword ptr cs:DBCOLUMN_ISUNIQUE.eKind
0x18000f5b3  movups  xmmword ptr [rax+150h], xmm1
0x18000f5ba  movups  xmm0, xmmword ptr cs:DBCOLUMN_BASECATALOGNAME.uGuid
0x18000f5c1  movups  xmmword ptr [rax+160h], xmm0
0x18000f5c8  movups  xmm1, xmmword ptr cs:DBCOLUMN_BASECATALOGNAME.eKind
0x18000f5cf  movups  xmmword ptr [rax+170h], xmm1
0x18000f5d6  movups  xmm0, xmmword ptr cs:DBCOLUMN_BASESCHEMANAME.uGuid
0x18000f5dd  movups  xmmword ptr [rax+180h], xmm0
0x18000f5e4  movups  xmm1, xmmword ptr cs:DBCOLUMN_BASESCHEMANAME.eKind
0x18000f5eb  movups  xmmword ptr [rax+190h], xmm1
0x18000f5f2  movups  xmm0, xmmword ptr cs:DBCOLUMN_DOMAINCATALOG.uGuid
0x18000f5f9  movups  xmmword ptr [rax+1A0h], xmm0
0x18000f600  movups  xmm1, xmmword ptr cs:DBCOLUMN_DOMAINCATALOG.eKind
0x18000f607  movups  xmmword ptr [rax+1B0h], xmm1
0x18000f60e  movups  xmm0, xmmword ptr cs:DBCOLUMN_DOMAINSCHEMA.uGuid
0x18000f615  movups  xmmword ptr [rax+1C0h], xmm0
0x18000f61c  movups  xmm1, xmmword ptr cs:DBCOLUMN_DOMAINSCHEMA.eKind
0x18000f623  movups  xmmword ptr [rax+1D0h], xmm1
0x18000f62a  movups  xmm0, xmmword ptr cs:DBCOLUMN_DATETIMEPRECISION.uGuid
0x18000f631  movups  xmmword ptr [rax+1E0h], xmm0
0x18000f638  movups  xmm1, xmmword ptr cs:DBCOLUMN_DATETIMEPRECISION.eKind
0x18000f63f  movups  xmmword ptr [rax+1F0h], xmm1
0x18000f646  movups  xmm0, xmmword ptr cs:DBCOLUMN_OCTETLENGTH.uGuid
0x18000f64d  movups  xmmword ptr [rax+200h], xmm0
0x18000f654  movups  xmm1, xmmword ptr cs:DBCOLUMN_OCTETLENGTH.eKind
0x18000f65b  movups  xmmword ptr [rax+210h], xmm1
0x18000f662  movups  xmm0, xmmword ptr cs:DBCOLUMN_CLSID.uGuid
0x18000f669  movups  xmmword ptr [rax+220h], xmm0
0x18000f670  movups  xmm1, xmmword ptr cs:DBCOLUMN_CLSID.eKind
0x18000f677  movups  xmmword ptr [rax+230h], xmm1
0x18000f67e  movups  xmm0, cs:xmmword_1800375C0
0x18000f685  movups  xmmword ptr [rax+240h], xmm0
0x18000f68c  movups  xmm1, cs:xmmword_1800375D0
0x18000f693  movups  xmmword ptr [rax+250h], xmm1
0x18000f69a  movups  xmm0, cs:xmmword_1800375A0
0x18000f6a1  movups  xmmword ptr [rax+260h], xmm0
0x18000f6a8  movups  xmm1, cs:xmmword_1800375B0
0x18000f6af  movups  xmmword ptr [rax+270h], xmm1
0x18000f6b6  movups  xmm0, cs:xmmword_180037580
0x18000f6bd  movups  xmmword ptr [rax+280h], xmm0
0x18000f6c4  movups  xmm1, cs:xmmword_180037590
0x18000f6cb  movups  xmmword ptr [rax+290h], xmm1
0x18000f6d2  mov     dword ptr [rdi+170h], 15h
0x18000f6dc  mov     [rdi+178h], rax
0x18000f6e3  mov     rcx, rdi; this
0x18000f6e6  call    ?Init@CRowset@@QEAAJXZ; CRowset::Init(void)
0x18000f6eb  mov     ebx, eax
0x18000f6ed  test    eax, eax
0x18000f6ef  jns     short loc_18000F731
0x18000f6f1  test    byte ptr cs:_bidGblFlags, 2
0x18000f6f8  jz      short loc_18000F729
0x18000f6fa  mov     rax, cs:off_1800488C0; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f701  test    rax, rax
0x18000f704  jz      short loc_18000F729
0x18000f706  mov     [rsp+98h+var_78], 0B7h
0x18000f70e  mov     r9d, ebx
0x18000f711  mov     r8, cs:off_1800488C0; "<CADTGRowset::arInit|ADO|ERR>  HRESULT:"...
0x18000f718  mov     edx, 2DC00h
0x18000f71d  mov     rcx, cs:off_1800481C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000f724  call    _bidTraceW
0x18000f729  mov     ecx, ebx; int
0x18000f72b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000f731  jmp     short loc_18000F73B
0x18000f733  mov     r14d, dword ptr [rsp+98h+arg_0]
0x18000f73b  mov     eax, r14d
0x18000f73e  jmp     short loc_18000F745
0x18000f740  mov     eax, 80004005h
0x18000f745  add     rsp, 78h
0x18000f749  pop     r14
0x18000f74b  pop     rdi
0x18000f74c  pop     rsi
0x18000f74d  pop     rbx
0x18000f74e  retn
```
