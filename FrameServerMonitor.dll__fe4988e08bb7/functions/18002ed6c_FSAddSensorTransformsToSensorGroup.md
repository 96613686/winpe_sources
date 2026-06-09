# FSAddSensorTransformsToSensorGroup

- ea: `0x18002ed6c`
- end: `0x18002f2dd`
- name: `FSAddSensorTransformsToSensorGroup`
- size: `1393`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800127f0`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180005f98`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x18002ed6c`
- `0x18002f2e4`
- `0x18002f698`
- `0x18002f910`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f282`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002f282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f26f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002f26f`
- `MFPlat!MFCreateCollection` at `0x18002ef4a`
- `MFPlat!MFCreateCollection` at `0x18002ef4a`

## pseudocode

```c
__int64 __fastcall FSAddSensorTransformsToSensorGroup(__int128 *a1, __int64 *a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  unsigned int i; // edi
  __int64 v7; // rax
  __int64 v8; // rdx
  unsigned int j; // edi
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v13; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp-88h] BYREF
  __int64 v15; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v16; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v17; // [rsp+8Ch] [rbp-74h] BYREF
  __int64 v18; // [rsp+90h] [rbp-70h] BYREF
  int v19; // [rsp+98h] [rbp-68h] BYREF
  __int64 v20; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+A8h] [rbp-58h] BYREF
  IID v22; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v23; // [rsp+C0h] [rbp-40h]
  LPVOID pv[2]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v25[264]; // [rsp+E0h] [rbp-20h] BYREF

  v21 = 0;
  v18 = 0;
  v15 = 0;
  v20 = 0;
  memset_0(v25, 0, 0x208u);
  v19 = 0;
  v22 = 0;
  v16 = 0;
  v23 = 0;
  v17 = 0;
  *(_OWORD *)pv = 0;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    WPP_SF_DDDDDDDDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      *((unsigned __int8 *)a1 + 13),
      *((unsigned __int8 *)a1 + 12),
      *(_DWORD *)a1,
      *((_WORD *)a1 + 2),
      *((_WORD *)a1 + 3),
      *((_BYTE *)a1 + 8),
      *((_BYTE *)a1 + 9),
      *((_BYTE *)a1 + 10),
      *((_BYTE *)a1 + 11),
      *((_BYTE *)a1 + 12),
      *((_BYTE *)a1 + 13),
      *((_BYTE *)a1 + 14),
      *((_BYTE *)a1 + 15));
  v22 = 0;
  v23 = 0;
  *(_OWORD *)pv = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_59;
    v5 = 32;
    goto LABEL_6;
  }
  v4 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))*a2)(
         a2,
         &GUID_8e3196f0_ce22_4599_a16a_886bb13a7966,
         &v21);
  if ( v4 >= 0 )
  {
    v23 = *a1;
    v4 = FSCreateSensorTransformFactory((__int64)&v22);
    if ( v4 >= 0 )
    {
      v4 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v22.Data4)(
             *(_QWORD *)v22.Data4,
             &GUID_eed9c2ee_66b4_4f18_a697_ac7d3960215c,
             &v15);
      if ( v4 >= 0 )
      {
        v4 = MFCreateCollection(&v18);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*a2 + 48))(a2, &v16);
          if ( v4 >= 0 )
          {
            for ( i = 0; i < v16; ++i )
            {
              v7 = *a2;
              v14 = 0;
              v13 = 0;
              v4 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(v7 + 56))(a2, i, &v14);
              if ( v4 < 0 )
              {
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_35;
                v8 = 38;
                goto LABEL_34;
              }
              v4 = (**v14)(v14, &GUID_00000000_0000_0000_c000_000000000046, &v13);
              if ( v4 < 0 )
              {
                if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                  goto LABEL_35;
                v8 = 39;
LABEL_34:
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v8,
                  &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids,
                  0,
                  v4);
                goto LABEL_35;
              }
              v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 40LL))(v18, v13);
              if ( v4 < 0 )
              {
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v8 = 40;
                  goto LABEL_34;
                }
