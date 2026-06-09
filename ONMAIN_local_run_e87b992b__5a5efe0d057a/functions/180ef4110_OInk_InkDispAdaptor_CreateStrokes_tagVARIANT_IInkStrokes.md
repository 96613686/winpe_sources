# OInk::InkDispAdaptor::CreateStrokes(tagVARIANT,IInkStrokes * *)

- ea: `0x180ef4110`
- end: `0x180ef4407`
- name: `?CreateStrokes@InkDispAdaptor@OInk@@UEAAJUtagVARIANT@@PEAPEAUIInkStrokes@@@Z`
- size: `759`
- prototype: `__int64 __fastcall(OInk::InkDispAdaptor *__hidden this, struct tagVARIANT *__struct_ptr, struct IInkStrokes **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18002fcf4`
- `0x180078ec0`
- `0x18008ee00`
- `0x1802e5190`
- `0x18044bc4c`
- `0x1804815b0`
- `0x180b3c644`
- `0x180ef4110`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180ef41bc`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180ef41bc`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180ef4217`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180ef4217`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180ef41d8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180ef41d8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180ef418d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180ef418d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180ef41ab`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180ef41ed`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180ef422c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180ef4245`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180ef4312`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180ef41ab`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180ef41ed`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180ef422c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180ef4245`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180ef4312`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180ef419c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180ef419c`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x180ef433d`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x180ef433d`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180ef432a`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x180ef432a`

## pseudocode

```c
__int64 __fastcall OInk::InkDispAdaptor::CreateStrokes(
        unsigned __int64 this,
        struct tagVARIANT *a2,
        struct IInkStrokes **a3)
{
  SAFEARRAY *parray; // rbx
  HRESULT LBound; // edi
  HRESULT UBound; // ebx
  _QWORD *v9; // r13
  unsigned __int64 v10; // r12
  LONG v11; // edi
  __int64 v12; // rsi
  unsigned __int64 i; // rbx
  _QWORD *v14; // rax
  int v15; // eax
  __int64 v16; // rax
  unsigned __int64 v17; // rsi
  struct IInkStrokes *v18; // rax
  struct IInkStrokes *v19; // rdi
  struct IInkStrokes *v20; // rbx
  struct IInkStrokesVtbl *lpVtbl; // rcx
  void *ppvData[2]; // [rsp+20h] [rbp-30h] BYREF
  __int128 v23; // [rsp+30h] [rbp-20h] BYREF
  __int64 v24; // [rsp+40h] [rbp-10h]
  LONG plUbound; // [rsp+A0h] [rbp+50h] BYREF
  LONG plLbound; // [rsp+A8h] [rbp+58h] BYREF

  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  if ( a2->vt )
  {
    if ( a2->vt != 8195 )
      return 2147942487LL;
  }
  if ( !*(_QWORD *)(this + 16) )
    return 2147500037LL;
  v23 = 0;
  v24 = 0;
  if ( a2->vt != 8195 )
    goto LABEL_38;
  parray = a2->parray;
  ppvData[0] = parray;
  ppvData[1] = 0;
  if ( parray && SafeArrayAccessData(parray, &ppvData[1]) < 0 )
  {
    MsoShipAssertTagProc(4024273);
    SafeArrayUnaccessData(parray);
    *(_OWORD *)ppvData = 0;
  }
  if ( SafeArrayGetDim(parray) != 1 )
    goto LABEL_21;
  plLbound = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(parray, 1u, &plLbound);
  if ( LBound >= 0 )
  {
    UBound = SafeArrayGetUBound(parray, 1u, &plUbound);
    if ( UBound < 0 )
    {
      if ( ppvData[0] )
        SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
LABEL_24:
      *(_OWORD *)ppvData = 0;
LABEL_25:
      std::vector<MsoCF::CIRef<Jot::IFolderProxy>>::~vector<MsoCF::CIRef<Jot::IFolderProxy>>(&v23);
      return (unsigned int)UBound;
    }
    if ( plLbound > plUbound )
    {
LABEL_21:
      if ( ppvData[0] )
        SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
      UBound = -2147024809;
      goto LABEL_24;
    }
    v9 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(this + 16) + 32LL))(*(_QWORD *)(this + 16));
    v10 = (__int64)(v9[1] - *v9) >> 3;
    v11 = plLbound;
    if ( plLbound <= plUbound )
    {
      v12 = 4LL * plLbound;
      do
      {
        for ( i = 0; i < v10; ++i )
        {
          v14 = (_QWORD *)std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](v9, i);
          v15 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 40LL))(*v14);
          if ( v15 == *(_DWORD *)((char *)ppvData[1] + v12) )
          {
            v16 = std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](v9, i);
            if ( *((_QWORD *)&v23 + 1) == v24 )
            {
              std::vector<MsoCF::CIRef<Jot::IFileProxy>>::_Emplace_reallocate<MsoCF::CIRef<Jot::IFileProxy> const &>(
                &v23,
                *((_QWORD *)&v23 + 1),
                v16);
            }
            else
            {
              MsoCF::CIPtr<OneNoteJscomApiImpl::IPageContentInstance,OneNoteJscomApiImpl::IPageContentInstance>::CIPtr<OneNoteJscomApiImpl::IPageContentInstance,OneNoteJscomApiImpl::IPageContentInstance>(
                *((_QWORD *)&v23 + 1),
                v16);
              *((_QWORD *)&v23 + 1) += 8LL;
            }
            break;
          }
        }
        ++v11;
        v12 += 4;
      }
      while ( v11 <= plUbound );
    }
    if ( ppvData[0] )
      SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
