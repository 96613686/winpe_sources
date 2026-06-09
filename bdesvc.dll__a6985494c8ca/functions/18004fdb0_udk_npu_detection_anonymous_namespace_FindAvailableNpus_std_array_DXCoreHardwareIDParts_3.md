# udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___

- ea: `0x18004fdb0`
- end: `0x180050187`
- name: `udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___`
- size: `983`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180052b38`

## callees

- `0x18002a718`
- `0x180034070`
- `0x18004fdb0`
- `0x180050d58`
- `0x180051754`
- `0x1800518d4`
- `0x180058590`
- `0x180058b6c`
- `0x180058f84`
- `0x18007e010`

## import_xrefs

- `dxcore!DXCoreCreateAdapterFactory` at `0x18004fe75`
- `dxcore!DXCoreCreateAdapterFactory` at `0x18004fe75`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall udk::npu_detection::_anonymous_namespace_::FindAvailableNpus_std::array_DXCoreHardwareIDParts_3___(
        __int64 a1,
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
  __int128 v21; // [rsp+38h] [rbp-81h] BYREF
  __int128 v22; // [rsp+48h] [rbp-71h]
  __int64 v23; // [rsp+58h] [rbp-61h] BYREF
  __int64 v24; // [rsp+60h] [rbp-59h] BYREF
  __int64 *v25; // [rsp+68h] [rbp-51h] BYREF
  __int64 *v26; // [rsp+70h] [rbp-49h] BYREF
  __int128 v27; // [rsp+78h] [rbp-41h] BYREF
  unsigned int v28; // [rsp+88h] [rbp-31h]
  char v29; // [rsp+8Ch] [rbp-2Dh] BYREF
  __int64 *v30; // [rsp+90h] [rbp-29h] BYREF
  __int128 v31; // [rsp+98h] [rbp-21h] BYREF
  void *v32[3]; // [rsp+A8h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v23 = a1;
  std::vector<_GUID const *>::vector<_GUID const *>(a1);
  v6 = (_DWORD *)(v5 + 60);
  std::vector<_GUID const *>::vector<_GUID const *>(v32);
  v25 = DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU;
  std::vector<_GUID const *>::push_back(v32, &v25);
  v25 = DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML;
  std::vector<_GUID const *>::push_back(v32, &v25);
  v25 = DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE;
  std::vector<_GUID const *>::push_back(v32, &v25);
  v30 = 0;
  v7 = DXCoreCreateAdapterFactory(&GUID_78ee5945_c36e_4b13_a669_005dd11c0f06, &v30);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x17D,
      (unsigned int)"onecore\\internal\\shell\\inc\\npu_detection.h",
      (const char *)(unsigned int)v7,
      v20);
  v8 = v32[0];
  v9 = v32[1];
  while ( v8 != v9 )
  {
    v26 = 0;
    v10 = *v30;
    v26 = 0;
    if ( (*(int (__fastcall **)(__int64 *, __int64, _QWORD, GUID *, __int64 **))(v10 + 24))(
           v30,
           1,
           *v8,
           &GUID_526c7776_40e9_459b_b711_f32ad76dfc28,
           &v26) >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64 *))(*v26 + 32))(v26);
      if ( v11 )
      {
        v12 = 0;
        while ( 1 )
        {
          v24 = 0;
          v13 = *v26;
          v24 = 0;
          if ( (*(int (__fastcall **)(__int64 *, _QWORD, GUID *, __int64 *))(v13 + 24))(
                 v26,
                 v12,
                 &GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e,
                 &v24) >= 0 )
          {
            if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 40LL))(v24, 11) )
            {
              v27 = 0;
              v28 = 0;
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 40LL))(v24, 14)
                && (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v24 + 48LL))(
                     v24,
                     14,
                     20,
                     &v27) >= 0 )
              {
                goto LABEL_14;
              }
              if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 40LL))(v24, 3) )
              {
                v31 = 0;
                if ( (*(int (__fastcall **)(__int64, __int64, __int64, __int128 *))(*(_QWORD *)v24 + 48LL))(
                       v24,
                       3,
                       16,
                       &v31) >= 0 )
                  break;
              }
            }
          }
LABEL_35:
          wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(&v24);
          if ( ++v12 >= v11 )
            goto LABEL_36;
        }
        *(_QWORD *)&v27 = v31;
        v28 = HIDWORD(v31);
        DWORD2(v27) = DWORD2(v31);
LABEL_14:
        v25 = 0;
        if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 40LL))(v24, 1)
          && (*(int (__fastcall **)(__int64, __int64, __int64, __int64 **))(*(_QWORD *)v24 + 48LL))(v24, 1, 8, &v25) >= 0 )
        {
          v21 = v27;
          *(_QWORD *)&v22 = v28;
          *((_QWORD *)&v22 + 1) = v25;
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
            v16 = *(_OWORD **)(a1 + 8);
            for ( j = *(_DWORD **)a1; j != (_DWORD *)v16; j += 8 )
            {
              for ( k = (__int64 *)&v21; k != &v23; k += 4 )
              {
                if ( *j == *(_DWORD *)k && j[1] == *((_DWORD *)k + 1) )
                  goto LABEL_35;
              }
            }
            if ( v16 == *(_OWORD **)(a1 + 16) )
            {
              std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(
                a1,
                *(_QWORD *)(a1 + 8),
                &v21);
            }
            else
            {
              *v16 = v21;
              v16[1] = v22;
              *(_QWORD *)(a1 + 8) += 32LL;
            }
          }
        }
        goto LABEL_35;
      }
    }
LABEL_36:
    wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>((__int64 *)&v26);
    ++v8;
  }
  wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>((__int64 *)&v30);
  if ( v32[0] )
    std::_Deallocate<16>(v32[0], (struct std::nothrow_t *)(((char *)v32[2] - (char *)v32[0]) & 0xFFFFFFFFFFFFFFF8uLL));
  return a1;
}

```

