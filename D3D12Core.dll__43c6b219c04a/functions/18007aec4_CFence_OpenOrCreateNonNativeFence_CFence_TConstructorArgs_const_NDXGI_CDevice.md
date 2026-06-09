# CFence::OpenOrCreateNonNativeFence(CFence::TConstructorArgs const &,NDXGI::CDevice &)

- ea: `0x18007aec4`
- end: `0x18007b21f`
- name: `?OpenOrCreateNonNativeFence@CFence@@AEAAXAEBUTConstructorArgs@1@AEAVCDevice@NDXGI@@@Z`
- size: `859`
- prototype: `void __fastcall(CFence *__hidden this, const struct CFence::TConstructorArgs *, struct CDevice *)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18007ac54`
- `0x180132538`

## callees

- `0x180004a38`
- `0x180007f20`
- `0x18000b010`
- `0x18006e724`
- `0x18007aec4`
- `0x1800a5ef4`
- `0x1800bc094`
- `0x18012423c`
- `0x1801324e8`

## import_xrefs

- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTCreateSynchronizationObject2` at `0x18007afdb`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTCreateSynchronizationObject2` at `0x18007b030`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTOpenSyncObjectFromNtHandle2` at `0x18007b0c9`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTOpenSyncObjectFromNtHandle2` at `0x18007b116`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTOpenSyncObjectFromNtHandle2` at `0x18007b140`

## string_xrefs

- `0x18007aff1`: `CreateSynchronizationObject2`
- `0x18007b037`: `CreateSynchronizationObject2`

## pseudocode

```c
void __fastcall CFence::OpenOrCreateNonNativeFence(
        CFence *this,
        const struct CFence::TConstructorArgs *a2,
        struct CDevice *a3)
{
  __int64 v6; // rdx
  char *v7; // r14
  bool v8; // al
  unsigned int v9; // r8d
  __int64 v10; // rax
  int v11; // ecx
  BOOL v12; // edx
  unsigned int v13; // eax
  int v14; // eax
  unsigned int v15; // eax
  int v16; // r10d
  bool v17; // zf
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  int v21; // r9d
  __int64 v22; // rdx
  unsigned int v23; // eax
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  unsigned int v27; // ecx
  unsigned int v28; // eax
  unsigned int v29; // eax
  int v30; // ecx
  bool v31; // cl
  int v32; // eax
  __int64 v33; // rcx
  int v34; // eax
  __int128 v35; // [rsp+20h] [rbp-49h] BYREF
  __int64 v36; // [rsp+30h] [rbp-39h]
  int v37; // [rsp+38h] [rbp-31h]
  int v38; // [rsp+3Ch] [rbp-2Dh]
  __int64 v39; // [rsp+40h] [rbp-29h] BYREF
  int v40; // [rsp+48h] [rbp-21h]
  unsigned int v41; // [rsp+4Ch] [rbp-1Dh]
  __int64 v42; // [rsp+50h] [rbp-19h]
  __int64 v43; // [rsp+58h] [rbp-11h]
  __int64 v44; // [rsp+60h] [rbp-9h]
  int v45; // [rsp+98h] [rbp+2Fh]

