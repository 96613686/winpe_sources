# Dr::LocalAsyncIAPerformer::OnUpdateStrokesCache(ulong,long const *)

- ea: `0x18082b9d0`
- end: `0x18082bdbf`
- name: `?OnUpdateStrokesCache@LocalAsyncIAPerformer@Dr@@UEAAJKPEBJ@Z`
- size: `1007`
- prototype: `__int64 __fastcall(Dr::LocalAsyncIAPerformer *__hidden this, unsigned int, const int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000fa38`
- `0x18002a690`
- `0x180276a40`
- `0x180279050`
- `0x18048121c`
- `0x1804b46a4`
- `0x1806bc6a8`
- `0x1806d19bc`
- `0x18082b9d0`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18082bcbc`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18082bcbc`
- `OLEAUT32!__imp_VariantInit` at `0x18082baf5`
- `OLEAUT32!__imp_VariantInit` at `0x18082bb32`
- `OLEAUT32!__imp_VariantInit` at `0x18082baf5`
- `OLEAUT32!__imp_VariantInit` at `0x18082bb32`
- `OLEAUT32!__imp_VariantClear` at `0x18082bccb`
- `OLEAUT32!__imp_VariantClear` at `0x18082bd18`
- `OLEAUT32!__imp_VariantClear` at `0x18082bccb`
- `OLEAUT32!__imp_VariantClear` at `0x18082bd18`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18082bb7d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18082bb9a`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18082bb7d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18082bb9a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18082bc9b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18082bcad`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18082bc9b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18082bcad`
- `ole32!CLSIDFromString` at `0x18082bbfb`
- `ole32!CLSIDFromString` at `0x18082bbfb`

## pseudocode

```c
__int64 __fastcall Dr::LocalAsyncIAPerformer::OnUpdateStrokesCache(
        Dr::LocalAsyncIAPerformer *this,
        unsigned int a2,
        const int *a3)
{
  unsigned int v3; // eax
  Dr::LocalAsyncIAPerformer *v4; // r12
  HRESULT StrokeTimestamp; // esi
  __int64 v6; // r13
  unsigned int v7; // r15d
  struct Ofc::CProxyPtrImpl ***ValGrow; // rax
  struct Art::IInkDrawing *v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rbx
  unsigned int v12; // r14d
  struct tagPOINT InkOffsetWrtHostBoundsInHm; // rdi
  Dr *v15; // r14
  __int64 v16; // r12
  unsigned __int64 *v17; // r8
  unsigned int v18; // r8d
  unsigned __int64 v19; // r15
  unsigned __int128 v20; // rax
  CLSID *v21; // rbx
  __int64 v22; // rsi
  HRESULT v23; // eax
  unsigned int v24; // edx
  LONG y; // r8d
  __int64 v26; // rcx
  unsigned int v27; // [rsp+40h] [rbp-B8h] BYREF
  struct IInkStrokeDisp v28; // [rsp+48h] [rbp-B0h] BYREF
  void *ppvData; // [rsp+50h] [rbp-A8h] BYREF
  Dr *v30; // [rsp+58h] [rbp-A0h] BYREF
  unsigned int v31; // [rsp+60h] [rbp-98h]
  __int64 v32; // [rsp+68h] [rbp-90h] BYREF
  __int64 v33; // [rsp+70h] [rbp-88h] BYREF
  struct Ofc::CProxyPtrImpl *v34; // [rsp+78h] [rbp-80h] BYREF
  struct tagPOINT v35; // [rsp+80h] [rbp-78h]
  VARIANTARG v36; // [rsp+88h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-58h] BYREF
  CLSID *v38; // [rsp+B8h] [rbp-40h]
  const int *v41; // [rsp+110h] [rbp+18h]
  unsigned int v42; // [rsp+118h] [rbp+20h] BYREF

  v41 = a3;
  v3 = a2;
  v4 = this;
  StrokeTimestamp = 0;
  v6 = 0;
  while ( StrokeTimestamp >= 0 && (unsigned int)v6 < v3 )
  {
    v7 = a3[v6];
    ValGrow = (struct Ofc::CProxyPtrImpl ***)Ofc::TMap<Dr::InkInputSurfaceBase::LayerId,Ofc::TCntPtr<Dr::InkInputSurfaceBase::InkInputLayerInfo>>::GetValGrow(
                                               (Dr::LocalAsyncIAPerformer *)((char *)v4 + 112),
                                               v7);
    v34 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(**ValGrow);
    v11 = *(_QWORD *)(v10 + 8);
    v12 = *(_DWORD *)(v10 + 16);
    if ( !v11 )
    {
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v34);
      return 2147500037LL;
    }
    InkOffsetWrtHostBoundsInHm = Dr::InkDocAnalyzerHelpers::GetInkOffsetWrtHostBoundsInHm(
                                   *(Dr::InkDocAnalyzerHelpers **)(v10 + 8),
                                   v9);
    v35 = InkOffsetWrtHostBoundsInHm;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 72LL))(v11, &v33);
    v32 = 0;
    v30 = 0;
    StrokeTimestamp = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 56LL))(v33, &v32);
    if ( StrokeTimestamp < 0
      || (StrokeTimestamp = (*(__int64 (__fastcall **)(__int64, _QWORD, Dr **))(*(_QWORD *)v32 + 96LL))(v32, v12, &v30),
          StrokeTimestamp < 0) )
    {
      v15 = v30;
    }
    else
    {
      v15 = v30;
      v27 = v7;
      v16 = *((_QWORD *)v4 - 4);
      if ( v30 && v16 )
      {
        VariantInit(&pvarg);
        StrokeTimestamp = (*(__int64 (__fastcall **)(Dr *, _QWORD, __int64, VARIANTARG *))(*(_QWORD *)v15 + 240LL))(
                            v15,
                            0,
                            0xFFFFFFFFLL,
                            &pvarg);
        if ( StrokeTimestamp >= 0 )
        {
          VariantInit(&v36);
          StrokeTimestamp = (*(__int64 (__fastcall **)(Dr *, VARIANTARG *))(*(_QWORD *)v15 + 144LL))(v15, &v36);
          if ( StrokeTimestamp >= 0 )
          {
            ppvData = 0;
            v28.lpVtbl = 0;
            StrokeTimestamp = SafeArrayAccessData(pvarg.parray, &ppvData);
            if ( StrokeTimestamp >= 0 )
            {
              StrokeTimestamp = SafeArrayAccessData(v36.parray, (void **)&v28.lpVtbl);
              if ( StrokeTimestamp >= 0 )
              {
                v19 = *(unsigned int *)(v36.llVal + 24);
                v31 = *(_DWORD *)(pvarg.llVal + 24);
                v20 = v19 * (unsigned __int128)0x10u;
                if ( !is_mul_ok(v19, 0x10u) )
                  *(_QWORD *)&v20 = -1;
                v21 = (CLSID *)Mso::Memory::Throw::AllocateEx(
                                 (Mso::Memory::Throw *)v20,
                                 *((unsigned __int64 *)&v20 + 1),
                                 v18);
                v38 = v21;
                v22 = 0;
                do
                {
                  if ( (unsigned int)v22 >= (unsigned int)v19 )
                    break;
                  v23 = CLSIDFromString(*((LPCOLESTR *)&v28.lpVtbl->QueryInterface + v22), &v21[(unsigned int)v22]);
                  v22 = (unsigned int)(v22 + 1);
                }
                while ( v23 >= 0 );
                v42 = v31 / (unsigned int)v19;
                v24 = 0;
                if ( v31 / (unsigned int)v19 )
                {
                  y = v35.y;
                  do
                  {
                    v26 = (unsigned int)v19 * v24;
                    *((_DWORD *)ppvData + v26) += InkOffsetWrtHostBoundsInHm.x;
                    *((_DWORD *)ppvData + (unsigned int)(v26 + 1)) += y;
                    ++v24;
                  }
                  while ( v24 < v42 );
                }
                StrokeTimestamp = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, _QWORD, CLSID *, unsigned int *, void *))(*(_QWORD *)v16 + 216LL))(
                                    v16,
                                    1,
                                    &v27,
                                    (unsigned int)v19,
                                    v21,
                                    &v42,
                                    ppvData);
                operator delete(v21);
              }
            }
            if ( SafeArrayUnaccessData(v36.parray) < 0 || SafeArrayUnaccessData(pvarg.parray) < 0 )
              MsoShipAssertTagProc(963851372);
          }
          VariantClear(&v36);
        }
        v28.lpVtbl = 0;
        if ( StrokeTimestamp >= 0 )
        {
          StrokeTimestamp = Dr::GetStrokeTimestamp(v15, &v28, v17);
          if ( StrokeTimestamp >= 0 )
            StrokeTimestamp = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IInkStrokeDispVtbl *))(*(_QWORD *)v16 + 464LL))(
                                v16,
                                v27,
                                v28.lpVtbl);
        }
        VariantClear(&pvarg);
        v15 = v30;
      }
      else
      {
        StrokeTimestamp = -2147024809;
      }
      v4 = this;
    }
    if ( v15 )
      (*(void (__fastcall **)(Dr *))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v34);
    v6 = (unsigned int)(v6 + 1);
    v3 = a2;
    a3 = v41;
  }
  return (unsigned int)StrokeTimestamp;
}

