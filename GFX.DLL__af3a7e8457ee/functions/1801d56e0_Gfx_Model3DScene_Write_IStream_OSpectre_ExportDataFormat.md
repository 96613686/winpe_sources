# Gfx::Model3DScene::Write(IStream &,OSpectre::ExportDataFormat)

- ea: `0x1801d56e0`
- end: `0x1801d5a5c`
- name: `?Write@Model3DScene@Gfx@@UEBAXAEAUIStream@@W4ExportDataFormat@OSpectre@@@Z`
- size: `892`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000ad70`
- `0x180056ee0`
- `0x1800573f0`
- `0x1800786fc`
- `0x180095ecc`
- `0x18009c940`
- `0x1800d33a4`
- `0x1800d7dd0`
- `0x1800fb788`
- `0x1800fc400`
- `0x1801d56e0`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x1801d5791`
- `KERNEL32!DecodePointer` at `0x1801d57a8`
- `KERNEL32!DecodePointer` at `0x1801d5791`
- `KERNEL32!DecodePointer` at `0x1801d57a8`
- `Mso20Win32Client!__imp_?CreateByteStreamOnBuffer@Stream@Mso@@YA?AV?$TCntPtr@UIByteStream@@@2@PEBEKPEAUIMsoMemHeap@@@Z` at `0x1801d5910`
- `Mso20Win32Client!__imp_?CreateByteStreamOnBuffer@Stream@Mso@@YA?AV?$TCntPtr@UIByteStream@@@2@PEBEKPEAUIMsoMemHeap@@@Z` at `0x1801d5910`
- `Mso20Win32Client!__imp_?MsoHrGetIBSFromIStreamEx@@YAJPEAUIStream@@K_K1PEAPEAUIByteStream@@@Z` at `0x1801d5970`
- `Mso20Win32Client!__imp_?MsoHrGetIBSFromIStreamEx@@YAJPEAUIStream@@K_K1PEAPEAUIByteStream@@@Z` at `0x1801d5970`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Gfx::Model3DScene::Write(_QWORD *a1, void (*a2)(void), BOOL a3)
{
  Gfx::Model3DFactory *v6; // rcx
  unsigned __int64 v7; // rdx
  unsigned int v8; // r8d
  __int64 (__fastcall *v9)(__int64); // rax
  _QWORD *v10; // rcx
  struct OSpectre::IFactory *SpectreFactory; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rsi
  unsigned int v15; // ebx
  __int64 v16; // rax
  Gfx::Model3DFactory **v17; // rbx
  __int64 v18; // rcx
  int IBSFromIStream; // eax
  int v20; // eax
  char v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  struct IByteStream *v24; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v25[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  Gfx::Model3DFactory **v27; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v28; // [rsp+80h] [rbp-80h]
  _QWORD v29[3]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v30[56]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v31; // [rsp+D8h] [rbp-28h]
  _BYTE v32[56]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v33; // [rsp+118h] [rbp+18h]

  if ( !a1[4] )
    (*(void (__fastcall **)(_QWORD *))(*a1 + 96LL))(a1);
  if ( !a1[4] )
  {
    Ofc::CHResultException::ThrowTag(-2147467259, 0x2594286u);
    __debugbreak();
  }
  v6 = Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance;
  if ( (unsigned __int64)Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance <= 1 )
  {
    while ( (unsigned __int64)Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance <= 1 )
    {
      if ( _InterlockedCompareExchange64(
             (volatile signed __int64 *)&Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance,
             1,
             0) )
      {
        v23 = 0;
        std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v23);
      }
      else
      {
        v27 = &Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance;
        v28 = 0;
        Ofc::AtExit(Ofc::TSingleton<Gfx::Model3DFactory>::Shutdown, a2, a3);
        if ( DecodePointer(qword_18051E980) )
        {
          v23 = 0;
          v9 = (__int64 (__fastcall *)(__int64))DecodePointer(qword_18051E980);
          v10 = (_QWORD *)v9(8);
        }
        else
        {
          v10 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v7, v8);
        }
        *v10 = 0;
        v28 = v10;
        _InterlockedCompareExchange64(
          (volatile signed __int64 *)&Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance,
          (signed __int64)v10,
          1);
      }
    }
    v6 = Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance;
  }
  SpectreFactory = Gfx::Model3DFactory::GetSpectreFactory(v6);
  (*(void (__fastcall **)(struct OSpectre::IFactory *, _QWORD *))(*(_QWORD *)SpectreFactory + 48LL))(
    SpectreFactory,
    v29);
  (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v29[0] + 56LL))(v29[0], 0);
  (*(void (__fastcall **)(_QWORD, _QWORD *, _QWORD))(*(_QWORD *)v29[0] + 48LL))(v29[0], v25, a1[4]);
  v12 = *(_QWORD *)v29[0];
  v33 = 0;
  v31 = 0;
  v22 = 0;
  v13 = (*(__int64 (__fastcall **)(_QWORD, Gfx::Model3DFactory ***, _QWORD *, _QWORD, int, BOOL, _BYTE *, _BYTE *, char))(v12 + 40))(
          v29[0],
          &v27,
          v25,
          0,
          6,
          a3,
          v30,
          v32,
          v22);
  std::shared_ptr<OSpectre::IRenderer>::operator=(v25, v13);
  std::shared_ptr<OSpectre::IModelData>::~shared_ptr<OSpectre::IModelData>(&v27);
  std::_Func_class<bool,float>::~_Func_class<bool,float>(v30);
  std::_Func_class<bool,float>::~_Func_class<bool,float>(v32);
  v14 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v25[0] + 16LL))(v25[0]);
  v15 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v25[0] + 16LL))(v25[0]);
  v16 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v25[0] + 8LL))(v25[0]);
  v17 = *(Gfx::Model3DFactory ***)Mso::Stream::CreateByteStreamOnBuffer(&v23, v16, v15, 0);
  v27 = v17;
  if ( v17 )
    (*((void (__fastcall **)(Gfx::Model3DFactory **))*v17 + 1))(v17);
  v18 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v24 = 0;
  IBSFromIStream = MsoHrGetIBSFromIStreamEx((struct IStream *)a2, 0x10u, 0, 0xFFFFFFFFFFFFFFFFuLL, &v24);
  if ( IBSFromIStream < 0 )
  {
    Ofc::CHResultException::ThrowTag(IBSFromIStream, 0x2594287u);
    __debugbreak();
  }
  v26 = 0;
  v20 = (*((__int64 (__fastcall **)(Gfx::Model3DFactory **, struct IByteStream *, _QWORD, _QWORD, __int64, __int64 *, _QWORD, _QWORD))*v17
         + 8))(
          v17,
          v24,
          0,
          0,
          -1,
          &v26,
          0,
          0);
  if ( v20 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v20, 0x2594288u);
    __debugbreak();
  }
  if ( v14 != v26 )
    Ofc::CHResultException::ThrowTag(-2147467259, 0x2594289u);
  if ( v24 )
    (*(void (__fastcall **)(struct IByteStream *))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v17 )
    (*((void (__fastcall **)(Gfx::Model3DFactory **))*v17 + 2))(v17);
  std::shared_ptr<OSpectre::IModelData>::~shared_ptr<OSpectre::IModelData>(v25);
  return std::shared_ptr<OSpectre::IModelData>::~shared_ptr<OSpectre::IModelData>(v29);
}

