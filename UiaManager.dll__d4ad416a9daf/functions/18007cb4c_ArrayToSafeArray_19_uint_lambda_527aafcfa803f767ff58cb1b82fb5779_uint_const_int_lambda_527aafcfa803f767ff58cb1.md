# ArrayToSafeArray<19,uint,_lambda_527aafcfa803f767ff58cb1b82fb5779_>(uint const *,int,_lambda_527aafcfa803f767ff58cb1b82fb5779_ &&)

- ea: `0x18007cb4c`
- end: `0x18007cc11`
- name: `??$ArrayToSafeArray@$0BD@IV_lambda_527aafcfa803f767ff58cb1b82fb5779_@@@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBIH$$QEAV_lambda_527aafcfa803f767ff58cb1b82fb5779_@@@Z`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002e420`

## callees

- `0x180023ce8`
- `0x180031540`
- `0x180039a50`
- `0x180057b58`
- `0x18007cb4c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007cb9e`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007cb9e`

## string_xrefs

- `0x18007cb85`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18007cbff`: `onecore\windows\accessibletech\common\SafeArray.h`

## pseudocode

```c
SAFEARRAY **__fastcall ArrayToSafeArray<19,unsigned int,_lambda_527aafcfa803f767ff58cb1b82fb5779_>(
        SAFEARRAY **a1,
        __int64 a2,
        signed int a3)
{
  SAFEARRAY *Vector; // rax
  const char *v7; // r9
  __int64 v8; // rdx
  __int64 i; // r8
  _BYTE v11[16]; // [rsp+28h] [rbp-20h] BYREF
  __int64 v12; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x130,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)0x80070057LL,
      0);
  Vector = SafeArrayCreateVector(0x13u, 0, a3);
  *a1 = Vector;
  if ( !Vector )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      v7);
  SafeArrayAccessor<unsigned int>::SafeArrayAccessor<unsigned int>(v11, Vector);
  for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    *(_DWORD *)(v12 + 4 * i) = *(_DWORD *)(a2 + 4 * i);
  SafeArrayAccessor<unsigned int>::~SafeArrayAccessor<unsigned int>(v11, v8, i);
  return a1;
}

```

## disassembly

```asm
0x18007cb4c  mov     rax, rsp
0x18007cb4f  mov     [rax+10h], rbx
0x18007cb53  mov     [rax+18h], rsi
0x18007cb57  mov     [rax+8], rcx
0x18007cb5b  push    rdi
0x18007cb5c  sub     rsp, 40h
0x18007cb60  mov     ebx, r8d
0x18007cb63  mov     rsi, rdx
0x18007cb66  mov     rdi, rcx
0x18007cb69  mov     dword ptr [rax-28h], 0
0x18007cb70  mov     rcx, [rsp+48h]; this
0x18007cb75  mov     eax, r8d
0x18007cb78  shr     eax, 1Fh
0x18007cb7b  test    al, al
0x18007cb7d  jz      short loc_18007CB97
0x18007cb7f  mov     r9d, 80070057h; char *
0x18007cb85  lea     r8, aOnecoreWindows_20; "onecore\\windows\\accessibletech\\commo"...
0x18007cb8c  mov     edx, 130h; void *
0x18007cb91  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007cb97  mov     ecx, 13h; vt
0x18007cb9c  xor     edx, edx; lLbound
0x18007cb9e  call    cs:__imp_SafeArrayCreateVector
0x18007cba4  mov     [rdi], rax
0x18007cba7  mov     [rsp+48h+var_28], 1
0x18007cbaf  mov     rcx, [rsp+48h]; this
0x18007cbb4  test    rax, rax
0x18007cbb7  jz      short loc_18007CBFF
0x18007cbb9  mov     rdx, rax
0x18007cbbc  lea     rcx, [rsp+48h+var_20]
0x18007cbc1  call    ??0?$SafeArrayAccessor@I@@QEAA@PEAUtagSAFEARRAY@@G@Z; SafeArrayAccessor<uint>::SafeArrayAccessor<uint>(tagSAFEARRAY *,ushort)
0x18007cbc6  xor     r8d, r8d
0x18007cbc9  test    ebx, ebx
0x18007cbcb  jz      short loc_18007CBE2
0x18007cbcd  mov     ecx, [rsi+r8*4]
0x18007cbd1  mov     rax, [rsp+48h+var_10]
0x18007cbd6  mov     [rax+r8*4], ecx
0x18007cbda  inc     r8d
0x18007cbdd  cmp     r8d, ebx
0x18007cbe0  jb      short loc_18007CBCD
0x18007cbe2  lea     rcx, [rsp+48h+var_20]
0x18007cbe7  call    ??1?$SafeArrayAccessor@I@@QEAA@XZ; SafeArrayAccessor<uint>::~SafeArrayAccessor<uint>(void)
0x18007cbec  mov     rax, rdi
0x18007cbef  mov     rbx, [rsp+48h+arg_8]
0x18007cbf4  mov     rsi, [rsp+48h+arg_10]
0x18007cbf9  add     rsp, 40h
0x18007cbfd  pop     rdi
0x18007cbfe  retn
0x18007cbff  lea     r8, aOnecoreWindows_20; "onecore\\windows\\accessibletech\\commo"...
0x18007cc06  mov     edx, 132h; void *
0x18007cc0b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
