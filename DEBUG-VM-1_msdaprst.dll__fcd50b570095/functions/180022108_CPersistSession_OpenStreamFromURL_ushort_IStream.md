# CPersistSession::OpenStreamFromURL(ushort *,IStream * *)

- ea: `0x180022108`
- end: `0x180022364`
- name: `?OpenStreamFromURL@CPersistSession@@AEAAJPEAGPEAPEAUIStream@@@Z`
- size: `604`
- prototype: `__int64 __fastcall(CPersistSession *__hidden this, unsigned __int16 *, struct IStream **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021680`

## callees

- `0x18000266c`
- `0x18001a6c8`
- `0x180020dec`
- `0x180021060`
- `0x180022108`
- `0x18002cd54`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CPersistSession::OpenStreamFromURL(CPersistSession *this, unsigned __int16 *a2, struct IStream **a3)
{
  unsigned int v5; // esi
  int v6; // ebx
  CPersistSession *v7; // rbx
  CPersistSession *v8; // rcx
  signed int URLMonDLL; // edi
  int v10; // edi
  int v11; // ebx
  int v12; // ebx
  int v14; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15; // [rsp+38h] [rbp-30h] BYREF
  __int64 v16; // [rsp+40h] [rbp-28h] BYREF
  CPersistSession *v17; // [rsp+70h] [rbp+8h] BYREF
  __int64 v18; // [rsp+88h] [rbp+20h] BYREF

  v17 = this;
  try
  {
    v5 = 0;
    v15 = 0;
    v18 = 0;
    v16 = 0;
    v17 = 0;
    v6 = ATL::CComObject<CBindingCallback>::CreateInstance(&v17);
    if ( v6 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180048C10[0] )
          bidTraceW(off_1800481F8[0], 303104, off_180048C10[0], (unsigned int)v6, 296);
      }
      ThrowHR(v6);
    }
    v7 = v17;
    (*(void (__fastcall **)(CPersistSession *))(*(_QWORD *)v17 + 8LL))(v17);
    *a3 = 0;
    URLMonDLL = CPersistSession::GetURLMonDLL(v8);
    if ( URLMonDLL < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048C08[0] )
        bidTraceW(off_1800481F8[0], 310272, off_180048C08[0], (unsigned int)URLMonDLL, 303);
      ThrowHR(URLMonDLL);
    }
    v10 = ((__int64 (__fastcall *)(_QWORD, unsigned __int16 *, __int64 *))CPersistSession::m_pCreateURLMoniker)(
            0,
            a2,
            &v15);
    if ( v10 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048C00[0] )
        bidTraceW(off_1800481F8[0], 313344, off_180048C00[0], (unsigned int)v10, 306);
      ThrowHR(v10);
    }
    v11 = ((__int64 (__fastcall *)(_QWORD, CPersistSession *, _QWORD, __int64 *))CPersistSession::m_pCreateAsyncBindCtx)(
            0,
            v7,
            0,
            &v18);
    if ( v11 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048BF8[0] )
        bidTraceW(off_1800481F8[0], 316416, off_180048BF8[0], (unsigned int)v11, 309);
      ThrowHR(v11);
    }
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, GUID *, struct IStream **))(*(_QWORD *)v15 + 72LL))(
            v15,
            v18,
            0,
            &IID_IStream,
            a3);
    if ( v12 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048BF0[0] )
        bidTraceW(off_1800481F8[0], 319488, off_180048BF0[0], (unsigned int)v12, 312);
      ThrowHR(v12);
    }
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v17);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v16);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v18);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v15);
  }
  catch ( long v14 )
  {
    LODWORD(v17) = v14;
    return (unsigned int)v17;
  }
  catch ( ... )
  {
    LODWORD(v17) = -2147467259;
    return (unsigned int)v17;
  }
  return v5;
}