  v36 = 0;
  v35 = 0;
  if ( *((_DWORD *)a2 + 6) )
  {
    memset_0(&v39, 0, 0x60u);
    v7 = (char *)this + 152;
    LODWORD(v39) = *((_DWORD *)a3 + 14);
    if ( (*((_DWORD *)a2 + 10) & 4) != 0 )
    {
      *((_DWORD *)this + 56) = 2;
      v9 = 0;
      v10 = *((_QWORD *)a2 + 4);
      *((_BYTE *)this + 230) = 0;
      v40 = 3;
    }
    else
    {
      *((_DWORD *)this + 56) = 0;
      v8 = (*((_DWORD *)a2 + 10) & 8) != 0;
      v40 = 5;
      *((_BYTE *)this + 230) = v8;
      if ( (*(_BYTE *)(*(_QWORD *)v7 + 5304LL) & 1) == 0
        || (*((_BYTE *)a2 + 40) & 3) != 0
        || *(_BYTE *)(*(_QWORD *)v7 + 296LL) < 0x47u )
      {
        v9 = 128;
      }
      else
      {
        LOBYTE(v6) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12_MonitoredFences_GpuAccess>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_D3D12_MonitoredFences_GpuAccess>::GetImpl'::`2'::impl,
          v6);
        v9 = v41 & 0xFFFFFF7F;
      }
      v10 = *((_QWORD *)a2 + 4);
    }
    v42 = v10;
    v11 = *((_DWORD *)a2 + 10) & 1;
    *((_BYTE *)this + 228) = v11;
    v12 = (*((_DWORD *)a2 + 10) & 2) != 0;
    *((_BYTE *)this + 229) = v12;
    v41 = (4 * v12) | (2 * (v11 | (v11 << 9))) & 0xFFFFFFFB | v11 & 0xFFFFFBF9 | v9 & 0xFFFFFBF8;
    v13 = CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
            D3DKMTCreateSynchronizationObject2,
            "CreateSynchronizationObject2",
            CLayeredObject<CCommandAllocator>::AddRef,
            &v39);
    v14 = NDXGI::CUMDAdapter::NTStatusToHResult(v13, 1);
    if ( (v41 & 0x400) != 0 && v14 < 0 )
    {
      v41 &= ~0x400u;
      v15 = CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
              D3DKMTCreateSynchronizationObject2,
              "CreateSynchronizationObject2",
              CLayeredObject<CCommandAllocator>::AddRef,
              &v39);
      v14 = NDXGI::CUMDAdapter::NTStatusToHResult(v15, 1);
    }
    ThrowFailure(v14);
    *((_DWORD *)this + 52) = v45;
    v16 = *((_DWORD *)this + 56);
    if ( v16 )
    {
      v21 = v36;
      v20 = *((_QWORD *)&v35 + 1);
      v19 = v35;
    }
    else
    {
      v17 = (v41 & 0x80u) == 0;
      v18 = v43;
      v19 = v44;
      *((_QWORD *)this + 27) = v43;
      if ( v17 && !v19 && (*(_DWORD *)(*(_QWORD *)v7 + 5304LL) & 4) != 0 )
        v19 = v18;
      v20 = 0;
      v21 = 1;
    }
  }
  else
  {
    memset_0(&v39, 0, 0x58u);
    v39 = *((_QWORD *)a2 + 4);
    v40 = *((_DWORD *)a3 + 14);
    *((_DWORD *)this + 56) = 0;
    v41 = 1155;
    v23 = CallAndLogExceptionOnly<long (*)(_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *),_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *>(
            D3DKMTOpenSyncObjectFromNtHandle2,
            v22,
            &v39);
    v24 = NDXGI::CUMDAdapter::NTStatusToHResult(v23, 1);
    v27 = v41;
    if ( (v41 & 0x400) != 0 && v24 < 0 )
    {
      v41 &= ~0x400u;
      v28 = CallAndLogExceptionOnly<long (*)(_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *),_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *>(
              D3DKMTOpenSyncObjectFromNtHandle2,
              v25,
              &v39);
      v24 = NDXGI::CUMDAdapter::NTStatusToHResult(v28, 1);
      v27 = v41;
    }
    if ( v24 == -2147024809 )
    {
      v41 = v27 & 0xFFFFFF7F;
      v29 = CallAndLogImpl<long (*)(_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *),_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *>(
              D3DKMTOpenSyncObjectFromNtHandle2,
              v25,
              v26,
              &v39);
      v24 = NDXGI::CUMDAdapter::NTStatusToHResult(v29, 1);
      if ( v43 || v44 )
        v30 = 0;
      else
        v30 = 2;
      *((_DWORD *)this + 56) = v30;
    }
    ThrowFailure(v24);
    *((_DWORD *)this + 52) = v42;
    v16 = *((_DWORD *)this + 56);
    if ( v16 )
    {
      v21 = v36;
      v20 = *((_QWORD *)&v35 + 1);
      v19 = v35;
    }
    else
    {
      v20 = 0;
      v19 = v44;
      v21 = 1;
      *((_QWORD *)this + 27) = v43;
      *((_BYTE *)this + 230) = 1;
    }
    v7 = (char *)this + 152;
    v31 = (v41 & 4) != 0;
    *((_BYTE *)this + 228) = 1;
    *((_BYTE *)this + 229) = v31;
  }
  v32 = HIDWORD(v36);
  if ( !v16 )
  {
    v33 = *(_QWORD *)v7;
    *((_QWORD *)&v35 + 1) = v19;
    v36 = v20;
    v37 = v21;
    *(_QWORD *)&v35 = 0;
    v38 = v32;
    v34 = ((__int64 (__fastcall *)(__int64, char *, CFence *, __int128 *))CDevice::VersionedCreateFence)(
            v33,
            (char *)this + 240,
            this,
            &v35);
    ThrowFailure(v34);
  }
}

