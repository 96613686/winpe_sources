# udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___

- ea: `0x18000d924`
- end: `0x18000dd5b`
- name: `udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___`
- size: `1079`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800151ac`

## callees

- `0x180002590`
- `0x180004ad0`
- `0x18000d924`
- `0x18000f350`
- `0x18000f4e0`
- `0x180013fd0`
- `0x18001f198`
- `0x18002065c`
- `0x180033010`

## import_xrefs

- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x18000da14`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x18000da14`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___(
        _QWORD *a1,
        __int64 a2,
        _DWORD *a3)
{
  unsigned int v5; // esi
  _DWORD *v6; // r15
  _QWORD *v7; // rdx
  int AdapterFactory; // eax
  _QWORD *i; // rdi
  _QWORD *v10; // r12
  __int64 v11; // rax
  unsigned int v12; // r14d
  __int64 v13; // rax
  _DWORD *v14; // rcx
  __int128 *v15; // rdx
  _OWORD *v16; // rdx
  _DWORD *v17; // rcx
  __int64 *v18; // r8
  int v20; // [rsp+20h] [rbp-99h]
  __int64 v21; // [rsp+30h] [rbp-89h] BYREF
  __int64 *v22; // [rsp+38h] [rbp-81h] BYREF
  __int64 *v23; // [rsp+40h] [rbp-79h] BYREF
  __int128 v24; // [rsp+48h] [rbp-71h] BYREF
  _QWORD *v25; // [rsp+58h] [rbp-61h]
  int v26; // [rsp+60h] [rbp-59h]
  _QWORD v27[2]; // [rsp+68h] [rbp-51h] BYREF
  __int128 v28; // [rsp+78h] [rbp-41h] BYREF
  unsigned int v29; // [rsp+88h] [rbp-31h]
  char v30; // [rsp+8Ch] [rbp-2Dh] BYREF
  __int128 v31; // [rsp+90h] [rbp-29h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v33; // [rsp+B0h] [rbp-9h]
  __int64 v34; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v27[1] = a1;
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
  v27[0] = 0;
  AdapterFactory = DXCoreCreateAdapterFactory(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, v27);
  if ( AdapterFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\npu_detection.h",
      (const char *)(unsigned int)AdapterFactory,
      v20);
  v10 = (_QWORD *)*((_QWORD *)&v24 + 1);
  for ( i = (_QWORD *)v24; i != v10; ++i )
  {
    v23 = 0;
    v11 = *(_QWORD *)v27[0];
    v23 = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int64, _QWORD, GUID *, __int64 **))(v11 + 24))(
           v27[0],
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
              v28 = 0;
              v29 = 0;
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 40LL))(v21, 14)
                && (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v21 + 48LL))(
                     v21,
                     14,
                     20,
                     &v28) >= 0 )
              {
                goto LABEL_18;
              }
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 40LL))(v21, 3) )
              {
                v31 = 0;
                if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v21 + 48LL))(
                       v21,
                       3,
                       16,
                       &v31) >= 0 )
                  break;
              }
            }
          }
LABEL_38:
          if ( v21 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          if ( ++v5 >= v12 )
          {
            v5 = 0;
            goto LABEL_42;
          }
        }
        *(_QWORD *)&v28 = v31;
        v29 = HIDWORD(v31);
        DWORD2(v28) = DWORD2(v31);
LABEL_18:
        v22 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 40LL))(v21, 1)
          && (*(int (__fastcall **)(__int64, __int64, __int64, __int64 **))(*(_QWORD *)v21 + 48LL))(v21, 1, 8, &v22) >= 0 )
        {
          v32 = v28;
          *(_QWORD *)&v33 = v29;
          *((_QWORD *)&v33 + 1) = v22;
          v14 = a3;
LABEL_21:
          v15 = &v28;
          while ( *v14 != *(_DWORD *)v15 || v14[1] != *((_DWORD *)v15 + 1) )
          {
            v15 = (__int128 *)((char *)v15 + 20);
            if ( v15 == (__int128 *)&v30 )
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
              v18 = (__int64 *)&v32;
              while ( *v17 != *(_DWORD *)v18 || v17[1] != *((_DWORD *)v18 + 1) )
              {
                v18 += 4;
                if ( v18 == &v34 )
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
                  &v32);
              }
              else
              {
                *v16 = v32;
                v16[1] = v33;
                a1[1] += 32LL;
              }
            }
          }
        }
        goto LABEL_38;
      }
    }
LABEL_42:
    if ( v23 )
      (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
  }
  if ( v27[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v27[0] + 16LL))(v27[0]);
  std::vector<_GUID const *>::~vector<_GUID const *>(&v24);
  return a1;
}

```

