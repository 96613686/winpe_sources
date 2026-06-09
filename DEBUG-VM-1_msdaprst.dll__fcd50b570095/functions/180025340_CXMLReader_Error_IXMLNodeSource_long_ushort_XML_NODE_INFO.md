# CXMLReader::Error(IXMLNodeSource *,long,ushort,_XML_NODE_INFO * *)

- ea: `0x180025340`
- end: `0x18002564c`
- name: `?Error@CXMLReader@@UEAAJPEAUIXMLNodeSource@@JGPEAPEAU_XML_NODE_INFO@@@Z`
- size: `780`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct IXMLNodeSource *, int, unsigned __int16, struct _XML_NODE_INFO **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000266c`
- `0x180015fb4`
- `0x18001a6c8`
- `0x180025340`
- `0x18002cd54`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002563e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002563e`
- `OLEAUT32!__imp_SysStringLen` at `0x1800253e6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800253e6`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180025376`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180025376`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800255c6`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800255c6`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800253f9`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800253f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CXMLReader::Error(CXMLReader *this, struct IXMLNodeSource *a2)
{
  int v3; // eax
  int v4; // ebx
  HRESULT v5; // eax
  int v6; // ebx
  int v7; // eax
  int v8; // ebx
  int v9; // eax
  int v10; // ebx
  int v11; // eax
  int v12; // ebx
  int v13; // eax
  int v14; // ebx
  HRESULT v15; // eax
  int v16; // ebx
  IErrorInfo *perrinfo; // [rsp+30h] [rbp-18h] BYREF
  BSTR pbstr[2]; // [rsp+38h] [rbp-10h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+50h] [rbp+8h] BYREF

  try
  {
    pbstr[0] = 0;
    pperrinfo = 0;
    perrinfo = 0;
    if ( *((_DWORD *)this + 120) <= 1u )
    {
      Exit(-2147467259, 0x8Fu);
    }
    else
    {
      if ( GetErrorInfo(0, &perrinfo) )
      {
        v3 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 56) + 88LL))(
               *((_QWORD *)this + 56),
               pbstr);
        v4 = v3;
        if ( v3 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( off_180048CF8[0] )
              bidTraceW(off_180048208[0], 2599936, off_180048CF8[0], (unsigned int)v3, 2539);
          }
          ThrowHR(v4);
        }
        if ( SysStringLen(pbstr[0]) )
        {
          v5 = CreateErrorInfo(&pperrinfo);
          v6 = v5;
          if ( v5 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180048CF0[0] )
              bidTraceW(off_180048208[0], 2604032, off_180048CF0[0], (unsigned int)v5, 2543);
            ThrowHR(v6);
          }
          v7 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, &GUID_NULL);
          v8 = v7;
          if ( v7 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180048CE8[0] )
              bidTraceW(off_180048208[0], 2605056, off_180048CE8[0], (unsigned int)v7, 2544);
            ThrowHR(v8);
          }
          v9 = ((__int64 (__fastcall *)(ICreateErrorInfo *, const wchar_t *))pperrinfo->lpVtbl->SetSource)(
                 pperrinfo,
                 L"Microsoft OLEDB Persistence Provider");
          v10 = v9;
          if ( v9 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180048CE0[0] )
              bidTraceW(off_180048208[0], 2606080, off_180048CE0[0], (unsigned int)v9, 2545);
            ThrowHR(v10);
          }
          v11 = ((__int64 (__fastcall *)(ICreateErrorInfo *, BSTR))pperrinfo->lpVtbl->SetDescription)(
                  pperrinfo,
                  pbstr[0]);
          v12 = v11;
          if ( v11 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180048CD8[0] )
              bidTraceW(off_180048208[0], 2607104, off_180048CD8[0], (unsigned int)v11, 2546);
            ThrowHR(v12);
          }
          v13 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))pperrinfo->lpVtbl->QueryInterface)(
                  pperrinfo,
                  &IID_IErrorInfo,
                  &perrinfo);
          v14 = v13;
          if ( v13 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180048CD0[0] )
              bidTraceW(off_180048208[0], 2608128, off_180048CD0[0], (unsigned int)v13, 2547);
            ThrowHR(v14);
          }
        }
      }
      if ( perrinfo )
      {
        v15 = SetErrorInfo(0, perrinfo);
        v16 = v15;
        if ( v15 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048CC8[0] )
            bidTraceW(off_180048208[0], 2615296, off_180048CC8[0], (unsigned int)v15, 2554);
          ThrowHR(v16);
        }
      }
    }
  }
  catch ( long )
  {
  }
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&perrinfo);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&pperrinfo);
  SysFreeString(pbstr[0]);
  return 0;
}

```

