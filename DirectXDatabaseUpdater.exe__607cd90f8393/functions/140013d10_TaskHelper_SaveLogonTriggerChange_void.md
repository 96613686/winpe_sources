# TaskHelper::SaveLogonTriggerChange(void)

- ea: `0x140013d10`
- end: `0x140013f56`
- name: `?SaveLogonTriggerChange@TaskHelper@@QEAAJXZ`
- size: `582`
- prototype: `__int64 __fastcall(TaskHelper *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000f2a4`
- `0x1400100e0`
- `0x140010ac0`

## callees

- `0x140005cac`
- `0x14000a4bc`
- `0x14001364c`
- `0x140013d10`
- `0x14001a010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x140013e43`
- `OLEAUT32!__imp_VariantInit` at `0x140013e5d`
- `OLEAUT32!__imp_VariantInit` at `0x140013e74`
- `OLEAUT32!__imp_VariantInit` at `0x140013e43`
- `OLEAUT32!__imp_VariantInit` at `0x140013e5d`
- `OLEAUT32!__imp_VariantInit` at `0x140013e74`
- `OLEAUT32!__imp_VariantClear` at `0x140013eea`
- `OLEAUT32!__imp_VariantClear` at `0x140013ef6`
- `OLEAUT32!__imp_VariantClear` at `0x140013f01`
- `OLEAUT32!__imp_VariantClear` at `0x140013eea`
- `OLEAUT32!__imp_VariantClear` at `0x140013ef6`
- `OLEAUT32!__imp_VariantClear` at `0x140013f01`

## string_xrefs

- `0x140013d90`: `onecore\windows\directx\database\updater\exe\taskschedulerhelper.cpp`
- `0x140013dd5`: `onecore\windows\directx\database\updater\exe\taskschedulerhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall TaskHelper::SaveLogonTriggerChange(TaskHelper *this)
{
  __int64 *v2; // rsi
  __int64 *v3; // rcx
  __int64 v4; // rax
  int v5; // eax
  int v6; // ebx
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r14
  __int64 (__fastcall *v12)(__int64, __int64, _QWORD, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *); // r15
  __int64 v13; // rcx
  __int128 v14; // xmm8
  IRecordInfo *pRecInfo; // xmm9_8
  int v16; // ebx
  __int128 v17; // xmm6
  __int64 v18; // xmm7_8
  int v20; // [rsp+28h] [rbp-E0h]
  VARIANTARG v21; // [rsp+50h] [rbp-B8h] BYREF
  VARIANTARG v22; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+80h] [rbp-88h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-80h] BYREF
  __int128 v25; // [rsp+A8h] [rbp-60h] BYREF
  IRecordInfo *v26; // [rsp+B8h] [rbp-50h]
  __int128 v27; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v28; // [rsp+D8h] [rbp-30h]
  __int128 v29; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v30; // [rsp+F8h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+170h] [rbp+68h]
  int v32; // [rsp+178h] [rbp+70h] BYREF
  __int64 v33; // [rsp+180h] [rbp+78h] BYREF
  __int64 v34; // [rsp+188h] [rbp+80h] BYREF

  if ( *((_QWORD *)this + 3) && *((_BYTE *)this + 40) )
  {
    v34 = 0;
    v2 = (__int64 *)((char *)this + 16);
    v3 = (__int64 *)*((_QWORD *)this + 2);
    v4 = *v3;
    v34 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v4 + 56))(v3, &v34);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D,
        (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\taskschedulerhelper.cpp",
        (const char *)(unsigned int)v5,
        v20);
LABEL_15:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
      return (unsigned int)v6;
    }
    v33 = 0;
    v7 = (__int64 *)*((_QWORD *)this + 3);
    v8 = *v7;
    v33 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v8 + 120))(v7, &v33);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v32 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v33 + 104LL))(v33, &v32);
      v6 = v9;
      if ( v9 >= 0 )
      {
        v11 = *((_QWORD *)this + 1);
        v12 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64, __int128 *, __int128 *, int, __int128 *, __int64 *))(*(_QWORD *)v11 + 136LL);
        v13 = *v2;
        *v2 = 0;
        if ( v13 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        VariantInit(&pvarg);
        v14 = *(_OWORD *)&pvarg.vt;
        pRecInfo = pvarg.pRecInfo;
        v16 = v32;
        VariantInit((VARIANTARG *)&v22.decVal.8);
        v17 = *(_OWORD *)&v22.decVal.Lo32;
        v18 = v23;
        VariantInit((VARIANTARG *)&v21.decVal.8);
        v25 = v14;
        v26 = pRecInfo;
        v27 = v17;
        v28 = v18;
        v29 = *(_OWORD *)&v21.decVal.Lo32;
        v30 = *(_QWORD *)&v22.vt;
        v6 = v12(v11, v34, *((_QWORD *)this + 3), 4, &v29, &v27, v16, &v25, v2);
        VariantClear((VARIANTARG *)&v21.decVal.8);
        VariantClear((VARIANTARG *)&v22.decVal.8);
        VariantClear(&pvarg);
        if ( v6 >= 0 )
          *((_BYTE *)this + 40) = 0;
        goto LABEL_14;
      }
      v10 = 83;
    }
    else
    {
      v10 = 80;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\windows\\directx\\database\\updater\\exe\\taskschedulerhelper.cpp",
      (const char *)(unsigned int)v9,
      v20);
LABEL_14:
    wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(&v33);
    goto LABEL_15;
  }
  return 0;
}

```

