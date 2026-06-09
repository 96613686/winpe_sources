# Dr::LocalAsyncIAPerformer::OnUpdateStrokesCache(ulong,long const *)

- ea: `0x18081ed20`
- end: `0x18081f10f`
- name: `?OnUpdateStrokesCache@LocalAsyncIAPerformer@Dr@@UEAAJKPEBJ@Z`
- size: `1007`
- prototype: `__int64 __fastcall(Dr::LocalAsyncIAPerformer *__hidden this, unsigned int, const int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180033360`
- `0x180065990`
- `0x1800659a0`
- `0x180071720`
- `0x18033e9c8`
- `0x1803a30d0`
- `0x1806a51d0`
- `0x1806a57c4`
- `0x18081ed20`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18081f00c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18081f00c`
- `OLEAUT32!__imp_VariantInit` at `0x18081ee45`
- `OLEAUT32!__imp_VariantInit` at `0x18081ee82`
- `OLEAUT32!__imp_VariantInit` at `0x18081ee45`
- `OLEAUT32!__imp_VariantInit` at `0x18081ee82`
- `OLEAUT32!__imp_VariantClear` at `0x18081f01b`
- `OLEAUT32!__imp_VariantClear` at `0x18081f068`
- `OLEAUT32!__imp_VariantClear` at `0x18081f01b`
- `OLEAUT32!__imp_VariantClear` at `0x18081f068`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18081eecd`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18081eeea`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18081eecd`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18081eeea`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18081efeb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18081effd`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18081efeb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18081effd`
- `ole32!CLSIDFromString` at `0x18081ef4b`
- `ole32!CLSIDFromString` at `0x18081ef4b`

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
0x18081ed20  mov     [rsp+arg_10], r8
0x18081ed25  mov     [rsp+arg_8], edx
0x18081ed29  mov     [rsp+arg_0], rcx
0x18081ed2e  push    rbx
0x18081ed2f  push    rsi
0x18081ed30  push    rdi
0x18081ed31  push    r12
0x18081ed33  push    r13
0x18081ed35  push    r14
0x18081ed37  push    r15
0x18081ed39  sub     rsp, 0C0h
0x18081ed40  mov     eax, edx
0x18081ed42  mov     r12, rcx
0x18081ed45  xor     esi, esi
0x18081ed47  xor     r13d, r13d
0x18081ed4a  test    esi, esi
0x18081ed4c  js      loc_18081F0F1
0x18081ed52  cmp     r13d, eax
0x18081ed55  jnb     loc_18081F0F1
0x18081ed5b  mov     r15d, [r8+r13*4]
0x18081ed5f  mov     edx, r15d; unsigned __int64
0x18081ed62  lea     rcx, [r12+70h]; this
0x18081ed67  call    ?GetValGrow@?$TMap@ULayerId@InkInputSurfaceBase@Dr@@V?$TCntPtr@VInkInputLayerInfo@InkInputSurfaceBase@Dr@@@Ofc@@@Ofc@@QEAAAEAV?$TCntPtr@VInkInputLayerInfo@InkInputSurfaceBase@Dr@@@2@AEBULayerId@InkInputSurfaceBase@Dr@@@Z; Ofc::TMap<Dr::InkInputSurfaceBase::LayerId,Ofc::TCntPtr<Dr::InkInputSurfaceBase::InkInputLayerInfo>>::GetValGrow(Dr::InkInputSurfaceBase::LayerId const &)
0x18081ed6c  mov     r8, [rax]
0x18081ed6f  mov     rcx, [r8]; struct Ofc::CProxyPtrImpl *
0x18081ed72  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18081ed77  mov     [rsp+0F8h+var_80], rax
0x18081ed7c  mov     rbx, [r8+8]
0x18081ed80  mov     r14d, [r8+10h]
0x18081ed84  test    rbx, rbx
0x18081ed87  jnz     short loc_18081ED9D
0x18081ed89  lea     rcx, [rsp+0F8h+var_80]; struct Ofc::CProxyPtrImpl **
0x18081ed8e  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18081ed93  mov     eax, 80004005h
0x18081ed98  jmp     loc_18081F0FC
0x18081ed9d  mov     rcx, rbx; this
0x18081eda0  call    ?GetInkOffsetWrtHostBoundsInHm@InkDocAnalyzerHelpers@Dr@@YA?AUtagPOINT@@AEAUIInkDrawing@Art@@@Z; Dr::InkDocAnalyzerHelpers::GetInkOffsetWrtHostBoundsInHm(Art::IInkDrawing &)
0x18081eda5  mov     rdi, rax
0x18081eda8  mov     [rsp+0F8h+var_78], rax
0x18081edb0  mov     rax, [rbx]
0x18081edb3  lea     rdx, [rsp+0F8h+var_88]
0x18081edb8  mov     rcx, rbx
0x18081edbb  mov     rax, [rax+48h]
0x18081edbf  call    cs:__guard_dispatch_icall_fptr
0x18081edc5  mov     [rsp+0F8h+var_90], 0
0x18081edce  mov     [rsp+0F8h+var_A0], 0
0x18081edd7  mov     rcx, [rsp+0F8h+var_88]
0x18081eddc  mov     rax, [rcx]
0x18081eddf  lea     rdx, [rsp+0F8h+var_90]
0x18081ede4  mov     rax, [rax+38h]
0x18081ede8  call    cs:__guard_dispatch_icall_fptr
0x18081edee  mov     esi, eax
0x18081edf0  test    eax, eax
0x18081edf2  js      loc_18081F084
0x18081edf8  mov     rcx, [rsp+0F8h+var_90]
0x18081edfd  mov     rax, [rcx]
0x18081ee00  lea     r8, [rsp+0F8h+var_A0]
0x18081ee05  mov     edx, r14d
0x18081ee08  mov     rax, [rax+60h]
0x18081ee0c  call    cs:__guard_dispatch_icall_fptr
0x18081ee12  mov     esi, eax
0x18081ee14  test    eax, eax
0x18081ee16  js      loc_18081F084
0x18081ee1c  mov     r14, [rsp+0F8h+var_A0]
0x18081ee21  mov     [rsp+0F8h+var_B8], r15d
0x18081ee26  mov     r12, [r12-20h]
0x18081ee2b  test    r14, r14
0x18081ee2e  jz      loc_18081F075
0x18081ee34  test    r12, r12
0x18081ee37  jz      loc_18081F075
0x18081ee3d  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x18081ee45  call    cs:__imp_VariantInit
0x18081ee4b  nop
0x18081ee4c  mov     rax, [r14]
0x18081ee4f  lea     r9, [rsp+0F8h+pvarg]
0x18081ee57  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18081ee5b  mov     r8d, ebx
0x18081ee5e  xor     edx, edx
0x18081ee60  mov     rcx, r14
0x18081ee63  mov     rax, [rax+0F0h]
0x18081ee6a  call    cs:__guard_dispatch_icall_fptr
0x18081ee70  mov     esi, eax
0x18081ee72  test    eax, eax
0x18081ee74  js      loc_18081F021
0x18081ee7a  lea     rcx, [rsp+0F8h+var_70]; pvarg
0x18081ee82  call    cs:__imp_VariantInit
0x18081ee88  nop
0x18081ee89  mov     rax, [r14]
0x18081ee8c  lea     rdx, [rsp+0F8h+var_70]
0x18081ee94  mov     rcx, r14
0x18081ee97  mov     rax, [rax+90h]
0x18081ee9e  call    cs:__guard_dispatch_icall_fptr
0x18081eea4  mov     esi, eax
0x18081eea6  test    eax, eax
0x18081eea8  js      loc_18081F013
0x18081eeae  mov     [rsp+0F8h+ppvData], 0
0x18081eeb7  mov     [rsp+0F8h+var_B0.lpVtbl], 0
0x18081eec0  lea     rdx, [rsp+0F8h+ppvData]; ppvData
0x18081eec5  mov     rcx, qword ptr [rsp+0F8h+pvarg+8]; psa
0x18081eecd  call    cs:__imp_SafeArrayAccessData
0x18081eed3  mov     esi, eax
0x18081eed5  test    eax, eax
0x18081eed7  js      loc_18081EFE3
0x18081eedd  lea     rdx, [rsp+0F8h+var_B0]; ppvData
0x18081eee2  mov     rcx, qword ptr [rsp+0F8h+var_70+8]; psa
0x18081eeea  call    cs:__imp_SafeArrayAccessData
0x18081eef0  mov     esi, eax
0x18081eef2  test    eax, eax
0x18081eef4  js      loc_18081EFE3
0x18081eefa  mov     rax, qword ptr [rsp+0F8h+var_70+8]
0x18081ef02  mov     r15d, [rax+18h]
0x18081ef06  mov     rax, qword ptr [rsp+0F8h+pvarg+8]
0x18081ef0e  mov     eax, [rax+18h]
0x18081ef11  mov     [rsp+0F8h+var_98], eax
0x18081ef15  lea     eax, [rbx+11h]
0x18081ef18  mul     r15
0x18081ef1b  cmovb   rax, rbx
0x18081ef1f  mov     rcx, rax; this
0x18081ef22  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18081ef27  mov     rbx, rax
0x18081ef2a  mov     [rsp+0F8h+var_40], rax
0x18081ef32  xor     esi, esi
0x18081ef34  cmp     esi, r15d
0x18081ef37  jnb     short loc_18081EF57
0x18081ef39  mov     edx, esi
0x18081ef3b  mov     rax, [rsp+0F8h+var_B0.lpVtbl]
0x18081ef40  mov     rcx, [rax+rsi*8]; lpsz
0x18081ef44  shl     rdx, 4
0x18081ef48  add     rdx, rbx; pclsid
0x18081ef4b  call    cs:__imp_CLSIDFromString
0x18081ef51  inc     esi
0x18081ef53  test    eax, eax
0x18081ef55  jns     short loc_18081EF34
0x18081ef57  xor     edx, edx
0x18081ef59  mov     eax, [rsp+0F8h+var_98]
0x18081ef5d  div     r15d
0x18081ef60  mov     [rsp+0F8h+arg_18], eax
0x18081ef67  xor     edx, edx
0x18081ef69  test    eax, eax
0x18081ef6b  jz      short loc_18081EF99
0x18081ef6d  mov     r8d, dword ptr [rsp+0F8h+var_78+4]
0x18081ef75  mov     ecx, edx
0x18081ef77  imul    ecx, r15d
0x18081ef7b  mov     rax, [rsp+0F8h+ppvData]
0x18081ef80  add     [rax+rcx*4], edi
0x18081ef83  inc     ecx
0x18081ef85  mov     rax, [rsp+0F8h+ppvData]
0x18081ef8a  add     [rax+rcx*4], r8d
0x18081ef8e  inc     edx
0x18081ef90  cmp     edx, [rsp+0F8h+arg_18]
0x18081ef97  jb      short loc_18081EF75
0x18081ef99  mov     rax, [r12]
0x18081ef9d  mov     r10, [rax+0D8h]
0x18081efa4  mov     rax, [rsp+0F8h+ppvData]
0x18081efa9  mov     [rsp+0F8h+var_C8], rax
0x18081efae  lea     rax, [rsp+0F8h+arg_18]
0x18081efb6  mov     [rsp+0F8h+var_D0], rax
0x18081efbb  mov     [rsp+0F8h+var_D8], rbx
0x18081efc0  mov     r9d, r15d
0x18081efc3  lea     r8, [rsp+0F8h+var_B8]
0x18081efc8  mov     edx, 1
0x18081efcd  mov     rcx, r12
0x18081efd0  mov     rax, r10
0x18081efd3  call    cs:__guard_dispatch_icall_fptr
0x18081efd9  mov     esi, eax
0x18081efdb  mov     rcx, rbx; void *
0x18081efde  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18081efe3  mov     rcx, qword ptr [rsp+0F8h+var_70+8]; psa
0x18081efeb  call    cs:__imp_SafeArrayUnaccessData
0x18081eff1  test    eax, eax
0x18081eff3  js      short loc_18081F007
0x18081eff5  mov     rcx, qword ptr [rsp+0F8h+pvarg+8]; psa
0x18081effd  call    cs:__imp_SafeArrayUnaccessData
0x18081f003  test    eax, eax
0x18081f005  jns     short loc_18081F013
0x18081f007  mov     ecx, 3973346Ch
0x18081f00c  call    cs:__imp_MsoShipAssertTagProc
0x18081f012  nop
0x18081f013  lea     rcx, [rsp+0F8h+var_70]; pvarg
0x18081f01b  call    cs:__imp_VariantClear
0x18081f021  mov     [rsp+0F8h+var_B0.lpVtbl], 0
0x18081f02a  test    esi, esi
0x18081f02c  js      short loc_18081F060
0x18081f02e  lea     rdx, [rsp+0F8h+var_B0]; struct IInkStrokeDisp *
0x18081f033  mov     rcx, r14; this
0x18081f036  call    ?GetStrokeTimestamp@Dr@@YAJPEAUIInkStrokeDisp@@AEA_K@Z; Dr::GetStrokeTimestamp(IInkStrokeDisp *,unsigned __int64 &)
0x18081f03b  mov     esi, eax
0x18081f03d  test    eax, eax
0x18081f03f  js      short loc_18081F060
0x18081f041  mov     rax, [r12]
0x18081f045  mov     r8, [rsp+0F8h+var_B0.lpVtbl]
0x18081f04a  mov     edx, [rsp+0F8h+var_B8]
0x18081f04e  mov     rcx, r12
0x18081f051  mov     rax, [rax+1D0h]
0x18081f058  call    cs:__guard_dispatch_icall_fptr
0x18081f05e  mov     esi, eax
0x18081f060  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x18081f068  call    cs:__imp_VariantClear
0x18081f06e  mov     r14, [rsp+0F8h+var_A0]
0x18081f073  jmp     short loc_18081F07A
0x18081f075  mov     esi, 80070057h
0x18081f07a  mov     r12, [rsp+0F8h+arg_0]
0x18081f082  jmp     short loc_18081F089
0x18081f084  mov     r14, [rsp+0F8h+var_A0]
0x18081f089  test    r14, r14
0x18081f08c  jz      short loc_18081F0A0
0x18081f08e  mov     rax, [r14]
0x18081f091  mov     rcx, r14
0x18081f094  mov     rax, [rax+10h]
0x18081f098  call    cs:__guard_dispatch_icall_fptr
0x18081f09e  nop
0x18081f09f  nop
0x18081f0a0  mov     rcx, [rsp+0F8h+var_90]
0x18081f0a5  test    rcx, rcx
0x18081f0a8  jz      short loc_18081F0B8
0x18081f0aa  mov     rax, [rcx]
0x18081f0ad  mov     rax, [rax+10h]
0x18081f0b1  call    cs:__guard_dispatch_icall_fptr
0x18081f0b7  nop
0x18081f0b8  mov     rcx, [rsp+0F8h+var_88]
0x18081f0bd  test    rcx, rcx
0x18081f0c0  jz      short loc_18081F0D0
0x18081f0c2  mov     rax, [rcx]
0x18081f0c5  mov     rax, [rax+10h]
0x18081f0c9  call    cs:__guard_dispatch_icall_fptr
0x18081f0cf  nop
0x18081f0d0  lea     rcx, [rsp+0F8h+var_80]; struct Ofc::CProxyPtrImpl **
0x18081f0d5  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18081f0da  inc     r13d
0x18081f0dd  mov     eax, [rsp+0F8h+arg_8]
0x18081f0e4  mov     r8, [rsp+0F8h+arg_10]
0x18081f0ec  jmp     loc_18081ED4A
0x18081f0f1  jmp     short loc_18081F0FA
0x18081f0f3  mov     esi, [rsp+0F8h+arg_18]
0x18081f0fa  mov     eax, esi
0x18081f0fc  add     rsp, 0C0h
0x18081f103  pop     r15
0x18081f105  pop     r14
0x18081f107  pop     r13
0x18081f109  pop     r12
0x18081f10b  pop     rdi
0x18081f10c  pop     rsi
0x18081f10d  pop     rbx
0x18081f10e  retn
```