LABEL_38:
    v17 = this & -(__int64)(this != 8);
    v18 = (struct IInkStrokes *)Mso::Memory::AllocateEx((Mso::Memory *)0x38, 0, (unsigned int)a3);
    v19 = v18;
    if ( !v18 )
    {
      CrashWithRecoveryOnOOM(0x1F65259Du);
      __debugbreak();
    }
    Mso::UnknownObject<Jot::IFluidFrameViewer,>::UnknownObject<Jot::IFluidFrameViewer,>(v18);
    v19->lpVtbl = (struct IInkStrokesVtbl *)&OInk::InkStrokesAdaptor::`vftable'{for `OInk::IInkStrokesAdaptor'};
    v20 = v19 + 1;
    v19[1].lpVtbl = (struct IInkStrokesVtbl *)&OInk::InkStrokesAdaptor::`vftable'{for `IInkStrokes'};
    v19[3].lpVtbl = 0;
    v19[4].lpVtbl = 0;
    v19[5].lpVtbl = 0;
    v19[6].lpVtbl = 0;
    if ( v17 )
    {
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v17 + 8LL))(this & -(__int64)(this != 8));
      lpVtbl = v19[3].lpVtbl;
      v19[3].lpVtbl = (struct IInkStrokesVtbl *)v17;
      if ( lpVtbl )
        (*((void (__fastcall **)(struct IInkStrokesVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
      std::vector<MsoCF::CIPtr<OInk::IInkStroke2,OInk::IInkStroke2>>::operator=(&v19[4], &v23);
    }
    if ( v19 != (struct IInkStrokes *)-8LL )
    {
      ((void (__fastcall *)(struct IInkStrokes *))v20->lpVtbl->AddRef)(&v19[1]);
      ((void (__fastcall *)(struct IInkStrokes *))v20->lpVtbl->Release)(&v19[1]);
    }
    *a3 = v20;
    UBound = v20 == 0 ? 0x8007000E : 0;
    goto LABEL_25;
  }
  if ( ppvData[0] )
    SafeArrayUnaccessData((SAFEARRAY *)ppvData[0]);
  *(_OWORD *)ppvData = 0;
  std::vector<MsoCF::CIRef<Jot::IFolderProxy>>::~vector<MsoCF::CIRef<Jot::IFolderProxy>>(&v23);
  return (unsigned int)LBound;
}

```

## disassembly

```asm
0x180ef4110  mov     [rsp-38h+arg_0], rbx
0x180ef4115  push    rbp
0x180ef4116  push    rsi
0x180ef4117  push    rdi
0x180ef4118  push    r12
0x180ef411a  push    r13
0x180ef411c  push    r14
0x180ef411e  push    r15
0x180ef4120  mov     rbp, rsp
0x180ef4123  sub     rsp, 50h
0x180ef4127  mov     r15, r8
0x180ef412a  mov     r14, rcx
0x180ef412d  xor     r12d, r12d
0x180ef4130  test    r8, r8
0x180ef4133  jz      loc_180EF43EA
0x180ef4139  mov     [r8], r12
0x180ef413c  mov     eax, 2003h
0x180ef4141  cmp     [rdx], r12w
0x180ef4145  jz      short loc_180EF4150
0x180ef4147  cmp     [rdx], ax
0x180ef414a  jnz     loc_180EF43EA
0x180ef4150  cmp     [rcx+10h], r12
0x180ef4154  jnz     short loc_180EF4160
0x180ef4156  mov     eax, 80004005h
0x180ef415b  jmp     loc_180EF43EF
0x180ef4160  xorps   xmm0, xmm0
0x180ef4163  movdqu  [rbp+var_20], xmm0
0x180ef4168  mov     [rbp+var_10], r12
0x180ef416c  cmp     [rdx], ax
0x180ef416f  jnz     loc_180EF4318
0x180ef4175  mov     rbx, [rdx+8]
0x180ef4179  mov     [rbp+ppvData], rbx
0x180ef417d  mov     [rbp+ppvData+8], r12
0x180ef4181  test    rbx, rbx
0x180ef4184  jz      short loc_180EF41B9
0x180ef4186  lea     rdx, [rbp+ppvData+8]; ppvData
0x180ef418a  mov     rcx, rbx; psa
0x180ef418d  call    cs:__imp_SafeArrayAccessData
0x180ef4193  test    eax, eax
0x180ef4195  jns     short loc_180EF41B9
0x180ef4197  mov     ecx, 3D67D1h
0x180ef419c  call    cs:__imp_MsoShipAssertTagProc
0x180ef41a2  mov     rcx, [rbp+ppvData]; psa
0x180ef41a6  test    rcx, rcx
0x180ef41a9  jz      short loc_180EF41B1
0x180ef41ab  call    cs:__imp_SafeArrayUnaccessData
0x180ef41b1  xorps   xmm0, xmm0
0x180ef41b4  movdqu  xmmword ptr [rbp+ppvData], xmm0
0x180ef41b9  mov     rcx, rbx; psa
0x180ef41bc  call    cs:__imp_SafeArrayGetDim
0x180ef41c2  cmp     eax, 1
0x180ef41c5  jnz     short loc_180EF423C
0x180ef41c7  mov     [rbp+plLbound], r12d
0x180ef41cb  mov     [rbp+plUbound], r12d
0x180ef41cf  lea     r8, [rbp+plLbound]; plLbound
0x180ef41d3  mov     edx, eax; nDim
0x180ef41d5  mov     rcx, rbx; psa
0x180ef41d8  call    cs:__imp_SafeArrayGetLBound
0x180ef41de  mov     edi, eax
0x180ef41e0  test    eax, eax
0x180ef41e2  jns     short loc_180EF420B
0x180ef41e4  mov     rcx, [rbp+ppvData]; psa
0x180ef41e8  test    rcx, rcx
0x180ef41eb  jz      short loc_180EF41F3
0x180ef41ed  call    cs:__imp_SafeArrayUnaccessData
0x180ef41f3  xorps   xmm0, xmm0
0x180ef41f6  movdqu  xmmword ptr [rbp+ppvData], xmm0
0x180ef41fb  lea     rcx, [rbp+var_20]
0x180ef41ff  call    ??1?$vector@V?$CIRef@UIFolderProxy@Jot@@@MsoCF@@V?$allocator@V?$CIRef@UIFolderProxy@Jot@@@MsoCF@@@std@@@std@@QEAA@XZ; std::vector<MsoCF::CIRef<Jot::IFolderProxy>>::~vector<MsoCF::CIRef<Jot::IFolderProxy>>(void)
0x180ef4204  mov     eax, edi
0x180ef4206  jmp     loc_180EF43EF
0x180ef420b  lea     r8, [rbp+plUbound]; plUbound
0x180ef420f  mov     edx, 1; nDim
0x180ef4214  mov     rcx, rbx; psa
0x180ef4217  call    cs:__imp_SafeArrayGetUBound
0x180ef421d  mov     ebx, eax
0x180ef421f  test    eax, eax
0x180ef4221  jns     short loc_180EF4234
0x180ef4223  mov     rcx, [rbp+ppvData]; psa
0x180ef4227  test    rcx, rcx
0x180ef422a  jz      short loc_180EF4250
0x180ef422c  call    cs:__imp_SafeArrayUnaccessData
0x180ef4232  jmp     short loc_180EF4250
0x180ef4234  mov     eax, [rbp+plUbound]
0x180ef4237  cmp     [rbp+plLbound], eax
0x180ef423a  jle     short loc_180EF4268
0x180ef423c  mov     rcx, [rbp+ppvData]; psa
0x180ef4240  test    rcx, rcx
0x180ef4243  jz      short loc_180EF424B
0x180ef4245  call    cs:__imp_SafeArrayUnaccessData
0x180ef424b  mov     ebx, 80070057h
0x180ef4250  xorps   xmm0, xmm0
0x180ef4253  movdqu  xmmword ptr [rbp+ppvData], xmm0
0x180ef4258  lea     rcx, [rbp+var_20]
0x180ef425c  call    ??1?$vector@V?$CIRef@UIFolderProxy@Jot@@@MsoCF@@V?$allocator@V?$CIRef@UIFolderProxy@Jot@@@MsoCF@@@std@@@std@@QEAA@XZ; std::vector<MsoCF::CIRef<Jot::IFolderProxy>>::~vector<MsoCF::CIRef<Jot::IFolderProxy>>(void)
0x180ef4261  mov     eax, ebx
0x180ef4263  jmp     loc_180EF43EF
0x180ef4268  mov     rcx, [r14+10h]
0x180ef426c  mov     rax, [rcx]
0x180ef426f  mov     rax, [rax+20h]
0x180ef4273  call    cs:__guard_dispatch_icall_fptr
0x180ef4279  mov     r13, rax
0x180ef427c  mov     r12, [rax+8]
0x180ef4280  sub     r12, [rax]
0x180ef4283  sar     r12, 3
0x180ef4287  movsxd  rdi, [rbp+plLbound]
0x180ef428b  cmp     edi, [rbp+plUbound]
0x180ef428e  jg      short loc_180EF4306
0x180ef4290  lea     rsi, ds:0[rdi*4]
0x180ef4298  xor     ebx, ebx
0x180ef429a  cmp     rbx, r12
0x180ef429d  jnb     short loc_180EF42FB
0x180ef429f  mov     rdx, rbx
0x180ef42a2  mov     rcx, r13
0x180ef42a5  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x180ef42aa  mov     rcx, [rax]
0x180ef42ad  mov     rax, [rcx]
0x180ef42b0  mov     rax, [rax+28h]
0x180ef42b4  call    cs:__guard_dispatch_icall_fptr
0x180ef42ba  mov     rcx, [rbp+ppvData+8]
0x180ef42be  cmp     eax, [rsi+rcx]
0x180ef42c1  jz      short loc_180EF42C8
0x180ef42c3  inc     rbx
0x180ef42c6  jmp     short loc_180EF429A
0x180ef42c8  mov     rdx, rbx
0x180ef42cb  mov     rcx, r13
0x180ef42ce  call    ??A?$vector@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@@std@@@std@@QEAAAEAV?$CIPtr@UIViewElement@Jot@@U12@@MsoCF@@_K@Z; std::vector<MsoCF::CIPtr<Jot::IViewElement,Jot::IViewElement>>::operator[](unsigned __int64)
0x180ef42d3  mov     rcx, qword ptr [rbp+var_20+8]
0x180ef42d7  cmp     rcx, [rbp+var_10]
0x180ef42db  jz      short loc_180EF42EC
0x180ef42dd  mov     rdx, rax
0x180ef42e0  call    ??0?$CIPtr@UIPageContentInstance@OneNoteJscomApiImpl@@U12@@MsoCF@@QEAA@AEBV01@@Z; MsoCF::CIPtr<OneNoteJscomApiImpl::IPageContentInstance,OneNoteJscomApiImpl::IPageContentInstance>::CIPtr<OneNoteJscomApiImpl::IPageContentInstance,OneNoteJscomApiImpl::IPageContentInstance>(MsoCF::CIPtr<OneNoteJscomApiImpl::IPageContentInstance,OneNoteJscomApiImpl::IPageContentInstance> const &)
0x180ef42e5  add     qword ptr [rbp+var_20+8], 8
0x180ef42ea  jmp     short loc_180EF42FB
0x180ef42ec  mov     r8, rax
0x180ef42ef  mov     rdx, rcx
0x180ef42f2  lea     rcx, [rbp+var_20]
0x180ef42f6  call    ??$_Emplace_reallocate@AEBV?$CIRef@UIFileProxy@Jot@@@MsoCF@@@?$vector@V?$CIRef@UIFileProxy@Jot@@@MsoCF@@V?$allocator@V?$CIRef@UIFileProxy@Jot@@@MsoCF@@@std@@@std@@AEAAPEAV?$CIRef@UIFileProxy@Jot@@@MsoCF@@QEAV23@AEBV23@@Z; std::vector<MsoCF::CIRef<Jot::IFileProxy>>::_Emplace_reallocate<MsoCF::CIRef<Jot::IFileProxy> const &>(MsoCF::CIRef<Jot::IFileProxy> * const,MsoCF::CIRef<Jot::IFileProxy> const &)
0x180ef42fb  inc     edi
0x180ef42fd  add     rsi, 4
0x180ef4301  cmp     edi, [rbp+plUbound]
0x180ef4304  jle     short loc_180EF4298
0x180ef4306  mov     rcx, [rbp+ppvData]; psa
0x180ef430a  xor     r12d, r12d
0x180ef430d  test    rcx, rcx
0x180ef4310  jz      short loc_180EF4318
0x180ef4312  call    cs:__imp_SafeArrayUnaccessData
0x180ef4318  lea     rax, [r14-8]
0x180ef431c  neg     rax
0x180ef431f  sbb     rsi, rsi
0x180ef4322  and     rsi, r14
0x180ef4325  xor     edx, edx
0x180ef4327  lea     ecx, [rdx+38h]
0x180ef432a  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x180ef4330  mov     rdi, rax
0x180ef4333  test    rax, rax
0x180ef4336  jnz     short loc_180EF4344
0x180ef4338  mov     ecx, 1F65259Dh
0x180ef433d  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x180ef4343  int     3; Trap to Debugger
0x180ef4344  mov     rcx, rdi
0x180ef4347  call    ??$?0$$V@?$UnknownObject@UIFluidFrameViewer@Jot@@$$V@Mso@@IEAA@XZ; Mso::UnknownObject<Jot::IFluidFrameViewer,>::UnknownObject<Jot::IFluidFrameViewer,>(void)
0x180ef434c  lea     rcx, ??_7InkStrokesAdaptor@OInk@@6BIInkStrokesAdaptor@1@@; const OInk::InkStrokesAdaptor::`vftable'{for `OInk::IInkStrokesAdaptor'}
0x180ef4353  mov     [rdi], rcx
0x180ef4356  lea     rbx, [rdi+8]
0x180ef435a  lea     rax, ??_7InkStrokesAdaptor@OInk@@6BIInkStrokes@@@; const OInk::InkStrokesAdaptor::`vftable'{for `IInkStrokes'}
0x180ef4361  mov     [rbx], rax
0x180ef4364  mov     [rdi+18h], r12
0x180ef4368  mov     [rdi+20h], r12
0x180ef436c  mov     [rdi+28h], r12
0x180ef4370  mov     [rdi+30h], r12
0x180ef4374  test    rsi, rsi
0x180ef4377  jz      short loc_180EF43B0
0x180ef4379  mov     rax, [rsi]
0x180ef437c  mov     rcx, rsi
0x180ef437f  mov     rax, [rax+8]
0x180ef4383  call    cs:__guard_dispatch_icall_fptr
0x180ef4389  mov     rcx, [rdi+18h]
0x180ef438d  mov     [rdi+18h], rsi
0x180ef4391  test    rcx, rcx
0x180ef4394  jz      short loc_180EF43A3
0x180ef4396  mov     rax, [rcx]
0x180ef4399  mov     rax, [rax+10h]
0x180ef439d  call    cs:__guard_dispatch_icall_fptr
0x180ef43a3  lea     rdx, [rbp+var_20]
0x180ef43a7  lea     rcx, [rdi+20h]
0x180ef43ab  call    ??4?$vector@V?$CIPtr@UIInkStroke2@OInk@@U12@@MsoCF@@V?$allocator@V?$CIPtr@UIInkStroke2@OInk@@U12@@MsoCF@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<MsoCF::CIPtr<OInk::IInkStroke2,OInk::IInkStroke2>>::operator=(std::vector<MsoCF::CIPtr<OInk::IInkStroke2,OInk::IInkStroke2>> const &)
0x180ef43b0  test    rbx, rbx
0x180ef43b3  jz      short loc_180EF43D5
0x180ef43b5  mov     rax, [rbx]
0x180ef43b8  mov     rcx, rbx
0x180ef43bb  mov     rax, [rax+8]
0x180ef43bf  call    cs:__guard_dispatch_icall_fptr
0x180ef43c5  mov     rax, [rbx]
0x180ef43c8  mov     rcx, rbx
0x180ef43cb  mov     rax, [rax+10h]
0x180ef43cf  call    cs:__guard_dispatch_icall_fptr
0x180ef43d5  mov     [r15], rbx
0x180ef43d8  neg     rbx
0x180ef43db  sbb     ebx, ebx
0x180ef43dd  not     ebx
0x180ef43df  and     ebx, 8007000Eh
0x180ef43e5  jmp     loc_180EF4258
0x180ef43ea  mov     eax, 80070057h
0x180ef43ef  mov     rbx, [rsp+50h+arg_0]
0x180ef43f7  add     rsp, 50h
0x180ef43fb  pop     r15
0x180ef43fd  pop     r14
0x180ef43ff  pop     r13
0x180ef4401  pop     r12
0x180ef4403  pop     rdi
0x180ef4404  pop     rsi
0x180ef4405  pop     rbp
0x180ef4406  retn
```
