# FSMConfigurationsOEMCollection::InternalSerializePayload(void)

- ea: `0x18004a230`
- end: `0x18004a632`
- name: `?InternalSerializePayload@FSMConfigurationsOEMCollection@@MEAAJXZ`
- size: `1026`
- prototype: `__int64 __fastcall(FSMConfigurationsOEMCollection *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005f98`
- `0x180006a68`
- `0x180006a98`
- `0x180006cc0`
- `0x18000723c`
- `0x18000d1e0`
- `0x18004a230`
- `0x18004d010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x18004a446`
- `MFPlat!MFCreateAttributes` at `0x18004a446`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x18004a4bf`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x18004a4bf`
- `MFPlat!MFGetAttributesAsBlob` at `0x18004a548`
- `MFPlat!MFGetAttributesAsBlob` at `0x18004a548`

## pseudocode

```c
__int64 __fastcall FSMConfigurationsOEMCollection::InternalSerializePayload(FSMConfigurationsOEMCollection *this)
{
  unsigned int v1; // r14d
  unsigned int v2; // r12d
  unsigned int v4; // edi
  unsigned int i; // ebx
  __int64 v6; // rax
  HRESULT v7; // eax
  unsigned int v8; // eax
  const struct std::nothrow_t *unique; // rax
  UINT8 *v10; // rbx
  __int64 v11; // rdx
  UINT32 j; // r15d
  __int64 v13; // rcx
  __int64 v14; // rdx
  UINT32 v15; // ecx
  const struct std::nothrow_t *v16; // rax
  UINT8 *v17; // rbx
  __int64 v18; // rdx
  UINT32 pcbBufSize; // [rsp+80h] [rbp+48h] BYREF
  __int64 v21; // [rsp+88h] [rbp+50h] BYREF
  UINT8 *v22; // [rsp+90h] [rbp+58h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+98h] [rbp+60h] BYREF

  v1 = *((_DWORD *)this + 16);
  v2 = 0;
  v22 = 0;
  pcbBufSize = 0;
  v4 = 0;
  ppMFAttributes = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 48, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids, this, v1);
  if ( v1 )
  {
    for ( i = 0; i < v1; ++i )
    {
      v6 = *((_QWORD *)this + 7);
      LODWORD(v21) = 0;
      v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(**(_QWORD **)(v6 + 8LL * i) + 48LL))(
             *(_QWORD *)(v6 + 8LL * i),
             0,
             0,
             &v21);
      v4 = v7;
      if ( v7 < 0 )
      {
        if ( g_wppLevels )
        {
          v11 = 49;
          goto LABEL_16;
        }
        goto LABEL_53;
      }
      v8 = pcbBufSize + v21;
      if ( pcbBufSize + (unsigned int)v21 < pcbBufSize )
      {
        pcbBufSize = -1;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50,
            WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids,
            this,
            -2147024362);
        v4 = -2147024362;
        goto LABEL_53;
      }
      pcbBufSize += v21;
    }
    unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v21, v8);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v22, unique);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v21);
    v10 = v22;
    if ( v22 )
    {
      for ( j = 0; ; j += v21 )
      {
        LODWORD(v21) = 0;
        if ( j > pcbBufSize )
        {
          v4 = -1072875845;
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids,
              this,
              -1072875845);
          goto LABEL_53;
        }
        v13 = *(_QWORD *)(*((_QWORD *)this + 7) + 8LL * v2);
        v7 = (*(__int64 (__fastcall **)(__int64, UINT8 *, _QWORD, __int64 *))(*(_QWORD *)v13 + 48LL))(
               v13,
               &v10[j],
               pcbBufSize - j,
               &v21);
        v4 = v7;
        if ( v7 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_53;
          v11 = 53;
          goto LABEL_16;
        }
        if ( j + (unsigned int)v21 < j )
        {
          v4 = -2147024362;
          if ( !g_wppLevels )
            goto LABEL_53;
          v14 = 54;
LABEL_52:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v14,
            WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids,
            this,
            -2147024362);
          goto LABEL_53;
        }
        if ( ++v2 >= v1 )
          break;
      }
      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&ppMFAttributes);
      v7 = MFCreateAttributes(&ppMFAttributes, 1u);
      v4 = v7;
      if ( v7 >= 0 )
      {
        v7 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, UINT8 *, _QWORD))ppMFAttributes->lpVtbl->SetBlob)(
               ppMFAttributes,
               FRAMESERVER_DEVICECONFIGURATION_ENTRIES,
               v10,
               pcbBufSize);
        v4 = v7;
        if ( v7 >= 0 )
        {
          pcbBufSize = 0;
          wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v22);
          v7 = MFGetAttributesAsBlobSize(ppMFAttributes, &pcbBufSize);
          v4 = v7;
          if ( v7 >= 0 )
          {
            v15 = pcbBufSize + 40;
            if ( pcbBufSize + 40 < pcbBufSize )
            {
              pcbBufSize = -1;
              v4 = -2147024362;
              if ( !g_wppLevels )
                goto LABEL_53;
              v14 = 58;
              goto LABEL_52;
            }
            pcbBufSize += 40;
            v16 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v21, v15);
            wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
              (void **)&v22,
              v16);
            wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v21);
            v17 = v22;
            if ( v22 )
            {
              v7 = MFGetAttributesAsBlob(ppMFAttributes, v22 + 40, pcbBufSize - 40);
              v4 = v7;
              if ( v7 >= 0 )
              {
                *((_DWORD *)v17 + 1) = 1;
                *(_OWORD *)(v17 + 8) = 0;
                *(_OWORD *)(v17 + 24) = 0;
                *(_DWORD *)v17 = pcbBufSize;
                v22 = (UINT8 *)*((_QWORD *)this + 13);
                *((_DWORD *)this + 28) = pcbBufSize;
                *((_QWORD *)this + 13) = v17;
                goto LABEL_46;
              }
              if ( !g_wppLevels )
                goto LABEL_53;
              v11 = 60;
            }
            else
            {
              v7 = -2147024882;
              v4 = -2147024882;
              if ( !g_wppLevels )
                goto LABEL_53;
              v11 = (unsigned int)((_DWORD)v22 + 59);
            }
          }
          else
          {
            if ( !g_wppLevels )
              goto LABEL_53;
            v11 = 57;
          }
        }
        else
        {
          if ( !g_wppLevels )
            goto LABEL_53;
          v11 = 56;
        }
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_53;
        v11 = 55;
      }
LABEL_16:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids, this, v7);
    }
    else
    {
      v7 = -2147024882;
      v4 = -2147024882;
      if ( g_wppLevels )
      {
        v11 = (unsigned int)((_DWORD)v22 + 51);
        goto LABEL_16;
      }
    }
LABEL_53:
    if ( byte_18005E5A5 )
    {
      v18 = 61;
      goto LABEL_48;
    }
  }
  else
  {
LABEL_46:
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
      v18 = 62;
LABEL_48:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v18, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids, this, v4);
    }
  }
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v22);
  return v4;
}

```

