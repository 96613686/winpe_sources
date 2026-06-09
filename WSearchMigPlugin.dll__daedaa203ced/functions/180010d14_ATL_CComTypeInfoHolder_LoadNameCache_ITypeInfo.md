# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x180010d14`
- end: `0x180010f7e`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `618`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000fc68`

## callees

- `0x180002c00`
- `0x180002c74`
- `0x180010d14`
- `0x180018010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180010ee0`
- `OLEAUT32!__imp_SysFreeString` at `0x180010f32`
- `OLEAUT32!__imp_SysFreeString` at `0x180010ee0`
- `OLEAUT32!__imp_SysFreeString` at `0x180010f32`
- `OLEAUT32!__imp_SysStringLen` at `0x180010ef3`
- `OLEAUT32!__imp_SysStringLen` at `0x180010ef3`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rsi
  BSTR v4; // rdi
  unsigned __int64 v5; // rcx
  _DWORD *v6; // r14
  __int64 v7; // r15
  __int64 v8; // rax
  bool v9; // cf
  unsigned __int64 v10; // rax
  unsigned int i; // r15d
  OLECHAR *v13; // r13
  char *v14; // [rsp+40h] [rbp-58h]
  BSTR *v15; // [rsp+48h] [rbp-50h]
  _QWORD *v16; // [rsp+60h] [rbp-38h]
  struct ITypeInfo *v17; // [rsp+A8h] [rbp+10h] BYREF
  BSTR pbstr; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v19; // [rsp+B8h] [rbp+20h] BYREF

  v17 = a2;
  v2 = a2;
  v19 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v19) >= 0 )
  {
    v4 = 0;
    pbstr = 0;
    v5 = *(unsigned __int16 *)(v19 + 48);
    v6 = (_DWORD *)((char *)this + 48);
    v14 = (char *)this + 48;
    *((_DWORD *)this + 12) = v5;
    v15 = (BSTR *)((char *)this + 40);
    *((_QWORD *)this + 5) = 0;
    if ( (_DWORD)v5 )
    {
      v7 = (unsigned int)v5;
      v8 = 16 * v5;
      if ( !is_mul_ok(v5, 0x10u) )
        v8 = -1;
      v9 = __CFADD__(v8, 8);
      v10 = v8 + 8;
      if ( v9 )
        v10 = -1;
      try
      {
        v16 = operator new[](v10);
        *v16 = v7;
        v4 = (BSTR)(v16 + 1);
        `eh vector constructor iterator'(
          v16 + 1,
          0x10u,
          (unsigned int)v7,
          (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
          (void (*)(void *))ATL::CComBSTR::~CComBSTR);
        pbstr = (BSTR)(v16 + 1);
      }
      catch ( ... )
      {
        v2 = v17;
        v4 = pbstr;
        v6 = v14;
      }
      if ( !v4 )
      {
        ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v19);
        return 2147942414LL;
      }
    }
    for ( i = 0; (signed int)i < *v6; ++i )
    {
      v17 = 0;
      *(_QWORD *)&v4[8 * i + 4] = 0;
      if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v2->lpVtbl->GetFuncDesc)(v2, i, &v17) >= 0 )
      {
        pbstr = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v2->lpVtbl->GetDocumentation)(
               v2,
               LODWORD(v17->lpVtbl),
               &pbstr,
               0,
               0,
               0) >= 0 )
        {
          v13 = pbstr;
          pbstr = 0;
          if ( *(OLECHAR **)&v4[8 * i] == v13 )
          {
            v13 = *(OLECHAR **)&v4[8 * i];
          }
          else
          {
            SysFreeString(*(BSTR *)&v4[8 * i]);
            *(_QWORD *)&v4[8 * i] = v13;
          }
          *(_DWORD *)&v4[8 * i + 4] = SysStringLen(v13);
          *(_DWORD *)&v4[8 * i + 6] = v17->lpVtbl;
        }
        ((void (__fastcall *)(struct ITypeInfo *))v2->lpVtbl->ReleaseFuncDesc)(v2);
        SysFreeString(pbstr);
      }
    }
    *v15 = v4;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v19);
  }
  return 0;
}

