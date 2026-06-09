# DetectAudioPostureSupport(IMMDevice *,IConnector *,wil::unique_struct<tagPROPVARIANT,long (*)(tagPROPVARIANT *),&PropVariantClear(tagPROPVARIANT *),void (*)(tagPROPVARIANT *),&PropVariantInit(tagPROPVARIANT *)> &)

- ea: `0x180021edc`
- end: `0x180022463`
- name: `?DetectAudioPostureSupport@@YAJPEAUIMMDevice@@PEAUIConnector@@AEAV?$unique_struct@UtagPROPVARIANT@@P6AJPEAU1@@Z$1?PropVariantClear@@YAJ0@ZP6AX0@Z$1?PropVariantInit@@YAX0@Z@wil@@@Z`
- size: `1415`
- prototype: `__int64 __fastcall(__int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _WORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a344`

## callees

- `0x180006b0c`
- `0x180010da8`
- `0x180021edc`
- `0x18003512c`
- `0x18003514c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022346`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022346`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021f6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002200f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800220d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022122`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002219a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800222df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800223c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800223d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002240a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002241a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021f6b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002200f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800220d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022122`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002219a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800222df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800223c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800223d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002240a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002241a`

## string_xrefs

- `0x180021f50`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180021ff4`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180022108`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002217f`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180022364`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800223b0`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall DetectAudioPostureSupport(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        _WORD *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 (__fastcall *v7)(__int64, __int64 *); // rdi
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, LPVOID *); // rsi
  void *v12; // rbx
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  int v14; // eax
  __int64 (__fastcall *v15)(__int64, GUID *, __int64); // rdi
  _DWORD *v16; // rbx
  int v17; // edi
  __int64 v18; // rdx
  __int64 *v20; // [rsp+20h] [rbp-59h]
  int v21; // [rsp+20h] [rbp-59h]
  __int64 v22; // [rsp+40h] [rbp-39h] BYREF
  __int64 v23; // [rsp+48h] [rbp-31h] BYREF
  __int64 v24; // [rsp+50h] [rbp-29h] BYREF
  __int64 v25; // [rsp+58h] [rbp-21h] BYREF
  _DWORD *v26; // [rsp+60h] [rbp-19h] BYREF
  _DWORD v27[8]; // [rsp+68h] [rbp-11h] BYREF
  SIZE_T cb[2]; // [rsp+88h] [rbp+Fh] BYREF
  __int128 v29; // [rsp+98h] [rbp+1Fh]
  __int64 v30; // [rsp+A8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  int v32; // [rsp+E0h] [rbp+67h] BYREF
  int v33; // [rsp+E4h] [rbp+6Bh]
  int v34; // [rsp+E8h] [rbp+6Fh]
  LPVOID pv; // [rsp+F8h] [rbp+7Fh] BYREF

  v33 = HIDWORD(a1);
  memset(v27, 0, sizeof(v27));
  v32 = 0;
  v22 = 0;
  v24 = 0;
  v23 = 0;
  pv = 0;
  v25 = 0;
  v4 = (**a2)(a2, &GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9, &v25);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF23,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v4,
      (int)v20);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    return v5;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 32LL))(v25, &v32);
  v5 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF25,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v6,
      (int)v20);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    return v5;
  }
  v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 96LL);
  v24 = 0;
  v8 = v7(v25, &v24);
  v5 = v8;
  if ( v8 < 0 )
  {
    v9 = 3880;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v8,
      (int)v20);
    goto LABEL_20;
  }
  v10 = v24;
  v11 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v24 + 64LL);
  v12 = pv;
  if ( pv )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v26);
    CoTaskMemFree(v12);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v26);
  }
  pv = 0;
  v8 = v11(v10, &pv);
  v5 = v8;
  if ( v8 < 0 )
  {
    v9 = 3883;
    goto LABEL_19;
  }
  Release = g_DeviceEnumerator->lpVtbl[1].Release;
  v23 = 0;
  v14 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID, __int64 *))Release)(g_DeviceEnumerator, pv, &v23);
  v5 = v14;
  if ( v14 >= 0 )
  {
    v15 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v23 + 24LL);
    v22 = 0;
    v20 = &v22;
    v8 = v15(v23, &GUID_28f54685_06fd_11d2_b27a_00a0c9223196, 1);
    v5 = v8;
    if ( v8 < 0 )
    {
      v9 = 3888;
      goto LABEL_19;
    }
    v27[7] = 0;
    v27[0] = -1543800051;
    *(_QWORD *)&v27[1] = *(_QWORD *)&GUID_a3fb7b0d_474e_4f51_a379_51282dd4fa8f.Data2;
    v27[3] = *(_DWORD *)&GUID_a3fb7b0d_474e_4f51_a379_51282dd4fa8f.Data4[4];
    v27[4] = 1;
    v27[5] = 512;
    v27[6] = (unsigned __int16)v32;
    *(_OWORD *)cb = 0;
    v29 = 0;
    v30 = 0;
    v34 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64, SIZE_T *))(*(_QWORD *)v22 + 24LL))(v22, v27, 32, cb);
    if ( (v5 & 0x80000000) == 0 )
    {
      v16 = CoTaskMemAlloc(HIDWORD(cb[0]));
      v26 = v16;
      if ( v16 )
      {
        v21 = HIDWORD(cb[0]);
        v17 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64, _DWORD *))(*(_QWORD *)v22 + 24LL))(
                v22,
                v27,
                32,
                v16);
        if ( v17 >= 0 )
        {
          if ( (*v16 & 0x202) == 0x202 )
          {
            *a3 = 11;
            a3[4] = -1;
            CoTaskMemFree(v16);
            if ( pv )
              CoTaskMemFree(pv);
            v5 = 0;
            goto LABEL_58;
          }
          v17 = -2147024809;
          v18 = 3921;
        }
        else
        {
          v18 = 3919;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)(unsigned int)v17,
          v21);
        CoTaskMemFree(v16);
        if ( pv )
          CoTaskMemFree(pv);
        v5 = v17;
LABEL_58:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
        return v5;
      }
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF47,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)0x8007000ELL,
        40);
LABEL_20:
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_58;
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF2E,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v14,
      (int)v20);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return v5;
}

```