## disassembly

```asm
0x140013d10  mov     rax, rsp
0x140013d13  mov     [rax+20h], rbx
0x140013d17  push    rbp
0x140013d18  push    rsi
0x140013d19  push    rdi
0x140013d1a  push    r14
0x140013d1c  push    r15
0x140013d1e  lea     rbp, [rax-68h]
0x140013d22  sub     rsp, 140h
0x140013d29  movaps  xmmword ptr [rax-38h], xmm6
0x140013d2d  movaps  xmmword ptr [rax-48h], xmm7
0x140013d31  movaps  xmmword ptr [rax-58h], xmm8
0x140013d36  movaps  xmmword ptr [rax-68h], xmm9
0x140013d3b  mov     rdi, rcx
0x140013d3e  cmp     qword ptr [rcx+18h], 0
0x140013d43  jz      loc_140013F29
0x140013d49  cmp     byte ptr [rcx+28h], 0
0x140013d4d  jz      loc_140013F29
0x140013d53  mov     [rbp+60h+arg_10], 0
0x140013d5e  lea     rsi, [rcx+10h]
0x140013d62  mov     rcx, [rsi]
0x140013d65  mov     rax, [rcx]
0x140013d68  mov     [rbp+60h+arg_10], 0
0x140013d73  lea     rdx, [rbp+60h+arg_10]
0x140013d7a  mov     rax, [rax+38h]
0x140013d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013d83  mov     ebx, eax
0x140013d85  test    eax, eax
0x140013d87  jns     short loc_140013DA6
0x140013d89  mov     rcx, [rbp+68h]; this
0x140013d8d  mov     r9d, eax; char *
0x140013d90  lea     r8, aOnecoreWindows_0; "onecore\\windows\\directx\\database\\up"...
0x140013d97  mov     edx, 4Dh ; 'M'; void *
0x140013d9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013da1  jmp     loc_140013F19
0x140013da6  mov     [rbp+60h+arg_8], 0
0x140013dae  mov     rcx, [rdi+18h]
0x140013db2  mov     rax, [rcx]
0x140013db5  mov     [rbp+60h+arg_8], 0
0x140013dbd  lea     rdx, [rbp+60h+arg_8]
0x140013dc1  mov     rax, [rax+78h]
0x140013dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013dca  mov     ebx, eax
0x140013dcc  test    eax, eax
0x140013dce  jns     short loc_140013DED
0x140013dd0  mov     edx, 50h ; 'P'; void *
0x140013dd5  lea     r8, aOnecoreWindows_0; "onecore\\windows\\directx\\database\\up"...
0x140013ddc  mov     r9d, eax; char *
0x140013ddf  mov     rcx, [rbp+68h]; this
0x140013de3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140013de8  jmp     loc_140013F0F
0x140013ded  mov     [rbp+60h+arg_0], 0
0x140013df4  mov     rcx, [rbp+60h+arg_8]
0x140013df8  mov     rax, [rcx]
0x140013dfb  lea     rdx, [rbp+60h+arg_0]
0x140013dff  mov     rax, [rax+68h]
0x140013e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013e08  mov     ebx, eax
0x140013e0a  test    eax, eax
0x140013e0c  jns     short loc_140013E15
0x140013e0e  mov     edx, 53h ; 'S'
0x140013e13  jmp     short loc_140013DD5
0x140013e15  mov     r14, [rdi+8]
0x140013e19  mov     rax, [r14]
0x140013e1c  mov     r15, [rax+88h]
0x140013e23  mov     rcx, [rsi]
0x140013e26  mov     qword ptr [rsi], 0
0x140013e2d  test    rcx, rcx
0x140013e30  jz      short loc_140013E3F
0x140013e32  mov     rax, [rcx]
0x140013e35  mov     rax, [rax+10h]
0x140013e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013e3e  nop
0x140013e3f  lea     rcx, [rbp+60h+pvarg]; pvarg
0x140013e43  call    cs:__imp_VariantInit
0x140013e49  nop
0x140013e4a  movups  xmm8, xmmword ptr [rbp+60h+pvarg]
0x140013e4f  movsd   xmm9, qword ptr [rbp+60h+pvarg+10h]
0x140013e55  mov     ebx, [rbp+60h+arg_0]
0x140013e58  lea     rcx, [rsp+160h+var_100+8]; pvarg
0x140013e5d  call    cs:__imp_VariantInit
0x140013e63  nop
0x140013e64  movups  xmm6, xmmword ptr [rsp+160h+var_100+8]
0x140013e69  movsd   xmm7, [rsp+160h+var_E8]
0x140013e6f  lea     rcx, [rsp+160h+var_118+8]; pvarg
0x140013e74  call    cs:__imp_VariantInit
0x140013e7a  nop
0x140013e7b  movups  xmm0, xmmword ptr [rsp+160h+var_118+8]
0x140013e80  movsd   xmm1, qword ptr [rsp+160h+var_100]
0x140013e86  movaps  [rbp+60h+var_C0], xmm8
0x140013e8b  movsd   [rbp+60h+var_B0], xmm9
0x140013e91  movaps  [rbp+60h+var_A0], xmm6
0x140013e95  movsd   [rbp+60h+var_90], xmm7
0x140013e9a  movaps  [rbp+60h+var_80], xmm0
0x140013e9e  movsd   [rbp+60h+var_70], xmm1
0x140013ea3  mov     [rsp+160h+var_120], rsi
0x140013ea8  lea     rax, [rbp+60h+var_C0]
0x140013eac  mov     [rsp+160h+var_128], rax
0x140013eb1  mov     dword ptr [rsp+160h+var_130], ebx
0x140013eb5  lea     rax, [rbp+60h+var_A0]
0x140013eb9  mov     qword ptr [rsp+160h+var_138], rax
0x140013ebe  lea     rax, [rbp+60h+var_80]
0x140013ec2  mov     [rsp+160h+var_140], rax
0x140013ec7  mov     r9d, 4
0x140013ecd  mov     r8, [rdi+18h]
0x140013ed1  mov     rdx, [rbp+60h+arg_10]
0x140013ed8  mov     rcx, r14
0x140013edb  mov     rax, r15
0x140013ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013ee3  mov     ebx, eax
0x140013ee5  lea     rcx, [rsp+160h+var_118+8]; pvarg
0x140013eea  call    cs:__imp_VariantClear
0x140013ef0  nop
0x140013ef1  lea     rcx, [rsp+160h+var_100+8]; pvarg
0x140013ef6  call    cs:__imp_VariantClear
0x140013efc  nop
0x140013efd  lea     rcx, [rbp+60h+pvarg]; pvarg
0x140013f01  call    cs:__imp_VariantClear
0x140013f07  test    ebx, ebx
0x140013f09  js      short loc_140013F0F
0x140013f0b  mov     byte ptr [rdi+28h], 0
0x140013f0f  lea     rcx, [rbp+60h+arg_8]
0x140013f13  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140013f18  nop
0x140013f19  lea     rcx, [rbp+60h+arg_10]
0x140013f20  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140013f25  mov     eax, ebx
0x140013f27  jmp     short loc_140013F2B
0x140013f29  xor     eax, eax
0x140013f2b  lea     r11, [rsp+160h+var_20]
0x140013f33  mov     rbx, [r11+48h]
0x140013f37  movaps  xmm6, xmmword ptr [r11-10h]
0x140013f3c  movaps  xmm7, xmmword ptr [r11-20h]
0x140013f41  movaps  xmm8, xmmword ptr [r11-30h]
0x140013f46  movaps  xmm9, xmmword ptr [r11-40h]
0x140013f4b  mov     rsp, r11
0x140013f4e  pop     r15
0x140013f50  pop     r14
0x140013f52  pop     rdi
0x140013f53  pop     rsi
0x140013f54  pop     rbp
0x140013f55  retn
```
