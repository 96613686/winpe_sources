# ClassFactory::CreateFactory(_GUID const &,_GUID const &,void * *)

- ea: `0x180010500`
- end: `0x1800105c5`
- name: `?CreateFactory@ClassFactory@@SAJAEBU_GUID@@0PEAPEAX@Z`
- size: `197`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800031c0`

## callees

- `0x180001078`
- `0x1800020b4`
- `0x1800021a4`
- `0x180010500`
- `0x180012010`

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
  for ( i = (_UNKNOWN **)off_1800194E0; ; i = (_UNKNOWN **)*i )
  {
    if ( i == &off_1800194E0 )
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
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
  return v9;
}

```

## disassembly

```asm
0x180010500  push    rbx
0x180010502  push    rbp
0x180010503  push    rsi
0x180010504  push    rdi
0x180010505  sub     rsp, 28h
0x180010509  mov     qword ptr [r8], 0
0x180010510  mov     rsi, r8
0x180010513  mov     rbx, cs:off_1800194E0
0x18001051a  mov     rbp, rdx
0x18001051d  lea     rax, off_1800194E0
0x180010524  cmp     rbx, rax
0x180010527  jz      loc_1800105B7
0x18001052d  mov     r8, [rbx+10h]
0x180010531  mov     rax, [rcx]
0x180010534  sub     rax, [r8]
0x180010537  jnz     short loc_180010541
0x180010539  mov     rax, [rcx+8]
0x18001053d  sub     rax, [r8+8]
0x180010541  test    rax, rax
0x180010544  jz      short loc_18001054B
0x180010546  mov     rbx, [rbx]
0x180010549  jmp     short loc_18001051D
0x18001054b  mov     ecx, 18h; Size
0x180010550  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010555  mov     rdi, rax
0x180010558  test    rax, rax
0x18001055b  jz      short loc_18001059B
0x18001055d  lea     rax, ??_7?$SimpleIUnknownImpl@UIClassFactory@@@@6B@; const SimpleIUnknownImpl<IClassFactory>::`vftable'
0x180010564  mov     [rdi], rax
0x180010567  mov     dword ptr [rdi+8], 1
0x18001056e  call    ?AddRef@ModuleRefCounter@@SAXXZ; ModuleRefCounter::AddRef(void)
0x180010573  lea     rax, ??_7ClassFactory@@6B@; const ClassFactory::`vftable'
0x18001057a  mov     [rdi+10h], rbx
0x18001057e  mov     [rdi], rax
0x180010581  mov     r8, rsi
0x180010584  mov     rax, [rax]
0x180010587  mov     rdx, rbp
0x18001058a  mov     rcx, rdi
0x18001058d  mov     [rsp+48h+arg_10], rdi
0x180010592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010597  mov     ebx, eax
0x180010599  jmp     short loc_1800105A9
0x18001059b  mov     [rsp+48h+arg_10], 0
0x1800105a4  mov     ebx, 8007000Eh
0x1800105a9  lea     rcx, [rsp+48h+arg_10]
0x1800105ae  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800105b3  mov     eax, ebx
0x1800105b5  jmp     short loc_1800105BC
0x1800105b7  mov     eax, 80040111h
0x1800105bc  add     rsp, 28h
0x1800105c0  pop     rdi
0x1800105c1  pop     rsi
0x1800105c2  pop     rbp
0x1800105c3  pop     rbx
0x1800105c4  retn
```
