# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180020500`
- end: `0x18002062a`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `298`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800013f4`
- `0x180001914`
- `0x180020500`
- `0x1800207fc`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020606`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180020606`

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
0x180020500  mov     [rsp+arg_10], r8
0x180020505  mov     [rsp+arg_8], rdx
0x18002050a  mov     [rsp+arg_0], rcx
0x18002050f  push    rbx
0x180020510  push    rsi
0x180020511  push    r12
0x180020513  push    r13
0x180020515  push    r14
0x180020517  push    r15
0x180020519  sub     rsp, 38h
0x18002051d  mov     r15, r8
0x180020520  mov     r12, rdx
0x180020523  mov     r14, rcx
0x180020526  test    r8, r8
0x180020529  jnz     short loc_180020535
0x18002052b  mov     eax, 80004003h
0x180020530  jmp     loc_18002061B
0x180020535  mov     qword ptr [r8], 0
0x18002053c  mov     esi, 8007000Eh
0x180020541  mov     [rsp+68h+arg_18], esi
0x180020548  mov     [rsp+68h+var_48], 0
0x180020551  mov     ecx, 48h ; 'H'; Size
0x180020556  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002055b  mov     rbx, rax
0x18002055e  test    rbx, rbx
0x180020561  jz      short loc_180020588
0x180020563  mov     dword ptr [rax+8], 0
0x18002056a  xorps   xmm0, xmm0
0x18002056d  xor     eax, eax
0x18002056f  movups  xmmword ptr [rbx+10h], xmm0
0x180020573  movups  xmmword ptr [rbx+20h], xmm0
0x180020577  mov     [rbx+30h], rax
0x18002057b  mov     [rbx+38h], al
0x18002057e  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180020585  mov     [rbx], rax
0x180020588  mov     [rsp+68h+var_48], rbx
0x18002058d  jmp     short loc_1800205AD
0x18002058f  mov     r15, [rsp+68h+arg_10]
0x180020597  mov     r12, [rsp+68h+arg_8]
0x18002059c  mov     r14, [rsp+68h+arg_0]
0x1800205a1  mov     esi, [rsp+68h+arg_18]
0x1800205a8  mov     rbx, [rsp+68h+var_48]
0x1800205ad  test    rbx, rbx
0x1800205b0  jz      short loc_180020619
0x1800205b2  mov     [rbx+40h], r14
0x1800205b6  lea     rcx, [rbx+10h]; this
0x1800205ba  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800205bf  mov     esi, eax
0x1800205c1  lea     r14, [rbx+38h]
0x1800205c5  test    eax, eax
0x1800205c7  js      short loc_1800205E7
0x1800205c9  mov     byte ptr [r14], 1
0x1800205cd  mov     rax, [rbx]
0x1800205d0  mov     r8, r15
0x1800205d3  mov     rdx, r12
0x1800205d6  mov     rcx, rbx
0x1800205d9  mov     rax, [rax]
0x1800205dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205e1  mov     esi, eax
0x1800205e3  test    eax, eax
0x1800205e5  jz      short loc_180020619
0x1800205e7  mov     dword ptr [rbx+8], 0C0000001h
0x1800205ee  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800205f5  mov     [rbx], rax
0x1800205f8  cmp     byte ptr [r14], 0
0x1800205fc  jz      short loc_18002060C
0x1800205fe  mov     byte ptr [r14], 0
0x180020602  lea     rcx, [rbx+10h]; lpCriticalSection
0x180020606  call    cs:__imp_DeleteCriticalSection
0x18002060c  mov     edx, 48h ; 'H'
0x180020611  mov     rcx, rbx; Block
0x180020614  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020619  mov     eax, esi
0x18002061b  add     rsp, 38h
0x18002061f  pop     r15
0x180020621  pop     r14
0x180020623  pop     r13
0x180020625  pop     r12
0x180020627  pop     rsi
0x180020628  pop     rbx
0x180020629  retn
```