```

## disassembly

```asm
0x180010d14  mov     r11, rsp
0x180010d17  mov     [r11+10h], rdx
0x180010d1b  push    rdi
0x180010d1c  push    r12
0x180010d1e  push    r13
0x180010d20  push    r14
0x180010d22  push    r15
0x180010d24  sub     rsp, 70h
0x180010d28  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x180010d30  mov     [r11+8], rsi
0x180010d34  mov     rsi, rdx
0x180010d37  mov     r15, rcx
0x180010d3a  mov     qword ptr [r11+20h], 0
0x180010d42  mov     rax, [rdx]
0x180010d45  lea     rdx, [r11+20h]
0x180010d49  mov     rcx, rsi
0x180010d4c  mov     rax, [rax+18h]
0x180010d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d55  test    eax, eax
0x180010d57  js      loc_180010F66
0x180010d5d  xor     edi, edi
0x180010d5f  mov     [rsp+98h+pbstr], rdi
0x180010d67  mov     rax, [rsp+98h+arg_18]
0x180010d6f  movzx   ecx, word ptr [rax+30h]
0x180010d73  lea     r14, [r15+30h]
0x180010d77  mov     [rsp+98h+var_58], r14
0x180010d7c  mov     [r14], ecx
0x180010d7f  lea     rax, [r15+28h]
0x180010d83  mov     [rsp+98h+var_50], rax
0x180010d88  mov     [rax], rdi
0x180010d8b  test    ecx, ecx
0x180010d8d  jz      loc_180010E33
0x180010d93  mov     r15d, ecx
0x180010d96  mov     [rsp+98h+var_40], rcx
0x180010d9b  lea     r12d, [rdi+10h]
0x180010d9f  mov     eax, r12d
0x180010da2  mul     rcx
0x180010da5  lea     rcx, [rdi-1]
0x180010da9  cmovb   rax, rcx
0x180010dad  add     rax, 8
0x180010db1  cmovb   rax, rcx
0x180010db5  mov     rcx, rax; unsigned __int64
0x180010db8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010dbd  mov     [rsp+98h+var_38], rax
0x180010dc2  mov     [rax], r15
0x180010dc5  lea     rdi, [rax+8]
0x180010dc9  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x180010dd0  mov     [rsp+98h+var_78], rax; void (*)(void *)
0x180010dd5  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x180010ddc  mov     r8d, r15d; unsigned __int64
0x180010ddf  mov     edx, r12d; unsigned __int64
0x180010de2  mov     rcx, rdi; void *
0x180010de5  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180010dea  nop
0x180010deb  mov     [rsp+98h+pbstr], rdi
0x180010df3  jmp     short loc_180010E0A
0x180010df5  mov     rsi, [rsp+98h+arg_8]
0x180010dfd  mov     rdi, [rsp+98h+pbstr]
0x180010e05  mov     r14, [rsp+98h+var_58]
0x180010e0a  test    rdi, rdi
0x180010e0d  jnz     short loc_180010E33
0x180010e0f  mov     rax, [rsi]
0x180010e12  mov     rdx, [rsp+98h+arg_18]
0x180010e1a  mov     rcx, rsi
0x180010e1d  mov     rax, [rax+98h]
0x180010e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e29  mov     eax, 8007000Eh
0x180010e2e  jmp     loc_180010F68
0x180010e33  xor     r15d, r15d
0x180010e36  cmp     [r14], r15d
0x180010e39  jle     loc_180010F44
0x180010e3f  mov     [rsp+98h+arg_8], 0
0x180010e4b  movsxd  r12, r15d
0x180010e4e  add     r12, r12
0x180010e51  mov     qword ptr [rdi+r12*8+8], 0
0x180010e5a  mov     rax, [rsi]
0x180010e5d  lea     r8, [rsp+98h+arg_8]
0x180010e65  mov     edx, r15d
0x180010e68  mov     rcx, rsi
0x180010e6b  mov     rax, [rax+28h]
0x180010e6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e74  test    eax, eax
0x180010e76  js      loc_180010F38
0x180010e7c  mov     [rsp+98h+pbstr], 0
0x180010e88  mov     rax, [rsi]
0x180010e8b  mov     [rsp+98h+var_70], 0
0x180010e94  mov     [rsp+98h+var_78], 0
0x180010e9d  xor     r9d, r9d
0x180010ea0  lea     r8, [rsp+98h+pbstr]
0x180010ea8  mov     rdx, [rsp+98h+arg_8]
0x180010eb0  mov     edx, [rdx]
0x180010eb2  mov     rcx, rsi
0x180010eb5  mov     rax, [rax+60h]
0x180010eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ebe  test    eax, eax
0x180010ec0  js      short loc_180010F0F
0x180010ec2  mov     r13, [rsp+98h+pbstr]
0x180010eca  mov     [rsp+98h+pbstr], 0
0x180010ed6  cmp     [rdi+r12*8], r13
0x180010eda  jz      short loc_180010EEC
0x180010edc  mov     rcx, [rdi+r12*8]; bstrString
0x180010ee0  call    cs:__imp_SysFreeString
0x180010ee6  mov     [rdi+r12*8], r13
0x180010eea  jmp     short loc_180010EF0
0x180010eec  mov     r13, [rdi+r12*8]
0x180010ef0  mov     rcx, r13; pbstr
0x180010ef3  call    cs:__imp_SysStringLen
0x180010ef9  mov     [rdi+r12*8+8], eax
0x180010efe  mov     rdx, [rsp+98h+arg_8]
0x180010f06  mov     eax, [rdx]
0x180010f08  mov     [rdi+r12*8+0Ch], eax
0x180010f0d  jmp     short loc_180010F17
0x180010f0f  mov     rdx, [rsp+98h+arg_8]
0x180010f17  mov     rax, [rsi]
0x180010f1a  mov     rcx, rsi
0x180010f1d  mov     rax, [rax+0A0h]
0x180010f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f29  nop
0x180010f2a  mov     rcx, [rsp+98h+pbstr]; bstrString
0x180010f32  call    cs:__imp_SysFreeString
0x180010f38  inc     r15d
0x180010f3b  cmp     r15d, [r14]
0x180010f3e  jl      loc_180010E3F
0x180010f44  mov     rax, [rsp+98h+var_50]
0x180010f49  mov     [rax], rdi
0x180010f4c  mov     rax, [rsi]
0x180010f4f  mov     rdx, [rsp+98h+arg_18]
0x180010f57  mov     rcx, rsi
0x180010f5a  mov     rax, [rax+98h]
0x180010f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f66  xor     eax, eax
0x180010f68  mov     rsi, [rsp+98h+arg_0]
0x180010f70  add     rsp, 70h
0x180010f74  pop     r15
0x180010f76  pop     r14
0x180010f78  pop     r13
0x180010f7a  pop     r12
0x180010f7c  pop     rdi
0x180010f7d  retn
```
