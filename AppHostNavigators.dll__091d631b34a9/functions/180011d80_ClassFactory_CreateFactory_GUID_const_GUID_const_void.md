# ClassFactory::CreateFactory(_GUID const &,_GUID const &,void * *)

- ea: `0x180011d80`
- end: `0x180011e45`
- name: `?CreateFactory@ClassFactory@@SAJAEBU_GUID@@0PEAPEAX@Z`
- size: `197`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000f850`

## callees

- `0x180001194`
- `0x180002310`
- `0x180011cd0`
- `0x180011d80`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ClassFactory::CreateFactory(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  _UNKNOWN **i; // rbx
  _QWORD *v6; // r8
  __int64 v7; // rax
  _DWORD *v8; // rdi
  unsigned int v9; // ebx
  _DWORD *v11; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  for ( i = (_UNKNOWN **)off_18001C1F8; ; i = (_UNKNOWN **)*i )
  {
    if ( i == &off_18001C1F8 )
      return 2147746065LL;
    v6 = i[2];
    v7 = *(_QWORD *)&a1->Data1 - *v6;
    if ( *(_QWORD *)&a1->Data1 == *v6 )
      v7 = *(_QWORD *)a1->Data4 - v6[1];
    if ( !v7 )
      break;
  }
  v8 = operator new(0x18u);
  if ( v8 )
  {
    *(_QWORD *)v8 = &SimpleIUnknownImpl<IClassFactory>::`vftable';
    v8[2] = 1;
    ModuleRefCounter::AddRef();
    *((_QWORD *)v8 + 2) = i;
    *(_QWORD *)v8 = &ClassFactory::`vftable';
    v11 = v8;
    v9 = ((__int64 (__fastcall *)(_DWORD *, const struct _GUID *, void **))ClassFactory::`vftable')(v8, a2, a3);
  }
  else
  {
    v11 = 0;
    v9 = -2147024882;
  }
  ATL::CComPtrBase<ISupportErrorInfo>::~CComPtrBase<ISupportErrorInfo>(&v11);
  return v9;
}

```

## disassembly

```asm
0x180011d80  push    rbx
0x180011d82  push    rbp
0x180011d83  push    rsi
0x180011d84  push    rdi
0x180011d85  sub     rsp, 28h
0x180011d89  mov     qword ptr [r8], 0
0x180011d90  mov     rsi, r8
0x180011d93  mov     rbx, cs:off_18001C1F8
0x180011d9a  mov     rbp, rdx
0x180011d9d  lea     rax, off_18001C1F8
0x180011da4  cmp     rbx, rax
0x180011da7  jz      loc_180011E37
0x180011dad  mov     r8, [rbx+10h]
0x180011db1  mov     rax, [rcx]
0x180011db4  sub     rax, [r8]
0x180011db7  jnz     short loc_180011DC1
0x180011db9  mov     rax, [rcx+8]
0x180011dbd  sub     rax, [r8+8]
0x180011dc1  test    rax, rax
0x180011dc4  jz      short loc_180011DCB
0x180011dc6  mov     rbx, [rbx]
0x180011dc9  jmp     short loc_180011D9D
0x180011dcb  mov     ecx, 18h; Size
0x180011dd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011dd5  mov     rdi, rax
0x180011dd8  test    rax, rax
0x180011ddb  jz      short loc_180011E1B
0x180011ddd  lea     rax, ??_7?$SimpleIUnknownImpl@UIClassFactory@@@@6B@; const SimpleIUnknownImpl<IClassFactory>::`vftable'
0x180011de4  mov     [rdi], rax
0x180011de7  mov     dword ptr [rdi+8], 1
0x180011dee  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180011df3  lea     rax, ??_7ClassFactory@@6B@; const ClassFactory::`vftable'
0x180011dfa  mov     [rdi+10h], rbx
0x180011dfe  mov     [rdi], rax
0x180011e01  mov     r8, rsi
0x180011e04  mov     rax, [rax]
0x180011e07  mov     rdx, rbp
0x180011e0a  mov     rcx, rdi
0x180011e0d  mov     [rsp+48h+arg_10], rdi
0x180011e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e17  mov     ebx, eax
0x180011e19  jmp     short loc_180011E29
0x180011e1b  mov     [rsp+48h+arg_10], 0
0x180011e24  mov     ebx, 8007000Eh
0x180011e29  lea     rcx, [rsp+48h+arg_10]
0x180011e2e  call    ??1?$CComPtrBase@UISupportErrorInfo@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISupportErrorInfo>::~CComPtrBase<ISupportErrorInfo>(void)
0x180011e33  mov     eax, ebx
0x180011e35  jmp     short loc_180011E3C
0x180011e37  mov     eax, 80040111h
0x180011e3c  add     rsp, 28h
0x180011e40  pop     rdi
0x180011e41  pop     rsi
0x180011e42  pop     rbp
0x180011e43  pop     rbx
0x180011e44  retn
```
