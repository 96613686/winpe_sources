# GenADTG::Term(unsigned __int64)

- ea: `0x180009ed0`
- end: `0x18000a0f1`
- name: `?Term@GenADTG@@QEAAX_K@Z`
- size: `545`
- prototype: `void __fastcall(GenADTG *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180007560`
- `0x180009ed0`

## callees

- `0x18000266c`
- `0x180007494`
- `0x180009ed0`
- `0x18001a6c8`
- `0x18002cd54`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180009f8f`
- `ole32!CoTaskMemFree` at `0x180009f99`
- `ole32!CoTaskMemFree` at `0x180009f8f`
- `ole32!CoTaskMemFree` at `0x180009f99`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180009f04`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180009f04`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000a0c0`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000a0c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall GenADTG::Term(GenADTG *this, __int64 a2)
{
  unsigned int *v4; // r9
  HRESULT ErrorInfo; // r15d
  __int64 v6; // rbx
  int v7; // eax
  int v8; // ebx
  __int64 i; // rbx
  __int64 v10; // rdx
  int v11; // esi
  __int64 v12; // [rsp+70h] [rbp+38h] BYREF
  __int64 v13; // [rsp+78h] [rbp+40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+80h] [rbp+48h] BYREF
  __int64 v15; // [rsp+88h] [rbp+50h] BYREF

  v15 = 0;
  pperrinfo = 0;
  v13 = 0;
  ErrorInfo = GetErrorInfo(0, &pperrinfo);
  v6 = *((_QWORD *)this + 37);
  if ( a2 )
  {
    v12 = 0;
    (***((void (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
      *((_QWORD *)this + 3),
      &IID_IChapteredRowset,
      &v12);
    if ( v12 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v12 + 32LL))(v12, a2, 0);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v12);
  }
  while ( v6 )
  {
    GenADTG::Term(*(GenADTG **)v6, *(_QWORD *)(v6 + 8));
    v6 = *(_QWORD *)(v6 + 16);
  }
  GenADTG::ReleaseHRows(this, *((_QWORD *)this + 13), *((unsigned __int64 **)this + 14), v4);
  *((_QWORD *)this + 13) = 0;
  CoTaskMemFree(*((LPVOID *)this + 14));
  CoTaskMemFree(*((LPVOID *)this + 15));
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
         *((_QWORD *)this + 3),
         &IID_IRowsetNotifyEnable,
         &v13) >= 0 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 24LL))(v13, 1);
  v7 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 3))(
         *((_QWORD *)this + 3),
         &IID_IAccessor,
         &v15);
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_1800485C0[0] )
        bidTraceW(off_1800481C0[0], 613376, off_1800485C0[0], (unsigned int)v7, 599);
    }
    ThrowHR(v8);
  }
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 20); i = (unsigned int)(i + 1) )
  {
    v10 = *(_QWORD *)(*((_QWORD *)this + 9) + 8 * i);
    if ( v10 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v15 + 48LL))(v15, v10, 0);
      if ( v11 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800485B8[0] )
          bidTraceW(off_1800481C0[0], 622592, off_1800485B8[0], (unsigned int)v11, 608);
        ThrowHR(v11);
      }
      *(_QWORD *)(*((_QWORD *)this + 9) + 8 * i) = 0;
    }
  }
  if ( !ErrorInfo )
    SetErrorInfo(0, pperrinfo);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v13);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&pperrinfo);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v15);
}

