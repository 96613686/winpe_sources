# udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___

- ea: `0x140007dc0`
- end: `0x1400081ec`
- name: `udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___`
- size: `1068`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015cb8`

## callees

- `0x140005240`
- `0x140007dc0`
- `0x14000a108`
- `0x14000a188`
- `0x14000a29c`
- `0x14000c91c`
- `0x14000e678`
- `0x1400317a8`
- `0x140070010`

## import_xrefs

- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x140007eb8`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x140007eb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___(
        _QWORD *a1,
        __int64 a2,
        _DWORD *a3)
{
  unsigned int v5; // esi
  _DWORD *v6; // r15
  _QWORD *v7; // rdx
  int v8; // eax
  _QWORD *i; // rdi
  _QWORD *v10; // r12
  __int64 v11; // rax
  unsigned int v12; // r14d
  __int64 v13; // rax
  _DWORD *v14; // rcx
  __int128 *v15; // rdx
  _OWORD *v16; // rdx
  _DWORD *v17; // rcx
  __int128 *v18; // r8
  int v20; // [rsp+20h] [rbp-99h]
  __int64 v21; // [rsp+30h] [rbp-89h] BYREF
  __int64 *v22; // [rsp+38h] [rbp-81h] BYREF
  __int64 *v23; // [rsp+40h] [rbp-79h] BYREF
  __int128 v24; // [rsp+48h] [rbp-71h] BYREF
  _QWORD *v25; // [rsp+58h] [rbp-61h]
  int v26; // [rsp+60h] [rbp-59h]
  __int64 *v27; // [rsp+68h] [rbp-51h] BYREF
  __int128 v28; // [rsp+70h] [rbp-49h] BYREF
  __int128 v29; // [rsp+80h] [rbp-39h]
  _QWORD v30[2]; // [rsp+90h] [rbp-29h] BYREF
  __int128 v31; // [rsp+A0h] [rbp-19h] BYREF
  unsigned int v32; // [rsp+B0h] [rbp-9h]
  char v33; // [rsp+B4h] [rbp-5h] BYREF
  __int128 v34; // [rsp+B8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v30[0] = -2;
  v30[1] = a1;
  v5 = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v26 = 1;
  v6 = a3 + 15;
  v24 = 0;
  v25 = 0;
  v22 = DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU;
  std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(&v24, 0, &v22);
  v22 = DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML;
  if ( *((_QWORD **)&v24 + 1) == v25 )
  {
    std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(&v24, *((_QWORD *)&v24 + 1), &v22);
    v7 = (_QWORD *)*((_QWORD *)&v24 + 1);
  }
  else
  {
    **((_QWORD **)&v24 + 1) = DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML;
    v7 = (_QWORD *)(*((_QWORD *)&v24 + 1) + 8LL);
    *((_QWORD *)&v24 + 1) += 8LL;
  }
  v22 = DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE;
  if ( v7 == v25 )
  {
    std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(&v24, v7, &v22);
  }
  else
  {
    *v7 = DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE;
    *((_QWORD *)&v24 + 1) += 8LL;
  }
  v27 = 0;
  v8 = DXCoreCreateAdapterFactory(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, &v27);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"onecore\\internal\\shell\\inc\\npu_detection.h",
      (const char *)(unsigned int)v8,
      v20);
  v10 = (_QWORD *)*((_QWORD *)&v24 + 1);
  for ( i = (_QWORD *)v24; i != v10; ++i )
  {
    v23 = 0;
    v11 = *v27;
    v23 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64, _QWORD, GUID *, __int64 **))(v11 + 24))(
           v27,
           1,
           *i,
           &GUID_526c7776_40e9_459b_b711_f32ad76dfc28,
           &v23) >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64 *))(*v23 + 32))(v23);
      if ( v12 )
      {
        while ( 1 )
        {
          v21 = 0;
          v13 = *v23;
          v21 = 0;
          if ( (*(int (__fastcall **)(__int64 *, _QWORD, GUID *, __int64 *))(v13 + 24))(
                 v23,
                 v5,
                 &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e,
                 &v21) >= 0 )
          {
            if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 40LL))(v21, 11) )
            {
              v31 = 0;
              v32 = 0;
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 40LL))(v21, 14)
                && (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v21 + 48LL))(
                     v21,
                     14,
                     20,
                     &v31) >= 0 )
              {
                goto LABEL_18;
              }
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 40LL))(v21, 3) )
              {
                v34 = 0;
                if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v21 + 48LL))(
                       v21,
                       3,
                       16,
                       &v34) >= 0 )
                  break;
              }
            }
          }
