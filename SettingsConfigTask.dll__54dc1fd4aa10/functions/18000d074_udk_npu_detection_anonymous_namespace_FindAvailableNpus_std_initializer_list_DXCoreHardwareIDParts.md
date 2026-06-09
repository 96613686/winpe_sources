# udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::initializer_list_DXCoreHardwareIDParts___

- ea: `0x18000d074`
- end: `0x18000d42b`
- name: `udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::initializer_list_DXCoreHardwareIDParts___`
- size: `951`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013a2c`

## callees

- `0x1800021d0`
- `0x18000d074`
- `0x18000e0b8`
- `0x18000e0f8`
- `0x180011cb8`
- `0x180012570`
- `0x18001c9e4`
- `0x18001f9bc`
- `0x180024010`

## import_xrefs

- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x18000d0fd`
- `ext-ms-win-dxcore-l1-1-0!DXCoreCreateAdapterFactory` at `0x18000d0fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::initializer_list_DXCoreHardwareIDParts___(
        __int64 a1,
        __int64 a2,
        _DWORD **a3)
{
  __int64 *v5; // r8
  __int64 v6; // r13
  int v7; // eax
  _QWORD *v8; // rdi
  _QWORD *v9; // r12
  __int64 v10; // rax
  unsigned int v11; // r14d
  unsigned int v12; // esi
  __int64 v13; // r12
  __int64 v14; // rax
  _DWORD *k; // rdx
  __int128 *m; // rcx
  _OWORD *v17; // r9
  _DWORD *i; // rdx
  __int64 *j; // rcx
  int v21; // [rsp+20h] [rbp-A9h]
  __int64 v22; // [rsp+30h] [rbp-99h] BYREF
  __int64 *v23; // [rsp+38h] [rbp-91h] BYREF
  __int64 *v24; // [rsp+40h] [rbp-89h] BYREF
  int v25; // [rsp+48h] [rbp-81h]
  __int64 *v26; // [rsp+50h] [rbp-79h] BYREF
  __int64 v27; // [rsp+58h] [rbp-71h]
  _QWORD *v28; // [rsp+60h] [rbp-69h]
  _QWORD *v29; // [rsp+68h] [rbp-61h] BYREF
  _QWORD *v30; // [rsp+70h] [rbp-59h]
  __int64 v31; // [rsp+78h] [rbp-51h]
  __int64 v32; // [rsp+80h] [rbp-49h]
  __int128 v33; // [rsp+88h] [rbp-41h] BYREF
  unsigned int v34; // [rsp+98h] [rbp-31h]
  char v35; // [rsp+9Ch] [rbp-2Dh] BYREF
  __int128 v36; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v37; // [rsp+B0h] [rbp-19h] BYREF
  __int128 v38; // [rsp+C0h] [rbp-9h]
  __int64 v39; // [rsp+D0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v32 = a1;
  std::vector<_GUID const *>::vector<_GUID const *>(a1);
  v25 = 1;
  v6 = *v5;
  v27 = v5[1];
  std::vector<_GUID const *>::vector<_GUID const *>(&v29);
  v24 = DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU;
  std::vector<_GUID const *>::push_back(&v29, &v24);
  v26 = 0;
  v7 = DXCoreCreateAdapterFactory(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, &v26);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\npu_detection.h",
      (const char *)(unsigned int)v7,
      v21);
  v8 = v29;
  v9 = v30;
  v28 = v30;
  while ( v8 != v9 )
  {
    v23 = 0;
    v10 = *v26;
    v23 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64, _QWORD, GUID *, __int64 **))(v10 + 24))(
           v26,
           1,
           *v8,
           &GUID_526c7776_40e9_459b_b711_f32ad76dfc28,
           &v23) >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64 *))(*v23 + 32))(v23);
      if ( v11 )
      {
        v12 = 0;
        v13 = v27;
        while ( 1 )
        {
          v22 = 0;
          v14 = *v23;
          v22 = 0;
          if ( (*(int (__fastcall **)(__int64 *, _QWORD, GUID *, __int64 *))(v14 + 24))(
                 v23,
                 v12,
                 &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e,
                 &v22) >= 0 )
          {
            if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, 11) )
            {
              v33 = 0;
              v34 = 0;
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, 14)
                && (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v22 + 48LL))(
                     v22,
                     14,
                     20,
                     &v33) >= 0 )
              {
                goto LABEL_14;
              }
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, 3) )
              {
                v36 = 0;
                if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v22 + 48LL))(
                       v22,
                       3,
                       16,
                       &v36) >= 0 )
                  break;
              }
            }
          }
LABEL_36:
          wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v22);
          if ( ++v12 >= v11 )
          {
            v9 = v28;
            goto LABEL_38;
          }
        }
        *(_QWORD *)&v33 = v36;
        v34 = HIDWORD(v36);
        DWORD2(v33) = DWORD2(v36);
LABEL_14:
        v24 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 40LL))(v22, 1)
          && (*(int (__fastcall **)(__int64, __int64, __int64, __int64 **))(*(_QWORD *)v22 + 48LL))(v22, 1, 8, &v24) >= 0 )
        {
          v37 = v33;
          *(_QWORD *)&v38 = v34;
          *((_QWORD *)&v38 + 1) = v24;
          if ( v6 == v13 )
          {
LABEL_25:
            v17 = *(_OWORD **)(a1 + 8);
            for ( i = *(_DWORD **)a1; i != (_DWORD *)v17; i += 8 )
            {
              for ( j = (__int64 *)&v37; j != &v39; j += 4 )
              {
                if ( *i == *(_DWORD *)j && i[1] == *((_DWORD *)j + 1) )
                  goto LABEL_36;
              }
            }
            if ( v17 == *(_OWORD **)(a1 + 16) )
            {
              std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(
                a1,
                *(_QWORD *)(a1 + 8),
                &v37);
            }
            else
            {
              *v17 = v37;
              v17[1] = v38;
              *(_QWORD *)(a1 + 8) += 32LL;
            }
          }
          else
          {
            for ( k = *a3; k != a3[1]; k += 5 )
            {
              for ( m = &v33; m != (__int128 *)&v35; m = (__int128 *)((char *)m + 20) )
              {
                if ( *k == *(_DWORD *)m && k[1] == *((_DWORD *)m + 1) )
                  goto LABEL_25;
              }
            }
          }
        }
        goto LABEL_36;
      }
    }
LABEL_38:
    wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v23);
    ++v8;
  }
  wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v26);
  if ( v29 )
    std::_Deallocate<16>(v29, (v31 - (_QWORD)v29) & 0xFFFFFFFFFFFFFFF8uLL);
  return a1;
}

```

