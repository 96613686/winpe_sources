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
        __int64 a2,
        struct IMFAttributes *a3,
        struct IMFMediaEventQueue *a4)
{
  unsigned int v6; // ebx
  HRESULT (__stdcall *GetUnknown)(IMFAttributes *, const GUID *const, const IID *const, LPVOID *); // rbx
  int v8; // eax
  __int64 v9; // rdx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 **v11; // r13
  __int64 (__fastcall *v12)(_QWORD, GUID *, char *); // rdi
  void *v13; // rbx
  struct IKsControl *v14; // rax
  const struct std::nothrow_t *v15; // rdx
  int Pin; // eax
  __int64 v17; // rdx
  unsigned int v18; // r12d
  __int64 v19; // r14
  __int64 *v20; // rdi
  __int64 v21; // rax
  __int64 (__fastcall *v22)(__int64 *, _QWORD, struct IMFAttributes **); // rbx
  int v23; // eax
  unsigned int v24; // edi
  __int64 v25; // r13
  struct IStBasePin *v26; // rbx
  __int64 v27; // rdx
  _QWORD *v28; // r14
  int updated; // eax
  __int64 v30; // rdx
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, struct IStBasePin **); // rbx
  struct IStBasePin *v33; // rbx
  __int64 (__fastcall *v34)(CStMuxPinMgr *, _QWORD, struct IStBasePin *, _QWORD, _DWORD); // rdi
  unsigned int v35; // eax
  const struct std::nothrow_t *v36; // rdx
  struct IKsControl *v38; // [rsp+20h] [rbp-49h]
  struct IStBasePin *v39; // [rsp+30h] [rbp-39h] BYREF
  struct IMFAttributes *v40; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v41; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v42; // [rsp+44h] [rbp-25h] BYREF
  __int64 v43; // [rsp+48h] [rbp-21h] BYREF
  __int64 (__fastcall ***v44)(_QWORD, GUID *, char *); // [rsp+50h] [rbp-19h] BYREF
  struct IMFMediaEventQueue *v45; // [rsp+58h] [rbp-11h]
  void *v46; // [rsp+60h] [rbp-9h]
  void *v47; // [rsp+68h] [rbp-1h]
  GUID Buf1; // [rsp+70h] [rbp+7h] BYREF

  v42 = 0;
  v45 = a4;
  v41 = 0;
  v44 = 0;
  v43 = 0;
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
  Microsoft::WRL::ComPtr<IMFMediaEventQueue>::operator=((__int64 *)this + 12, (__int64)a4);
  GetUnknown = a3->lpVtbl->GetUnknown;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
  v8 = ((__int64 (__fastcall *)(struct IMFAttributes *, const IID *, GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, char *)))GetUnknown)(
         a3,
         &MF_DEVICEMFT_CONNECTED_FILTER_KSCONTROL,
         &GUID_00000000_0000_0000_c000_000000000046,
         &v44);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_73;
    v9 = 14;
    goto LABEL_7;
  }
  v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v44;
  v11 = (__int64 **)((char *)this + 88);
  v12 = **v44;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 88);
  v8 = v12(v10, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, (char *)this + 88);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_73;
    v9 = 15;
    goto LABEL_7;
  }
  v8 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *, unsigned int *))(**v11 + 32))(*v11, &v42, &v41);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_73;
    v9 = 16;
    goto LABEL_7;
  }
  v47 = operator new[](saturated_mul(v42, 4u));
  v13 = v47;
  if ( !v47 )
  {
    v8 = -2147024882;
    v6 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_73;
    v9 = 17;
LABEL_7:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids, this, v8);
    goto LABEL_73;
  }
  v14 = (struct IKsControl *)operator new[](saturated_mul(v41, 4u));
  v46 = v14;
  v15 = (const struct std::nothrow_t *)v14;
  if ( !v14 )
  {
    Pin = -2147024882;
    v6 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_71;
    v17 = 18;
    goto LABEL_20;
  }
  v38 = v14;
  Pin = (*(__int64 (__fastcall **)(__int64 *, _QWORD, void *, _QWORD))(**v11 + 40))(*v11, v42, v13, v41);
  v6 = Pin;
  if ( Pin < 0 )
  {
    if ( g_wppLevels )
    {
      v17 = 19;
LABEL_20:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids, this, Pin);
      goto LABEL_71;
    }
    goto LABEL_71;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
  Pin = MFCreateCollection(&v43);
  v6 = Pin;
  if ( Pin >= 0 )
  {
    CTUnkArray<IFSMemStream>::RemoveAll((char *)this + 8);
    v18 = 0;
    v19 = 0;
    while ( (unsigned int)v19 < v41 )
    {
      v20 = *v11;
      v40 = 0;
      Buf1 = GUID_00000000_0000_0000_0000_000000000000;
      v21 = *v20;
      v39 = 0;
      v22 = *(__int64 (__fastcall **)(__int64 *, _QWORD, struct IMFAttributes **))(v21 + 80);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
      v23 = v22(v20, (unsigned int)v19, &v40);
      v6 = v23;
      if ( v23 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_53;
        v27 = 21;
        goto LABEL_52;
      }
      v23 = ((__int64 (__fastcall *)(struct IMFAttributes *, const IID *, GUID *))v40->lpVtbl->GetGUID)(
              v40,
              &MF_DEVICESTREAM_STREAM_CATEGORY,
              &Buf1);
      v6 = v23;
      if ( v23 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_53;
        v27 = 22;
LABEL_52:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids, this, v23);
        goto LABEL_53;
      }
      if ( !memcmp_0(&Buf1, &GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba, 0x10u)
        || (v24 = -1, !memcmp_0(&Buf1, &GUID_fb6c4282_0353_11d1_905f_0000c0cc16ba, 0x10u)) )
      {
        v24 = v18;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      v23 = CStBasePin::CreatePin(v24, *((_DWORD *)v46 + v19), v40, v45, v38, &v39);
      v6 = v23;
      if ( v23 < 0 )
      {
        if ( g_wppLevels )
        {
          v27 = 23;
          goto LABEL_52;
        }
LABEL_53:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
        goto LABEL_71;
      }
      v25 = *((unsigned int *)this + 4);
      if ( !(unsigned int)CTEntryArray<FSCallback<IFSSourceFrameCallback,void *,int> *>::SetSize(
                            (char **)this + 1,
                            (const struct std::nothrow_t *)(unsigned int)(v25 + 1)) )
      {
        v23 = -2147024882;
        v6 = -2147024882;
        if ( g_wppLevels )
        {
          v27 = 24;
          goto LABEL_52;
        }
        goto LABEL_53;
      }
      v26 = v39;
      *(_QWORD *)(*((_QWORD *)this + 1) + 8 * v25) = v39;
      if ( v26 )
        (*(void (__fastcall **)(struct IStBasePin *))(*(_QWORD *)v26 + 8LL))(v26);
      if ( v24 != -1 )
      {
        v23 = (*(__int64 (__fastcall **)(__int64, struct IStBasePin *))(*(_QWORD *)v43 + 40LL))(v43, v26);
        v6 = v23;
        if ( v23 < 0 )
        {
          if ( g_wppLevels )
          {
            v27 = 25;
            goto LABEL_52;
          }
          goto LABEL_53;
        }
        ++v18;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
      v19 = (unsigned int)(v19 + 1);
      v11 = (__int64 **)((char *)this + 88);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 104);
    Pin = MFCreateMuxStreamAttributes(v43, (char *)this + 104);
    v6 = Pin;
    if ( Pin < 0 )
    {
      if ( g_wppLevels )
      {
        v17 = 26;
        goto LABEL_20;
      }
      goto LABEL_71;
    }
    v28 = (_QWORD *)((char *)this + 80);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 80);
    Pin = CStBasePin::CreatePin(0, 0, *((struct IMFAttributes **)this + 13), v45, v38, (struct IStBasePin **)this + 10);
    v6 = Pin;
    if ( Pin < 0 )
    {
      if ( g_wppLevels )
      {
        v17 = 27;
        goto LABEL_20;
      }
      goto LABEL_71;
    }
    v39 = 0;
    updated = CStMuxPinMgr::UpdateMediaTypes(this);
    v6 = updated;
    if ( updated >= 0 )
    {
      v31 = *v28;
      v32 = *(__int64 (__fastcall **)(__int64, struct IStBasePin **))(*(_QWORD *)*v28 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      updated = v32(v31, &v39);
      v6 = updated;
      if ( updated >= 0 )
      {
        v33 = v39;
        v34 = *(__int64 (__fastcall **)(CStMuxPinMgr *, _QWORD, struct IStBasePin *, _QWORD, _DWORD))(*(_QWORD *)this + 96LL);
        v35 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v28 + 88LL))(*v28);
        updated = v34(this, v35, v33, 0, 0);
        v6 = updated;
        if ( updated >= 0 || !g_wppLevels )
          goto LABEL_70;
        v30 = 30;
        goto LABEL_69;
      }
      if ( g_wppLevels )
      {
        v30 = 29;
        goto LABEL_69;
      }
    }
    else if ( g_wppLevels )
    {
      v30 = 28;
LABEL_69:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v30,
        &WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids,
        this,
        updated);
    }
LABEL_70:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    goto LABEL_71;
  }
  if ( g_wppLevels )
  {
    v17 = 20;
    goto LABEL_20;
  }
LABEL_71:
  operator delete(v47, v15);
  if ( v46 )
    operator delete(v46, v36);
LABEL_73:
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 31, &WPP_cb699efcc07f36b0bda24e6fac55e876_Traceguids, this, v6);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
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
