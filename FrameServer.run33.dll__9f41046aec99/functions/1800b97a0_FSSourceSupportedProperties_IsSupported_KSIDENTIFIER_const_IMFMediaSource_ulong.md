# FSSourceSupportedProperties::IsSupported(KSIDENTIFIER const &,IMFMediaSource *,ulong)

- ea: `0x1800b97a0`
- end: `0x1800b9c05`
- name: `?IsSupported@FSSourceSupportedProperties@@UEAA_NAEBUKSIDENTIFIER@@PEAUIMFMediaSource@@K@Z`
- size: `1125`
- prototype: `bool __fastcall(FSSourceSupportedProperties *__hidden this, const struct KSIDENTIFIER *, IUnknown *punkObject, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x18004d714`
- `0x18004d748`
- `0x1800677b8`
- `0x1800a6a0c`
- `0x1800b94b8`
- `0x1800b9658`
- `0x1800b97a0`
- `0x1800b9ec0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b9be8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b9be8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b97d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b97d3`
- `MF!MFGetService` at `0x1800b98b0`
- `MF!MFGetService` at `0x1800b98b0`

## pseudocode

```c
bool __fastcall FSSourceSupportedProperties::IsSupported(
        FSSourceSupportedProperties *this,
        const struct KSIDENTIFIER *a2,
        IUnknown *punkObject,
        unsigned int a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  char v9; // si
  KSPropertyTrace *v10; // rax
  const char *String; // rax
  int v12; // r8d
  HRESULT v13; // eax
  int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rcx
  LPVOID v17; // rdi
  __int64 (__fastcall *v18)(LPVOID, __int64, _QWORD, __int64 *); // rbx
  __int64 v19; // rdx
  int v20; // edi
  bool v21; // di
  GUID Set; // xmm0
  __int64 v23; // xmm1_8
  int v24; // eax
  int v25; // eax
  KSPropertyTrace *v26; // rax
  const char *v27; // rax
  bool v28; // zf
  KSPropertyTrace *v29; // rax
  const char *v30; // rax
  int v31; // r8d
  int v33; // [rsp+40h] [rbp-29h] BYREF
  LPVOID ppvObject; // [rsp+48h] [rbp-21h] BYREF
  __int64 v35; // [rsp+50h] [rbp-19h] BYREF
  __int64 v36; // [rsp+58h] [rbp-11h] BYREF
  GUID v37; // [rsp+60h] [rbp-9h] BYREF
  __int64 v38; // [rsp+70h] [rbp+7h]
  int v39; // [rsp+D0h] [rbp+67h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v39 = 0;
  v9 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  LOBYTE(v39) = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v10 = KSPropertyTrace::KSPropertyTrace((KSPropertyTrace *)&v37, a2);
    String = FSString::GetString((KSPropertyTrace *)((char *)v10 + 8));
    WPP_SF_qsqL(*((_QWORD *)WPP_GLOBAL_Control + 27), 15, v12, (_DWORD)this, (__int64)String, (char)punkObject, a4);
    v9 = 1;
  }
  if ( (v9 & 1) != 0 )
  {
    v9 &= ~1u;
    *(_QWORD *)&v37.Data1 = &FSSourceIdentityControlTrace::`vftable';
    FSString::~FSString((FSString *)v37.Data4);
  }
  if ( FSSourceSupportedProperties::InternalFind(this, a2, (bool *)&v39) || !punkObject )
    goto LABEL_41;
  if ( a2->Alignment == *(_QWORD *)&GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data1
    && *(&a2->Alignment + 1) == *(_QWORD *)GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data4 )
  {
    v35 = 0;
    ppvObject = 0;
    v36 = 0;
    v33 = 0;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppvObject);
    v13 = MFGetService(
            punkObject,
            &GUID_00000000_0000_0000_0000_000000000000,
            &GUID_b91ebfee_ca03_4af4_8a82_a31752f4a0fc,
            &ppvObject);
    v14 = v13;
    if ( v13 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_13:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v36);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppvObject);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v35);
        goto LABEL_37;
      }
      v15 = 16;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_3bb71757635139aa4982c210a8729c8d_Traceguids, this, v13);
      goto LABEL_13;
    }
    v16 = v35;
    v35 = 0;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v13 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppvObject)(
            ppvObject,
            &GUID_37ab888c_9d3e_46eb_9d5c_ac1ec00e2729,
            &v35);
    v14 = v13;
    if ( v13 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_13;
      v15 = 17;
      goto LABEL_12;
    }
    v13 = (*(__int64 (__fastcall **)(__int64, const struct KSIDENTIFIER *, _QWORD, int *))(*(_QWORD *)v35 + 32LL))(
            v35,
            a2,
            a2->Id,
            &v33);
    v14 = v13;
    if ( v13 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_13;
      v15 = 18;
      goto LABEL_12;
    }
    v17 = ppvObject;
    v18 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, __int64 *))(*(_QWORD *)ppvObject + 24LL);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v36);
    v19 = 0xFFFFFFFFLL;
    if ( v33 == 1 )
      v19 = a4;
    v20 = v18(v17, v19, a2->Id, &v36);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v36);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppvObject);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v35);
    v21 = v20 >= 0;
    goto LABEL_32;
  }
  Set = a2->Set;
  v36 = 0;
  v23 = *(&a2->Alignment + 2);
  v37 = Set;
  LODWORD(ppvObject) = 0;
  v38 = v23;
  v33 = 0;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v36);
  v24 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))punkObject->lpVtbl->QueryInterface)(
          punkObject,
          &GUID_28f54685_06fd_11d2_b27a_00a0c9223196,
          &v36);
  v14 = v24;
  if ( v24 >= 0 )
  {
    HIDWORD(v38) = 512;
    v21 = 0;
    if ( (*(int (__fastcall **)(__int64, GUID *, __int64, int *, int, LPVOID *))(*(_QWORD *)v36 + 24LL))(
           v36,
           &v37,
           24,
           &v33,
           4,
           &ppvObject) >= 0 )
      v21 = (v33 & 3) != 0;
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v36);
LABEL_32:
    v25 = FSSourceSupportedProperties::InternalAddOrUpdate(this, a2, v21);
    v14 = v25;
    if ( v25 >= 0 )
    {
      LOBYTE(v39) = v21;
    }
    else if ( g_wppLevels )
    {
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_3bb71757635139aa4982c210a8729c8d_Traceguids, this, v25);
    }
    v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
    goto LABEL_37;
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_3bb71757635139aa4982c210a8729c8d_Traceguids, this, v24);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v36);
LABEL_37:
  if ( v14 < 0 )
  {
    if ( byte_18010EC4D )
    {
      v9 |= 2u;
      v26 = KSPropertyTrace::KSPropertyTrace((KSPropertyTrace *)&v37, a2);
      v27 = FSString::GetString((KSPropertyTrace *)((char *)v26 + 8));
      WPP_SF_qsq(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        21,
        (unsigned int)&WPP_3bb71757635139aa4982c210a8729c8d_Traceguids,
        (_DWORD)this,
        (__int64)v27,
        (char)punkObject);
    }
    v28 = (v9 & 2) == 0;
    goto LABEL_44;
  }
