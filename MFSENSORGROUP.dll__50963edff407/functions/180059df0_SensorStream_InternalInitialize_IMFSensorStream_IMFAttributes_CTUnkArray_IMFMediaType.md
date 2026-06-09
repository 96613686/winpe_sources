# SensorStream::InternalInitialize(IMFSensorStream *,IMFAttributes *,CTUnkArray<IMFMediaType> &)

- ea: `0x180059df0`
- end: `0x18005a180`
- name: `?InternalInitialize@SensorStream@@MEAAJPEAUIMFSensorStream@@PEAUIMFAttributes@@AEAV?$CTUnkArray@UIMFMediaType@@@@@Z`
- size: `912`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x180008fe4`
- `0x180028d34`
- `0x18002f3cc`
- `0x1800373c8`
- `0x180044f30`
- `0x180059df0`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a062`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a0ae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a062`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a0ae`
- `MFPlat!MFCreateAttributes` at `0x180059f6a`
- `MFPlat!MFCreateAttributes` at `0x180059f6a`

## pseudocode

```c
__int64 __fastcall SensorStream::InternalInitialize(
        _QWORD *a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 *a3,
        __int64 a4)
{
  int v8; // ebx
  __int64 v9; // rdx
  __int64 (__fastcall **v10)(_QWORD, GUID *, __int64 *); // rax
  HRESULT v11; // eax
  __int64 v12; // rdx
  UINT32 v13; // ebx
  unsigned int v14; // eax
  unsigned int i; // esi
  __int64 v16; // rax
  __int64 (__fastcall *v17)(__int64 *, _QWORD, GUID *, PROPVARIANT *); // rax
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rdx
  UINT32 v22; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v23; // [rsp+34h] [rbp-4Ch] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+38h] [rbp-48h] BYREF
  __int64 v25; // [rsp+40h] [rbp-40h] BYREF
  int v26; // [rsp+48h] [rbp-38h] BYREF
  PROPVARIANT pvar[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v28; // [rsp+60h] [rbp-20h]
  GUID v29; // [rsp+68h] [rbp-18h] BYREF

  v22 = 0;
  v23 = 0;
  v25 = 0;
  ppMFAttributes = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 27), 31, &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids, a1, a2);
  if ( !a2 )
  {
    v8 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_43;
    v9 = 32;
    goto LABEL_42;
  }
  v10 = *a2;
  v25 = 0;
  v11 = (*v10)(a2, &GUID_cfa380d0_f3e1_43ca_a35a_3c7b19d27304, &v25);
  v8 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_43;
    v12 = 33;
    goto LABEL_9;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v25 + 240LL))(v25, &v22);
  v8 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_43;
    v12 = 34;
    goto LABEL_9;
  }
  if ( a3 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*a3 + 240))(a3, &v23);
    v8 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_43;
      v12 = 35;
      goto LABEL_9;
    }
    v13 = v23 + v22;
    v22 += v23;
  }
  else
  {
    v13 = v22;
  }
  wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&ppMFAttributes);
  v11 = MFCreateAttributes(&ppMFAttributes, v13);
  v8 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_43;
    v12 = 36;
    goto LABEL_9;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, IMFAttributes *))(*(_QWORD *)v25 + 256LL))(v25, ppMFAttributes);
  v8 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_43;
    v12 = 37;
LABEL_9:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids, a1, v11);
    goto LABEL_43;
  }
  if ( a3 )
  {
    v14 = v23;
    if ( v23 )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= v14 )
          goto LABEL_39;
        v26 = 19;
        v28 = 0;
        v16 = *a3;
        *(_OWORD *)pvar = 0;
        v17 = *(__int64 (__fastcall **)(__int64 *, _QWORD, GUID *, PROPVARIANT *))(v16 + 248);
        v29 = GUID_00000000_0000_0000_0000_000000000000;
        v18 = v17(a3, i, &v29, pvar);
        v8 = v18;
        if ( v18 < 0 )
          break;
        if ( ((int (__fastcall *)(IMFAttributes *, GUID *, int *))ppMFAttributes->lpVtbl->GetItemType)(
               ppMFAttributes,
               &v29,
               &v26) < 0 )
        {
          v18 = ((__int64 (__fastcall *)(IMFAttributes *, GUID *, PROPVARIANT *))ppMFAttributes->lpVtbl->SetItem)(
                  ppMFAttributes,
                  &v29,
                  pvar);
          v8 = v18;
          if ( v18 < 0 )
          {
            if ( g_wppLevels )
            {
              v19 = 39;
              goto LABEL_37;
            }
            goto LABEL_38;
          }
        }
        PropVariantClear(pvar);
        v14 = v23;
      }
      if ( g_wppLevels )
      {
        v19 = 38;
LABEL_37:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids, a1, v18);
      }
LABEL_38:
      PropVariantClear(pvar);
      goto LABEL_43;
    }
  }
LABEL_39:
  v8 = (*(__int64 (__fastcall **)(_QWORD *, IMFAttributes *, __int64))(*a1 + 376LL))(a1, ppMFAttributes, a4);
  if ( v8 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_43;
    v9 = 40;
LABEL_42:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids, a1, v8);
LABEL_43:
    CTUnkArray<IMFSensorDeviceIdInternal>::RemoveAll(a1 + 9);
    if ( byte_18008D62D )
    {
      v20 = 41;
LABEL_47:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v20, &WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids, a1, v8);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  ComSmartPtr<IMFCameraProfileValidation>::operator=(a1 + 8, (__int64)ppMFAttributes);
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v20 = 42;
    goto LABEL_47;
  }
LABEL_48:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v25);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180059df0  push    rbp
0x180059df2  push    rbx
0x180059df3  push    rsi
0x180059df4  push    rdi
0x180059df5  push    r13
0x180059df7  push    r14
0x180059df9  push    r15
0x180059dfb  mov     rbp, rsp
0x180059dfe  sub     rsp, 80h
0x180059e05  mov     rax, cs:__security_cookie
0x180059e0c  xor     rax, rsp
0x180059e0f  mov     [rbp+var_8], rax
0x180059e13  mov     rdi, rcx
0x180059e16  mov     [rbp+var_50], 0
0x180059e1d  xor     ecx, ecx
0x180059e1f  mov     [rbp+var_4C], 0
0x180059e26  mov     [rbp+var_40], rcx
0x180059e2a  mov     r15, r9
0x180059e2d  mov     r14, r8
0x180059e30  mov     [rbp+ppMFAttributes], 0
0x180059e38  mov     rbx, rdx
0x180059e3b  cmp     cs:byte_18008D62D, 8
0x180059e42  lea     r13, WPP_c558ff4fa6803944f4e63d947b8359f8_Traceguids
0x180059e49  jb      short loc_180059E70
0x180059e4b  lea     edx, [rcx+1Fh]
0x180059e4e  mov     [rsp+80h+var_60], rbx
0x180059e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180059e5a  mov     r9, rdi
0x180059e5d  mov     r8, r13
0x180059e60  mov     rcx, [rcx+0D8h]
0x180059e67  call    WPP_SF_qq
0x180059e6c  mov     rcx, [rbp+var_40]
0x180059e70  test    rbx, rbx
0x180059e73  jnz     short loc_180059E91
0x180059e75  mov     ebx, 80070057h
0x180059e7a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059e81  jb      loc_18005A0FD
0x180059e87  mov     edx, 20h ; ' '
0x180059e8c  jmp     loc_18005A0E3
0x180059e91  mov     rax, [rbx]
0x180059e94  mov     [rbp+var_40], 0
0x180059e9c  mov     rsi, [rax]
0x180059e9f  test    rcx, rcx
0x180059ea2  jz      short loc_180059EB0
0x180059ea4  mov     rax, [rcx]
0x180059ea7  mov     rax, [rax+10h]
0x180059eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059eb0  lea     r8, [rbp+var_40]
0x180059eb4  mov     rcx, rbx
0x180059eb7  lea     rdx, _GUID_cfa380d0_f3e1_43ca_a35a_3c7b19d27304
0x180059ebe  mov     rax, rsi
0x180059ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ec6  mov     ebx, eax
0x180059ec8  test    eax, eax
0x180059eca  jns     short loc_180059EE7
0x180059ecc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059ed3  jb      loc_18005A0FD
0x180059ed9  mov     edx, 21h ; '!'
0x180059ede  mov     dword ptr [rsp+80h+var_60], eax
0x180059ee2  jmp     loc_18005A0E7
0x180059ee7  mov     rcx, [rbp+var_40]
0x180059eeb  lea     rdx, [rbp+var_50]
0x180059eef  mov     rax, [rcx]
0x180059ef2  mov     rax, [rax+0F0h]
0x180059ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059efe  mov     ebx, eax
0x180059f00  test    eax, eax
0x180059f02  jns     short loc_180059F18
0x180059f04  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059f0b  jb      loc_18005A0FD
0x180059f11  mov     edx, 22h ; '"'
0x180059f16  jmp     short loc_180059EDE
0x180059f18  test    r14, r14
0x180059f1b  jz      short loc_180059F58
0x180059f1d  mov     rax, [r14]
0x180059f20  lea     rdx, [rbp+var_4C]
0x180059f24  mov     rcx, r14
0x180059f27  mov     rax, [rax+0F0h]
0x180059f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f33  mov     ebx, eax
0x180059f35  test    eax, eax
0x180059f37  jns     short loc_180059F4D
0x180059f39  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059f40  jb      loc_18005A0FD
0x180059f46  mov     edx, 23h ; '#'
0x180059f4b  jmp     short loc_180059EDE
0x180059f4d  mov     ebx, [rbp+var_50]
0x180059f50  add     ebx, [rbp+var_4C]
0x180059f53  mov     [rbp+var_50], ebx
0x180059f56  jmp     short loc_180059F5B
0x180059f58  mov     ebx, [rbp+var_50]
0x180059f5b  lea     rcx, [rbp+ppMFAttributes]
0x180059f5f  call    ?reset@?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(void)
0x180059f64  mov     edx, ebx; cInitialSize
0x180059f66  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x180059f6a  call    cs:__imp_MFCreateAttributes
0x180059f70  mov     ebx, eax
0x180059f72  test    eax, eax
0x180059f74  jns     short loc_180059F8D
0x180059f76  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059f7d  jb      loc_18005A0FD
0x180059f83  mov     edx, 24h ; '$'
0x180059f88  jmp     loc_180059EDE
0x180059f8d  mov     rcx, [rbp+var_40]
0x180059f91  mov     rdx, [rbp+ppMFAttributes]
0x180059f95  mov     rax, [rcx]
0x180059f98  mov     rax, [rax+100h]
0x180059f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fa4  mov     ebx, eax
0x180059fa6  test    eax, eax
0x180059fa8  jns     short loc_180059FC1
0x180059faa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180059fb1  jb      loc_18005A0FD
0x180059fb7  mov     edx, 25h ; '%'
0x180059fbc  jmp     loc_180059EDE
0x180059fc1  test    r14, r14
0x180059fc4  jz      loc_18005A0B6
0x180059fca  mov     eax, [rbp+var_4C]
0x180059fcd  test    eax, eax
0x180059fcf  jz      loc_18005A0B6
0x180059fd5  xor     esi, esi
0x180059fd7  cmp     esi, eax
0x180059fd9  jnb     loc_18005A0B6
0x180059fdf  movups  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180059fe6  xor     eax, eax
0x180059fe8  mov     [rbp+var_38], 13h
0x180059fef  mov     [rbp+var_20], rax
0x180059ff3  lea     r9, [rbp+pvar]
0x180059ff7  mov     rax, [r14]
0x180059ffa  lea     r8, [rbp+var_18]
0x180059ffe  xorps   xmm0, xmm0
0x18005a001  mov     edx, esi
0x18005a003  mov     rcx, r14
0x18005a006  movups  xmmword ptr [rbp+pvar], xmm0
0x18005a00a  mov     rax, [rax+0F8h]
0x18005a011  movdqu  [rbp+var_18], xmm1
0x18005a016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a01b  mov     ebx, eax
0x18005a01d  test    eax, eax
0x18005a01f  js      short loc_18005A082
0x18005a021  mov     rcx, [rbp+ppMFAttributes]
0x18005a025  lea     r8, [rbp+var_38]
0x18005a029  lea     rdx, [rbp+var_18]
0x18005a02d  mov     rax, [rcx]
0x18005a030  mov     rax, [rax+20h]
0x18005a034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a039  test    eax, eax
0x18005a03b  jns     short loc_18005A05E
0x18005a03d  mov     rcx, [rbp+ppMFAttributes]
0x18005a041  lea     r8, [rbp+pvar]
0x18005a045  lea     rdx, [rbp+var_18]
0x18005a049  mov     rax, [rcx]
0x18005a04c  mov     rax, [rax+90h]
0x18005a053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a058  mov     ebx, eax
0x18005a05a  test    eax, eax
0x18005a05c  js      short loc_18005A072
0x18005a05e  lea     rcx, [rbp+pvar]; pvar
0x18005a062  call    cs:__imp_PropVariantClear
0x18005a068  mov     eax, [rbp+var_4C]
0x18005a06b  inc     esi
0x18005a06d  jmp     loc_180059FD7
0x18005a072  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005a079  jb      short loc_18005A0AA
0x18005a07b  mov     edx, 27h ; '''
0x18005a080  jmp     short loc_18005A090
0x18005a082  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005a089  jb      short loc_18005A0AA
0x18005a08b  mov     edx, 26h ; '&'
0x18005a090  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a097  mov     r9, rdi
0x18005a09a  mov     r8, r13
0x18005a09d  mov     dword ptr [rsp+80h+var_60], eax
0x18005a0a1  mov     rcx, [rcx+10h]
0x18005a0a5  call    WPP_SF_qD
0x18005a0aa  lea     rcx, [rbp+pvar]; pvar
0x18005a0ae  call    cs:__imp_PropVariantClear
0x18005a0b4  jmp     short loc_18005A0FD
0x18005a0b6  mov     rax, [rdi]
0x18005a0b9  mov     r8, r15
0x18005a0bc  mov     rdx, [rbp+ppMFAttributes]
0x18005a0c0  mov     rcx, rdi
0x18005a0c3  mov     rax, [rax+178h]
0x18005a0ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a0cf  mov     ebx, eax
0x18005a0d1  test    eax, eax
0x18005a0d3  jns     short loc_18005A116
0x18005a0d5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005a0dc  jb      short loc_18005A0FD
0x18005a0de  mov     edx, 28h ; '('
0x18005a0e3  mov     dword ptr [rsp+80h+var_60], ebx
0x18005a0e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a0ee  mov     r9, rdi
0x18005a0f1  mov     r8, r13
0x18005a0f4  mov     rcx, [rcx+10h]
0x18005a0f8  call    WPP_SF_qD
0x18005a0fd  lea     rcx, [rdi+48h]
0x18005a101  call    ?RemoveAll@?$CTUnkArray@UIMFSensorDeviceIdInternal@@@@QEAAXXZ; CTUnkArray<IMFSensorDeviceIdInternal>::RemoveAll(void)
0x18005a106  cmp     cs:byte_18008D62D, 1
0x18005a10d  jb      short loc_18005A14E
0x18005a10f  mov     edx, 29h ; ')'
0x18005a114  jmp     short loc_18005A131
0x18005a116  mov     rdx, [rbp+ppMFAttributes]
0x18005a11a  lea     rcx, [rdi+40h]
0x18005a11e  call    ??4?$ComSmartPtr@UIMFCameraProfileValidation@@@@QEAAPEAUIMFCameraProfileValidation@@PEAU1@@Z; ComSmartPtr<IMFCameraProfileValidation>::operator=(IMFCameraProfileValidation *)
0x18005a123  cmp     cs:byte_18008D62D, 8
0x18005a12a  jb      short loc_18005A14E
0x18005a12c  mov     edx, 2Ah ; '*'
0x18005a131  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a138  mov     r9, rdi
0x18005a13b  mov     r8, r13
0x18005a13e  mov     dword ptr [rsp+80h+var_60], ebx
0x18005a142  mov     rcx, [rcx+0D8h]
0x18005a149  call    WPP_SF_qD
0x18005a14e  lea     rcx, [rbp+var_40]
0x18005a152  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18005a157  lea     rcx, [rbp+ppMFAttributes]
0x18005a15b  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18005a160  mov     eax, ebx
0x18005a162  mov     rcx, [rbp+var_8]
0x18005a166  xor     rcx, rsp; StackCookie
0x18005a169  call    __security_check_cookie
0x18005a16e  add     rsp, 80h
0x18005a175  pop     r15
0x18005a177  pop     r14
0x18005a179  pop     r13
0x18005a17b  pop     rdi
0x18005a17c  pop     rsi
0x18005a17d  pop     rbx
0x18005a17e  pop     rbp
0x18005a17f  retn
```
