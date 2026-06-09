# Rdp::Avenc::Hevc::CMFApi::CreateHWEncoderByLuid(_LUID,__MIDL___MIDL_itf_mfobjects_0000_0009_0003 const *,IMFTransform * *)

- ea: `0x180027108`
- end: `0x1800273e1`
- name: `?CreateHWEncoderByLuid@CMFApi@Hevc@Avenc@Rdp@@QEAAXU_LUID@@PEBU__MIDL___MIDL_itf_mfobjects_0000_0009_0003@@PEAPEAUIMFTransform@@@Z`
- size: `729`
- prototype: `void __fastcall(Rdp::Avenc::Hevc::CMFApi *__hidden this, struct _LUID, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, struct IMFTransform **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003131c`

## callees

- `0x18000e848`
- `0x1800146bc`
- `0x180018d88`
- `0x180027108`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027368`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027368`
- `MFPlat!MFCreateAttributes` at `0x180027198`
- `MFPlat!MFCreateAttributes` at `0x180027198`

## string_xrefs

- `0x1800271a8`: `MFCreateAttributes failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Rdp::Avenc::Hevc::CMFApi::CreateHWEncoderByLuid(
        Rdp::Avenc::Hevc::CMFApi *this,
        struct _LUID a2,
        const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *a3,
        struct IMFTransform **a4)
{
  HRESULT v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // rbx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, GUID *, struct IMFTransform **); // rsi
  struct IMFTransform *v13; // rcx
  int v14; // edi
  __int64 v15; // rbx
  struct IMFTransform *v16; // rax
  int v17; // [rsp+20h] [rbp-60h]
  char *v18; // [rsp+28h] [rbp-58h]
  char *v19; // [rsp+28h] [rbp-58h]
  const char *v20; // [rsp+30h] [rbp-50h]
  struct IMFTransform *v21; // [rsp+40h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-38h] BYREF
  struct _LUID v23; // [rsp+50h] [rbp-30h] BYREF
  GUID v24; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  unsigned int v26; // [rsp+B0h] [rbp+30h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+B8h] [rbp+38h] BYREF

  v21 = 0;
  pv = 0;
  v26 = 0;
  LOBYTE(v17) = *((_QWORD *)this + 6) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x8E,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\cmfapi.cpp",
    (const char *)0x80070057LL,
    v17,
    (bool)"MFT Enum2 not supported in the host device",
    v20);
  v23 = a2;
  ppMFAttributes = 0;
  v8 = MFCreateAttributes(&ppMFAttributes, 1u);
  if ( v8 >= 0 )
  {
    v8 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, struct _LUID *, __int64))ppMFAttributes->lpVtbl->SetBlob)(
           ppMFAttributes,
           MFT_ENUM_ADAPTER_LUID,
           &v23,
           8);
    if ( v8 >= 0 )
    {
      v24 = MFT_CATEGORY_VIDEO_ENCODER;
      v8 = (*((__int64 (__fastcall **)(GUID *, __int64, _QWORD, const struct __MIDL___MIDL_itf_mfobjects_0000_0009_0003 *, IMFAttributes *, LPVOID *, unsigned int *))this
            + 6))(
             &v24,
             87,
             0,
             a3,
             ppMFAttributes,
             &pv,
             &v26);
      if ( v8 >= 0 )
      {
        if ( ppMFAttributes )
          ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
        v8 = 0;
      }
      else
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xF3,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\cmfapi.cpp",
          (const char *)(unsigned int)v8,
          (int)"CMFTEnum2 failed",
          v19);
        if ( ppMFAttributes )
          ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
      }
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0xEF,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\cmfapi.cpp",
        (const char *)(unsigned int)v8,
        (int)"spMFTAttributes->SetBlob failed",
        v18);
      if ( ppMFAttributes )
        ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\cmfapi.cpp",
      (const char *)(unsigned int)v8,
      (int)"MFCreateAttributes failed",
      v18);
    if ( ppMFAttributes )
      ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
  }
  v9 = v26;
  if ( v8 >= 0 && (v10 = 0, v26) )
  {
    while ( 1 )
    {
      v11 = *((_QWORD *)pv + v10);
      v12 = *(__int64 (__fastcall **)(__int64, GUID *, struct IMFTransform **))(*(_QWORD *)v11 + 264LL);
      v13 = v21;
      v21 = 0;
      if ( v13 )
        ((void (__fastcall *)(struct IMFTransform *))v13->lpVtbl->Release)(v13);
      v14 = v12(v11, &GUID_bf94c121_5b05_4e6f_8000_ba598961414d, &v21);
      if ( v14 >= 0 )
        break;
      v10 = (unsigned int)(v10 + 1);
      v9 = v26;
      if ( (unsigned int)v10 >= v26 )
        goto LABEL_22;
    }
    v16 = v21;
    v21 = 0;
    *a4 = v16;
    v9 = v26;
  }
  else
  {
LABEL_22:
    v14 = -2147024463;
  }
  if ( v9 )
  {
    v15 = 0;
    do
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)pv + v15) + 16LL))(*((_QWORD *)pv + v15));
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < v26 );
    CoTaskMemFree(pv);
    pv = 0;
  }
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xB9,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\cmfapi.cpp",
    (const char *)(unsigned int)v14,
    (int)"No such device",
    v19);
  if ( v21 )
    ((void (__fastcall *)(struct IMFTransform *))v21->lpVtbl->Release)(v21);
}

```