```

## disassembly

```asm
0x1801d56e0  mov     [rsp-8+arg_18], rbx
0x1801d56e5  push    rbp
0x1801d56e6  push    rsi
0x1801d56e7  push    rdi
0x1801d56e8  push    r14
0x1801d56ea  push    r15
0x1801d56ec  lea     rbp, [rsp-30h]
0x1801d56f1  sub     rsp, 130h
0x1801d56f8  mov     rax, cs:__security_cookie
0x1801d56ff  xor     rax, rsp
0x1801d5702  mov     [rbp+50h+var_30], rax
0x1801d5706  mov     esi, r8d
0x1801d5709  mov     rdi, rdx
0x1801d570c  mov     rbx, rcx
0x1801d570f  xor     r14d, r14d
0x1801d5712  cmp     [rcx+20h], r14
0x1801d5716  jnz     short loc_1801D5725
0x1801d5718  mov     rax, [rcx]
0x1801d571b  mov     rax, [rax+60h]
0x1801d571f  call    cs:__guard_dispatch_icall_fptr
0x1801d5725  cmp     [rbx+20h], r14
0x1801d5729  jnz     short loc_1801D573B
0x1801d572b  mov     edx, 2594286h; unsigned int
0x1801d5730  mov     ecx, 80004005h; int
0x1801d5735  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1801d573a  int     3; Trap to Debugger
0x1801d573b  mov     rcx, cs:?s_pInstance@?$TSingleton@VModel3DFactory@Gfx@@@Ofc@@0PEAVModel3DFactory@Gfx@@EA; Gfx::Model3DFactory * Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance
0x1801d5742  mov     r15d, 1
0x1801d5748  cmp     rcx, r15
0x1801d574b  ja      loc_1801D5801
0x1801d5751  mov     rax, cs:?s_pInstance@?$TSingleton@VModel3DFactory@Gfx@@@Ofc@@0PEAVModel3DFactory@Gfx@@EA; Gfx::Model3DFactory * Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance
0x1801d5758  cmp     rax, r15
0x1801d575b  ja      loc_1801D57FA
0x1801d5761  xor     eax, eax
0x1801d5763  lock cmpxchg cs:?s_pInstance@?$TSingleton@VModel3DFactory@Gfx@@@Ofc@@0PEAVModel3DFactory@Gfx@@EA, r15; Gfx::Model3DFactory * Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance
0x1801d576c  jnz     short loc_1801D57E6
0x1801d576e  lea     rax, ?s_pInstance@?$TSingleton@VModel3DFactory@Gfx@@@Ofc@@0PEAVModel3DFactory@Gfx@@EA; Gfx::Model3DFactory * Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance
0x1801d5775  mov     [rsp+150h+var_D8], rax
0x1801d577a  mov     [rbp+50h+var_D0], r14
0x1801d577e  lea     rcx, ?Shutdown@?$TSingleton@VModel3DFactory@Gfx@@@Ofc@@SAXXZ; Ptr
0x1801d5785  call    ?AtExit@Ofc@@YAXP6AXXZ_N@Z; Ofc::AtExit(void (*)(void),bool)
0x1801d578a  mov     rcx, cs:qword_18051E980; Ptr
0x1801d5791  call    cs:__imp_DecodePointer
0x1801d5797  test    rax, rax
0x1801d579a  jz      short loc_1801D57C1
0x1801d579c  mov     [rsp+150h+var_100], r14
0x1801d57a1  mov     rcx, cs:qword_18051E980; Ptr
0x1801d57a8  call    cs:__imp_DecodePointer
0x1801d57ae  mov     ecx, 8
0x1801d57b3  call    cs:__guard_dispatch_icall_fptr
0x1801d57b9  mov     rcx, rax
0x1801d57bc  mov     [rax], r14
0x1801d57bf  jmp     short loc_1801D57D1
0x1801d57c1  mov     ecx, 8; this
0x1801d57c6  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1801d57cb  mov     rcx, rax
0x1801d57ce  mov     [rax], r14
0x1801d57d1  mov     [rbp+50h+var_D0], rcx
0x1801d57d5  mov     rax, r15
0x1801d57d8  lock cmpxchg cs:?s_pInstance@?$TSingleton@VModel3DFactory@Gfx@@@Ofc@@0PEAVModel3DFactory@Gfx@@EA, rcx; Gfx::Model3DFactory * Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance
0x1801d57e1  jmp     loc_1801D5751
0x1801d57e6  mov     [rsp+150h+var_100], r14
0x1801d57eb  lea     rcx, [rsp+150h+var_100]
0x1801d57f0  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1801d57f5  jmp     loc_1801D5751
0x1801d57fa  mov     rcx, cs:?s_pInstance@?$TSingleton@VModel3DFactory@Gfx@@@Ofc@@0PEAVModel3DFactory@Gfx@@EA; this
0x1801d5801  call    ?GetSpectreFactory@Model3DFactory@Gfx@@QEAAAEAUIFactory@OSpectre@@XZ; Gfx::Model3DFactory::GetSpectreFactory(void)
0x1801d5806  mov     r8, rax
0x1801d5809  mov     rcx, [rax]
0x1801d580c  mov     rax, [rcx+30h]
0x1801d5810  lea     rdx, [rbp+50h+var_C8]
0x1801d5814  mov     rcx, r8
0x1801d5817  call    cs:__guard_dispatch_icall_fptr
0x1801d581d  nop
0x1801d581e  mov     rcx, [rbp+50h+var_C8]
0x1801d5822  mov     rax, [rcx]
0x1801d5825  xor     edx, edx
0x1801d5827  mov     rax, [rax+38h]
0x1801d582b  call    cs:__guard_dispatch_icall_fptr
0x1801d5831  mov     rcx, [rbp+50h+var_C8]
0x1801d5835  mov     rax, [rcx]
0x1801d5838  mov     r8, [rbx+20h]
0x1801d583c  lea     rdx, [rsp+150h+var_F0]
0x1801d5841  mov     rax, [rax+30h]
0x1801d5845  call    cs:__guard_dispatch_icall_fptr
0x1801d584b  nop
0x1801d584c  mov     rcx, [rbp+50h+var_C8]
0x1801d5850  mov     rax, [rcx]
0x1801d5853  mov     [rbp+50h+var_38], r14
0x1801d5857  mov     [rbp+50h+var_78], r14
0x1801d585b  mov     [rsp+150h+var_110], r14b
0x1801d5860  lea     rdx, [rbp+50h+var_70]
0x1801d5864  mov     [rsp+150h+var_118], rdx
0x1801d5869  lea     rdx, [rbp+50h+var_B0]
0x1801d586d  mov     [rsp+150h+var_120], rdx
0x1801d5872  mov     dword ptr [rsp+150h+var_128], esi
0x1801d5876  mov     dword ptr [rsp+150h+var_130], 6
0x1801d587e  xor     r9d, r9d
0x1801d5881  lea     r8, [rsp+150h+var_F0]
0x1801d5886  lea     rdx, [rsp+150h+var_D8]
0x1801d588b  mov     rax, [rax+28h]
0x1801d588f  call    cs:__guard_dispatch_icall_fptr
0x1801d5895  mov     rdx, rax
0x1801d5898  lea     rcx, [rsp+150h+var_F0]
0x1801d589d  call    ??4?$shared_ptr@UIRenderer@OSpectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<OSpectre::IRenderer>::operator=(std::shared_ptr<OSpectre::IRenderer> &&)
0x1801d58a2  lea     rcx, [rsp+150h+var_D8]
0x1801d58a7  call    ??1?$shared_ptr@UIModelData@OSpectre@@@std@@QEAA@XZ; std::shared_ptr<OSpectre::IModelData>::~shared_ptr<OSpectre::IModelData>(void)
0x1801d58ac  lea     rcx, [rbp+50h+var_B0]
0x1801d58b0  call    ??1?$_Func_class@_NM@std@@QEAA@XZ; std::_Func_class<bool,float>::~_Func_class<bool,float>(void)
0x1801d58b5  lea     rcx, [rbp+50h+var_70]
0x1801d58b9  call    ??1?$_Func_class@_NM@std@@QEAA@XZ; std::_Func_class<bool,float>::~_Func_class<bool,float>(void)
0x1801d58be  xchg    ax, ax
0x1801d58c0  mov     rcx, [rsp+150h+var_F0]
0x1801d58c5  mov     rax, [rcx]
0x1801d58c8  mov     rax, [rax+10h]
0x1801d58cc  call    cs:__guard_dispatch_icall_fptr
0x1801d58d2  mov     rsi, rax
0x1801d58d5  mov     rdx, [rsp+150h+var_F0]
0x1801d58da  mov     rcx, [rdx]
0x1801d58dd  mov     rax, [rcx+10h]
0x1801d58e1  mov     rcx, rdx
0x1801d58e4  call    cs:__guard_dispatch_icall_fptr
0x1801d58ea  mov     rbx, rax
0x1801d58ed  mov     rdx, [rsp+150h+var_F0]
0x1801d58f2  mov     rcx, [rdx]
0x1801d58f5  mov     rax, [rcx+8]
0x1801d58f9  mov     rcx, rdx
0x1801d58fc  call    cs:__guard_dispatch_icall_fptr
0x1801d5902  xor     r9d, r9d
0x1801d5905  mov     r8d, ebx
0x1801d5908  mov     rdx, rax
0x1801d590b  lea     rcx, [rsp+150h+var_100]
0x1801d5910  call    cs:__imp_?CreateByteStreamOnBuffer@Stream@Mso@@YA?AV?$TCntPtr@UIByteStream@@@2@PEBEKPEAUIMsoMemHeap@@@Z; Mso::Stream::CreateByteStreamOnBuffer(uchar const *,ulong,IMsoMemHeap *)
0x1801d5916  mov     rbx, [rax]
0x1801d5919  mov     [rsp+150h+var_D8], rbx
0x1801d591e  test    rbx, rbx
0x1801d5921  jz      short loc_1801D5934
0x1801d5923  mov     rax, [rbx]
0x1801d5926  mov     rcx, rbx
0x1801d5929  mov     rax, [rax+8]
0x1801d592d  call    cs:__guard_dispatch_icall_fptr
0x1801d5933  nop
0x1801d5934  mov     rcx, [rsp+150h+var_100]
0x1801d5939  test    rcx, rcx
0x1801d593c  jz      short loc_1801D5950
0x1801d593e  mov     [rsp+150h+var_100], r14
0x1801d5943  mov     rax, [rcx]
0x1801d5946  mov     rax, [rax+10h]
0x1801d594a  call    cs:__guard_dispatch_icall_fptr
0x1801d5950  mov     [rsp+150h+var_F8], r14
0x1801d5955  lea     rax, [rsp+150h+var_F8]
0x1801d595a  mov     [rsp+150h+var_130], rax
0x1801d595f  or      r15, 0FFFFFFFFFFFFFFFFh
0x1801d5963  mov     r9, r15
0x1801d5966  xor     r8d, r8d
0x1801d5969  lea     edx, [r15+11h]
0x1801d596d  mov     rcx, rdi
0x1801d5970  call    cs:__imp_?MsoHrGetIBSFromIStreamEx@@YAJPEAUIStream@@K_K1PEAPEAUIByteStream@@@Z; MsoHrGetIBSFromIStreamEx(IStream *,ulong,unsigned __int64,unsigned __int64,IByteStream * *)
0x1801d5976  test    eax, eax
0x1801d5978  jns     short loc_1801D5987
0x1801d597a  mov     edx, 2594287h; unsigned int
0x1801d597f  mov     ecx, eax; int
0x1801d5981  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1801d5986  int     3; Trap to Debugger
0x1801d5987  mov     [rsp+150h+var_E0], r14
0x1801d598c  mov     rax, [rbx]
0x1801d598f  mov     [rsp+150h+var_118], r14
0x1801d5994  mov     [rsp+150h+var_120], r14
0x1801d5999  lea     rcx, [rsp+150h+var_E0]
0x1801d599e  mov     [rsp+150h+var_128], rcx
0x1801d59a3  mov     [rsp+150h+var_130], r15
0x1801d59a8  xor     r9d, r9d
0x1801d59ab  xor     r8d, r8d
0x1801d59ae  mov     rdx, [rsp+150h+var_F8]
0x1801d59b3  mov     rcx, rbx
0x1801d59b6  mov     rax, [rax+40h]
0x1801d59ba  call    cs:__guard_dispatch_icall_fptr
0x1801d59c0  test    eax, eax
0x1801d59c2  jns     short loc_1801D59D1
0x1801d59c4  mov     edx, 2594288h; unsigned int
0x1801d59c9  mov     ecx, eax; int
0x1801d59cb  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1801d59d0  int     3; Trap to Debugger
0x1801d59d1  cmp     rsi, [rsp+150h+var_E0]
0x1801d59d6  jz      short loc_1801D59EB
0x1801d59d8  mov     edx, 2594289h; unsigned int
0x1801d59dd  mov     ecx, 80004005h; int
0x1801d59e2  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1801d59e7  nop
0x1801d59e8  jmp     short $+2
0x1801d59ea  nop
0x1801d59eb  mov     rcx, [rsp+150h+var_F8]
0x1801d59f0  test    rcx, rcx
0x1801d59f3  jz      short loc_1801D5A10
0x1801d59f5  mov     rax, [rcx]
0x1801d59f8  mov     rax, [rax+10h]
0x1801d59fc  call    cs:__guard_dispatch_icall_fptr
0x1801d5a02  nop
0x1801d5a03  nop     dword ptr [rax+00h]
0x1801d5a07  nop     word ptr [rax+rax+00000000h]
0x1801d5a10  test    rbx, rbx
0x1801d5a13  jz      short loc_1801D5A26
0x1801d5a15  mov     rax, [rbx]
0x1801d5a18  mov     rcx, rbx
0x1801d5a1b  mov     rax, [rax+10h]
0x1801d5a1f  call    cs:__guard_dispatch_icall_fptr
0x1801d5a25  nop
0x1801d5a26  lea     rcx, [rsp+150h+var_F0]
0x1801d5a2b  call    ??1?$shared_ptr@UIModelData@OSpectre@@@std@@QEAA@XZ; std::shared_ptr<OSpectre::IModelData>::~shared_ptr<OSpectre::IModelData>(void)
0x1801d5a30  lea     rcx, [rbp+50h+var_C8]
0x1801d5a34  call    ??1?$shared_ptr@UIModelData@OSpectre@@@std@@QEAA@XZ; std::shared_ptr<OSpectre::IModelData>::~shared_ptr<OSpectre::IModelData>(void)
0x1801d5a39  mov     rcx, [rbp+50h+var_30]
0x1801d5a3d  xor     rcx, rsp; StackCookie
0x1801d5a40  call    __security_check_cookie
0x1801d5a45  mov     rbx, [rsp+150h+arg_18]
0x1801d5a4d  add     rsp, 130h
0x1801d5a54  pop     r15
0x1801d5a56  pop     r14
0x1801d5a58  pop     rdi
0x1801d5a59  pop     rsi
0x1801d5a5a  pop     rbp
0x1801d5a5b  retn
```