```

## disassembly

```asm
0x180009ed0  push    rbp
0x180009ed2  push    rbx
0x180009ed3  push    rsi
0x180009ed4  push    rdi
0x180009ed5  push    r14
0x180009ed7  push    r15
0x180009ed9  mov     rbp, rsp
0x180009edc  sub     rsp, 38h
0x180009ee0  mov     rsi, rdx
0x180009ee3  mov     rdi, rcx
0x180009ee6  mov     [rbp+arg_18], 0
0x180009eee  mov     [rbp+pperrinfo], 0
0x180009ef6  mov     [rbp+arg_8], 0
0x180009efe  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180009f02  xor     ecx, ecx; dwReserved
0x180009f04  call    cs:__imp_GetErrorInfo
0x180009f0a  mov     r15d, eax
0x180009f0d  mov     rbx, [rdi+128h]
0x180009f14  test    rsi, rsi
0x180009f17  jz      short loc_180009F72
0x180009f19  mov     [rbp+arg_0], 0
0x180009f21  mov     rcx, [rdi+18h]
0x180009f25  mov     rdx, [rcx]
0x180009f28  mov     rax, [rdx]
0x180009f2b  lea     r8, [rbp+arg_0]
0x180009f2f  lea     rdx, IID_IChapteredRowset
0x180009f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f3b  mov     rcx, [rbp+arg_0]
0x180009f3f  test    rcx, rcx
0x180009f42  jz      short loc_180009F57
0x180009f44  mov     rax, [rcx]
0x180009f47  xor     r8d, r8d
0x180009f4a  mov     rdx, rsi
0x180009f4d  mov     rax, [rax+20h]
0x180009f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f56  nop
0x180009f57  lea     rcx, [rbp+arg_0]
0x180009f5b  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180009f60  jmp     short loc_180009F72
0x180009f62  mov     rdx, [rbx+8]; unsigned __int64
0x180009f66  mov     rcx, [rbx]; this
0x180009f69  call    ?Term@GenADTG@@QEAAX_K@Z; GenADTG::Term(unsigned __int64)
0x180009f6e  mov     rbx, [rbx+10h]
0x180009f72  test    rbx, rbx
0x180009f75  jnz     short loc_180009F62
0x180009f77  mov     r8, [rdi+70h]; unsigned __int64 *
0x180009f7b  mov     rdx, [rdi+68h]; unsigned __int64
0x180009f7f  mov     rcx, rdi; this
0x180009f82  call    ?ReleaseHRows@GenADTG@@AEAAX_KPEA_KPEAK@Z; GenADTG::ReleaseHRows(unsigned __int64,unsigned __int64 *,ulong *)
0x180009f87  mov     [rdi+68h], rbx
0x180009f8b  mov     rcx, [rdi+70h]; pv
0x180009f8f  call    cs:__imp_CoTaskMemFree
0x180009f95  mov     rcx, [rdi+78h]; pv
0x180009f99  call    cs:__imp_CoTaskMemFree
0x180009f9f  mov     [rdi+70h], rbx
0x180009fa3  mov     [rdi+78h], rbx
0x180009fa7  mov     rcx, [rdi+18h]
0x180009fab  mov     rax, [rcx]
0x180009fae  lea     r8, [rbp+arg_8]
0x180009fb2  lea     rdx, ?IID_IRowsetNotifyEnable@@3U_GUID@@B; _GUID const IID_IRowsetNotifyEnable
0x180009fb9  mov     rax, [rax]
0x180009fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fc1  test    eax, eax
0x180009fc3  js      short loc_180009FD8
0x180009fc5  mov     rcx, [rbp+arg_8]
0x180009fc9  mov     rax, [rcx]
0x180009fcc  lea     edx, [rbx+1]
0x180009fcf  mov     rax, [rax+18h]
0x180009fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fd8  mov     rcx, [rdi+18h]
0x180009fdc  mov     rax, [rcx]
0x180009fdf  lea     r8, [rbp+arg_18]
0x180009fe3  lea     rdx, IID_IAccessor
0x180009fea  mov     rax, [rax]
0x180009fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ff2  mov     ebx, eax
0x180009ff4  test    eax, eax
0x180009ff6  jns     short loc_18000A038
0x180009ff8  test    byte ptr cs:_bidGblFlags, 2
0x180009fff  jz      short loc_18000A030
0x18000a001  mov     rcx, cs:off_1800485C0; "<GenADTG::Term|ADO|ERR>  HRESULT: 0x%08"...
0x18000a008  test    rcx, rcx
0x18000a00b  jz      short loc_18000A030
0x18000a00d  mov     [rsp+38h+var_18], 257h
0x18000a015  mov     r9d, eax
0x18000a018  mov     r8, cs:off_1800485C0; "<GenADTG::Term|ADO|ERR>  HRESULT: 0x%08"...
0x18000a01f  mov     edx, 95C00h
0x18000a024  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000a02b  call    _bidTraceW
0x18000a030  mov     ecx, ebx; int
0x18000a032  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000a038  xor     ebx, ebx
0x18000a03a  cmp     ebx, [rdi+50h]
0x18000a03d  jnb     short loc_18000A0B5
0x18000a03f  mov     rax, [rdi+48h]
0x18000a043  mov     rdx, [rax+rbx*8]
0x18000a047  test    rdx, rdx
0x18000a04a  jz      short loc_18000A071
0x18000a04c  mov     rcx, [rbp+arg_18]
0x18000a050  mov     rax, [rcx]
0x18000a053  xor     r8d, r8d
0x18000a056  mov     rax, [rax+30h]
0x18000a05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a05f  mov     esi, eax
0x18000a061  test    eax, eax
0x18000a063  js      short loc_18000A075
0x18000a065  mov     rax, [rdi+48h]
0x18000a069  mov     qword ptr [rax+rbx*8], 0
0x18000a071  inc     ebx
0x18000a073  jmp     short loc_18000A03A
0x18000a075  test    byte ptr cs:_bidGblFlags, 2
0x18000a07c  jz      short loc_18000A0AD
0x18000a07e  mov     rax, cs:off_1800485B8; "<GenADTG::Term|ADO|ERR>  HRESULT: 0x%08"...
0x18000a085  test    rax, rax
0x18000a088  jz      short loc_18000A0AD
0x18000a08a  mov     [rsp+38h+var_18], 260h
0x18000a092  mov     r9d, esi
0x18000a095  mov     r8, cs:off_1800485B8; "<GenADTG::Term|ADO|ERR>  HRESULT: 0x%08"...
0x18000a09c  mov     edx, 98000h
0x18000a0a1  mov     rcx, cs:off_1800481C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000a0a8  call    _bidTraceW
0x18000a0ad  mov     ecx, esi; int
0x18000a0af  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000a0b5  test    r15d, r15d
0x18000a0b8  jnz     short loc_18000A0C7
0x18000a0ba  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18000a0be  xor     ecx, ecx; dwReserved
0x18000a0c0  call    cs:__imp_SetErrorInfo
0x18000a0c6  nop
0x18000a0c7  lea     rcx, [rbp+arg_8]
0x18000a0cb  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18000a0d0  nop
0x18000a0d1  lea     rcx, [rbp+pperrinfo]
0x18000a0d5  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18000a0da  nop
0x18000a0db  lea     rcx, [rbp+arg_18]
0x18000a0df  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18000a0e4  add     rsp, 38h
0x18000a0e8  pop     r15
0x18000a0ea  pop     r14
0x18000a0ec  pop     rdi
0x18000a0ed  pop     rsi
0x18000a0ee  pop     rbx
0x18000a0ef  pop     rbp
0x18000a0f0  retn
```
