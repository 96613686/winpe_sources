# CPersistErrorCache::AddInternalError(long,ulong)

- ea: `0x180015b78`
- end: `0x180015f0c`
- name: `?AddInternalError@CPersistErrorCache@@QEAAXJK@Z`
- size: `916`
- prototype: `void __fastcall(CPersistErrorCache *__hidden this, int, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180015f14`
- `0x1800160ac`

## callees

- `0x180002650`
- `0x18000266c`
- `0x1800153fc`
- `0x180015b78`
- `0x18001616c`
- `0x180016564`
- `0x18001a6c8`
- `0x18002cd54`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180015ec3`
- `OLEAUT32!__imp_SysFreeString` at `0x180015ec3`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180015bcd`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x180015bcd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CPersistErrorCache::AddInternalError(CPersistErrorCache *this, unsigned int a2, unsigned int a3)
{
  OLECHAR *v6; // rbx
  OLECHAR *v7; // rcx
  HRESULT v8; // eax
  int v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  int v13; // edi
  unsigned __int16 *ErrorDescription; // rax
  int v15; // eax
  int v16; // edi
  __int64 ErrorDescriptionSDK; // rax
  int v18; // eax
  int v19; // edi
  unsigned __int16 *v20; // rax
  int v21; // eax
  int v22; // edi
  int v23; // eax
  int v24; // edi
  unsigned __int16 *v25; // [rsp+30h] [rbp-38h] BYREF
  struct IErrorInfo *v26; // [rsp+38h] [rbp-30h] BYREF
  __int64 v27; // [rsp+40h] [rbp-28h]
  _QWORD v28[4]; // [rsp+48h] [rbp-20h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+88h] [rbp+20h] BYREF

  pperrinfo = 0;
  v26 = 0;
  v28[0] = 0;
  v25 = 0;
  v6 = 0;
  v27 = 0;
  if ( a2 )
  {
    v8 = CreateErrorInfo(&pperrinfo);
    try
    {
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048A88[0] )
          bidTraceW(off_1800481E8[0], 397312, off_180048A88[0], (unsigned int)v8, 388);
        ThrowHR(v9);
      }
      v10 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, &GUID_NULL);
      v11 = v10;
      if ( v10 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048A80[0] )
          bidTraceW(off_1800481E8[0], 399360, off_180048A80[0], (unsigned int)v10, 390);
        ThrowHR(v11);
      }
      v12 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const wchar_t *))pperrinfo->lpVtbl->SetSource)(
              pperrinfo,
              L"Microsoft OLEDB Persistence Provider");
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048A78[0] )
          bidTraceW(off_1800481E8[0], 400384, off_180048A78[0], (unsigned int)v12, 391);
        ThrowHR(v13);
      }
      ErrorDescription = CPersistErrorCache::GetErrorDescription(this, a2, a3);
      v25 = ErrorDescription;
      if ( ErrorDescription )
      {
        v15 = ((__int64 (__fastcall *)(ICreateErrorInfo *, unsigned __int16 *))pperrinfo->lpVtbl->SetDescription)(
                pperrinfo,
                ErrorDescription);
        v16 = v15;
        if ( v15 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048A70[0] )
            bidTraceW(off_1800481E8[0], 404480, off_180048A70[0], (unsigned int)v15, 395);
          ThrowHR(v16);
        }
      }
      else
      {
        a3 = 136;
        ErrorDescriptionSDK = GetErrorDescriptionSDK(a2);
        v6 = (OLECHAR *)ErrorDescriptionSDK;
        v27 = ErrorDescriptionSDK;
        if ( ErrorDescriptionSDK )
        {
          v18 = ((__int64 (__fastcall *)(ICreateErrorInfo *, __int64))pperrinfo->lpVtbl->SetDescription)(
                  pperrinfo,
                  ErrorDescriptionSDK);
          v19 = v18;
          if ( v18 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180048A68[0] )
              bidTraceW(off_1800481E8[0], 412672, off_180048A68[0], (unsigned int)v18, 403);
            ThrowHR(v19);
          }
        }
        else
        {
          v20 = CPersistErrorCache::GetErrorDescription(this, a2, 0x88u);
          v25 = v20;
          if ( v20 )
          {
            v21 = ((__int64 (__fastcall *)(ICreateErrorInfo *, unsigned __int16 *))pperrinfo->lpVtbl->SetDescription)(
                    pperrinfo,
                    v20);
            v22 = v21;
            if ( v21 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180048A60[0] )
                bidTraceW(off_1800481E8[0], 418816, off_180048A60[0], (unsigned int)v21, 409);
              ThrowHR(v22);
            }
          }
        }
      }
      v23 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, struct IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
              pperrinfo,
              &IID_IErrorInfo,
              &v26);
      v24 = v23;
      if ( v23 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180048A58[0] )
          bidTraceW(off_1800481E8[0], 423936, off_180048A58[0], (unsigned int)v23, 414);
        ThrowHR(v24);
      }
      CPersistErrorCache::AddError(this, a2, a3, v26);
    }
    catch ( long )
    {
      v6 = (OLECHAR *)v27;
    }
    v7 = v6;
  }
  else
  {
    v7 = 0;
  }
  SysFreeString(v7);
  CAutoP<_GUID>::~CAutoP<_GUID>(&v25);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(v28);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v26);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&pperrinfo);
}

