# ProtobufHelper::WriteIntArray(UIAutomationCoreProto::IntArrayMsg &,tagSAFEARRAY *)

- ea: `0x1800c960c`
- end: `0x1800c9825`
- name: `?WriteIntArray@ProtobufHelper@@SAXAEAVIntArrayMsg@UIAutomationCoreProto@@PEAUtagSAFEARRAY@@@Z`
- size: `537`
- prototype: `static void(struct UIAutomationCoreProto::IntArrayMsg *, struct tagSAFEARRAY *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800239fc`
- `0x1800c93b0`
- `0x1800c9460`

## callees

- `0x18002f580`
- `0x180032724`
- `0x1800c960c`
- `0x1801e8344`
- `0x1801e88a0`
- `0x1801eae30`
- `0x1801eafa0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800c963c`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800c963c`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800c96a4`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800c96a4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800c9687`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800c9687`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c96c7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c96c7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c9735`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c9780`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c9735`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c9780`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c9659`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c9659`

## string_xrefs

- `0x1800c9767`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c97c6`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c9748`: `onecore\windows\accessibletech\uiautomationcore\protobufhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ProtobufHelper::WriteIntArray(struct UIAutomationCoreProto::IntArrayMsg *a1, struct tagSAFEARRAY *a2)
{
  _DWORD *v3; // rbx
  int i; // esi
  HRESULT Vartype; // eax
  int v6; // edi
  unsigned __int64 v7; // rax
  _DWORD *v8; // r9
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 j; // rdi
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // [rsp+20h] [rbp-20h]
  int v16; // [rsp+20h] [rbp-20h]
  unsigned int v18; // [rsp+30h] [rbp-10h]
  void *ppvData; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int pvt; // [rsp+78h] [rbp+38h] BYREF
  LONG plUbound; // [rsp+80h] [rbp+40h] BYREF
  LONG plLbound; // [rsp+88h] [rbp+48h] BYREF

  if ( !a2 )
  {
    google::protobuf::RepeatedField<bool>::Clear((char *)a1 + 16);
    return;
  }
  v3 = 0;
  v15 = 0;
  ppvData = 0;
  i = 0;
  if ( SafeArrayGetDim(a2) != 1 )
  {
    v14 = 2147942487LL;
    v6 = -2147024809;
    v13 = 92;
    goto LABEL_26;
  }
  LOWORD(pvt) = 0;
  Vartype = SafeArrayGetVartype(a2, (VARTYPE *)&pvt);
  v6 = Vartype;
  if ( Vartype < 0 )
  {
    v13 = 95;
    goto LABEL_25;
  }
  if ( (_WORD)pvt != 3 && (_WORD)pvt != 22 )
  {
    v14 = 2147942487LL;
    v6 = -2147024809;
    v13 = 106;
    goto LABEL_26;
  }
  plLbound = 0;
  plUbound = 0;
  Vartype = SafeArrayGetLBound(a2, 1u, &plLbound);
  v6 = Vartype;
  if ( Vartype < 0 )
  {
    v13 = 111;
LABEL_25:
    v14 = (unsigned int)Vartype;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v14,
      0);
    v11 = 159;
    goto LABEL_19;
  }
  Vartype = SafeArrayGetUBound(a2, 1u, &plUbound);
  v6 = Vartype;
  if ( Vartype < 0 )
  {
    v13 = 112;
    goto LABEL_25;
  }
  v18 = plUbound - plLbound + 1;
  Vartype = SafeArrayAccessData(a2, &ppvData);
  v6 = Vartype;
  if ( Vartype < 0 )
  {
    v13 = 115;
    goto LABEL_25;
  }
  v7 = 4LL * v18;
  if ( !is_mul_ok(v18, 4u) )
    v7 = -1;
  v8 = operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
  if ( v8 )
  {
    v9 = 0;
    for ( i = v18; (unsigned int)v9 < v18; i = v18 )
    {
      v8[v9] = *((_DWORD *)ppvData + v9);
      v9 = (unsigned int)(v9 + 1);
    }
    v3 = v8;
    v16 = (int)v8;
    SafeArrayUnaccessData(a2);
    v6 = 0;
    goto LABEL_16;
  }
  v6 = -2147024882;
  v11 = 162;
LABEL_19:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
    (const char *)(unsigned int)v6,
    v15);
  SafeArrayUnaccessData(a2);
LABEL_16:
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x290,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\protobufhelper.cpp",
      (const char *)(unsigned int)v6,
      v16);
  for ( j = 0; (int)j < i; j = (unsigned int)(j + 1) )
  {
    pvt = v3[j];
    google::protobuf::RepeatedField<unsigned int>::Add((char *)a1 + 16, &pvt, v10);
  }
  operator delete(v3);
}

```

