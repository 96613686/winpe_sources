# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x180017e64`
- end: `0x1800180e2`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `638`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800177b4`

## callees

- `0x180011fc0`
- `0x180012a28`
- `0x180017e64`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180018038`
- `OLEAUT32!__imp_SysFreeString` at `0x18001808d`
- `OLEAUT32!__imp_SysFreeString` at `0x180018038`
- `OLEAUT32!__imp_SysFreeString` at `0x18001808d`
- `OLEAUT32!__imp_SysStringLen` at `0x18001804b`
- `OLEAUT32!__imp_SysStringLen` at `0x18001804b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rdi
  ATL::CComTypeInfoHolder *v3; // r15
  ATL::CComTypeInfoHolder *v4; // r13
  OLECHAR *v5; // rsi
  unsigned __int64 v6; // rcx
  int *v7; // r14
  __int64 v8; // r12
  __int64 v9; // rax
  bool v10; // cf
  unsigned __int64 v11; // rax
  _QWORD *v12; // rax
  unsigned int v14; // r12d
  _DWORD *v15; // r14
  BSTR v16; // r13
  OLECHAR *v17; // rcx
  _DWORD *v18; // [rsp+40h] [rbp-58h]
  int *v20; // [rsp+50h] [rbp-48h]
  struct ITypeInfo *v22; // [rsp+A8h] [rbp+10h] BYREF
  BSTR pbstr; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v24; // [rsp+B8h] [rbp+20h] BYREF

  v22 = a2;
  v2 = a2;
  v3 = this;
  v4 = this;
  v24 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v24) >= 0 )
  {
    v5 = 0;
    pbstr = 0;
    v6 = *(unsigned __int16 *)(v24 + 48);
    v7 = (int *)((char *)v4 + 48);
    v20 = (int *)((char *)v4 + 48);
    *((_DWORD *)v4 + 12) = v6;
    *((_QWORD *)v4 + 5) = 0;
    v18 = (_DWORD *)((char *)v4 + 48);
    if ( (_WORD)v6 )
    {
      v8 = (unsigned int)v6;
      v9 = 16 * v6;
      if ( !is_mul_ok(v6, 0x10u) )
        v9 = -1;
      v10 = __CFADD__(v9, 8);
      v11 = v9 + 8;
      if ( v10 )
        v11 = -1;
      try
      {
        v12 = operator new[](v11);
        if ( v12 )
        {
          *v12 = v8;
          v5 = (OLECHAR *)(v12 + 1);
          `eh vector constructor iterator'(
            v12 + 1,
            0x10u,
            (unsigned int)v8,
            (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
            (void (*)(void *))ATL::CComBSTR::~CComBSTR);
        }
        else
        {
          v5 = 0;
        }
        pbstr = v5;
      }
      catch ( ... )
      {
        v3 = this;
        v2 = v22;
        v5 = pbstr;
        v4 = this;
        v7 = v20;
      }
      if ( !v5 )
      {
        ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v24);
        return 2147942414LL;
      }
      v18 = (_DWORD *)((char *)v4 + 48);
    }
    v14 = 0;
    if ( *v7 > 0 )
    {
      v15 = v5 + 6;
      do
      {
        v22 = 0;
        *(_QWORD *)(v15 - 1) = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v2->lpVtbl->GetFuncDesc)(
               v2,
               v14,
               &v22) >= 0 )
        {
          pbstr = 0;
          if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v2->lpVtbl->GetDocumentation)(
                 v2,
                 LODWORD(v22->lpVtbl),
                 &pbstr,
                 0,
                 0,
                 0) >= 0 )
          {
            v16 = pbstr;
            pbstr = 0;
            v17 = *(OLECHAR **)(v15 - 3);
            if ( v17 != v16 )
            {
              SysFreeString(v17);
              *(_QWORD *)(v15 - 3) = v16;
              v17 = v16;
            }
            *(v15 - 1) = SysStringLen(v17);
            *v15 = v22->lpVtbl;
          }
          ((void (__fastcall *)(struct ITypeInfo *))v2->lpVtbl->ReleaseFuncDesc)(v2);
          SysFreeString(pbstr);
        }
        ++v14;
        v15 += 4;
      }
      while ( (signed int)v14 < *v18 );
      v3 = this;
    }
    *((_QWORD *)v3 + 5) = v5;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v24);
  }
  return 0;
}

