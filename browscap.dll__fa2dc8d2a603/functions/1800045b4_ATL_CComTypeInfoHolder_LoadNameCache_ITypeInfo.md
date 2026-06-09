# ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)

- ea: `0x1800045b4`
- end: `0x1800047f7`
- name: `?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z`
- size: `579`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, struct ITypeInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003f7c`

## callees

- `0x180001c50`
- `0x1800045b4`
- `0x1800099f8`
- `0x18000d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000475e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800047b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000475e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800047b0`
- `OLEAUT32!__imp_SysStringLen` at `0x180004771`
- `OLEAUT32!__imp_SysStringLen` at `0x180004771`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComTypeInfoHolder::LoadNameCache(OLECHAR *this, struct ITypeInfo *a2)
{
  struct ITypeInfo *v2; // rsi
  OLECHAR *v3; // rdi
  unsigned __int64 v4; // rcx
  __int64 v5; // r14
  __int64 v6; // rax
  bool v7; // cf
  unsigned __int64 v8; // rax
  _QWORD *v9; // rax
  int v11; // r14d
  OLECHAR *v12; // r12
  BSTR pbstr; // [rsp+80h] [rbp+8h] BYREF
  struct ITypeInfo *v14; // [rsp+88h] [rbp+10h] BYREF
  __int64 v15; // [rsp+90h] [rbp+18h] BYREF
  _QWORD *v16; // [rsp+98h] [rbp+20h]

  v14 = a2;
  pbstr = this;
  v2 = a2;
  v15 = 0;
  if ( ((int (__fastcall *)(struct ITypeInfo *, __int64 *))a2->lpVtbl->GetTypeAttr)(a2, &v15) >= 0 )
  {
    v3 = 0;
    pbstr = 0;
    v4 = *(unsigned __int16 *)(v15 + 48);
    dword_1800120C0 = v4;
    qword_1800120B8 = 0;
    if ( (_WORD)v4 )
    {
      v5 = (unsigned int)v4;
      v6 = 16 * v4;
      if ( !is_mul_ok(v4, 0x10u) )
        v6 = -1;
      v7 = __CFADD__(v6, 8);
      v8 = v6 + 8;
      if ( v7 )
        v8 = -1;
      try
      {
        v9 = operator new(v8);
        v16 = v9;
        if ( v9 )
        {
          *v9 = v5;
          v3 = (OLECHAR *)(v9 + 1);
          `eh vector constructor iterator'(
            v9 + 1,
            0x10u,
            (unsigned int)v5,
            (void (*)(void *))ATL::CComTypeInfoHolder::stringdispid::stringdispid,
            (void (*)(void *))ATL::CComBSTR::~CComBSTR);
        }
        else
        {
          v3 = 0;
        }
        pbstr = v3;
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
      LODWORD(v4) = dword_1800120C0;
    }
    v11 = 0;
    if ( (int)v4 > 0 )
    {
      do
      {
        v14 = 0;
        *(_QWORD *)&v3[8 * v11 + 4] = 0;
        if ( ((int (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v2->lpVtbl->GetFuncDesc)(
               v2,
               (unsigned int)v11,
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
            v12 = pbstr;
            pbstr = 0;
            if ( *(OLECHAR **)&v3[8 * v11] == v12 )
            {
              v12 = *(OLECHAR **)&v3[8 * v11];
            }
            else
            {
              SysFreeString(*(BSTR *)&v3[8 * v11]);
              *(_QWORD *)&v3[8 * v11] = v12;
            }
            *(_DWORD *)&v3[8 * v11 + 4] = SysStringLen(v12);
            *(_DWORD *)&v3[8 * v11 + 6] = v14->lpVtbl;
          }
          ((void (__fastcall *)(struct ITypeInfo *))v2->lpVtbl->ReleaseFuncDesc)(v2);
          SysFreeString(pbstr);
        }
        ++v11;
      }
      while ( v11 < dword_1800120C0 );
    }
    qword_1800120B8 = (__int64)v3;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v2->lpVtbl->ReleaseTypeAttr)(v2, v15);
  }
  return 0;
}