## disassembly

```asm
0x18000d924  push    rbp
0x18000d926  push    rbx
0x18000d927  push    rsi
0x18000d928  push    rdi
0x18000d929  push    r12
0x18000d92b  push    r13
0x18000d92d  push    r14
0x18000d92f  push    r15
0x18000d931  lea     rbp, [rsp-1Fh]
0x18000d936  sub     rsp, 0D8h
0x18000d93d  mov     rax, cs:__security_cookie
0x18000d944  xor     rax, rsp
0x18000d947  mov     [rbp+57h+var_50], rax
0x18000d94b  mov     r13, r8
0x18000d94e  mov     rbx, rcx
0x18000d951  mov     [rbp+57h+var_A0], rcx
0x18000d955  xor     esi, esi
0x18000d957  mov     [rbp+57h+var_B0], esi
0x18000d95a  mov     [rcx], rsi
0x18000d95d  mov     [rcx+8], rsi
0x18000d961  mov     [rcx+10h], rsi
0x18000d965  mov     [rbp+57h+var_B0], 1
0x18000d96c  lea     r15, [r8+3Ch]
0x18000d970  cmp     r8, r15
0x18000d973  jz      loc_18000DD44
0x18000d979  xorps   xmm0, xmm0
0x18000d97c  movdqu  [rbp+57h+var_C8], xmm0
0x18000d981  mov     [rbp+57h+var_B8], rsi
0x18000d985  lea     rax, DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU
0x18000d98c  mov     [rsp+110h+var_D8], rax
0x18000d991  lea     r8, [rsp+110h+var_D8]
0x18000d996  xor     edx, edx
0x18000d998  lea     rcx, [rbp+57h+var_C8]
0x18000d99c  call    ??$_Emplace_reallocate@PEBU_GUID@@@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@AEAAPEAPEBU_GUID@@QEAPEBU2@$$QEAPEBU2@@Z; std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(_GUID const * * const,_GUID const * &&)
0x18000d9a1  lea     rax, DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML
0x18000d9a8  mov     [rsp+110h+var_D8], rax
0x18000d9ad  mov     rdx, qword ptr [rbp+57h+var_C8+8]
0x18000d9b1  cmp     rdx, [rbp+57h+var_B8]
0x18000d9b5  jz      short loc_18000D9C8
0x18000d9b7  mov     [rdx], rax
0x18000d9ba  mov     rdx, qword ptr [rbp+57h+var_C8+8]
0x18000d9be  add     rdx, 8
0x18000d9c2  mov     qword ptr [rbp+57h+var_C8+8], rdx
0x18000d9c6  jmp     short loc_18000D9DA
0x18000d9c8  lea     r8, [rsp+110h+var_D8]
0x18000d9cd  lea     rcx, [rbp+57h+var_C8]
0x18000d9d1  call    ??$_Emplace_reallocate@PEBU_GUID@@@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@AEAAPEAPEBU_GUID@@QEAPEBU2@$$QEAPEBU2@@Z; std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(_GUID const * * const,_GUID const * &&)
0x18000d9d6  mov     rdx, qword ptr [rbp+57h+var_C8+8]
0x18000d9da  lea     rax, DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE
0x18000d9e1  mov     [rsp+110h+var_D8], rax
0x18000d9e6  cmp     rdx, [rbp+57h+var_B8]
0x18000d9ea  jz      short loc_18000D9F6
0x18000d9ec  mov     [rdx], rax
0x18000d9ef  add     qword ptr [rbp+57h+var_C8+8], 8
0x18000d9f4  jmp     short loc_18000DA05
0x18000d9f6  lea     r8, [rsp+110h+var_D8]
0x18000d9fb  lea     rcx, [rbp+57h+var_C8]
0x18000d9ff  call    ??$_Emplace_reallocate@PEBU_GUID@@@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@AEAAPEAPEBU_GUID@@QEAPEBU2@$$QEAPEBU2@@Z; std::vector<_GUID const *>::_Emplace_reallocate<_GUID const *>(_GUID const * * const,_GUID const * &&)
0x18000da04  nop
0x18000da05  mov     [rbp+57h+var_A8], rsi
0x18000da09  lea     rdx, [rbp+57h+var_A8]
0x18000da0d  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x18000da14  call    cs:__imp_DXCoreCreateAdapterFactory
0x18000da1a  mov     rcx, [rbp+5Fh]; this
0x18000da1e  test    eax, eax
0x18000da20  js      loc_18000DD2F
0x18000da26  mov     rdi, qword ptr [rbp+57h+var_C8]
0x18000da2a  mov     r12, qword ptr [rbp+57h+var_C8+8]
0x18000da2e  jmp     loc_18000DCE4
0x18000da33  mov     [rbp+57h+var_D0], rsi
0x18000da37  mov     rcx, [rbp+57h+var_A8]
0x18000da3b  mov     rax, [rcx]
0x18000da3e  mov     [rbp+57h+var_D0], rsi
0x18000da42  lea     rdx, [rbp+57h+var_D0]
0x18000da46  mov     qword ptr [rsp+110h+var_F0], rdx
0x18000da4b  lea     r9, _GUID_526c7776_40e9_459b_b711_f32ad76dfc28
0x18000da52  mov     r8, [rdi]
0x18000da55  mov     edx, 1
0x18000da5a  mov     rax, [rax+18h]
0x18000da5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da63  test    eax, eax
0x18000da65  jns     short loc_18000DA6C
0x18000da67  jmp     loc_18000DCCA
0x18000da6c  mov     rcx, [rbp+57h+var_D0]
0x18000da70  mov     rax, [rcx]
0x18000da73  mov     rax, [rax+20h]
0x18000da77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da7c  mov     r14d, eax
0x18000da7f  test    eax, eax
0x18000da81  jnz     short loc_18000DA88
0x18000da83  jmp     loc_18000DCCA
0x18000da88  test    r14d, r14d
0x18000da8b  jz      loc_18000DCC8
0x18000da91  mov     [rsp+110h+var_E0], 0
0x18000da9a  mov     rcx, [rbp+57h+var_D0]
0x18000da9e  mov     rax, [rcx]
0x18000daa1  mov     [rsp+110h+var_E0], 0
0x18000daaa  lea     r9, [rsp+110h+var_E0]
0x18000daaf  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x18000dab6  mov     edx, esi
0x18000dab8  mov     rax, [rax+18h]
0x18000dabc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dac1  test    eax, eax
0x18000dac3  jns     short loc_18000DACA
0x18000dac5  jmp     loc_18000DCA6
0x18000daca  mov     rcx, [rsp+110h+var_E0]
0x18000dacf  mov     rax, [rcx]
0x18000dad2  mov     edx, 0Bh
0x18000dad7  mov     rax, [rax+28h]
0x18000dadb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dae0  test    al, al
0x18000dae2  jnz     short loc_18000DAE9
0x18000dae4  jmp     loc_18000DCA6
0x18000dae9  xorps   xmm0, xmm0
0x18000daec  xor     eax, eax
0x18000daee  movups  [rbp+57h+var_98], xmm0
0x18000daf2  mov     [rbp+57h+var_88], eax
0x18000daf5  mov     rcx, [rsp+110h+var_E0]
0x18000dafa  mov     rax, [rcx]
0x18000dafd  mov     edx, 0Eh
0x18000db02  mov     rax, [rax+28h]
0x18000db06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db0b  test    al, al
0x18000db0d  jz      short loc_18000DB31
0x18000db0f  mov     rcx, [rsp+110h+var_E0]
0x18000db14  mov     rax, [rcx]
0x18000db17  lea     r9, [rbp+57h+var_98]
0x18000db1b  mov     edx, 0Eh
0x18000db20  lea     r8d, [rdx+6]
0x18000db24  mov     rax, [rax+30h]
0x18000db28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db2d  test    eax, eax
0x18000db2f  jns     short loc_18000DB94
0x18000db31  mov     rcx, [rsp+110h+var_E0]
0x18000db36  mov     rax, [rcx]
0x18000db39  mov     edx, 3
0x18000db3e  mov     rax, [rax+28h]
0x18000db42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db47  test    al, al
0x18000db49  jz      loc_18000DCA6
0x18000db4f  xorps   xmm0, xmm0
0x18000db52  movups  [rbp+57h+var_80], xmm0
0x18000db56  mov     rcx, [rsp+110h+var_E0]
0x18000db5b  mov     rax, [rcx]
0x18000db5e  lea     r9, [rbp+57h+var_80]
0x18000db62  mov     edx, 3
0x18000db67  lea     r8d, [rdx+0Dh]
0x18000db6b  mov     rax, [rax+30h]
0x18000db6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db74  test    eax, eax
0x18000db76  js      loc_18000DCA6
0x18000db7c  mov     eax, dword ptr [rbp+57h+var_80]
0x18000db7f  mov     dword ptr [rbp+57h+var_98], eax
0x18000db82  mov     eax, dword ptr [rbp+57h+var_80+4]
0x18000db85  mov     dword ptr [rbp+57h+var_98+4], eax
0x18000db88  mov     eax, dword ptr [rbp+57h+var_80+0Ch]
0x18000db8b  mov     [rbp+57h+var_88], eax
0x18000db8e  mov     eax, dword ptr [rbp+57h+var_80+8]
0x18000db91  mov     dword ptr [rbp+57h+var_98+8], eax
0x18000db94  mov     [rsp+110h+var_D8], 0
0x18000db9d  mov     rcx, [rsp+110h+var_E0]
0x18000dba2  mov     rax, [rcx]
0x18000dba5  mov     edx, 1
0x18000dbaa  mov     rax, [rax+28h]
0x18000dbae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbb3  test    al, al
0x18000dbb5  jz      loc_18000DCA4
0x18000dbbb  mov     rcx, [rsp+110h+var_E0]
0x18000dbc0  mov     rax, [rcx]
0x18000dbc3  lea     r9, [rsp+110h+var_D8]
0x18000dbc8  mov     edx, 1
0x18000dbcd  lea     r8d, [rdx+7]
0x18000dbd1  mov     rax, [rax+30h]
0x18000dbd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbda  test    eax, eax
0x18000dbdc  js      loc_18000DCA4
0x18000dbe2  mov     eax, dword ptr [rbp+57h+var_98]
0x18000dbe5  mov     dword ptr [rbp+57h+var_70], eax
0x18000dbe8  mov     eax, dword ptr [rbp+57h+var_98+4]
0x18000dbeb  mov     dword ptr [rbp+57h+var_70+4], eax
0x18000dbee  mov     eax, dword ptr [rbp+57h+var_98+8]
0x18000dbf1  mov     dword ptr [rbp+57h+var_70+8], eax
0x18000dbf4  mov     eax, dword ptr [rbp+57h+var_98+0Ch]
0x18000dbf7  mov     dword ptr [rbp+57h+var_70+0Ch], eax
0x18000dbfa  mov     eax, [rbp+57h+var_88]
0x18000dbfd  mov     dword ptr [rbp+57h+var_60], eax
0x18000dc00  xor     eax, eax
0x18000dc02  mov     dword ptr [rbp+57h+var_60+4], eax
0x18000dc05  mov     rax, [rsp+110h+var_D8]
0x18000dc0a  mov     qword ptr [rbp+57h+var_60+8], rax
0x18000dc0e  mov     rcx, r13
0x18000dc11  lea     rdx, [rbp+57h+var_98]
0x18000dc15  mov     r8d, [rcx]
0x18000dc18  cmp     r8d, [rdx]
0x18000dc1b  jnz     short loc_18000DC25
0x18000dc1d  mov     eax, [rdx+4]
0x18000dc20  cmp     [rcx+4], eax
0x18000dc23  jz      short loc_18000DC3B
0x18000dc25  add     rdx, 14h
0x18000dc29  lea     rax, [rbp+57h+var_84]
0x18000dc2d  cmp     rdx, rax
0x18000dc30  jnz     short loc_18000DC18
0x18000dc32  add     rcx, 14h
0x18000dc36  cmp     rcx, r15
0x18000dc39  jnz     short loc_18000DC11
0x18000dc3b  cmp     rcx, r15
0x18000dc3e  jz      short loc_18000DCA2
0x18000dc40  mov     rdx, [rbx+8]
0x18000dc44  mov     rcx, [rbx]
0x18000dc47  jmp     short loc_18000DC6F
0x18000dc49  lea     r8, [rbp+57h+var_70]
0x18000dc4d  mov     r9d, [rcx]
0x18000dc50  cmp     r9d, [r8]
0x18000dc53  jnz     short loc_18000DC5E
0x18000dc55  mov     eax, [r8+4]
0x18000dc59  cmp     [rcx+4], eax
0x18000dc5c  jz      short loc_18000DC74
0x18000dc5e  add     r8, 20h ; ' '
0x18000dc62  lea     rax, [rbp+57h+var_50]
0x18000dc66  cmp     r8, rax
0x18000dc69  jnz     short loc_18000DC50
0x18000dc6b  add     rcx, 20h ; ' '
0x18000dc6f  cmp     rcx, rdx
0x18000dc72  jnz     short loc_18000DC49
0x18000dc74  cmp     rcx, rdx
0x18000dc77  jnz     short loc_18000DCA2
0x18000dc79  cmp     rdx, [rbx+10h]
0x18000dc7d  jz      short loc_18000DC95
0x18000dc7f  movups  xmm0, [rbp+57h+var_70]
0x18000dc83  movups  xmmword ptr [rdx], xmm0
0x18000dc86  movups  xmm1, [rbp+57h+var_60]
0x18000dc8a  movups  xmmword ptr [rdx+10h], xmm1
0x18000dc8e  add     qword ptr [rbx+8], 20h ; ' '
0x18000dc93  jmp     short loc_18000DCA2
0x18000dc95  lea     r8, [rbp+57h+var_70]
0x18000dc99  mov     rcx, rbx
0x18000dc9c  call    ??$_Emplace_reallocate@AEBUFoundNpu@npu_detection@udk@@@?$vector@UFoundNpu@npu_detection@udk@@V?$allocator@UFoundNpu@npu_detection@udk@@@std@@@std@@AEAAPEAUFoundNpu@npu_detection@udk@@QEAU234@AEBU234@@Z; std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(udk::npu_detection::FoundNpu * const,udk::npu_detection::FoundNpu const &)
0x18000dca1  nop
0x18000dca2  jmp     short loc_18000DCA6
0x18000dca4  jmp     short $+2
0x18000dca6  mov     rcx, [rsp+110h+var_E0]
0x18000dcab  test    rcx, rcx
0x18000dcae  jz      short loc_18000DCBD
0x18000dcb0  mov     rax, [rcx]
0x18000dcb3  mov     rax, [rax+10h]
0x18000dcb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcbc  nop
0x18000dcbd  inc     esi
0x18000dcbf  cmp     esi, r14d
0x18000dcc2  jb      loc_18000DA91
0x18000dcc8  xor     esi, esi
0x18000dcca  mov     rcx, [rbp+57h+var_D0]
0x18000dcce  test    rcx, rcx
0x18000dcd1  jz      short loc_18000DCE0
0x18000dcd3  mov     rax, [rcx]
0x18000dcd6  mov     rax, [rax+10h]
0x18000dcda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcdf  nop
0x18000dce0  add     rdi, 8
0x18000dce4  cmp     rdi, r12
0x18000dce7  jnz     loc_18000DA33
0x18000dced  mov     rcx, [rbp+57h+var_A8]
0x18000dcf1  test    rcx, rcx
0x18000dcf4  jz      short loc_18000DD03
0x18000dcf6  mov     rdx, [rcx]
0x18000dcf9  mov     rax, [rdx+10h]
0x18000dcfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd02  nop
0x18000dd03  lea     rcx, [rbp+57h+var_C8]
0x18000dd07  call    ??1?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID const *>::~vector<_GUID const *>(void)
0x18000dd0c  mov     rax, rbx
0x18000dd0f  mov     rcx, [rbp+57h+var_50]
0x18000dd13  xor     rcx, rsp; StackCookie
0x18000dd16  call    __security_check_cookie
0x18000dd1b  add     rsp, 0D8h
0x18000dd22  pop     r15
0x18000dd24  pop     r14
0x18000dd26  pop     r13
0x18000dd28  pop     r12
0x18000dd2a  pop     rdi
0x18000dd2b  pop     rsi
0x18000dd2c  pop     rbx
0x18000dd2d  pop     rbp
0x18000dd2e  retn
0x18000dd2f  mov     r9d, eax; char *
0x18000dd32  lea     r8, aOnecoreInterna_3; "OneCore\\Internal\\Shell\\inc\\npu_dete"...
0x18000dd39  mov     edx, 17Dh; void *
0x18000dd3e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000dd44  mov     ecx, 80070057h
0x18000dd49  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000dd4e  mov     r9d, eax; char *
0x18000dd51  mov     rcx, [rbp+5Fh]; this
0x18000dd55  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
