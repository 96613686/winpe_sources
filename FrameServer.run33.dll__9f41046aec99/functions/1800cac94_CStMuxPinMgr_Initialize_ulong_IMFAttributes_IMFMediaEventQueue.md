# CStMuxPinMgr::Initialize(ulong,IMFAttributes *,IMFMediaEventQueue *)

- ea: `0x1800cac94`
- end: `0x1800cb2c6`
- name: `?Initialize@CStMuxPinMgr@@IEAAJKPEAUIMFAttributes@@PEAUIMFMediaEventQueue@@@Z`
- size: `1586`
- prototype: `__int64 __fastcall(CStMuxPinMgr *__hidden this, unsigned int, struct IMFAttributes *, struct IMFMediaEventQueue *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800ca354`

## callees

- `0x180003e20`
- `0x1800041f0`
- `0x180004f20`
- `0x180009608`
- `0x180014f08`
- `0x180016790`
- `0x180018e9c`
- `0x1800ca2ac`
- `0x1800cac94`
- `0x1800cbc54`
- `0x1800cc944`
- `0x1800e9240`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreateCollection` at `0x1800caee0`
- `MFPlat!MFCreateCollection` at `0x1800caee0`
- `MFPlat!MFCreateMuxStreamAttributes` at `0x1800cb10c`
- `MFPlat!MFCreateMuxStreamAttributes` at `0x1800cb10c`

## pseudocode

```c
__int64 __fastcall CStMuxPinMgr::Initialize(
        CStMuxPinMgr *this,
        const struct std::nothrow_t *a2,
        struct IMFAttributes *a3,
        struct IMFMediaEventQueue *a4)
{
  unsigned int v6; // ebx
  HRESULT (__stdcall *GetUnknown)(IMFAttributes *, const GUID *const, const IID *const, LPVOID *); // rbx
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // eax
  __int64 v12; // rdx
  __int64 (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 **v14; // r13
  __int64 (__fastcall *v15)(_QWORD, GUID *, char *); // rdi
  void *v16; // rbx
  struct IKsControl *v17; // rax
  const struct std::nothrow_t *v18; // rdx
  int Pin; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  unsigned int v26; // r12d
  __int64 v27; // r14
  __int64 *v28; // rdi
  __int64 v29; // rax
  __int64 (__fastcall *v30)(__int64 *, _QWORD, struct IMFAttributes **); // rbx
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  unsigned int v38; // edi
  __int64 v39; // r13
  struct IStBasePin *v40; // rbx
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  __int64 v48; // r8
  __int64 v49; // r9
  _QWORD *v50; // r14
  int updated; // eax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // r9
  __int64 v55; // rdx
  __int64 v56; // rdi
  __int64 (__fastcall *v57)(__int64, struct IStBasePin **); // rbx
  struct IStBasePin *v58; // rbx
  __int64 (__fastcall *v59)(CStMuxPinMgr *, _QWORD, struct IStBasePin *, _QWORD, _DWORD); // rdi
  unsigned int v60; // eax
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r9
  struct IKsControl *v65; // [rsp+20h] [rbp-49h]
  struct IStBasePin *v66; // [rsp+30h] [rbp-39h] BYREF
  struct IMFAttributes *v67; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v68; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v69; // [rsp+44h] [rbp-25h] BYREF
  __int64 v70; // [rsp+48h] [rbp-21h] BYREF
  __int64 (__fastcall ***v71)(_QWORD, GUID *, char *); // [rsp+50h] [rbp-19h] BYREF
  struct IMFMediaEventQueue *v72; // [rsp+58h] [rbp-11h]
  void *v73; // [rsp+60h] [rbp-9h]
  void *v74; // [rsp+68h] [rbp-1h]
  GUID Buf1; // [rsp+70h] [rbp+7h] BYREF

  v69 = 0;
  v72 = a4;
  v68 = 0;
  v71 = 0;
  v70 = 0;
  if ( !a4 )
  {
    v6 = -2147024809;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids,
        this,
        -2147024809);
    goto LABEL_73;
  }
  Microsoft::WRL::ComPtr<IMFMediaEventQueue>::operator=((char *)this + 96, a4);
  GetUnknown = a3->lpVtbl->GetUnknown;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71, v8, v9, v10);
  v11 = ((__int64 (__fastcall *)(struct IMFAttributes *, const IID *, GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, char *)))GetUnknown)(
          a3,
          &MF_DEVICEMFT_CONNECTED_FILTER_KSCONTROL,
          &GUID_00000000_0000_0000_c000_000000000046,
          &v71);
  v6 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_73;
    v12 = 14;
    goto LABEL_7;
  }
  v13 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v71;
  v14 = (__int64 **)((char *)this + 88);
  v15 = **v71;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 88, a2, a3, a4);
  v11 = v15(v13, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, (char *)this + 88);
  v6 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_73;
    v12 = 15;
    goto LABEL_7;
  }
  v11 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, unsigned int *))(**v14 + 32))(*v14, &v69, &v68);
  v6 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_73;
    v12 = 16;
    goto LABEL_7;
  }
  v74 = operator new[](saturated_mul(v69, 4u));
  v16 = v74;
  if ( !v74 )
  {
    v11 = -2147024882;
    v6 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_73;
    v12 = 17;
LABEL_7:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids, this, v11);
    goto LABEL_73;
  }
  v17 = (struct IKsControl *)operator new[](saturated_mul(v68, 4u));
  v73 = v17;
  v18 = (const struct std::nothrow_t *)v17;
  if ( !v17 )
  {
    Pin = -2147024882;
    v6 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_71;
    v20 = 18;
    goto LABEL_20;
  }
  v65 = v17;
  Pin = (*(__int64 (__fastcall **)(__int64 *, _QWORD, void *, _QWORD))(**v14 + 40))(*v14, v69, v16, v68);
  v6 = Pin;
  if ( Pin < 0 )
  {
    if ( g_wppLevels )
    {
      v20 = 19;
LABEL_20:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids, this, Pin);
      goto LABEL_71;
    }
    goto LABEL_71;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70, v18, v21, v22);
  Pin = MFCreateCollection(&v70);
  v6 = Pin;
  if ( Pin >= 0 )
  {
    CTUnkArray<IFSMemStream>::RemoveAll((char *)this + 8);
    v26 = 0;
    v27 = 0;
    while ( (unsigned int)v27 < v68 )
    {
      v28 = *v14;
      v67 = 0;
      Buf1 = GUID_00000000_0000_0000_0000_000000000000;
      v29 = *v28;
      v66 = 0;
      v30 = *(__int64 (__fastcall **)(__int64 *, _QWORD, struct IMFAttributes **))(v29 + 80);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67, v23, v24, v25);
      v31 = v30(v28, (unsigned int)v27, &v67);
      v6 = v31;
      if ( v31 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_53;
        v44 = 21;
        goto LABEL_52;
      }
      v31 = ((__int64 (__fastcall *)(struct IMFAttributes *, const IID *, GUID *))v67->lpVtbl->GetGUID)(
              v67,
              &MF_DEVICESTREAM_STREAM_CATEGORY,
              &Buf1);
      v6 = v31;
      if ( v31 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_53;
        v44 = 22;
LABEL_52:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v44, &WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids, this, v31);
        goto LABEL_53;
      }
      if ( !memcmp_0(&Buf1, &GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba, 0x10u)
        || (v38 = -1, !memcmp_0(&Buf1, &GUID_fb6c4282_0353_11d1_905f_0000c0cc16ba, 0x10u)) )
      {
        v38 = v26;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66, v35, v36, v37);
      v31 = CStBasePin::CreatePin(v38, *((_DWORD *)v73 + v27), v67, v72, v65, &v66);
      v6 = v31;
      if ( v31 < 0 )
      {
        if ( g_wppLevels )
        {
          v44 = 23;
          goto LABEL_52;
        }
LABEL_53:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66, v32, v33, v34);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67, v45, v46, v47);
        goto LABEL_71;
      }
      v39 = *((unsigned int *)this + 4);
      if ( !(unsigned int)CTEntryArray<FSCallback<IFSSourceFrameCallback,void *,int> *>::SetSize(
                            (char *)this + 8,
                            (unsigned int)(v39 + 1)) )
      {
        v31 = -2147024882;
        v6 = -2147024882;
        if ( g_wppLevels )
        {
          v44 = 24;
          goto LABEL_52;
        }
        goto LABEL_53;
      }
      v40 = v66;
      *(_QWORD *)(*((_QWORD *)this + 1) + 8 * v39) = v66;
      if ( v40 )
        (*(void (__fastcall **)(struct IStBasePin *))(*(_QWORD *)v40 + 8LL))(v40);
      if ( v38 != -1 )
      {
        v31 = (*(__int64 (__fastcall **)(__int64, struct IStBasePin *))(*(_QWORD *)v70 + 40LL))(v70, v40);
        v6 = v31;
        if ( v31 < 0 )
        {
          if ( g_wppLevels )
          {
            v44 = 25;
            goto LABEL_52;
          }
          goto LABEL_53;
        }
        ++v26;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66, v32, v33, v34);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v67, v41, v42, v43);
      v27 = (unsigned int)(v27 + 1);
      v14 = (__int64 **)((char *)this + 88);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 104, v23, v24, v25);
    Pin = MFCreateMuxStreamAttributes(v70, (char *)this + 104);
    v6 = Pin;
    if ( Pin < 0 )
    {
      if ( g_wppLevels )
      {
        v20 = 26;
        goto LABEL_20;
      }
      goto LABEL_71;
    }
    v50 = (_QWORD *)((char *)this + 80);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 80, v18, v48, v49);
    Pin = CStBasePin::CreatePin(0, 0, *((struct IMFAttributes **)this + 13), v72, v65, (struct IStBasePin **)this + 10);
    v6 = Pin;
    if ( Pin < 0 )
    {
      if ( g_wppLevels )
      {
        v20 = 27;
        goto LABEL_20;
      }
      goto LABEL_71;
    }
    v66 = 0;
    updated = CStMuxPinMgr::UpdateMediaTypes(this);
    v6 = updated;
    if ( updated >= 0 )
    {
      v56 = *v50;
      v57 = *(__int64 (__fastcall **)(__int64, struct IStBasePin **))(*(_QWORD *)*v50 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66, v52, v53, v54);
      updated = v57(v56, &v66);
      v6 = updated;
      if ( updated >= 0 )
      {
        v58 = v66;
        v59 = *(__int64 (__fastcall **)(CStMuxPinMgr *, _QWORD, struct IStBasePin *, _QWORD, _DWORD))(*(_QWORD *)this + 96LL);
        v60 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v50 + 88LL))(*v50);
        updated = v59(this, v60, v58, 0, 0);
        v6 = updated;
        if ( updated >= 0 || !g_wppLevels )
          goto LABEL_70;
        v55 = 30;
        goto LABEL_69;
      }
      if ( g_wppLevels )
      {
        v55 = 29;
        goto LABEL_69;
      }
    }
    else if ( g_wppLevels )
    {
      v55 = 28;
LABEL_69:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v55,
        &WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids,
        this,
        updated);
    }
