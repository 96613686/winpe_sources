# ArrayToSafeArray_19_HWND______lambda_0a054218ed4fa835f87cf116472260d8_

- ea: `0x18001b1b4`
- end: `0x18001b279`
- name: `ArrayToSafeArray_19_HWND______lambda_0a054218ed4fa835f87cf116472260d8___`
- size: `197`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001b280`
- `0x180038370`

## callees

- `0x18001b1b4`
- `0x180023ce8`
- `0x180031540`
- `0x180039a50`
- `0x180057b58`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18001b206`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18001b206`

## string_xrefs

- `0x18001b1ed`: `onecore\windows\accessibletech\Common\SafeArray.h`
- `0x18001b267`: `onecore\windows\accessibletech\Common\SafeArray.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SAFEARRAY **__fastcall ArrayToSafeArray_19_HWND______lambda_0a054218ed4fa835f87cf116472260d8_(
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
      (unsigned int)"onecore\\windows\\accessibletech\\Common\\SafeArray.h",
      (const char *)0x80070057LL,
      0);
  Vector = SafeArrayCreateVector(0x13u, 0, a3);
  *a1 = Vector;
  if ( !Vector )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x132,
      (unsigned int)"onecore\\windows\\accessibletech\\Common\\SafeArray.h",
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
0x18001b1b4  mov     rax, rsp
0x18001b1b7  mov     [rax+10h], rbx
0x18001b1bb  mov     [rax+18h], rsi
0x18001b1bf  mov     [rax+8], rcx
0x18001b1c3  push    rdi
0x18001b1c4  sub     rsp, 40h
0x18001b1c8  mov     ebx, r8d
0x18001b1cb  mov     rsi, rdx
0x18001b1ce  mov     rdi, rcx
0x18001b1d1  mov     dword ptr [rax-28h], 0
0x18001b1d8  mov     rcx, [rsp+48h]; this
0x18001b1dd  mov     eax, r8d
0x18001b1e0  shr     eax, 1Fh
0x18001b1e3  test    al, al
0x18001b1e5  jz      short loc_18001B1FF
0x18001b1e7  mov     r9d, 80070057h; char *
0x18001b1ed  lea     r8, aOnecoreWindows_18; "onecore\\windows\\accessibletech\\Commo"...
0x18001b1f4  mov     edx, 130h; void *
0x18001b1f9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001b1ff  mov     ecx, 13h; vt
0x18001b204  xor     edx, edx; lLbound
0x18001b206  call    cs:__imp_SafeArrayCreateVector
0x18001b20c  mov     [rdi], rax
0x18001b20f  mov     [rsp+48h+var_28], 1
0x18001b217  mov     rcx, [rsp+48h]; this
0x18001b21c  test    rax, rax
0x18001b21f  jz      short loc_18001B267
0x18001b221  mov     rdx, rax
0x18001b224  lea     rcx, [rsp+48h+var_20]
0x18001b229  call    ??0?$SafeArrayAccessor@I@@QEAA@PEAUtagSAFEARRAY@@G@Z; SafeArrayAccessor<uint>::SafeArrayAccessor<uint>(tagSAFEARRAY *,ushort)
0x18001b22e  xor     r8d, r8d
0x18001b231  test    ebx, ebx
0x18001b233  jz      short loc_18001B24A
0x18001b235  mov     ecx, [rsi+r8*8]
0x18001b239  mov     rax, [rsp+48h+var_10]
0x18001b23e  mov     [rax+r8*4], ecx
0x18001b242  inc     r8d
0x18001b245  cmp     r8d, ebx
0x18001b248  jb      short loc_18001B235
0x18001b24a  lea     rcx, [rsp+48h+var_20]
0x18001b24f  call    ??1?$SafeArrayAccessor@I@@QEAA@XZ; SafeArrayAccessor<uint>::~SafeArrayAccessor<uint>(void)
0x18001b254  mov     rax, rdi
0x18001b257  mov     rbx, [rsp+48h+arg_8]
0x18001b25c  mov     rsi, [rsp+48h+arg_10]
0x18001b261  add     rsp, 40h
0x18001b265  pop     rdi
0x18001b266  retn
0x18001b267  lea     r8, aOnecoreWindows_18; "onecore\\windows\\accessibletech\\Commo"...
0x18001b26e  mov     edx, 132h; void *
0x18001b273  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