LABEL_35:
                wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v13);
                wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v14);
                goto LABEL_59;
              }
              wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v13);
              wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v14);
            }
            v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v15 + 32LL))(
                   v15,
                   0xFFFFFFFFLL,
                   v18,
                   0);
            if ( v4 >= 0 )
            {
              v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 24LL))(v15, &v20);
              if ( v4 >= 0 )
              {
                v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 40LL))(v15, &v17);
                if ( v4 >= 0 )
                {
                  for ( j = 0; ; ++j )
                  {
                    if ( j >= v17 )
                      goto LABEL_59;
                    v13 = 0;
                    v14 = 0;
                    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), __int64 *))(*(_QWORD *)v15 + 48LL))(
                           v15,
                           j,
                           pv,
                           &v14,
                           &v13);
                    if ( v4 < 0 )
                      break;
                    v4 = FSConstructSensorTransformUri(&v22, v25, v10, &v19);
                    if ( v4 < 0 )
                    {
                      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                        goto LABEL_58;
                      v11 = 45;
LABEL_57:
                      WPP_SF_qD(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v11,
                        &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids,
                        0,
                        v4);
                      goto LABEL_58;
                    }
                    v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, __int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64, __int128 *))(*(_QWORD *)v21 + 80LL))(
                           v21,
                           v25,
                           v20,
                           v14,
                           v13,
                           a1);
                    if ( v4 < 0 )
                    {
                      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                      {
                        v11 = 46;
                        goto LABEL_57;
                      }
LABEL_58:
                      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v14);
                      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v13);
                      goto LABEL_59;
                    }
                    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v14);
                    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v13);
                  }
                  if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                    goto LABEL_58;
                  v11 = 44;
                  goto LABEL_57;
                }
                if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
                {
                  v5 = 43;
                  goto LABEL_6;
                }
              }
              else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v5 = 42;
                goto LABEL_6;
              }
            }
            else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v5 = 41;
              goto LABEL_6;
            }
          }
          else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v5 = 37;
            goto LABEL_6;
          }
        }
        else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v5 = 36;
          goto LABEL_6;
        }
      }
      else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v5 = 35;
        goto LABEL_6;
      }
    }
    else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v5 = 34;
      goto LABEL_6;
    }
  }
  else if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v5 = 33;
LABEL_6:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids, 0, v4);
  }