## disassembly

```asm
0x180025340  mov     rax, rsp
0x180025343  push    rbx
0x180025344  sub     rsp, 40h
0x180025348  mov     rbx, rcx
0x18002534b  mov     qword ptr [rax-10h], 0
0x180025353  mov     qword ptr [rax+8], 0
0x18002535b  mov     qword ptr [rax-18h], 0
0x180025363  cmp     dword ptr [rcx+1E0h], 1
0x18002536a  jbe     loc_180025611
0x180025370  lea     rdx, [rax-18h]; pperrinfo
0x180025374  xor     ecx, ecx; dwReserved
0x180025376  call    cs:__imp_GetErrorInfo
0x18002537c  test    eax, eax
0x18002537e  jz      loc_1800255BA
0x180025384  mov     rcx, [rbx+1C0h]
0x18002538b  mov     rax, [rcx]
0x18002538e  lea     rdx, [rsp+48h+pbstr]
0x180025393  mov     rax, [rax+58h]
0x180025397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002539c  mov     ebx, eax
0x18002539e  test    eax, eax
0x1800253a0  jns     short loc_1800253E1
0x1800253a2  test    byte ptr cs:_bidGblFlags, 2
0x1800253a9  jz      short loc_1800253DA
0x1800253ab  mov     rcx, cs:off_180048CF8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x1800253b2  test    rcx, rcx
0x1800253b5  jz      short loc_1800253DA
0x1800253b7  mov     [rsp+48h+var_28], 9EBh
0x1800253bf  mov     r9d, eax
0x1800253c2  mov     r8, cs:off_180048CF8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x1800253c9  mov     edx, 27AC00h
0x1800253ce  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800253d5  call    _bidTraceW
0x1800253da  mov     ecx, ebx; int
0x1800253dc  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800253e1  mov     rcx, [rsp+48h+pbstr]; pbstr
0x1800253e6  call    cs:__imp_SysStringLen
0x1800253ec  test    eax, eax
0x1800253ee  jz      loc_1800255BA
0x1800253f4  lea     rcx, [rsp+48h+pperrinfo]; pperrinfo
0x1800253f9  call    cs:__imp_CreateErrorInfo
0x1800253ff  mov     ebx, eax
0x180025401  test    eax, eax
0x180025403  jns     short loc_180025444
0x180025405  test    byte ptr cs:_bidGblFlags, 2
0x18002540c  jz      short loc_18002543D
0x18002540e  mov     rcx, cs:off_180048CF0; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x180025415  test    rcx, rcx
0x180025418  jz      short loc_18002543D
0x18002541a  mov     [rsp+48h+var_28], 9EFh
0x180025422  mov     r9d, eax
0x180025425  mov     r8, cs:off_180048CF0; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x18002542c  mov     edx, 27BC00h
0x180025431  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180025438  call    _bidTraceW
0x18002543d  mov     ecx, ebx; int
0x18002543f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180025444  mov     rcx, [rsp+48h+pperrinfo]
0x180025449  mov     rax, [rcx]
0x18002544c  lea     rdx, GUID_NULL
0x180025453  mov     rax, [rax+18h]
0x180025457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002545c  mov     ebx, eax
0x18002545e  test    eax, eax
0x180025460  jns     short loc_1800254A1
0x180025462  test    byte ptr cs:_bidGblFlags, 2
0x180025469  jz      short loc_18002549A
0x18002546b  mov     rcx, cs:off_180048CE8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x180025472  test    rcx, rcx
0x180025475  jz      short loc_18002549A
0x180025477  mov     [rsp+48h+var_28], 9F0h
0x18002547f  mov     r9d, eax
0x180025482  mov     r8, cs:off_180048CE8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x180025489  mov     edx, 27C000h
0x18002548e  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180025495  call    _bidTraceW
0x18002549a  mov     ecx, ebx; int
0x18002549c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800254a1  mov     rcx, [rsp+48h+pperrinfo]
0x1800254a6  mov     rax, [rcx]
0x1800254a9  lea     rdx, aMicrosoftOledb; "Microsoft OLEDB Persistence Provider"
0x1800254b0  mov     rax, [rax+20h]
0x1800254b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254b9  mov     ebx, eax
0x1800254bb  test    eax, eax
0x1800254bd  jns     short loc_1800254FE
0x1800254bf  test    byte ptr cs:_bidGblFlags, 2
0x1800254c6  jz      short loc_1800254F7
0x1800254c8  mov     rcx, cs:off_180048CE0; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x1800254cf  test    rcx, rcx
0x1800254d2  jz      short loc_1800254F7
0x1800254d4  mov     [rsp+48h+var_28], 9F1h
0x1800254dc  mov     r9d, eax
0x1800254df  mov     r8, cs:off_180048CE0; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x1800254e6  mov     edx, 27C400h
0x1800254eb  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800254f2  call    _bidTraceW
0x1800254f7  mov     ecx, ebx; int
0x1800254f9  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800254fe  mov     rcx, [rsp+48h+pperrinfo]
0x180025503  mov     rax, [rcx]
0x180025506  mov     rdx, [rsp+48h+pbstr]
0x18002550b  mov     rax, [rax+28h]
0x18002550f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025514  mov     ebx, eax
0x180025516  test    eax, eax
0x180025518  jns     short loc_180025559
0x18002551a  test    byte ptr cs:_bidGblFlags, 2
0x180025521  jz      short loc_180025552
0x180025523  mov     rcx, cs:off_180048CD8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x18002552a  test    rcx, rcx
0x18002552d  jz      short loc_180025552
0x18002552f  mov     [rsp+48h+var_28], 9F2h
0x180025537  mov     r9d, eax
0x18002553a  mov     r8, cs:off_180048CD8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x180025541  mov     edx, 27C800h
0x180025546  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002554d  call    _bidTraceW
0x180025552  mov     ecx, ebx; int
0x180025554  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180025559  mov     rcx, [rsp+48h+pperrinfo]
0x18002555e  mov     rax, [rcx]
0x180025561  lea     r8, [rsp+48h+perrinfo]
0x180025566  lea     rdx, IID_IErrorInfo
0x18002556d  mov     rax, [rax]
0x180025570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025575  mov     ebx, eax
0x180025577  test    eax, eax
0x180025579  jns     short loc_1800255BA
0x18002557b  test    byte ptr cs:_bidGblFlags, 2
0x180025582  jz      short loc_1800255B3
0x180025584  mov     rcx, cs:off_180048CD0; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x18002558b  test    rcx, rcx
0x18002558e  jz      short loc_1800255B3
0x180025590  mov     [rsp+48h+var_28], 9F3h
0x180025598  mov     r9d, eax
0x18002559b  mov     r8, cs:off_180048CD0; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x1800255a2  mov     edx, 27CC00h
0x1800255a7  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800255ae  call    _bidTraceW
0x1800255b3  mov     ecx, ebx; int
0x1800255b5  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800255ba  mov     rdx, [rsp+48h+perrinfo]; perrinfo
0x1800255bf  test    rdx, rdx
0x1800255c2  jz      short loc_180025621
0x1800255c4  xor     ecx, ecx; dwReserved
0x1800255c6  call    cs:__imp_SetErrorInfo
0x1800255cc  mov     ebx, eax
0x1800255ce  test    eax, eax
0x1800255d0  jns     short loc_180025621
0x1800255d2  test    byte ptr cs:_bidGblFlags, 2
0x1800255d9  jz      short loc_18002560A
0x1800255db  mov     rcx, cs:off_180048CC8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x1800255e2  test    rcx, rcx
0x1800255e5  jz      short loc_18002560A
0x1800255e7  mov     [rsp+48h+var_28], 9FAh
0x1800255ef  mov     r9d, eax
0x1800255f2  mov     r8, cs:off_180048CC8; "<CXMLReader::Error|ADO|ERR>  HRESULT: 0"...
0x1800255f9  mov     edx, 27E800h
0x1800255fe  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180025605  call    _bidTraceW
0x18002560a  mov     ecx, ebx; int
0x18002560c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180025611  mov     edx, 8Fh; unsigned int
0x180025616  mov     ecx, 80004005h; int
0x18002561b  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180025620  nop
0x180025621  jmp     short $+2
0x180025623  lea     rcx, [rsp+48h+perrinfo]
0x180025628  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002562d  nop
0x18002562e  lea     rcx, [rsp+48h+pperrinfo]
0x180025633  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180025638  nop
0x180025639  mov     rcx, [rsp+48h+pbstr]; bstrString
0x18002563e  call    cs:__imp_SysFreeString
0x180025644  xor     eax, eax
0x180025646  add     rsp, 40h
0x18002564a  pop     rbx
0x18002564b  retn
```
