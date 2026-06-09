# SensorTransformStream::InitializeSensorTransformStream(void)

- ea: `0x1800c5f40`
- end: `0x1800c63c3`
- name: `?InitializeSensorTransformStream@SensorTransformStream@@MEAAJXZ`
- size: `1155`
- prototype: `__int64 __fastcall(SensorTransformStream *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800041f0`
- `0x180004f20`
- `0x180008cf0`
- `0x180009608`
- `0x1800096f4`
- `0x18000a460`
- `0x18000ad10`
- `0x18001c674`
- `0x1800b20bc`
- `0x1800bcae4`
- `0x1800bcdb8`
- `0x1800be690`
- `0x1800c5f40`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreateEventQueue` at `0x1800c6319`
- `MFPlat!MFCreateEventQueue` at `0x1800c6319`
- `MFPlat!MFCreateStreamDescriptor` at `0x1800c61a8`
- `MFPlat!MFCreateStreamDescriptor` at `0x1800c61a8`

## pseudocode

```c
__int64 __fastcall SensorTransformStream::InitializeSensorTransformStream(SensorTransformStream *this)
{
  int v2; // eax
  unsigned int v3; // edi
  __int64 v4; // rdx
  int v5; // eax
  int v6; // ecx
  int v7; // r14d
  DWORD v8; // edi
  __int64 v9; // rcx
  __int64 v10; // rdx
  const char *String; // rax
  IMFMediaType **v12; // r14
  DWORD v13; // edx
  __int64 v14; // r8
  __int64 v15; // rcx
  HRESULT v16; // eax
  const struct std::nothrow_t *v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+4Ch] [rbp-B4h]
  _BYTE v30[224]; // [rsp+60h] [rbp-A0h] BYREF
  struct IMFAttributes *v31; // [rsp+150h] [rbp+50h] BYREF
  __int64 v32; // [rsp+158h] [rbp+58h] BYREF
  IMFStreamDescriptor *ppDescriptor; // [rsp+160h] [rbp+60h] BYREF
  int (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // [rsp+168h] [rbp+68h] BYREF

  ppDescriptor = 0;
  v27 = 0;
  v29 = 0;
  v28 = 0;
  v34 = 0;
  v32 = 0;
  if ( !*((_QWORD *)this + 11) )
  {
    v2 = -2147024809;
    v3 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_58;
    v4 = 67;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_975d346cb9d8347ecb4cc8baf1358652_Traceguids, this, v2);
    goto LABEL_58;
  }
  if ( !*((_QWORD *)this + 9) )
  {
    v2 = -2147024809;
    v3 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_58;
    v4 = 68;
    goto LABEL_4;
  }
  v5 = *((_DWORD *)this + 21);
  v6 = *((_DWORD *)this + 20);
  if ( v6 != v5 )
  {
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        69,
        &WPP_975d346cb9d8347ecb4cc8baf1358652_Traceguids,
        this,
        v6,
        v5);
    v3 = -1072875853;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        &WPP_975d346cb9d8347ecb4cc8baf1358652_Traceguids,
        this,
        -1072875853);
    goto LABEL_58;
  }
  v7 = 0;
  v8 = 0;
  while ( 1 )
  {
    if ( v7 < 0 )
    {
      v12 = (IMFMediaType **)operator new[](saturated_mul(v8, 8u));
      if ( !v12 )
      {
        v2 = -2147024882;
        v3 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_58;
        v4 = 73;
        goto LABEL_4;
      }
      v13 = 0;
      if ( v8 )
      {
        v14 = v27;
        do
        {
          v15 = v13++;
          v12[v15] = *(IMFMediaType **)(v14 + 8 * v15);
        }
        while ( v13 < v8 );
      }
      v16 = MFCreateStreamDescriptor(*((_DWORD *)this + 21), v8, v12, &ppDescriptor);
      v3 = v16;
      if ( v16 >= 0 )
      {
        if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 9) + 72LL))(
               *((_QWORD *)this + 9),
               *((unsigned int *)this + 20),
               &v34) >= 0
          && (**v34)(v34, &GUID_28f54685_06fd_11d2_b27a_00a0c9223196, &v32) >= 0 )
        {
          if ( (unsigned __int8)byte_18010EC4D >= 8u )
            WPP_SF_qDDq(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              75,
              &WPP_975d346cb9d8347ecb4cc8baf1358652_Traceguids,
              this,
              *((_DWORD *)this + 20),
              *((_DWORD *)this + 21),
              v32);
          if ( v32 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
            v20 = *((_QWORD *)this + 71);
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            *((_QWORD *)this + 71) = v32;
          }
          else
          {
            v19 = *((_QWORD *)this + 71);
            if ( v19 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
              *((_QWORD *)this + 71) = 0;
            }
          }
        }
        *((_QWORD *)this + 66) = 0;
        if ( !*((_QWORD *)this + 15) )
        {
          *((_DWORD *)this + 32) = 1;
          *((_QWORD *)this + 15) = (char *)this + 136;
          v21 = 0;
          *((_QWORD *)this + 17) = 0;
          do
          {
            v22 = v21 + 2 * v21 + 1;
            ++v21;
            v23 = *((_QWORD *)this + 15) + 8 * v22;
            *(_QWORD *)(v23 + 8) = *((_QWORD *)this + 14);
            *((_QWORD *)this + 14) = v23;
          }
          while ( v21 != 16 );
        }
        v16 = MFCreateEventQueue((IMFMediaEventQueue **)this + 12);
        v3 = v16;
        if ( v16 >= 0 )
        {
          if ( ppDescriptor )
          {
            ((void (__fastcall *)(IMFStreamDescriptor *))ppDescriptor->lpVtbl->AddRef)(ppDescriptor);
            v25 = *((_QWORD *)this + 13);
            if ( v25 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
            *((_QWORD *)this + 13) = ppDescriptor;
          }
          else
          {
            v24 = *((_QWORD *)this + 13);
            if ( v24 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
              *((_QWORD *)this + 13) = 0;
            }
          }
          goto LABEL_57;
        }
        if ( g_wppLevels )
        {
          v18 = 77;
          goto LABEL_34;
        }
      }
      else if ( g_wppLevels )
      {
        v18 = 74;
LABEL_34:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_975d346cb9d8347ecb4cc8baf1358652_Traceguids, this, v16);
      }