```

## disassembly

```asm
0x18007aec4  push    rbp
0x18007aec6  push    rbx
0x18007aec7  push    rsi
0x18007aec8  push    rdi
0x18007aec9  push    r14
0x18007aecb  lea     rbp, [rsp-37h]
0x18007aed0  sub     rsp, 0A0h
0x18007aed7  xor     eax, eax
0x18007aed9  xorps   xmm0, xmm0
0x18007aedc  mov     rdi, r8
0x18007aedf  mov     rsi, rdx
0x18007aee2  mov     rbx, rcx
0x18007aee5  mov     [rbp+57h+var_90], rax
0x18007aee9  movups  [rbp+57h+var_A0], xmm0
0x18007aeed  cmp     [rdx+18h], eax
0x18007aef0  jz      loc_18007B0B2
0x18007aef6  xor     edx, edx; Val
0x18007aef8  lea     r8d, [rax+60h]; Size
0x18007aefc  lea     rcx, [rbp+57h+var_80]; void *
0x18007af00  call    memset_0
0x18007af05  mov     eax, [rdi+38h]
0x18007af08  lea     r14, [rbx+98h]
0x18007af0f  mov     dword ptr [rbp+57h+var_80], eax
0x18007af12  mov     edi, 1
0x18007af17  mov     eax, [rsi+28h]
0x18007af1a  test    al, 4
0x18007af1c  jnz     short loc_18007AF7F
0x18007af1e  mov     dword ptr [rbx+0E0h], 0
0x18007af28  mov     eax, [rsi+28h]
0x18007af2b  shr     eax, 3
0x18007af2e  and     al, dil
0x18007af31  mov     [rbp+57h+var_78], 5
0x18007af38  mov     [rbx+0E6h], al
0x18007af3e  mov     rax, [r14]
0x18007af41  test    [rax+14B8h], dil
0x18007af48  jz      short loc_18007AF73
0x18007af4a  test    byte ptr [rsi+28h], 3
0x18007af4e  jnz     short loc_18007AF73
0x18007af50  cmp     byte ptr [rax+128h], 47h ; 'G'
0x18007af57  jb      short loc_18007AF73
0x18007af59  mov     dl, dil
0x18007af5c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12_MonitoredFences_GpuAccess@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12_MonitoredFences_GpuAccess@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12_MonitoredFences_GpuAccess> `wil::Feature<__WilFeatureTraits_Feature_D3D12_MonitoredFences_GpuAccess>::GetImpl(void)'::`2'::impl
0x18007af63  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12_MonitoredFences_GpuAccess@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12_MonitoredFences_GpuAccess>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18007af68  mov     r8d, [rbp+57h+var_74]
0x18007af6c  btr     r8d, 7
0x18007af71  jmp     short loc_18007AF79
0x18007af73  mov     r8d, 80h
0x18007af79  mov     rax, [rsi+20h]
0x18007af7d  jmp     short loc_18007AF9E
0x18007af7f  mov     dword ptr [rbx+0E0h], 2
0x18007af89  xor     r8d, r8d
0x18007af8c  mov     rax, [rsi+20h]
0x18007af90  mov     byte ptr [rbx+0E6h], 0
0x18007af97  mov     [rbp+57h+var_78], 3
0x18007af9e  mov     [rbp+57h+var_70], rax
0x18007afa2  lea     r9, [rbp+57h+var_80]
0x18007afa6  mov     eax, [rsi+28h]
0x18007afa9  and     r8d, 0FFFFFFFEh
0x18007afad  and     al, dil
0x18007afb0  movzx   ecx, al
0x18007afb3  or      r8d, ecx
0x18007afb6  mov     [rbx+0E4h], cl
0x18007afbc  mov     eax, [rsi+28h]
0x18007afbf  and     r8d, 0FFFFFBFDh
0x18007afc6  shr     eax, 1
0x18007afc8  and     al, dil
0x18007afcb  movzx   edx, al
0x18007afce  mov     eax, ecx
0x18007afd0  shl     eax, 9
0x18007afd3  or      eax, ecx
0x18007afd5  mov     [rbx+0E5h], dl
0x18007afdb  mov     rcx, cs:__imp_D3DKMTCreateSynchronizationObject2
0x18007afe2  add     eax, eax
0x18007afe4  or      r8d, eax
0x18007afe7  shl     edx, 2
0x18007afea  and     r8d, 0FFFFFFFBh
0x18007afee  or      r8d, edx
0x18007aff1  lea     rdx, aCreatesynchron; "CreateSynchronizationObject2"
0x18007aff8  mov     [rbp+57h+var_74], r8d
0x18007affc  lea     r8, ?AddRef@?$CLayeredObject@VCCommandAllocator@@@@UEAAKXZ; CLayeredObject<CCommandAllocator>::AddRef(void)
0x18007b003  call    ??$CallAndLogImpl@P6AJPEAUD3DDDI_DESTROYPAGINGQUEUE@@@ZPEAU1@@@YAJP6AJPEAUD3DDDI_DESTROYPAGINGQUEUE@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(long (*)(D3DDDI_DESTROYPAGINGQUEUE *),char const *,RecordStatusFilterResult (*)(long),D3DDDI_DESTROYPAGINGQUEUE *)
0x18007b008  mov     edx, edi
0x18007b00a  mov     ecx, eax
0x18007b00c  call    ?NTStatusToHResult@CUMDAdapter@NDXGI@@SAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CUMDAdapter::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x18007b011  mov     ecx, [rbp+57h+var_74]
0x18007b014  bt      ecx, 0Ah
0x18007b018  jnb     short loc_18007B04C
0x18007b01a  test    eax, eax
0x18007b01c  jns     short loc_18007B04C
0x18007b01e  btr     ecx, 0Ah
0x18007b022  lea     r9, [rbp+57h+var_80]
0x18007b026  mov     [rbp+57h+var_74], ecx
0x18007b029  lea     r8, ?AddRef@?$CLayeredObject@VCCommandAllocator@@@@UEAAKXZ; CLayeredObject<CCommandAllocator>::AddRef(void)
0x18007b030  mov     rcx, cs:__imp_D3DKMTCreateSynchronizationObject2
0x18007b037  lea     rdx, aCreatesynchron; "CreateSynchronizationObject2"
0x18007b03e  call    ??$CallAndLogImpl@P6AJPEAUD3DDDI_DESTROYPAGINGQUEUE@@@ZPEAU1@@@YAJP6AJPEAUD3DDDI_DESTROYPAGINGQUEUE@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(long (*)(D3DDDI_DESTROYPAGINGQUEUE *),char const *,RecordStatusFilterResult (*)(long),D3DDDI_DESTROYPAGINGQUEUE *)
0x18007b043  mov     edx, edi
0x18007b045  mov     ecx, eax
0x18007b047  call    ?NTStatusToHResult@CUMDAdapter@NDXGI@@SAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CUMDAdapter::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x18007b04c  mov     ecx, eax; int
0x18007b04e  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18007b053  mov     eax, [rbp+57h+var_28]
0x18007b056  mov     [rbx+0D0h], eax
0x18007b05c  mov     r10d, [rbx+0E0h]
0x18007b063  test    r10d, r10d
0x18007b066  jnz     short loc_18007B0A1
0x18007b068  test    byte ptr [rbp+57h+var_74], 80h
0x18007b06c  mov     r8, [rbp+57h+var_68]
0x18007b070  mov     rdx, [rbp+57h+var_60]
0x18007b074  mov     [rbx+0D8h], r8
0x18007b07b  jnz     short loc_18007B096
0x18007b07d  test    rdx, rdx
0x18007b080  jnz     short loc_18007B096
0x18007b082  mov     rax, [r14]
0x18007b085  mov     ecx, [rax+14B8h]
0x18007b08b  shr     ecx, 2
0x18007b08e  test    dil, cl
0x18007b091  jz      short loc_18007B096
0x18007b093  mov     rdx, r8
0x18007b096  xor     r8d, r8d
0x18007b099  mov     r9d, edi
0x18007b09c  jmp     loc_18007B1D5
0x18007b0a1  mov     r9d, dword ptr [rbp+57h+var_90]
0x18007b0a5  mov     r8, qword ptr [rbp+57h+var_A0+8]
0x18007b0a9  mov     rdx, qword ptr [rbp+57h+var_A0]
0x18007b0ad  jmp     loc_18007B1D5
0x18007b0b2  xor     edx, edx; Val
0x18007b0b4  lea     rcx, [rbp+57h+var_80]; void *
0x18007b0b8  lea     r8d, [rdx+58h]; Size
0x18007b0bc  call    memset_0
0x18007b0c1  mov     rax, [rsi+20h]
0x18007b0c5  lea     r8, [rbp+57h+var_80]
0x18007b0c9  mov     rcx, cs:__imp_D3DKMTOpenSyncObjectFromNtHandle2
0x18007b0d0  mov     [rbp+57h+var_80], rax
0x18007b0d4  mov     eax, [rdi+38h]
0x18007b0d7  mov     [rbp+57h+var_78], eax
0x18007b0da  mov     dword ptr [rbx+0E0h], 0
0x18007b0e4  mov     [rbp+57h+var_74], 483h
0x18007b0eb  call    ??$CallAndLogExceptionOnly@P6AJPEAU_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2@@@ZPEBD0@Z; CallAndLogExceptionOnly<long (*)(_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *),_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *>(long (*)(_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *),char const *,_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *)
0x18007b0f0  mov     edi, 1
0x18007b0f5  mov     ecx, eax
0x18007b0f7  mov     edx, edi
0x18007b0f9  call    ?NTStatusToHResult@CUMDAdapter@NDXGI@@SAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CUMDAdapter::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x18007b0fe  mov     ecx, [rbp+57h+var_74]
0x18007b101  bt      ecx, 0Ah
0x18007b105  jnb     short loc_18007B12E
0x18007b107  test    eax, eax
0x18007b109  jns     short loc_18007B12E
0x18007b10b  btr     ecx, 0Ah
0x18007b10f  lea     r8, [rbp+57h+var_80]
0x18007b113  mov     [rbp+57h+var_74], ecx
0x18007b116  mov     rcx, cs:__imp_D3DKMTOpenSyncObjectFromNtHandle2
0x18007b11d  call    ??$CallAndLogExceptionOnly@P6AJPEAU_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2@@@ZPEBD0@Z; CallAndLogExceptionOnly<long (*)(_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *),_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *>(long (*)(_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *),char const *,_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *)
0x18007b122  mov     edx, edi
0x18007b124  mov     ecx, eax
0x18007b126  call    ?NTStatusToHResult@CUMDAdapter@NDXGI@@SAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CUMDAdapter::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x18007b12b  mov     ecx, [rbp+57h+var_74]
0x18007b12e  cmp     eax, 80070057h
0x18007b133  jnz     short loc_18007B172
0x18007b135  btr     ecx, 7
0x18007b139  lea     r9, [rbp+57h+var_80]
0x18007b13d  mov     [rbp+57h+var_74], ecx
0x18007b140  mov     rcx, cs:__imp_D3DKMTOpenSyncObjectFromNtHandle2
0x18007b147  call    ??$CallAndLogImpl@P6AJPEAU_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2@@@ZPEAU1@@@YAJP6AJPEAU_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *),_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *>(long (*)(_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *),char const *,RecordStatusFilterResult (*)(long),_D3DKMT_OPENSYNCOBJECTFROMNTHANDLE2 *)
0x18007b14c  mov     edx, edi
0x18007b14e  mov     ecx, eax
0x18007b150  call    ?NTStatusToHResult@CUMDAdapter@NDXGI@@SAJJW4EErrorTranslationBehavior@2@@Z; NDXGI::CUMDAdapter::NTStatusToHResult(long,NDXGI::EErrorTranslationBehavior)
0x18007b155  cmp     [rbp+57h+var_68], 0
0x18007b15a  jnz     short loc_18007B16A
0x18007b15c  cmp     [rbp+57h+var_60], 0
0x18007b161  jnz     short loc_18007B16A
0x18007b163  mov     ecx, 2
0x18007b168  jmp     short loc_18007B16C
0x18007b16a  xor     ecx, ecx
0x18007b16c  mov     [rbx+0E0h], ecx
0x18007b172  mov     ecx, eax; int
0x18007b174  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18007b179  mov     eax, dword ptr [rbp+57h+var_70]
0x18007b17c  mov     [rbx+0D0h], eax
0x18007b182  mov     r10d, [rbx+0E0h]
0x18007b189  test    r10d, r10d
0x18007b18c  jnz     short loc_18007B1AC
0x18007b18e  mov     rax, [rbp+57h+var_68]
0x18007b192  xor     r8d, r8d
0x18007b195  mov     rdx, [rbp+57h+var_60]
0x18007b199  mov     r9d, edi
0x18007b19c  mov     [rbx+0D8h], rax
0x18007b1a3  mov     [rbx+0E6h], dil
0x18007b1aa  jmp     short loc_18007B1B8
0x18007b1ac  mov     r9d, dword ptr [rbp+57h+var_90]
0x18007b1b0  mov     r8, qword ptr [rbp+57h+var_A0+8]
0x18007b1b4  mov     rdx, qword ptr [rbp+57h+var_A0]
0x18007b1b8  mov     ecx, [rbp+57h+var_74]
0x18007b1bb  lea     r14, [rbx+98h]
0x18007b1c2  shr     ecx, 2
0x18007b1c5  and     cl, dil
0x18007b1c8  mov     [rbx+0E4h], dil
0x18007b1cf  mov     [rbx+0E5h], cl
0x18007b1d5  mov     eax, dword ptr [rbp+57h+var_90+4]
0x18007b1d8  test    r10d, r10d
0x18007b1db  jnz     short loc_18007B211
0x18007b1dd  mov     rcx, [r14]
0x18007b1e0  mov     qword ptr [rbp+57h+var_A0+8], rdx
0x18007b1e4  lea     rdx, [rbx+0F0h]
0x18007b1eb  mov     [rbp+57h+var_90], r8
0x18007b1ef  mov     r8, rbx
0x18007b1f2  mov     [rbp+57h+var_88], r9d
0x18007b1f6  lea     r9, [rbp+57h+var_A0]
0x18007b1fa  mov     qword ptr [rbp+57h+var_A0], 0
0x18007b202  mov     [rbp+57h+var_84], eax
0x18007b205  call    ?VersionedCreateFence@CDevice@@QEAAJUD3D12DDI_HFENCE@@UD3D12DDI_HRTFENCE@@PEAUD3D12DDIARG_CREATE_FENCE_0116@@@Z; CDevice::VersionedCreateFence(D3D12DDI_HFENCE,D3D12DDI_HRTFENCE,D3D12DDIARG_CREATE_FENCE_0116 *)
0x18007b20a  mov     ecx, eax; int
0x18007b20c  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18007b211  add     rsp, 0A0h
0x18007b218  pop     r14
0x18007b21a  pop     rdi
0x18007b21b  pop     rsi
0x18007b21c  pop     rbx
0x18007b21d  pop     rbp
0x18007b21e  retn
```
