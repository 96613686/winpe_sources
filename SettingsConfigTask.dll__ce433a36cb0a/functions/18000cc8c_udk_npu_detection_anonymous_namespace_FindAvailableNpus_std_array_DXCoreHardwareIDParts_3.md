# udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___

- ea: `0x18000cc8c`
- end: `0x18000d06b`
- name: `udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___`
- size: `991`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013a2c`

## callees

- `0x1800021d0`
- `0x18000cc8c`
- `0x18000e0b8`
- `0x18000e0f8`
- `0x180011cb8`
- `0x180012570`
- `0x18001bf78`
- `0x18001c9e4`
- `0x18001f9bc`
- `0x180024010`

## import_xrefs

- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x18000cd55`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x18000cd55`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___(
        _QWORD *a1,
        __int64 a2,
        _DWORD *a3)
{
  __int64 v5; // r8
  _DWORD *v6; // r13
  int v7; // eax
  _QWORD *v8; // rdi
  _QWORD *v9; // r12
  __int64 v10; // rax
  unsigned int v11; // r15d
  unsigned int v12; // esi
  __int64 v13; // rax
  _DWORD *v14; // rdx
  __int128 *i; // rcx
  _OWORD *v16; // r9
  _DWORD *j; // rdx
  __int64 *k; // rcx
  int v20; // [rsp+20h] [rbp-99h]
  __int64 v21; // [rsp+30h] [rbp-89h] BYREF
  __int64 *v22; // [rsp+38h] [rbp-81h] BYREF
  __int64 *v23; // [rsp+40h] [rbp-79h] BYREF
  int v24; // [rsp+48h] [rbp-71h]
  __int64 *v25; // [rsp+50h] [rbp-69h] BYREF
  void *v26[4]; // [rsp+58h] [rbp-61h] BYREF
  __int128 v27; // [rsp+78h] [rbp-41h] BYREF
  unsigned int v28; // [rsp+88h] [rbp-31h]
  char v29; // [rsp+8Ch] [rbp-2Dh] BYREF
  __int128 v30; // [rsp+90h] [rbp-29h] BYREF
  __int128 v31; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v32; // [rsp+B0h] [rbp-9h]
  __int64 v33; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v26[3] = a1;
  std::vector<_GUID const *>::vector<_GUID const *>(a1);
  v24 = 1;
  v6 = (_DWORD *)(v5 + 60);
  std::vector<_GUID const *>::vector<_GUID const *>(v26);
  v22 = DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU;
  std::vector<_GUID const *>::push_back(v26, &v22);
  v22 = DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML;
  std::vector<_GUID const *>::push_back(v26, &v22);
  v22 = DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE;
  std::vector<_GUID const *>::push_back(v26, &v22);
  v25 = 0;
  v7 = DXCoreCreateAdapterFactory(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, &v25);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\npu_detection.h",
      (const char *)(unsigned int)v7,
      v20);
  v8 = v26[0];
  v9 = v26[1];
  while ( v8 != v9 )
  {
    v23 = 0;
    v10 = *v25;
    v23 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64, _QWORD, GUID *, __int64 **))(v10 + 24))(
           v25,
           1,
           *v8,
           &GUID_526c7776_40e9_459b_b711_f32ad76dfc28,
           &v23) >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64 *))(*v23 + 32))(v23);
      if ( v11 )
      {
        v12 = 0;
        while ( 1 )
        {
          v21 = 0;
          v13 = *v23;
          v21 = 0;
          if ( (*(int (__fastcall **)(__int64 *, _QWORD, GUID *, __int64 *))(v13 + 24))(
                 v23,
                 v12,
                 &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e,
                 &v21) >= 0 )
          {
            if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 40LL))(v21, 11) )
            {
              v27 = 0;
              v28 = 0;
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 40LL))(v21, 14)
                && (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v21 + 48LL))(
                     v21,
                     14,
                     20,
                     &v27) >= 0 )
              {
                goto LABEL_14;
              }
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 40LL))(v21, 3) )
              {
                v30 = 0;
                if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v21 + 48LL))(
                       v21,
                       3,
                       16,
                       &v30) >= 0 )
                  break;
              }
            }
          }
LABEL_35:
          wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v21);
          if ( ++v12 >= v11 )
            goto LABEL_36;
        }
        *(_QWORD *)&v27 = v30;
        v28 = HIDWORD(v30);
        DWORD2(v27) = DWORD2(v30);
LABEL_14:
        v22 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 40LL))(v21, 1)
          && (*(int (__fastcall **)(__int64, __int64, __int64, __int64 **))(*(_QWORD *)v21 + 48LL))(v21, 1, 8, &v22) >= 0 )
        {
          v31 = v27;
          *(_QWORD *)&v32 = v28;
          *((_QWORD *)&v32 + 1) = v22;
          v14 = a3;
LABEL_17:
          if ( v14 != v6 )
          {
            for ( i = &v27; ; i = (__int128 *)((char *)i + 20) )
            {
              if ( i == (__int128 *)&v29 )
              {
                v14 += 5;
                goto LABEL_17;
              }
              if ( *v14 == *(_DWORD *)i && v14[1] == *((_DWORD *)i + 1) )
                break;
            }
            v16 = (_OWORD *)a1[1];
            for ( j = (_DWORD *)*a1; j != (_DWORD *)v16; j += 8 )
            {
              for ( k = (__int64 *)&v31; k != &v33; k += 4 )
              {
                if ( *j == *(_DWORD *)k && j[1] == *((_DWORD *)k + 1) )
                  goto LABEL_35;
              }
            }
            if ( v16 == (_OWORD *)a1[2] )
            {
              std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(
                a1,
                a1[1],
                &v31);
            }
            else
            {
              *v16 = v31;
              v16[1] = v32;
              a1[1] += 32LL;
            }
          }
        }
        goto LABEL_35;
      }
    }
LABEL_36:
    wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>((__int64 *)&v23);
    ++v8;
  }
  wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>((__int64 *)&v25);
  if ( v26[0] )
    std::_Deallocate<16>(v26[0], (struct std::nothrow_t *)(((char *)v26[2] - (char *)v26[0]) & 0xFFFFFFFFFFFFFFF8uLL));
  return a1;
}

```