LABEL_38:
          wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v21);
          if ( ++v5 >= v12 )
          {
            v5 = 0;
            goto LABEL_40;
          }
        }
        *(_QWORD *)&v31 = v34;
        v32 = HIDWORD(v34);
        DWORD2(v31) = DWORD2(v34);
LABEL_18:
        v22 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 40LL))(v21, 1)
          && (*(int (__fastcall **)(__int64, __int64, __int64, __int64 **))(*(_QWORD *)v21 + 48LL))(v21, 1, 8, &v22) >= 0 )
        {
          v28 = v31;
          *(_QWORD *)&v29 = v32;
          *((_QWORD *)&v29 + 1) = v22;
          v14 = a3;
LABEL_21:
          v15 = &v31;
          while ( *v14 != *(_DWORD *)v15 || v14[1] != *((_DWORD *)v15 + 1) )
          {
            v15 = (__int128 *)((char *)v15 + 20);
            if ( v15 == (__int128 *)&v33 )
            {
              v14 += 5;
              if ( v14 != v6 )
                goto LABEL_21;
              break;
            }
          }
          if ( v14 != v6 )
          {
            v16 = (_OWORD *)a1[1];
            v17 = (_DWORD *)*a1;
LABEL_33:
            if ( v17 != (_DWORD *)v16 )
            {
              v18 = &v28;
              while ( *v17 != *(_DWORD *)v18 || v17[1] != *((_DWORD *)v18 + 1) )
              {
                v18 += 2;
                if ( v18 == (__int128 *)v30 )
                {
                  v17 += 8;
                  goto LABEL_33;
                }
              }
            }
            if ( v17 == (_DWORD *)v16 )
            {
              if ( v16 == (_OWORD *)a1[2] )
              {
                std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(
                  a1,
                  v16,
                  &v28);
              }
              else
              {
                *v16 = v28;
                v16[1] = v29;
                a1[1] += 32LL;
              }
            }
          }
        }
        goto LABEL_38;
      }
    }
LABEL_40:
    wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v23);
  }
  wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v27);
  if ( (_QWORD)v24 )
    std::_Deallocate<16>(v24, ((unsigned __int64)v25 - v24) & 0xFFFFFFFFFFFFFFF8uLL);
  return a1;
}

