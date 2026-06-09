# PhotoDocument::SaveToFile(Base::Path const &,_GUID &)

- ea: `0x18005fb28`
- end: `0x18005ff41`
- name: `?SaveToFile@PhotoDocument@@AEAAXAEBVPath@Base@@AEAU_GUID@@@Z`
- size: `1049`
- prototype: `void __fastcall(PhotoDocument *__hidden this, const struct Path *, struct _GUID *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18005fa80`

## callees

- `0x180004908`
- `0x18000b2b4`
- `0x18000cb74`
- `0x18001f670`
- `0x18002e5a8`
- `0x180030b10`
- `0x180037c14`
- `0x1800389a0`
- `0x180039560`
- `0x1800395b0`
- `0x18005e18c`
- `0x18005e840`
- `0x18005ef0c`
- `0x18005fb28`
- `0x1800603b4`
- `0x180060820`
- `0x180080010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005fbc0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005fbc0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fe1e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fef0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fe1e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fef0`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x18005fbfa`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x18005fbfa`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fba2`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fc06`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fc43`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fc73`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fcb4`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fce5`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fd5d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fd88`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fdef`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fdfd`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fea1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005ff2d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005ff39`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fba2`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fc06`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fc43`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fc73`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fcb4`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fce5`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fd5d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fd88`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fdef`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fdfd`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005fea1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005ff2d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18005ff39`
- `PhotoBase!?Increment@Sqm@@YAXKK@Z` at `0x18005fec3`
- `PhotoBase!?Increment@Sqm@@YAXKK@Z` at `0x18005fec3`
- `PhotoBase!?StartStreamTimer@Sqm@@YAXKK@Z` at `0x18005fb5d`
- `PhotoBase!?StartStreamTimer@Sqm@@YAXKK@Z` at `0x18005fb5d`
- `PhotoBase!?StopStreamTimer@Sqm@@YAXKK@Z` at `0x18005ff21`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall PhotoDocument::SaveToFile(PhotoDocument *this, LPCWSTR *a2, struct _GUID *a3)
{
  const struct _GUID *v6; // r8
  int v7; // eax
  int v8; // edx
  int v9; // r15d
  HRESULT v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edx
  int v14; // eax
  int v15; // edx
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // eax
  int v19; // edx
  int v20; // eax
  int v21; // edx
  unsigned int i; // edi
  bool IsMultiPageNavigationAllowed; // al
  char *v24; // rcx
  __int64 v25; // rax
  PhotoDocument *v26; // rcx
  __int64 TransformOptionFromRotation; // r8
  int v28; // eax
  int v29; // edx
  int v30; // eax
  int v31; // edx
  __int64 v32; // rdi
  int v33; // eax
  int v34; // edx
  unsigned int v35; // r8d
  unsigned int j; // r14d
  __int64 v37; // rax
  PhotoDocumentFrame *v38; // rax
  __int64 v39; // rax
  int v40; // edx
  __int64 v41; // rcx
  unsigned int v42; // r8d
  __int64 v43; // [rsp+30h] [rbp-A8h] BYREF
  int v44; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+40h] [rbp-98h] BYREF
  BSTR v46; // [rsp+48h] [rbp-90h]
  IStream *ppstm; // [rsp+50h] [rbp-88h] BYREF
  __int64 v48; // [rsp+58h] [rbp-80h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-78h] BYREF
  _QWORD v50[2]; // [rsp+68h] [rbp-70h] BYREF
  _BYTE v51[32]; // [rsp+78h] [rbp-60h] BYREF
  __int64 v52; // [rsp+98h] [rbp-40h] BYREF
  int v54; // [rsp+F8h] [rbp+20h] BYREF

  v50[1] = 2376;
  Sqm::StartStreamTimer((Sqm *)0x948, 0, (unsigned int)a3);
  WPP::PrivateAutoPerfTrace::PrivateAutoPerfTrace(
    (WPP::PrivateAutoPerfTrace *)v51,
    *((_QWORD *)WPP_GLOBAL_Control + 7),
    v6,
    0xAu);
  v46 = 0;
  try
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 48LL))(*((_QWORD *)this + 42));
    if ( v7 < 0 )
      Base::Throw((Base *)(unsigned int)v7, v8);
    Base::Path::Path((Base::Path *)v50, v46);
    v9 = _o__wcsicmp(*a2, v50[0]);
    PhotoDocument::EnsureImagingFactory(this);
    ppstm = 0;
    v10 = SHCreateStreamOnFileEx(*a2, 0x40u, 0, 0, 0, &ppstm);
    if ( v10 < 0 )
      Base::Throw((Base *)(unsigned int)v10, v11);
    v45 = 0;
    v12 = (*(__int64 (__fastcall **)(_QWORD, IStream *, _QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 25) + 32LL))(
            *((_QWORD *)this + 25),
            ppstm,
            0,
            0,
            &v45);
    if ( v12 < 0 )
      Base::Throw((Base *)(unsigned int)v12, v13);
    v54 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v45 + 96LL))(v45, &v54);
    if ( v14 < 0 )
      Base::Throw((Base *)(unsigned int)v14, v15);
    if ( v54 == *((_QWORD *)this + 38) )
    {
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, *a2);
      v43 = 0;
      v18 = ATL::CComCreator<ATL::CComObject<PhotoDocumentSaveWorker>>::CreateInstance(v17, v16, &v43);
      if ( v18 < 0 )
        Base::Throw((Base *)(unsigned int)v18, v19);
      v20 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR, BSTR, struct _GUID *))(*(_QWORD *)v43 + 64LL))(
              v43,
              v45,
              v46,
              bstrString,
              a3);
      if ( v20 < 0 )
        Base::Throw((Base *)(unsigned int)v20, v21);
      ATL::CComPtrBase<IWICBitmapDecoder>::Release(&v45);
      for ( i = 0; (unsigned __int64)i < *((_QWORD *)this + 38); ++i )
      {
        IsMultiPageNavigationAllowed = PhotoDocument::IsMultiPageNavigationAllowed(this);
        v24 = (char *)this + 296;
        if ( IsMultiPageNavigationAllowed )
          v25 = ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(v24, i);
        else
          v25 = ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(v24, 0);
        TransformOptionFromRotation = (unsigned int)PhotoDocument::GetTransformOptionFromRotation(
                                                      v26,
                                                      *(_DWORD *)(v25 + 44) - *(_DWORD *)(v25 + 48));
        v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v43 + 80LL))(
                v43,
                i,
                TransformOptionFromRotation);
        if ( v28 < 0 )
          Base::Throw((Base *)(unsigned int)v28, v29);
      }
      PhotoDocument::SetSaveStatus(this, -2147483638);
      v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 24LL))(v43);
      if ( v30 < 0 )
        Base::Throw((Base *)(unsigned int)v30, v31);
      v32 = v43;
      v48 = v43;
      if ( v43 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 8LL))(v43);
      if ( v32 )
      {
        PhotoWorkerMessagePump::Pump((PhotoWorkerMessagePump *)&v48);
        ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v48);
        v44 = 0;
        v33 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 56LL))(v43, &v44);
        if ( v33 < 0 )
          Base::Throw((Base *)(unsigned int)v33, v34);
        if ( v44 < 0 )
          Base::Throw((Base *)(unsigned int)v44, v34);
        PhotoDocument::SetSaveStatus(this, 0);
        ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v43);
        SysFreeString(bstrString);
        if ( !v9 )
        {
          for ( j = 0; (unsigned __int64)j < *((_QWORD *)this + 38); ++j )
          {
            v37 = ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(
                    (char *)this + 296,
                    j);
            if ( *(_DWORD *)(v37 + 44) != *(_DWORD *)(v37 + 48)
              && !*(_BYTE *)(ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(
                               (char *)this + 296,
                               j)
                           + 40) )
            {
              v38 = (PhotoDocumentFrame *)ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(
                                            (char *)this + 296,
                                            j);
              PhotoDocumentFrame::Initialize(v38);
            }
            if ( *(_BYTE *)(ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(
                              (char *)this + 296,
                              j)
                          + 40) )
            {
              v39 = ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(
                      (char *)this + 296,
                      j);
              v41 = v39;
              if ( !*(_BYTE *)(v39 + 40) )
                Base::Throw((Base *)0x80004005LL, v40);
              *(_DWORD *)(v41 + 48) = *(_DWORD *)(v39 + 44);
              *(_BYTE *)(v41 + 42) = 0;
            }
          }
        }
        Sqm::Increment((Sqm *)0x64B, 1u, v35);
        goto LABEL_49;
      }
      Base::Throw((Base *)0x80004003LL, v31);
    }
    Base::Throw((Base *)0x80004005LL, v15);
    JUMPOUT(0x18005FF3FLL);
  }
  catch ( Base::Exception v52 )
  {
    PhotoDocument::SetSaveStatus(this, -2147467259);
    throw;
  }