## disassembly

```asm
0x18004fdb0  push    rbp
0x18004fdb2  push    rbx
0x18004fdb3  push    rsi
0x18004fdb4  push    rdi
0x18004fdb5  push    r12
0x18004fdb7  push    r13
0x18004fdb9  push    r14
0x18004fdbb  push    r15
0x18004fdbd  lea     rbp, [rsp-1Fh]
0x18004fdc2  sub     rsp, 0D8h
0x18004fdc9  mov     rax, cs:__security_cookie
0x18004fdd0  xor     rax, rsp
0x18004fdd3  mov     [rbp+57h+var_50], rax
0x18004fdd7  mov     r14, r8
0x18004fdda  mov     rbx, rcx
0x18004fddd  mov     [rbp+57h+var_B8], rcx
0x18004fde1  mov     [rsp+110h+var_E0], 0
0x18004fde9  call    ??0?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID const *>::vector<_GUID const *>(void)
0x18004fdee  mov     [rsp+110h+var_E0], 1
0x18004fdf6  lea     r13, [r8+3Ch]
0x18004fdfa  cmp     r8, r13
0x18004fdfd  jnz     short loc_18004FE0F
0x18004fdff  mov     rcx, [rbp+5Fh]; this
0x18004fe03  mov     r9d, 80070057h; char *
0x18004fe09  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004fe0f  lea     rcx, [rbp+57h+var_68]
0x18004fe13  call    ??0?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID const *>::vector<_GUID const *>(void)
0x18004fe18  nop
0x18004fe19  lea     rax, DXCORE_HARDWARE_TYPE_ATTRIBUTE_NPU
0x18004fe20  mov     [rbp+57h+var_A8], rax
0x18004fe24  lea     rdx, [rbp+57h+var_A8]
0x18004fe28  lea     rcx, [rbp+57h+var_68]
0x18004fe2c  call    ?push_back@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAAX$$QEAPEBU_GUID@@@Z; std::vector<_GUID const *>::push_back(_GUID const * &&)
0x18004fe31  lea     rax, DXCORE_ADAPTER_ATTRIBUTE_D3D12_GENERIC_ML
0x18004fe38  mov     [rbp+57h+var_A8], rax
0x18004fe3c  lea     rdx, [rbp+57h+var_A8]
0x18004fe40  lea     rcx, [rbp+57h+var_68]
0x18004fe44  call    ?push_back@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAAX$$QEAPEBU_GUID@@@Z; std::vector<_GUID const *>::push_back(_GUID const * &&)
0x18004fe49  lea     rax, DXCORE_ADAPTER_ATTRIBUTE_D3D12_CORE_COMPUTE
0x18004fe50  mov     [rbp+57h+var_A8], rax
0x18004fe54  lea     rdx, [rbp+57h+var_A8]
0x18004fe58  lea     rcx, [rbp+57h+var_68]
0x18004fe5c  call    ?push_back@?$vector@PEBU_GUID@@V?$allocator@PEBU_GUID@@@std@@@std@@QEAAX$$QEAPEBU_GUID@@@Z; std::vector<_GUID const *>::push_back(_GUID const * &&)
0x18004fe61  nop
0x18004fe62  mov     [rbp+57h+var_80], 0
0x18004fe6a  lea     rdx, [rbp+57h+var_80]
0x18004fe6e  lea     rcx, _GUID_78ee5945_c36e_4b13_a669_005dd11c0f06
0x18004fe75  call    cs:__imp_DXCoreCreateAdapterFactory
0x18004fe7c  nop     dword ptr [rax+rax+00h]
0x18004fe81  mov     rcx, [rbp+5Fh]; this
0x18004fe85  test    eax, eax
0x18004fe87  jns     short loc_18004FE9E
0x18004fe89  mov     r9d, eax; char *
0x18004fe8c  lea     r8, aOnecoreInterna_2; "onecore\\internal\\shell\\inc\\npu_dete"...
0x18004fe93  mov     edx, 17Dh; void *
0x18004fe98  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004fe9e  mov     rdi, [rbp+57h+var_68]
0x18004fea2  mov     r12, [rbp+57h+var_60]
0x18004fea6  jmp     loc_180050137
0x18004feab  mov     [rbp+57h+var_A0], 0
0x18004feb3  mov     rcx, [rbp+57h+var_80]
0x18004feb7  mov     rax, [rcx]
0x18004feba  mov     [rbp+57h+var_A0], 0
0x18004fec2  lea     rdx, [rbp+57h+var_A0]
0x18004fec6  mov     qword ptr [rsp+110h+var_F0], rdx
0x18004fecb  lea     r9, _GUID_526c7776_40e9_459b_b711_f32ad76dfc28
0x18004fed2  mov     r8, [rdi]
0x18004fed5  mov     edx, 1
0x18004feda  mov     rax, [rax+18h]
0x18004fede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fee3  test    eax, eax
0x18004fee5  js      loc_18005012A
0x18004feeb  mov     rcx, [rbp+57h+var_A0]
0x18004feef  mov     rax, [rcx]
0x18004fef2  mov     rax, [rax+20h]
0x18004fef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fefb  mov     r15d, eax
0x18004fefe  test    eax, eax
0x18004ff00  jz      loc_18005012A
0x18004ff06  xor     esi, esi
0x18004ff08  test    eax, eax
0x18004ff0a  jz      loc_18005012A
0x18004ff10  mov     [rbp+57h+var_B0], 0
0x18004ff18  mov     rcx, [rbp+57h+var_A0]
0x18004ff1c  mov     rax, [rcx]
0x18004ff1f  mov     [rbp+57h+var_B0], 0
0x18004ff27  lea     r9, [rbp+57h+var_B0]
0x18004ff2b  lea     r8, _GUID_f0db4c7f_fe5a_42a2_bd62_f2a6cf6fc83e
0x18004ff32  mov     edx, esi
0x18004ff34  mov     rax, [rax+18h]
0x18004ff38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff3d  test    eax, eax
0x18004ff3f  js      loc_180050116
0x18004ff45  mov     rcx, [rbp+57h+var_B0]
0x18004ff49  mov     rax, [rcx]
0x18004ff4c  mov     edx, 0Bh
0x18004ff51  mov     rax, [rax+28h]
0x18004ff55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff5a  test    al, al
0x18004ff5c  jz      loc_180050116
0x18004ff62  xorps   xmm0, xmm0
0x18004ff65  xor     eax, eax
0x18004ff67  movups  [rbp+57h+var_98], xmm0
0x18004ff6b  mov     [rbp+57h+var_88], eax
0x18004ff6e  mov     rcx, [rbp+57h+var_B0]
0x18004ff72  mov     rax, [rcx]
0x18004ff75  mov     edx, 0Eh
0x18004ff7a  mov     rax, [rax+28h]
0x18004ff7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ff83  test    al, al
0x18004ff85  jz      short loc_18004FFA8
0x18004ff87  mov     rcx, [rbp+57h+var_B0]
0x18004ff8b  mov     rax, [rcx]
0x18004ff8e  lea     r9, [rbp+57h+var_98]
0x18004ff92  mov     edx, 0Eh
0x18004ff97  lea     r8d, [rdx+6]
0x18004ff9b  mov     rax, [rax+30h]
0x18004ff9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ffa4  test    eax, eax
0x18004ffa6  jns     short loc_180050009
0x18004ffa8  mov     rcx, [rbp+57h+var_B0]
0x18004ffac  mov     rax, [rcx]
0x18004ffaf  mov     edx, 3
0x18004ffb4  mov     rax, [rax+28h]
0x18004ffb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ffbd  test    al, al
0x18004ffbf  jz      loc_180050116
0x18004ffc5  xorps   xmm0, xmm0
0x18004ffc8  movups  [rbp+57h+var_78], xmm0
0x18004ffcc  mov     rcx, [rbp+57h+var_B0]
0x18004ffd0  mov     rax, [rcx]
0x18004ffd3  lea     r9, [rbp+57h+var_78]
0x18004ffd7  mov     edx, 3
0x18004ffdc  lea     r8d, [rdx+0Dh]
0x18004ffe0  mov     rax, [rax+30h]
0x18004ffe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ffe9  test    eax, eax
0x18004ffeb  js      loc_180050116
0x18004fff1  mov     eax, dword ptr [rbp+57h+var_78]
0x18004fff4  mov     dword ptr [rbp+57h+var_98], eax
0x18004fff7  mov     eax, dword ptr [rbp+57h+var_78+4]
0x18004fffa  mov     dword ptr [rbp+57h+var_98+4], eax
0x18004fffd  mov     eax, dword ptr [rbp+57h+var_78+0Ch]
0x180050000  mov     [rbp+57h+var_88], eax
0x180050003  mov     eax, dword ptr [rbp+57h+var_78+8]
0x180050006  mov     dword ptr [rbp+57h+var_98+8], eax
0x180050009  mov     [rbp+57h+var_A8], 0
0x180050011  mov     rcx, [rbp+57h+var_B0]
0x180050015  mov     rax, [rcx]
0x180050018  mov     edx, 1
0x18005001d  mov     rax, [rax+28h]
0x180050021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050026  test    al, al
0x180050028  jz      loc_180050116
0x18005002e  mov     rcx, [rbp+57h+var_B0]
0x180050032  mov     rax, [rcx]
0x180050035  lea     r9, [rbp+57h+var_A8]
0x180050039  mov     edx, 1
0x18005003e  lea     r8d, [rdx+7]
0x180050042  mov     rax, [rax+30h]
0x180050046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005004b  test    eax, eax
0x18005004d  js      loc_180050116
0x180050053  mov     eax, dword ptr [rbp+57h+var_98]
0x180050056  mov     dword ptr [rsp+110h+var_D8], eax
0x18005005a  mov     eax, dword ptr [rbp+57h+var_98+4]
0x18005005d  mov     dword ptr [rbp+57h+var_D8+4], eax
0x180050060  mov     eax, dword ptr [rbp+57h+var_98+8]
0x180050063  mov     dword ptr [rbp+57h+var_D8+8], eax
0x180050066  mov     eax, dword ptr [rbp+57h+var_98+0Ch]
0x180050069  mov     dword ptr [rbp+57h+var_D8+0Ch], eax
0x18005006c  mov     eax, [rbp+57h+var_88]
0x18005006f  mov     dword ptr [rbp+57h+var_C8], eax
0x180050072  xor     eax, eax
0x180050074  mov     dword ptr [rbp+57h+var_C8+4], eax
0x180050077  mov     rax, [rbp+57h+var_A8]
0x18005007b  mov     qword ptr [rbp+57h+var_C8+8], rax
0x18005007f  mov     rdx, r14
0x180050082  cmp     rdx, r13
0x180050085  jz      loc_180050116
0x18005008b  lea     rcx, [rbp+57h+var_98]
0x18005008f  lea     rax, [rbp+57h+var_84]
0x180050093  cmp     rcx, rax
0x180050096  jz      short loc_1800500AC
0x180050098  mov     eax, [rcx]
0x18005009a  cmp     [rdx], eax
0x18005009c  jnz     short loc_1800500A6
0x18005009e  mov     eax, [rcx+4]
0x1800500a1  cmp     [rdx+4], eax
0x1800500a4  jz      short loc_1800500B2
0x1800500a6  add     rcx, 14h
0x1800500aa  jmp     short loc_18005008F
0x1800500ac  add     rdx, 14h
0x1800500b0  jmp     short loc_180050082
0x1800500b2  mov     r9, [rbx+8]
0x1800500b6  mov     rdx, [rbx]
0x1800500b9  cmp     rdx, r9
0x1800500bc  jz      short loc_1800500E6
0x1800500be  lea     rcx, [rsp+110h+var_D8]
0x1800500c3  lea     rax, [rbp+57h+var_B8]
0x1800500c7  cmp     rcx, rax
0x1800500ca  jz      short loc_1800500E0
0x1800500cc  mov     eax, [rcx]
0x1800500ce  cmp     [rdx], eax
0x1800500d0  jnz     short loc_1800500DA
0x1800500d2  mov     eax, [rcx+4]
0x1800500d5  cmp     [rdx+4], eax
0x1800500d8  jz      short loc_180050116
0x1800500da  add     rcx, 20h ; ' '
0x1800500de  jmp     short loc_1800500C3
0x1800500e0  add     rdx, 20h ; ' '
0x1800500e4  jmp     short loc_1800500B9
0x1800500e6  cmp     r9, [rbx+10h]
0x1800500ea  jz      short loc_180050105
0x1800500ec  movups  xmm0, [rsp+110h+var_D8]
0x1800500f1  movups  xmmword ptr [r9], xmm0
0x1800500f5  movups  xmm1, [rbp+57h+var_C8]
0x1800500f9  movups  xmmword ptr [r9+10h], xmm1
0x1800500fe  add     qword ptr [rbx+8], 20h ; ' '
0x180050103  jmp     short loc_180050116
0x180050105  lea     r8, [rsp+110h+var_D8]
0x18005010a  mov     rdx, r9
0x18005010d  mov     rcx, rbx
0x180050110  call    ??$_Emplace_reallocate@AEBUFoundNpu@npu_detection@udk@@@?$vector@UFoundNpu@npu_detection@udk@@V?$allocator@UFoundNpu@npu_detection@udk@@@std@@@std@@AEAAPEAUFoundNpu@npu_detection@udk@@QEAU234@AEBU234@@Z; std::vector<udk::npu_detection::FoundNpu>::_Emplace_reallocate<udk::npu_detection::FoundNpu const &>(udk::npu_detection::FoundNpu * const,udk::npu_detection::FoundNpu const &)
0x180050115  nop
0x180050116  lea     rcx, [rbp+57h+var_B0]
0x18005011a  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x18005011f  inc     esi
0x180050121  cmp     esi, r15d
0x180050124  jb      loc_18004FF10
0x18005012a  lea     rcx, [rbp+57h+var_A0]
0x18005012e  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180050133  add     rdi, 8
0x180050137  cmp     rdi, r12
0x18005013a  jnz     loc_18004FEAB
0x180050140  lea     rcx, [rbp+57h+var_80]
0x180050144  call    ??1?$com_ptr_t@UIDXCoreAdapterFactory@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>::~com_ptr_t<IDXCoreAdapterFactory,wil::err_exception_policy>(void)
0x180050149  nop
0x18005014a  mov     rcx, [rbp+57h+var_68]
0x18005014e  test    rcx, rcx
0x180050151  jz      short loc_180050163
0x180050153  mov     rdx, [rbp+57h+var_58]
0x180050157  sub     rdx, rcx
0x18005015a  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18005015e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180050163  mov     rax, rbx
0x180050166  mov     rcx, [rbp+57h+var_50]
0x18005016a  xor     rcx, rsp; StackCookie
0x18005016d  call    __security_check_cookie
0x180050172  add     rsp, 0D8h
0x180050179  pop     r15
0x18005017b  pop     r14
0x18005017d  pop     r13
0x18005017f  pop     r12
0x180050181  pop     rdi
0x180050182  pop     rsi
0x180050183  pop     rbx
0x180050184  pop     rbp
0x180050185  retn
```
