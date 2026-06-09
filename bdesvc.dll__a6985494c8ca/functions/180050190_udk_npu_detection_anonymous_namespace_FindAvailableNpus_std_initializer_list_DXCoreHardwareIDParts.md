# udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::initializer_list_DXCoreHardwareIDParts___

- ea: `0x180050190`
- end: `0x180050540`
- name: `udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::initializer_list_DXCoreHardwareIDParts___`
- size: `944`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052b38`

## callees

- `0x18002a718`
- `0x180034070`
- `0x180050190`
- `0x180050d58`
- `0x180051754`
- `0x1800518d4`
- `0x180058b6c`
- `0x180058f84`
- `0x18007e010`

## import_xrefs

- `dxcore!DXCoreCreateAdapterFactory` at `0x180050217`
- `dxcore!DXCoreCreateAdapterFactory` at `0x180050217`

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
  __int128 v22; // [rsp+38h] [rbp-91h] BYREF
  __int128 v23; // [rsp+48h] [rbp-81h]
  __int64 v24; // [rsp+58h] [rbp-71h] BYREF
  _QWORD *v25; // [rsp+60h] [rbp-69h]
  __int64 v26; // [rsp+68h] [rbp-61h]
  __int64 v27; // [rsp+70h] [rbp-59h] BYREF
  __int64 *v28; // [rsp+78h] [rbp-51h] BYREF
  __int128 v29; // [rsp+80h] [rbp-49h] BYREF
  unsigned int v30; // [rsp+90h] [rbp-39h]
  char v31; // [rsp+94h] [rbp-35h] BYREF
  __int64 *v32; // [rsp+98h] [rbp-31h] BYREF
  __int64 *v33; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v34; // [rsp+A8h] [rbp-21h] BYREF
  _QWORD *v35; // [rsp+B8h] [rbp-11h] BYREF
  _QWORD *v36; // [rsp+C0h] [rbp-9h]
  __int64 v37; // [rsp+C8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v26 = a1;
  std::vector<_GUID const *>::vector<_GUID const *>(a1);
  v6 = *v5;
  v24 = v5[1];
  std::vector<_GUID const *>::vector<_GUID const *>(&v35);
  v32 = DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU;
  std::vector<_GUID const *>::push_back(&v35, &v32);
  v33 = 0;
  v7 = DXCoreCreateAdapterFactory(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, &v33);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"onecore\\internal\\shell\\inc\\npu_detection.h",
      (const char *)(unsigned int)v7,
      v21);
  v8 = v35;
  v9 = v36;
  v25 = v36;
  while ( v8 != v9 )
  {
    v28 = 0;
    v10 = *v33;
    v28 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64, _QWORD, GUID *, __int64 **))(v10 + 24))(
           v33,
           1,
           *v8,
           &GUID_526c7776_40e9_459b_b711_f32ad76dfc28,
           &v28) >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64 *))(*v28 + 32))(v28);
      if ( v11 )
      {
        v12 = 0;
        v13 = v24;
        while ( 1 )
        {
          v27 = 0;
          v14 = *v28;
          v27 = 0;
          if ( (*(int (__fastcall **)(__int64 *, _QWORD, GUID *, __int64 *))(v14 + 24))(
                 v28,
                 v12,
                 &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e,
                 &v27) >= 0 )
          {
            if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 40LL))(v27, 11) )
            {
              v29 = 0;
              v30 = 0;
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 40LL))(v27, 14)
                && (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v27 + 48LL))(
                     v27,
                     14,
                     20,
                     &v29) >= 0 )
              {
                goto LABEL_14;
              }
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 40LL))(v27, 3) )
              {
                v34 = 0;
                if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v27 + 48LL))(
                       v27,
                       3,
                       16,
                       &v34) >= 0 )
                  break;
              }
            }
          }
LABEL_36:
          wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v27);
          if ( ++v12 >= v11 )
          {
            v9 = v25;
            goto LABEL_38;
          }
        }
        *(_QWORD *)&v29 = v34;
        v30 = HIDWORD(v34);
        DWORD2(v29) = DWORD2(v34);
LABEL_14:
        v32 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v27 + 40LL))(v27, 1)
          && (*(int (__fastcall **)(__int64, __int64, __int64, __int64 **))(*(_QWORD *)v27 + 48LL))(v27, 1, 8, &v32) >= 0 )
        {
          v22 = v29;
          *(_QWORD *)&v23 = v30;
          *((_QWORD *)&v23 + 1) = v32;
          if ( v6 == v13 )
          {
LABEL_25:
            v17 = *(_OWORD **)(a1 + 8);
            for ( i = *(_DWORD **)a1; i != (_DWORD *)v17; i += 8 )
            {
              for ( j = (__int64 *)&v22; j != &v24; j += 4 )
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
                &v22);
            }
            else
            {
              *v17 = v22;
              v17[1] = v23;
              *(_QWORD *)(a1 + 8) += 32LL;
            }
          }
          else
          {
            for ( k = *a3; k != a3[1]; k += 5 )
            {
              for ( m = &v29; m != (__int128 *)&v31; m = (__int128 *)((char *)m + 20) )
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
    wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>((__int64 *)&v28);
    ++v8;
  }
  wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>((__int64 *)&v33);
  if ( v35 )
    std::_Deallocate<16>(v35, (struct std::nothrow_t *)((v37 - (_QWORD)v35) & 0xFFFFFFFFFFFFFFF8uLL));
  return a1;
}

```