## disassembly

```asm
0x180027108  mov     [rsp-28h+arg_10], rbx
0x18002710d  push    rbp
0x18002710e  push    rsi
0x18002710f  push    rdi
0x180027110  push    r12
0x180027112  push    r14
0x180027114  mov     rbp, rsp
0x180027117  sub     rsp, 80h
0x18002711e  movaps  [rsp+80h+var_10], xmm6
0x180027123  mov     r14, r9
0x180027126  mov     rsi, r8
0x180027129  mov     rbx, rdx
0x18002712c  mov     rdi, rcx
0x18002712f  mov     [rbp+var_40], 0
0x180027137  mov     [rbp+pv], 0
0x18002713f  mov     [rbp+arg_0], 0
0x180027146  cmp     qword ptr [rcx+30h], 0
0x18002714b  setz    al
0x18002714e  mov     rcx, [rbp+28h]; this
0x180027152  lea     rdx, aMftEnum2NotSup; "MFT Enum2 not supported in the host dev"...
0x180027159  mov     [rsp+80h+var_58], rdx; char *
0x18002715e  mov     byte ptr [rsp+80h+var_60], al; int
0x180027162  mov     r9d, 80070057h; char *
0x180027168  lea     r12, aOnecoreuapTerm_17; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002716f  mov     r8, r12; unsigned int
0x180027172  mov     edx, 8Eh; void *
0x180027177  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18002717c  mov     [rbp+var_30], rbx
0x180027180  movups  xmm6, xmmword ptr cs:MFT_CATEGORY_VIDEO_ENCODER.Data1
0x180027187  mov     [rbp+ppMFAttributes], 0
0x18002718f  mov     edx, 1; cInitialSize
0x180027194  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x180027198  call    cs:__imp_MFCreateAttributes
0x18002719e  mov     ebx, eax
0x1800271a0  test    eax, eax
0x1800271a2  jns     short loc_1800271E0
0x1800271a4  mov     rcx, [rbp+28h]; this
0x1800271a8  lea     rax, aMfcreateattrib_1; "MFCreateAttributes failed"
0x1800271af  mov     qword ptr [rsp+80h+var_60], rax; int
0x1800271b4  mov     r9d, ebx; char *
0x1800271b7  mov     r8, r12; unsigned int
0x1800271ba  mov     edx, 0ECh; void *
0x1800271bf  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800271c4  nop
0x1800271c5  mov     rcx, [rbp+ppMFAttributes]
0x1800271c9  test    rcx, rcx
0x1800271cc  jz      short loc_1800271DB
0x1800271ce  mov     rax, [rcx]
0x1800271d1  mov     rax, [rax+10h]
0x1800271d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271da  nop
0x1800271db  jmp     loc_1800272D4
0x1800271e0  mov     rcx, [rbp+ppMFAttributes]
0x1800271e4  mov     rax, [rcx]
0x1800271e7  mov     r9d, 8
0x1800271ed  lea     r8, [rbp+var_30]
0x1800271f1  lea     rdx, MFT_ENUM_ADAPTER_LUID
0x1800271f8  mov     rax, [rax+0D0h]
0x1800271ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027204  mov     ebx, eax
0x180027206  test    eax, eax
0x180027208  jns     short loc_180027246
0x18002720a  mov     rcx, [rbp+28h]; this
0x18002720e  lea     rax, aSpmftattribute; "spMFTAttributes->SetBlob failed"
0x180027215  mov     qword ptr [rsp+80h+var_60], rax; int
0x18002721a  mov     r9d, ebx; char *
0x18002721d  mov     r8, r12; unsigned int
0x180027220  mov     edx, 0EFh; void *
0x180027225  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002722a  nop
0x18002722b  mov     rcx, [rbp+ppMFAttributes]
0x18002722f  test    rcx, rcx
0x180027232  jz      short loc_180027241
0x180027234  mov     rax, [rcx]
0x180027237  mov     rax, [rax+10h]
0x18002723b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027240  nop
0x180027241  jmp     loc_1800272D4
0x180027246  mov     rcx, [rbp+ppMFAttributes]
0x18002724a  movdqa  [rbp+var_20], xmm6
0x18002724f  lea     rax, [rbp+arg_0]
0x180027253  mov     [rsp+80h+var_50], rax
0x180027258  lea     rax, [rbp+pv]
0x18002725c  mov     [rsp+80h+var_58], rax; char *
0x180027261  mov     qword ptr [rsp+80h+var_60], rcx
0x180027266  mov     r9, rsi
0x180027269  xor     r8d, r8d
0x18002726c  lea     edx, [r8+57h]
0x180027270  lea     rcx, [rbp+var_20]
0x180027274  mov     rax, [rdi+30h]
0x180027278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002727d  mov     ebx, eax
0x18002727f  test    eax, eax
0x180027281  jns     short loc_1800272BC
0x180027283  mov     rcx, [rbp+28h]; this
0x180027287  lea     rax, aCmftenum2Faile; "CMFTEnum2 failed"
0x18002728e  mov     qword ptr [rsp+80h+var_60], rax; int
0x180027293  mov     r9d, ebx; char *
0x180027296  mov     r8, r12; unsigned int
0x180027299  mov     edx, 0F3h; void *
0x18002729e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800272a3  nop
0x1800272a4  mov     rcx, [rbp+ppMFAttributes]
0x1800272a8  test    rcx, rcx
0x1800272ab  jz      short loc_1800272BA
0x1800272ad  mov     rax, [rcx]
0x1800272b0  mov     rax, [rax+10h]
0x1800272b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272b9  nop
0x1800272ba  jmp     short loc_1800272D4
0x1800272bc  mov     rcx, [rbp+ppMFAttributes]
0x1800272c0  test    rcx, rcx
0x1800272c3  jz      short loc_1800272D2
0x1800272c5  mov     rax, [rcx]
0x1800272c8  mov     rax, [rax+10h]
0x1800272cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272d1  nop
0x1800272d2  xor     ebx, ebx
0x1800272d4  mov     eax, [rbp+arg_0]
0x1800272d7  test    ebx, ebx
0x1800272d9  js      short loc_18002733A
0x1800272db  xor     ebx, ebx
0x1800272dd  test    eax, eax
0x1800272df  jz      short loc_18002733A
0x1800272e1  mov     rax, [rbp+pv]
0x1800272e5  mov     rdi, [rax+rbx*8]
0x1800272e9  mov     rax, [rdi]
0x1800272ec  mov     rsi, [rax+108h]
0x1800272f3  mov     rcx, [rbp+var_40]
0x1800272f7  mov     [rbp+var_40], 0
0x1800272ff  test    rcx, rcx
0x180027302  jz      short loc_180027311
0x180027304  mov     rdx, [rcx]
0x180027307  mov     rax, [rdx+10h]
0x18002730b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027310  nop
0x180027311  lea     r8, [rbp+var_40]
0x180027315  lea     rdx, _GUID_bf94c121_5b05_4e6f_8000_ba598961414d
0x18002731c  mov     rcx, rdi
0x18002731f  mov     rax, rsi
0x180027322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027327  mov     edi, eax
0x180027329  test    eax, eax
0x18002732b  jns     loc_1800273C9
0x180027331  inc     ebx
0x180027333  mov     eax, [rbp+arg_0]
0x180027336  cmp     ebx, eax
0x180027338  jb      short loc_1800272E1
0x18002733a  mov     edi, 800701B1h
0x18002733f  test    eax, eax
0x180027341  jz      short loc_180027376
0x180027343  xor     ebx, ebx
0x180027345  test    eax, eax
0x180027347  jz      short loc_180027364
0x180027349  mov     rax, [rbp+pv]
0x18002734d  mov     rcx, [rax+rbx*8]
0x180027351  mov     rax, [rcx]
0x180027354  mov     rax, [rax+10h]
0x180027358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002735d  inc     ebx
0x18002735f  cmp     ebx, [rbp+arg_0]
0x180027362  jb      short loc_180027349
0x180027364  mov     rcx, [rbp+pv]; pv
0x180027368  call    cs:__imp_CoTaskMemFree
0x18002736e  mov     [rbp+pv], 0
0x180027376  mov     rcx, [rbp+28h]; this
0x18002737a  lea     rax, aNoSuchDevice_0; "No such device"
0x180027381  mov     qword ptr [rsp+80h+var_60], rax; int
0x180027386  mov     r9d, edi; char *
0x180027389  mov     r8, r12; unsigned int
0x18002738c  mov     edx, 0B9h; void *
0x180027391  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180027396  nop
0x180027397  mov     rcx, [rbp+var_40]
0x18002739b  test    rcx, rcx
0x18002739e  jz      short loc_1800273AD
0x1800273a0  mov     rax, [rcx]
0x1800273a3  mov     rax, [rax+10h]
0x1800273a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273ac  nop
0x1800273ad  mov     rbx, [rsp+80h+arg_10]
0x1800273b5  movaps  xmm6, [rsp+80h+var_10]
0x1800273ba  add     rsp, 80h
0x1800273c1  pop     r14
0x1800273c3  pop     r12
0x1800273c5  pop     rdi
0x1800273c6  pop     rsi
0x1800273c7  pop     rbp
0x1800273c8  retn
0x1800273c9  mov     rax, [rbp+var_40]
0x1800273cd  mov     [rbp+var_40], 0
0x1800273d5  mov     [r14], rax
0x1800273d8  mov     eax, [rbp+arg_0]
0x1800273db  jmp     loc_18002733F
```
