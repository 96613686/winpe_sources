# Gfx::Model3DScene::Write(IStream &,OSpectre::ExportDataFormat)

- ea: `0x1801d9360`
- end: `0x1801d96dc`
- name: `?Write@Model3DScene@Gfx@@UEBAXAEAUIStream@@W4ExportDataFormat@OSpectre@@@Z`
- size: `892`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000aef0`
- `0x1800578b0`
- `0x180057e70`
- `0x18005a4a0`
- `0x180092a58`
- `0x180096050`
- `0x1800b0c24`
- `0x1800dc860`
- `0x1800dcec0`
- `0x1800fa77c`
- `0x1801d9360`

## import_xrefs

- `KERNEL32!DecodePointer` at `0x1801d9411`
- `KERNEL32!DecodePointer` at `0x1801d9428`
- `KERNEL32!DecodePointer` at `0x1801d9411`
- `KERNEL32!DecodePointer` at `0x1801d9428`
- `Mso20Win32Client!__imp_?CreateByteStreamOnBuffer@Stream@Mso@@YA?AV?$TCntPtr@UIByteStream@@@2@PEBEKPEAUIMsoMemHeap@@@Z` at `0x1801d9590`
- `Mso20Win32Client!__imp_?CreateByteStreamOnBuffer@Stream@Mso@@YA?AV?$TCntPtr@UIByteStream@@@2@PEBEKPEAUIMsoMemHeap@@@Z` at `0x1801d9590`
- `Mso20Win32Client!__imp_?MsoHrGetIBSFromIStreamEx@@YAJPEAUIStream@@K_K1PEAPEAUIByteStream@@@Z` at `0x1801d95f0`
- `Mso20Win32Client!__imp_?MsoHrGetIBSFromIStreamEx@@YAJPEAUIStream@@K_K1PEAPEAUIByteStream@@@Z` at `0x1801d95f0`

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
        if ( DecodePointer(qword_180522980) )
        {
          v23 = 0;
          v9 = (__int64 (__fastcall *)(__int64))DecodePointer(qword_180522980);
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
0x1801d9360  mov     [rsp-8+arg_18], rbx
0x1801d9365  push    rbp
0x1801d9366  push    rsi
0x1801d9367  push    rdi
0x1801d9368  push    r14
0x1801d936a  push    r15
0x1801d936c  lea     rbp, [rsp-30h]
0x1801d9371  sub     rsp, 130h
0x1801d9378  mov     rax, cs:__security_cookie
0x1801d937f  xor     rax, rsp
0x1801d9382  mov     [rbp+50h+var_30], rax
0x1801d9386  mov     esi, r8d
0x1801d9389  mov     rdi, rdx
0x1801d938c  mov     rbx, rcx
0x1801d938f  xor     r14d, r14d
0x1801d9392  cmp     [rcx+20h], r14
0x1801d9396  jnz     short loc_1801D93A5
0x1801d9398  mov     rax, [rcx]
0x1801d939b  mov     rax, [rax+60h]
0x1801d939f  call    cs:__guard_dispatch_icall_fptr
0x1801d93a5  cmp     [rbx+20h], r14
0x1801d93a9  jnz     short loc_1801D93BB
0x1801d93ab  mov     edx, 2594286h; unsigned int
0x1801d93b0  mov     ecx, 80004005h; int
0x1801d93b5  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1801d93ba  int     3; Trap to Debugger
0x1801d93bb  mov     rcx, cs:?s_pInstance@?$TSingleton@VModel3DFactory@Gfx@@@Ofc@@0PEAVModel3DFactory@Gfx@@EA; Gfx::Model3DFactory * Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance
0x1801d93c2  mov     r15d, 1
0x1801d93c8  cmp     rcx, r15
0x1801d93cb  ja      loc_1801D9481
0x1801d93d1  mov     rax, cs:?s_pInstance@?$TSingleton@VModel3DFactory@Gfx@@@Ofc@@0PEAVModel3DFactory@Gfx@@EA; Gfx::Model3DFactory * Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance
0x1801d93d8  cmp     rax, r15
0x1801d93db  ja      loc_1801D947A
0x1801d93e1  xor     eax, eax
0x1801d93e3  lock cmpxchg cs:?s_pInstance@?$TSingleton@VModel3DFactory@Gfx@@@Ofc@@0PEAVModel3DFactory@Gfx@@EA, r15; Gfx::Model3DFactory * Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance
0x1801d93ec  jnz     short loc_1801D9466
0x1801d93ee  lea     rax, ?s_pInstance@?$TSingleton@VModel3DFactory@Gfx@@@Ofc@@0PEAVModel3DFactory@Gfx@@EA; Gfx::Model3DFactory * Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance
0x1801d93f5  mov     [rsp+150h+var_D8], rax
0x1801d93fa  mov     [rbp+50h+var_D0], r14
0x1801d93fe  lea     rcx, ?Shutdown@?$TSingleton@VModel3DFactory@Gfx@@@Ofc@@SAXXZ; Ptr
0x1801d9405  call    ?AtExit@Ofc@@YAXP6AXXZ_N@Z; Ofc::AtExit(void (*)(void),bool)
0x1801d940a  mov     rcx, cs:qword_180522980; Ptr
0x1801d9411  call    cs:__imp_DecodePointer
0x1801d9417  test    rax, rax
0x1801d941a  jz      short loc_1801D9441
0x1801d941c  mov     [rsp+150h+var_100], r14
0x1801d9421  mov     rcx, cs:qword_180522980; Ptr
0x1801d9428  call    cs:__imp_DecodePointer
0x1801d942e  mov     ecx, 8
0x1801d9433  call    cs:__guard_dispatch_icall_fptr
0x1801d9439  mov     rcx, rax
0x1801d943c  mov     [rax], r14
0x1801d943f  jmp     short loc_1801D9451
0x1801d9441  mov     ecx, 8; this
0x1801d9446  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1801d944b  mov     rcx, rax
0x1801d944e  mov     [rax], r14
0x1801d9451  mov     [rbp+50h+var_D0], rcx
0x1801d9455  mov     rax, r15
0x1801d9458  lock cmpxchg cs:?s_pInstance@?$TSingleton@VModel3DFactory@Gfx@@@Ofc@@0PEAVModel3DFactory@Gfx@@EA, rcx; Gfx::Model3DFactory * Ofc::TSingleton<Gfx::Model3DFactory>::s_pInstance
0x1801d9461  jmp     loc_1801D93D1
0x1801d9466  mov     [rsp+150h+var_100], r14
0x1801d946b  lea     rcx, [rsp+150h+var_100]
0x1801d9470  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1801d9475  jmp     loc_1801D93D1
0x1801d947a  mov     rcx, cs:?s_pInstance@?$TSingleton@VModel3DFactory@Gfx@@@Ofc@@0PEAVModel3DFactory@Gfx@@EA; this
0x1801d9481  call    ?GetSpectreFactory@Model3DFactory@Gfx@@QEAAAEAUIFactory@OSpectre@@XZ; Gfx::Model3DFactory::GetSpectreFactory(void)
0x1801d9486  mov     r8, rax
0x1801d9489  mov     rcx, [rax]
0x1801d948c  mov     rax, [rcx+30h]
0x1801d9490  lea     rdx, [rbp+50h+var_C8]
0x1801d9494  mov     rcx, r8
0x1801d9497  call    cs:__guard_dispatch_icall_fptr
0x1801d949d  nop
0x1801d949e  mov     rcx, [rbp+50h+var_C8]
0x1801d94a2  mov     rax, [rcx]
0x1801d94a5  xor     edx, edx
0x1801d94a7  mov     rax, [rax+38h]
0x1801d94ab  call    cs:__guard_dispatch_icall_fptr
0x1801d94b1  mov     rcx, [rbp+50h+var_C8]
0x1801d94b5  mov     rax, [rcx]
0x1801d94b8  mov     r8, [rbx+20h]
0x1801d94bc  lea     rdx, [rsp+150h+var_F0]
0x1801d94c1  mov     rax, [rax+30h]
0x1801d94c5  call    cs:__guard_dispatch_icall_fptr
0x1801d94cb  nop
0x1801d94cc  mov     rcx, [rbp+50h+var_C8]
0x1801d94d0  mov     rax, [rcx]
0x1801d94d3  mov     [rbp+50h+var_38], r14
0x1801d94d7  mov     [rbp+50h+var_78], r14
0x1801d94db  mov     [rsp+150h+var_110], r14b
0x1801d94e0  lea     rdx, [rbp+50h+var_70]
0x1801d94e4  mov     [rsp+150h+var_118], rdx
0x1801d94e9  lea     rdx, [rbp+50h+var_B0]
0x1801d94ed  mov     [rsp+150h+var_120], rdx
0x1801d94f2  mov     dword ptr [rsp+150h+var_128], esi
0x1801d94f6  mov     dword ptr [rsp+150h+var_130], 6
0x1801d94fe  xor     r9d, r9d
0x1801d9501  lea     r8, [rsp+150h+var_F0]
0x1801d9506  lea     rdx, [rsp+150h+var_D8]
0x1801d950b  mov     rax, [rax+28h]
0x1801d950f  call    cs:__guard_dispatch_icall_fptr
0x1801d9515  mov     rdx, rax
0x1801d9518  lea     rcx, [rsp+150h+var_F0]
0x1801d951d  call    ??4?$shared_ptr@UIRenderer@OSpectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<OSpectre::IRenderer>::operator=(std::shared_ptr<OSpectre::IRenderer> &&)
0x1801d9522  lea     rcx, [rsp+150h+var_D8]
0x1801d9527  call    ??1?$shared_ptr@UIModelData@OSpectre@@@std@@QEAA@XZ; std::shared_ptr<OSpectre::IModelData>::~shared_ptr<OSpectre::IModelData>(void)
0x1801d952c  lea     rcx, [rbp+50h+var_B0]
0x1801d9530  call    ??1?$_Func_class@_NM@std@@QEAA@XZ; std::_Func_class<bool,float>::~_Func_class<bool,float>(void)
0x1801d9535  lea     rcx, [rbp+50h+var_70]
0x1801d9539  call    ??1?$_Func_class@_NM@std@@QEAA@XZ; std::_Func_class<bool,float>::~_Func_class<bool,float>(void)
0x1801d953e  xchg    ax, ax
0x1801d9540  mov     rcx, [rsp+150h+var_F0]
0x1801d9545  mov     rax, [rcx]
0x1801d9548  mov     rax, [rax+10h]
0x1801d954c  call    cs:__guard_dispatch_icall_fptr
0x1801d9552  mov     rsi, rax
0x1801d9555  mov     rdx, [rsp+150h+var_F0]
0x1801d955a  mov     rcx, [rdx]
0x1801d955d  mov     rax, [rcx+10h]
0x1801d9561  mov     rcx, rdx
0x1801d9564  call    cs:__guard_dispatch_icall_fptr
0x1801d956a  mov     rbx, rax
0x1801d956d  mov     rdx, [rsp+150h+var_F0]
0x1801d9572  mov     rcx, [rdx]
0x1801d9575  mov     rax, [rcx+8]
0x1801d9579  mov     rcx, rdx
0x1801d957c  call    cs:__guard_dispatch_icall_fptr
0x1801d9582  xor     r9d, r9d
0x1801d9585  mov     r8d, ebx
0x1801d9588  mov     rdx, rax
0x1801d958b  lea     rcx, [rsp+150h+var_100]
0x1801d9590  call    cs:__imp_?CreateByteStreamOnBuffer@Stream@Mso@@YA?AV?$TCntPtr@UIByteStream@@@2@PEBEKPEAUIMsoMemHeap@@@Z; Mso::Stream::CreateByteStreamOnBuffer(uchar const *,ulong,IMsoMemHeap *)
0x1801d9596  mov     rbx, [rax]
0x1801d9599  mov     [rsp+150h+var_D8], rbx
0x1801d959e  test    rbx, rbx
0x1801d95a1  jz      short loc_1801D95B4
0x1801d95a3  mov     rax, [rbx]
0x1801d95a6  mov     rcx, rbx
0x1801d95a9  mov     rax, [rax+8]
0x1801d95ad  call    cs:__guard_dispatch_icall_fptr
0x1801d95b3  nop
0x1801d95b4  mov     rcx, [rsp+150h+var_100]
0x1801d95b9  test    rcx, rcx
0x1801d95bc  jz      short loc_1801D95D0
0x1801d95be  mov     [rsp+150h+var_100], r14
0x1801d95c3  mov     rax, [rcx]
0x1801d95c6  mov     rax, [rax+10h]
0x1801d95ca  call    cs:__guard_dispatch_icall_fptr
0x1801d95d0  mov     [rsp+150h+var_F8], r14
0x1801d95d5  lea     rax, [rsp+150h+var_F8]
0x1801d95da  mov     [rsp+150h+var_130], rax
0x1801d95df  or      r15, 0FFFFFFFFFFFFFFFFh
0x1801d95e3  mov     r9, r15
0x1801d95e6  xor     r8d, r8d
0x1801d95e9  lea     edx, [r15+11h]
0x1801d95ed  mov     rcx, rdi
0x1801d95f0  call    cs:__imp_?MsoHrGetIBSFromIStreamEx@@YAJPEAUIStream@@K_K1PEAPEAUIByteStream@@@Z; MsoHrGetIBSFromIStreamEx(IStream *,ulong,unsigned __int64,unsigned __int64,IByteStream * *)
0x1801d95f6  test    eax, eax
0x1801d95f8  jns     short loc_1801D9607
0x1801d95fa  mov     edx, 2594287h; unsigned int
0x1801d95ff  mov     ecx, eax; int
0x1801d9601  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1801d9606  int     3; Trap to Debugger
0x1801d9607  mov     [rsp+150h+var_E0], r14
0x1801d960c  mov     rax, [rbx]
0x1801d960f  mov     [rsp+150h+var_118], r14
0x1801d9614  mov     [rsp+150h+var_120], r14
0x1801d9619  lea     rcx, [rsp+150h+var_E0]
0x1801d961e  mov     [rsp+150h+var_128], rcx
0x1801d9623  mov     [rsp+150h+var_130], r15
0x1801d9628  xor     r9d, r9d
0x1801d962b  xor     r8d, r8d
0x1801d962e  mov     rdx, [rsp+150h+var_F8]
0x1801d9633  mov     rcx, rbx
0x1801d9636  mov     rax, [rax+40h]
0x1801d963a  call    cs:__guard_dispatch_icall_fptr
0x1801d9640  test    eax, eax
0x1801d9642  jns     short loc_1801D9651
0x1801d9644  mov     edx, 2594288h; unsigned int
0x1801d9649  mov     ecx, eax; int
0x1801d964b  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1801d9650  int     3; Trap to Debugger
0x1801d9651  cmp     rsi, [rsp+150h+var_E0]
0x1801d9656  jz      short loc_1801D966B
0x1801d9658  mov     edx, 2594289h; unsigned int
0x1801d965d  mov     ecx, 80004005h; int
0x1801d9662  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x1801d9667  nop
0x1801d9668  jmp     short $+2
0x1801d966a  nop
0x1801d966b  mov     rcx, [rsp+150h+var_F8]
0x1801d9670  test    rcx, rcx
0x1801d9673  jz      short loc_1801D9690
0x1801d9675  mov     rax, [rcx]
0x1801d9678  mov     rax, [rax+10h]
0x1801d967c  call    cs:__guard_dispatch_icall_fptr
0x1801d9682  nop
0x1801d9683  nop     dword ptr [rax+00h]
0x1801d9687  nop     word ptr [rax+rax+00000000h]
0x1801d9690  test    rbx, rbx
0x1801d9693  jz      short loc_1801D96A6
0x1801d9695  mov     rax, [rbx]
0x1801d9698  mov     rcx, rbx
0x1801d969b  mov     rax, [rax+10h]
0x1801d969f  call    cs:__guard_dispatch_icall_fptr
0x1801d96a5  nop
0x1801d96a6  lea     rcx, [rsp+150h+var_F0]
0x1801d96ab  call    ??1?$shared_ptr@UIModelData@OSpectre@@@std@@QEAA@XZ; std::shared_ptr<OSpectre::IModelData>::~shared_ptr<OSpectre::IModelData>(void)
0x1801d96b0  lea     rcx, [rbp+50h+var_C8]
0x1801d96b4  call    ??1?$shared_ptr@UIModelData@OSpectre@@@std@@QEAA@XZ; std::shared_ptr<OSpectre::IModelData>::~shared_ptr<OSpectre::IModelData>(void)
0x1801d96b9  mov     rcx, [rbp+50h+var_30]
0x1801d96bd  xor     rcx, rsp; StackCookie
0x1801d96c0  call    __security_check_cookie
0x1801d96c5  mov     rbx, [rsp+150h+arg_18]
0x1801d96cd  add     rsp, 130h
0x1801d96d4  pop     r15
0x1801d96d6  pop     r14
0x1801d96d8  pop     rdi
0x1801d96d9  pop     rsi
0x1801d96da  pop     rbp
0x1801d96db  retn
```