## disassembly

```asm
0x18000d074  push    rbp
0x18000d076  push    rbx
0x18000d077  push    rsi
0x18000d078  push    rdi
0x18000d079  push    r12
0x18000d07b  push    r13
0x18000d07d  push    r14
0x18000d07f  push    r15
0x18000d081  lea     rbp, [rsp-1Fh]
0x18000d086  sub     rsp, 0E8h
0x18000d08d  mov     rax, cs:__security_cookie
0x18000d094  xor     rax, rsp
0x18000d097  mov     [rbp+57h+var_50], rax
0x18000d09b  mov     r15, r8
0x18000d09e  mov     rbx, rcx
0x18000d0a1  mov     [rbp+57h+var_A0], rcx
0x18000d0a5  mov     [rsp+120h+var_D8], 0
0x18000d0ad  call    ??0?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID const *>::vector<_GUID const *>(void)
0x18000d0b2  mov     [rsp+120h+var_D8], 1
0x18000d0ba  mov     r13, [r8]
0x18000d0bd  mov     rax, [r8+8]
0x18000d0c1  mov     [rbp+57h+var_C8], rax
0x18000d0c5  lea     rcx, [rbp+57h+var_B8]
0x18000d0c9  call    ??0?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID const *>::vector<_GUID const *>(void)
0x18000d0ce  nop
0x18000d0cf  lea     rax, DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU
0x18000d0d6  mov     [rsp+120h+var_E0], rax
0x18000d0db  lea     rdx, [rsp+120h+var_E0]
0x18000d0e0  lea     rcx, [rbp+57h+var_B8]
0x18000d0e4  call    ?push_back@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAAX$$QEAPEBU_GUID@@@Z; std::vector<_GUID const *>::push_back(_GUID const * &&)
0x18000d0e9  nop
0x18000d0ea  mov     [rbp+57h+var_D0], 0
0x18000d0f2  lea     rdx, [rbp+57h+var_D0]
0x18000d0f6  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x18000d0fd  call    cs:__imp_DXCoreCreateAdapterFactory
0x18000d103  mov     rcx, [rbp+5Fh]; this
0x18000d107  test    eax, eax
0x18000d109  jns     short loc_18000D120
0x18000d10b  mov     r9d, eax; char *
0x18000d10e  lea     r8, aOnecoreInterna_3; "OneCore\\Internal\\Shell\\inc\\npu_dete"...
0x18000d115  mov     edx, 17Dh; void *
0x18000d11a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000d120  mov     rdi, [rbp+57h+var_B8]
0x18000d124  mov     r12, [rbp+57h+var_B0]
0x18000d128  mov     [rbp+57h+var_C0], r12
0x18000d12c  jmp     loc_18000D3DB
0x18000d131  mov     [rsp+120h+var_E8], 0
0x18000d13a  mov     rcx, [rbp+57h+var_D0]
0x18000d13e  mov     rax, [rcx]
0x18000d141  mov     [rsp+120h+var_E8], 0
0x18000d14a  lea     rdx, [rsp+120h+var_E8]
0x18000d14f  mov     qword ptr [rsp+120h+var_100], rdx
0x18000d154  lea     r9, _GUID_526c7776_40e9_459b_b711_f32ad76dfc28
0x18000d15b  mov     r8, [rdi]
0x18000d15e  mov     edx, 1
0x18000d163  mov     rax, [rax+18h]
0x18000d167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d16c  test    eax, eax
0x18000d16e  js      loc_18000D3CD
0x18000d174  mov     rcx, [rsp+120h+var_E8]
0x18000d179  mov     rax, [rcx]
0x18000d17c  mov     rax, [rax+20h]
0x18000d180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d185  mov     r14d, eax
0x18000d188  test    eax, eax
0x18000d18a  jz      loc_18000D3CD
0x18000d190  xor     esi, esi
0x18000d192  test    eax, eax
0x18000d194  jz      loc_18000D3CD
0x18000d19a  mov     r12, [rbp+57h+var_C8]
0x18000d19e  mov     [rsp+120h+var_F0], 0
0x18000d1a7  mov     rcx, [rsp+120h+var_E8]
0x18000d1ac  mov     rax, [rcx]
0x18000d1af  mov     [rsp+120h+var_F0], 0
0x18000d1b8  lea     r9, [rsp+120h+var_F0]
0x18000d1bd  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x18000d1c4  mov     edx, esi
0x18000d1c6  mov     rax, [rax+18h]
0x18000d1ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1cf  test    eax, eax
0x18000d1d1  js      loc_18000D3B4
0x18000d1d7  mov     rcx, [rsp+120h+var_F0]
0x18000d1dc  mov     rax, [rcx]
0x18000d1df  mov     edx, 0Bh
0x18000d1e4  mov     rax, [rax+28h]
0x18000d1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1ed  test    al, al
0x18000d1ef  jz      loc_18000D3B4
0x18000d1f5  xorps   xmm0, xmm0
0x18000d1f8  xor     eax, eax
0x18000d1fa  movups  [rbp+57h+var_98], xmm0
0x18000d1fe  mov     [rbp+57h+var_88], eax
0x18000d201  mov     rcx, [rsp+120h+var_F0]
0x18000d206  mov     rax, [rcx]
0x18000d209  mov     edx, 0Eh
0x18000d20e  mov     rax, [rax+28h]
0x18000d212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d217  test    al, al
0x18000d219  jz      short loc_18000D23D
0x18000d21b  mov     rcx, [rsp+120h+var_F0]
0x18000d220  mov     rax, [rcx]
0x18000d223  lea     r9, [rbp+57h+var_98]
0x18000d227  mov     edx, 0Eh
0x18000d22c  lea     r8d, [rdx+6]
0x18000d230  mov     rax, [rax+30h]
0x18000d234  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d239  test    eax, eax
0x18000d23b  jns     short loc_18000D2A0
0x18000d23d  mov     rcx, [rsp+120h+var_F0]
0x18000d242  mov     rax, [rcx]
0x18000d245  mov     edx, 3
0x18000d24a  mov     rax, [rax+28h]
0x18000d24e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d253  test    al, al
0x18000d255  jz      loc_18000D3B4
0x18000d25b  xorps   xmm0, xmm0
0x18000d25e  movups  [rbp+57h+var_80], xmm0
0x18000d262  mov     rcx, [rsp+120h+var_F0]
0x18000d267  mov     rax, [rcx]
0x18000d26a  lea     r9, [rbp+57h+var_80]
0x18000d26e  mov     edx, 3
0x18000d273  lea     r8d, [rdx+0Dh]
0x18000d277  mov     rax, [rax+30h]
0x18000d27b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d280  test    eax, eax
0x18000d282  js      loc_18000D3B4
0x18000d288  mov     eax, dword ptr [rbp+57h+var_80]
0x18000d28b  mov     dword ptr [rbp+57h+var_98], eax
0x18000d28e  mov     eax, dword ptr [rbp+57h+var_80+4]
0x18000d291  mov     dword ptr [rbp+57h+var_98+4], eax
0x18000d294  mov     eax, dword ptr [rbp+57h+var_80+0Ch]
0x18000d297  mov     [rbp+57h+var_88], eax
0x18000d29a  mov     eax, dword ptr [rbp+57h+var_80+8]
0x18000d29d  mov     dword ptr [rbp+57h+var_98+8], eax
0x18000d2a0  mov     [rsp+120h+var_E0], 0
0x18000d2a9  mov     rcx, [rsp+120h+var_F0]
0x18000d2ae  mov     rax, [rcx]
0x18000d2b1  mov     edx, 1
0x18000d2b6  mov     rax, [rax+28h]
0x18000d2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2bf  test    al, al
0x18000d2c1  jz      loc_18000D3B4
0x18000d2c7  mov     rcx, [rsp+120h+var_F0]
0x18000d2cc  mov     rax, [rcx]
0x18000d2cf  lea     r9, [rsp+120h+var_E0]
0x18000d2d4  mov     edx, 1
0x18000d2d9  lea     r8d, [rdx+7]
0x18000d2dd  mov     rax, [rax+30h]
0x18000d2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2e6  test    eax, eax
0x18000d2e8  js      loc_18000D3B4
0x18000d2ee  mov     eax, dword ptr [rbp+57h+var_98]
0x18000d2f1  mov     dword ptr [rbp+57h+var_70], eax
0x18000d2f4  mov     eax, dword ptr [rbp+57h+var_98+4]
0x18000d2f7  mov     dword ptr [rbp+57h+var_70+4], eax
0x18000d2fa  mov     eax, dword ptr [rbp+57h+var_98+8]
0x18000d2fd  mov     dword ptr [rbp+57h+var_70+8], eax
0x18000d300  mov     eax, dword ptr [rbp+57h+var_98+0Ch]
0x18000d303  mov     dword ptr [rbp+57h+var_70+0Ch], eax
0x18000d306  mov     eax, [rbp+57h+var_88]
0x18000d309  mov     dword ptr [rbp+57h+var_60], eax
0x18000d30c  xor     eax, eax
0x18000d30e  mov     dword ptr [rbp+57h+var_60+4], eax
0x18000d311  mov     rax, [rsp+120h+var_E0]
0x18000d316  mov     qword ptr [rbp+57h+var_60+8], rax
0x18000d31a  cmp     r13, r12
0x18000d31d  jz      short loc_18000D353
0x18000d31f  mov     rdx, [r15]
0x18000d322  cmp     rdx, [r15+8]
0x18000d326  jz      loc_18000D3B4
0x18000d32c  lea     rcx, [rbp+57h+var_98]
0x18000d330  lea     rax, [rbp+57h+var_84]
0x18000d334  cmp     rcx, rax
0x18000d337  jz      short loc_18000D34D
0x18000d339  mov     eax, [rcx]
0x18000d33b  cmp     [rdx], eax
0x18000d33d  jnz     short loc_18000D347
0x18000d33f  mov     eax, [rcx+4]
0x18000d342  cmp     [rdx+4], eax
0x18000d345  jz      short loc_18000D353
0x18000d347  add     rcx, 14h
0x18000d34b  jmp     short loc_18000D330
0x18000d34d  add     rdx, 14h
0x18000d351  jmp     short loc_18000D322
0x18000d353  mov     r9, [rbx+8]
0x18000d357  mov     rdx, [rbx]
0x18000d35a  cmp     rdx, r9
0x18000d35d  jz      short loc_18000D386
0x18000d35f  lea     rcx, [rbp+57h+var_70]
0x18000d363  lea     rax, [rbp+57h+var_50]
0x18000d367  cmp     rcx, rax
0x18000d36a  jz      short loc_18000D380
0x18000d36c  mov     eax, [rcx]
0x18000d36e  cmp     [rdx], eax
0x18000d370  jnz     short loc_18000D37A
0x18000d372  mov     eax, [rcx+4]
0x18000d375  cmp     [rdx+4], eax
0x18000d378  jz      short loc_18000D3B4
0x18000d37a  add     rcx, 20h ; ' '
0x18000d37e  jmp     short loc_18000D363
0x18000d380  add     rdx, 20h ; ' '
0x18000d384  jmp     short loc_18000D35A
0x18000d386  cmp     r9, [rbx+10h]
0x18000d38a  jz      short loc_18000D3A4
0x18000d38c  movups  xmm0, [rbp+57h+var_70]
0x18000d390  movups  xmmword ptr [r9], xmm0
0x18000d394  movups  xmm1, [rbp+57h+var_60]
0x18000d398  movups  xmmword ptr [r9+10h], xmm1
0x18000d39d  add     qword ptr [rbx+8], 20h ; ' '
0x18000d3a2  jmp     short loc_18000D3B4
0x18000d3a4  lea     r8, [rbp+57h+var_70]
0x18000d3a8  mov     rdx, r9
0x18000d3ab  mov     rcx, rbx
0x18000d3ae  call    ??$_Emplace_reallocate@AEBUFoundNpu@npu_detection@udk@@@?$vector@UFoundNpu@npu_detection@udk@@V?$allocator@UFoundNpu@npu_detection@udk@@@std@@@std@@AEAAPEAUFoundNpu@npu_detection@udk@@QEAU234@AEBU234@@Z; std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(udk::npu_detection::FoundNpu * const,udk::npu_detection::FoundNpu const &)
0x18000d3b3  nop
0x18000d3b4  lea     rcx, [rsp+120h+var_F0]
0x18000d3b9  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x18000d3be  inc     esi
0x18000d3c0  cmp     esi, r14d
0x18000d3c3  jb      loc_18000D19E
0x18000d3c9  mov     r12, [rbp+57h+var_C0]
0x18000d3cd  lea     rcx, [rsp+120h+var_E8]
0x18000d3d2  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x18000d3d7  add     rdi, 8
0x18000d3db  cmp     rdi, r12
0x18000d3de  jnz     loc_18000D131
0x18000d3e4  lea     rcx, [rbp+57h+var_D0]
0x18000d3e8  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x18000d3ed  nop
0x18000d3ee  mov     rcx, [rbp+57h+var_B8]
0x18000d3f2  test    rcx, rcx
0x18000d3f5  jz      short loc_18000D407
0x18000d3f7  mov     rdx, [rbp+57h+var_A8]
0x18000d3fb  sub     rdx, rcx
0x18000d3fe  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000d402  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000d407  mov     rax, rbx
0x18000d40a  mov     rcx, [rbp+57h+var_50]
0x18000d40e  xor     rcx, rsp; StackCookie
0x18000d411  call    __security_check_cookie
0x18000d416  add     rsp, 0E8h
0x18000d41d  pop     r15
0x18000d41f  pop     r14
0x18000d421  pop     r13
0x18000d423  pop     r12
0x18000d425  pop     rdi
0x18000d426  pop     rsi
0x18000d427  pop     rbx
0x18000d428  pop     rbp
0x18000d429  retn
```
