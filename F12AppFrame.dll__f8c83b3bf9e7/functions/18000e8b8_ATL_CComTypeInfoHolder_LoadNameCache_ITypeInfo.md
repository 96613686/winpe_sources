# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x18000e8b8`
- end: `0x18000eb08`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `592`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d9a4`

## callees

- `0x180001c10`
- `0x180001c84`
- `0x18000e8b8`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000ea70`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eac2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea70`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eac2`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ea83`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ea83`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(OLECHAR *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rsi
  BSTR v3; // rdi
  unsigned __int64 v4; // rcx
  __int64 v5; // r14
  __int64 v6; // rax
  bool v7; // cf
  size_t v8; // rax
  int v10; // r14d
  OLECHAR *v11; // r12
  _QWORD *v12; // [rsp+40h] [rbp-38h]
  BSTR pbstr; // [rsp+80h] [rbp+8h] BYREF
  struct ITypeInfo *v14; // [rsp+88h] [rbp+10h] BYREF
  __int64 v15; // [rsp+90h] [rbp+18h] BYREF
  unsigned __int64 v16; // [rsp+98h] [rbp+20h]

  v14 = a2;
  pbstr = this;
  v2 = a2;
  v15 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v15) >= 0 )
  {
    v3 = 0;
    pbstr = 0;
    v4 = *(unsigned __int16 *)(v15 + 48);
    dword_18004B960 = v4;
    qword_18004B958 = 0;
    if ( (_DWORD)v4 )
    {
      v5 = (unsigned int)v4;
      v16 = v4;
      v6 = 16 * v4;
      if ( !is_mul_ok(v4, 0x10u) )
        v6 = -1;
      v7 = __CFADD__(v6, 8);
      v8 = v6 + 8;
      if ( v7 )
        v8 = -1;
      try
      {
        v12 = operator new[](v8);
        *v12 = v5;
        v3 = (BSTR)(v12 + 1);
        `eh vector constructor iterator'(
          v12 + 1,
          0x10u,
          (unsigned int)v5,
          (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
          (void (*)(void *))ATL::CComBSTR::~CComBSTR);
        pbstr = (BSTR)(v12 + 1);
      }
      catch ( ... )
      {
        v2 = v14;
        v3 = pbstr;
      }
      if ( !v3 )
      {
        ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v15);
        return 2147942414LL;
      }
      LODWORD(v4) = dword_18004B960;
    }
    v10 = 0;
    if ( (int)v4 > 0 )
    {
      do
      {
        v14 = 0;
        *(_QWORD *)&v3[8 * v10 + 4] = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v2->lpVtbl->GetFuncDesc)(
               v2,
               (unsigned int)v10,
               &v14) >= 0 )
        {
          pbstr = 0;
          if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v2->lpVtbl->GetDocumentation)(
                 v2,
                 LODWORD(v14->lpVtbl),
                 &pbstr,
                 0,
                 0,
                 0) >= 0 )
          {
            v11 = pbstr;
            pbstr = 0;
            if ( *(OLECHAR **)&v3[8 * v10] == v11 )
            {
              v11 = *(OLECHAR **)&v3[8 * v10];
            }
            else
            {
              SysFreeString(*(BSTR *)&v3[8 * v10]);
              *(_QWORD *)&v3[8 * v10] = v11;
            }
            *(_DWORD *)&v3[8 * v10 + 4] = SysStringLen(v11);
            *(_DWORD *)&v3[8 * v10 + 6] = v14->lpVtbl;
          }
          ((void (__fastcall *)(struct ITypeInfo *))v2->lpVtbl->ReleaseFuncDesc)(v2);
          SysFreeString(pbstr);
        }
        ++v10;
      }
      while ( v10 < dword_18004B960 );
    }
    qword_18004B958 = (__int64)v3;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v15);
  }
  return 0;
}

```

## disassembly

```asm
0x18000e8b8  mov     r11, rsp
0x18000e8bb  mov     [r11+10h], rdx
0x18000e8bf  mov     [r11+8], rcx
0x18000e8c3  push    rsi
0x18000e8c4  push    rdi
0x18000e8c5  push    r12
0x18000e8c7  push    r14
0x18000e8c9  push    r15
0x18000e8cb  sub     rsp, 50h
0x18000e8cf  mov     rsi, rdx
0x18000e8d2  mov     qword ptr [r11+18h], 0
0x18000e8da  mov     rax, [rdx]
0x18000e8dd  lea     rdx, [r11+18h]
0x18000e8e1  mov     rcx, rsi
0x18000e8e4  mov     rax, [rax+18h]
0x18000e8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8ed  test    eax, eax
0x18000e8ef  js      loc_18000EAF9
0x18000e8f5  xor     edi, edi
0x18000e8f7  mov     [rsp+78h+pbstr], rdi
0x18000e8ff  mov     rax, [rsp+78h+arg_10]
0x18000e907  movzx   ecx, word ptr [rax+30h]
0x18000e90b  mov     cs:dword_18004B960, ecx
0x18000e911  mov     cs:qword_18004B958, rdi
0x18000e918  test    ecx, ecx
0x18000e91a  jz      loc_18000E9C4
0x18000e920  mov     r14d, ecx
0x18000e923  mov     [rsp+78h+arg_18], rcx
0x18000e92b  lea     r15d, [rdi+10h]
0x18000e92f  mov     eax, r15d
0x18000e932  mul     rcx
0x18000e935  lea     rcx, [rdi-1]
0x18000e939  cmovb   rax, rcx
0x18000e93d  add     rax, 8
0x18000e941  cmovb   rax, rcx
0x18000e945  mov     rcx, rax; unsigned __int64
0x18000e948  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000e94d  mov     [rsp+78h+var_38], rax
0x18000e952  mov     [rax], r14
0x18000e955  lea     rdi, [rax+8]
0x18000e959  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18000e960  mov     [rsp+78h+var_58], rax; void (*)(void *)
0x18000e965  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x18000e96c  mov     r8d, r14d; unsigned __int64
0x18000e96f  mov     edx, r15d; unsigned __int64
0x18000e972  mov     rcx, rdi; void *
0x18000e975  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000e97a  nop
0x18000e97b  mov     [rsp+78h+pbstr], rdi
0x18000e983  jmp     short loc_18000E995
0x18000e985  mov     rsi, [rsp+78h+arg_8]
0x18000e98d  mov     rdi, [rsp+78h+pbstr]
0x18000e995  test    rdi, rdi
0x18000e998  jnz     short loc_18000E9BE
0x18000e99a  mov     rax, [rsi]
0x18000e99d  mov     rdx, [rsp+78h+arg_10]
0x18000e9a5  mov     rcx, rsi
0x18000e9a8  mov     rax, [rax+98h]
0x18000e9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9b4  mov     eax, 8007000Eh
0x18000e9b9  jmp     loc_18000EAFB
0x18000e9be  mov     ecx, cs:dword_18004B960
0x18000e9c4  xor     r14d, r14d
0x18000e9c7  test    ecx, ecx
0x18000e9c9  jle     loc_18000EAD8
0x18000e9cf  mov     [rsp+78h+arg_8], 0
0x18000e9db  movsxd  r15, r14d
0x18000e9de  add     r15, r15
0x18000e9e1  mov     qword ptr [rdi+r15*8+8], 0
0x18000e9ea  mov     rax, [rsi]
0x18000e9ed  lea     r8, [rsp+78h+arg_8]
0x18000e9f5  mov     edx, r14d
0x18000e9f8  mov     rcx, rsi
0x18000e9fb  mov     rax, [rax+28h]
0x18000e9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea04  test    eax, eax
0x18000ea06  js      loc_18000EAC8
0x18000ea0c  mov     [rsp+78h+pbstr], 0
0x18000ea18  mov     rax, [rsi]
0x18000ea1b  mov     [rsp+78h+var_50], 0
0x18000ea24  mov     [rsp+78h+var_58], 0
0x18000ea2d  xor     r9d, r9d
0x18000ea30  lea     r8, [rsp+78h+pbstr]
0x18000ea38  mov     rdx, [rsp+78h+arg_8]
0x18000ea40  mov     edx, [rdx]
0x18000ea42  mov     rcx, rsi
0x18000ea45  mov     rax, [rax+60h]
0x18000ea49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea4e  test    eax, eax
0x18000ea50  js      short loc_18000EA9F
0x18000ea52  mov     r12, [rsp+78h+pbstr]
0x18000ea5a  mov     [rsp+78h+pbstr], 0
0x18000ea66  cmp     [rdi+r15*8], r12
0x18000ea6a  jz      short loc_18000EA7C
0x18000ea6c  mov     rcx, [rdi+r15*8]; bstrString
0x18000ea70  call    cs:__imp_SysFreeString
0x18000ea76  mov     [rdi+r15*8], r12
0x18000ea7a  jmp     short loc_18000EA80
0x18000ea7c  mov     r12, [rdi+r15*8]
0x18000ea80  mov     rcx, r12; pbstr
0x18000ea83  call    cs:__imp_SysStringLen
0x18000ea89  mov     [rdi+r15*8+8], eax
0x18000ea8e  mov     rdx, [rsp+78h+arg_8]
0x18000ea96  mov     eax, [rdx]
0x18000ea98  mov     [rdi+r15*8+0Ch], eax
0x18000ea9d  jmp     short loc_18000EAA7
0x18000ea9f  mov     rdx, [rsp+78h+arg_8]
0x18000eaa7  mov     rax, [rsi]
0x18000eaaa  mov     rcx, rsi
0x18000eaad  mov     rax, [rax+0A0h]
0x18000eab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eab9  nop
0x18000eaba  mov     rcx, [rsp+78h+pbstr]; bstrString
0x18000eac2  call    cs:__imp_SysFreeString
0x18000eac8  inc     r14d
0x18000eacb  cmp     r14d, cs:dword_18004B960
0x18000ead2  jl      loc_18000E9CF
0x18000ead8  mov     cs:qword_18004B958, rdi
0x18000eadf  mov     rax, [rsi]
0x18000eae2  mov     rdx, [rsp+78h+arg_10]
0x18000eaea  mov     rcx, rsi
0x18000eaed  mov     rax, [rax+98h]
0x18000eaf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaf9  xor     eax, eax
0x18000eafb  add     rsp, 50h
0x18000eaff  pop     r15
0x18000eb01  pop     r14
0x18000eb03  pop     r12
0x18000eb05  pop     rdi
0x18000eb06  pop     rsi
0x18000eb07  retn
```
