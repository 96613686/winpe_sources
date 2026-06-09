# CSystemAudioDeviceBase::ActivateEndpoint(AUDIO_DEVICE_PIPE_DESCRIPTOR *)

- ea: `0x140055904`
- end: `0x140055cab`
- name: `?ActivateEndpoint@CSystemAudioDeviceBase@@IEAAJPEAUAUDIO_DEVICE_PIPE_DESCRIPTOR@@@Z`
- size: `935`
- prototype: `__int64 __fastcall(CSystemAudioDeviceBase *__hidden this, struct AUDIO_DEVICE_PIPE_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x140055490`
- `0x14007f400`

## callees

- `0x140008124`
- `0x140029be4`
- `0x1400332b4`
- `0x14003b9a8`
- `0x140055904`
- `0x140055de0`
- `0x14005e150`
- `0x14007e764`
- `0x1400b5010`

## import_xrefs

- `MMDevAPI!__imp_GetSessionIdFromEndpointId` at `0x140055a3a`
- `MMDevAPI!__imp_GetSessionIdFromEndpointId` at `0x140055a9b`
- `MMDevAPI!__imp_GetSessionIdFromEndpointId` at `0x140055a3a`
- `MMDevAPI!__imp_GetSessionIdFromEndpointId` at `0x140055a9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140055a15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140055a80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140055a15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140055a80`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005598e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14005598e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140055bf6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140055bf6`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSystemAudioDeviceBase::ActivateEndpoint(
        CSystemAudioDeviceBase *this,
        struct AUDIO_DEVICE_PIPE_DESCRIPTOR *a2)
{
  HRESULT v4; // ebx
  struct IUnknown *v5; // rcx
  int v6; // eax
  unsigned int *v7; // rsi
  __int64 v8; // rcx
  char *v9; // rbx
  int v10; // eax
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rax
  _QWORD *v12; // r14
  __int64 (__fastcall ***v14)(_QWORD, GUID *, char *); // [rsp+90h] [rbp-9h] BYREF
  __int64 (__fastcall ***v15)(_QWORD, GUID *, char *); // [rsp+98h] [rbp-1h] BYREF
  LPVOID ppv; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v17; // [rsp+A8h] [rbp+Fh] BYREF
  PROPVARIANT pvar[2]; // [rsp+B0h] [rbp+17h] BYREF
  char *v19; // [rsp+C0h] [rbp+27h]
  struct IUnknown *v20; // [rsp+110h] [rbp+77h] BYREF
  struct IUnknown *v21; // [rsp+118h] [rbp+7Fh] BYREF

  ppv = 0;
  v20 = 0;
  v17 = 0;
  v15 = 0;
  v14 = 0;
  v21 = 0;
  *(_OWORD *)pvar = 0;
  v19 = 0;
  v4 = ValidateDevicePipeDescriptor(a2);
  if ( v4 >= 0 )
  {
    v4 = CoCreateInstance(
           &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
           0,
           0x17u,
           &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
           &ppv);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, struct IUnknown **))(*(_QWORD *)ppv + 40LL))(
             ppv,
             *((_QWORD *)a2 + 7),
             &v20);
      if ( v4 >= 0 )
      {
        v5 = v21;
        if ( v21 != v20 )
        {
          ATL::AtlComQIPtrAssign(&v21, v20, &GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21);
          v5 = v21;
        }
        if ( !v5 )
        {
          v4 = -2147467262;
          goto LABEL_21;
        }
        LOWORD(pvar[0]) = 65;
        v6 = ((__int64 (__fastcall *)(struct IUnknown *))v5->lpVtbl[2].QueryInterface)(v5);
        v7 = (unsigned int *)*((_QWORD *)a2 + 1);
        v8 = *((unsigned __int16 *)v7 + 8);
        if ( v6 )
        {
          v9 = (char *)CoTaskMemAlloc(v8 + 32);
          if ( !v9 )
            goto LABEL_10;
          *(_DWORD *)v9 = *((unsigned __int16 *)v7 + 8) + 32;
          *((_DWORD *)v9 + 1) = GetSessionIdFromEndpointId(*((_QWORD *)a2 + 7));
          *((_DWORD *)v9 + 2) = *((_DWORD *)a2 + 25);
          memcpy_0(v9 + 12, v7, *((unsigned __int16 *)v7 + 8) + 18LL);
          v10 = *((unsigned __int16 *)v7 + 8) + 32;
        }
        else
        {
          v9 = (char *)CoTaskMemAlloc(v8 + 64);
          if ( !v9 )
          {
LABEL_10:
            v4 = -2147024882;
            goto LABEL_21;
          }
          *(_DWORD *)v9 = *((unsigned __int16 *)v7 + 8) + 64;
          *((_DWORD *)v9 + 1) = GetSessionIdFromEndpointId(*((_QWORD *)a2 + 7));
          *((_DWORD *)v9 + 2) = *((_DWORD *)a2 + 25);
          *(_OWORD *)(v9 + 12) = *(_OWORD *)((char *)a2 + 104);
          *(_OWORD *)(v9 + 28) = *(_OWORD *)((char *)a2 + 148);
          memcpy_0(v9 + 44, v7, *((unsigned __int16 *)v7 + 8) + 18LL);
          v10 = *((unsigned __int16 *)v7 + 8) + 64;
        }
        v19 = v9;
        LODWORD(pvar[1]) = v10;
        QueryInterface = v20->lpVtbl[1].QueryInterface;
        if ( *((_DWORD *)a2 + 18) )
        {
          v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64, PROPVARIANT *, __int64 (__fastcall ****)(_QWORD, GUID *, char *)))QueryInterface)(
                 v20,
                 &GUID_8026ab61_92b2_43c1_a1df_5c37ebd08d82,
                 1,
                 pvar,
                 &v15);
          if ( v4 < 0 )
            goto LABEL_21;
          v12 = (_QWORD *)((char *)this + 88);
          v4 = (**v15)(v15, &GUID_30a99515_1527_4451_af9f_00c5f0234daf, (char *)this + 88);
        }
        else
        {
          v4 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64, PROPVARIANT *, __int64 (__fastcall ****)(_QWORD, GUID *, char *)))QueryInterface)(
                 v20,
                 &GUID_8fa906e4_c31c_4e31_932e_19a66385e9aa,
                 1,
                 pvar,
                 &v14);
          if ( v4 < 0 )
            goto LABEL_21;
          v12 = (_QWORD *)((char *)this + 88);
          v4 = (**v14)(v14, &GUID_30a99515_1527_4451_af9f_00c5f0234daf, (char *)this + 88);
        }
        AEWMILOG_ENDPOINT_ACTIVATION(
          *((_DWORD *)a2 + 20) != 0,
          this,
          *((_WORD *)v7 + 7),
          *(_WORD *)v7,
          *((_DWORD *)a2 + 34),
          *((_DWORD *)a2 + 25),
          *((_DWORD *)a2 + 18),
          *((_DWORD *)a2 + 35),
          *(unsigned __int16 *)v7,
          v7[1],
          *((unsigned __int16 *)v7 + 7),
          *((unsigned __int16 *)v7 + 1),
          *((_DWORD *)a2 + 8),
          *((_DWORD *)this + 20),
          *((_DWORD *)a2 + 20) != 0,
          *((_DWORD *)a2 + 24),
          v4);
        if ( v4 >= 0 )
          (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v12 + 48LL))(*v12, *((unsigned int *)this + 20));
      }
    }
  }
LABEL_21:
  PropVariantClear(pvar);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_f439333ca32d38002cb7cfdad9c030a3_Traceguids,
        v4,
        (__int64)"CSystemAudioDeviceBase::ActivateEndpoint");
    }
    AudDGTraceLoggingErrorHelper("CSystemAudioDeviceBase::ActivateEndpoint", 0x10Bu, v4);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140055904  mov     [rsp-8+arg_0], rbx
0x140055909  push    rbp
0x14005590a  push    rsi
0x14005590b  push    rdi
0x14005590c  push    r14
0x14005590e  push    r15
0x140055910  lea     rbp, [rsp-37h]
0x140055915  sub     rsp, 0D0h
0x14005591c  mov     rdi, rdx
0x14005591f  mov     r15, rcx
0x140055922  mov     [rbp+57h+var_50], 0
0x14005592a  mov     [rbp+57h+arg_10], 0
0x140055932  mov     [rbp+57h+var_48], 0
0x14005593a  mov     [rbp+57h+var_58], 0
0x140055942  mov     [rbp+57h+var_60], 0
0x14005594a  mov     [rbp+57h+arg_18], 0
0x140055952  xorps   xmm0, xmm0
0x140055955  xor     eax, eax
0x140055957  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x14005595b  mov     [rbp+57h+var_30], rax
0x14005595f  mov     rcx, rdx; struct AUDIO_DEVICE_PIPE_DESCRIPTOR *
0x140055962  call    ?ValidateDevicePipeDescriptor@@YAJPEAUAUDIO_DEVICE_PIPE_DESCRIPTOR@@@Z; ValidateDevicePipeDescriptor(AUDIO_DEVICE_PIPE_DESCRIPTOR *)
0x140055967  mov     ebx, eax
0x140055969  test    eax, eax
0x14005596b  js      loc_140055BF2
0x140055971  lea     rax, [rbp+57h+var_50]
0x140055975  mov     [rsp+0F0h+ppv], rax; ppv
0x14005597a  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x140055981  xor     edx, edx; pUnkOuter
0x140055983  lea     r8d, [rdx+17h]; dwClsContext
0x140055987  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x14005598e  call    cs:__imp_CoCreateInstance
0x140055994  mov     ebx, eax
0x140055996  test    eax, eax
0x140055998  js      loc_140055BF2
0x14005599e  mov     rcx, [rbp+57h+var_50]
0x1400559a2  mov     rax, [rcx]
0x1400559a5  lea     r8, [rbp+57h+arg_10]
0x1400559a9  mov     rdx, [rdi+38h]
0x1400559ad  mov     rax, [rax+28h]
0x1400559b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400559b6  mov     ebx, eax
0x1400559b8  test    eax, eax
0x1400559ba  js      loc_140055BF2
0x1400559c0  mov     rdx, [rbp+57h+arg_10]; struct IUnknown *
0x1400559c4  mov     rcx, [rbp+57h+arg_18]
0x1400559c8  cmp     rcx, rdx
0x1400559cb  jz      short loc_1400559E1
0x1400559cd  lea     r8, _GUID_67c5fc9c_29e1_4154_8307_84ed8edb5a21; struct _GUID *
0x1400559d4  lea     rcx, [rbp+57h+arg_18]; struct IUnknown **
0x1400559d8  call    ?AtlComQIPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@AEBU_GUID@@@Z; ATL::AtlComQIPtrAssign(IUnknown * *,IUnknown *,_GUID const &)
0x1400559dd  mov     rcx, [rbp+57h+arg_18]
0x1400559e1  test    rcx, rcx
0x1400559e4  jnz     short loc_1400559F0
0x1400559e6  mov     ebx, 80004002h
0x1400559eb  jmp     loc_140055BF2
0x1400559f0  mov     eax, 41h ; 'A'
0x1400559f5  mov     word ptr [rbp+57h+pvar], ax
0x1400559f9  mov     rax, [rcx]
0x1400559fc  mov     rax, [rax+30h]
0x140055a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055a05  mov     rsi, [rdi+8]
0x140055a09  movzx   ecx, word ptr [rsi+10h]
0x140055a0d  test    eax, eax
0x140055a0f  jnz     short loc_140055A7C
0x140055a11  add     rcx, 40h ; '@'; cb
0x140055a15  call    cs:__imp_CoTaskMemAlloc
0x140055a1b  mov     rbx, rax
0x140055a1e  test    rax, rax
0x140055a21  jnz     short loc_140055A2D
0x140055a23  mov     ebx, 8007000Eh
0x140055a28  jmp     loc_140055BF2
0x140055a2d  movzx   eax, word ptr [rsi+10h]
0x140055a31  add     eax, 40h ; '@'
0x140055a34  mov     [rbx], eax
0x140055a36  mov     rcx, [rdi+38h]
0x140055a3a  call    cs:__imp_GetSessionIdFromEndpointId
0x140055a40  mov     [rbx+4], eax
0x140055a43  mov     eax, [rdi+64h]
0x140055a46  mov     [rbx+8], eax
0x140055a49  movups  xmm0, xmmword ptr [rdi+68h]
0x140055a4d  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x140055a52  movups  xmm1, xmmword ptr [rdi+94h]
0x140055a59  movdqu  xmmword ptr [rbx+1Ch], xmm1
0x140055a5e  movzx   r8d, word ptr [rsi+10h]
0x140055a63  add     r8, 12h; Size
0x140055a67  lea     rcx, [rbx+2Ch]; void *
0x140055a6b  mov     rdx, rsi; Src
0x140055a6e  call    memcpy_0
0x140055a73  movzx   eax, word ptr [rsi+10h]
0x140055a77  add     eax, 40h ; '@'
0x140055a7a  jmp     short loc_140055AC6
0x140055a7c  add     rcx, 20h ; ' '; cb
0x140055a80  call    cs:__imp_CoTaskMemAlloc
0x140055a86  mov     rbx, rax
0x140055a89  test    rax, rax
0x140055a8c  jz      short loc_140055A23
0x140055a8e  movzx   eax, word ptr [rsi+10h]
0x140055a92  add     eax, 20h ; ' '
0x140055a95  mov     [rbx], eax
0x140055a97  mov     rcx, [rdi+38h]
0x140055a9b  call    cs:__imp_GetSessionIdFromEndpointId
0x140055aa1  mov     [rbx+4], eax
0x140055aa4  mov     eax, [rdi+64h]
0x140055aa7  mov     [rbx+8], eax
0x140055aaa  movzx   r8d, word ptr [rsi+10h]
0x140055aaf  add     r8, 12h; Size
0x140055ab3  lea     rcx, [rbx+0Ch]; void *
0x140055ab7  mov     rdx, rsi; Src
0x140055aba  call    memcpy_0
0x140055abf  movzx   eax, word ptr [rsi+10h]
0x140055ac3  add     eax, 20h ; ' '
0x140055ac6  mov     [rbp+57h+var_30], rbx
0x140055aca  mov     dword ptr [rbp+57h+pvar+8], eax
0x140055acd  mov     rcx, [rbp+57h+arg_10]
0x140055ad1  lea     r9, [rbp+57h+pvar]
0x140055ad5  mov     r8d, 1
0x140055adb  mov     rax, [rcx]
0x140055ade  mov     rax, [rax+18h]
0x140055ae2  cmp     dword ptr [rdi+48h], 0
0x140055ae6  jnz     short loc_140055B28
0x140055ae8  lea     rdx, [rbp+57h+var_60]
0x140055aec  mov     [rsp+0F0h+ppv], rdx
0x140055af1  lea     rdx, _GUID_8fa906e4_c31c_4e31_932e_19a66385e9aa
0x140055af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055afd  mov     ebx, eax
0x140055aff  test    eax, eax
0x140055b01  js      loc_140055BF2
0x140055b07  mov     rcx, [rbp+57h+var_60]
0x140055b0b  lea     r14, [r15+58h]
0x140055b0f  mov     rax, [rcx]
0x140055b12  mov     r8, r14
0x140055b15  lea     rdx, _GUID_30a99515_1527_4451_af9f_00c5f0234daf
0x140055b1c  mov     rax, [rax]
0x140055b1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055b24  mov     ebx, eax
0x140055b26  jmp     short loc_140055B66
0x140055b28  lea     rdx, [rbp+57h+var_58]
0x140055b2c  mov     [rsp+0F0h+ppv], rdx
0x140055b31  lea     rdx, _GUID_8026ab61_92b2_43c1_a1df_5c37ebd08d82
0x140055b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055b3d  mov     ebx, eax
0x140055b3f  test    eax, eax
0x140055b41  js      loc_140055BF2
0x140055b47  mov     rcx, [rbp+57h+var_58]
0x140055b4b  lea     r14, [r15+58h]
0x140055b4f  mov     rax, [rcx]
0x140055b52  mov     r8, r14
0x140055b55  lea     rdx, _GUID_30a99515_1527_4451_af9f_00c5f0234daf
0x140055b5c  mov     rax, [rax]
0x140055b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055b64  mov     ebx, eax
0x140055b66  xor     ecx, ecx
0x140055b68  cmp     [rdi+50h], ecx
0x140055b6b  setnz   cl; unsigned int
0x140055b6e  movzx   edx, word ptr [rsi+2]
0x140055b72  movzx   r8d, word ptr [rsi+0Eh]; unsigned __int8
0x140055b77  movzx   r9d, word ptr [rsi]; unsigned __int8
0x140055b7b  mov     [rsp+0F0h+var_70], ebx; unsigned int
0x140055b82  mov     eax, [rdi+60h]
0x140055b85  mov     [rsp+0F0h+var_78], eax; unsigned int
0x140055b89  mov     [rsp+0F0h+var_80], ecx; unsigned int
0x140055b8d  mov     eax, [r15+50h]
0x140055b91  mov     [rsp+0F0h+var_88], eax; unsigned int
0x140055b95  mov     eax, [rdi+20h]
0x140055b98  mov     [rsp+0F0h+var_90], eax; unsigned int
0x140055b9c  mov     [rsp+0F0h+var_98], edx; unsigned int
0x140055ba0  mov     [rsp+0F0h+var_A0], r8d; unsigned int
0x140055ba5  mov     eax, [rsi+4]
0x140055ba8  mov     [rsp+0F0h+var_A8], eax; unsigned int
0x140055bac  mov     [rsp+0F0h+var_B0], r9d; unsigned int
0x140055bb1  mov     eax, [rdi+8Ch]
0x140055bb7  mov     [rsp+0F0h+var_B8], eax; unsigned int
0x140055bbb  mov     eax, [rdi+48h]
0x140055bbe  mov     [rsp+0F0h+var_C0], eax; unsigned int
0x140055bc2  mov     eax, [rdi+64h]
0x140055bc5  mov     [rsp+0F0h+var_C8], eax; unsigned int
0x140055bc9  mov     eax, [rdi+88h]
0x140055bcf  mov     dword ptr [rsp+0F0h+ppv], eax; unsigned int
0x140055bd3  mov     rdx, r15; void *
0x140055bd6  call    ?AEWMILOG_ENDPOINT_ACTIVATION@@YAXKPEAXEEKKKKKKKKKKKKK@Z; AEWMILOG_ENDPOINT_ACTIVATION(ulong,void *,uchar,uchar,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong,ulong)
0x140055bdb  test    ebx, ebx
0x140055bdd  js      short loc_140055BF2
0x140055bdf  mov     rcx, [r14]
0x140055be2  mov     rax, [rcx]
0x140055be5  mov     edx, [r15+50h]
0x140055be9  mov     rax, [rax+30h]
0x140055bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055bf2  lea     rcx, [rbp+57h+pvar]; pvar
0x140055bf6  call    cs:__imp_PropVariantClear
0x140055bfc  test    ebx, ebx
0x140055bfe  jns     short loc_140055C57
0x140055c00  lea     rax, WPP_GLOBAL_Control
0x140055c07  lea     rdi, aCsystemaudiode_2; "CSystemAudioDeviceBase::ActivateEndpoin"...
0x140055c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140055c15  cmp     rcx, rax
0x140055c18  jz      short loc_140055C46
0x140055c1a  test    dword ptr [rcx+1Ch], 200h
0x140055c21  jz      short loc_140055C46
0x140055c23  cmp     byte ptr [rcx+19h], 2
0x140055c27  jb      short loc_140055C46
0x140055c29  mov     edx, 0Ah
0x140055c2e  mov     [rsp+0F0h+ppv], rdi
0x140055c33  mov     r9d, ebx
0x140055c36  lea     r8, WPP_f439333ca32d38002cb7cfdad9c030a3_Traceguids
0x140055c3d  mov     rcx, [rcx+10h]
0x140055c41  call    WPP_SF_Ds
0x140055c46  mov     r8d, ebx; int
0x140055c49  mov     edx, 10Bh; unsigned int
0x140055c4e  mov     rcx, rdi; char *
0x140055c51  call    ?AudDGTraceLoggingErrorHelper@@YAXPEBDIJ@Z; AudDGTraceLoggingErrorHelper(char const *,uint,long)
0x140055c56  nop
0x140055c57  lea     rcx, [rbp+57h+arg_18]
0x140055c5b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140055c60  nop
0x140055c61  lea     rcx, [rbp+57h+var_60]
0x140055c65  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140055c6a  nop
0x140055c6b  lea     rcx, [rbp+57h+var_58]
0x140055c6f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140055c74  nop
0x140055c75  lea     rcx, [rbp+57h+var_48]
0x140055c79  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140055c7e  nop
0x140055c7f  lea     rcx, [rbp+57h+arg_10]
0x140055c83  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140055c88  nop
0x140055c89  lea     rcx, [rbp+57h+var_50]
0x140055c8d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140055c92  mov     eax, ebx
0x140055c94  mov     rbx, [rsp+0F0h+arg_0]
0x140055c9c  add     rsp, 0D0h
0x140055ca3  pop     r15
0x140055ca5  pop     r14
0x140055ca7  pop     rdi
0x140055ca8  pop     rsi
0x140055ca9  pop     rbp
0x140055caa  retn
```
