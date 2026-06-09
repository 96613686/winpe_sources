# udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::initializer_list_DXCoreHardwareIDParts___

- ea: `0x1400081f4`
- end: `0x140008654`
- name: `udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::initializer_list_DXCoreHardwareIDParts___`
- size: `1120`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015cb8`

## callees

- `0x140005240`
- `0x1400081f4`
- `0x14000a108`
- `0x14000a188`
- `0x14000a29c`
- `0x14000c91c`
- `0x14000e678`
- `0x1400317a8`
- `0x140070010`

## import_xrefs

- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x140008303`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x140008303`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::initializer_list_DXCoreHardwareIDParts___(
        _QWORD *a1,
        int a2,
        _QWORD *a3)
{
  unsigned int v6; // esi
  _DWORD *v7; // r13
  _DWORD *v8; // rax
  _QWORD *v9; // rdx
  int v10; // eax
  _QWORD *v11; // r12
  _QWORD *i; // rdi
  unsigned __int128 v13; // kr00_16
  __int64 v14; // rax
  unsigned int v15; // r14d
  _DWORD *v16; // r12
  __int64 v17; // rax
  _DWORD *v18; // rcx
  __int128 *v19; // rdx
  _OWORD *v20; // rdx
  _DWORD *v21; // rcx
  __int128 *v22; // r8
  const char *v24; // r9
  int v25; // [rsp+20h] [rbp-A9h]
  __int64 v26; // [rsp+30h] [rbp-99h] BYREF
  __int64 *v27; // [rsp+38h] [rbp-91h] BYREF
  __int64 *v28; // [rsp+40h] [rbp-89h] BYREF
  unsigned __int128 v29; // [rsp+48h] [rbp-81h] BYREF
  _QWORD *v30; // [rsp+58h] [rbp-71h]
  int v31; // [rsp+60h] [rbp-69h]
  __int64 *v32; // [rsp+68h] [rbp-61h] BYREF
  __int128 v33; // [rsp+70h] [rbp-59h] BYREF
  __int128 v34; // [rsp+80h] [rbp-49h]
  _DWORD *v35; // [rsp+90h] [rbp-39h] BYREF
  _QWORD *v36; // [rsp+98h] [rbp-31h]
  __int64 v37; // [rsp+A0h] [rbp-29h]
  _QWORD *v38; // [rsp+A8h] [rbp-21h]
  __int128 v39; // [rsp+B0h] [rbp-19h] BYREF
  unsigned int v40; // [rsp+C0h] [rbp-9h]
  char v41; // [rsp+C4h] [rbp-5h] BYREF
  __int128 v42; // [rsp+C8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v37 = -2;
  v38 = a1;
  v6 = 0;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v31 = 1;
  v7 = (_DWORD *)*a3;
  v8 = (_DWORD *)a3[1];
  v35 = v8;
  if ( a2 == 1 && v7 == v8 )
  {
    v24 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x170,
      (unsigned int)"onecore\\internal\\shell\\inc\\npu_detection.h",
      v24,
      v25);
  }
  v29 = 0;
  v30 = 0;
  v27 = DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU;
  std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(&v29, 0, &v27);
  if ( a2 == 1 )
  {
    v27 = DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML;
    if ( *((_QWORD **)&v29 + 1) == v30 )
    {
      std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(&v29, *((_QWORD *)&v29 + 1), &v27);
      v9 = (_QWORD *)*((_QWORD *)&v29 + 1);
    }
    else
    {
      **((_QWORD **)&v29 + 1) = DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML;
      v9 = (_QWORD *)(*((_QWORD *)&v29 + 1) + 8LL);
      *((_QWORD *)&v29 + 1) += 8LL;
    }
    v27 = DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE;
    if ( v9 == v30 )
    {
      std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(&v29, v9, &v27);
    }
    else
    {
      *v9 = DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE;
      *((_QWORD *)&v29 + 1) += 8LL;
    }
  }
  v32 = 0;
  v10 = DXCoreCreateAdapterFactory(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, &v32);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"onecore\\internal\\shell\\inc\\npu_detection.h",
      (const char *)(unsigned int)v10,
      v25);
  v11 = (_QWORD *)*((_QWORD *)&v29 + 1);
  v13 = v29;
  v36 = (_QWORD *)(v13 >> 64);
  for ( i = (_QWORD *)v13; i != v11; ++i )
  {
    v28 = 0;
    v14 = *v32;
    v28 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64, _QWORD, GUID *, __int64 **))(v14 + 24))(
           v32,
           1,
           *i,
           &GUID_526c7776_40e9_459b_b711_f32ad76dfc28,
           &v28) >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64 *))(*v28 + 32))(v28);
      if ( v15 )
      {
        v16 = v35;
        while ( 1 )
        {
          v26 = 0;
          v17 = *v28;
          v26 = 0;
          if ( (*(int (__fastcall **)(__int64 *, _QWORD, GUID *, __int64 *))(v17 + 24))(
                 v28,
                 v6,
                 &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e,
                 &v26) >= 0 )
          {
            if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 40LL))(v26, 11) )
            {
              v39 = 0;
              v40 = 0;
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 40LL))(v26, 14)
                && (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v26 + 48LL))(
                     v26,
                     14,
                     20,
                     &v39) >= 0 )
              {
                goto LABEL_22;
              }
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 40LL))(v26, 3) )
              {
                v42 = 0;
                if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v26 + 48LL))(
                       v26,
                       3,
                       16,
                       &v42) >= 0 )
                  break;
              }
            }
          }
LABEL_44:
          wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v26);
          if ( ++v6 >= v15 )
          {
            v11 = v36;
            v6 = 0;
            goto LABEL_46;
          }
        }
        *(_QWORD *)&v39 = v42;
        v40 = HIDWORD(v42);
        DWORD2(v39) = DWORD2(v42);
LABEL_22:
        v27 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 40LL))(v26, 1)
          && (*(int (__fastcall **)(__int64, __int64, __int64, __int64 **))(*(_QWORD *)v26 + 48LL))(v26, 1, 8, &v27) >= 0 )
        {
          v33 = v39;
          *(_QWORD *)&v34 = v40;
          *((_QWORD *)&v34 + 1) = v27;
          if ( v7 == v16 )
            goto LABEL_33;
          v18 = (_DWORD *)*a3;
LABEL_31:
          if ( v18 != (_DWORD *)a3[1] )
          {
            v19 = &v39;
            while ( *v18 != *(_DWORD *)v19 || v18[1] != *((_DWORD *)v19 + 1) )
            {
              v19 = (__int128 *)((char *)v19 + 20);
              if ( v19 == (__int128 *)&v41 )
              {
                v18 += 5;
                goto LABEL_31;
              }
            }
          }
          if ( v18 != (_DWORD *)a3[1] )
          {
LABEL_33:
            v20 = (_OWORD *)a1[1];
            v21 = (_DWORD *)*a1;
LABEL_39:
            if ( v21 != (_DWORD *)v20 )
            {
              v22 = &v33;
              while ( *v21 != *(_DWORD *)v22 || v21[1] != *((_DWORD *)v22 + 1) )
              {
                v22 += 2;
                if ( v22 == (__int128 *)&v35 )
                {
                  v21 += 8;
                  goto LABEL_39;
                }
              }
            }
            if ( v21 == (_DWORD *)v20 )
            {
              if ( v20 == (_OWORD *)a1[2] )
              {
                std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(
                  a1,
                  v20,
                  &v33);
              }
              else
              {
                *v20 = v33;
                v20[1] = v34;
                a1[1] += 32LL;
              }
            }
          }
        }
        goto LABEL_44;
      }
    }
LABEL_46:
    wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v28);
  }
  wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v32);
  if ( (_QWORD)v29 )
    std::_Deallocate<16>(v29, ((unsigned __int64)v30 - v29) & 0xFFFFFFFFFFFFFFF8uLL);
  return a1;
}

```

