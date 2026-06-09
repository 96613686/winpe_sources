# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180007800`
- end: `0x1800078da`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `218`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001be0`
- `0x180001c04`
- `0x180007800`
- `0x180008290`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800078bd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800078bd`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
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
    *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
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
0x180007800  push    rbx
0x180007802  push    rbp
0x180007803  push    rsi
0x180007804  push    rdi
0x180007805  push    r14
0x180007807  push    r15
0x180007809  sub     rsp, 28h
0x18000780d  mov     r14, r8
0x180007810  mov     r15, rdx
0x180007813  mov     rdi, rcx
0x180007816  test    r8, r8
0x180007819  jnz     short loc_180007825
0x18000781b  mov     eax, 80004003h
0x180007820  jmp     loc_1800078CD
0x180007825  mov     ecx, 48h ; 'H'; Size
0x18000782a  mov     qword ptr [r8], 0
0x180007831  mov     esi, 8007000Eh
0x180007836  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000783b  mov     rbx, rax
0x18000783e  test    rax, rax
0x180007841  jz      loc_1800078CB
0x180007847  mov     dword ptr [rax+8], 0
0x18000784e  lea     rcx, [rbx+10h]; this
0x180007852  xor     eax, eax
0x180007854  xorps   xmm0, xmm0
0x180007857  movups  xmmword ptr [rbx+10h], xmm0
0x18000785b  movups  xmmword ptr [rbx+20h], xmm0
0x18000785f  mov     [rbx+30h], rax
0x180007863  mov     [rbx+38h], al
0x180007866  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000786d  mov     [rbx], rax
0x180007870  mov     [rbx+40h], rdi
0x180007874  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180007879  lea     rdi, [rbx+38h]
0x18000787d  mov     esi, eax
0x18000787f  test    eax, eax
0x180007881  js      short loc_1800078A0
0x180007883  mov     byte ptr [rdi], 1
0x180007886  mov     r8, r14
0x180007889  mov     rax, [rbx]
0x18000788c  mov     rdx, r15
0x18000788f  mov     rcx, rbx
0x180007892  mov     rax, [rax]
0x180007895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000789a  mov     esi, eax
0x18000789c  test    eax, eax
0x18000789e  jz      short loc_1800078CB
0x1800078a0  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800078a7  mov     dword ptr [rbx+8], 0C0000001h
0x1800078ae  mov     [rbx], rax
0x1800078b1  cmp     byte ptr [rdi], 0
0x1800078b4  jz      short loc_1800078C3
0x1800078b6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800078ba  mov     byte ptr [rdi], 0
0x1800078bd  call    cs:__imp_DeleteCriticalSection
0x1800078c3  mov     rcx, rbx; Block
0x1800078c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800078cb  mov     eax, esi
0x1800078cd  add     rsp, 28h
0x1800078d1  pop     r15
0x1800078d3  pop     r14
0x1800078d5  pop     rdi
0x1800078d6  pop     rsi
0x1800078d7  pop     rbp
0x1800078d8  pop     rbx
0x1800078d9  retn
```