LABEL_41:
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v9 |= 4u;
    v29 = KSPropertyTrace::KSPropertyTrace((KSPropertyTrace *)&v37, a2);
    v30 = FSString::GetString((KSPropertyTrace *)((char *)v29 + 8));
    WPP_SF_qsqL(*((_QWORD *)WPP_GLOBAL_Control + 27), 22, v31, (_DWORD)this, (__int64)v30, (char)punkObject, v39);
  }
  v28 = (v9 & 4) == 0;
LABEL_44:
  if ( !v28 )
  {
    *(_QWORD *)&v37.Data1 = &FSSourceIdentityControlTrace::`vftable';
    FSString::~FSString((FSString *)v37.Data4);
  }
  LeaveCriticalSection(v4);
  return v39;
}

```

## disassembly

```asm
0x1800b97a0  push    rbp
0x1800b97a2  push    rbx
0x1800b97a3  push    rsi
0x1800b97a4  push    rdi
0x1800b97a5  push    r12
0x1800b97a7  push    r13
0x1800b97a9  push    r14
0x1800b97ab  push    r15
0x1800b97ad  lea     rbp, [rsp-1Fh]
0x1800b97b2  sub     rsp, 88h
0x1800b97b9  xor     ebx, ebx
0x1800b97bb  lea     rdi, [rcx+10h]
0x1800b97bf  mov     r14, rcx
0x1800b97c2  mov     [rbp+57h+arg_0], ebx
0x1800b97c5  mov     rcx, rdi; lpCriticalSection
0x1800b97c8  mov     r13d, r9d
0x1800b97cb  mov     r12, r8
0x1800b97ce  mov     r15, rdx
0x1800b97d1  mov     esi, ebx
0x1800b97d3  call    cs:__imp_EnterCriticalSection
0x1800b97d9  mov     byte ptr [rbp+57h+arg_0], bl
0x1800b97dc  cmp     cs:byte_18010EC4D, 8
0x1800b97e3  jb      short loc_1800B9825
0x1800b97e5  mov     rdx, r15; struct KSIDENTIFIER *
0x1800b97e8  lea     rcx, [rbp+57h+var_60]; this
0x1800b97ec  call    ??0KSPropertyTrace@@QEAA@QEBUKSIDENTIFIER@@@Z; KSPropertyTrace::KSPropertyTrace(KSIDENTIFIER const * const)
0x1800b97f1  lea     rcx, [rax+8]; this
0x1800b97f5  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x1800b97fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9801  lea     edx, [rbx+0Fh]
0x1800b9804  mov     [rsp+0C0h+var_90], r13d
0x1800b9809  mov     r9, r14
0x1800b980c  mov     [rsp+0C0h+var_98], r12
0x1800b9811  mov     [rsp+0C0h+var_A0], rax
0x1800b9816  mov     rcx, [rcx+0D8h]
0x1800b981d  call    WPP_SF_qsqL
0x1800b9822  lea     esi, [rbx+1]
0x1800b9825  lea     rax, ??_7FSSourceIdentityControlTrace@@6B@; const FSSourceIdentityControlTrace::`vftable'
0x1800b982c  test    sil, 1
0x1800b9830  jz      short loc_1800B9842
0x1800b9832  and     esi, 0FFFFFFFEh
0x1800b9835  mov     qword ptr [rbp+57h+var_60], rax
0x1800b9839  lea     rcx, [rbp+57h+var_60+8]; this
0x1800b983d  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800b9842  lea     r8, [rbp+57h+arg_0]; bool *
0x1800b9846  mov     rdx, r15; struct KSIDENTIFIER *
0x1800b9849  mov     rcx, r14; this
0x1800b984c  call    ?InternalFind@FSSourceSupportedProperties@@AEBA_NAEBUKSIDENTIFIER@@AEA_N@Z; FSSourceSupportedProperties::InternalFind(KSIDENTIFIER const &,bool &)
0x1800b9851  test    al, al
0x1800b9853  jnz     loc_1800B9B7D
0x1800b9859  test    r12, r12
0x1800b985c  jz      loc_1800B9B7D
0x1800b9862  mov     rax, [r15]
0x1800b9865  cmp     rax, qword ptr cs:_GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data1
0x1800b986c  jnz     loc_1800B99FF
0x1800b9872  mov     rax, [r15+8]
0x1800b9876  cmp     rax, qword ptr cs:_GUID_1cb79112_c0d2_4213_9ca6_cd4fdb927972.Data4
0x1800b987d  jnz     loc_1800B99FF
0x1800b9883  lea     rcx, [rbp+57h+ppvObject]
0x1800b9887  mov     [rbp+57h+var_70], rbx
0x1800b988b  mov     [rbp+57h+ppvObject], rbx
0x1800b988f  mov     [rbp+57h+var_68], rbx
0x1800b9893  mov     [rbp+57h+var_80], ebx
0x1800b9896  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800b989b  lea     r9, [rbp+57h+ppvObject]; ppvObject
0x1800b989f  mov     rcx, r12; punkObject
0x1800b98a2  lea     r8, _GUID_b91ebfee_ca03_4af4_8a82_a31752f4a0fc; riid
0x1800b98a9  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidService
0x1800b98b0  call    cs:__imp_MFGetService
0x1800b98b6  mov     ebx, eax
0x1800b98b8  test    eax, eax
0x1800b98ba  jns     short loc_1800B990D
0x1800b98bc  mov     r13d, 1
0x1800b98c2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800b98c9  jb      short loc_1800B98ED
0x1800b98cb  lea     edx, [r13+0Fh]
0x1800b98cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b98d6  lea     r8, WPP_3bb71757635139aa4982c210a8729c8d_Traceguids
0x1800b98dd  mov     r9, r14
0x1800b98e0  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800b98e4  mov     rcx, [rcx+10h]
0x1800b98e8  call    WPP_SF_qD
0x1800b98ed  lea     rcx, [rbp+57h+var_68]; void *
0x1800b98f1  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b98f6  lea     rcx, [rbp+57h+ppvObject]; void *
0x1800b98fa  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b98ff  lea     rcx, [rbp+57h+var_70]; void *
0x1800b9903  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b9908  jmp     loc_1800B9B26
0x1800b990d  mov     rcx, [rbp+57h+var_70]
0x1800b9911  mov     [rbp+57h+var_70], 0
0x1800b9919  test    rcx, rcx
0x1800b991c  jz      short loc_1800B992A
0x1800b991e  mov     rax, [rcx]
0x1800b9921  mov     rax, [rax+10h]
0x1800b9925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b992a  mov     rcx, [rbp+57h+ppvObject]
0x1800b992e  lea     r8, [rbp+57h+var_70]
0x1800b9932  lea     rdx, _GUID_37ab888c_9d3e_46eb_9d5c_ac1ec00e2729
0x1800b9939  mov     rax, [rcx]
0x1800b993c  mov     rax, [rax]
0x1800b993f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9944  mov     ebx, eax
0x1800b9946  test    eax, eax
0x1800b9948  jns     short loc_1800B9962
0x1800b994a  mov     r13d, 1
0x1800b9950  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800b9957  jb      short loc_1800B98ED
0x1800b9959  lea     edx, [r13+10h]
0x1800b995d  jmp     loc_1800B98CF
0x1800b9962  mov     rcx, [rbp+57h+var_70]
0x1800b9966  lea     r9, [rbp+57h+var_80]
0x1800b996a  mov     r8d, [r15+10h]
0x1800b996e  mov     rdx, r15
0x1800b9971  mov     rax, [rcx]
0x1800b9974  mov     rax, [rax+20h]
0x1800b9978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b997d  mov     ebx, eax
0x1800b997f  test    eax, eax
0x1800b9981  jns     short loc_1800B999F
0x1800b9983  mov     r13d, 1
0x1800b9989  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800b9990  jb      loc_1800B98ED
0x1800b9996  lea     edx, [r13+11h]
0x1800b999a  jmp     loc_1800B98CF
0x1800b999f  mov     rdi, [rbp+57h+ppvObject]
0x1800b99a3  lea     rcx, [rbp+57h+var_68]
0x1800b99a7  mov     rax, [rdi]
0x1800b99aa  mov     rbx, [rax+18h]
0x1800b99ae  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800b99b3  mov     r8d, [r15+10h]
0x1800b99b7  lea     r9, [rbp+57h+var_68]
0x1800b99bb  or      edx, 0FFFFFFFFh
0x1800b99be  mov     rcx, rdi
0x1800b99c1  cmp     [rbp+57h+var_80], 1
0x1800b99c5  mov     rax, rbx
0x1800b99c8  cmovz   edx, r13d
0x1800b99cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b99d1  lea     rcx, [rbp+57h+var_68]; void *
0x1800b99d5  mov     edi, eax
0x1800b99d7  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b99dc  lea     rcx, [rbp+57h+ppvObject]; void *
0x1800b99e0  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b99e5  lea     rcx, [rbp+57h+var_70]; void *
0x1800b99e9  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b99ee  shr     edi, 1Fh
0x1800b99f1  mov     r13d, 1
0x1800b99f7  xor     dil, r13b
0x1800b99fa  jmp     loc_1800B9ADC
0x1800b99ff  movups  xmm0, xmmword ptr [r15]
0x1800b9a03  lea     rcx, [rbp+57h+var_68]
0x1800b9a07  mov     [rbp+57h+var_68], rbx
0x1800b9a0b  movsd   xmm1, qword ptr [r15+10h]
0x1800b9a11  movups  [rbp+57h+var_60], xmm0
0x1800b9a15  mov     dword ptr [rbp+57h+ppvObject], ebx
0x1800b9a18  movsd   [rbp+57h+var_50], xmm1
0x1800b9a1d  mov     [rbp+57h+var_80], ebx
0x1800b9a20  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800b9a25  mov     rax, [r12]
0x1800b9a29  lea     r8, [rbp+57h+var_68]
0x1800b9a2d  lea     rdx, _GUID_28f54685_06fd_11d2_b27a_00a0c9223196
0x1800b9a34  mov     rcx, r12
0x1800b9a37  mov     rax, [rax]
0x1800b9a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9a3f  mov     ebx, eax
0x1800b9a41  test    eax, eax
0x1800b9a43  jns     short loc_1800B9A84
0x1800b9a45  mov     r13d, 1
0x1800b9a4b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800b9a52  jb      short loc_1800B9A76
0x1800b9a54  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9a5b  lea     edx, [r13+12h]
0x1800b9a5f  mov     r9, r14
0x1800b9a62  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800b9a66  lea     r8, WPP_3bb71757635139aa4982c210a8729c8d_Traceguids
0x1800b9a6d  mov     rcx, [rcx+10h]
0x1800b9a71  call    WPP_SF_qD
0x1800b9a76  lea     rcx, [rbp+57h+var_68]; void *
0x1800b9a7a  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b9a7f  jmp     loc_1800B9B26
0x1800b9a84  mov     rcx, [rbp+57h+var_68]
0x1800b9a88  lea     rdx, [rbp+57h+ppvObject]
0x1800b9a8c  mov     [rsp+0C0h+var_98], rdx
0x1800b9a91  lea     r9, [rbp+57h+var_80]
0x1800b9a95  mov     dword ptr [rbp+57h+var_50+4], 200h
0x1800b9a9c  lea     rdx, [rbp+57h+var_60]
0x1800b9aa0  mov     r8d, 18h
0x1800b9aa6  mov     dword ptr [rsp+0C0h+var_A0], 4
0x1800b9aae  mov     rax, [rcx]
0x1800b9ab1  xor     dil, dil
0x1800b9ab4  mov     rax, [rax+18h]
0x1800b9ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9abd  mov     r13d, 1
0x1800b9ac3  test    eax, eax
0x1800b9ac5  js      short loc_1800B9AD3
0x1800b9ac7  test    byte ptr [rbp+57h+var_80], 3
0x1800b9acb  movzx   edi, dil
0x1800b9acf  cmovnz  edi, r13d
0x1800b9ad3  lea     rcx, [rbp+57h+var_68]; void *
0x1800b9ad7  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b9adc  mov     r8b, dil; bool
0x1800b9adf  mov     rdx, r15; struct KSIDENTIFIER *
0x1800b9ae2  mov     rcx, r14; this
0x1800b9ae5  call    ?InternalAddOrUpdate@FSSourceSupportedProperties@@AEAAJAEBUKSIDENTIFIER@@_N@Z; FSSourceSupportedProperties::InternalAddOrUpdate(KSIDENTIFIER const &,bool)
0x1800b9aea  mov     ebx, eax
0x1800b9aec  test    eax, eax
0x1800b9aee  jns     short loc_1800B9B1E
0x1800b9af0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1800b9af7  jb      short loc_1800B9B22
0x1800b9af9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9b00  lea     r8, WPP_3bb71757635139aa4982c210a8729c8d_Traceguids
0x1800b9b07  mov     edx, 14h
0x1800b9b0c  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800b9b10  mov     r9, r14
0x1800b9b13  mov     rcx, [rcx+10h]
0x1800b9b17  call    WPP_SF_qD
0x1800b9b1c  jmp     short loc_1800B9B22
0x1800b9b1e  mov     byte ptr [rbp+57h+arg_0], dil
0x1800b9b22  lea     rdi, [r14+10h]
0x1800b9b26  test    ebx, ebx
0x1800b9b28  jns     short loc_1800B9B7D
0x1800b9b2a  cmp     cs:byte_18010EC4D, r13b
0x1800b9b31  jb      short loc_1800B9B77
0x1800b9b33  mov     rdx, r15; struct KSIDENTIFIER *
0x1800b9b36  lea     rcx, [rbp+57h+var_60]; this
0x1800b9b3a  or      esi, 2
0x1800b9b3d  call    ??0KSPropertyTrace@@QEAA@QEBUKSIDENTIFIER@@@Z; KSPropertyTrace::KSPropertyTrace(KSIDENTIFIER const * const)
0x1800b9b42  lea     rcx, [rax+8]; this
0x1800b9b46  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x1800b9b4b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9b52  lea     r8, WPP_3bb71757635139aa4982c210a8729c8d_Traceguids
0x1800b9b59  mov     edx, 15h
0x1800b9b5e  mov     [rsp+0C0h+var_98], r12
0x1800b9b63  mov     r9, r14
0x1800b9b66  mov     [rsp+0C0h+var_A0], rax
0x1800b9b6b  mov     rcx, [rcx+0D8h]
0x1800b9b72  call    WPP_SF_qsq
0x1800b9b77  test    sil, 2
0x1800b9b7b  jmp     short loc_1800B9BCF
0x1800b9b7d  cmp     cs:byte_18010EC4D, 8
0x1800b9b84  jb      short loc_1800B9BCB
0x1800b9b86  mov     rdx, r15; struct KSIDENTIFIER *
0x1800b9b89  lea     rcx, [rbp+57h+var_60]; this
0x1800b9b8d  or      esi, 4
0x1800b9b90  call    ??0KSPropertyTrace@@QEAA@QEBUKSIDENTIFIER@@@Z; KSPropertyTrace::KSPropertyTrace(KSIDENTIFIER const * const)
0x1800b9b95  lea     rcx, [rax+8]; this
0x1800b9b99  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x1800b9b9e  movzx   ecx, byte ptr [rbp+57h+arg_0]
0x1800b9ba2  mov     edx, 16h
0x1800b9ba7  mov     [rsp+0C0h+var_90], ecx
0x1800b9bab  mov     r9, r14
0x1800b9bae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9bb5  mov     [rsp+0C0h+var_98], r12
0x1800b9bba  mov     [rsp+0C0h+var_A0], rax
0x1800b9bbf  mov     rcx, [rcx+0D8h]
0x1800b9bc6  call    WPP_SF_qsqL
0x1800b9bcb  test    sil, 4
0x1800b9bcf  jz      short loc_1800B9BE5
0x1800b9bd1  lea     rax, ??_7FSSourceIdentityControlTrace@@6B@; const FSSourceIdentityControlTrace::`vftable'
0x1800b9bd8  lea     rcx, [rbp+57h+var_60+8]; this
0x1800b9bdc  mov     qword ptr [rbp+57h+var_60], rax
0x1800b9be0  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800b9be5  mov     rcx, rdi; lpCriticalSection
0x1800b9be8  call    cs:__imp_LeaveCriticalSection
0x1800b9bee  mov     al, byte ptr [rbp+57h+arg_0]
0x1800b9bf1  add     rsp, 88h
0x1800b9bf8  pop     r15
0x1800b9bfa  pop     r14
0x1800b9bfc  pop     r13
0x1800b9bfe  pop     r12
0x1800b9c00  pop     rdi
0x1800b9c01  pop     rsi
0x1800b9c02  pop     rbx
0x1800b9c03  pop     rbp
0x1800b9c04  retn
```
