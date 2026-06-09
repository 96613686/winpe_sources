# FSSourceMediaStream::ProcessSample(IMFSample *)

- ea: `0x180043d5c`
- end: `0x180044167`
- name: `?ProcessSample@FSSourceMediaStream@@IEAAJPEAUIMFSample@@@Z`
- size: `1035`
- prototype: `int(FSSourceMediaStream *__hidden this, struct IMFSample *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800431a0`
- `0x180044540`

## callees

- `0x180003e20`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x18000a880`
- `0x180017ccc`
- `0x1800411e8`
- `0x180043d5c`
- `0x1800457b8`
- `0x180045bc0`
- `0x18004d714`
- `0x18004d748`
- `0x18005017c`
- `0x180063d30`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004413c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004413c`
- `MFPlat!MFCreateMediaEvent` at `0x180043fd1`
- `MFPlat!MFCreateMediaEvent` at `0x180043fd1`

## pseudocode

```c
__int64 __fastcall FSSourceMediaStream::ProcessSample(FSSourceMediaStream *this, struct IMFSample *a2)
{
  char v2; // r15
  int v5; // ebx
  __int64 v6; // rdx
  int v7; // eax
  HRESULT v8; // eax
  __int64 v9; // rdx
  struct IMFSample *v10; // rsi
  __int64 v11; // rdx
  __int64 *v12; // rdx
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  FSString *v17; // rax
  const char *String; // rax
  int v19; // edx
  int v20; // r8d
  __int64 v22; // [rsp+50h] [rbp-49h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+58h] [rbp-41h] BYREF
  struct IMFSample *v24; // [rsp+60h] [rbp-39h] BYREF
  PROPVARIANT pvValue[2]; // [rsp+68h] [rbp-31h] BYREF
  __int64 v26; // [rsp+78h] [rbp-21h]
  _BYTE v27[24]; // [rsp+80h] [rbp-19h] BYREF
  _OWORD v28[2]; // [rsp+98h] [rbp-1h] BYREF
  __int64 v29; // [rsp+B8h] [rbp+1Fh]

  v2 = 0;
  LODWORD(v22) = 0;
  v29 = 0;
  v26 = 0;
  v24 = 0;
  ppEvent = 0;
  memset(v28, 0, sizeof(v28));
  *(_OWORD *)pvValue = 0;
  if ( a2 )
  {
    if ( !*((_QWORD *)this + 33) )
    {
      v5 = -2147418113;
      if ( !g_wppLevels )
        goto LABEL_37;
      v6 = 129;
      goto LABEL_4;
    }
    v7 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *, _OWORD *, __int64, _QWORD))a2->lpVtbl->GetBlob)(
           a2,
           MFSampleExtension_FSMediaTypeInfo,
           v28,
           40,
           0);
    if ( v7 >= 0 && LODWORD(v28[0]) == *((_DWORD *)this + 52) )
    {
      v8 = FSCloneSample(a2, &v24);
      v5 = v8;
      if ( v8 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_36;
        v9 = 131;
        goto LABEL_13;
      }
      v10 = v24;
      v8 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))v24->lpVtbl->DeleteItem)(
             v24,
             MFSampleExtension_FSMediaTypeInfo);
      v5 = v8;
      if ( v8 >= 0 )
      {
        v11 = *((_QWORD *)this + 31);
        v22 = 0;
        wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(&v22, *(_QWORD *)(v11 + 16));
        v12 = (__int64 *)*((_QWORD *)this + 31);
        v13 = (__int64 *)v12[1];
        v14 = *v12;
        *v13 = *v12;
        *(_QWORD *)(v14 + 8) = v13;
        utl::_ContainerBase<wil::com_ptr_t<IMFSample,wil::err_returncode_policy>,utl::allocator<wil::com_ptr_t<IMFSample,wil::err_returncode_policy>>>::_DeleteNode<utl::_DlistNode<wil::com_ptr_t<IMFSample,wil::err_returncode_policy>>>(
          (__int64)v13,
          (__int64)v12);
        --*((_QWORD *)this + 33);
        v15 = ((__int64 (__fastcall *)(struct IMFSample *, const GUID *, __int64))v10->lpVtbl->SetUnknown)(
                v10,
                &MFSampleExtension_Token,
                v22);
        v5 = v15;
        if ( v15 >= 0 )
        {
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v22);
          v8 = ((__int64 (__fastcall *)(struct IMFSample *, GUID *, PROPVARIANT *))v10->lpVtbl->QueryInterface)(
                 v10,
                 &GUID_00000000_0000_0000_c000_000000000046,
                 &pvValue[1]);
          v5 = v8;
          if ( v8 >= 0 )
          {
            LOWORD(pvValue[0]) = 13;
            wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppEvent);
            v8 = MFCreateMediaEvent(0xD5u, &GUID_00000000_0000_0000_0000_000000000000, 0, pvValue, &ppEvent);
            v5 = v8;
            if ( v8 >= 0 )
            {
              v8 = (*(__int64 (__fastcall **)(_QWORD, IMFMediaEvent *))(**((_QWORD **)this + 13) + 48LL))(
                     *((_QWORD *)this + 13),
                     ppEvent);
              v5 = v8;
              if ( v8 >= 0 )
              {
                ++*((_QWORD *)this + 38);
                if ( (Microsoft_Windows_MF_FrameServerEnableBits & 2) != 0 )
                {
                  v22 = 0;
                  ((void (__fastcall *)(struct IMFSample *, __int64 *))v10->lpVtbl->GetSampleTime)(v10, &v22);
                  if ( (Microsoft_Windows_MF_FrameServerEnableBits & 2) != 0 )
                    McTemplateU0pi_EventWriteTransfer(
                      v16,
                      MF_FrameServer_FSSourceMediaStream_ProcessSample_Start,
                      this,
                      v22);
                }
              }
              else if ( g_wppLevels )
              {
                v9 = 136;
                goto LABEL_13;
              }
            }
            else if ( g_wppLevels )
            {
              v9 = 135;
              goto LABEL_13;
            }
          }
          else if ( g_wppLevels )
          {
            v9 = 134;
            goto LABEL_13;
          }
        }
        else
        {
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              133,
              &WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids,
              this,
              v15);
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v22);
        }
      }
      else if ( g_wppLevels )
      {
        v9 = 132;
LABEL_13:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids, this, v8);
      }
    }
    else
    {
      if ( byte_18010EC4D )
        WPP_SF_qddd(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          130,
          &WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids,
          this,
          v7,
          v28[0],
          *((_DWORD *)this + 52));
      v5 = 0;
    }
LABEL_36:
    if ( v5 >= 0 )
      goto LABEL_41;
    goto LABEL_37;
  }
  v5 = -2147024809;
  if ( g_wppLevels )
  {
    v6 = 128;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids, this, v5);
  }
LABEL_37:
  if ( byte_18010EC4D )
  {
    v17 = SampleTrace::SampleTrace((SampleTrace *)v27, a2);
    String = FSString::GetString(v17);
    WPP_SF_qDiiIs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v19,
      v20,
      (_DWORD)this,
      v5,
      *((_QWORD *)this + 37),
      *((_QWORD *)this + 38),
      *((_QWORD *)this + 33),
      (__int64)String);
    v2 = 1;
  }
  if ( (v2 & 1) != 0 )
    FSString::~FSString((FSString *)v27, (const struct std::nothrow_t *)a2);
LABEL_41:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppEvent);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v24);
  PropVariantClear(pvValue);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180043d5c  mov     [rsp-8+arg_10], rbx
0x180043d61  push    rbp
0x180043d62  push    rsi
0x180043d63  push    rdi
0x180043d64  push    r14
0x180043d66  push    r15
0x180043d68  lea     rbp, [rsp-37h]
0x180043d6d  sub     rsp, 0D0h
0x180043d74  mov     rax, cs:__security_cookie
0x180043d7b  xor     rax, rsp
0x180043d7e  mov     [rbp+57h+var_30], rax
0x180043d82  xor     eax, eax
0x180043d84  xorps   xmm0, xmm0
0x180043d87  xor     r15d, r15d
0x180043d8a  mov     r14, rdx
0x180043d8d  mov     dword ptr [rbp+57h+var_A0], r15d
0x180043d91  mov     rdi, rcx
0x180043d94  mov     [rbp+57h+var_38], rax
0x180043d98  mov     [rbp+57h+var_78], rax
0x180043d9c  mov     [rbp+57h+var_90], rax
0x180043da0  mov     [rbp+57h+var_98], rax
0x180043da4  movups  [rbp+57h+var_58], xmm0
0x180043da8  movups  [rbp+57h+var_48], xmm0
0x180043dac  movups  xmmword ptr [rbp+57h+pvValue], xmm0
0x180043db0  test    rdx, rdx
0x180043db3  jnz     short loc_180043DEF
0x180043db5  mov     ebx, 80070057h
0x180043dba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043dc1  jb      loc_1800440B1
0x180043dc7  mov     edx, 80h
0x180043dcc  mov     rcx, cs:WPP_GLOBAL_Control
0x180043dd3  lea     r8, WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids
0x180043dda  mov     r9, rdi
0x180043ddd  mov     dword ptr [rsp+0F0h+ppEvent], ebx
0x180043de1  mov     rcx, [rcx+10h]
0x180043de5  call    WPP_SF_qD
0x180043dea  jmp     loc_1800440B1
0x180043def  cmp     [rcx+108h], rax
0x180043df6  jnz     short loc_180043E11
0x180043df8  mov     ebx, 8000FFFFh
0x180043dfd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043e04  jb      loc_1800440B1
0x180043e0a  mov     edx, 81h
0x180043e0f  jmp     short loc_180043DCC
0x180043e11  mov     rax, [rdx]
0x180043e14  lea     r8, [rbp+57h+var_58]
0x180043e18  mov     r9d, 28h ; '('
0x180043e1e  mov     [rsp+0F0h+ppEvent], r15
0x180043e23  lea     rdx, MFSampleExtension_FSMediaTypeInfo
0x180043e2a  mov     rcx, r14
0x180043e2d  mov     rax, [rax+78h]
0x180043e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e36  mov     ecx, dword ptr [rbp+57h+var_58]
0x180043e39  mov     r8d, eax
0x180043e3c  test    eax, eax
0x180043e3e  js      loc_18004406D
0x180043e44  cmp     ecx, [rdi+0D0h]
0x180043e4a  jnz     loc_18004406D
0x180043e50  lea     rdx, [rbp+57h+var_90]; struct IMFSample **
0x180043e54  mov     rcx, r14; struct IMFSample *
0x180043e57  call    ?FSCloneSample@@YAJPEAUIMFSample@@PEAPEAU1@@Z; FSCloneSample(IMFSample *,IMFSample * *)
0x180043e5c  mov     ebx, eax
0x180043e5e  test    eax, eax
0x180043e60  jns     short loc_180043E97
0x180043e62  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043e69  jb      loc_1800440AD
0x180043e6f  mov     edx, 83h
0x180043e74  mov     rcx, cs:WPP_GLOBAL_Control
0x180043e7b  lea     r8, WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids
0x180043e82  mov     r9, rdi
0x180043e85  mov     dword ptr [rsp+0F0h+ppEvent], eax
0x180043e89  mov     rcx, [rcx+10h]
0x180043e8d  call    WPP_SF_qD
0x180043e92  jmp     loc_1800440AD
0x180043e97  mov     rsi, [rbp+57h+var_90]
0x180043e9b  lea     rdx, MFSampleExtension_FSMediaTypeInfo
0x180043ea2  mov     rcx, rsi
0x180043ea5  mov     rax, [rsi]
0x180043ea8  mov     rax, [rax+98h]
0x180043eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043eb4  mov     ebx, eax
0x180043eb6  test    eax, eax
0x180043eb8  jns     short loc_180043ECE
0x180043eba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043ec1  jb      loc_1800440AD
0x180043ec7  mov     edx, 84h
0x180043ecc  jmp     short loc_180043E74
0x180043ece  mov     rdx, [rdi+0F8h]
0x180043ed5  lea     rcx, [rbp+57h+var_A0]
0x180043ed9  mov     [rbp+57h+var_A0], r15
0x180043edd  mov     rdx, [rdx+10h]
0x180043ee1  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x180043ee6  mov     rdx, [rdi+0F8h]
0x180043eed  mov     rcx, [rdx+8]
0x180043ef1  mov     rax, [rdx]
0x180043ef4  mov     [rcx], rax
0x180043ef7  mov     [rax+8], rcx
0x180043efb  call    ??$_DeleteNode@U?$_DlistNode@V?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@@utl@@@?$_ContainerBase@V?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@@utl@@@utl@@IEAAXPEAU?$_DlistNode@V?$com_ptr_t@UIMFSample@@Uerr_returncode_policy@wil@@@wil@@@1@@Z; utl::_ContainerBase<wil::com_ptr_t<IMFSample,wil::err_returncode_policy>,utl::allocator<wil::com_ptr_t<IMFSample,wil::err_returncode_policy>>>::_DeleteNode<utl::_DlistNode<wil::com_ptr_t<IMFSample,wil::err_returncode_policy>>>(utl::_DlistNode<wil::com_ptr_t<IMFSample,wil::err_returncode_policy>> *)
0x180043f00  dec     qword ptr [rdi+108h]
0x180043f07  lea     rdx, MFSampleExtension_Token
0x180043f0e  mov     rax, [rsi]
0x180043f11  mov     rcx, rsi
0x180043f14  mov     r8, [rbp+57h+var_A0]
0x180043f18  mov     rax, [rax+0D8h]
0x180043f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f24  mov     ebx, eax
0x180043f26  test    eax, eax
0x180043f28  jns     short loc_180043F64
0x180043f2a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043f31  jb      short loc_180043F56
0x180043f33  mov     rcx, cs:WPP_GLOBAL_Control
0x180043f3a  lea     r8, WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids
0x180043f41  mov     edx, 85h
0x180043f46  mov     dword ptr [rsp+0F0h+ppEvent], eax
0x180043f4a  mov     r9, rdi
0x180043f4d  mov     rcx, [rcx+10h]
0x180043f51  call    WPP_SF_qD
0x180043f56  lea     rcx, [rbp+57h+var_A0]; void *
0x180043f5a  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180043f5f  jmp     loc_1800440AD
0x180043f64  lea     rcx, [rbp+57h+var_A0]; void *
0x180043f68  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180043f6d  mov     rax, [rsi]
0x180043f70  lea     r8, [rbp+57h+pvValue+8]
0x180043f74  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180043f7b  mov     rcx, rsi
0x180043f7e  mov     rax, [rax]
0x180043f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f86  mov     ebx, eax
0x180043f88  test    eax, eax
0x180043f8a  jns     short loc_180043FA3
0x180043f8c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043f93  jb      loc_1800440AD
0x180043f99  mov     edx, 86h
0x180043f9e  jmp     loc_180043E74
0x180043fa3  mov     eax, 0Dh
0x180043fa8  lea     rcx, [rbp+57h+var_98]
0x180043fac  mov     word ptr [rbp+57h+pvValue], ax
0x180043fb0  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180043fb5  lea     rax, [rbp+57h+var_98]
0x180043fb9  xor     r8d, r8d; hrStatus
0x180043fbc  lea     r9, [rbp+57h+pvValue]; pvValue
0x180043fc0  mov     [rsp+0F0h+ppEvent], rax; ppEvent
0x180043fc5  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x180043fcc  mov     ecx, 0D5h; met
0x180043fd1  call    cs:__imp_MFCreateMediaEvent
0x180043fd7  mov     ebx, eax
0x180043fd9  test    eax, eax
0x180043fdb  jns     short loc_180043FF4
0x180043fdd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180043fe4  jb      loc_1800440AD
0x180043fea  mov     edx, 87h
0x180043fef  jmp     loc_180043E74
0x180043ff4  mov     rcx, [rdi+68h]
0x180043ff8  mov     rdx, [rbp+57h+var_98]
0x180043ffc  mov     rax, [rcx]
0x180043fff  mov     rax, [rax+30h]
0x180044003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044008  mov     ebx, eax
0x18004400a  test    eax, eax
0x18004400c  jns     short loc_180044025
0x18004400e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180044015  jb      loc_1800440AD
0x18004401b  mov     edx, 88h
0x180044020  jmp     loc_180043E74
0x180044025  inc     qword ptr [rdi+130h]
0x18004402c  test    cs:Microsoft_Windows_MF_FrameServerEnableBits, 2
0x180044033  jz      short loc_1800440AD
0x180044035  mov     [rbp+57h+var_A0], r15
0x180044039  lea     rdx, [rbp+57h+var_A0]
0x18004403d  mov     rax, [rsi]
0x180044040  mov     rcx, rsi
0x180044043  mov     rax, [rax+118h]
0x18004404a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004404f  test    cs:Microsoft_Windows_MF_FrameServerEnableBits, 2
0x180044056  jz      short loc_1800440AD
0x180044058  mov     r9, [rbp+57h+var_A0]
0x18004405c  lea     rdx, MF_FrameServer_FSSourceMediaStream_ProcessSample_Start
0x180044063  mov     r8, rdi
0x180044066  call    McTemplateU0pi_EventWriteTransfer
0x18004406b  jmp     short loc_1800440AD
0x18004406d  cmp     cs:byte_18010EC4D, 1
0x180044074  jb      short loc_1800440AB
0x180044076  mov     eax, [rdi+0D0h]
0x18004407c  mov     edx, 82h
0x180044081  mov     dword ptr [rsp+0F0h+var_C0], eax
0x180044085  mov     r9, rdi
0x180044088  mov     dword ptr [rsp+0F0h+var_C8], ecx
0x18004408c  mov     rcx, cs:WPP_GLOBAL_Control
0x180044093  mov     dword ptr [rsp+0F0h+ppEvent], r8d
0x180044098  lea     r8, WPP_a9a3e2c9ce9f3089c592519dee6be839_Traceguids
0x18004409f  mov     rcx, [rcx+0D8h]
0x1800440a6  call    WPP_SF_qddd
0x1800440ab  xor     ebx, ebx
0x1800440ad  test    ebx, ebx
0x1800440af  jns     short loc_180044126
0x1800440b1  cmp     cs:byte_18010EC4D, 1
0x1800440b8  jb      short loc_180044117
0x1800440ba  mov     rdx, r14; struct IMFSample *
0x1800440bd  lea     rcx, [rbp+57h+var_70]; this
0x1800440c1  call    ??0SampleTrace@@QEAA@PEAUIMFSample@@@Z; SampleTrace::SampleTrace(IMFSample *)
0x1800440c6  mov     rcx, rax; this
0x1800440c9  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x1800440ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800440d5  mov     r9, rdi
0x1800440d8  mov     [rsp+0F0h+var_B0], rax
0x1800440dd  mov     rax, [rdi+108h]
0x1800440e4  mov     [rsp+0F0h+var_B8], rax
0x1800440e9  mov     rax, [rdi+130h]
0x1800440f0  mov     rcx, [rcx+0D8h]
0x1800440f7  mov     [rsp+0F0h+var_C0], rax
0x1800440fc  mov     rax, [rdi+128h]
0x180044103  mov     [rsp+0F0h+var_C8], rax
0x180044108  mov     dword ptr [rsp+0F0h+ppEvent], ebx
0x18004410c  call    WPP_SF_qDiiIs
0x180044111  mov     r15d, 1
0x180044117  test    r15b, 1
0x18004411b  jz      short loc_180044126
0x18004411d  lea     rcx, [rbp+57h+var_70]; this
0x180044121  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180044126  lea     rcx, [rbp+57h+var_98]; void *
0x18004412a  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18004412f  lea     rcx, [rbp+57h+var_90]; void *
0x180044133  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180044138  lea     rcx, [rbp+57h+pvValue]; pvar
0x18004413c  call    cs:__imp_PropVariantClear
0x180044142  mov     eax, ebx
0x180044144  mov     rcx, [rbp+57h+var_30]
0x180044148  xor     rcx, rsp; StackCookie
0x18004414b  call    __security_check_cookie
0x180044150  mov     rbx, [rsp+0F0h+arg_10]
0x180044158  add     rsp, 0D0h
0x18004415f  pop     r15
0x180044161  pop     r14
0x180044163  pop     rdi
0x180044164  pop     rsi
0x180044165  pop     rbp
0x180044166  retn
```
