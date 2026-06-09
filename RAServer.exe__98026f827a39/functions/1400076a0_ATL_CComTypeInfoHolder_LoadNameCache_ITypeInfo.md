# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x1400076a0`
- end: `0x1400078f8`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400069fc`

## callees

- `0x140001558`
- `0x140001ed8`
- `0x140004f74`
- `0x1400076a0`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400078b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1400078b0`
- `OLEAUT32!__imp_SysStringLen` at `0x140007873`
- `OLEAUT32!__imp_SysStringLen` at `0x140007873`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rdi
  OLECHAR *v4; // rsi
  unsigned __int64 v5; // rcx
  _DWORD *v6; // r14
  OLECHAR **v7; // r12
  __int64 v8; // r15
  __int64 v9; // rax
  bool v10; // cf
  unsigned __int64 v11; // rax
  _QWORD *v12; // rax
  unsigned int i; // r15d
  OLECHAR *v15; // r13
  unsigned __int16 *v16; // rdx
  char *v17; // [rsp+40h] [rbp-48h]
  struct ITypeInfo *v18; // [rsp+98h] [rbp+10h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+20h] BYREF

  v18 = a2;
  v2 = a2;
  v20 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v20) >= 0 )
  {
    v4 = 0;
    bstrString = 0;
    v5 = *(unsigned __int16 *)(v20 + 48);
    v6 = (_DWORD *)((char *)this + 48);
    v17 = (char *)this + 48;
    *((_DWORD *)this + 12) = v5;
    v7 = (OLECHAR **)((char *)this + 40);
    *v7 = 0;
    if ( (_DWORD)v5 )
    {
      v8 = (unsigned int)v5;
      v9 = 16 * v5;
      if ( !is_mul_ok(v5, 0x10u) )
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
          v4 = (OLECHAR *)(v12 + 1);
          `eh vector constructor iterator'(
            v12 + 1,
            0x10u,
            (unsigned int)v8,
            (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
            (void (*)(void *))ATL::CComBSTR::~CComBSTR);
        }
        else
        {
          v4 = 0;
        }
        bstrString = v4;
      }
      catch ( ... )
      {
        v2 = v18;
        v4 = bstrString;
        v6 = v17;
      }
      if ( !v4 )
      {
        ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v20);
        return 2147942414LL;
      }
    }
    for ( i = 0; (signed int)i < *v6; ++i )
    {
      v18 = 0;
      v15 = &v4[8 * i];
      *((_QWORD *)v15 + 1) = 0;
      if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v2->lpVtbl->GetFuncDesc)(v2, i, &v18) >= 0 )
      {
        bstrString = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))v2->lpVtbl->GetDocumentation)(
               v2,
               LODWORD(v18->lpVtbl),
               &bstrString,
               0,
               0,
               0) >= 0 )
        {
          v16 = bstrString;
          bstrString = 0;
          ATL::CComBSTR::Attach((BSTR *)v15, v16);
          *((_DWORD *)v15 + 2) = SysStringLen(*(BSTR *)v15);
          *((_DWORD *)v15 + 3) = v18->lpVtbl;
        }
        ((void (__fastcall *)(struct ITypeInfo *))v2->lpVtbl->ReleaseFuncDesc)(v2);
        SysFreeString(bstrString);
      }
    }
    *v7 = v4;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v20);
  }
  return 0;
}

```

## disassembly

```asm
0x1400076a0  mov     r11, rsp
0x1400076a3  mov     [r11+8], rsi
0x1400076a7  mov     [r11+10h], rdx
0x1400076ab  push    rdi
0x1400076ac  push    r12
0x1400076ae  push    r13
0x1400076b0  push    r14
0x1400076b2  push    r15
0x1400076b4  sub     rsp, 60h
0x1400076b8  mov     rdi, rdx
0x1400076bb  mov     r12, rcx
0x1400076be  mov     qword ptr [r11+20h], 0
0x1400076c6  mov     rax, [rdx]
0x1400076c9  lea     rdx, [r11+20h]
0x1400076cd  mov     rcx, rdi
0x1400076d0  mov     rax, [rax+18h]
0x1400076d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400076d9  test    eax, eax
0x1400076db  js      loc_1400078E0
0x1400076e1  xor     esi, esi
0x1400076e3  mov     [rsp+88h+bstrString], rsi
0x1400076eb  mov     rax, [rsp+88h+arg_18]
0x1400076f3  movzx   ecx, word ptr [rax+30h]
0x1400076f7  lea     r14, [r12+30h]
0x1400076fc  mov     [rsp+88h+var_48], r14
0x140007701  mov     [r14], ecx
0x140007704  add     r12, 28h ; '('
0x140007708  mov     [rsp+88h+var_40], r12
0x14000770d  mov     [r12], rsi
0x140007711  test    ecx, ecx
0x140007713  jz      loc_1400077C1
0x140007719  mov     r15d, ecx
0x14000771c  lea     r13d, [rsi+10h]
0x140007720  mov     eax, r13d
0x140007723  mul     rcx
0x140007726  lea     rcx, [rsi-1]
0x14000772a  cmovb   rax, rcx
0x14000772e  add     rax, 8
0x140007732  cmovb   rax, rcx
0x140007736  mov     rcx, rax; unsigned __int64
0x140007739  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000773e  mov     [rsp+88h+var_38], rax
0x140007743  test    rax, rax
0x140007746  jz      short loc_140007772
0x140007748  mov     [rax], r15
0x14000774b  lea     rsi, [rax+8]
0x14000774f  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x140007756  mov     [rsp+88h+var_68], rax; void (*)(void *)
0x14000775b  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x140007762  mov     r8d, r15d; unsigned __int64
0x140007765  mov     edx, r13d; unsigned __int64
0x140007768  mov     rcx, rsi; void *
0x14000776b  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140007770  jmp     short loc_140007774
0x140007772  xor     esi, esi
0x140007774  mov     [rsp+88h+bstrString], rsi
0x14000777c  jmp     short loc_140007798
0x14000777e  mov     rdi, [rsp+88h+arg_8]
0x140007786  mov     rsi, [rsp+88h+bstrString]
0x14000778e  mov     r14, [rsp+88h+var_48]
0x140007793  mov     r12, [rsp+88h+var_40]
0x140007798  test    rsi, rsi
0x14000779b  jnz     short loc_1400077C1
0x14000779d  mov     rax, [rdi]
0x1400077a0  mov     rdx, [rsp+88h+arg_18]
0x1400077a8  mov     rcx, rdi
0x1400077ab  mov     rax, [rax+98h]
0x1400077b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400077b7  mov     eax, 8007000Eh
0x1400077bc  jmp     loc_1400078E2
0x1400077c1  xor     r15d, r15d
0x1400077c4  cmp     [r14], r15d
0x1400077c7  jle     loc_1400078C2
0x1400077cd  mov     [rsp+88h+arg_8], 0
0x1400077d9  movsxd  r13, r15d
0x1400077dc  shl     r13, 4
0x1400077e0  add     r13, rsi
0x1400077e3  mov     qword ptr [r13+8], 0
0x1400077eb  mov     rax, [rdi]
0x1400077ee  lea     r8, [rsp+88h+arg_8]
0x1400077f6  mov     edx, r15d
0x1400077f9  mov     rcx, rdi
0x1400077fc  mov     rax, [rax+28h]
0x140007800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007805  test    eax, eax
0x140007807  js      loc_1400078B6
0x14000780d  mov     [rsp+88h+bstrString], 0
0x140007819  mov     rax, [rdi]
0x14000781c  mov     [rsp+88h+var_60], 0
0x140007825  mov     [rsp+88h+var_68], 0
0x14000782e  xor     r9d, r9d
0x140007831  lea     r8, [rsp+88h+bstrString]
0x140007839  mov     rdx, [rsp+88h+arg_8]
0x140007841  mov     edx, [rdx]
0x140007843  mov     rcx, rdi
0x140007846  mov     rax, [rax+60h]
0x14000784a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000784f  test    eax, eax
0x140007851  js      short loc_14000788D
0x140007853  mov     rdx, [rsp+88h+bstrString]; unsigned __int16 *
0x14000785b  mov     [rsp+88h+bstrString], 0
0x140007867  mov     rcx, r13; this
0x14000786a  call    ?Attach@CComBSTR@ATL@@QEAAXPEAG@Z; ATL::CComBSTR::Attach(ushort *)
0x14000786f  mov     rcx, [r13+0]; pbstr
0x140007873  call    cs:__imp_SysStringLen
0x140007879  mov     [r13+8], eax
0x14000787d  mov     rdx, [rsp+88h+arg_8]
0x140007885  mov     eax, [rdx]
0x140007887  mov     [r13+0Ch], eax
0x14000788b  jmp     short loc_140007895
0x14000788d  mov     rdx, [rsp+88h+arg_8]
0x140007895  mov     rax, [rdi]
0x140007898  mov     rcx, rdi
0x14000789b  mov     rax, [rax+0A0h]
0x1400078a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400078a7  nop
0x1400078a8  mov     rcx, [rsp+88h+bstrString]; bstrString
0x1400078b0  call    cs:__imp_SysFreeString
0x1400078b6  inc     r15d
0x1400078b9  cmp     r15d, [r14]
0x1400078bc  jl      loc_1400077CD
0x1400078c2  mov     [r12], rsi
0x1400078c6  mov     rax, [rdi]
0x1400078c9  mov     rdx, [rsp+88h+arg_18]
0x1400078d1  mov     rcx, rdi
0x1400078d4  mov     rax, [rax+98h]
0x1400078db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400078e0  xor     eax, eax
0x1400078e2  mov     rsi, [rsp+88h+arg_0]
0x1400078ea  add     rsp, 60h
0x1400078ee  pop     r15
0x1400078f0  pop     r14
0x1400078f2  pop     r13
0x1400078f4  pop     r12
0x1400078f6  pop     rdi
0x1400078f7  retn
```