```

## disassembly

```asm
0x18082b9d0  mov     [rsp+arg_10], r8
0x18082b9d5  mov     [rsp+arg_8], edx
0x18082b9d9  mov     [rsp+arg_0], rcx
0x18082b9de  push    rbx
0x18082b9df  push    rsi
0x18082b9e0  push    rdi
0x18082b9e1  push    r12
0x18082b9e3  push    r13
0x18082b9e5  push    r14
0x18082b9e7  push    r15
0x18082b9e9  sub     rsp, 0C0h
0x18082b9f0  mov     eax, edx
0x18082b9f2  mov     r12, rcx
0x18082b9f5  xor     esi, esi
0x18082b9f7  xor     r13d, r13d
0x18082b9fa  test    esi, esi
0x18082b9fc  js      loc_18082BDA1
0x18082ba02  cmp     r13d, eax
0x18082ba05  jnb     loc_18082BDA1
0x18082ba0b  mov     r15d, [r8+r13*4]
0x18082ba0f  mov     edx, r15d; unsigned __int64
0x18082ba12  lea     rcx, [r12+70h]; this
0x18082ba17  call    ?GetValGrow@?$TMap@ULayerId@InkInputSurfaceBase@Dr@@V?$TCntPtr@VInkInputLayerInfo@InkInputSurfaceBase@Dr@@@Ofc@@@Ofc@@QEAAAEAV?$TCntPtr@VInkInputLayerInfo@InkInputSurfaceBase@Dr@@@2@AEBULayerId@InkInputSurfaceBase@Dr@@@Z; Ofc::TMap<Dr::InkInputSurfaceBase::LayerId,Ofc::TCntPtr<Dr::InkInputSurfaceBase::InkInputLayerInfo>>::GetValGrow(Dr::InkInputSurfaceBase::LayerId const &)
0x18082ba1c  mov     r8, [rax]
0x18082ba1f  mov     rcx, [r8]; struct Ofc::CProxyPtrImpl *
0x18082ba22  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18082ba27  mov     [rsp+0F8h+var_80], rax
0x18082ba2c  mov     rbx, [r8+8]
0x18082ba30  mov     r14d, [r8+10h]
0x18082ba34  test    rbx, rbx
0x18082ba37  jnz     short loc_18082BA4D
0x18082ba39  lea     rcx, [rsp+0F8h+var_80]; struct Ofc::CProxyPtrImpl **
0x18082ba3e  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18082ba43  mov     eax, 80004005h
0x18082ba48  jmp     loc_18082BDAC
0x18082ba4d  mov     rcx, rbx; this
0x18082ba50  call    ?GetInkOffsetWrtHostBoundsInHm@InkDocAnalyzerHelpers@Dr@@YA?AUtagPOINT@@AEAUIInkDrawing@Art@@@Z; Dr::InkDocAnalyzerHelpers::GetInkOffsetWrtHostBoundsInHm(Art::IInkDrawing &)
0x18082ba55  mov     rdi, rax
0x18082ba58  mov     [rsp+0F8h+var_78], rax
0x18082ba60  mov     rax, [rbx]
0x18082ba63  lea     rdx, [rsp+0F8h+var_88]
0x18082ba68  mov     rcx, rbx
0x18082ba6b  mov     rax, [rax+48h]
0x18082ba6f  call    cs:__guard_dispatch_icall_fptr
0x18082ba75  mov     [rsp+0F8h+var_90], 0
0x18082ba7e  mov     [rsp+0F8h+var_A0], 0
0x18082ba87  mov     rcx, [rsp+0F8h+var_88]
0x18082ba8c  mov     rax, [rcx]
0x18082ba8f  lea     rdx, [rsp+0F8h+var_90]
0x18082ba94  mov     rax, [rax+38h]
0x18082ba98  call    cs:__guard_dispatch_icall_fptr
0x18082ba9e  mov     esi, eax
0x18082baa0  test    eax, eax
0x18082baa2  js      loc_18082BD34
0x18082baa8  mov     rcx, [rsp+0F8h+var_90]
0x18082baad  mov     rax, [rcx]
0x18082bab0  lea     r8, [rsp+0F8h+var_A0]
0x18082bab5  mov     edx, r14d
0x18082bab8  mov     rax, [rax+60h]
0x18082babc  call    cs:__guard_dispatch_icall_fptr
0x18082bac2  mov     esi, eax
0x18082bac4  test    eax, eax
0x18082bac6  js      loc_18082BD34
0x18082bacc  mov     r14, [rsp+0F8h+var_A0]
0x18082bad1  mov     [rsp+0F8h+var_B8], r15d
0x18082bad6  mov     r12, [r12-20h]
0x18082badb  test    r14, r14
0x18082bade  jz      loc_18082BD25
0x18082bae4  test    r12, r12
0x18082bae7  jz      loc_18082BD25
0x18082baed  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x18082baf5  call    cs:__imp_VariantInit
0x18082bafb  nop
0x18082bafc  mov     rax, [r14]
0x18082baff  lea     r9, [rsp+0F8h+pvarg]
0x18082bb07  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18082bb0b  mov     r8d, ebx
0x18082bb0e  xor     edx, edx
0x18082bb10  mov     rcx, r14
0x18082bb13  mov     rax, [rax+0F0h]
0x18082bb1a  call    cs:__guard_dispatch_icall_fptr
0x18082bb20  mov     esi, eax
0x18082bb22  test    eax, eax
0x18082bb24  js      loc_18082BCD1
0x18082bb2a  lea     rcx, [rsp+0F8h+var_70]; pvarg
0x18082bb32  call    cs:__imp_VariantInit
0x18082bb38  nop
0x18082bb39  mov     rax, [r14]
0x18082bb3c  lea     rdx, [rsp+0F8h+var_70]
0x18082bb44  mov     rcx, r14
0x18082bb47  mov     rax, [rax+90h]
0x18082bb4e  call    cs:__guard_dispatch_icall_fptr
0x18082bb54  mov     esi, eax
0x18082bb56  test    eax, eax
0x18082bb58  js      loc_18082BCC3
0x18082bb5e  mov     [rsp+0F8h+ppvData], 0
0x18082bb67  mov     [rsp+0F8h+var_B0.lpVtbl], 0
0x18082bb70  lea     rdx, [rsp+0F8h+ppvData]; ppvData
0x18082bb75  mov     rcx, qword ptr [rsp+0F8h+pvarg+8]; psa
0x18082bb7d  call    cs:__imp_SafeArrayAccessData
0x18082bb83  mov     esi, eax
0x18082bb85  test    eax, eax
0x18082bb87  js      loc_18082BC93
0x18082bb8d  lea     rdx, [rsp+0F8h+var_B0]; ppvData
0x18082bb92  mov     rcx, qword ptr [rsp+0F8h+var_70+8]; psa
0x18082bb9a  call    cs:__imp_SafeArrayAccessData
0x18082bba0  mov     esi, eax
0x18082bba2  test    eax, eax
0x18082bba4  js      loc_18082BC93
0x18082bbaa  mov     rax, qword ptr [rsp+0F8h+var_70+8]
0x18082bbb2  mov     r15d, [rax+18h]
0x18082bbb6  mov     rax, qword ptr [rsp+0F8h+pvarg+8]
0x18082bbbe  mov     eax, [rax+18h]
0x18082bbc1  mov     [rsp+0F8h+var_98], eax
0x18082bbc5  lea     eax, [rbx+11h]
0x18082bbc8  mul     r15
0x18082bbcb  cmovb   rax, rbx
0x18082bbcf  mov     rcx, rax; this
0x18082bbd2  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18082bbd7  mov     rbx, rax
0x18082bbda  mov     [rsp+0F8h+var_40], rax
0x18082bbe2  xor     esi, esi
0x18082bbe4  cmp     esi, r15d
0x18082bbe7  jnb     short loc_18082BC07
0x18082bbe9  mov     edx, esi
0x18082bbeb  mov     rax, [rsp+0F8h+var_B0.lpVtbl]
0x18082bbf0  mov     rcx, [rax+rsi*8]; lpsz
0x18082bbf4  shl     rdx, 4
0x18082bbf8  add     rdx, rbx; pclsid
0x18082bbfb  call    cs:__imp_CLSIDFromString
0x18082bc01  inc     esi
0x18082bc03  test    eax, eax
0x18082bc05  jns     short loc_18082BBE4
0x18082bc07  xor     edx, edx
0x18082bc09  mov     eax, [rsp+0F8h+var_98]
0x18082bc0d  div     r15d
0x18082bc10  mov     [rsp+0F8h+arg_18], eax
0x18082bc17  xor     edx, edx
0x18082bc19  test    eax, eax
0x18082bc1b  jz      short loc_18082BC49
0x18082bc1d  mov     r8d, dword ptr [rsp+0F8h+var_78+4]
0x18082bc25  mov     ecx, edx
0x18082bc27  imul    ecx, r15d
0x18082bc2b  mov     rax, [rsp+0F8h+ppvData]
0x18082bc30  add     [rax+rcx*4], edi
0x18082bc33  inc     ecx
0x18082bc35  mov     rax, [rsp+0F8h+ppvData]
0x18082bc3a  add     [rax+rcx*4], r8d
0x18082bc3e  inc     edx
0x18082bc40  cmp     edx, [rsp+0F8h+arg_18]
0x18082bc47  jb      short loc_18082BC25
0x18082bc49  mov     rax, [r12]
0x18082bc4d  mov     r10, [rax+0D8h]
0x18082bc54  mov     rax, [rsp+0F8h+ppvData]
0x18082bc59  mov     [rsp+0F8h+var_C8], rax
0x18082bc5e  lea     rax, [rsp+0F8h+arg_18]
0x18082bc66  mov     [rsp+0F8h+var_D0], rax
0x18082bc6b  mov     [rsp+0F8h+var_D8], rbx
0x18082bc70  mov     r9d, r15d
0x18082bc73  lea     r8, [rsp+0F8h+var_B8]
0x18082bc78  mov     edx, 1
0x18082bc7d  mov     rcx, r12
0x18082bc80  mov     rax, r10
0x18082bc83  call    cs:__guard_dispatch_icall_fptr
0x18082bc89  mov     esi, eax
0x18082bc8b  mov     rcx, rbx; void *
0x18082bc8e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18082bc93  mov     rcx, qword ptr [rsp+0F8h+var_70+8]; psa
0x18082bc9b  call    cs:__imp_SafeArrayUnaccessData
0x18082bca1  test    eax, eax
0x18082bca3  js      short loc_18082BCB7
0x18082bca5  mov     rcx, qword ptr [rsp+0F8h+pvarg+8]; psa
0x18082bcad  call    cs:__imp_SafeArrayUnaccessData
0x18082bcb3  test    eax, eax
0x18082bcb5  jns     short loc_18082BCC3
0x18082bcb7  mov     ecx, 3973346Ch
0x18082bcbc  call    cs:__imp_MsoShipAssertTagProc
0x18082bcc2  nop
0x18082bcc3  lea     rcx, [rsp+0F8h+var_70]; pvarg
0x18082bccb  call    cs:__imp_VariantClear
0x18082bcd1  mov     [rsp+0F8h+var_B0.lpVtbl], 0
0x18082bcda  test    esi, esi
0x18082bcdc  js      short loc_18082BD10
0x18082bcde  lea     rdx, [rsp+0F8h+var_B0]; struct IInkStrokeDisp *
0x18082bce3  mov     rcx, r14; this
0x18082bce6  call    ?GetStrokeTimestamp@Dr@@YAJPEAUIInkStrokeDisp@@AEA_K@Z; Dr::GetStrokeTimestamp(IInkStrokeDisp *,unsigned __int64 &)
0x18082bceb  mov     esi, eax
0x18082bced  test    eax, eax
0x18082bcef  js      short loc_18082BD10
0x18082bcf1  mov     rax, [r12]
0x18082bcf5  mov     r8, [rsp+0F8h+var_B0.lpVtbl]
0x18082bcfa  mov     edx, [rsp+0F8h+var_B8]
0x18082bcfe  mov     rcx, r12
0x18082bd01  mov     rax, [rax+1D0h]
0x18082bd08  call    cs:__guard_dispatch_icall_fptr
0x18082bd0e  mov     esi, eax
0x18082bd10  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x18082bd18  call    cs:__imp_VariantClear
0x18082bd1e  mov     r14, [rsp+0F8h+var_A0]
0x18082bd23  jmp     short loc_18082BD2A
0x18082bd25  mov     esi, 80070057h
0x18082bd2a  mov     r12, [rsp+0F8h+arg_0]
0x18082bd32  jmp     short loc_18082BD39
0x18082bd34  mov     r14, [rsp+0F8h+var_A0]
0x18082bd39  test    r14, r14
0x18082bd3c  jz      short loc_18082BD50
0x18082bd3e  mov     rax, [r14]
0x18082bd41  mov     rcx, r14
0x18082bd44  mov     rax, [rax+10h]
0x18082bd48  call    cs:__guard_dispatch_icall_fptr
0x18082bd4e  nop
0x18082bd4f  nop
0x18082bd50  mov     rcx, [rsp+0F8h+var_90]
0x18082bd55  test    rcx, rcx
0x18082bd58  jz      short loc_18082BD68
0x18082bd5a  mov     rax, [rcx]
0x18082bd5d  mov     rax, [rax+10h]
0x18082bd61  call    cs:__guard_dispatch_icall_fptr
0x18082bd67  nop
0x18082bd68  mov     rcx, [rsp+0F8h+var_88]
0x18082bd6d  test    rcx, rcx
0x18082bd70  jz      short loc_18082BD80
0x18082bd72  mov     rax, [rcx]
0x18082bd75  mov     rax, [rax+10h]
0x18082bd79  call    cs:__guard_dispatch_icall_fptr
0x18082bd7f  nop
0x18082bd80  lea     rcx, [rsp+0F8h+var_80]; struct Ofc::CProxyPtrImpl **
0x18082bd85  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18082bd8a  inc     r13d
0x18082bd8d  mov     eax, [rsp+0F8h+arg_8]
0x18082bd94  mov     r8, [rsp+0F8h+arg_10]
0x18082bd9c  jmp     loc_18082B9FA
0x18082bda1  jmp     short loc_18082BDAA
0x18082bda3  mov     esi, [rsp+0F8h+arg_18]
0x18082bdaa  mov     eax, esi
0x18082bdac  add     rsp, 0C0h
0x18082bdb3  pop     r15
0x18082bdb5  pop     r14
0x18082bdb7  pop     r13
0x18082bdb9  pop     r12
0x18082bdbb  pop     rdi
0x18082bdbc  pop     rsi
0x18082bdbd  pop     rbx
0x18082bdbe  retn
```