## disassembly

```asm
0x180021edc  mov     [rsp-8+arg_10], rbx
0x180021ee1  mov     [rsp-8+arg_0], rcx
0x180021ee6  push    rbp
0x180021ee7  push    rsi
0x180021ee8  push    rdi
0x180021ee9  push    r14
0x180021eeb  push    r15
0x180021eed  lea     rbp, [rsp-37h]
0x180021ef2  sub     rsp, 0B0h
0x180021ef9  mov     r14, r8
0x180021efc  mov     rcx, rdx
0x180021eff  xor     r15d, r15d
0x180021f02  mov     [rbp+57h+var_68], r15d
0x180021f06  xorps   xmm0, xmm0
0x180021f09  movups  [rbp+57h+var_64], xmm0
0x180021f0d  movups  [rbp+57h+var_64+0Ch], xmm0
0x180021f11  mov     dword ptr [rbp+57h+arg_0], r15d
0x180021f15  mov     [rbp+57h+var_90], r15
0x180021f19  mov     [rbp+57h+var_80], r15
0x180021f1d  mov     [rbp+57h+var_88], r15
0x180021f21  mov     [rbp+57h+pv], r15
0x180021f25  mov     [rbp+57h+var_78], r15
0x180021f29  mov     rax, [rdx]
0x180021f2c  lea     r8, [rbp+57h+var_78]
0x180021f30  lea     rdx, _GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9
0x180021f37  mov     rax, [rax]
0x180021f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f3f  mov     ebx, eax
0x180021f41  test    eax, eax
0x180021f43  jns     loc_180021FCF
0x180021f49  mov     rcx, [rbp+5Fh]; this
0x180021f4d  mov     r9d, eax; char *
0x180021f50  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180021f57  mov     edx, 0F23h; void *
0x180021f5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021f61  nop
0x180021f62  mov     rcx, [rbp+57h+pv]; pv
0x180021f66  test    rcx, rcx
0x180021f69  jz      short loc_180021F72
0x180021f6b  call    cs:__imp_CoTaskMemFree
0x180021f71  nop
0x180021f72  mov     rcx, [rbp+57h+var_88]
0x180021f76  test    rcx, rcx
0x180021f79  jz      short loc_180021F88
0x180021f7b  mov     rax, [rcx]
0x180021f7e  mov     rax, [rax+10h]
0x180021f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f87  nop
0x180021f88  mov     rcx, [rbp+57h+var_80]
0x180021f8c  test    rcx, rcx
0x180021f8f  jz      short loc_180021F9E
0x180021f91  mov     rax, [rcx]
0x180021f94  mov     rax, [rax+10h]
0x180021f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f9d  nop
0x180021f9e  mov     rcx, [rbp+57h+var_90]
0x180021fa2  test    rcx, rcx
0x180021fa5  jz      short loc_180021FB4
0x180021fa7  mov     rax, [rcx]
0x180021faa  mov     rax, [rax+10h]
0x180021fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fb3  nop
0x180021fb4  mov     rcx, [rbp+57h+var_78]
0x180021fb8  test    rcx, rcx
0x180021fbb  jz      short loc_180021FCA
0x180021fbd  mov     rax, [rcx]
0x180021fc0  mov     rax, [rax+10h]
0x180021fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fc9  nop
0x180021fca  jmp     loc_18002244A
0x180021fcf  mov     rcx, [rbp+57h+var_78]
0x180021fd3  mov     rax, [rcx]
0x180021fd6  lea     rdx, [rbp+57h+arg_0]
0x180021fda  mov     rax, [rax+20h]
0x180021fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fe3  mov     ebx, eax
0x180021fe5  test    eax, eax
0x180021fe7  jns     loc_180022073
0x180021fed  mov     rcx, [rbp+5Fh]; this
0x180021ff1  mov     r9d, eax; char *
0x180021ff4  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180021ffb  mov     edx, 0F25h; void *
0x180022000  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022005  nop
0x180022006  mov     rcx, [rbp+57h+pv]; pv
0x18002200a  test    rcx, rcx
0x18002200d  jz      short loc_180022016
0x18002200f  call    cs:__imp_CoTaskMemFree
0x180022015  nop
0x180022016  mov     rcx, [rbp+57h+var_88]
0x18002201a  test    rcx, rcx
0x18002201d  jz      short loc_18002202C
0x18002201f  mov     rax, [rcx]
0x180022022  mov     rax, [rax+10h]
0x180022026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002202b  nop
0x18002202c  mov     rcx, [rbp+57h+var_80]
0x180022030  test    rcx, rcx
0x180022033  jz      short loc_180022042
0x180022035  mov     rax, [rcx]
0x180022038  mov     rax, [rax+10h]
0x18002203c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022041  nop
0x180022042  mov     rcx, [rbp+57h+var_90]
0x180022046  test    rcx, rcx
0x180022049  jz      short loc_180022058
0x18002204b  mov     rax, [rcx]
0x18002204e  mov     rax, [rax+10h]
0x180022052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022057  nop
0x180022058  mov     rcx, [rbp+57h+var_78]
0x18002205c  test    rcx, rcx
0x18002205f  jz      short loc_18002206E
0x180022061  mov     rax, [rcx]
0x180022064  mov     rax, [rax+10h]
0x180022068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002206d  nop
0x18002206e  jmp     loc_18002244A
0x180022073  mov     rbx, [rbp+57h+var_78]
0x180022077  mov     rax, [rbx]
0x18002207a  mov     rdi, [rax+60h]
0x18002207e  mov     rcx, [rbp+57h+var_80]
0x180022082  mov     [rbp+57h+var_80], r15
0x180022086  test    rcx, rcx
0x180022089  jz      short loc_180022098
0x18002208b  mov     rdx, [rcx]
0x18002208e  mov     rax, [rdx+10h]
0x180022092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022097  nop
0x180022098  lea     rdx, [rbp+57h+var_80]
0x18002209c  mov     rcx, rbx
0x18002209f  mov     rax, rdi
0x1800220a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220a7  mov     ebx, eax
0x1800220a9  test    eax, eax
0x1800220ab  jns     short loc_1800220B4
0x1800220ad  mov     edx, 0F28h
0x1800220b2  jmp     short loc_180022101
0x1800220b4  mov     rdi, [rbp+57h+var_80]
0x1800220b8  mov     rax, [rdi]
0x1800220bb  mov     rsi, [rax+40h]
0x1800220bf  mov     rbx, [rbp+57h+pv]
0x1800220c3  test    rbx, rbx
0x1800220c6  jz      short loc_1800220E3
0x1800220c8  lea     rcx, [rbp+57h+var_70]; this
0x1800220cc  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800220d1  mov     rcx, rbx; pv
0x1800220d4  call    cs:__imp_CoTaskMemFree
0x1800220da  lea     rcx, [rbp+57h+var_70]; this
0x1800220de  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800220e3  mov     [rbp+57h+pv], r15
0x1800220e7  lea     rdx, [rbp+57h+pv]
0x1800220eb  mov     rcx, rdi
0x1800220ee  mov     rax, rsi
0x1800220f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220f6  mov     ebx, eax
0x1800220f8  test    eax, eax
0x1800220fa  jns     short loc_18002212D
0x1800220fc  mov     edx, 0F2Bh; void *
0x180022101  mov     rcx, [rbp+5Fh]; this
0x180022105  mov     r9d, eax; char *
0x180022108  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002210f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022114  nop
0x180022115  mov     rcx, [rbp+57h+pv]; pv
0x180022119  test    rcx, rcx
0x18002211c  jz      loc_180022423
0x180022122  call    cs:__imp_CoTaskMemFree
0x180022128  jmp     loc_180022423
0x18002212d  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180022134  mov     rax, [r9]
0x180022137  mov     rbx, [rax+28h]
0x18002213b  mov     rcx, [rbp+57h+var_88]
0x18002213f  mov     [rbp+57h+var_88], r15
0x180022143  test    rcx, rcx
0x180022146  jz      short loc_18002215B
0x180022148  mov     rax, [rcx]
0x18002214b  mov     rax, [rax+10h]
0x18002214f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022154  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18002215b  lea     r8, [rbp+57h+var_88]
0x18002215f  mov     rdx, [rbp+57h+pv]
0x180022163  mov     rcx, r9
0x180022166  mov     rax, rbx
0x180022169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002216e  mov     ebx, eax
0x180022170  test    eax, eax
0x180022172  jns     loc_1800221FE
0x180022178  mov     rcx, [rbp+5Fh]; this
0x18002217c  mov     r9d, eax; char *
0x18002217f  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180022186  mov     edx, 0F2Eh; void *
0x18002218b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022190  nop
0x180022191  mov     rcx, [rbp+57h+pv]; pv
0x180022195  test    rcx, rcx
0x180022198  jz      short loc_1800221A1
0x18002219a  call    cs:__imp_CoTaskMemFree
0x1800221a0  nop
0x1800221a1  mov     rcx, [rbp+57h+var_88]
0x1800221a5  test    rcx, rcx
0x1800221a8  jz      short loc_1800221B7
0x1800221aa  mov     rax, [rcx]
0x1800221ad  mov     rax, [rax+10h]
0x1800221b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221b6  nop
0x1800221b7  mov     rcx, [rbp+57h+var_80]
0x1800221bb  test    rcx, rcx
0x1800221be  jz      short loc_1800221CD
0x1800221c0  mov     rax, [rcx]
0x1800221c3  mov     rax, [rax+10h]
0x1800221c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221cc  nop
0x1800221cd  mov     rcx, [rbp+57h+var_90]
0x1800221d1  test    rcx, rcx
0x1800221d4  jz      short loc_1800221E3
0x1800221d6  mov     rax, [rcx]
0x1800221d9  mov     rax, [rax+10h]
0x1800221dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221e2  nop
0x1800221e3  mov     rcx, [rbp+57h+var_78]
0x1800221e7  test    rcx, rcx
0x1800221ea  jz      short loc_1800221F9
0x1800221ec  mov     rax, [rcx]
0x1800221ef  mov     rax, [rax+10h]
0x1800221f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221f8  nop
0x1800221f9  jmp     loc_18002244A
0x1800221fe  mov     rbx, [rbp+57h+var_88]
0x180022202  mov     rax, [rbx]
0x180022205  mov     rdi, [rax+18h]
0x180022209  mov     rcx, [rbp+57h+var_90]
0x18002220d  mov     [rbp+57h+var_90], r15
0x180022211  test    rcx, rcx
0x180022214  jz      short loc_180022223
0x180022216  mov     rax, [rcx]
0x180022219  mov     rax, [rax+10h]
0x18002221d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022222  nop
0x180022223  lea     rax, [rbp+57h+var_90]
0x180022227  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18002222c  xor     r9d, r9d
0x18002222f  lea     esi, [r9+1]
0x180022233  mov     r8d, esi
0x180022236  lea     rdx, _GUID_28f54685_06fd_11d2_b27a_00a0c9223196
0x18002223d  mov     rcx, rbx
0x180022240  mov     rax, rdi
0x180022243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022248  mov     ebx, eax
0x18002224a  test    eax, eax
0x18002224c  jns     short loc_180022258
0x18002224e  mov     edx, 0F30h
0x180022253  jmp     loc_180022101
0x180022258  mov     [rbp+57h+var_4C], r15d
0x18002225c  mov     [rbp+57h+var_68], 0A3FB7B0Dh
0x180022263  movsd   xmm0, qword ptr cs:_GUID_a3fb7b0d_474e_4f51_a379_51282dd4fa8f.Data2
0x18002226b  movsd   qword ptr [rbp+57h+var_64], xmm0
0x180022270  mov     eax, dword ptr cs:_GUID_a3fb7b0d_474e_4f51_a379_51282dd4fa8f.Data4+4
0x180022276  mov     dword ptr [rbp+57h+var_64+8], eax
0x180022279  mov     dword ptr [rbp+57h+var_64+0Ch], esi
0x18002227c  mov     [rbp+57h+var_54], 200h
0x180022283  movzx   eax, word ptr [rbp+57h+arg_0]
0x180022287  mov     [rbp+57h+var_50], eax
0x18002228a  xorps   xmm0, xmm0
0x18002228d  xor     eax, eax
0x18002228f  movups  xmmword ptr [rbp+57h+cb], xmm0
0x180022293  movups  [rbp+57h+var_38], xmm0
0x180022297  mov     [rbp+57h+var_28], rax
0x18002229b  mov     [rbp+57h+arg_8], r15d
0x18002229f  mov     rcx, [rbp+57h+var_90]
0x1800222a3  mov     rax, [rcx]
0x1800222a6  lea     rdx, [rbp+57h+arg_8]
0x1800222aa  mov     [rsp+0D0h+var_A8], rdx
0x1800222af  mov     [rsp+0D0h+var_B0], 28h ; '('; int
0x1800222b7  lea     r9, [rbp+57h+cb]
0x1800222bb  mov     edi, 20h ; ' '
0x1800222c0  mov     r8d, edi
0x1800222c3  lea     rdx, [rbp+57h+var_68]
0x1800222c7  mov     rax, [rax+18h]
0x1800222cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222d0  mov     ebx, eax
0x1800222d2  test    eax, eax
0x1800222d4  jns     short loc_180022343
0x1800222d6  mov     rcx, [rbp+57h+pv]; pv
0x1800222da  test    rcx, rcx
0x1800222dd  jz      short loc_1800222E6
0x1800222df  call    cs:__imp_CoTaskMemFree
0x1800222e5  nop
0x1800222e6  mov     rcx, [rbp+57h+var_88]
0x1800222ea  test    rcx, rcx
0x1800222ed  jz      short loc_1800222FC
0x1800222ef  mov     rax, [rcx]
0x1800222f2  mov     rax, [rax+10h]
0x1800222f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222fb  nop
0x1800222fc  mov     rcx, [rbp+57h+var_80]
0x180022300  test    rcx, rcx
0x180022303  jz      short loc_180022312
0x180022305  mov     rax, [rcx]
0x180022308  mov     rax, [rax+10h]
  ... truncated ...
```