```

## disassembly

```asm
0x180022108  mov     rax, rsp
0x18002210b  mov     [rax+10h], rbx
0x18002210f  mov     [rax+18h], rsi
0x180022113  mov     [rax+8], rcx
0x180022117  push    rdi
0x180022118  push    r14
0x18002211a  push    r15
0x18002211c  sub     rsp, 50h
0x180022120  mov     r14, r8
0x180022123  mov     r15, rdx
0x180022126  xor     esi, esi
0x180022128  mov     [rax-30h], rsi
0x18002212c  mov     [rax+20h], rsi
0x180022130  mov     [rax-28h], rsi
0x180022134  mov     [rax+8], rsi
0x180022138  lea     rcx, [rax+8]
0x18002213c  call    ?CreateInstance@?$CComObject@VCBindingCallback@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CBindingCallback>::CreateInstance(ATL::CComObject<CBindingCallback> * *)
0x180022141  mov     ebx, eax
0x180022143  test    eax, eax
0x180022145  jns     short loc_180022186
0x180022147  test    byte ptr cs:_bidGblFlags, 2
0x18002214e  jz      short loc_18002217F
0x180022150  mov     rax, cs:off_180048C10; "<CPersistSession::OpenStreamFromURL|ADO"...
0x180022157  test    rax, rax
0x18002215a  jz      short loc_18002217F
0x18002215c  mov     dword ptr [rsp+68h+var_48], 128h
0x180022164  mov     r9d, ebx
0x180022167  mov     r8, cs:off_180048C10; "<CPersistSession::OpenStreamFromURL|ADO"...
0x18002216e  mov     edx, 4A000h
0x180022173  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002217a  call    _bidTraceW
0x18002217f  mov     ecx, ebx; int
0x180022181  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180022186  mov     rbx, [rsp+68h+arg_0]
0x18002218b  mov     rax, [rbx]
0x18002218e  mov     rcx, rbx
0x180022191  mov     rax, [rax+8]
0x180022195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002219a  mov     qword ptr [r14], 0
0x1800221a1  call    ?GetURLMonDLL@CPersistSession@@AEAAJXZ; CPersistSession::GetURLMonDLL(void)
0x1800221a6  mov     edi, eax
0x1800221a8  test    eax, eax
0x1800221aa  jns     short loc_1800221EB
0x1800221ac  test    byte ptr cs:_bidGblFlags, 2
0x1800221b3  jz      short loc_1800221E4
0x1800221b5  mov     rax, cs:off_180048C08; "<CPersistSession::OpenStreamFromURL|ADO"...
0x1800221bc  test    rax, rax
0x1800221bf  jz      short loc_1800221E4
0x1800221c1  mov     dword ptr [rsp+68h+var_48], 12Fh
0x1800221c9  mov     r9d, edi
0x1800221cc  mov     r8, cs:off_180048C08; "<CPersistSession::OpenStreamFromURL|ADO"...
0x1800221d3  mov     edx, 4BC00h
0x1800221d8  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800221df  call    _bidTraceW
0x1800221e4  mov     ecx, edi; int
0x1800221e6  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800221eb  lea     r8, [rsp+68h+var_30]
0x1800221f0  mov     rdx, r15
0x1800221f3  xor     ecx, ecx
0x1800221f5  mov     rax, cs:?m_pCreateURLMoniker@CPersistSession@@0P6AJPEAUIMoniker@@PEAGPEAPEAU2@@ZEA; long (*CPersistSession::m_pCreateURLMoniker)(IMoniker *,ushort *,IMoniker * *)
0x1800221fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022201  mov     edi, eax
0x180022203  test    eax, eax
0x180022205  jns     short loc_180022246
0x180022207  test    byte ptr cs:_bidGblFlags, 2
0x18002220e  jz      short loc_18002223F
0x180022210  mov     rax, cs:off_180048C00; "<CPersistSession::OpenStreamFromURL|ADO"...
0x180022217  test    rax, rax
0x18002221a  jz      short loc_18002223F
0x18002221c  mov     dword ptr [rsp+68h+var_48], 132h
0x180022224  mov     r9d, edi
0x180022227  mov     r8, cs:off_180048C00; "<CPersistSession::OpenStreamFromURL|ADO"...
0x18002222e  mov     edx, 4C800h
0x180022233  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002223a  call    _bidTraceW
0x18002223f  mov     ecx, edi; int
0x180022241  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180022246  lea     r9, [rsp+68h+arg_18]
0x18002224e  xor     r8d, r8d
0x180022251  mov     rdx, rbx
0x180022254  xor     ecx, ecx
0x180022256  mov     rax, cs:?m_pCreateAsyncBindCtx@CPersistSession@@0P6AJKPEAUIBindStatusCallback@@PEAUIEnumFORMATETC@@PEAPEAUIBindCtx@@@ZEA; long (*CPersistSession::m_pCreateAsyncBindCtx)(ulong,IBindStatusCallback *,IEnumFORMATETC *,IBindCtx * *)
0x18002225d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022262  mov     ebx, eax
0x180022264  test    eax, eax
0x180022266  jns     short loc_1800222A7
0x180022268  test    byte ptr cs:_bidGblFlags, 2
0x18002226f  jz      short loc_1800222A0
0x180022271  mov     rax, cs:off_180048BF8; "<CPersistSession::OpenStreamFromURL|ADO"...
0x180022278  test    rax, rax
0x18002227b  jz      short loc_1800222A0
0x18002227d  mov     dword ptr [rsp+68h+var_48], 135h
0x180022285  mov     r9d, ebx
0x180022288  mov     r8, cs:off_180048BF8; "<CPersistSession::OpenStreamFromURL|ADO"...
0x18002228f  mov     edx, 4D400h
0x180022294  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002229b  call    _bidTraceW
0x1800222a0  mov     ecx, ebx; int
0x1800222a2  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800222a7  mov     rcx, [rsp+68h+var_30]
0x1800222ac  mov     rax, [rcx]
0x1800222af  mov     [rsp+68h+var_48], r14
0x1800222b4  lea     r9, IID_IStream
0x1800222bb  xor     r8d, r8d
0x1800222be  mov     rdx, [rsp+68h+arg_18]
0x1800222c6  mov     rax, [rax+48h]
0x1800222ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222cf  mov     ebx, eax
0x1800222d1  test    eax, eax
0x1800222d3  jns     short loc_180022315
0x1800222d5  test    byte ptr cs:_bidGblFlags, 2
0x1800222dc  jz      short loc_18002230D
0x1800222de  mov     rax, cs:off_180048BF0; "<CPersistSession::OpenStreamFromURL|ADO"...
0x1800222e5  test    rax, rax
0x1800222e8  jz      short loc_18002230D
0x1800222ea  mov     dword ptr [rsp+68h+var_48], 138h
0x1800222f2  mov     r9d, ebx
0x1800222f5  mov     r8, cs:off_180048BF0; "<CPersistSession::OpenStreamFromURL|ADO"...
0x1800222fc  mov     edx, 4E000h
0x180022301  mov     rcx, cs:off_1800481F8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180022308  call    _bidTraceW
0x18002230d  mov     ecx, ebx; int
0x18002230f  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180022315  lea     rcx, [rsp+68h+arg_0]
0x18002231a  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002231f  nop
0x180022320  lea     rcx, [rsp+68h+var_28]
0x180022325  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002232a  nop
0x18002232b  lea     rcx, [rsp+68h+arg_18]
0x180022333  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180022338  nop
0x180022339  lea     rcx, [rsp+68h+var_30]
0x18002233e  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180022343  nop
0x180022344  jmp     short loc_18002234C
0x180022346  jmp     short $+2
0x180022348  mov     esi, dword ptr [rsp+68h+arg_0]
0x18002234c  mov     eax, esi
0x18002234e  lea     r11, [rsp+68h+var_18]
0x180022353  mov     rbx, [r11+28h]
0x180022357  mov     rsi, [r11+30h]
0x18002235b  mov     rsp, r11
0x18002235e  pop     r15
0x180022360  pop     r14
0x180022362  pop     rdi
0x180022363  retn
```