## disassembly

```asm
0x180050190  push    rbp
0x180050192  push    rbx
0x180050193  push    rsi
0x180050194  push    rdi
0x180050195  push    r12
0x180050197  push    r13
0x180050199  push    r14
0x18005019b  push    r15
0x18005019d  lea     rbp, [rsp-1Fh]
0x1800501a2  sub     rsp, 0E8h
0x1800501a9  mov     rax, cs:__security_cookie
0x1800501b0  xor     rax, rsp
0x1800501b3  mov     [rbp+57h+var_50], rax
0x1800501b7  mov     r15, r8
0x1800501ba  mov     rbx, rcx
0x1800501bd  mov     [rbp+57h+var_B8], rcx
0x1800501c1  mov     [rsp+120h+var_F0], 0
0x1800501c9  call    ??0?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID const *>::vector<_GUID const *>(void)
0x1800501ce  mov     [rsp+120h+var_F0], 1
0x1800501d6  mov     r13, [r8]
0x1800501d9  mov     rax, [r8+8]
0x1800501dd  mov     [rbp+57h+var_C8], rax
0x1800501e1  lea     rcx, [rbp+57h+var_68]
0x1800501e5  call    ??0?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID const *>::vector<_GUID const *>(void)
0x1800501ea  nop
0x1800501eb  lea     rax, DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU
0x1800501f2  mov     [rbp+57h+var_88], rax
0x1800501f6  lea     rdx, [rbp+57h+var_88]
0x1800501fa  lea     rcx, [rbp+57h+var_68]
0x1800501fe  call    ?push_back@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAAX$$QEAPEBU_GUID@@@Z; std::vector<_GUID const *>::push_back(_GUID const * &&)
0x180050203  nop
0x180050204  mov     [rbp+57h+var_80], 0
0x18005020c  lea     rdx, [rbp+57h+var_80]
0x180050210  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x180050217  call    cs:__imp_DXCoreCreateAdapterFactory
0x18005021e  nop     dword ptr [rax+rax+00h]
0x180050223  mov     rcx, [rbp+5Fh]; this
0x180050227  test    eax, eax
0x180050229  jns     short loc_180050240
0x18005022b  mov     r9d, eax; char *
0x18005022e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\shell\\inc\\npu_dete"...
0x180050235  mov     edx, 17Dh; void *
0x18005023a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180050240  mov     rdi, [rbp+57h+var_68]
0x180050244  mov     r12, [rbp+57h+var_60]
0x180050248  mov     [rbp+57h+var_C0], r12
0x18005024c  jmp     loc_1800504F0
0x180050251  mov     [rbp+57h+var_A8], 0
0x180050259  mov     rcx, [rbp+57h+var_80]
0x18005025d  mov     rax, [rcx]
0x180050260  mov     [rbp+57h+var_A8], 0
0x180050268  lea     rdx, [rbp+57h+var_A8]
0x18005026c  mov     qword ptr [rsp+120h+var_100], rdx
0x180050271  lea     r9, _GUID_526c7776_40e9_459b_b711_f32ad76dfc28
0x180050278  mov     r8, [rdi]
0x18005027b  mov     edx, 1
0x180050280  mov     rax, [rax+18h]
0x180050284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050289  test    eax, eax
0x18005028b  js      loc_1800504E3
0x180050291  mov     rcx, [rbp+57h+var_A8]
0x180050295  mov     rax, [rcx]
0x180050298  mov     rax, [rax+20h]
0x18005029c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502a1  mov     r14d, eax
0x1800502a4  test    eax, eax
0x1800502a6  jz      loc_1800504E3
0x1800502ac  xor     esi, esi
0x1800502ae  test    eax, eax
0x1800502b0  jz      loc_1800504E3
0x1800502b6  mov     r12, [rbp+57h+var_C8]
0x1800502ba  mov     [rbp+57h+var_B0], 0
0x1800502c2  mov     rcx, [rbp+57h+var_A8]
0x1800502c6  mov     rax, [rcx]
0x1800502c9  mov     [rbp+57h+var_B0], 0
0x1800502d1  lea     r9, [rbp+57h+var_B0]
0x1800502d5  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x1800502dc  mov     edx, esi
0x1800502de  mov     rax, [rax+18h]
0x1800502e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800502e7  test    eax, eax
0x1800502e9  js      loc_1800504CB
0x1800502ef  mov     rcx, [rbp+57h+var_B0]
0x1800502f3  mov     rax, [rcx]
0x1800502f6  mov     edx, 0Bh
0x1800502fb  mov     rax, [rax+28h]
0x1800502ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050304  test    al, al
0x180050306  jz      loc_1800504CB
0x18005030c  xorps   xmm0, xmm0
0x18005030f  xor     eax, eax
0x180050311  movups  [rbp+57h+var_A0], xmm0
0x180050315  mov     [rbp+57h+var_90], eax
0x180050318  mov     rcx, [rbp+57h+var_B0]
0x18005031c  mov     rax, [rcx]
0x18005031f  mov     edx, 0Eh
0x180050324  mov     rax, [rax+28h]
0x180050328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005032d  test    al, al
0x18005032f  jz      short loc_180050352
0x180050331  mov     rcx, [rbp+57h+var_B0]
0x180050335  mov     rax, [rcx]
0x180050338  lea     r9, [rbp+57h+var_A0]
0x18005033c  mov     edx, 0Eh
0x180050341  lea     r8d, [rdx+6]
0x180050345  mov     rax, [rax+30h]
0x180050349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005034e  test    eax, eax
0x180050350  jns     short loc_1800503B3
0x180050352  mov     rcx, [rbp+57h+var_B0]
0x180050356  mov     rax, [rcx]
0x180050359  mov     edx, 3
0x18005035e  mov     rax, [rax+28h]
0x180050362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050367  test    al, al
0x180050369  jz      loc_1800504CB
0x18005036f  xorps   xmm0, xmm0
0x180050372  movups  [rbp+57h+var_78], xmm0
0x180050376  mov     rcx, [rbp+57h+var_B0]
0x18005037a  mov     rax, [rcx]
0x18005037d  lea     r9, [rbp+57h+var_78]
0x180050381  mov     edx, 3
0x180050386  lea     r8d, [rdx+0Dh]
0x18005038a  mov     rax, [rax+30h]
0x18005038e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050393  test    eax, eax
0x180050395  js      loc_1800504CB
0x18005039b  mov     eax, dword ptr [rbp+57h+var_78]
0x18005039e  mov     dword ptr [rbp+57h+var_A0], eax
0x1800503a1  mov     eax, dword ptr [rbp+57h+var_78+4]
0x1800503a4  mov     dword ptr [rbp+57h+var_A0+4], eax
0x1800503a7  mov     eax, dword ptr [rbp+57h+var_78+0Ch]
0x1800503aa  mov     [rbp+57h+var_90], eax
0x1800503ad  mov     eax, dword ptr [rbp+57h+var_78+8]
0x1800503b0  mov     dword ptr [rbp+57h+var_A0+8], eax
0x1800503b3  mov     [rbp+57h+var_88], 0
0x1800503bb  mov     rcx, [rbp+57h+var_B0]
0x1800503bf  mov     rax, [rcx]
0x1800503c2  mov     edx, 1
0x1800503c7  mov     rax, [rax+28h]
0x1800503cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503d0  test    al, al
0x1800503d2  jz      loc_1800504CB
0x1800503d8  mov     rcx, [rbp+57h+var_B0]
0x1800503dc  mov     rax, [rcx]
0x1800503df  lea     r9, [rbp+57h+var_88]
0x1800503e3  mov     edx, 1
0x1800503e8  lea     r8d, [rdx+7]
0x1800503ec  mov     rax, [rax+30h]
0x1800503f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800503f5  test    eax, eax
0x1800503f7  js      loc_1800504CB
0x1800503fd  mov     eax, dword ptr [rbp+57h+var_A0]
0x180050400  mov     dword ptr [rsp+120h+var_E8], eax
0x180050404  mov     eax, dword ptr [rbp+57h+var_A0+4]
0x180050407  mov     dword ptr [rsp+120h+var_E8+4], eax
0x18005040b  mov     eax, dword ptr [rbp+57h+var_A0+8]
0x18005040e  mov     dword ptr [rsp+120h+var_E8+8], eax
0x180050412  mov     eax, dword ptr [rbp+57h+var_A0+0Ch]
0x180050415  mov     dword ptr [rsp+120h+var_E8+0Ch], eax
0x180050419  mov     eax, [rbp+57h+var_90]
0x18005041c  mov     dword ptr [rsp+120h+var_D8], eax
0x180050420  xor     eax, eax
0x180050422  mov     dword ptr [rbp+57h+var_D8+4], eax
0x180050425  mov     rax, [rbp+57h+var_88]
0x180050429  mov     qword ptr [rbp+57h+var_D8+8], rax
0x18005042d  cmp     r13, r12
0x180050430  jz      short loc_180050466
0x180050432  mov     rdx, [r15]
0x180050435  cmp     rdx, [r15+8]
0x180050439  jz      loc_1800504CB
0x18005043f  lea     rcx, [rbp+57h+var_A0]
0x180050443  lea     rax, [rbp+57h+var_8C]
0x180050447  cmp     rcx, rax
0x18005044a  jz      short loc_180050460
0x18005044c  mov     eax, [rcx]
0x18005044e  cmp     [rdx], eax
0x180050450  jnz     short loc_18005045A
0x180050452  mov     eax, [rcx+4]
0x180050455  cmp     [rdx+4], eax
0x180050458  jz      short loc_180050466
0x18005045a  add     rcx, 14h
0x18005045e  jmp     short loc_180050443
0x180050460  add     rdx, 14h
0x180050464  jmp     short loc_180050435
0x180050466  mov     r9, [rbx+8]
0x18005046a  mov     rdx, [rbx]
0x18005046d  cmp     rdx, r9
0x180050470  jz      short loc_18005049A
0x180050472  lea     rcx, [rsp+120h+var_E8]
0x180050477  lea     rax, [rbp+57h+var_C8]
0x18005047b  cmp     rcx, rax
0x18005047e  jz      short loc_180050494
0x180050480  mov     eax, [rcx]
0x180050482  cmp     [rdx], eax
0x180050484  jnz     short loc_18005048E
0x180050486  mov     eax, [rcx+4]
0x180050489  cmp     [rdx+4], eax
0x18005048c  jz      short loc_1800504CB
0x18005048e  add     rcx, 20h ; ' '
0x180050492  jmp     short loc_180050477
0x180050494  add     rdx, 20h ; ' '
0x180050498  jmp     short loc_18005046D
0x18005049a  cmp     r9, [rbx+10h]
0x18005049e  jz      short loc_1800504BA
0x1800504a0  movups  xmm0, [rsp+120h+var_E8]
0x1800504a5  movups  xmmword ptr [r9], xmm0
0x1800504a9  movups  xmm1, [rsp+120h+var_D8]
0x1800504ae  movups  xmmword ptr [r9+10h], xmm1
0x1800504b3  add     qword ptr [rbx+8], 20h ; ' '
0x1800504b8  jmp     short loc_1800504CB
0x1800504ba  lea     r8, [rsp+120h+var_E8]
0x1800504bf  mov     rdx, r9
0x1800504c2  mov     rcx, rbx
0x1800504c5  call    ??$_Emplace_reallocate@AEBUFoundNpu@npu_detection@udk@@@?$vector@UFoundNpu@npu_detection@udk@@V?$allocator@UFoundNpu@npu_detection@udk@@@std@@@std@@AEAAPEAUFoundNpu@npu_detection@udk@@QEAU234@AEBU234@@Z; std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(udk::npu_detection::FoundNpu * const,udk::npu_detection::FoundNpu const &)
0x1800504ca  nop
0x1800504cb  lea     rcx, [rbp+57h+var_B0]
0x1800504cf  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x1800504d4  inc     esi
0x1800504d6  cmp     esi, r14d
0x1800504d9  jb      loc_1800502BA
0x1800504df  mov     r12, [rbp+57h+var_C0]
0x1800504e3  lea     rcx, [rbp+57h+var_A8]
0x1800504e7  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x1800504ec  add     rdi, 8
0x1800504f0  cmp     rdi, r12
0x1800504f3  jnz     loc_180050251
0x1800504f9  lea     rcx, [rbp+57h+var_80]
0x1800504fd  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180050502  nop
0x180050503  mov     rcx, [rbp+57h+var_68]
0x180050507  test    rcx, rcx
0x18005050a  jz      short loc_18005051C
0x18005050c  mov     rdx, [rbp+57h+var_58]
0x180050510  sub     rdx, rcx
0x180050513  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180050517  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18005051c  mov     rax, rbx
0x18005051f  mov     rcx, [rbp+57h+var_50]
0x180050523  xor     rcx, rsp; StackCookie
0x180050526  call    __security_check_cookie
0x18005052b  add     rsp, 0E8h
0x180050532  pop     r15
0x180050534  pop     r14
0x180050536  pop     r13
0x180050538  pop     r12
0x18005053a  pop     rdi
0x18005053b  pop     rsi
0x18005053c  pop     rbx
0x18005053d  pop     rbp
0x18005053e  retn
```
