# ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x140005c30`
- end: `0x140005d0f`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000196c`
- `0x140001f64`
- `0x140005c30`
- `0x140005dec`
- `0x140008010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140005ced`
- `KERNEL32!DeleteCriticalSection` at `0x140005ced`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectNoLock<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // rdi

  if ( !a3 )
    return 2147500035LL;
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
    *(_QWORD *)v8 = &ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable';
    *((_QWORD *)v8 + 8) = a1;
    v10 = v8 + 56;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 16));
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0) )
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
0x140005c30  push    rbx
0x140005c32  push    rbp
0x140005c33  push    rsi
0x140005c34  push    rdi
0x140005c35  push    r14
0x140005c37  push    r15
0x140005c39  sub     rsp, 28h
0x140005c3d  mov     r14, r8
0x140005c40  mov     r15, rdx
0x140005c43  mov     rdi, rcx
0x140005c46  test    r8, r8
0x140005c49  jnz     short loc_140005C55
0x140005c4b  mov     eax, 80004003h
0x140005c50  jmp     loc_140005D02
0x140005c55  mov     ecx, 48h ; 'H'; Size
0x140005c5a  mov     qword ptr [r8], 0
0x140005c61  mov     esi, 8007000Eh
0x140005c66  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005c6b  mov     rbx, rax
0x140005c6e  test    rax, rax
0x140005c71  jz      loc_140005D00
0x140005c77  mov     dword ptr [rax+8], 0
0x140005c7e  lea     rcx, [rbx+10h]; this
0x140005c82  xor     eax, eax
0x140005c84  xorps   xmm0, xmm0
0x140005c87  movups  xmmword ptr [rbx+10h], xmm0
0x140005c8b  movups  xmmword ptr [rbx+20h], xmm0
0x140005c8f  mov     [rbx+30h], rax
0x140005c93  mov     [rbx+38h], al
0x140005c96  lea     rax, ??_7?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable'
0x140005c9d  mov     [rbx], rax
0x140005ca0  mov     [rbx+40h], rdi
0x140005ca4  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140005ca9  lea     rdi, [rbx+38h]
0x140005cad  mov     esi, eax
0x140005caf  test    eax, eax
0x140005cb1  js      short loc_140005CD0
0x140005cb3  mov     byte ptr [rdi], 1
0x140005cb6  mov     r8, r14
0x140005cb9  mov     rax, [rbx]
0x140005cbc  mov     rdx, r15
0x140005cbf  mov     rcx, rbx
0x140005cc2  mov     rax, [rax]
0x140005cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cca  mov     esi, eax
0x140005ccc  test    eax, eax
0x140005cce  jz      short loc_140005D00
0x140005cd0  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x140005cd7  mov     dword ptr [rbx+8], 0C0000001h
0x140005cde  mov     [rbx], rax
0x140005ce1  cmp     byte ptr [rdi], 0
0x140005ce4  jz      short loc_140005CF3
0x140005ce6  lea     rcx, [rbx+10h]; lpCriticalSection
0x140005cea  mov     byte ptr [rdi], 0
0x140005ced  call    cs:__imp_DeleteCriticalSection
0x140005cf3  mov     edx, 48h ; 'H'
0x140005cf8  mov     rcx, rbx; Block
0x140005cfb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005d00  mov     eax, esi
0x140005d02  add     rsp, 28h
0x140005d06  pop     r15
0x140005d08  pop     r14
0x140005d0a  pop     rdi
0x140005d0b  pop     rsi
0x140005d0c  pop     rbp
0x140005d0d  pop     rbx
0x140005d0e  retn
```
