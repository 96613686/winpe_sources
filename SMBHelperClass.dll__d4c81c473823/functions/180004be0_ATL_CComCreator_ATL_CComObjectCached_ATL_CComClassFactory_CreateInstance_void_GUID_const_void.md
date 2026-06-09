# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004be0`
- end: `0x180004d06`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000123c`
- `0x180004be0`
- `0x1800058dc`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004cef`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004cef`
- `KERNEL32!DeleteCriticalSection` at `0x180004ce6`
- `KERNEL32!DeleteCriticalSection` at `0x180004ce6`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r15
  __int64 v4; // r12
  __int64 v5; // r14
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // r14
  char *v11; // [rsp+20h] [rbp-48h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x48u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 6) = 0;
      v8[56] = 0;
      *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    }
    v11 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v7 = -2147024882;
    v9 = v11;
  }
  if ( v9 )
  {
    *((_QWORD *)v9 + 8) = v5;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 16));
    v10 = v9 + 56;
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactory::`vftable';
      if ( *v10 )
      {
        *v10 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      operator delete(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004be0  mov     [rsp+arg_10], r8
0x180004be5  mov     [rsp+arg_8], rdx
0x180004bea  mov     [rsp+arg_0], rcx
0x180004bef  push    rbx
0x180004bf0  push    rsi
0x180004bf1  push    r12
0x180004bf3  push    r13
0x180004bf5  push    r14
0x180004bf7  push    r15
0x180004bf9  sub     rsp, 38h
0x180004bfd  mov     r15, r8
0x180004c00  mov     r12, rdx
0x180004c03  mov     r14, rcx
0x180004c06  test    r8, r8
0x180004c09  jnz     short loc_180004C15
0x180004c0b  mov     eax, 80004003h
0x180004c10  jmp     loc_180004CF7
0x180004c15  mov     qword ptr [r8], 0
0x180004c1c  mov     esi, 8007000Eh
0x180004c21  mov     [rsp+68h+arg_18], esi
0x180004c28  mov     [rsp+68h+var_48], 0
0x180004c31  mov     ecx, 48h ; 'H'; Size
0x180004c36  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c3b  mov     rbx, rax
0x180004c3e  test    rbx, rbx
0x180004c41  jz      short loc_180004C68
0x180004c43  mov     dword ptr [rax+8], 0
0x180004c4a  xorps   xmm0, xmm0
0x180004c4d  xor     eax, eax
0x180004c4f  movups  xmmword ptr [rbx+10h], xmm0
0x180004c53  movups  xmmword ptr [rbx+20h], xmm0
0x180004c57  mov     [rbx+30h], rax
0x180004c5b  mov     [rbx+38h], al
0x180004c5e  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180004c65  mov     [rbx], rax
0x180004c68  mov     [rsp+68h+var_48], rbx
0x180004c6d  jmp     short loc_180004C8D
0x180004c6f  mov     r15, [rsp+68h+arg_10]
0x180004c77  mov     r12, [rsp+68h+arg_8]
0x180004c7c  mov     r14, [rsp+68h+arg_0]
0x180004c81  mov     esi, [rsp+68h+arg_18]
0x180004c88  mov     rbx, [rsp+68h+var_48]
0x180004c8d  test    rbx, rbx
0x180004c90  jz      short loc_180004CF5
0x180004c92  mov     [rbx+40h], r14
0x180004c96  lea     rcx, [rbx+10h]; this
0x180004c9a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004c9f  mov     esi, eax
0x180004ca1  lea     r14, [rbx+38h]
0x180004ca5  test    eax, eax
0x180004ca7  js      short loc_180004CC7
0x180004ca9  mov     byte ptr [r14], 1
0x180004cad  mov     rax, [rbx]
0x180004cb0  mov     r8, r15
0x180004cb3  mov     rdx, r12
0x180004cb6  mov     rcx, rbx
0x180004cb9  mov     rax, [rax]
0x180004cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc1  mov     esi, eax
0x180004cc3  test    eax, eax
0x180004cc5  jz      short loc_180004CF5
0x180004cc7  mov     dword ptr [rbx+8], 0C0000001h
0x180004cce  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180004cd5  mov     [rbx], rax
0x180004cd8  cmp     byte ptr [r14], 0
0x180004cdc  jz      short loc_180004CEC
0x180004cde  mov     byte ptr [r14], 0
0x180004ce2  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004ce6  call    cs:__imp_DeleteCriticalSection
0x180004cec  mov     rcx, rbx
0x180004cef  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004cf5  mov     eax, esi
0x180004cf7  add     rsp, 38h
0x180004cfb  pop     r15
0x180004cfd  pop     r14
0x180004cff  pop     r13
0x180004d01  pop     r12
0x180004d03  pop     rsi
0x180004d04  pop     rbx
0x180004d05  retn
```