```

## disassembly

```asm
0x180015b78  mov     rax, rsp
0x180015b7b  mov     [rax+8], rbx
0x180015b7f  mov     [rax+10h], rsi
0x180015b83  push    rdi
0x180015b84  push    r14
0x180015b86  push    r15
0x180015b88  sub     rsp, 50h
0x180015b8c  mov     r14d, r8d
0x180015b8f  mov     esi, edx
0x180015b91  mov     r15, rcx
0x180015b94  mov     qword ptr [rax+20h], 0
0x180015b9c  mov     qword ptr [rax-30h], 0
0x180015ba4  mov     qword ptr [rax-20h], 0
0x180015bac  mov     qword ptr [rax-38h], 0
0x180015bb4  xor     ebx, ebx
0x180015bb6  mov     [rax-28h], rbx
0x180015bba  test    edx, edx
0x180015bbc  jnz     short loc_180015BC5
0x180015bbe  xor     ecx, ecx
0x180015bc0  jmp     loc_180015EC3
0x180015bc5  lea     rcx, [rsp+68h+pperrinfo]; pperrinfo
0x180015bcd  call    cs:__imp_CreateErrorInfo
0x180015bd3  mov     edi, eax
0x180015bd5  test    eax, eax
0x180015bd7  jns     short loc_180015C18
0x180015bd9  test    byte ptr cs:_bidGblFlags, 2
0x180015be0  jz      short loc_180015C11
0x180015be2  mov     rcx, cs:off_180048A88; "<CPersistErrorCache::AddInternalError|A"...
0x180015be9  test    rcx, rcx
0x180015bec  jz      short loc_180015C11
0x180015bee  mov     [rsp+68h+var_48], 184h
0x180015bf6  mov     r9d, eax
0x180015bf9  mov     r8, cs:off_180048A88; "<CPersistErrorCache::AddInternalError|A"...
0x180015c00  mov     edx, 61000h
0x180015c05  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015c0c  call    _bidTraceW
0x180015c11  mov     ecx, edi; int
0x180015c13  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015c18  mov     rcx, [rsp+68h+pperrinfo]
0x180015c20  mov     rax, [rcx]
0x180015c23  lea     rdx, GUID_NULL
0x180015c2a  mov     rax, [rax+18h]
0x180015c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c33  mov     edi, eax
0x180015c35  test    eax, eax
0x180015c37  jns     short loc_180015C78
0x180015c39  test    byte ptr cs:_bidGblFlags, 2
0x180015c40  jz      short loc_180015C71
0x180015c42  mov     rcx, cs:off_180048A80; "<CPersistErrorCache::AddInternalError|A"...
0x180015c49  test    rcx, rcx
0x180015c4c  jz      short loc_180015C71
0x180015c4e  mov     [rsp+68h+var_48], 186h
0x180015c56  mov     r9d, eax
0x180015c59  mov     r8, cs:off_180048A80; "<CPersistErrorCache::AddInternalError|A"...
0x180015c60  mov     edx, 61800h
0x180015c65  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015c6c  call    _bidTraceW
0x180015c71  mov     ecx, edi; int
0x180015c73  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015c78  mov     rcx, [rsp+68h+pperrinfo]
0x180015c80  mov     rax, [rcx]
0x180015c83  lea     rdx, aMicrosoftOledb; "Microsoft OLEDB Persistence Provider"
0x180015c8a  mov     rax, [rax+20h]
0x180015c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c93  mov     edi, eax
0x180015c95  test    eax, eax
0x180015c97  jns     short loc_180015CD8
0x180015c99  test    byte ptr cs:_bidGblFlags, 2
0x180015ca0  jz      short loc_180015CD1
0x180015ca2  mov     rcx, cs:off_180048A78; "<CPersistErrorCache::AddInternalError|A"...
0x180015ca9  test    rcx, rcx
0x180015cac  jz      short loc_180015CD1
0x180015cae  mov     [rsp+68h+var_48], 187h
0x180015cb6  mov     r9d, eax
0x180015cb9  mov     r8, cs:off_180048A78; "<CPersistErrorCache::AddInternalError|A"...
0x180015cc0  mov     edx, 61C00h
0x180015cc5  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015ccc  call    _bidTraceW
0x180015cd1  mov     ecx, edi; int
0x180015cd3  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015cd8  mov     r8d, r14d; unsigned int
0x180015cdb  mov     edx, esi; int
0x180015cdd  mov     rcx, r15; this
0x180015ce0  call    ?GetErrorDescription@CPersistErrorCache@@AEAAPEAGJK@Z; CPersistErrorCache::GetErrorDescription(long,ulong)
0x180015ce5  mov     [rsp+68h+var_38], rax
0x180015cea  test    rax, rax
0x180015ced  jz      short loc_180015D52
0x180015cef  mov     rcx, [rsp+68h+pperrinfo]
0x180015cf7  mov     rdx, [rcx]
0x180015cfa  mov     r8, [rdx+28h]
0x180015cfe  mov     rdx, rax
0x180015d01  mov     rax, r8
0x180015d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d09  mov     edi, eax
0x180015d0b  test    eax, eax
0x180015d0d  jns     loc_180015E42
0x180015d13  test    byte ptr cs:_bidGblFlags, 2
0x180015d1a  jz      short loc_180015D4B
0x180015d1c  mov     rcx, cs:off_180048A70; "<CPersistErrorCache::AddInternalError|A"...
0x180015d23  test    rcx, rcx
0x180015d26  jz      short loc_180015D4B
0x180015d28  mov     [rsp+68h+var_48], 18Bh
0x180015d30  mov     r9d, eax
0x180015d33  mov     r8, cs:off_180048A70; "<CPersistErrorCache::AddInternalError|A"...
0x180015d3a  mov     edx, 62C00h
0x180015d3f  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015d46  call    _bidTraceW
0x180015d4b  mov     ecx, edi; int
0x180015d4d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015d52  mov     r14d, 88h
0x180015d58  mov     ecx, esi
0x180015d5a  call    GetErrorDescriptionSDK
0x180015d5f  mov     rbx, rax
0x180015d62  mov     [rsp+68h+var_28], rax
0x180015d67  test    rax, rax
0x180015d6a  jz      short loc_180015DCC
0x180015d6c  mov     rcx, [rsp+68h+pperrinfo]
0x180015d74  mov     rax, [rcx]
0x180015d77  mov     rdx, rbx
0x180015d7a  mov     rax, [rax+28h]
0x180015d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d83  mov     edi, eax
0x180015d85  test    eax, eax
0x180015d87  jns     loc_180015E42
0x180015d8d  test    byte ptr cs:_bidGblFlags, 2
0x180015d94  jz      short loc_180015DC5
0x180015d96  mov     rcx, cs:off_180048A68; "<CPersistErrorCache::AddInternalError|A"...
0x180015d9d  test    rcx, rcx
0x180015da0  jz      short loc_180015DC5
0x180015da2  mov     [rsp+68h+var_48], 193h
0x180015daa  mov     r9d, eax
0x180015dad  mov     r8, cs:off_180048A68; "<CPersistErrorCache::AddInternalError|A"...
0x180015db4  mov     edx, 64C00h
0x180015db9  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015dc0  call    _bidTraceW
0x180015dc5  mov     ecx, edi; int
0x180015dc7  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015dcc  mov     r8d, r14d; unsigned int
0x180015dcf  mov     edx, esi; int
0x180015dd1  mov     rcx, r15; this
0x180015dd4  call    ?GetErrorDescription@CPersistErrorCache@@AEAAPEAGJK@Z; CPersistErrorCache::GetErrorDescription(long,ulong)
0x180015dd9  mov     [rsp+68h+var_38], rax
0x180015dde  test    rax, rax
0x180015de1  jz      short loc_180015E42
0x180015de3  mov     rcx, [rsp+68h+pperrinfo]
0x180015deb  mov     rdx, [rcx]
0x180015dee  mov     r8, [rdx+28h]
0x180015df2  mov     rdx, rax
0x180015df5  mov     rax, r8
0x180015df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dfd  mov     edi, eax
0x180015dff  test    eax, eax
0x180015e01  jns     short loc_180015E42
0x180015e03  test    byte ptr cs:_bidGblFlags, 2
0x180015e0a  jz      short loc_180015E3B
0x180015e0c  mov     rcx, cs:off_180048A60; "<CPersistErrorCache::AddInternalError|A"...
0x180015e13  test    rcx, rcx
0x180015e16  jz      short loc_180015E3B
0x180015e18  mov     [rsp+68h+var_48], 199h
0x180015e20  mov     r9d, eax
0x180015e23  mov     r8, cs:off_180048A60; "<CPersistErrorCache::AddInternalError|A"...
0x180015e2a  mov     edx, 66400h
0x180015e2f  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015e36  call    _bidTraceW
0x180015e3b  mov     ecx, edi; int
0x180015e3d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015e42  mov     rcx, [rsp+68h+pperrinfo]
0x180015e4a  mov     rax, [rcx]
0x180015e4d  lea     r8, [rsp+68h+var_30]
0x180015e52  lea     rdx, IID_IErrorInfo
0x180015e59  mov     rax, [rax]
0x180015e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e61  mov     edi, eax
0x180015e63  test    eax, eax
0x180015e65  jns     short loc_180015EA6
0x180015e67  test    byte ptr cs:_bidGblFlags, 2
0x180015e6e  jz      short loc_180015E9F
0x180015e70  mov     rcx, cs:off_180048A58; "<CPersistErrorCache::AddInternalError|A"...
0x180015e77  test    rcx, rcx
0x180015e7a  jz      short loc_180015E9F
0x180015e7c  mov     [rsp+68h+var_48], 19Eh
0x180015e84  mov     r9d, eax
0x180015e87  mov     r8, cs:off_180048A58; "<CPersistErrorCache::AddInternalError|A"...
0x180015e8e  mov     edx, 67800h
0x180015e93  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015e9a  call    _bidTraceW
0x180015e9f  mov     ecx, edi; int
0x180015ea1  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015ea6  mov     r9, [rsp+68h+var_30]; struct IErrorInfo *
0x180015eab  mov     r8d, r14d; unsigned int
0x180015eae  mov     edx, esi; int
0x180015eb0  mov     rcx, r15; this
0x180015eb3  call    ?AddError@CPersistErrorCache@@AEAAXJKPEAUIErrorInfo@@@Z; CPersistErrorCache::AddError(long,ulong,IErrorInfo *)
0x180015eb8  nop
0x180015eb9  jmp     short loc_180015EC0
0x180015ebb  mov     rbx, [rsp+68h+var_28]
0x180015ec0  mov     rcx, rbx; bstrString
0x180015ec3  call    cs:__imp_SysFreeString
0x180015ec9  nop
0x180015eca  lea     rcx, [rsp+68h+var_38]
0x180015ecf  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x180015ed4  nop
0x180015ed5  lea     rcx, [rsp+68h+var_20]
0x180015eda  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180015edf  nop
0x180015ee0  lea     rcx, [rsp+68h+var_30]
0x180015ee5  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180015eea  nop
0x180015eeb  lea     rcx, [rsp+68h+pperrinfo]
0x180015ef3  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180015ef8  mov     rbx, [rsp+68h+arg_0]
0x180015efd  mov     rsi, [rsp+68h+arg_8]
0x180015f02  add     rsp, 50h
0x180015f06  pop     r15
0x180015f08  pop     r14
0x180015f0a  pop     rdi
0x180015f0b  retn
```