```

## disassembly

```asm
0x1800045b4  mov     r11, rsp
0x1800045b7  mov     [r11+10h], rdx
0x1800045bb  mov     [r11+8], rcx
0x1800045bf  push    rbx
0x1800045c0  push    rsi
0x1800045c1  push    rdi
0x1800045c2  push    r12
0x1800045c4  push    r14
0x1800045c6  push    r15
0x1800045c8  sub     rsp, 48h
0x1800045cc  mov     rsi, rdx
0x1800045cf  xor     ebx, ebx
0x1800045d1  mov     [r11+18h], rbx
0x1800045d5  mov     rax, [rdx]
0x1800045d8  lea     rdx, [r11+18h]
0x1800045dc  mov     rcx, rsi
0x1800045df  mov     rax, [rax+18h]
0x1800045e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045e8  test    eax, eax
0x1800045ea  js      loc_1800047E7
0x1800045f0  mov     edi, ebx
0x1800045f2  mov     [rsp+78h+pbstr], rbx
0x1800045fa  mov     rax, [rsp+78h+arg_10]
0x180004602  movzx   ecx, word ptr [rax+30h]
0x180004606  mov     cs:dword_1800120C0, ecx
0x18000460c  mov     cs:qword_1800120B8, rbx
0x180004613  test    cx, cx
0x180004616  jz      loc_1800046C6
0x18000461c  mov     r14d, ecx
0x18000461f  lea     r15d, [rbx+10h]
0x180004623  mov     eax, r15d
0x180004626  mul     rcx
0x180004629  lea     rcx, [rbx-1]
0x18000462d  cmovb   rax, rcx
0x180004631  add     rax, 8
0x180004635  cmovb   rax, rcx
0x180004639  mov     rcx, rax; unsigned __int64
0x18000463c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004641  mov     [rsp+78h+arg_18], rax
0x180004649  test    rax, rax
0x18000464c  jz      short loc_180004678
0x18000464e  mov     [rax], r14
0x180004651  lea     rdi, [rax+8]
0x180004655  lea     rax, ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18000465c  mov     [rsp+78h+var_58], rax; void (*)(void *)
0x180004661  lea     r9, ??0stringdispid@CComTypeInfoHolder@ATL@@QEAA@XZ; void (*)(void *)
0x180004668  mov     r8d, r14d; unsigned __int64
0x18000466b  mov     edx, r15d; unsigned __int64
0x18000466e  mov     rcx, rdi; void *
0x180004671  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180004676  jmp     short loc_18000467B
0x180004678  mov     rdi, rbx
0x18000467b  mov     [rsp+78h+pbstr], rdi
0x180004683  jmp     short loc_180004697
0x180004685  xor     ebx, ebx
0x180004687  mov     rsi, [rsp+78h+arg_8]
0x18000468f  mov     rdi, [rsp+78h+pbstr]
0x180004697  test    rdi, rdi
0x18000469a  jnz     short loc_1800046C0
0x18000469c  mov     rax, [rsi]
0x18000469f  mov     rdx, [rsp+78h+arg_10]
0x1800046a7  mov     rcx, rsi
0x1800046aa  mov     rax, [rax+98h]
0x1800046b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046b6  mov     eax, 8007000Eh
0x1800046bb  jmp     loc_1800047E9
0x1800046c0  mov     ecx, cs:dword_1800120C0
0x1800046c6  mov     r14d, ebx
0x1800046c9  test    ecx, ecx
0x1800046cb  jle     loc_1800047C6
0x1800046d1  mov     [rsp+78h+arg_8], rbx
0x1800046d9  movsxd  r15, r14d
0x1800046dc  add     r15, r15
0x1800046df  mov     qword ptr [rdi+r15*8+8], 0
0x1800046e8  mov     rax, [rsi]
0x1800046eb  lea     r8, [rsp+78h+arg_8]
0x1800046f3  mov     edx, r14d
0x1800046f6  mov     rcx, rsi
0x1800046f9  mov     rax, [rax+28h]
0x1800046fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004702  test    eax, eax
0x180004704  js      loc_1800047B6
0x18000470a  mov     [rsp+78h+pbstr], rbx
0x180004712  mov     rax, [rsi]
0x180004715  mov     [rsp+78h+var_50], rbx
0x18000471a  mov     [rsp+78h+var_58], rbx
0x18000471f  xor     r9d, r9d
0x180004722  lea     r8, [rsp+78h+pbstr]
0x18000472a  mov     rdx, [rsp+78h+arg_8]
0x180004732  mov     edx, [rdx]
0x180004734  mov     rcx, rsi
0x180004737  mov     rax, [rax+60h]
0x18000473b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004740  test    eax, eax
0x180004742  js      short loc_18000478D
0x180004744  mov     r12, [rsp+78h+pbstr]
0x18000474c  mov     [rsp+78h+pbstr], rbx
0x180004754  cmp     [rdi+r15*8], r12
0x180004758  jz      short loc_18000476A
0x18000475a  mov     rcx, [rdi+r15*8]; bstrString
0x18000475e  call    cs:__imp_SysFreeString
0x180004764  mov     [rdi+r15*8], r12
0x180004768  jmp     short loc_18000476E
0x18000476a  mov     r12, [rdi+r15*8]
0x18000476e  mov     rcx, r12; pbstr
0x180004771  call    cs:__imp_SysStringLen
0x180004777  mov     [rdi+r15*8+8], eax
0x18000477c  mov     rdx, [rsp+78h+arg_8]
0x180004784  mov     eax, [rdx]
0x180004786  mov     [rdi+r15*8+0Ch], eax
0x18000478b  jmp     short loc_180004795
0x18000478d  mov     rdx, [rsp+78h+arg_8]
0x180004795  mov     rax, [rsi]
0x180004798  mov     rcx, rsi
0x18000479b  mov     rax, [rax+0A0h]
0x1800047a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047a7  nop
0x1800047a8  mov     rcx, [rsp+78h+pbstr]; bstrString
0x1800047b0  call    cs:__imp_SysFreeString
0x1800047b6  inc     r14d
0x1800047b9  cmp     r14d, cs:dword_1800120C0
0x1800047c0  jl      loc_1800046D1
0x1800047c6  mov     cs:qword_1800120B8, rdi
0x1800047cd  mov     rax, [rsi]
0x1800047d0  mov     rdx, [rsp+78h+arg_10]
0x1800047d8  mov     rcx, rsi
0x1800047db  mov     rax, [rax+98h]
0x1800047e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047e7  xor     eax, eax
0x1800047e9  add     rsp, 48h
0x1800047ed  pop     r15
0x1800047ef  pop     r14
0x1800047f1  pop     r12
0x1800047f3  pop     rdi
0x1800047f4  pop     rsi
0x1800047f5  pop     rbx
0x1800047f6  retn
```
