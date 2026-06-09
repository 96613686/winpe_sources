# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x180003134`
- end: `0x180003399`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002ae0`

## callees

- `0x1800011e0`
- `0x180001808`
- `0x180003134`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800032fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000334d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800032fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18000334d`
- `OLEAUT32!__imp_SysStringLen` at `0x18000330e`
- `OLEAUT32!__imp_SysStringLen` at `0x18000330e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(ATL::CComTypeInfoHolder *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rsi
  OLECHAR *v4; // rdi
  unsigned __int64 v5; // rcx
  _DWORD *v6; // r14
  __int64 v7; // r15
  __int64 v8; // rax
  bool v9; // cf
  unsigned __int64 v10; // rax
  _QWORD *v11; // rax
  unsigned int i; // r15d
  OLECHAR *v14; // r13
  char *v15; // [rsp+40h] [rbp-48h]
  OLECHAR **v16; // [rsp+48h] [rbp-40h]
  struct ITypeInfo *v17; // [rsp+98h] [rbp+10h] BYREF
  BSTR pbstr; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+20h] BYREF

  v17 = a2;
  v2 = a2;
  v19 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v19) >= 0 )
  {
    v4 = 0;
    pbstr = 0;
    v5 = *(unsigned __int16 *)(v19 + 48);
    v6 = (_DWORD *)((char *)this + 48);
    v15 = (char *)this + 48;
    *((_DWORD *)this + 12) = v5;
    v16 = (OLECHAR **)((char *)this + 40);
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
        v11 = operator new[](v10);
        if ( v11 )
        {
          *v11 = v7;
          v4 = (OLECHAR *)(v11 + 1);
          `eh vector constructor iterator'(
            v11 + 1,
            0x10u,
            (unsigned int)v7,
            (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
            (void (*)(void *))ATL::CComBSTR::~CComBSTR);
        }
        else
        {
          v4 = 0;
        }
        pbstr = v4;
      }
      catch ( ... )
      {
        v2 = v17;
        v4 = pbstr;
        v6 = v15;
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
          v14 = pbstr;
          pbstr = 0;
          if ( *(OLECHAR **)&v4[8 * i] == v14 )
          {
            v14 = *(OLECHAR **)&v4[8 * i];
          }
          else
          {
            SysFreeString(*(BSTR *)&v4[8 * i]);
            *(_QWORD *)&v4[8 * i] = v14;
          }
          *(_DWORD *)&v4[8 * i + 4] = SysStringLen(v14);
          *(_DWORD *)&v4[8 * i + 6] = v17->lpVtbl;
        }
        ((void (__fastcall *)(struct ITypeInfo *))v2->lpVtbl->ReleaseFuncDesc)(v2);
        SysFreeString(pbstr);
      }
    }
    *v16 = v4;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v19);
  }
  return 0;
}

