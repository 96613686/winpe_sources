# ATL::CComCreator<ATL::CComObject<CPolicyComponent>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002950`
- end: `0x180002a73`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPolicyComponent@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800028f0`

## callees

- `0x180002950`
- `0x180002a80`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002992`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002992`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CPolicyComponent>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v5; // edi
  _DWORD *v6; // rax
  _DWORD *v7; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v5 = -2147024882;
  v6 = LocalAlloc(0x40u, 0x48u);
  v7 = v6;
  if ( v6 )
  {
    v6[2] = 0;
    *((_OWORD *)v6 + 1) = 0;
    *((_OWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 6) = 0;
    *((_BYTE *)v6 + 56) = 0;
    *((_BYTE *)v6 + 64) = 0;
    v6[17] = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CPolicyComponent>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  else
  {
    v7 = 0;
  }
  if ( v7 )
  {
    v5 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v7 + 4));
    if ( v5 < 0
      || (*((_BYTE *)v7 + 56) = 1, (v5 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v7)(v7, a2, a3)) != 0) )
    {
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v7 + 72LL))(v7, 1);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002950  mov     [rsp+arg_10], r8
0x180002955  mov     [rsp+arg_8], rdx
0x18000295a  mov     [rsp+arg_0], rcx
0x18000295f  push    rbx
0x180002960  push    rsi
0x180002961  push    rdi
0x180002962  push    r14
0x180002964  push    r15
0x180002966  sub     rsp, 20h
0x18000296a  mov     rsi, r8
0x18000296d  mov     r15, rdx
0x180002970  test    r8, r8
0x180002973  jz      loc_180002A36
0x180002979  xor     r14d, r14d
0x18000297c  mov     [r8], r14
0x18000297f  mov     edi, 8007000Eh
0x180002984  mov     dword ptr [rsp+48h+arg_0], edi
0x180002988  mov     edx, 48h ; 'H'; uBytes
0x18000298d  mov     ecx, 40h ; '@'; uFlags
0x180002992  call    cs:__imp_LocalAlloc
0x180002999  nop     dword ptr [rax+rax+00h]
0x18000299e  mov     rbx, rax
0x1800029a1  mov     [rsp+48h+arg_18], rax
0x1800029a6  test    rax, rax
0x1800029a9  jz      loc_180002A31
0x1800029af  mov     [rax+8], r14d
0x1800029b3  xorps   xmm0, xmm0
0x1800029b6  xor     eax, eax
0x1800029b8  movups  xmmword ptr [rbx+10h], xmm0
0x1800029bc  movups  xmmword ptr [rbx+20h], xmm0
0x1800029c0  mov     [rbx+30h], rax
0x1800029c4  mov     [rbx+38h], al
0x1800029c7  mov     [rbx+40h], al
0x1800029ca  mov     [rbx+44h], r14d
0x1800029ce  lea     rax, ??_7?$CComObject@VCPolicyComponent@@@ATL@@6B@; const ATL::CComObject<CPolicyComponent>::`vftable'
0x1800029d5  mov     [rbx], rax
0x1800029d8  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800029df  mov     rax, [rcx]
0x1800029e2  mov     rax, [rax+8]
0x1800029e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029eb  mov     [rsp+48h+arg_18], rbx
0x1800029f0  test    rbx, rbx
0x1800029f3  jz      short loc_180002A22
0x1800029f5  lea     rcx, [rbx+10h]; this
0x1800029f9  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800029fe  mov     edi, eax
0x180002a00  test    eax, eax
0x180002a02  js      short loc_180002A5D
0x180002a04  mov     byte ptr [rbx+38h], 1
0x180002a08  mov     rax, [rbx]
0x180002a0b  mov     r8, rsi
0x180002a0e  mov     rdx, r15
0x180002a11  mov     rcx, rbx
0x180002a14  mov     rax, [rax]
0x180002a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a1c  mov     edi, eax
0x180002a1e  test    eax, eax
0x180002a20  jnz     short loc_180002A5D
0x180002a22  mov     eax, edi
0x180002a24  add     rsp, 20h
0x180002a28  pop     r15
0x180002a2a  pop     r14
0x180002a2c  pop     rdi
0x180002a2d  pop     rsi
0x180002a2e  pop     rbx
0x180002a2f  retn
0x180002a31  mov     rbx, r14
0x180002a34  jmp     short loc_1800029EB
0x180002a36  mov     eax, 80004003h
0x180002a3b  add     rsp, 20h
0x180002a3f  pop     r15
0x180002a41  pop     r14
0x180002a43  pop     rdi
0x180002a44  pop     rsi
0x180002a45  pop     rbx
0x180002a46  retn
0x180002a48  mov     rsi, [rsp+48h+arg_10]
0x180002a4d  mov     r15, [rsp+48h+arg_8]
0x180002a52  mov     edi, dword ptr [rsp+48h+arg_0]
0x180002a56  mov     rbx, [rsp+48h+arg_18]
0x180002a5b  jmp     short loc_1800029F0
0x180002a5d  mov     rax, [rbx]
0x180002a60  mov     edx, 1
0x180002a65  mov     rcx, rbx
0x180002a68  mov     rax, [rax+48h]
0x180002a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a71  jmp     short loc_180002A22
```