## disassembly

```asm
0x18004a230  push    rbp
0x18004a232  push    rbx
0x18004a233  push    rsi
0x18004a234  push    rdi
0x18004a235  push    r12
0x18004a237  push    r13
0x18004a239  push    r14
0x18004a23b  push    r15
0x18004a23d  mov     rbp, rsp
0x18004a240  sub     rsp, 38h
0x18004a244  mov     r14d, [rcx+40h]
0x18004a248  xor     r12d, r12d
0x18004a24b  mov     eax, r12d
0x18004a24e  mov     [rbp+arg_10], r12
0x18004a252  mov     [rbp+pcbBufSize], eax
0x18004a255  mov     rsi, rcx
0x18004a258  mov     edi, r12d
0x18004a25b  mov     [rbp+ppMFAttributes], r12
0x18004a25f  cmp     cs:byte_18005E5A5, 8
0x18004a266  jb      short loc_18004A292
0x18004a268  mov     r9, rcx
0x18004a26b  mov     [rsp+38h+var_18], r14d
0x18004a270  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a277  lea     edx, [r12+30h]
0x18004a27c  lea     r8, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids
0x18004a283  mov     rcx, [rcx+0D8h]
0x18004a28a  call    WPP_SF_qD
0x18004a28f  mov     eax, [rbp+pcbBufSize]
0x18004a292  test    r14d, r14d
0x18004a295  jz      loc_18004A591
0x18004a29b  mov     ebx, r12d
0x18004a29e  mov     r13d, 1
0x18004a2a4  mov     rax, [rsi+38h]
0x18004a2a8  lea     r9, [rbp+arg_8]
0x18004a2ac  mov     dword ptr [rbp+arg_8], r12d
0x18004a2b0  xor     r8d, r8d
0x18004a2b3  mov     ecx, ebx
0x18004a2b5  xor     edx, edx
0x18004a2b7  mov     rcx, [rax+rcx*8]
0x18004a2bb  mov     rax, [rcx]
0x18004a2be  mov     rax, [rax+30h]
0x18004a2c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a2c7  mov     edi, eax
0x18004a2c9  test    eax, eax
0x18004a2cb  js      loc_18004A368
0x18004a2d1  mov     eax, dword ptr [rbp+arg_8]
0x18004a2d4  add     eax, [rbp+pcbBufSize]
0x18004a2d7  cmp     eax, [rbp+pcbBufSize]
0x18004a2da  jb      short loc_18004A329
0x18004a2dc  add     ebx, r13d
0x18004a2df  mov     [rbp+pcbBufSize], eax
0x18004a2e2  cmp     ebx, r14d
0x18004a2e5  jb      short loc_18004A2A4
0x18004a2e7  mov     edx, eax
0x18004a2e9  lea     rcx, [rbp+arg_8]
0x18004a2ed  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18004a2f2  mov     rdx, rax
0x18004a2f5  lea     rcx, [rbp+arg_10]
0x18004a2f9  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18004a2fe  lea     rcx, [rbp+arg_8]
0x18004a302  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18004a307  mov     rbx, [rbp+arg_10]
0x18004a30b  test    rbx, rbx
0x18004a30e  jnz     short loc_18004A383
0x18004a310  mov     eax, 8007000Eh
0x18004a315  mov     edi, eax
0x18004a317  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004a31e  jb      loc_18004A61F
0x18004a324  lea     edx, [rbx+33h]
0x18004a327  jmp     short loc_18004A37A
0x18004a329  mov     [rbp+pcbBufSize], 0FFFFFFFFh
0x18004a330  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004a337  mov     ebx, 80070216h
0x18004a33c  jb      short loc_18004A361
0x18004a33e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a345  lea     r8, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids
0x18004a34c  mov     edx, 32h ; '2'
0x18004a351  mov     [rsp+38h+var_18], ebx
0x18004a355  mov     r9, rsi
0x18004a358  mov     rcx, [rcx+10h]
0x18004a35c  call    WPP_SF_qD
0x18004a361  mov     edi, ebx
0x18004a363  jmp     loc_18004A61F
0x18004a368  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004a36f  jb      loc_18004A61F
0x18004a375  mov     edx, 31h ; '1'
0x18004a37a  mov     [rsp+38h+var_18], eax
0x18004a37e  jmp     loc_18004A605
0x18004a383  mov     r15d, r12d
0x18004a386  test    r14d, r14d
0x18004a389  jz      loc_18004A436
0x18004a38f  mov     r8d, [rbp+pcbBufSize]
0x18004a393  mov     dword ptr [rbp+arg_8], 0
0x18004a39a  cmp     r15d, r8d
0x18004a39d  ja      short loc_18004A416
0x18004a39f  mov     rax, [rsi+38h]
0x18004a3a3  lea     r9, [rbp+arg_8]
0x18004a3a7  mov     ecx, r12d
0x18004a3aa  sub     r8d, r15d
0x18004a3ad  mov     edx, r15d
0x18004a3b0  add     rdx, rbx
0x18004a3b3  mov     rcx, [rax+rcx*8]
0x18004a3b7  mov     rax, [rcx]
0x18004a3ba  mov     rax, [rax+30h]
0x18004a3be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3c3  mov     edi, eax
0x18004a3c5  test    eax, eax
0x18004a3c7  js      short loc_18004A3FF
0x18004a3c9  mov     ecx, dword ptr [rbp+arg_8]
0x18004a3cc  add     ecx, r15d
0x18004a3cf  cmp     ecx, r15d
0x18004a3d2  jb      short loc_18004A3E1
0x18004a3d4  add     r12d, r13d
0x18004a3d7  cmp     r12d, r14d
0x18004a3da  jnb     short loc_18004A436
0x18004a3dc  mov     r15d, ecx
0x18004a3df  jmp     short loc_18004A38F
0x18004a3e1  mov     ebx, 80070216h
0x18004a3e6  mov     edi, ebx
0x18004a3e8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004a3ef  jb      loc_18004A61F
0x18004a3f5  mov     edx, 36h ; '6'
0x18004a3fa  jmp     loc_18004A601
0x18004a3ff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004a406  jb      loc_18004A61F
0x18004a40c  mov     edx, 35h ; '5'
0x18004a411  jmp     loc_18004A37A
0x18004a416  mov     edi, 0C00D36BBh
0x18004a41b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004a422  jb      loc_18004A61F
0x18004a428  mov     edx, 34h ; '4'
0x18004a42d  mov     [rsp+38h+var_18], edi
0x18004a431  jmp     loc_18004A605
0x18004a436  lea     rcx, [rbp+ppMFAttributes]
0x18004a43a  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18004a43f  mov     edx, r13d; cInitialSize
0x18004a442  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18004a446  call    cs:__imp_MFCreateAttributes
0x18004a44c  mov     edi, eax
0x18004a44e  test    eax, eax
0x18004a450  jns     short loc_18004A469
0x18004a452  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004a459  jb      loc_18004A61F
0x18004a45f  mov     edx, 37h ; '7'
0x18004a464  jmp     loc_18004A37A
0x18004a469  mov     rcx, [rbp+ppMFAttributes]
0x18004a46d  lea     rdx, FRAMESERVER_DEVICECONFIGURATION_ENTRIES
0x18004a474  mov     r9d, [rbp+pcbBufSize]
0x18004a478  mov     r8, rbx
0x18004a47b  mov     rax, [rcx]
0x18004a47e  mov     rax, [rax+0D0h]
0x18004a485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a48a  mov     edi, eax
0x18004a48c  test    eax, eax
0x18004a48e  jns     short loc_18004A4A7
0x18004a490  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004a497  jb      loc_18004A61F
0x18004a49d  mov     edx, 38h ; '8'
0x18004a4a2  jmp     loc_18004A37A
0x18004a4a7  lea     rcx, [rbp+arg_10]
0x18004a4ab  mov     [rbp+pcbBufSize], 0
0x18004a4b2  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18004a4b7  mov     rcx, [rbp+ppMFAttributes]; pAttributes
0x18004a4bb  lea     rdx, [rbp+pcbBufSize]; pcbBufSize
0x18004a4bf  call    cs:__imp_MFGetAttributesAsBlobSize
0x18004a4c5  mov     edi, eax
0x18004a4c7  test    eax, eax
0x18004a4c9  jns     short loc_18004A4E2
0x18004a4cb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004a4d2  jb      loc_18004A61F
0x18004a4d8  mov     edx, 39h ; '9'
0x18004a4dd  jmp     loc_18004A37A
0x18004a4e2  mov     eax, [rbp+pcbBufSize]
0x18004a4e5  lea     ecx, [rax+28h]
0x18004a4e8  cmp     ecx, eax
0x18004a4ea  jb      loc_18004A5E5
0x18004a4f0  mov     [rbp+pcbBufSize], ecx
0x18004a4f3  mov     edx, ecx
0x18004a4f5  lea     rcx, [rbp+arg_8]
0x18004a4f9  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18004a4fe  mov     rdx, rax
0x18004a501  lea     rcx, [rbp+arg_10]
0x18004a505  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18004a50a  lea     rcx, [rbp+arg_8]
0x18004a50e  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18004a513  mov     rbx, [rbp+arg_10]
0x18004a517  test    rbx, rbx
0x18004a51a  jnz     short loc_18004A538
0x18004a51c  mov     eax, 8007000Eh
0x18004a521  mov     edi, eax
0x18004a523  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004a52a  jb      loc_18004A61F
0x18004a530  lea     edx, [rbx+3Bh]
0x18004a533  jmp     loc_18004A37A
0x18004a538  mov     r8d, [rbp+pcbBufSize]
0x18004a53c  lea     rdx, [rbx+28h]; pBuf
0x18004a540  mov     rcx, [rbp+ppMFAttributes]; pAttributes
0x18004a544  add     r8d, 0FFFFFFD8h; cbBufSize
0x18004a548  call    cs:__imp_MFGetAttributesAsBlob
0x18004a54e  mov     edi, eax
0x18004a550  test    eax, eax
0x18004a552  jns     short loc_18004A56B
0x18004a554  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004a55b  jb      loc_18004A61F
0x18004a561  mov     edx, 3Ch ; '<'
0x18004a566  jmp     loc_18004A37A
0x18004a56b  mov     [rbx+4], r13d
0x18004a56f  xorps   xmm0, xmm0
0x18004a572  movups  xmmword ptr [rbx+8], xmm0
0x18004a576  movups  xmmword ptr [rbx+18h], xmm0
0x18004a57a  mov     eax, [rbp+pcbBufSize]
0x18004a57d  mov     [rbx], eax
0x18004a57f  mov     rax, [rsi+68h]
0x18004a583  mov     [rbp+arg_10], rax
0x18004a587  mov     eax, [rbp+pcbBufSize]
0x18004a58a  mov     [rsi+70h], eax
0x18004a58d  mov     [rsi+68h], rbx
0x18004a591  cmp     cs:byte_18005E5A5, 8
0x18004a598  jb      short loc_18004A5C0
0x18004a59a  mov     edx, 3Eh ; '>'
0x18004a59f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a5a6  lea     r8, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids
0x18004a5ad  mov     r9, rsi
0x18004a5b0  mov     [rsp+38h+var_18], edi
0x18004a5b4  mov     rcx, [rcx+0D8h]
0x18004a5bb  call    WPP_SF_qD
0x18004a5c0  lea     rcx, [rbp+ppMFAttributes]
0x18004a5c4  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18004a5c9  lea     rcx, [rbp+arg_10]
0x18004a5cd  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18004a5d2  mov     eax, edi
0x18004a5d4  add     rsp, 38h
0x18004a5d8  pop     r15
0x18004a5da  pop     r14
0x18004a5dc  pop     r13
0x18004a5de  pop     r12
0x18004a5e0  pop     rdi
0x18004a5e1  pop     rsi
0x18004a5e2  pop     rbx
0x18004a5e3  pop     rbp
0x18004a5e4  retn
0x18004a5e5  mov     ebx, 80070216h
0x18004a5ea  mov     [rbp+pcbBufSize], 0FFFFFFFFh
0x18004a5f1  mov     edi, ebx
0x18004a5f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18004a5fa  jb      short loc_18004A61F
0x18004a5fc  mov     edx, 3Ah ; ':'
0x18004a601  mov     [rsp+38h+var_18], ebx
0x18004a605  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a60c  lea     r8, WPP_05511007120d3393f1a8ac4501dd3aa6_Traceguids
0x18004a613  mov     r9, rsi
0x18004a616  mov     rcx, [rcx+10h]
0x18004a61a  call    WPP_SF_qD
0x18004a61f  cmp     cs:byte_18005E5A5, r13b
0x18004a626  jb      short loc_18004A5C0
0x18004a628  mov     edx, 3Dh ; '='
0x18004a62d  jmp     loc_18004A59F
```