```

## disassembly

```asm
0x180017e64  mov     r11, rsp
0x180017e67  mov     [r11+10h], rdx
0x180017e6b  mov     [r11+8], rcx
0x180017e6f  push    rbx
0x180017e70  push    rsi
0x180017e71  push    rdi
0x180017e72  push    r12
0x180017e74  push    r13
0x180017e76  push    r14
0x180017e78  push    r15
0x180017e7a  sub     rsp, 60h
0x180017e7e  mov     qword ptr [r11-40h], 0FFFFFFFFFFFFFFFEh
0x180017e86  mov     rdi, rdx
0x180017e89  mov     r15, rcx
0x180017e8c  mov     r13, rcx
0x180017e8f  mov     [rsp+98h+var_50], rcx
0x180017e94  xor     ebx, ebx
0x180017e96  mov     [r11+20h], rbx
0x180017e9a  mov     rax, [rdx]
0x180017e9d  lea     rdx, [r11+20h]
0x180017ea1  mov     rcx, rdi
0x180017ea4  mov     rax, [rax+18h]
0x180017ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ead  test    eax, eax
0x180017eaf  js      loc_1800180CF
0x180017eb5  mov     esi, ebx
0x180017eb7  mov     [rsp+98h+pbstr], rbx
0x180017ebf  mov     rax, [rsp+98h+arg_18]
0x180017ec7  movzx   ecx, word ptr [rax+30h]
0x180017ecb  lea     r14, [r13+30h]
0x180017ecf  mov     [rsp+98h+var_48], r14
0x180017ed4  mov     [r14], ecx
0x180017ed7  mov     [r13+28h], rbx
0x180017edb  mov     [rsp+98h+var_58], r14
0x180017ee0  test    cx, cx
0x180017ee3  jz      loc_180017FA1
0x180017ee9  mov     r12d, ecx
0x180017eec  lea     eax, [rbx+10h]
0x180017eef  mul     rcx
0x180017ef2  lea     rcx, [rbx-1]
0x180017ef6  cmovo   rax, rcx
0x180017efa  add     rax, 8
0x180017efe  cmovb   rax, rcx
0x180017f02  mov     rcx, rax; unsigned __int64
0x180017f05  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180017f0a  mov     [rsp+98h+var_58], rax
0x180017f0f  test    rax, rax
0x180017f12  jz      short loc_180017F3E
0x180017f14  mov     [rax], r12
0x180017f17  lea     rsi, [rax+8]
0x180017f1b  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x180017f22  mov     [rsp+98h+var_78], rax; void (*)(void *)
0x180017f27  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x180017f2e  mov     r8d, r12d; unsigned __int64
0x180017f31  lea     edx, [rbx+10h]; unsigned __int64
0x180017f34  mov     rcx, rsi; void *
0x180017f37  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180017f3c  jmp     short loc_180017F41
0x180017f3e  mov     rsi, rbx
0x180017f41  mov     [rsp+98h+pbstr], rsi
0x180017f49  jmp     short loc_180017F6F
0x180017f4b  xor     ebx, ebx
0x180017f4d  mov     r15, [rsp+98h+arg_0]
0x180017f55  mov     rdi, [rsp+98h+arg_8]
0x180017f5d  mov     rsi, [rsp+98h+pbstr]
0x180017f65  mov     r13, [rsp+98h+var_50]
0x180017f6a  mov     r14, [rsp+98h+var_48]
0x180017f6f  test    rsi, rsi
0x180017f72  jnz     short loc_180017F98
0x180017f74  mov     rax, [rdi]
0x180017f77  mov     rdx, [rsp+98h+arg_18]
0x180017f7f  mov     rcx, rdi
0x180017f82  mov     rax, [rax+98h]
0x180017f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f8e  mov     eax, 8007000Eh
0x180017f93  jmp     loc_1800180D1
0x180017f98  lea     rax, [r13+30h]
0x180017f9c  mov     [rsp+98h+var_58], rax
0x180017fa1  mov     r12d, ebx
0x180017fa4  cmp     [r14], ebx
0x180017fa7  jle     loc_1800180B1
0x180017fad  lea     r14, [rsi+0Ch]
0x180017fb1  mov     r15, [rsp+98h+var_58]
0x180017fb6  mov     [rsp+98h+arg_8], rbx
0x180017fbe  and     qword ptr [r14-4], 0
0x180017fc3  mov     rax, [rdi]
0x180017fc6  lea     r8, [rsp+98h+arg_8]
0x180017fce  mov     edx, r12d
0x180017fd1  mov     rcx, rdi
0x180017fd4  mov     rax, [rax+28h]
0x180017fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fdd  test    eax, eax
0x180017fdf  js      loc_180018099
0x180017fe5  mov     [rsp+98h+pbstr], rbx
0x180017fed  mov     rax, [rdi]
0x180017ff0  mov     rcx, [rsp+98h+arg_8]
0x180017ff8  mov     [rsp+98h+var_70], rbx
0x180017ffd  mov     [rsp+98h+var_78], rbx
0x180018002  xor     r9d, r9d
0x180018005  lea     r8, [rsp+98h+pbstr]
0x18001800d  mov     edx, [rcx]
0x18001800f  mov     rcx, rdi
0x180018012  mov     rax, [rax+60h]
0x180018016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001801b  test    eax, eax
0x18001801d  js      short loc_18001806A
0x18001801f  mov     r13, [rsp+98h+pbstr]
0x180018027  mov     [rsp+98h+pbstr], rbx
0x18001802f  mov     rcx, [r14-0Ch]; bstrString
0x180018033  cmp     rcx, r13
0x180018036  jz      short loc_18001804B
0x180018038  call    cs:__imp_SysFreeString
0x18001803f  nop     dword ptr [rax+rax+00h]
0x180018044  mov     [r14-0Ch], r13
0x180018048  mov     rcx, r13; pbstr
0x18001804b  call    cs:__imp_SysStringLen
0x180018052  nop     dword ptr [rax+rax+00h]
0x180018057  mov     [r14-4], eax
0x18001805b  mov     rdx, [rsp+98h+arg_8]
0x180018063  mov     eax, [rdx]
0x180018065  mov     [r14], eax
0x180018068  jmp     short loc_180018072
0x18001806a  mov     rdx, [rsp+98h+arg_8]
0x180018072  mov     rax, [rdi]
0x180018075  mov     rcx, rdi
0x180018078  mov     rax, [rax+0A0h]
0x18001807f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018084  nop
0x180018085  mov     rcx, [rsp+98h+pbstr]; bstrString
0x18001808d  call    cs:__imp_SysFreeString
0x180018094  nop     dword ptr [rax+rax+00h]
0x180018099  inc     r12d
0x18001809c  add     r14, 10h
0x1800180a0  cmp     r12d, [r15]
0x1800180a3  jl      loc_180017FB6
0x1800180a9  mov     r15, [rsp+98h+arg_0]
0x1800180b1  mov     [r15+28h], rsi
0x1800180b5  mov     rax, [rdi]
0x1800180b8  mov     rdx, [rsp+98h+arg_18]
0x1800180c0  mov     rcx, rdi
0x1800180c3  mov     rax, [rax+98h]
0x1800180ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800180cf  xor     eax, eax
0x1800180d1  add     rsp, 60h
0x1800180d5  pop     r15
0x1800180d7  pop     r14
0x1800180d9  pop     r13
0x1800180db  pop     r12
0x1800180dd  pop     rdi
0x1800180de  pop     rsi
0x1800180df  pop     rbx
0x1800180e0  retn
```