## disassembly

```asm
0x1800c960c  push    rbp
0x1800c960e  push    rbx
0x1800c960f  push    rsi
0x1800c9610  push    rdi
0x1800c9611  push    r14
0x1800c9613  mov     rbp, rsp
0x1800c9616  sub     rsp, 40h
0x1800c961a  mov     r14, rcx
0x1800c961d  test    rdx, rdx
0x1800c9620  jz      loc_1800C97F7
0x1800c9626  xor     ebx, ebx
0x1800c9628  mov     [rbp+var_20], rbx
0x1800c962c  mov     [rbp+var_10], ebx
0x1800c962f  mov     [rbp+ppvData], rbx
0x1800c9633  xor     esi, esi
0x1800c9635  mov     [rbp+psa], rdx
0x1800c9639  mov     rcx, rdx; psa
0x1800c963c  call    cs:__imp_SafeArrayGetDim
0x1800c9642  cmp     eax, 1
0x1800c9645  jnz     loc_1800C97E0
0x1800c964b  xor     eax, eax
0x1800c964d  mov     word ptr [rbp+pvt], ax
0x1800c9651  lea     rdx, [rbp+pvt]; pvt
0x1800c9655  mov     rcx, [rbp+psa]; psa
0x1800c9659  call    cs:__imp_SafeArrayGetVartype
0x1800c965f  mov     edi, eax
0x1800c9661  test    eax, eax
0x1800c9663  js      loc_1800C97F0
0x1800c9669  cmp     word ptr [rbp+pvt], 3
0x1800c966e  jnz     loc_1800C9809
0x1800c9674  mov     [rbp+plLbound], esi
0x1800c9677  mov     [rbp+plUbound], esi
0x1800c967a  lea     r8, [rbp+plLbound]; plLbound
0x1800c967e  mov     edx, 1; nDim
0x1800c9683  mov     rcx, [rbp+psa]; psa
0x1800c9687  call    cs:__imp_SafeArrayGetLBound
0x1800c968d  mov     edi, eax
0x1800c968f  test    eax, eax
0x1800c9691  js      loc_1800C97BA
0x1800c9697  lea     r8, [rbp+plUbound]; plUbound
0x1800c969b  mov     edx, 1; nDim
0x1800c96a0  mov     rcx, [rbp+psa]; psa
0x1800c96a4  call    cs:__imp_SafeArrayGetUBound
0x1800c96aa  mov     edi, eax
0x1800c96ac  test    eax, eax
0x1800c96ae  js      loc_1800C97D9
0x1800c96b4  mov     eax, [rbp+plUbound]
0x1800c96b7  sub     eax, [rbp+plLbound]
0x1800c96ba  inc     eax
0x1800c96bc  mov     [rbp+var_10], eax
0x1800c96bf  lea     rdx, [rbp+ppvData]; ppvData
0x1800c96c3  mov     rcx, [rbp+psa]; psa
0x1800c96c7  call    cs:__imp_SafeArrayAccessData
0x1800c96cd  mov     edi, eax
0x1800c96cf  test    eax, eax
0x1800c96d1  js      loc_1800C9802
0x1800c96d7  mov     ecx, [rbp+var_10]
0x1800c96da  mov     eax, 4
0x1800c96df  mul     rcx
0x1800c96e2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800c96e9  cmovb   rax, rcx
0x1800c96ed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c96f4  mov     rcx, rax; unsigned __int64
0x1800c96f7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800c96fc  mov     r9, rax
0x1800c96ff  test    rax, rax
0x1800c9702  jz      short loc_1800C975A
0x1800c9704  xor     r8d, r8d
0x1800c9707  mov     esi, [rbp+var_10]
0x1800c970a  test    esi, esi
0x1800c970c  jz      short loc_1800C9725
0x1800c970e  mov     rcx, [rbp+ppvData]
0x1800c9712  mov     eax, [rcx+r8*4]
0x1800c9716  mov     [r9+r8*4], eax
0x1800c971a  inc     r8d
0x1800c971d  mov     esi, [rbp+var_10]
0x1800c9720  cmp     r8d, esi
0x1800c9723  jb      short loc_1800C970E
0x1800c9725  mov     rbx, r9
0x1800c9728  mov     [rbp+var_20], rbx
0x1800c972c  mov     rcx, [rbp+psa]; psa
0x1800c9730  test    rcx, rcx
0x1800c9733  jz      short loc_1800C973B
0x1800c9735  call    cs:__imp_SafeArrayUnaccessData
0x1800c973b  xor     edi, edi
0x1800c973d  mov     rcx, [rbp+28h]; this
0x1800c9741  test    edi, edi
0x1800c9743  jns     short loc_1800C9788
0x1800c9745  mov     r9d, edi; char *
0x1800c9748  lea     r8, aOnecoreWindows_122; "onecore\\windows\\accessibletech\\uiaut"...
0x1800c974f  mov     edx, 290h; void *
0x1800c9754  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c975a  mov     edi, 8007000Eh
0x1800c975f  mov     edx, 0A2h; void *
0x1800c9764  mov     r9d, edi; char *
0x1800c9767  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c976e  mov     rcx, [rbp+28h]; this
0x1800c9772  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9777  mov     rcx, [rbp+psa]; psa
0x1800c977b  test    rcx, rcx
0x1800c977e  jz      short loc_1800C973D
0x1800c9780  call    cs:__imp_SafeArrayUnaccessData
0x1800c9786  jmp     short loc_1800C973D
0x1800c9788  xor     edi, edi
0x1800c978a  test    esi, esi
0x1800c978c  jle     short loc_1800C97A7
0x1800c978e  mov     ecx, [rbx+rdi*4]
0x1800c9791  mov     [rbp+pvt], ecx
0x1800c9794  lea     rdx, [rbp+pvt]
0x1800c9798  lea     rcx, [r14+10h]
0x1800c979c  call    ?Add@?$RepeatedField@I@protobuf@google@@QEAAXAEBI@Z; google::protobuf::RepeatedField<uint>::Add(uint const &)
0x1800c97a1  inc     edi
0x1800c97a3  cmp     edi, esi
0x1800c97a5  jl      short loc_1800C978E
0x1800c97a7  mov     rcx, rbx; Block
0x1800c97aa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c97af  add     rsp, 40h
0x1800c97b3  pop     r14
0x1800c97b5  pop     rdi
0x1800c97b6  pop     rsi
0x1800c97b7  pop     rbx
0x1800c97b8  pop     rbp
0x1800c97b9  retn
0x1800c97ba  mov     edx, 6Fh ; 'o'; void *
0x1800c97bf  mov     r9d, eax; char *
0x1800c97c2  mov     rcx, [rbp+28h]; this
0x1800c97c6  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c97cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c97d2  mov     edx, 9Fh
0x1800c97d7  jmp     short loc_1800C9764
0x1800c97d9  mov     edx, 70h ; 'p'
0x1800c97de  jmp     short loc_1800C97BF
0x1800c97e0  mov     r9d, 80070057h
0x1800c97e6  mov     edi, r9d
0x1800c97e9  mov     edx, 5Ch ; '\'
0x1800c97ee  jmp     short loc_1800C97C2
0x1800c97f0  mov     edx, 5Fh ; '_'
0x1800c97f5  jmp     short loc_1800C97BF
0x1800c97f7  add     rcx, 10h
0x1800c97fb  call    ?Clear@?$RepeatedField@_N@protobuf@google@@QEAAXXZ; google::protobuf::RepeatedField<bool>::Clear(void)
0x1800c9800  jmp     short loc_1800C97AF
0x1800c9802  mov     edx, 73h ; 's'
0x1800c9807  jmp     short loc_1800C97BF
0x1800c9809  cmp     word ptr [rbp+pvt], 16h
0x1800c980e  jz      loc_1800C9674
0x1800c9814  mov     r9d, 80070057h
0x1800c981a  mov     edi, r9d
0x1800c981d  mov     edx, 6Ah ; 'j'
0x1800c9822  jmp     short loc_1800C97C2
```