LABEL_59:
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( *(_QWORD *)v22.Data4 )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v22.Data4 + 16LL))(*(_QWORD *)v22.Data4);
    *(_QWORD *)v22.Data4 = 0;
  }
  if ( v22.Data1 == 2 )
  {
    if ( pv[0] )
    {
      CoTaskMemFree(pv[0]);
      pv[0] = 0;
    }
    if ( pv[1] )
    {
      FreeLibrary((HMODULE)pv[1]);
      pv[1] = 0;
    }
  }
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v20);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v15);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v18);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v21);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002ed6c  mov     [rsp-8+arg_10], rbx
0x18002ed71  mov     [rsp-8+arg_18], rsi
0x18002ed76  push    rbp
0x18002ed77  push    rdi
0x18002ed78  push    r12
0x18002ed7a  push    r14
0x18002ed7c  push    r15
0x18002ed7e  lea     rbp, [rsp-200h]
0x18002ed86  sub     rsp, 300h
0x18002ed8d  mov     rax, cs:__security_cookie
0x18002ed94  xor     rax, rsp
0x18002ed97  mov     [rbp+220h+var_30], rax
0x18002ed9e  xor     r12d, r12d
0x18002eda1  mov     r14, rdx
0x18002eda4  mov     r15, rcx
0x18002eda7  mov     [rbp+220h+var_278], r12
0x18002edab  xor     edx, edx; Val
0x18002edad  mov     [rbp+220h+var_290], r12
0x18002edb1  lea     rcx, [rbp+220h+var_240]; void *
0x18002edb5  mov     [rbp+220h+var_2A0], r12
0x18002edb9  mov     r8d, 208h; Size
0x18002edbf  mov     [rbp+220h+var_280], r12
0x18002edc3  call    memset_0
0x18002edc8  xorps   xmm0, xmm0
0x18002edcb  mov     [rbp+220h+var_288], r12d
0x18002edcf  movups  [rbp+220h+var_270], xmm0
0x18002edd3  mov     [rbp+220h+var_298], r12d
0x18002edd7  movups  [rbp+220h+var_260], xmm0
0x18002eddb  mov     [rbp+220h+var_294], r12d
0x18002eddf  movups  xmmword ptr [rbp+220h+pv], xmm0
0x18002ede3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18002ede8  cmp     al, 8
0x18002edea  jb      short loc_18002EE60
0x18002edec  movzx   ecx, byte ptr [r15+0Eh]
0x18002edf1  movzx   r9d, byte ptr [r15+0Bh]
0x18002edf6  movzx   eax, byte ptr [r15+0Fh]
0x18002edfb  movzx   edx, byte ptr [r15+0Dh]
0x18002ee00  movzx   r8d, byte ptr [r15+0Ch]
0x18002ee05  movzx   r10d, byte ptr [r15+0Ah]
0x18002ee0a  movzx   r11d, byte ptr [r15+9]
0x18002ee0f  movzx   ebx, byte ptr [r15+8]
0x18002ee14  movzx   edi, word ptr [r15+6]
0x18002ee19  movzx   esi, word ptr [r15+4]
0x18002ee1e  mov     [rsp+320h+var_2B8], eax
0x18002ee22  mov     [rsp+320h+var_2C0], ecx
0x18002ee26  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee2d  mov     [rsp+320h+var_2C8], edx
0x18002ee31  mov     [rsp+320h+var_2D0], r8d
0x18002ee36  mov     [rsp+320h+var_2D8], r9d
0x18002ee3b  mov     r9d, [r15]
0x18002ee3e  mov     rcx, [rcx+0D8h]
0x18002ee45  mov     [rsp+320h+var_2E0], r10d
0x18002ee4a  mov     [rsp+320h+var_2E8], r11d
0x18002ee4f  mov     [rsp+320h+var_2F0], ebx
0x18002ee53  mov     dword ptr [rsp+320h+var_2F8], edi
0x18002ee57  mov     dword ptr [rsp+320h+var_300], esi
0x18002ee5b  call    WPP_SF_DDDDDDDDDDD
0x18002ee60  xorps   xmm0, xmm0
0x18002ee63  movups  [rbp+220h+var_270], xmm0
0x18002ee67  movups  [rbp+220h+var_260], xmm0
0x18002ee6b  movups  xmmword ptr [rbp+220h+pv], xmm0
0x18002ee6f  test    r14, r14
0x18002ee72  jnz     short loc_18002EEAD
0x18002ee74  mov     ebx, 80070057h
0x18002ee79  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002ee7e  cmp     al, 1
0x18002ee80  jb      loc_18002F22E
0x18002ee86  lea     edx, [r14+20h]
0x18002ee8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee91  lea     r8, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
0x18002ee98  xor     r9d, r9d
0x18002ee9b  mov     dword ptr [rsp+320h+var_300], ebx
0x18002ee9f  mov     rcx, [rcx+10h]
0x18002eea3  call    WPP_SF_qD
0x18002eea8  jmp     loc_18002F22E
0x18002eead  mov     rax, [r14]
0x18002eeb0  lea     r8, [rbp+220h+var_278]
0x18002eeb4  lea     rdx, _GUID_8e3196f0_ce22_4599_a16a_886bb13a7966
0x18002eebb  mov     rcx, r14
0x18002eebe  mov     rax, [rax]
0x18002eec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eec6  mov     ebx, eax
0x18002eec8  test    eax, eax
0x18002eeca  jns     short loc_18002EEE0
0x18002eecc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002eed1  cmp     al, 1
0x18002eed3  jb      loc_18002F22E
0x18002eed9  mov     edx, 21h ; '!'
0x18002eede  jmp     short loc_18002EE8A
0x18002eee0  movups  xmm0, xmmword ptr [r15]
0x18002eee4  lea     rcx, [rbp+220h+var_270]
0x18002eee8  movdqu  [rbp+220h+var_260], xmm0
0x18002eeed  call    FSCreateSensorTransformFactory
0x18002eef2  mov     ebx, eax
0x18002eef4  test    eax, eax
0x18002eef6  jns     short loc_18002EF0F
0x18002eef8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002eefd  cmp     al, 1
0x18002eeff  jb      loc_18002F22E
0x18002ef05  mov     edx, 22h ; '"'
0x18002ef0a  jmp     loc_18002EE8A
0x18002ef0f  mov     rcx, qword ptr [rbp+220h+var_270+8]
0x18002ef13  lea     r8, [rbp+220h+var_2A0]
0x18002ef17  lea     rdx, _GUID_eed9c2ee_66b4_4f18_a697_ac7d3960215c
0x18002ef1e  mov     rax, [rcx]
0x18002ef21  mov     rax, [rax]
0x18002ef24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef29  mov     ebx, eax
0x18002ef2b  test    eax, eax
0x18002ef2d  jns     short loc_18002EF46
0x18002ef2f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002ef34  cmp     al, 1
0x18002ef36  jb      loc_18002F22E
0x18002ef3c  mov     edx, 23h ; '#'
0x18002ef41  jmp     loc_18002EE8A
0x18002ef46  lea     rcx, [rbp+220h+var_290]
0x18002ef4a  call    cs:__imp_MFCreateCollection
0x18002ef50  mov     ebx, eax
0x18002ef52  test    eax, eax
0x18002ef54  jns     short loc_18002EF6D
0x18002ef56  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002ef5b  cmp     al, 1
0x18002ef5d  jb      loc_18002F22E
0x18002ef63  mov     edx, 24h ; '$'
0x18002ef68  jmp     loc_18002EE8A
0x18002ef6d  mov     rax, [r14]
0x18002ef70  lea     rdx, [rbp+220h+var_298]
0x18002ef74  mov     rcx, r14
0x18002ef77  mov     rax, [rax+30h]
0x18002ef7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef80  mov     ebx, eax
0x18002ef82  test    eax, eax
0x18002ef84  jns     short loc_18002EF9D
0x18002ef86  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002ef8b  cmp     al, 1
0x18002ef8d  jb      loc_18002F22E
0x18002ef93  mov     edx, 25h ; '%'
0x18002ef98  jmp     loc_18002EE8A
0x18002ef9d  mov     edi, r12d
0x18002efa0  cmp     edi, [rbp+220h+var_298]
0x18002efa3  jnb     loc_18002F08C
0x18002efa9  mov     rax, [r14]
0x18002efac  lea     r8, [rsp+320h+var_2A8]
0x18002efb1  mov     edx, edi
0x18002efb3  mov     [rsp+320h+var_2A8], r12
0x18002efb8  mov     rcx, r14
0x18002efbb  mov     [rsp+320h+var_2B0], r12
0x18002efc0  mov     rax, [rax+38h]
0x18002efc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efc9  mov     ebx, eax
0x18002efcb  test    eax, eax
0x18002efcd  js      short loc_18002F047
0x18002efcf  mov     rcx, [rsp+320h+var_2A8]
0x18002efd4  lea     r8, [rsp+320h+var_2B0]
0x18002efd9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18002efe0  mov     rax, [rcx]
0x18002efe3  mov     rax, [rax]
0x18002efe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efeb  mov     ebx, eax
0x18002efed  test    eax, eax
0x18002efef  js      short loc_18002F037
0x18002eff1  mov     rcx, [rbp+220h+var_290]
0x18002eff5  mov     rdx, [rsp+320h+var_2B0]
0x18002effa  mov     rax, [rcx]
0x18002effd  mov     rax, [rax+28h]
0x18002f001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f006  mov     ebx, eax
0x18002f008  test    eax, eax
0x18002f00a  js      short loc_18002F027
0x18002f00c  lea     rcx, [rsp+320h+var_2B0]
0x18002f011  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18002f016  lea     rcx, [rsp+320h+var_2A8]
0x18002f01b  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18002f020  inc     edi
0x18002f022  jmp     loc_18002EFA0
0x18002f027  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f02c  cmp     al, 1
0x18002f02e  jb      short loc_18002F073
0x18002f030  mov     edx, 28h ; '('
0x18002f035  jmp     short loc_18002F055
0x18002f037  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f03c  cmp     al, 1
0x18002f03e  jb      short loc_18002F073
0x18002f040  mov     edx, 27h ; '''
0x18002f045  jmp     short loc_18002F055
0x18002f047  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f04c  cmp     al, 1
0x18002f04e  jb      short loc_18002F073
0x18002f050  mov     edx, 26h ; '&'
0x18002f055  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f05c  lea     r8, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
0x18002f063  xor     r9d, r9d
0x18002f066  mov     dword ptr [rsp+320h+var_300], ebx
0x18002f06a  mov     rcx, [rcx+10h]
0x18002f06e  call    WPP_SF_qD
0x18002f073  lea     rcx, [rsp+320h+var_2B0]
0x18002f078  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18002f07d  lea     rcx, [rsp+320h+var_2A8]
0x18002f082  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18002f087  jmp     loc_18002F22E
0x18002f08c  mov     rcx, [rbp+220h+var_2A0]
0x18002f090  xor     r9d, r9d
0x18002f093  mov     r8, [rbp+220h+var_290]
0x18002f097  or      edx, 0FFFFFFFFh
0x18002f09a  mov     rax, [rcx]
0x18002f09d  mov     rax, [rax+20h]
0x18002f0a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0a6  mov     ebx, eax
0x18002f0a8  test    eax, eax
0x18002f0aa  jns     short loc_18002F0C3
0x18002f0ac  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f0b1  cmp     al, 1
0x18002f0b3  jb      loc_18002F22E
0x18002f0b9  mov     edx, 29h ; ')'
0x18002f0be  jmp     loc_18002EE8A
0x18002f0c3  mov     rcx, [rbp+220h+var_2A0]
0x18002f0c7  lea     rdx, [rbp+220h+var_280]
0x18002f0cb  mov     rax, [rcx]
0x18002f0ce  mov     rax, [rax+18h]
0x18002f0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f0d7  mov     ebx, eax
0x18002f0d9  test    eax, eax
0x18002f0db  jns     short loc_18002F0F4
0x18002f0dd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f0e2  cmp     al, 1
0x18002f0e4  jb      loc_18002F22E
0x18002f0ea  mov     edx, 2Ah ; '*'
0x18002f0ef  jmp     loc_18002EE8A
0x18002f0f4  mov     rcx, [rbp+220h+var_2A0]
0x18002f0f8  lea     rdx, [rbp+220h+var_294]
0x18002f0fc  mov     rax, [rcx]
0x18002f0ff  mov     rax, [rax+28h]
0x18002f103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f108  mov     ebx, eax
0x18002f10a  test    eax, eax
0x18002f10c  jns     short loc_18002F125
0x18002f10e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f113  cmp     al, 1
0x18002f115  jb      loc_18002F22E
0x18002f11b  mov     edx, 2Bh ; '+'
0x18002f120  jmp     loc_18002EE8A
0x18002f125  mov     edi, r12d
0x18002f128  cmp     edi, [rbp+220h+var_294]
0x18002f12b  jnb     loc_18002F22E
0x18002f131  mov     rcx, [rbp+220h+var_2A0]
0x18002f135  lea     rdx, [rsp+320h+var_2B0]
0x18002f13a  mov     [rsp+320h+var_2B0], r12
0x18002f13f  lea     r9, [rsp+320h+var_2A8]
0x18002f144  mov     [rsp+320h+var_2A8], r12
0x18002f149  lea     r8, [rbp+220h+pv]
0x18002f14d  mov     [rsp+320h+var_300], rdx
0x18002f152  mov     edx, edi
0x18002f154  mov     rax, [rcx]
0x18002f157  mov     rax, [rax+30h]
0x18002f15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f160  mov     ebx, eax
0x18002f162  test    eax, eax
0x18002f164  js      loc_18002F1EE
0x18002f16a  lea     r9, [rbp+220h+var_288]
0x18002f16e  lea     rdx, [rbp+220h+var_240]
0x18002f172  lea     rcx, [rbp+220h+var_270]
0x18002f176  call    FSConstructSensorTransformUri
0x18002f17b  mov     ebx, eax
0x18002f17d  test    eax, eax
0x18002f17f  js      short loc_18002F1DE
0x18002f181  mov     rdx, [rsp+320h+var_2B0]
0x18002f186  mov     rcx, [rbp+220h+var_278]
0x18002f18a  mov     r9, [rsp+320h+var_2A8]
0x18002f18f  mov     r8, [rbp+220h+var_280]
0x18002f193  mov     [rsp+320h+var_2F8], r15
0x18002f198  mov     rax, [rcx]
0x18002f19b  mov     [rsp+320h+var_300], rdx
0x18002f1a0  lea     rdx, [rbp+220h+var_240]
0x18002f1a4  mov     rax, [rax+50h]
0x18002f1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1ad  mov     ebx, eax
0x18002f1af  test    eax, eax
0x18002f1b1  js      short loc_18002F1CE
0x18002f1b3  lea     rcx, [rsp+320h+var_2A8]
0x18002f1b8  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18002f1bd  lea     rcx, [rsp+320h+var_2B0]
0x18002f1c2  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18002f1c7  inc     edi
0x18002f1c9  jmp     loc_18002F128
0x18002f1ce  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f1d3  cmp     al, 1
0x18002f1d5  jb      short loc_18002F21A
0x18002f1d7  mov     edx, 2Eh ; '.'
0x18002f1dc  jmp     short loc_18002F1FC
0x18002f1de  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f1e3  cmp     al, 1
0x18002f1e5  jb      short loc_18002F21A
0x18002f1e7  mov     edx, 2Dh ; '-'
0x18002f1ec  jmp     short loc_18002F1FC
0x18002f1ee  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002f1f3  cmp     al, 1
0x18002f1f5  jb      short loc_18002F21A
0x18002f1f7  mov     edx, 2Ch ; ','
0x18002f1fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f203  lea     r8, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
  ... truncated ...
```