LABEL_70:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v66, v52, v53, v54);
    goto LABEL_71;
  }
  if ( g_wppLevels )
  {
    v20 = 20;
    goto LABEL_20;
  }
LABEL_71:
  operator delete(v74, v18);
  if ( v73 )
    operator delete(v73, a2);
LABEL_73:
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 31, &WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids, this, v6);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v70, a2, a3, a4);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v71, v61, v62, v63);
  return v6;
}

```

## disassembly

```asm
0x1800cac94  mov     [rsp-8+arg_8], rbx
0x1800cac99  push    rbp
0x1800cac9a  push    rsi
0x1800cac9b  push    rdi
0x1800cac9c  push    r12
0x1800cac9e  push    r13
0x1800caca0  push    r14
0x1800caca2  push    r15
0x1800caca4  lea     rbp, [rsp-27h]
0x1800caca9  sub     rsp, 90h
0x1800cacb0  mov     rax, cs:__security_cookie
0x1800cacb7  xor     rax, rsp
0x1800cacba  mov     [rbp+57h+var_40], rax
0x1800cacbe  mov     [rbp+57h+var_7C], 0
0x1800cacc5  mov     rax, r9
0x1800cacc8  mov     [rbp+57h+var_68], rax
0x1800caccc  mov     rdi, r8
0x1800caccf  mov     [rbp+57h+var_80], 0
0x1800cacd6  mov     rsi, rcx
0x1800cacd9  mov     [rbp+57h+var_70], 0
0x1800cace1  mov     [rbp+57h+var_78], 0
0x1800cace9  test    r9, r9
0x1800cacec  jnz     short loc_1800CAD27
0x1800cacee  mov     ebx, 80070057h
0x1800cacf3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cacfa  jb      loc_1800CB25C
0x1800cad00  lea     edx, [r9+0Dh]
0x1800cad04  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1800cad08  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cad0f  lea     r8, WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids
0x1800cad16  mov     r9, rsi
0x1800cad19  mov     rcx, [rcx+10h]
0x1800cad1d  call    WPP_SF_qD
0x1800cad22  jmp     loc_1800CB25C
0x1800cad27  add     rcx, 60h ; '`'
0x1800cad2b  mov     rdx, rax
0x1800cad2e  call    ??4?$ComPtr@UIMFMediaEventQueue@@@WRL@Microsoft@@QEAAAEAV012@PEAUIMFMediaEventQueue@@@Z; Microsoft::WRL::ComPtr<IMFMediaEventQueue>::operator=(IMFMediaEventQueue *)
0x1800cad33  mov     rax, [rdi]
0x1800cad36  lea     rcx, [rbp+57h+var_70]
0x1800cad3a  mov     rbx, [rax+88h]
0x1800cad41  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cad46  lea     r9, [rbp+57h+var_70]
0x1800cad4a  mov     rcx, rdi
0x1800cad4d  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x1800cad54  mov     rax, rbx
0x1800cad57  lea     rdx, MF_DEVICEMFT_CONNECTED_FILTER_KSCONTROL
0x1800cad5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cad63  mov     ebx, eax
0x1800cad65  test    eax, eax
0x1800cad67  jns     short loc_1800CAD81
0x1800cad69  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cad70  jb      loc_1800CB25C
0x1800cad76  mov     edx, 0Eh
0x1800cad7b  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800cad7f  jmp     short loc_1800CAD08
0x1800cad81  mov     rbx, [rbp+57h+var_70]
0x1800cad85  lea     r13, [rsi+58h]
0x1800cad89  mov     rcx, r13
0x1800cad8c  mov     rax, [rbx]
0x1800cad8f  mov     rdi, [rax]
0x1800cad92  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cad97  mov     r8, r13
0x1800cad9a  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x1800cada1  mov     rcx, rbx
0x1800cada4  mov     rax, rdi
0x1800cada7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cadac  mov     ebx, eax
0x1800cadae  test    eax, eax
0x1800cadb0  jns     short loc_1800CADC6
0x1800cadb2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cadb9  jb      loc_1800CB25C
0x1800cadbf  mov     edx, 0Fh
0x1800cadc4  jmp     short loc_1800CAD7B
0x1800cadc6  mov     rcx, [r13+0]
0x1800cadca  lea     r8, [rbp+57h+var_80]
0x1800cadce  lea     rdx, [rbp+57h+var_7C]
0x1800cadd2  mov     rax, [rcx]
0x1800cadd5  mov     rax, [rax+20h]
0x1800cadd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cadde  mov     ebx, eax
0x1800cade0  test    eax, eax
0x1800cade2  jns     short loc_1800CADF8
0x1800cade4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cadeb  jb      loc_1800CB25C
0x1800cadf1  mov     edx, 10h
0x1800cadf6  jmp     short loc_1800CAD7B
0x1800cadf8  mov     ecx, [rbp+57h+var_7C]
0x1800cadfb  mov     edi, 4
0x1800cae00  mov     eax, edi
0x1800cae02  mul     rcx
0x1800cae05  lea     r14, [rdi-5]
0x1800cae09  cmovb   rax, r14
0x1800cae0d  mov     rcx, rax; unsigned __int64
0x1800cae10  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800cae15  mov     [rbp+57h+var_58], rax
0x1800cae19  mov     rbx, rax
0x1800cae1c  test    rax, rax
0x1800cae1f  jnz     short loc_1800CAE3D
0x1800cae21  mov     eax, 8007000Eh
0x1800cae26  mov     ebx, eax
0x1800cae28  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cae2f  jb      loc_1800CB25C
0x1800cae35  lea     edx, [rdi+0Dh]
0x1800cae38  jmp     loc_1800CAD7B
0x1800cae3d  mov     ecx, [rbp+57h+var_80]
0x1800cae40  mov     rax, rdi
0x1800cae43  mul     rcx
0x1800cae46  cmovb   rax, r14
0x1800cae4a  mov     rcx, rax; unsigned __int64
0x1800cae4d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800cae52  mov     [rbp+57h+var_60], rax
0x1800cae56  mov     rdx, rax
0x1800cae59  test    rax, rax
0x1800cae5c  jnz     short loc_1800CAE9A
0x1800cae5e  mov     eax, 8007000Eh
0x1800cae63  mov     ebx, eax
0x1800cae65  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cae6c  jb      loc_1800CB242
0x1800cae72  mov     edx, 12h
0x1800cae77  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cae7e  lea     r8, WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids
0x1800cae85  mov     r9, rsi
0x1800cae88  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800cae8c  mov     rcx, [rcx+10h]
0x1800cae90  call    WPP_SF_qD
0x1800cae95  jmp     loc_1800CB242
0x1800cae9a  mov     rcx, [r13+0]
0x1800cae9e  mov     r8, rbx
0x1800caea1  mov     r9d, [rbp+57h+var_80]
0x1800caea5  mov     [rsp+0C0h+var_A0], rdx; struct IKsControl *
0x1800caeaa  mov     edx, [rbp+57h+var_7C]
0x1800caead  mov     rax, [rcx]
0x1800caeb0  mov     rax, [rax+28h]
0x1800caeb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caeb9  mov     ebx, eax
0x1800caebb  test    eax, eax
0x1800caebd  jns     short loc_1800CAED3
0x1800caebf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800caec6  jb      loc_1800CB242
0x1800caecc  mov     edx, 13h
0x1800caed1  jmp     short loc_1800CAE77
0x1800caed3  lea     rcx, [rbp+57h+var_78]
0x1800caed7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800caedc  lea     rcx, [rbp+57h+var_78]
0x1800caee0  call    cs:__imp_MFCreateCollection
0x1800caee6  mov     ebx, eax
0x1800caee8  test    eax, eax
0x1800caeea  jns     short loc_1800CAF03
0x1800caeec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800caef3  jb      loc_1800CB242
0x1800caef9  mov     edx, 14h
0x1800caefe  jmp     loc_1800CAE77
0x1800caf03  lea     r15, [rsi+8]
0x1800caf07  mov     rcx, r15
0x1800caf0a  call    ?RemoveAll@?$CTUnkArray@UIFSMemStream@@@@QEAAXXZ; CTUnkArray<IFSMemStream>::RemoveAll(void)
0x1800caf0f  xor     r12d, r12d
0x1800caf12  xor     r14d, r14d
0x1800caf15  cmp     r14d, [rbp+57h+var_80]
0x1800caf19  jnb     loc_1800CB0F9
0x1800caf1f  mov     rdi, [r13+0]
0x1800caf23  lea     rcx, [rbp+57h+var_88]
0x1800caf27  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800caf2e  mov     [rbp+57h+var_88], 0
0x1800caf36  movdqu  [rbp+57h+Buf1], xmm0
0x1800caf3b  mov     rax, [rdi]
0x1800caf3e  mov     [rbp+57h+var_90], 0
0x1800caf46  mov     rbx, [rax+50h]
0x1800caf4a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800caf4f  lea     r8, [rbp+57h+var_88]
0x1800caf53  mov     edx, r14d
0x1800caf56  mov     rcx, rdi
0x1800caf59  mov     rax, rbx
0x1800caf5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caf61  mov     ebx, eax
0x1800caf63  test    eax, eax
0x1800caf65  js      loc_1800CB0B6
0x1800caf6b  mov     rcx, [rbp+57h+var_88]
0x1800caf6f  lea     r8, [rbp+57h+Buf1]
0x1800caf73  lea     rdx, MF_DEVICESTREAM_STREAM_CATEGORY
0x1800caf7a  mov     rax, [rcx]
0x1800caf7d  mov     rax, [rax+50h]
0x1800caf81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800caf86  mov     ebx, eax
0x1800caf88  test    eax, eax
0x1800caf8a  js      loc_1800CB0A6
0x1800caf90  mov     r8d, 10h; Size
0x1800caf96  lea     rdx, _GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba; Buf2
0x1800caf9d  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800cafa1  call    memcmp_0
0x1800cafa6  test    eax, eax
0x1800cafa8  jz      short loc_1800CAFC7
0x1800cafaa  mov     r8d, 10h; Size
0x1800cafb0  lea     rdx, _GUID_fb6c4282_0353_11d1_905f_0000c0cc16ba; Buf2
0x1800cafb7  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800cafbb  or      edi, 0FFFFFFFFh
0x1800cafbe  call    memcmp_0
0x1800cafc3  test    eax, eax
0x1800cafc5  jnz     short loc_1800CAFCA
0x1800cafc7  mov     edi, r12d
0x1800cafca  lea     rcx, [rbp+57h+var_90]
0x1800cafce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cafd3  mov     r9, [rbp+57h+var_68]; struct IMFMediaEventQueue *
0x1800cafd7  lea     rax, [rbp+57h+var_90]
0x1800cafdb  mov     r8, [rbp+57h+var_88]; struct IMFAttributes *
0x1800cafdf  mov     ecx, edi; unsigned int
0x1800cafe1  mov     [rsp+0C0h+var_98], rax; struct IStBasePin **
0x1800cafe6  mov     rax, [rbp+57h+var_60]
0x1800cafea  mov     edx, [rax+r14*4]; unsigned int
0x1800cafee  call    ?CreatePin@CStBasePin@@SAJKKPEAUIMFAttributes@@PEAUIMFMediaEventQueue@@PEAUIKsControl@@PEAPEAUIStBasePin@@@Z; CStBasePin::CreatePin(ulong,ulong,IMFAttributes *,IMFMediaEventQueue *,IKsControl *,IStBasePin * *)
0x1800caff3  mov     ebx, eax
0x1800caff5  test    eax, eax
0x1800caff7  js      loc_1800CB096
0x1800caffd  mov     r13d, [r15+8]
0x1800cb001  mov     rcx, r15
0x1800cb004  lea     edx, [r13+1]
0x1800cb008  call    ?SetSize@?$CTEntryArray@PEAV?$FSCallback@UIFSSourceFrameCallback@@PEAXH@@@@QEAAHKK@Z; CTEntryArray<FSCallback<IFSSourceFrameCallback,void *,int> *>::SetSize(ulong,ulong)
0x1800cb00d  test    eax, eax
0x1800cb00f  jz      short loc_1800CB07F
0x1800cb011  mov     rbx, [rbp+57h+var_90]
0x1800cb015  mov     rax, [r15]
0x1800cb018  mov     [rax+r13*8], rbx
0x1800cb01c  test    rbx, rbx
0x1800cb01f  jz      short loc_1800CB030
0x1800cb021  mov     rax, [rbx]
0x1800cb024  mov     rcx, rbx
0x1800cb027  mov     rax, [rax+8]
0x1800cb02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb030  cmp     edi, 0FFFFFFFFh
0x1800cb033  jz      short loc_1800CB051
0x1800cb035  mov     rcx, [rbp+57h+var_78]
0x1800cb039  mov     rdx, rbx
0x1800cb03c  mov     rax, [rcx]
0x1800cb03f  mov     rax, [rax+28h]
0x1800cb043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cb048  mov     ebx, eax
0x1800cb04a  test    eax, eax
0x1800cb04c  js      short loc_1800CB06F
0x1800cb04e  inc     r12d
0x1800cb051  lea     rcx, [rbp+57h+var_90]
0x1800cb055  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cb05a  lea     rcx, [rbp+57h+var_88]
0x1800cb05e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cb063  inc     r14d
0x1800cb066  lea     r13, [rsi+58h]
0x1800cb06a  jmp     loc_1800CAF15
0x1800cb06f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cb076  jb      short loc_1800CB0E2
0x1800cb078  mov     edx, 19h
0x1800cb07d  jmp     short loc_1800CB0C4
0x1800cb07f  mov     eax, 8007000Eh
0x1800cb084  mov     ebx, eax
0x1800cb086  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cb08d  jb      short loc_1800CB0E2
0x1800cb08f  mov     edx, 18h
0x1800cb094  jmp     short loc_1800CB0C4
0x1800cb096  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cb09d  jb      short loc_1800CB0E2
0x1800cb09f  mov     edx, 17h
0x1800cb0a4  jmp     short loc_1800CB0C4
0x1800cb0a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cb0ad  jb      short loc_1800CB0E2
0x1800cb0af  mov     edx, 16h
0x1800cb0b4  jmp     short loc_1800CB0C4
0x1800cb0b6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cb0bd  jb      short loc_1800CB0E2
0x1800cb0bf  mov     edx, 15h
0x1800cb0c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cb0cb  lea     r8, WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids
0x1800cb0d2  mov     r9, rsi
0x1800cb0d5  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800cb0d9  mov     rcx, [rcx+10h]
0x1800cb0dd  call    WPP_SF_qD
0x1800cb0e2  lea     rcx, [rbp+57h+var_90]
0x1800cb0e6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cb0eb  lea     rcx, [rbp+57h+var_88]
0x1800cb0ef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cb0f4  jmp     loc_1800CB242
0x1800cb0f9  lea     rdi, [rsi+68h]
0x1800cb0fd  mov     rcx, rdi
0x1800cb100  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cb105  mov     rcx, [rbp+57h+var_78]
0x1800cb109  mov     rdx, rdi
0x1800cb10c  call    cs:__imp_MFCreateMuxStreamAttributes
0x1800cb112  mov     ebx, eax
0x1800cb114  test    eax, eax
0x1800cb116  jns     short loc_1800CB12F
0x1800cb118  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800cb11f  jb      loc_1800CB242
0x1800cb125  mov     edx, 1Ah
0x1800cb12a  jmp     loc_1800CAE77
0x1800cb12f  lea     r14, [rsi+50h]
0x1800cb133  mov     rcx, r14
0x1800cb136  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800cb13b  mov     r9, [rbp+57h+var_68]; struct IMFMediaEventQueue *
0x1800cb13f  xor     edx, edx; unsigned int
0x1800cb141  mov     r8, [rdi]; struct IMFAttributes *
0x1800cb144  xor     ecx, ecx; unsigned int
0x1800cb146  mov     [rsp+0C0h+var_98], r14; struct IStBasePin **
0x1800cb14b  call    ?CreatePin@CStBasePin@@SAJKKPEAUIMFAttributes@@PEAUIMFMediaEventQueue@@PEAUIKsControl@@PEAPEAUIStBasePin@@@Z; CStBasePin::CreatePin(ulong,ulong,IMFAttributes *,IMFMediaEventQueue *,IKsControl *,IStBasePin * *)
0x1800cb150  mov     ebx, eax
  ... truncated ...
```