LABEL_49:
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v45);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppstm);
  Base::String::~String((Base::String *)v50);
  SysFreeString(v46);
  WPP::PrivateAutoPerfTrace::~PrivateAutoPerfTrace((WPP::PrivateAutoPerfTrace *)v51);
  Sqm::StopStreamTimer((Sqm *)0x948, 0, v42);
}

```

## disassembly

```asm
0x18005fb28  mov     [rsp+arg_8], rbx
0x18005fb2d  mov     [rsp+arg_0], rcx
0x18005fb32  push    rsi
0x18005fb33  push    rdi
0x18005fb34  push    r12
0x18005fb36  push    r14
0x18005fb38  push    r15
0x18005fb3a  sub     rsp, 0B0h
0x18005fb41  mov     rsi, r8
0x18005fb44  mov     rdi, rdx
0x18005fb47  mov     rbx, rcx
0x18005fb4a  mov     r14d, 948h
0x18005fb50  mov     [rsp+0D8h+var_68], r14
0x18005fb55  xor     r12d, r12d
0x18005fb58  xor     edx, edx
0x18005fb5a  mov     ecx, r14d
0x18005fb5d  call    cs:__imp_?StartStreamTimer@Sqm@@YAXKK@Z; Sqm::StartStreamTimer(ulong,ulong)
0x18005fb63  nop
0x18005fb64  lea     r9d, [r12+0Ah]; unsigned int
0x18005fb69  mov     rdx, cs:WPP_GLOBAL_Control
0x18005fb70  mov     rdx, [rdx+38h]; unsigned __int64
0x18005fb74  lea     rcx, [rsp+0D8h+var_60]; this
0x18005fb79  call    ??0PrivateAutoPerfTrace@WPP@@QEAA@_KPEBU_GUID@@K@Z; WPP::PrivateAutoPerfTrace::PrivateAutoPerfTrace(unsigned __int64,_GUID const *,ulong)
0x18005fb7e  nop
0x18005fb7f  mov     [rsp+0D8h+var_90], r12
0x18005fb84  mov     rcx, [rbx+150h]
0x18005fb8b  mov     rax, [rcx]
0x18005fb8e  lea     rdx, [rsp+0D8h+var_90]
0x18005fb93  mov     rax, [rax+30h]
0x18005fb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb9c  test    eax, eax
0x18005fb9e  jns     short loc_18005FBA8
0x18005fba0  mov     ecx, eax
0x18005fba2  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005fba8  mov     rdx, [rsp+0D8h+var_90]; unsigned __int16 *
0x18005fbad  lea     rcx, [rsp+0D8h+var_70]; this
0x18005fbb2  call    ??0Path@Base@@QEAA@PEBG@Z; Base::Path::Path(ushort const *)
0x18005fbb7  nop
0x18005fbb8  mov     rdx, [rsp+0D8h+var_70]
0x18005fbbd  mov     rcx, [rdi]
0x18005fbc0  call    cs:__imp__o__wcsicmp
0x18005fbc6  mov     r15d, eax
0x18005fbc9  mov     rcx, rbx; this
0x18005fbcc  call    ?EnsureImagingFactory@PhotoDocument@@AEAAXXZ; PhotoDocument::EnsureImagingFactory(void)
0x18005fbd1  mov     [rsp+0D8h+var_88], 0
0x18005fbda  lea     rax, [rsp+0D8h+var_88]
0x18005fbdf  mov     [rsp+0D8h+ppstm], rax; ppstm
0x18005fbe4  mov     [rsp+0D8h+pstmTemplate], 0; pstmTemplate
0x18005fbed  xor     r9d, r9d; fCreate
0x18005fbf0  xor     r8d, r8d; dwAttributes
0x18005fbf3  lea     edx, [r9+40h]; grfMode
0x18005fbf7  mov     rcx, [rdi]; pszFile
0x18005fbfa  call    cs:__imp_SHCreateStreamOnFileEx
0x18005fc00  test    eax, eax
0x18005fc02  jns     short loc_18005FC0C
0x18005fc04  mov     ecx, eax
0x18005fc06  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005fc0c  mov     [rsp+0D8h+var_98], 0
0x18005fc15  mov     rcx, [rbx+0C8h]
0x18005fc1c  mov     rax, [rcx]
0x18005fc1f  lea     rdx, [rsp+0D8h+var_98]
0x18005fc24  mov     [rsp+0D8h+pstmTemplate], rdx
0x18005fc29  xor     r9d, r9d
0x18005fc2c  xor     r8d, r8d
0x18005fc2f  mov     rdx, [rsp+0D8h+var_88]
0x18005fc34  mov     rax, [rax+20h]
0x18005fc38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc3d  test    eax, eax
0x18005fc3f  jns     short loc_18005FC49
0x18005fc41  mov     ecx, eax
0x18005fc43  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005fc49  mov     [rsp+0D8h+arg_18], 0
0x18005fc54  mov     rcx, [rsp+0D8h+var_98]
0x18005fc59  mov     rax, [rcx]
0x18005fc5c  lea     rdx, [rsp+0D8h+arg_18]
0x18005fc64  mov     rax, [rax+60h]
0x18005fc68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc6d  test    eax, eax
0x18005fc6f  jns     short loc_18005FC79
0x18005fc71  mov     ecx, eax
0x18005fc73  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005fc79  mov     eax, [rsp+0D8h+arg_18]
0x18005fc80  cmp     rax, [rbx+130h]
0x18005fc87  jnz     loc_18005FF34
0x18005fc8d  mov     rdx, [rdi]; unsigned __int16 *
0x18005fc90  lea     rcx, [rsp+0D8h+bstrString]; this
0x18005fc95  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18005fc9a  nop
0x18005fc9b  mov     [rsp+0D8h+var_A8], 0
0x18005fca4  lea     r8, [rsp+0D8h+var_A8]
0x18005fca9  call    ?CreateInstance@?$CComCreator@V?$CComObject@VPhotoDocumentSaveWorker@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<PhotoDocumentSaveWorker>>::CreateInstance(void *,_GUID const &,void * *)
0x18005fcae  test    eax, eax
0x18005fcb0  jns     short loc_18005FCBA
0x18005fcb2  mov     ecx, eax
0x18005fcb4  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005fcba  mov     rcx, [rsp+0D8h+var_A8]
0x18005fcbf  mov     rax, [rcx]
0x18005fcc2  mov     [rsp+0D8h+pstmTemplate], rsi
0x18005fcc7  mov     r9, [rsp+0D8h+bstrString]
0x18005fccc  mov     r8, [rsp+0D8h+var_90]
0x18005fcd1  mov     rdx, [rsp+0D8h+var_98]
0x18005fcd6  mov     rax, [rax+40h]
0x18005fcda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fcdf  test    eax, eax
0x18005fce1  jns     short loc_18005FCEB
0x18005fce3  mov     ecx, eax
0x18005fce5  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005fceb  lea     rcx, [rsp+0D8h+var_98]
0x18005fcf0  call    ?Release@?$CComPtrBase@UIWICBitmapDecoder@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IWICBitmapDecoder>::Release(void)
0x18005fcf5  xor     edi, edi
0x18005fcf7  mov     esi, edi
0x18005fcf9  mov     rcx, rbx; this
0x18005fcfc  cmp     rsi, [rbx+130h]
0x18005fd03  jnb     short loc_18005FD67
0x18005fd05  lea     r14, [rbx+128h]
0x18005fd0c  call    ?IsMultiPageNavigationAllowed@PhotoDocument@@AEAA_NXZ; PhotoDocument::IsMultiPageNavigationAllowed(void)
0x18005fd11  mov     rcx, r14
0x18005fd14  test    al, al
0x18005fd16  jz      short loc_18005FD2F
0x18005fd18  mov     edx, esi
0x18005fd1a  call    ?GetAt@?$CAtlArray@VPhotoDocumentFrame@@V?$CElementTraits@VPhotoDocumentFrame@@@ATL@@@ATL@@QEAAAEAVPhotoDocumentFrame@@_K@Z; ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(unsigned __int64)
0x18005fd1f  mov     edx, [rax+2Ch]
0x18005fd22  sub     edx, [rax+30h]; int
0x18005fd25  call    ?GetTransformOptionFromRotation@PhotoDocument@@AEBA?AW4WICBitmapTransformOptions@@J@Z; PhotoDocument::GetTransformOptionFromRotation(long)
0x18005fd2a  mov     r8d, eax
0x18005fd2d  jmp     short loc_18005FD44
0x18005fd2f  xor     edx, edx
0x18005fd31  call    ?GetAt@?$CAtlArray@VPhotoDocumentFrame@@V?$CElementTraits@VPhotoDocumentFrame@@@ATL@@@ATL@@QEAAAEAVPhotoDocumentFrame@@_K@Z; ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(unsigned __int64)
0x18005fd36  mov     edx, [rax+2Ch]
0x18005fd39  sub     edx, [rax+30h]; int
0x18005fd3c  call    ?GetTransformOptionFromRotation@PhotoDocument@@AEBA?AW4WICBitmapTransformOptions@@J@Z; PhotoDocument::GetTransformOptionFromRotation(long)
0x18005fd41  mov     r8d, eax
0x18005fd44  mov     rcx, [rsp+0D8h+var_A8]
0x18005fd49  mov     rax, [rcx]
0x18005fd4c  mov     edx, edi
0x18005fd4e  mov     rax, [rax+50h]
0x18005fd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd57  test    eax, eax
0x18005fd59  jns     short loc_18005FD63
0x18005fd5b  mov     ecx, eax
0x18005fd5d  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005fd63  inc     edi
0x18005fd65  jmp     short loc_18005FCF7
0x18005fd67  mov     edx, 8000000Ah; int
0x18005fd6c  call    ?SetSaveStatus@PhotoDocument@@AEAAXJ@Z; PhotoDocument::SetSaveStatus(long)
0x18005fd71  mov     rcx, [rsp+0D8h+var_A8]
0x18005fd76  mov     rax, [rcx]
0x18005fd79  mov     rax, [rax+18h]
0x18005fd7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fd82  test    eax, eax
0x18005fd84  jns     short loc_18005FD8E
0x18005fd86  mov     ecx, eax
0x18005fd88  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005fd8e  mov     rdi, [rsp+0D8h+var_A8]
0x18005fd93  mov     [rsp+0D8h+var_80], rdi
0x18005fd98  test    rdi, rdi
0x18005fd9b  jz      short loc_18005FDAD
0x18005fd9d  mov     rax, [rdi]
0x18005fda0  mov     rcx, rdi
0x18005fda3  mov     rax, [rax+8]
0x18005fda7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fdac  nop
0x18005fdad  test    rdi, rdi
0x18005fdb0  jz      loc_18005FF28
0x18005fdb6  lea     rcx, [rsp+0D8h+var_80]; this
0x18005fdbb  call    ?Pump@PhotoWorkerMessagePump@@QEAAXXZ; PhotoWorkerMessagePump::Pump(void)
0x18005fdc0  nop
0x18005fdc1  lea     rcx, [rsp+0D8h+var_80]
0x18005fdc6  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18005fdcb  mov     [rsp+0D8h+var_A0], 0
0x18005fdd3  mov     rcx, [rsp+0D8h+var_A8]
0x18005fdd8  mov     rax, [rcx]
0x18005fddb  lea     rdx, [rsp+0D8h+var_A0]
0x18005fde0  mov     rax, [rax+38h]
0x18005fde4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fde9  test    eax, eax
0x18005fdeb  jns     short loc_18005FDF5
0x18005fded  mov     ecx, eax
0x18005fdef  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005fdf5  mov     ecx, [rsp+0D8h+var_A0]
0x18005fdf9  test    ecx, ecx
0x18005fdfb  jns     short loc_18005FE03
0x18005fdfd  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005fe03  xor     edx, edx; int
0x18005fe05  mov     rcx, rbx; this
0x18005fe08  call    ?SetSaveStatus@PhotoDocument@@AEAAXJ@Z; PhotoDocument::SetSaveStatus(long)
0x18005fe0d  nop
0x18005fe0e  lea     rcx, [rsp+0D8h+var_A8]
0x18005fe13  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18005fe18  nop
0x18005fe19  mov     rcx, [rsp+0D8h+bstrString]; bstrString
0x18005fe1e  call    cs:__imp_SysFreeString
0x18005fe24  test    r15d, r15d
0x18005fe27  jnz     loc_18005FEB9
0x18005fe2d  xor     r14d, r14d
0x18005fe30  mov     edi, r14d
0x18005fe33  cmp     rdi, [rbx+130h]
0x18005fe3a  jnb     short loc_18005FEB9
0x18005fe3c  lea     rsi, [rbx+128h]
0x18005fe43  mov     edx, edi
0x18005fe45  mov     rcx, rsi
0x18005fe48  call    ?GetAt@?$CAtlArray@VPhotoDocumentFrame@@V?$CElementTraits@VPhotoDocumentFrame@@@ATL@@@ATL@@QEAAAEAVPhotoDocumentFrame@@_K@Z; ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(unsigned __int64)
0x18005fe4d  mov     ecx, [rax+30h]
0x18005fe50  cmp     [rax+2Ch], ecx
0x18005fe53  jz      short loc_18005FE77
0x18005fe55  mov     edx, edi
0x18005fe57  mov     rcx, rsi
0x18005fe5a  call    ?GetAt@?$CAtlArray@VPhotoDocumentFrame@@V?$CElementTraits@VPhotoDocumentFrame@@@ATL@@@ATL@@QEAAAEAVPhotoDocumentFrame@@_K@Z; ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(unsigned __int64)
0x18005fe5f  cmp     byte ptr [rax+28h], 0
0x18005fe63  jnz     short loc_18005FE77
0x18005fe65  mov     edx, edi
0x18005fe67  mov     rcx, rsi
0x18005fe6a  call    ?GetAt@?$CAtlArray@VPhotoDocumentFrame@@V?$CElementTraits@VPhotoDocumentFrame@@@ATL@@@ATL@@QEAAAEAVPhotoDocumentFrame@@_K@Z; ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(unsigned __int64)
0x18005fe6f  mov     rcx, rax; this
0x18005fe72  call    ?Initialize@PhotoDocumentFrame@@QEAAXXZ; PhotoDocumentFrame::Initialize(void)
0x18005fe77  mov     rdx, rdi
0x18005fe7a  mov     rcx, rsi
0x18005fe7d  call    ?GetAt@?$CAtlArray@VPhotoDocumentFrame@@V?$CElementTraits@VPhotoDocumentFrame@@@ATL@@@ATL@@QEAAAEAVPhotoDocumentFrame@@_K@Z; ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(unsigned __int64)
0x18005fe82  cmp     byte ptr [rax+28h], 0
0x18005fe86  jz      short loc_18005FEB1
0x18005fe88  mov     rdx, rdi
0x18005fe8b  mov     rcx, rsi
0x18005fe8e  call    ?GetAt@?$CAtlArray@VPhotoDocumentFrame@@V?$CElementTraits@VPhotoDocumentFrame@@@ATL@@@ATL@@QEAAAEAVPhotoDocumentFrame@@_K@Z; ATL::CAtlArray<PhotoDocumentFrame,ATL::CElementTraits<PhotoDocumentFrame>>::GetAt(unsigned __int64)
0x18005fe93  mov     rcx, rax
0x18005fe96  cmp     byte ptr [rax+28h], 0
0x18005fe9a  jnz     short loc_18005FEA7
0x18005fe9c  mov     ecx, 80004005h
0x18005fea1  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005fea7  mov     eax, [rax+2Ch]
0x18005feaa  mov     [rcx+30h], eax
0x18005fead  mov     byte ptr [rcx+2Ah], 0
0x18005feb1  inc     r14d
0x18005feb4  jmp     loc_18005FE30
0x18005feb9  mov     edx, 1
0x18005febe  mov     ecx, 64Bh
0x18005fec3  call    cs:__imp_?Increment@Sqm@@YAXKK@Z; Sqm::Increment(ulong,ulong)
0x18005fec9  nop
0x18005feca  lea     rcx, [rsp+0D8h+var_98]
0x18005fecf  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18005fed4  nop
0x18005fed5  lea     rcx, [rsp+0D8h+var_88]
0x18005feda  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18005fedf  nop
0x18005fee0  lea     rcx, [rsp+0D8h+var_70]; this
0x18005fee5  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18005feea  nop
0x18005feeb  mov     rcx, [rsp+0D8h+var_90]; bstrString
0x18005fef0  call    cs:__imp_SysFreeString
0x18005fef6  nop
0x18005fef7  lea     rcx, [rsp+0D8h+var_60]; this
0x18005fefc  call    ??1PrivateAutoPerfTrace@WPP@@UEAA@XZ; WPP::PrivateAutoPerfTrace::~PrivateAutoPerfTrace(void)
0x18005ff01  nop
0x18005ff02  mov     edx, r12d
0x18005ff05  mov     ecx, 948h
0x18005ff0a  mov     rbx, [rsp+0D8h+arg_8]
0x18005ff12  add     rsp, 0B0h
0x18005ff19  pop     r15
0x18005ff1b  pop     r14
0x18005ff1d  pop     r12
0x18005ff1f  pop     rdi
0x18005ff20  pop     rsi
0x18005ff21  jmp     cs:__imp_?StopStreamTimer@Sqm@@YAXKK@Z; Sqm::StopStreamTimer(ulong,ulong)
0x18005ff28  mov     ecx, 80004003h
0x18005ff2d  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18005ff33  nop
0x18005ff34  mov     ecx, 80004005h
0x18005ff39  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
```
