# ArrayToSafeArray<uint>(uint const *,int,ushort,tagSAFEARRAY * *)

- ea: `0x18007a864`
- end: `0x18007a93f`
- name: `??$ArrayToSafeArray@I@@YAJPEBIHGPEAPEAUtagSAFEARRAY@@@Z`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001af30`

## callees

- `0x18001a280`
- `0x180023ce8`
- `0x180031540`
- `0x180039a50`
- `0x180057b58`
- `0x18007a864`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007a8b5`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007a8b5`

## string_xrefs

- `0x18007a89a`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18007a91a`: `onecore\windows\accessibletech\common\SafeArray.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ArrayToSafeArray<unsigned int>(__int64 a1, signed int a2, __int64 a3, SAFEARRAY **a4)
{
  SAFEARRAY *Vector; // rax
  const char *v8; // r9
  SAFEARRAY *v9; // rdi
  __int64 v10; // rdx
  __int64 i; // r8
  const char *v12; // r9
  __int64 result; // rax
  int v14[4]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v15; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  SAFEARRAY *v17; // [rsp+78h] [rbp+20h] BYREF

  try
  {
    *a4 = 0;
    if ( a2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
        (const char *)0x80070057LL,
        v14[0]);
    Vector = SafeArrayCreateVector(0x13u, 0, a2);
    v9 = Vector;
    v17 = Vector;
    if ( !Vector )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xEA,
        (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
        v8);
    SafeArrayAccessor<unsigned int>::SafeArrayAccessor<unsigned int>(v14, Vector);
    for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
      *(_DWORD *)(v15 + 4 * i) = *(_DWORD *)(a1 + 4 * i);
    SafeArrayAccessor<unsigned int>::~SafeArrayAccessor<unsigned int>(v14, v10, i);
    v17 = 0;
    *a4 = v9;
    wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>(&v17);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xF8,
                           (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x18007a864  mov     [rsp+arg_0], rbx
0x18007a869  mov     word ptr [rsp+arg_10], r8w
0x18007a86f  push    rsi
0x18007a870  push    rdi
0x18007a871  push    r14
0x18007a873  sub     rsp, 40h
0x18007a877  mov     rsi, r9
0x18007a87a  mov     ebx, edx
0x18007a87c  mov     r14, rcx
0x18007a87f  mov     qword ptr [r9], 0
0x18007a886  mov     rcx, [rsp+58h]; this
0x18007a88b  mov     eax, edx
0x18007a88d  shr     eax, 1Fh
0x18007a890  test    al, al
0x18007a892  jz      short loc_18007A8AB
0x18007a894  mov     r9d, 80070057h; char *
0x18007a89a  lea     r8, aOnecoreWindows_20; "onecore\\windows\\accessibletech\\commo"...
0x18007a8a1  mov     edx, 0E8h; void *
0x18007a8a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007a8ab  mov     ecx, 13h; vt
0x18007a8b0  mov     r8d, ebx; cElements
0x18007a8b3  xor     edx, edx; lLbound
0x18007a8b5  call    cs:__imp_SafeArrayCreateVector
0x18007a8bb  mov     rdi, rax
0x18007a8be  mov     [rsp+58h+arg_18], rax
0x18007a8c3  mov     rcx, [rsp+58h]; this
0x18007a8c8  test    rax, rax
0x18007a8cb  jz      short loc_18007A91A
0x18007a8cd  mov     rdx, rax
0x18007a8d0  lea     rcx, [rsp+58h+var_38]
0x18007a8d5  call    ??0?$SafeArrayAccessor@I@@QEAA@PEAUtagSAFEARRAY@@G@Z; SafeArrayAccessor<uint>::SafeArrayAccessor<uint>(tagSAFEARRAY *,ushort)
0x18007a8da  xor     r8d, r8d
0x18007a8dd  test    ebx, ebx
0x18007a8df  jz      short loc_18007A8F6
0x18007a8e1  mov     ecx, [r14+r8*4]
0x18007a8e5  mov     rax, [rsp+58h+var_28]
0x18007a8ea  mov     [rax+r8*4], ecx
0x18007a8ee  inc     r8d
0x18007a8f1  cmp     r8d, ebx
0x18007a8f4  jb      short loc_18007A8E1
0x18007a8f6  lea     rcx, [rsp+58h+var_38]
0x18007a8fb  call    ??1?$SafeArrayAccessor@I@@QEAA@XZ; SafeArrayAccessor<uint>::~SafeArrayAccessor<uint>(void)
0x18007a900  mov     [rsp+58h+arg_18], 0
0x18007a909  mov     [rsi], rdi
0x18007a90c  lea     rcx, [rsp+58h+arg_18]
0x18007a911  call    ??1?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>(void)
0x18007a916  xor     eax, eax
0x18007a918  jmp     short loc_18007A930
0x18007a91a  lea     r8, aOnecoreWindows_20; "onecore\\windows\\accessibletech\\commo"...
0x18007a921  mov     edx, 0EAh; void *
0x18007a926  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18007a92c  mov     eax, [rsp+58h+arg_10]
0x18007a930  mov     rbx, [rsp+58h+arg_0]
0x18007a935  add     rsp, 40h
0x18007a939  pop     r14
0x18007a93b  pop     rdi
0x18007a93c  pop     rsi
0x18007a93d  retn
```