LABEL_57:
      operator delete(v12, v17);
      goto LABEL_58;
    }
    v9 = *((_QWORD *)this + 9);
    v10 = *((unsigned int *)this + 20);
    v31 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, struct IMFAttributes **))(*(_QWORD *)v9 + 56LL))(
           v9,
           v10,
           v8,
           &v31);
    if ( v7 < 0 )
      goto LABEL_21;
    if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add(&v27, v31) )
      break;
    ++v8;
    if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
    {
      CMFAttributesTrace::CMFAttributesTrace((CMFAttributesTrace *)v30, v31);
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        String = CMFAttributesTrace::GetString((CMFAttributesTrace *)v30, 0);
        WPP_SF_qDDDs(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          72,
          (unsigned int)&WPP_975d346cb9d8347ecb4cc8baf1358652_Traceguids,
          (_DWORD)this,
          *((_DWORD *)this + 20),
          *((_DWORD *)this + 21),
          v8,
          (__int64)String);
      }
      CMFAttributesTrace::~CMFAttributesTrace((CMFAttributesTrace *)v30);
    }
LABEL_21:
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v31);
  }
  v3 = -2147024882;
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      71,
      &WPP_975d346cb9d8347ecb4cc8baf1358652_Traceguids,
      this,
      -2147024882);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v31);
LABEL_58:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v32);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v34);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(&v27);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppDescriptor);
  return v3;
}

