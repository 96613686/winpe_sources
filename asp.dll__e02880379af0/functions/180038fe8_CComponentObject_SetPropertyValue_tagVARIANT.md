# CComponentObject::SetPropertyValue(tagVARIANT *)

- ea: `0x180038fe8`
- end: `0x18003915b`
- name: `?SetPropertyValue@CComponentObject@@AEAAJPEAUtagVARIANT@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(CComponentObject *__hidden this, VARIANTARG *pvargSrc)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800371a0`

## callees

- `0x180037974`
- `0x180037b98`
- `0x180037f34`
- `0x180038fe8`
- `0x180062d14`
- `0x180062de8`
- `0x180064010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003900a`
- `OLEAUT32!__imp_VariantInit` at `0x18003900a`
- `OLEAUT32!__imp_VariantClear` at `0x18003913a`
- `OLEAUT32!__imp_VariantClear` at `0x18003913a`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180039023`
- `OLEAUT32!__imp_VariantCopyInd` at `0x180039023`

## pseudocode

```c
HRESULT __fastcall CComponentObject::SetPropertyValue(struct IUnknown **this, VARIANTARG *pvargSrc)
{
  VARIANTARG *v4; // r15
  unsigned int *v5; // rdi
  HRESULT result; // eax
  struct IUnknown **v7; // rbx
  struct IUnknown *v8; // rcx
  unsigned int v9; // ecx
  int ComponentWithoutContext; // eax
  int v11; // ecx
  struct CComponentObject *v12; // [rsp+60h] [rbp+8h] BYREF
  char *v13; // [rsp+70h] [rbp+18h]
  char *v14; // [rsp+78h] [rbp+20h]

  v12 = (struct CComponentObject *)this;
  v4 = (VARIANTARG *)(this + 8);
  v13 = (char *)(this + 8);
  VariantInit((VARIANTARG *)(this + 8));
  v5 = (unsigned int *)(this + 5);
  v14 = (char *)(this + 5);
  *((_DWORD *)this + 10) |= 0x40000u;
  result = VariantCopyInd(v4, pvargSrc);
  if ( result >= 0 )
  {
    v7 = this + 6;
    if ( v4->vt == 9 )
      v8 = this[9];
    else
      v8 = 0;
    *v7 = v8;
    if ( v8 )
    {
      ((void (__fastcall *)(struct IUnknown *))v8->lpVtbl->AddRef)(v8);
      CComponentObject::GetOnPageInfo((CComponentObject *)this);
      v9 = *v5 ^ (*v5 ^ ((unsigned int)ViperCoObjectAggregatesFTM(*v7) << 12)) & 0x1000;
      *v5 = v9;
      if ( (_BYTE)xmmword_180079F90 )
      {
        if ( (v9 & 0x1000) == 0 )
        {
          v12 = 0;
          ComponentWithoutContext = CPageComponentManager::FindComponentWithoutContext((struct IDispatch *)*v7, &v12);
          v9 = *v5;
          if ( !ComponentWithoutContext )
          {
            v9 = *v5 ^ (*((_DWORD *)v12 + 10) ^ v9) & 0x1000;
            *v5 = v9;
          }
        }
      }
      result = 0;
      if ( (v9 & 0x1000) == 0 && (v9 & 0x100000) == 0 )
      {
        v11 = v9 & 0xF;
        if ( v11 == 1 || v11 == 2 )
        {
          if ( (unsigned int)ViperCoObjectIsaProxy(*v7) || (*(_BYTE *)v5 & 0xF) != 1 )
          {
            return CComponentObject::ConvertToGIPCookie((CComponentObject *)this);
          }
          else
          {
            ((void (__fastcall *)(struct IUnknown *))(*v7)->lpVtbl->Release)(*v7);
            *v7 = 0;
            VariantClear(v4);
            return -2147417842;
          }
        }
      }
    }
    else
    {
      *v5 |= 0x1000u;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180038fe8  mov     [rsp+arg_0], rcx
0x180038fed  push    rbx
0x180038fee  push    rsi
0x180038fef  push    rdi
0x180038ff0  push    r14
0x180038ff2  push    r15
0x180038ff4  sub     rsp, 30h
0x180038ff8  mov     rbx, rdx
0x180038ffb  mov     rsi, rcx
0x180038ffe  lea     r15, [rcx+40h]
0x180039002  mov     [rsp+58h+arg_10], r15
0x180039007  mov     rcx, r15; pvarg
0x18003900a  call    cs:__imp_VariantInit
0x180039010  lea     rdi, [rsi+28h]
0x180039014  mov     [rsp+58h+arg_18], rdi
0x180039019  bts     dword ptr [rdi], 12h
0x18003901d  mov     rdx, rbx; pvargSrc
0x180039020  mov     rcx, r15; pvarDest
0x180039023  call    cs:__imp_VariantCopyInd
0x180039029  test    eax, eax
0x18003902b  js      loc_18003914F
0x180039031  lea     rbx, [rsi+30h]
0x180039035  mov     [rsp+58h+var_30], rbx
0x18003903a  cmp     word ptr [r15], 9
0x18003903f  jnz     short loc_180039047
0x180039041  mov     rcx, [rsi+48h]
0x180039045  jmp     short loc_180039049
0x180039047  xor     ecx, ecx
0x180039049  mov     [rbx], rcx
0x18003904c  test    rcx, rcx
0x18003904f  jnz     short loc_180039061
0x180039051  mov     r14d, 1000h
0x180039057  or      [rdi], r14d
0x18003905a  xor     eax, eax
0x18003905c  jmp     loc_18003914F
0x180039061  mov     rax, [rcx]
0x180039064  mov     rax, [rax+8]
0x180039068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003906d  cmp     byte ptr cs:qword_180079F88, 0
0x180039074  jz      short loc_180039096
0x180039076  mov     rcx, rsi; this
0x180039079  call    ?GetOnPageInfo@CComponentObject@@AEAAJXZ; CComponentObject::GetOnPageInfo(void)
0x18003907e  jmp     short loc_18003909E
0x180039080  mov     rsi, [rsp+58h+arg_0]
0x180039085  mov     r15, [rsp+58h+arg_10]
0x18003908a  mov     rdi, [rsp+58h+arg_18]
0x18003908f  mov     rbx, [rsp+58h+var_30]
0x180039094  jmp     short loc_18003909E
0x180039096  mov     rcx, rsi; this
0x180039099  call    ?GetOnPageInfo@CComponentObject@@AEAAJXZ; CComponentObject::GetOnPageInfo(void)
0x18003909e  mov     rcx, [rbx]; struct IUnknown *
0x1800390a1  call    ?ViperCoObjectAggregatesFTM@@YAHPEAUIUnknown@@@Z; ViperCoObjectAggregatesFTM(IUnknown *)
0x1800390a6  mov     ecx, eax
0x1800390a8  shl     ecx, 0Ch
0x1800390ab  xor     ecx, [rdi]
0x1800390ad  mov     r14d, 1000h
0x1800390b3  and     ecx, r14d
0x1800390b6  xor     ecx, [rdi]
0x1800390b8  mov     [rdi], ecx
0x1800390ba  cmp     byte ptr cs:xmmword_180079F90, 0
0x1800390c1  jz      short loc_1800390F3
0x1800390c3  test    r14d, ecx
0x1800390c6  jnz     short loc_1800390F3
0x1800390c8  mov     [rsp+58h+arg_0], 0
0x1800390d1  lea     rdx, [rsp+58h+arg_0]; struct CComponentObject **
0x1800390d6  mov     rcx, [rbx]; struct IDispatch *
0x1800390d9  call    ?FindComponentWithoutContext@CPageComponentManager@@SAJPEAUIDispatch@@PEAPEAVCComponentObject@@@Z; CPageComponentManager::FindComponentWithoutContext(IDispatch *,CComponentObject * *)
0x1800390de  mov     ecx, [rdi]
0x1800390e0  test    eax, eax
0x1800390e2  jnz     short loc_1800390F3
0x1800390e4  mov     rax, [rsp+58h+arg_0]
0x1800390e9  xor     ecx, [rax+28h]
0x1800390ec  and     ecx, r14d
0x1800390ef  xor     ecx, [rdi]
0x1800390f1  mov     [rdi], ecx
0x1800390f3  xor     eax, eax
0x1800390f5  test    r14d, ecx
0x1800390f8  jnz     short loc_18003914F
0x1800390fa  bt      ecx, 14h
0x1800390fe  jb      short loc_18003914F
0x180039100  and     ecx, 0Fh
0x180039103  cmp     ecx, 1
0x180039106  jz      short loc_18003910D
0x180039108  cmp     ecx, 2
0x18003910b  jnz     short loc_18003914F
0x18003910d  mov     rcx, [rbx]; struct IUnknown *
0x180039110  call    ?ViperCoObjectIsaProxy@@YAHPEAUIUnknown@@@Z; ViperCoObjectIsaProxy(IUnknown *)
0x180039115  test    eax, eax
0x180039117  jnz     short loc_180039147
0x180039119  mov     eax, [rdi]
0x18003911b  and     al, 0Fh
0x18003911d  cmp     al, 1
0x18003911f  jnz     short loc_180039147
0x180039121  mov     rcx, [rbx]
0x180039124  mov     rax, [rcx]
0x180039127  mov     rax, [rax+10h]
0x18003912b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039130  mov     qword ptr [rbx], 0
0x180039137  mov     rcx, r15; pvarg
0x18003913a  call    cs:__imp_VariantClear
0x180039140  mov     eax, 8001010Eh
0x180039145  jmp     short loc_18003914F
0x180039147  mov     rcx, rsi; this
0x18003914a  call    ?ConvertToGIPCookie@CComponentObject@@AEAAJXZ; CComponentObject::ConvertToGIPCookie(void)
0x18003914f  add     rsp, 30h
0x180039153  pop     r15
0x180039155  pop     r14
0x180039157  pop     rdi
0x180039158  pop     rsi
0x180039159  pop     rbx
0x18003915a  retn
```
