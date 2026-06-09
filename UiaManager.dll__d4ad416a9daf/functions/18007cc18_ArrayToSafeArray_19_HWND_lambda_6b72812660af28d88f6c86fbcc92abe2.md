# ArrayToSafeArray_19_HWND______lambda_6b72812660af28d88f6c86fbcc92abe2_

- ea: `0x18007cc18`
- end: `0x18007ccdd`
- name: `ArrayToSafeArray_19_HWND______lambda_6b72812660af28d88f6c86fbcc92abe2___`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001b704`

## callees

- `0x180023ce8`
- `0x180031540`
- `0x180039a50`
- `0x180057b58`
- `0x18007cc18`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007cc6a`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18007cc6a`

## string_xrefs

- `0x18007cc51`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x18007cccb`: `onecore\windows\accessibletech\common\SafeArray.h`

## pseudocode

```c
SAFEARRAY **__fastcall ArrayToSafeArray_19_HWND______lambda_6b72812660af28d88f6c86fbcc92abe2_(
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
    *(_DWORD *)(v12 + 4 * i) = *(_DWORD *)(a2 + 8 * i);
  SafeArrayAccessor<unsigned int>::~SafeArrayAccessor<unsigned int>(v11, v8, i);
  return a1;
}

```

## disassembly

```asm
0x18007cc18  mov     rax, rsp
0x18007cc1b  mov     [rax+10h], rbx
0x18007cc1f  mov     [rax+18h], rsi
0x18007cc23  mov     [rax+8], rcx
0x18007cc27  push    rdi
0x18007cc28  sub     rsp, 40h
0x18007cc2c  mov     ebx, r8d
0x18007cc2f  mov     rsi, rdx
0x18007cc32  mov     rdi, rcx
0x18007cc35  mov     dword ptr [rax-28h], 0
0x18007cc3c  mov     rcx, [rsp+48h]; this
0x18007cc41  mov     eax, r8d
0x18007cc44  shr     eax, 1Fh
0x18007cc47  test    al, al
0x18007cc49  jz      short loc_18007CC63
0x18007cc4b  mov     r9d, 80070057h; char *
0x18007cc51  lea     r8, aOnecoreWindows_20; "onecore\\windows\\accessibletech\\commo"...
0x18007cc58  mov     edx, 130h; void *
0x18007cc5d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007cc63  mov     ecx, 13h; vt
0x18007cc68  xor     edx, edx; lLbound
0x18007cc6a  call    cs:__imp_SafeArrayCreateVector
0x18007cc70  mov     [rdi], rax
0x18007cc73  mov     [rsp+48h+var_28], 1
0x18007cc7b  mov     rcx, [rsp+48h]; this
0x18007cc80  test    rax, rax
0x18007cc83  jz      short loc_18007CCCB
0x18007cc85  mov     rdx, rax
0x18007cc88  lea     rcx, [rsp+48h+var_20]
0x18007cc8d  call    ??0?$SafeArrayAccessor@I@@QEAA@PEAUtagSAFEARRAY@@G@Z; SafeArrayAccessor<uint>::SafeArrayAccessor<uint>(tagSAFEARRAY *,ushort)
0x18007cc92  xor     r8d, r8d
0x18007cc95  test    ebx, ebx
0x18007cc97  jz      short loc_18007CCAE
0x18007cc99  mov     ecx, [rsi+r8*8]
0x18007cc9d  mov     rax, [rsp+48h+var_10]
0x18007cca2  mov     [rax+r8*4], ecx
0x18007cca6  inc     r8d
0x18007cca9  cmp     r8d, ebx
0x18007ccac  jb      short loc_18007CC99
0x18007ccae  lea     rcx, [rsp+48h+var_20]
0x18007ccb3  call    ??1?$SafeArrayAccessor@I@@QEAA@XZ; SafeArrayAccessor<uint>::~SafeArrayAccessor<uint>(void)
0x18007ccb8  mov     rax, rdi
0x18007ccbb  mov     rbx, [rsp+48h+arg_8]
0x18007ccc0  mov     rsi, [rsp+48h+arg_10]
0x18007ccc5  add     rsp, 40h
0x18007ccc9  pop     rdi
0x18007ccca  retn
0x18007cccb  lea     r8, aOnecoreWindows_20; "onecore\\windows\\accessibletech\\commo"...
0x18007ccd2  mov     edx, 132h; void *
0x18007ccd7  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