```

## disassembly

```asm
0x140007dc0  push    rbp
0x140007dc2  push    rbx
0x140007dc3  push    rsi
0x140007dc4  push    rdi
0x140007dc5  push    r12
0x140007dc7  push    r13
0x140007dc9  push    r14
0x140007dcb  push    r15
0x140007dcd  lea     rbp, [rsp-1Fh]
0x140007dd2  sub     rsp, 0D8h
0x140007dd9  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFEh
0x140007de1  mov     rax, cs:__security_cookie
0x140007de8  xor     rax, rsp
0x140007deb  mov     [rbp+57h+var_48], rax
0x140007def  mov     r13, r8
0x140007df2  mov     rbx, rcx
0x140007df5  mov     [rbp+57h+var_78], rcx
0x140007df9  xor     esi, esi
0x140007dfb  mov     [rbp+57h+var_B0], esi
0x140007dfe  mov     [rcx], rsi
0x140007e01  mov     [rcx+8], rsi
0x140007e05  mov     [rcx+10h], rsi
0x140007e09  mov     [rbp+57h+var_B0], 1
0x140007e10  lea     r15, [r8+3Ch]
0x140007e14  cmp     r8, r15
0x140007e17  jz      loc_1400081C9
0x140007e1d  xorps   xmm0, xmm0
0x140007e20  movdqu  [rbp+57h+var_C8], xmm0
0x140007e25  mov     [rbp+57h+var_B8], rsi
0x140007e29  lea     rax, DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU
0x140007e30  mov     [rsp+110h+var_D8], rax
0x140007e35  lea     r8, [rsp+110h+var_D8]
0x140007e3a  xor     edx, edx
0x140007e3c  lea     rcx, [rbp+57h+var_C8]
0x140007e40  call    ??$_Emplace_reallocate@PEBU_GUID@@@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@AEAAPEAPEBU_GUID@@QEAPEBU2@$$QEAPEBU2@@Z; std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(_GUID const * * const,_GUID const * &&)
0x140007e45  lea     rax, DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML
0x140007e4c  mov     [rsp+110h+var_D8], rax
0x140007e51  mov     rdx, qword ptr [rbp+57h+var_C8+8]
0x140007e55  cmp     rdx, [rbp+57h+var_B8]
0x140007e59  jz      short loc_140007E6C
0x140007e5b  mov     [rdx], rax
0x140007e5e  mov     rdx, qword ptr [rbp+57h+var_C8+8]
0x140007e62  add     rdx, 8
0x140007e66  mov     qword ptr [rbp+57h+var_C8+8], rdx
0x140007e6a  jmp     short loc_140007E7E
0x140007e6c  lea     r8, [rsp+110h+var_D8]
0x140007e71  lea     rcx, [rbp+57h+var_C8]
0x140007e75  call    ??$_Emplace_reallocate@PEBU_GUID@@@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@AEAAPEAPEBU_GUID@@QEAPEBU2@$$QEAPEBU2@@Z; std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(_GUID const * * const,_GUID const * &&)
0x140007e7a  mov     rdx, qword ptr [rbp+57h+var_C8+8]
0x140007e7e  lea     rax, DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE
0x140007e85  mov     [rsp+110h+var_D8], rax
0x140007e8a  cmp     rdx, [rbp+57h+var_B8]
0x140007e8e  jz      short loc_140007E9A
0x140007e90  mov     [rdx], rax
0x140007e93  add     qword ptr [rbp+57h+var_C8+8], 8
0x140007e98  jmp     short loc_140007EA9
0x140007e9a  lea     r8, [rsp+110h+var_D8]
0x140007e9f  lea     rcx, [rbp+57h+var_C8]
0x140007ea3  call    ??$_Emplace_reallocate@PEBU_GUID@@@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@AEAAPEAPEBU_GUID@@QEAPEBU2@$$QEAPEBU2@@Z; std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(_GUID const * * const,_GUID const * &&)
0x140007ea8  nop
0x140007ea9  mov     [rbp+57h+var_A8], rsi
0x140007ead  lea     rdx, [rbp+57h+var_A8]
0x140007eb1  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x140007eb8  call    cs:__imp_DXCoreCreateAdapterFactory
0x140007ebe  mov     rcx, [rbp+5Fh]; this
0x140007ec2  test    eax, eax
0x140007ec4  js      loc_1400081B4
0x140007eca  mov     rdi, qword ptr [rbp+57h+var_C8]
0x140007ece  mov     r12, qword ptr [rbp+57h+var_C8+8]
0x140007ed2  jmp     loc_140008165
0x140007ed7  mov     [rbp+57h+var_D0], rsi
0x140007edb  mov     rcx, [rbp+57h+var_A8]
0x140007edf  mov     rax, [rcx]
0x140007ee2  mov     [rbp+57h+var_D0], rsi
0x140007ee6  lea     rdx, [rbp+57h+var_D0]
0x140007eea  mov     qword ptr [rsp+110h+var_F0], rdx
0x140007eef  lea     r9, _GUID_526c7776_40e9_459b_b711_f32ad76dfc28
0x140007ef6  mov     r8, [rdi]
0x140007ef9  mov     edx, 1
0x140007efe  mov     rax, [rax+18h]
0x140007f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f07  test    eax, eax
0x140007f09  js      loc_140008158
0x140007f0f  mov     rcx, [rbp+57h+var_D0]
0x140007f13  mov     rax, [rcx]
0x140007f16  mov     rax, [rax+20h]
0x140007f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f1f  mov     r14d, eax
0x140007f22  test    eax, eax
0x140007f24  jz      loc_140008158
0x140007f2a  test    eax, eax
0x140007f2c  jz      loc_140008156
0x140007f32  mov     [rsp+110h+var_E0], 0
0x140007f3b  mov     rcx, [rbp+57h+var_D0]
0x140007f3f  mov     rax, [rcx]
0x140007f42  mov     [rsp+110h+var_E0], 0
0x140007f4b  lea     r9, [rsp+110h+var_E0]
0x140007f50  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x140007f57  mov     edx, esi
0x140007f59  mov     rax, [rax+18h]
0x140007f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f62  test    eax, eax
0x140007f64  js      loc_140008141
0x140007f6a  mov     rcx, [rsp+110h+var_E0]
0x140007f6f  mov     rax, [rcx]
0x140007f72  mov     edx, 0Bh
0x140007f77  mov     rax, [rax+28h]
0x140007f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007f80  test    al, al
0x140007f82  jz      loc_140008141
0x140007f88  xorps   xmm0, xmm0
0x140007f8b  xor     eax, eax
0x140007f8d  movups  [rbp+57h+var_70], xmm0
0x140007f91  mov     [rbp+57h+var_60], eax
0x140007f94  mov     rcx, [rsp+110h+var_E0]
0x140007f99  mov     rax, [rcx]
0x140007f9c  mov     edx, 0Eh
0x140007fa1  mov     rax, [rax+28h]
0x140007fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007faa  test    al, al
0x140007fac  jz      short loc_140007FD0
0x140007fae  mov     rcx, [rsp+110h+var_E0]
0x140007fb3  mov     rax, [rcx]
0x140007fb6  lea     r9, [rbp+57h+var_70]
0x140007fba  mov     edx, 0Eh
0x140007fbf  lea     r8d, [rdx+6]
0x140007fc3  mov     rax, [rax+30h]
0x140007fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007fcc  test    eax, eax
0x140007fce  jns     short loc_140008033
0x140007fd0  mov     rcx, [rsp+110h+var_E0]
0x140007fd5  mov     rax, [rcx]
0x140007fd8  mov     edx, 3
0x140007fdd  mov     rax, [rax+28h]
0x140007fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007fe6  test    al, al
0x140007fe8  jz      loc_140008141
0x140007fee  xorps   xmm0, xmm0
0x140007ff1  movups  [rbp+57h+var_58], xmm0
0x140007ff5  mov     rcx, [rsp+110h+var_E0]
0x140007ffa  mov     rax, [rcx]
0x140007ffd  lea     r9, [rbp+57h+var_58]
0x140008001  mov     edx, 3
0x140008006  lea     r8d, [rdx+0Dh]
0x14000800a  mov     rax, [rax+30h]
0x14000800e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008013  test    eax, eax
0x140008015  js      loc_140008141
0x14000801b  mov     eax, dword ptr [rbp+57h+var_58]
0x14000801e  mov     dword ptr [rbp+57h+var_70], eax
0x140008021  mov     eax, dword ptr [rbp+57h+var_58+4]
0x140008024  mov     dword ptr [rbp+57h+var_70+4], eax
0x140008027  mov     eax, dword ptr [rbp+57h+var_58+0Ch]
0x14000802a  mov     [rbp+57h+var_60], eax
0x14000802d  mov     eax, dword ptr [rbp+57h+var_58+8]
0x140008030  mov     dword ptr [rbp+57h+var_70+8], eax
0x140008033  mov     [rsp+110h+var_D8], 0
0x14000803c  mov     rcx, [rsp+110h+var_E0]
0x140008041  mov     rax, [rcx]
0x140008044  mov     edx, 1
0x140008049  mov     rax, [rax+28h]
0x14000804d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008052  test    al, al
0x140008054  jz      loc_140008141
0x14000805a  mov     rcx, [rsp+110h+var_E0]
0x14000805f  mov     rax, [rcx]
0x140008062  lea     r9, [rsp+110h+var_D8]
0x140008067  mov     edx, 1
0x14000806c  lea     r8d, [rdx+7]
0x140008070  mov     rax, [rax+30h]
0x140008074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008079  test    eax, eax
0x14000807b  js      loc_140008141
0x140008081  mov     eax, dword ptr [rbp+57h+var_70]
0x140008084  mov     dword ptr [rbp+57h+var_A0], eax
0x140008087  mov     eax, dword ptr [rbp+57h+var_70+4]
0x14000808a  mov     dword ptr [rbp+57h+var_A0+4], eax
0x14000808d  mov     eax, dword ptr [rbp+57h+var_70+8]
0x140008090  mov     dword ptr [rbp+57h+var_A0+8], eax
0x140008093  mov     eax, dword ptr [rbp+57h+var_70+0Ch]
0x140008096  mov     dword ptr [rbp+57h+var_A0+0Ch], eax
0x140008099  mov     eax, [rbp+57h+var_60]
0x14000809c  mov     dword ptr [rbp+57h+var_90], eax
0x14000809f  xor     eax, eax
0x1400080a1  mov     dword ptr [rbp+57h+var_90+4], eax
0x1400080a4  mov     rax, [rsp+110h+var_D8]
0x1400080a9  mov     qword ptr [rbp+57h+var_90+8], rax
0x1400080ad  mov     rcx, r13
0x1400080b0  lea     rdx, [rbp+57h+var_70]
0x1400080b4  mov     r8d, [rcx]
0x1400080b7  cmp     r8d, [rdx]
0x1400080ba  jnz     short loc_1400080C4
0x1400080bc  mov     eax, [rdx+4]
0x1400080bf  cmp     [rcx+4], eax
0x1400080c2  jz      short loc_1400080DA
0x1400080c4  add     rdx, 14h
0x1400080c8  lea     rax, [rbp+57h+var_5C]
0x1400080cc  cmp     rdx, rax
0x1400080cf  jnz     short loc_1400080B7
0x1400080d1  add     rcx, 14h
0x1400080d5  cmp     rcx, r15
0x1400080d8  jnz     short loc_1400080B0
0x1400080da  cmp     rcx, r15
0x1400080dd  jz      short loc_140008141
0x1400080df  mov     rdx, [rbx+8]
0x1400080e3  mov     rcx, [rbx]
0x1400080e6  jmp     short loc_14000810E
0x1400080e8  lea     r8, [rbp+57h+var_A0]
0x1400080ec  mov     r9d, [rcx]
0x1400080ef  cmp     r9d, [r8]
0x1400080f2  jnz     short loc_1400080FD
0x1400080f4  mov     eax, [r8+4]
0x1400080f8  cmp     [rcx+4], eax
0x1400080fb  jz      short loc_140008113
0x1400080fd  add     r8, 20h ; ' '
0x140008101  lea     rax, [rbp+57h+var_80]
0x140008105  cmp     r8, rax
0x140008108  jnz     short loc_1400080EF
0x14000810a  add     rcx, 20h ; ' '
0x14000810e  cmp     rcx, rdx
0x140008111  jnz     short loc_1400080E8
0x140008113  cmp     rcx, rdx
0x140008116  jnz     short loc_140008141
0x140008118  cmp     rdx, [rbx+10h]
0x14000811c  jz      short loc_140008134
0x14000811e  movups  xmm0, [rbp+57h+var_A0]
0x140008122  movups  xmmword ptr [rdx], xmm0
0x140008125  movups  xmm1, [rbp+57h+var_90]
0x140008129  movups  xmmword ptr [rdx+10h], xmm1
0x14000812d  add     qword ptr [rbx+8], 20h ; ' '
0x140008132  jmp     short loc_140008141
0x140008134  lea     r8, [rbp+57h+var_A0]
0x140008138  mov     rcx, rbx
0x14000813b  call    ??$_Emplace_reallocate@AEBUFoundNpu@npu_detection@udk@@@?$vector@UFoundNpu@npu_detection@udk@@V?$allocator@UFoundNpu@npu_detection@udk@@@std@@@std@@AEAAPEAUFoundNpu@npu_detection@udk@@QEAU234@AEBU234@@Z; std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(udk::npu_detection::FoundNpu * const,udk::npu_detection::FoundNpu const &)
0x140008140  nop
0x140008141  lea     rcx, [rsp+110h+var_E0]
0x140008146  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x14000814b  inc     esi
0x14000814d  cmp     esi, r14d
0x140008150  jb      loc_140007F32
0x140008156  xor     esi, esi
0x140008158  lea     rcx, [rbp+57h+var_D0]
0x14000815c  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x140008161  add     rdi, 8
0x140008165  cmp     rdi, r12
0x140008168  jnz     loc_140007ED7
0x14000816e  lea     rcx, [rbp+57h+var_A8]
0x140008172  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x140008177  nop
0x140008178  mov     rcx, qword ptr [rbp+57h+var_C8]
0x14000817c  test    rcx, rcx
0x14000817f  jz      short loc_140008191
0x140008181  mov     rdx, [rbp+57h+var_B8]
0x140008185  sub     rdx, rcx
0x140008188  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14000818c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140008191  mov     rax, rbx
0x140008194  mov     rcx, [rbp+57h+var_48]
0x140008198  xor     rcx, rsp; StackCookie
0x14000819b  call    __security_check_cookie
0x1400081a0  add     rsp, 0D8h
0x1400081a7  pop     r15
0x1400081a9  pop     r14
0x1400081ab  pop     r13
0x1400081ad  pop     r12
0x1400081af  pop     rdi
0x1400081b0  pop     rsi
0x1400081b1  pop     rbx
0x1400081b2  pop     rbp
0x1400081b3  retn
0x1400081b4  mov     r9d, eax; char *
0x1400081b7  lea     r8, aOnecoreInterna_3; "onecore\\internal\\shell\\inc\\npu_dete"...
0x1400081be  mov     edx, 17Dh; void *
0x1400081c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400081c9  mov     ecx, 80070057h
0x1400081ce  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1400081d3  mov     r9d, eax; char *
0x1400081d6  mov     rcx, [rbp+5Fh]; this
0x1400081da  lea     r8, aOnecoreInterna_3; "onecore\\internal\\shell\\inc\\npu_dete"...
0x1400081e1  mov     edx, 170h; void *
0x1400081e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