```

## disassembly

```asm
0x180003134  mov     r11, rsp
0x180003137  mov     [r11+8], rsi
0x18000313b  mov     [r11+10h], rdx
0x18000313f  push    rdi
0x180003140  push    r12
0x180003142  push    r13
0x180003144  push    r14
0x180003146  push    r15
0x180003148  sub     rsp, 60h
0x18000314c  mov     rsi, rdx
0x18000314f  mov     r15, rcx
0x180003152  mov     qword ptr [r11+20h], 0
0x18000315a  mov     rax, [rdx]
0x18000315d  lea     rdx, [r11+20h]
0x180003161  mov     rcx, rsi
0x180003164  mov     rax, [rax+18h]
0x180003168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000316d  test    eax, eax
0x18000316f  js      loc_180003381
0x180003175  xor     edi, edi
0x180003177  mov     [rsp+88h+pbstr], rdi
0x18000317f  mov     rax, [rsp+88h+arg_18]
0x180003187  movzx   ecx, word ptr [rax+30h]
0x18000318b  lea     r14, [r15+30h]
0x18000318f  mov     [rsp+88h+var_48], r14
0x180003194  mov     [r14], ecx
0x180003197  lea     rax, [r15+28h]
0x18000319b  mov     [rsp+88h+var_40], rax
0x1800031a0  mov     [rax], rdi
0x1800031a3  test    ecx, ecx
0x1800031a5  jz      loc_18000324E
0x1800031ab  mov     r15d, ecx
0x1800031ae  lea     r12d, [rdi+10h]
0x1800031b2  mov     eax, r12d
0x1800031b5  mul     rcx
0x1800031b8  lea     rcx, [rdi-1]
0x1800031bc  cmovb   rax, rcx
0x1800031c0  add     rax, 8
0x1800031c4  cmovb   rax, rcx
0x1800031c8  mov     rcx, rax; unsigned __int64
0x1800031cb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800031d0  mov     [rsp+88h+var_38], rax
0x1800031d5  test    rax, rax
0x1800031d8  jz      short loc_180003204
0x1800031da  mov     [rax], r15
0x1800031dd  lea     rdi, [rax+8]
0x1800031e1  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x1800031e8  mov     [rsp+88h+var_68], rax; void (*)(void *)
0x1800031ed  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x1800031f4  mov     r8d, r15d; unsigned __int64
0x1800031f7  mov     edx, r12d; unsigned __int64
0x1800031fa  mov     rcx, rdi; void *
0x1800031fd  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180003202  jmp     short loc_180003206
0x180003204  xor     edi, edi
0x180003206  mov     [rsp+88h+pbstr], rdi
0x18000320e  jmp     short loc_180003225
0x180003210  mov     rsi, [rsp+88h+arg_8]
0x180003218  mov     rdi, [rsp+88h+pbstr]
0x180003220  mov     r14, [rsp+88h+var_48]
0x180003225  test    rdi, rdi
0x180003228  jnz     short loc_18000324E
0x18000322a  mov     rax, [rsi]
0x18000322d  mov     rdx, [rsp+88h+arg_18]
0x180003235  mov     rcx, rsi
0x180003238  mov     rax, [rax+98h]
0x18000323f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003244  mov     eax, 8007000Eh
0x180003249  jmp     loc_180003383
0x18000324e  xor     r15d, r15d
0x180003251  cmp     [r14], r15d
0x180003254  jle     loc_18000335F
0x18000325a  mov     [rsp+88h+arg_8], 0
0x180003266  movsxd  r12, r15d
0x180003269  add     r12, r12
0x18000326c  mov     qword ptr [rdi+r12*8+8], 0
0x180003275  mov     rax, [rsi]
0x180003278  lea     r8, [rsp+88h+arg_8]
0x180003280  mov     edx, r15d
0x180003283  mov     rcx, rsi
0x180003286  mov     rax, [rax+28h]
0x18000328a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000328f  test    eax, eax
0x180003291  js      loc_180003353
0x180003297  mov     [rsp+88h+pbstr], 0
0x1800032a3  mov     rax, [rsi]
0x1800032a6  mov     [rsp+88h+var_60], 0
0x1800032af  mov     [rsp+88h+var_68], 0
0x1800032b8  xor     r9d, r9d
0x1800032bb  lea     r8, [rsp+88h+pbstr]
0x1800032c3  mov     rdx, [rsp+88h+arg_8]
0x1800032cb  mov     edx, [rdx]
0x1800032cd  mov     rcx, rsi
0x1800032d0  mov     rax, [rax+60h]
0x1800032d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032d9  test    eax, eax
0x1800032db  js      short loc_18000332A
0x1800032dd  mov     r13, [rsp+88h+pbstr]
0x1800032e5  mov     [rsp+88h+pbstr], 0
0x1800032f1  cmp     [rdi+r12*8], r13
0x1800032f5  jz      short loc_180003307
0x1800032f7  mov     rcx, [rdi+r12*8]; bstrString
0x1800032fb  call    cs:__imp_SysFreeString
0x180003301  mov     [rdi+r12*8], r13
0x180003305  jmp     short loc_18000330B
0x180003307  mov     r13, [rdi+r12*8]
0x18000330b  mov     rcx, r13; pbstr
0x18000330e  call    cs:__imp_SysStringLen
0x180003314  mov     [rdi+r12*8+8], eax
0x180003319  mov     rdx, [rsp+88h+arg_8]
0x180003321  mov     eax, [rdx]
0x180003323  mov     [rdi+r12*8+0Ch], eax
0x180003328  jmp     short loc_180003332
0x18000332a  mov     rdx, [rsp+88h+arg_8]
0x180003332  mov     rax, [rsi]
0x180003335  mov     rcx, rsi
0x180003338  mov     rax, [rax+0A0h]
0x18000333f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003344  nop
0x180003345  mov     rcx, [rsp+88h+pbstr]; bstrString
0x18000334d  call    cs:__imp_SysFreeString
0x180003353  inc     r15d
0x180003356  cmp     r15d, [r14]
0x180003359  jl      loc_18000325A
0x18000335f  mov     rax, [rsp+88h+var_40]
0x180003364  mov     [rax], rdi
0x180003367  mov     rax, [rsi]
0x18000336a  mov     rdx, [rsp+88h+arg_18]
0x180003372  mov     rcx, rsi
0x180003375  mov     rax, [rax+98h]
0x18000337c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003381  xor     eax, eax
0x180003383  mov     rsi, [rsp+88h+arg_0]
0x18000338b  add     rsp, 60h
0x18000338f  pop     r15
0x180003391  pop     r14
0x180003393  pop     r13
0x180003395  pop     r12
0x180003397  pop     rdi
0x180003398  retn
```