## disassembly

```asm
0x18000cc8c  push    rbp
0x18000cc8e  push    rbx
0x18000cc8f  push    rsi
0x18000cc90  push    rdi
0x18000cc91  push    r12
0x18000cc93  push    r13
0x18000cc95  push    r14
0x18000cc97  push    r15
0x18000cc99  lea     rbp, [rsp-1Fh]
0x18000cc9e  sub     rsp, 0D8h
0x18000cca5  mov     rax, cs:__security_cookie
0x18000ccac  xor     rax, rsp
0x18000ccaf  mov     [rbp+57h+var_50], rax
0x18000ccb3  mov     r14, r8
0x18000ccb6  mov     rbx, rcx
0x18000ccb9  mov     [rbp+57h+var_A0], rcx
0x18000ccbd  mov     [rbp+57h+var_C8], 0
0x18000ccc4  call    ??0?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID const *>::vector<_GUID const *>(void)
0x18000ccc9  mov     [rbp+57h+var_C8], 1
0x18000ccd0  lea     r13, [r8+3Ch]
0x18000ccd4  cmp     r8, r13
0x18000ccd7  jnz     short loc_18000CCE9
0x18000ccd9  mov     rcx, [rbp+5Fh]; this
0x18000ccdd  mov     r9d, 80070057h; char *
0x18000cce3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cce9  lea     rcx, [rbp+57h+var_B8]
0x18000cced  call    ??0?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID const *>::vector<_GUID const *>(void)
0x18000ccf2  nop
0x18000ccf3  lea     rax, DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU
0x18000ccfa  mov     [rsp+110h+var_D8], rax
0x18000ccff  lea     rdx, [rsp+110h+var_D8]
0x18000cd04  lea     rcx, [rbp+57h+var_B8]
0x18000cd08  call    ?push_back@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAAX$$QEAPEBU_GUID@@@Z; std::vector<_GUID const *>::push_back(_GUID const * &&)
0x18000cd0d  lea     rax, DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML
0x18000cd14  mov     [rsp+110h+var_D8], rax
0x18000cd19  lea     rdx, [rsp+110h+var_D8]
0x18000cd1e  lea     rcx, [rbp+57h+var_B8]
0x18000cd22  call    ?push_back@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAAX$$QEAPEBU_GUID@@@Z; std::vector<_GUID const *>::push_back(_GUID const * &&)
0x18000cd27  lea     rax, DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE
0x18000cd2e  mov     [rsp+110h+var_D8], rax
0x18000cd33  lea     rdx, [rsp+110h+var_D8]
0x18000cd38  lea     rcx, [rbp+57h+var_B8]
0x18000cd3c  call    ?push_back@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAAX$$QEAPEBU_GUID@@@Z; std::vector<_GUID const *>::push_back(_GUID const * &&)
0x18000cd41  nop
0x18000cd42  mov     [rbp+57h+var_C0], 0
0x18000cd4a  lea     rdx, [rbp+57h+var_C0]
0x18000cd4e  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x18000cd55  call    cs:__imp_DXCoreCreateAdapterFactory
0x18000cd5b  mov     rcx, [rbp+5Fh]; this
0x18000cd5f  test    eax, eax
0x18000cd61  jns     short loc_18000CD78
0x18000cd63  mov     r9d, eax; char *
0x18000cd66  lea     r8, aOnecoreInterna_3; "OneCore\\Internal\\Shell\\inc\\npu_dete"...
0x18000cd6d  mov     edx, 17Dh; void *
0x18000cd72  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000cd78  mov     rdi, [rbp+57h+var_B8]
0x18000cd7c  mov     r12, [rbp+57h+var_B0]
0x18000cd80  jmp     loc_18000D01B
0x18000cd85  mov     [rbp+57h+var_D0], 0
0x18000cd8d  mov     rcx, [rbp+57h+var_C0]
0x18000cd91  mov     rax, [rcx]
0x18000cd94  mov     [rbp+57h+var_D0], 0
0x18000cd9c  lea     rdx, [rbp+57h+var_D0]
0x18000cda0  mov     qword ptr [rsp+110h+var_F0], rdx
0x18000cda5  lea     r9, _GUID_526c7776_40e9_459b_b711_f32ad76dfc28
0x18000cdac  mov     r8, [rdi]
0x18000cdaf  mov     edx, 1
0x18000cdb4  mov     rax, [rax+18h]
0x18000cdb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdbd  test    eax, eax
0x18000cdbf  js      loc_18000D00E
0x18000cdc5  mov     rcx, [rbp+57h+var_D0]
0x18000cdc9  mov     rax, [rcx]
0x18000cdcc  mov     rax, [rax+20h]
0x18000cdd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdd5  mov     r15d, eax
0x18000cdd8  test    eax, eax
0x18000cdda  jz      loc_18000D00E
0x18000cde0  xor     esi, esi
0x18000cde2  test    eax, eax
0x18000cde4  jz      loc_18000D00E
0x18000cdea  mov     [rsp+110h+var_E0], 0
0x18000cdf3  mov     rcx, [rbp+57h+var_D0]
0x18000cdf7  mov     rax, [rcx]
0x18000cdfa  mov     [rsp+110h+var_E0], 0
0x18000ce03  lea     r9, [rsp+110h+var_E0]
0x18000ce08  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x18000ce0f  mov     edx, esi
0x18000ce11  mov     rax, [rax+18h]
0x18000ce15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce1a  test    eax, eax
0x18000ce1c  js      loc_18000CFF9
0x18000ce22  mov     rcx, [rsp+110h+var_E0]
0x18000ce27  mov     rax, [rcx]
0x18000ce2a  mov     edx, 0Bh
0x18000ce2f  mov     rax, [rax+28h]
0x18000ce33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce38  test    al, al
0x18000ce3a  jz      loc_18000CFF9
0x18000ce40  xorps   xmm0, xmm0
0x18000ce43  xor     eax, eax
0x18000ce45  movups  [rbp+57h+var_98], xmm0
0x18000ce49  mov     [rbp+57h+var_88], eax
0x18000ce4c  mov     rcx, [rsp+110h+var_E0]
0x18000ce51  mov     rax, [rcx]
0x18000ce54  mov     edx, 0Eh
0x18000ce59  mov     rax, [rax+28h]
0x18000ce5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce62  test    al, al
0x18000ce64  jz      short loc_18000CE88
0x18000ce66  mov     rcx, [rsp+110h+var_E0]
0x18000ce6b  mov     rax, [rcx]
0x18000ce6e  lea     r9, [rbp+57h+var_98]
0x18000ce72  mov     edx, 0Eh
0x18000ce77  lea     r8d, [rdx+6]
0x18000ce7b  mov     rax, [rax+30h]
0x18000ce7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce84  test    eax, eax
0x18000ce86  jns     short loc_18000CEEB
0x18000ce88  mov     rcx, [rsp+110h+var_E0]
0x18000ce8d  mov     rax, [rcx]
0x18000ce90  mov     edx, 3
0x18000ce95  mov     rax, [rax+28h]
0x18000ce99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce9e  test    al, al
0x18000cea0  jz      loc_18000CFF9
0x18000cea6  xorps   xmm0, xmm0
0x18000cea9  movups  [rbp+57h+var_80], xmm0
0x18000cead  mov     rcx, [rsp+110h+var_E0]
0x18000ceb2  mov     rax, [rcx]
0x18000ceb5  lea     r9, [rbp+57h+var_80]
0x18000ceb9  mov     edx, 3
0x18000cebe  lea     r8d, [rdx+0Dh]
0x18000cec2  mov     rax, [rax+30h]
0x18000cec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cecb  test    eax, eax
0x18000cecd  js      loc_18000CFF9
0x18000ced3  mov     eax, dword ptr [rbp+57h+var_80]
0x18000ced6  mov     dword ptr [rbp+57h+var_98], eax
0x18000ced9  mov     eax, dword ptr [rbp+57h+var_80+4]
0x18000cedc  mov     dword ptr [rbp+57h+var_98+4], eax
0x18000cedf  mov     eax, dword ptr [rbp+57h+var_80+0Ch]
0x18000cee2  mov     [rbp+57h+var_88], eax
0x18000cee5  mov     eax, dword ptr [rbp+57h+var_80+8]
0x18000cee8  mov     dword ptr [rbp+57h+var_98+8], eax
0x18000ceeb  mov     [rsp+110h+var_D8], 0
0x18000cef4  mov     rcx, [rsp+110h+var_E0]
0x18000cef9  mov     rax, [rcx]
0x18000cefc  mov     edx, 1
0x18000cf01  mov     rax, [rax+28h]
0x18000cf05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf0a  test    al, al
0x18000cf0c  jz      loc_18000CFF9
0x18000cf12  mov     rcx, [rsp+110h+var_E0]
0x18000cf17  mov     rax, [rcx]
0x18000cf1a  lea     r9, [rsp+110h+var_D8]
0x18000cf1f  mov     edx, 1
0x18000cf24  lea     r8d, [rdx+7]
0x18000cf28  mov     rax, [rax+30h]
0x18000cf2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf31  test    eax, eax
0x18000cf33  js      loc_18000CFF9
0x18000cf39  mov     eax, dword ptr [rbp+57h+var_98]
0x18000cf3c  mov     dword ptr [rbp+57h+var_70], eax
0x18000cf3f  mov     eax, dword ptr [rbp+57h+var_98+4]
0x18000cf42  mov     dword ptr [rbp+57h+var_70+4], eax
0x18000cf45  mov     eax, dword ptr [rbp+57h+var_98+8]
0x18000cf48  mov     dword ptr [rbp+57h+var_70+8], eax
0x18000cf4b  mov     eax, dword ptr [rbp+57h+var_98+0Ch]
0x18000cf4e  mov     dword ptr [rbp+57h+var_70+0Ch], eax
0x18000cf51  mov     eax, [rbp+57h+var_88]
0x18000cf54  mov     dword ptr [rbp+57h+var_60], eax
0x18000cf57  xor     eax, eax
0x18000cf59  mov     dword ptr [rbp+57h+var_60+4], eax
0x18000cf5c  mov     rax, [rsp+110h+var_D8]
0x18000cf61  mov     qword ptr [rbp+57h+var_60+8], rax
0x18000cf65  mov     rdx, r14
0x18000cf68  cmp     rdx, r13
0x18000cf6b  jz      loc_18000CFF9
0x18000cf71  lea     rcx, [rbp+57h+var_98]
0x18000cf75  lea     rax, [rbp+57h+var_84]
0x18000cf79  cmp     rcx, rax
0x18000cf7c  jz      short loc_18000CF92
0x18000cf7e  mov     eax, [rcx]
0x18000cf80  cmp     [rdx], eax
0x18000cf82  jnz     short loc_18000CF8C
0x18000cf84  mov     eax, [rcx+4]
0x18000cf87  cmp     [rdx+4], eax
0x18000cf8a  jz      short loc_18000CF98
0x18000cf8c  add     rcx, 14h
0x18000cf90  jmp     short loc_18000CF75
0x18000cf92  add     rdx, 14h
0x18000cf96  jmp     short loc_18000CF68
0x18000cf98  mov     r9, [rbx+8]
0x18000cf9c  mov     rdx, [rbx]
0x18000cf9f  cmp     rdx, r9
0x18000cfa2  jz      short loc_18000CFCB
0x18000cfa4  lea     rcx, [rbp+57h+var_70]
0x18000cfa8  lea     rax, [rbp+57h+var_50]
0x18000cfac  cmp     rcx, rax
0x18000cfaf  jz      short loc_18000CFC5
0x18000cfb1  mov     eax, [rcx]
0x18000cfb3  cmp     [rdx], eax
0x18000cfb5  jnz     short loc_18000CFBF
0x18000cfb7  mov     eax, [rcx+4]
0x18000cfba  cmp     [rdx+4], eax
0x18000cfbd  jz      short loc_18000CFF9
0x18000cfbf  add     rcx, 20h ; ' '
0x18000cfc3  jmp     short loc_18000CFA8
0x18000cfc5  add     rdx, 20h ; ' '
0x18000cfc9  jmp     short loc_18000CF9F
0x18000cfcb  cmp     r9, [rbx+10h]
0x18000cfcf  jz      short loc_18000CFE9
0x18000cfd1  movups  xmm0, [rbp+57h+var_70]
0x18000cfd5  movups  xmmword ptr [r9], xmm0
0x18000cfd9  movups  xmm1, [rbp+57h+var_60]
0x18000cfdd  movups  xmmword ptr [r9+10h], xmm1
0x18000cfe2  add     qword ptr [rbx+8], 20h ; ' '
0x18000cfe7  jmp     short loc_18000CFF9
0x18000cfe9  lea     r8, [rbp+57h+var_70]
0x18000cfed  mov     rdx, r9
0x18000cff0  mov     rcx, rbx
0x18000cff3  call    ??$_Emplace_reallocate@AEBUFoundNpu@npu_detection@udk@@@?$vector@UFoundNpu@npu_detection@udk@@V?$allocator@UFoundNpu@npu_detection@udk@@@std@@@std@@AEAAPEAUFoundNpu@npu_detection@udk@@QEAU234@AEBU234@@Z; std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(udk::npu_detection::FoundNpu * const,udk::npu_detection::FoundNpu const &)
0x18000cff8  nop
0x18000cff9  lea     rcx, [rsp+110h+var_E0]
0x18000cffe  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x18000d003  inc     esi
0x18000d005  cmp     esi, r15d
0x18000d008  jb      loc_18000CDEA
0x18000d00e  lea     rcx, [rbp+57h+var_D0]
0x18000d012  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x18000d017  add     rdi, 8
0x18000d01b  cmp     rdi, r12
0x18000d01e  jnz     loc_18000CD85
0x18000d024  lea     rcx, [rbp+57h+var_C0]
0x18000d028  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x18000d02d  nop
0x18000d02e  mov     rcx, [rbp+57h+var_B8]
0x18000d032  test    rcx, rcx
0x18000d035  jz      short loc_18000D047
0x18000d037  mov     rdx, [rbp+57h+var_A8]
0x18000d03b  sub     rdx, rcx
0x18000d03e  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000d042  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000d047  mov     rax, rbx
0x18000d04a  mov     rcx, [rbp+57h+var_50]
0x18000d04e  xor     rcx, rsp; StackCookie
0x18000d051  call    __security_check_cookie
0x18000d056  add     rsp, 0D8h
0x18000d05d  pop     r15
0x18000d05f  pop     r14
0x18000d061  pop     r13
0x18000d063  pop     r12
0x18000d065  pop     rdi
0x18000d066  pop     rsi
0x18000d067  pop     rbx
0x18000d068  pop     rbp
0x18000d069  retn
```