```

## disassembly

```asm
0x1800c5f40  push    rbp
0x1800c5f42  push    rbx
0x1800c5f43  push    rdi
0x1800c5f44  push    r14
0x1800c5f46  push    r15
0x1800c5f48  lea     rbp, [rsp-20h]
0x1800c5f4d  sub     rsp, 120h
0x1800c5f54  xor     r15d, r15d
0x1800c5f57  mov     rbx, rcx
0x1800c5f5a  mov     [rbp+40h+ppDescriptor], r15
0x1800c5f5e  mov     [rsp+140h+var_100], r15
0x1800c5f63  mov     [rsp+140h+var_F4], r15
0x1800c5f68  mov     [rsp+140h+var_F8], r15d
0x1800c5f6d  mov     [rbp+40h+arg_18], r15
0x1800c5f71  mov     [rbp+40h+arg_8], r15
0x1800c5f75  cmp     [rcx+58h], r15
0x1800c5f79  jnz     short loc_1800C5FB6
0x1800c5f7b  mov     eax, 80070057h
0x1800c5f80  mov     edi, eax
0x1800c5f82  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c5f89  jb      loc_1800C638D
0x1800c5f8f  lea     edx, [r15+43h]
0x1800c5f93  mov     [rsp+140h+var_120], eax
0x1800c5f97  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c5f9e  lea     r8, WPP_975d346cb9d8347ecb4cc8baf1358652_Traceguids
0x1800c5fa5  mov     r9, rbx
0x1800c5fa8  mov     rcx, [rcx+10h]
0x1800c5fac  call    WPP_SF_qD
0x1800c5fb1  jmp     loc_1800C638D
0x1800c5fb6  cmp     [rcx+48h], r15
0x1800c5fba  jnz     short loc_1800C5FD7
0x1800c5fbc  mov     eax, 80070057h
0x1800c5fc1  mov     edi, eax
0x1800c5fc3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c5fca  jb      loc_1800C638D
0x1800c5fd0  mov     edx, 44h ; 'D'
0x1800c5fd5  jmp     short loc_1800C5F93
0x1800c5fd7  mov     eax, [rcx+54h]
0x1800c5fda  mov     ecx, [rcx+50h]
0x1800c5fdd  cmp     ecx, eax
0x1800c5fdf  jz      short loc_1800C6034
0x1800c5fe1  cmp     cs:byte_18010EC4D, 8
0x1800c5fe8  jb      short loc_1800C6014
0x1800c5fea  mov     [rsp+140h+var_118], eax
0x1800c5fee  lea     r8, WPP_975d346cb9d8347ecb4cc8baf1358652_Traceguids
0x1800c5ff5  mov     [rsp+140h+var_120], ecx
0x1800c5ff9  mov     edx, 45h ; 'E'
0x1800c5ffe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6005  mov     r9, rbx
0x1800c6008  mov     rcx, [rcx+0D8h]
0x1800c600f  call    WPP_SF_qDD
0x1800c6014  mov     edi, 0C00D36B3h
0x1800c6019  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c6020  jb      loc_1800C638D
0x1800c6026  mov     edx, 46h ; 'F'
0x1800c602b  mov     [rsp+140h+var_120], edi
0x1800c602f  jmp     loc_1800C5F97
0x1800c6034  mov     r14d, r15d
0x1800c6037  mov     edi, r15d
0x1800c603a  test    r14d, r14d
0x1800c603d  js      loc_1800C613E
0x1800c6043  mov     rcx, [rbx+48h]
0x1800c6047  lea     r9, [rbp+40h+arg_0]
0x1800c604b  mov     edx, [rbx+50h]
0x1800c604e  mov     r8d, edi
0x1800c6051  mov     [rbp+40h+arg_0], r15
0x1800c6055  mov     rax, [rcx]
0x1800c6058  mov     rax, [rax+38h]
0x1800c605c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6061  mov     r14d, eax
0x1800c6064  test    eax, eax
0x1800c6066  js      loc_1800C60EF
0x1800c606c  mov     rdx, [rbp+40h+arg_0]
0x1800c6070  lea     rcx, [rsp+140h+var_100]
0x1800c6075  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x1800c607a  test    eax, eax
0x1800c607c  jz      short loc_1800C60FD
0x1800c607e  inc     edi
0x1800c6080  cmp     cs:byte_18010EC4D, 10h
0x1800c6087  jb      short loc_1800C60EF
0x1800c6089  mov     rdx, [rbp+40h+arg_0]; struct IMFAttributes *
0x1800c608d  lea     rcx, [rsp+140h+var_E0]; this
0x1800c6092  call    ??0CMFAttributesTrace@@QEAA@PEAUIMFAttributes@@@Z; CMFAttributesTrace::CMFAttributesTrace(IMFAttributes *)
0x1800c6097  cmp     cs:byte_18010EC4D, 8
0x1800c609e  jb      short loc_1800C60E5
0x1800c60a0  xor     edx, edx; bool
0x1800c60a2  lea     rcx, [rsp+140h+var_E0]; this
0x1800c60a7  call    ?GetString@CMFAttributesTrace@@QEAAPEBD_N@Z; CMFAttributesTrace::GetString(bool)
0x1800c60ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c60b3  lea     r8, WPP_975d346cb9d8347ecb4cc8baf1358652_Traceguids
0x1800c60ba  mov     [rsp+140h+var_108], rax
0x1800c60bf  mov     edx, 48h ; 'H'
0x1800c60c4  mov     eax, [rbx+54h]
0x1800c60c7  mov     r9, rbx
0x1800c60ca  mov     dword ptr [rsp+140h+var_110], edi
0x1800c60ce  mov     rcx, [rcx+0D8h]
0x1800c60d5  mov     [rsp+140h+var_118], eax
0x1800c60d9  mov     eax, [rbx+50h]
0x1800c60dc  mov     [rsp+140h+var_120], eax
0x1800c60e0  call    WPP_SF_qDDDs
0x1800c60e5  lea     rcx, [rsp+140h+var_E0]; this
0x1800c60ea  call    ??1CMFAttributesTrace@@QEAA@XZ; CMFAttributesTrace::~CMFAttributesTrace(void)
0x1800c60ef  lea     rcx, [rbp+40h+arg_0]; void *
0x1800c60f3  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800c60f8  jmp     loc_1800C603A
0x1800c60fd  mov     eax, 8007000Eh
0x1800c6102  mov     edi, eax
0x1800c6104  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c610b  jb      short loc_1800C6130
0x1800c610d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6114  lea     r8, WPP_975d346cb9d8347ecb4cc8baf1358652_Traceguids
0x1800c611b  mov     edx, 47h ; 'G'
0x1800c6120  mov     [rsp+140h+var_120], eax
0x1800c6124  mov     r9, rbx
0x1800c6127  mov     rcx, [rcx+10h]
0x1800c612b  call    WPP_SF_qD
0x1800c6130  lea     rcx, [rbp+40h+arg_0]; void *
0x1800c6134  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800c6139  jmp     loc_1800C638D
0x1800c613e  mov     ecx, edi
0x1800c6140  mov     eax, 8
0x1800c6145  mul     rcx
0x1800c6148  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c614f  cmovb   rax, rcx
0x1800c6153  mov     rcx, rax; unsigned __int64
0x1800c6156  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800c615b  mov     r14, rax
0x1800c615e  test    rax, rax
0x1800c6161  jnz     short loc_1800C6180
0x1800c6163  mov     eax, 8007000Eh
0x1800c6168  mov     edi, eax
0x1800c616a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c6171  jb      loc_1800C638D
0x1800c6177  lea     edx, [r14+49h]
0x1800c617b  jmp     loc_1800C5F93
0x1800c6180  mov     edx, r15d
0x1800c6183  test    edi, edi
0x1800c6185  jz      short loc_1800C619C
0x1800c6187  mov     r8, [rsp+140h+var_100]
0x1800c618c  mov     ecx, edx
0x1800c618e  inc     edx
0x1800c6190  mov     rax, [r8+rcx*8]
0x1800c6194  mov     [r14+rcx*8], rax
0x1800c6198  cmp     edx, edi
0x1800c619a  jb      short loc_1800C618C
0x1800c619c  mov     ecx, [rbx+54h]; dwStreamIdentifier
0x1800c619f  lea     r9, [rbp+40h+ppDescriptor]; ppDescriptor
0x1800c61a3  mov     r8, r14; apMediaTypes
0x1800c61a6  mov     edx, edi; cMediaTypes
0x1800c61a8  call    cs:__imp_MFCreateStreamDescriptor
0x1800c61ae  mov     edi, eax
0x1800c61b0  test    eax, eax
0x1800c61b2  jns     short loc_1800C61E9
0x1800c61b4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c61bb  jb      loc_1800C6385
0x1800c61c1  mov     edx, 4Ah ; 'J'
0x1800c61c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c61cd  lea     r8, WPP_975d346cb9d8347ecb4cc8baf1358652_Traceguids
0x1800c61d4  mov     r9, rbx
0x1800c61d7  mov     [rsp+140h+var_120], eax
0x1800c61db  mov     rcx, [rcx+10h]
0x1800c61df  call    WPP_SF_qD
0x1800c61e4  jmp     loc_1800C6385
0x1800c61e9  mov     rcx, [rbx+48h]
0x1800c61ed  lea     r8, [rbp+40h+arg_18]
0x1800c61f1  mov     edx, [rbx+50h]
0x1800c61f4  mov     rax, [rcx]
0x1800c61f7  mov     rax, [rax+48h]
0x1800c61fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6200  test    eax, eax
0x1800c6202  js      loc_1800C62C5
0x1800c6208  mov     rcx, [rbp+40h+arg_18]
0x1800c620c  lea     r8, [rbp+40h+arg_8]
0x1800c6210  lea     rdx, _GUID_28f54685_06fd_11d2_b27a_00a0c9223196
0x1800c6217  mov     rax, [rcx]
0x1800c621a  mov     rax, [rax]
0x1800c621d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6222  test    eax, eax
0x1800c6224  js      loc_1800C62C5
0x1800c622a  cmp     cs:byte_18010EC4D, 8
0x1800c6231  jb      short loc_1800C626C
0x1800c6233  mov     rax, [rbp+40h+arg_8]
0x1800c6237  lea     r8, WPP_975d346cb9d8347ecb4cc8baf1358652_Traceguids
0x1800c623e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6245  mov     edx, 4Bh ; 'K'
0x1800c624a  mov     [rsp+140h+var_110], rax
0x1800c624f  mov     r9, rbx
0x1800c6252  mov     eax, [rbx+54h]
0x1800c6255  mov     [rsp+140h+var_118], eax
0x1800c6259  mov     eax, [rbx+50h]
0x1800c625c  mov     rcx, [rcx+0D8h]
0x1800c6263  mov     [rsp+140h+var_120], eax
0x1800c6267  call    WPP_SF_qDDq
0x1800c626c  mov     rcx, [rbp+40h+arg_8]
0x1800c6270  test    rcx, rcx
0x1800c6273  jnz     short loc_1800C6296
0x1800c6275  mov     rcx, [rbx+238h]
0x1800c627c  test    rcx, rcx
0x1800c627f  jz      short loc_1800C62C5
0x1800c6281  mov     rax, [rcx]
0x1800c6284  mov     rax, [rax+10h]
0x1800c6288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c628d  mov     [rbx+238h], r15
0x1800c6294  jmp     short loc_1800C62C5
0x1800c6296  mov     rax, [rcx]
0x1800c6299  mov     rax, [rax+8]
0x1800c629d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c62a2  mov     rcx, [rbx+238h]
0x1800c62a9  test    rcx, rcx
0x1800c62ac  jz      short loc_1800C62BA
0x1800c62ae  mov     rax, [rcx]
0x1800c62b1  mov     rax, [rax+10h]
0x1800c62b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c62ba  mov     rax, [rbp+40h+arg_8]
0x1800c62be  mov     [rbx+238h], rax
0x1800c62c5  mov     [rbx+210h], r15
0x1800c62cc  cmp     [rbx+78h], r15
0x1800c62d0  jnz     short loc_1800C6315
0x1800c62d2  lea     rax, [rbx+88h]
0x1800c62d9  mov     dword ptr [rbx+80h], 1
0x1800c62e3  mov     [rbx+78h], rax
0x1800c62e7  mov     r8, r15
0x1800c62ea  mov     [rax], r15
0x1800c62ed  mov     rax, [rbx+78h]
0x1800c62f1  lea     rdx, ds:1[r8*2]
0x1800c62f9  add     rdx, r8
0x1800c62fc  inc     r8
0x1800c62ff  lea     rdx, [rax+rdx*8]
0x1800c6303  mov     rax, [rbx+70h]
0x1800c6307  mov     [rdx+8], rax
0x1800c630b  mov     [rbx+70h], rdx
0x1800c630f  cmp     r8, 10h
0x1800c6313  jnz     short loc_1800C62ED
0x1800c6315  lea     rcx, [rbx+60h]; ppMediaEventQueue
0x1800c6319  call    cs:__imp_MFCreateEventQueue
0x1800c631f  mov     edi, eax
0x1800c6321  test    eax, eax
0x1800c6323  jns     short loc_1800C6338
0x1800c6325  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800c632c  jb      short loc_1800C6385
0x1800c632e  mov     edx, 4Dh ; 'M'
0x1800c6333  jmp     loc_1800C61C6
0x1800c6338  mov     rcx, [rbp+40h+ppDescriptor]
0x1800c633c  test    rcx, rcx
0x1800c633f  jnz     short loc_1800C635C
0x1800c6341  mov     rcx, [rbx+68h]
0x1800c6345  test    rcx, rcx
0x1800c6348  jz      short loc_1800C6385
0x1800c634a  mov     rax, [rcx]
0x1800c634d  mov     rax, [rax+10h]
0x1800c6351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6356  mov     [rbx+68h], r15
0x1800c635a  jmp     short loc_1800C6385
0x1800c635c  mov     rax, [rcx]
0x1800c635f  mov     rax, [rax+8]
0x1800c6363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6368  mov     rcx, [rbx+68h]
0x1800c636c  test    rcx, rcx
0x1800c636f  jz      short loc_1800C637D
0x1800c6371  mov     rax, [rcx]
0x1800c6374  mov     rax, [rax+10h]
0x1800c6378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c637d  mov     rax, [rbp+40h+ppDescriptor]
0x1800c6381  mov     [rbx+68h], rax
0x1800c6385  mov     rcx, r14; void *
0x1800c6388  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c638d  lea     rcx, [rbp+40h+arg_8]; void *
0x1800c6391  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800c6396  lea     rcx, [rbp+40h+arg_18]; void *
0x1800c639a  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800c639f  lea     rcx, [rsp+140h+var_100]; void *
0x1800c63a4  call    ??1?$CTUnkArray@VSensorTransformContextStream@@@@QEAA@XZ; CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(void)
0x1800c63a9  lea     rcx, [rbp+40h+ppDescriptor]; void *
0x1800c63ad  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800c63b2  mov     eax, edi
0x1800c63b4  add     rsp, 120h
0x1800c63bb  pop     r15
0x1800c63bd  pop     r14
0x1800c63bf  pop     rdi
0x1800c63c0  pop     rbx
0x1800c63c1  pop     rbp
0x1800c63c2  retn
```