## disassembly

```asm
0x1400081f4  push    rbp
0x1400081f6  push    rbx
0x1400081f7  push    rsi
0x1400081f8  push    rdi
0x1400081f9  push    r12
0x1400081fb  push    r13
0x1400081fd  push    r14
0x1400081ff  push    r15
0x140008201  lea     rbp, [rsp-1Fh]
0x140008206  sub     rsp, 0E8h
0x14000820d  mov     [rbp+57h+var_80], 0FFFFFFFFFFFFFFFEh
0x140008215  mov     rax, cs:__security_cookie
0x14000821c  xor     rax, rsp
0x14000821f  mov     [rbp+57h+var_48], rax
0x140008223  mov     r15, r8
0x140008226  mov     edi, edx
0x140008228  mov     rbx, rcx
0x14000822b  mov     [rbp+57h+var_78], rcx
0x14000822f  xor     esi, esi
0x140008231  mov     [rbp+57h+var_C0], esi
0x140008234  mov     [rcx], rsi
0x140008237  mov     [rcx+8], rsi
0x14000823b  mov     [rcx+10h], rsi
0x14000823f  mov     [rbp+57h+var_C0], 1
0x140008246  mov     r13, [r8]
0x140008249  mov     rax, [r8+8]
0x14000824d  mov     [rbp+57h+var_90], rax
0x140008251  cmp     edx, 1
0x140008254  jnz     short loc_14000825F
0x140008256  cmp     r13, rax
0x140008259  jz      loc_140008631
0x14000825f  xorps   xmm0, xmm0
0x140008262  movdqu  [rsp+120h+var_D8], xmm0
0x140008268  mov     [rbp+57h+var_C8], rsi
0x14000826c  lea     rax, DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU
0x140008273  mov     [rsp+120h+var_E8], rax
0x140008278  lea     r8, [rsp+120h+var_E8]
0x14000827d  xor     edx, edx
0x14000827f  lea     rcx, [rsp+120h+var_D8]
0x140008284  call    ??$_Emplace_reallocate@PEBU_GUID@@@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@AEAAPEAPEBU_GUID@@QEAPEBU2@$$QEAPEBU2@@Z; std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(_GUID const * * const,_GUID const * &&)
0x140008289  cmp     edi, 1
0x14000828c  jnz     short loc_1400082F4
0x14000828e  lea     rax, DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML
0x140008295  mov     [rsp+120h+var_E8], rax
0x14000829a  mov     rdx, qword ptr [rbp+57h+var_D8+8]
0x14000829e  cmp     rdx, [rbp+57h+var_C8]
0x1400082a2  jz      short loc_1400082B5
0x1400082a4  mov     [rdx], rax
0x1400082a7  mov     rdx, qword ptr [rbp+57h+var_D8+8]
0x1400082ab  add     rdx, 8
0x1400082af  mov     qword ptr [rbp+57h+var_D8+8], rdx
0x1400082b3  jmp     short loc_1400082C8
0x1400082b5  lea     r8, [rsp+120h+var_E8]
0x1400082ba  lea     rcx, [rsp+120h+var_D8]
0x1400082bf  call    ??$_Emplace_reallocate@PEBU_GUID@@@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@AEAAPEAPEBU_GUID@@QEAPEBU2@$$QEAPEBU2@@Z; std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(_GUID const * * const,_GUID const * &&)
0x1400082c4  mov     rdx, qword ptr [rbp+57h+var_D8+8]
0x1400082c8  lea     rax, DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE
0x1400082cf  mov     [rsp+120h+var_E8], rax
0x1400082d4  cmp     rdx, [rbp+57h+var_C8]
0x1400082d8  jz      short loc_1400082E4
0x1400082da  mov     [rdx], rax
0x1400082dd  add     qword ptr [rbp+57h+var_D8+8], 8
0x1400082e2  jmp     short loc_1400082F4
0x1400082e4  lea     r8, [rsp+120h+var_E8]
0x1400082e9  lea     rcx, [rsp+120h+var_D8]
0x1400082ee  call    ??$_Emplace_reallocate@PEBU_GUID@@@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@AEAAPEAPEBU_GUID@@QEAPEBU2@$$QEAPEBU2@@Z; std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(_GUID const * * const,_GUID const * &&)
0x1400082f3  nop
0x1400082f4  mov     [rbp+57h+var_B8], rsi
0x1400082f8  lea     rdx, [rbp+57h+var_B8]
0x1400082fc  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x140008303  call    cs:__imp_DXCoreCreateAdapterFactory
0x140008309  mov     rcx, [rbp+5Fh]; this
0x14000830d  test    eax, eax
0x14000830f  js      loc_14000861C
0x140008315  mov     rdi, qword ptr [rsp+120h+var_D8]
0x14000831a  mov     r12, qword ptr [rbp+57h+var_D8+8]
0x14000831e  mov     [rbp+57h+var_88], r12
0x140008322  jmp     loc_1400085CC
0x140008327  mov     [rsp+120h+var_E0], rsi
0x14000832c  mov     rcx, [rbp+57h+var_B8]
0x140008330  mov     rax, [rcx]
0x140008333  mov     [rsp+120h+var_E0], rsi
0x140008338  lea     rdx, [rsp+120h+var_E0]
0x14000833d  mov     qword ptr [rsp+120h+var_100], rdx
0x140008342  lea     r9, _GUID_526c7776_40e9_459b_b711_f32ad76dfc28
0x140008349  mov     r8, [rdi]
0x14000834c  mov     edx, 1
0x140008351  mov     rax, [rax+18h]
0x140008355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000835a  test    eax, eax
0x14000835c  js      loc_1400085BE
0x140008362  mov     rcx, [rsp+120h+var_E0]
0x140008367  mov     rax, [rcx]
0x14000836a  mov     rax, [rax+20h]
0x14000836e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008373  mov     r14d, eax
0x140008376  test    eax, eax
0x140008378  jz      loc_1400085BE
0x14000837e  test    eax, eax
0x140008380  jz      loc_1400085BC
0x140008386  mov     r12, [rbp+57h+var_90]
0x14000838a  mov     [rsp+120h+var_F0], 0
0x140008393  mov     rcx, [rsp+120h+var_E0]
0x140008398  mov     rax, [rcx]
0x14000839b  mov     [rsp+120h+var_F0], 0
0x1400083a4  lea     r9, [rsp+120h+var_F0]
0x1400083a9  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x1400083b0  mov     edx, esi
0x1400083b2  mov     rax, [rax+18h]
0x1400083b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400083bb  test    eax, eax
0x1400083bd  js      loc_1400085A3
0x1400083c3  mov     rcx, [rsp+120h+var_F0]
0x1400083c8  mov     rax, [rcx]
0x1400083cb  mov     edx, 0Bh
0x1400083d0  mov     rax, [rax+28h]
0x1400083d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400083d9  test    al, al
0x1400083db  jz      loc_1400085A3
0x1400083e1  xorps   xmm0, xmm0
0x1400083e4  xor     eax, eax
0x1400083e6  movups  [rbp+57h+var_70], xmm0
0x1400083ea  mov     [rbp+57h+var_60], eax
0x1400083ed  mov     rcx, [rsp+120h+var_F0]
0x1400083f2  mov     rax, [rcx]
0x1400083f5  mov     edx, 0Eh
0x1400083fa  mov     rax, [rax+28h]
0x1400083fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008403  test    al, al
0x140008405  jz      short loc_140008429
0x140008407  mov     rcx, [rsp+120h+var_F0]
0x14000840c  mov     rax, [rcx]
0x14000840f  lea     r9, [rbp+57h+var_70]
0x140008413  mov     edx, 0Eh
0x140008418  lea     r8d, [rdx+6]
0x14000841c  mov     rax, [rax+30h]
0x140008420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008425  test    eax, eax
0x140008427  jns     short loc_14000848C
0x140008429  mov     rcx, [rsp+120h+var_F0]
0x14000842e  mov     rax, [rcx]
0x140008431  mov     edx, 3
0x140008436  mov     rax, [rax+28h]
0x14000843a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000843f  test    al, al
0x140008441  jz      loc_1400085A3
0x140008447  xorps   xmm0, xmm0
0x14000844a  movups  [rbp+57h+var_58], xmm0
0x14000844e  mov     rcx, [rsp+120h+var_F0]
0x140008453  mov     rax, [rcx]
0x140008456  lea     r9, [rbp+57h+var_58]
0x14000845a  mov     edx, 3
0x14000845f  lea     r8d, [rdx+0Dh]
0x140008463  mov     rax, [rax+30h]
0x140008467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000846c  test    eax, eax
0x14000846e  js      loc_1400085A3
0x140008474  mov     eax, dword ptr [rbp+57h+var_58]
0x140008477  mov     dword ptr [rbp+57h+var_70], eax
0x14000847a  mov     eax, dword ptr [rbp+57h+var_58+4]
0x14000847d  mov     dword ptr [rbp+57h+var_70+4], eax
0x140008480  mov     eax, dword ptr [rbp+57h+var_58+0Ch]
0x140008483  mov     [rbp+57h+var_60], eax
0x140008486  mov     eax, dword ptr [rbp+57h+var_58+8]
0x140008489  mov     dword ptr [rbp+57h+var_70+8], eax
0x14000848c  mov     [rsp+120h+var_E8], 0
0x140008495  mov     rcx, [rsp+120h+var_F0]
0x14000849a  mov     rax, [rcx]
0x14000849d  mov     edx, 1
0x1400084a2  mov     rax, [rax+28h]
0x1400084a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084ab  test    al, al
0x1400084ad  jz      loc_1400085A3
0x1400084b3  mov     rcx, [rsp+120h+var_F0]
0x1400084b8  mov     rax, [rcx]
0x1400084bb  lea     r9, [rsp+120h+var_E8]
0x1400084c0  mov     edx, 1
0x1400084c5  lea     r8d, [rdx+7]
0x1400084c9  mov     rax, [rax+30h]
0x1400084cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084d2  test    eax, eax
0x1400084d4  js      loc_1400085A3
0x1400084da  mov     eax, dword ptr [rbp+57h+var_70]
0x1400084dd  mov     dword ptr [rbp+57h+var_B0], eax
0x1400084e0  mov     eax, dword ptr [rbp+57h+var_70+4]
0x1400084e3  mov     dword ptr [rbp+57h+var_B0+4], eax
0x1400084e6  mov     eax, dword ptr [rbp+57h+var_70+8]
0x1400084e9  mov     dword ptr [rbp+57h+var_B0+8], eax
0x1400084ec  mov     eax, dword ptr [rbp+57h+var_70+0Ch]
0x1400084ef  mov     dword ptr [rbp+57h+var_B0+0Ch], eax
0x1400084f2  mov     eax, [rbp+57h+var_60]
0x1400084f5  mov     dword ptr [rbp+57h+var_A0], eax
0x1400084f8  xor     eax, eax
0x1400084fa  mov     dword ptr [rbp+57h+var_A0+4], eax
0x1400084fd  mov     rax, [rsp+120h+var_E8]
0x140008502  mov     qword ptr [rbp+57h+var_A0+8], rax
0x140008506  cmp     r13, r12
0x140008509  jz      short loc_140008541
0x14000850b  mov     rcx, [r15]
0x14000850e  jmp     short loc_140008535
0x140008510  lea     rdx, [rbp+57h+var_70]
0x140008514  mov     r8d, [rcx]
0x140008517  cmp     r8d, [rdx]
0x14000851a  jnz     short loc_140008524
0x14000851c  mov     eax, [rdx+4]
0x14000851f  cmp     [rcx+4], eax
0x140008522  jz      short loc_14000853B
0x140008524  add     rdx, 14h
0x140008528  lea     rax, [rbp+57h+var_5C]
0x14000852c  cmp     rdx, rax
0x14000852f  jnz     short loc_140008517
0x140008531  add     rcx, 14h
0x140008535  cmp     rcx, [r15+8]
0x140008539  jnz     short loc_140008510
0x14000853b  cmp     rcx, [r15+8]
0x14000853f  jz      short loc_1400085A3
0x140008541  mov     rdx, [rbx+8]
0x140008545  mov     rcx, [rbx]
0x140008548  jmp     short loc_140008570
0x14000854a  lea     r8, [rbp+57h+var_B0]
0x14000854e  mov     r9d, [rcx]
0x140008551  cmp     r9d, [r8]
0x140008554  jnz     short loc_14000855F
0x140008556  mov     eax, [r8+4]
0x14000855a  cmp     [rcx+4], eax
0x14000855d  jz      short loc_140008575
0x14000855f  add     r8, 20h ; ' '
0x140008563  lea     rax, [rbp+57h+var_90]
0x140008567  cmp     r8, rax
0x14000856a  jnz     short loc_140008551
0x14000856c  add     rcx, 20h ; ' '
0x140008570  cmp     rcx, rdx
0x140008573  jnz     short loc_14000854A
0x140008575  cmp     rcx, rdx
0x140008578  jnz     short loc_1400085A3
0x14000857a  cmp     rdx, [rbx+10h]
0x14000857e  jz      short loc_140008596
0x140008580  movups  xmm0, [rbp+57h+var_B0]
0x140008584  movups  xmmword ptr [rdx], xmm0
0x140008587  movups  xmm1, [rbp+57h+var_A0]
0x14000858b  movups  xmmword ptr [rdx+10h], xmm1
0x14000858f  add     qword ptr [rbx+8], 20h ; ' '
0x140008594  jmp     short loc_1400085A3
0x140008596  lea     r8, [rbp+57h+var_B0]
0x14000859a  mov     rcx, rbx
0x14000859d  call    ??$_Emplace_reallocate@AEBUFoundNpu@npu_detection@udk@@@?$vector@UFoundNpu@npu_detection@udk@@V?$allocator@UFoundNpu@npu_detection@udk@@@std@@@std@@AEAAPEAUFoundNpu@npu_detection@udk@@QEAU234@AEBU234@@Z; std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(udk::npu_detection::FoundNpu * const,udk::npu_detection::FoundNpu const &)
0x1400085a2  nop
0x1400085a3  lea     rcx, [rsp+120h+var_F0]
0x1400085a8  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x1400085ad  inc     esi
0x1400085af  cmp     esi, r14d
0x1400085b2  jb      loc_14000838A
0x1400085b8  mov     r12, [rbp+57h+var_88]
0x1400085bc  xor     esi, esi
0x1400085be  lea     rcx, [rsp+120h+var_E0]
0x1400085c3  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x1400085c8  add     rdi, 8
0x1400085cc  cmp     rdi, r12
0x1400085cf  jnz     loc_140008327
0x1400085d5  lea     rcx, [rbp+57h+var_B8]
0x1400085d9  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x1400085de  nop
0x1400085df  mov     rcx, qword ptr [rsp+120h+var_D8]
0x1400085e4  test    rcx, rcx
0x1400085e7  jz      short loc_1400085F9
0x1400085e9  mov     rdx, [rbp+57h+var_C8]
0x1400085ed  sub     rdx, rcx
0x1400085f0  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1400085f4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400085f9  mov     rax, rbx
0x1400085fc  mov     rcx, [rbp+57h+var_48]
0x140008600  xor     rcx, rsp; StackCookie
0x140008603  call    __security_check_cookie
0x140008608  add     rsp, 0E8h
0x14000860f  pop     r15
0x140008611  pop     r14
0x140008613  pop     r13
0x140008615  pop     r12
0x140008617  pop     rdi
0x140008618  pop     rsi
0x140008619  pop     rbx
0x14000861a  pop     rbp
0x14000861b  retn
0x14000861c  mov     r9d, eax; char *
0x14000861f  lea     r8, aOnecoreInterna_3; "onecore\\internal\\shell\\inc\\npu_dete"...
0x140008626  mov     edx, 17Dh; void *
0x14000862b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140008631  mov     ecx, 80070057h
0x140008636  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x14000863b  mov     r9d, eax; char *
0x14000863e  mov     rcx, [rbp+5Fh]; this
0x140008642  lea     r8, aOnecoreInterna_3; "onecore\\internal\\shell\\inc\\npu_dete"...
0x140008649  mov     edx, 170h; void *
0x14000864e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
