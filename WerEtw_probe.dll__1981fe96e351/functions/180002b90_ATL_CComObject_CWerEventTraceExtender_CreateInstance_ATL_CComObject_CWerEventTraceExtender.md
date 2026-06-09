# ATL::CComObject<CWerEventTraceExtender>::CreateInstance(ATL::CComObject<CWerEventTraceExtender> * *)

- ea: `0x180002b90`
- end: `0x180002cd6`
- name: `?CreateInstance@?$CComObject@VCWerEventTraceExtender@@@ATL@@SAJPEAPEAV12@@Z`
- size: `326`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800037d0`

## callees

- `0x1800018a0`
- `0x180002420`
- `0x180002b90`
- `0x180002f84`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWerEventTraceExtender>::CreateInstance(_QWORD *a1)
{
  _QWORD *v1; // r14
  int v3; // esi
  _DWORD *v4; // rdi
  _DWORD *v6; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = operator new(0xAE8u);
    v4[6] = 0;
    *((_OWORD *)v4 + 2) = 0;
    *((_OWORD *)v4 + 3) = 0;
    *((_QWORD *)v4 + 8) = 0;
    *((_BYTE *)v4 + 72) = 0;
    *((_QWORD *)v4 + 1) = 0;
    *((_QWORD *)v4 + 2) = 0;
    memset_0(v4 + 20, 0, 0xA50u);
    *((_QWORD *)v4 + 340) = 0;
    *((_QWORD *)v4 + 341) = 0;
    v4[684] = 0;
    *((_QWORD *)v4 + 343) = 0;
    *((_QWORD *)v4 + 344) = 0;
    *((_QWORD *)v4 + 345) = 0;
    *((_QWORD *)v4 + 346) = 0;
    *((_QWORD *)v4 + 347) = 0;
    *((_QWORD *)v4 + 348) = 0;
    *(_QWORD *)v4 = &ATL::CComObject<CWerEventTraceExtender>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v6 = v4;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v4 = v6;
  }
  if ( v4 )
  {
    v3 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v4 + 8));
    if ( v3 < 0 )
    {
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v4 + 136LL))(v4, 1);
      v4 = 0;
    }
    else
    {
      *((_BYTE *)v4 + 72) = 1;
      v3 = 0;
    }
  }
  *v1 = v4;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180002b90  mov     [rsp+arg_18], rsi
0x180002b95  mov     [rsp+arg_0], rcx
0x180002b9a  push    rdi
0x180002b9b  push    r14
0x180002b9d  push    r15
0x180002b9f  sub     rsp, 20h
0x180002ba3  mov     r14, rcx
0x180002ba6  test    rcx, rcx
0x180002ba9  jnz     short loc_180002BB5
0x180002bab  mov     eax, 80004003h
0x180002bb0  jmp     loc_180002CC7
0x180002bb5  mov     qword ptr [rcx], 0
0x180002bbc  mov     esi, 8007000Eh
0x180002bc1  mov     [rsp+38h+arg_8], esi
0x180002bc5  mov     [rsp+38h+arg_10], 0
0x180002bce  mov     ecx, 0AE8h; Size
0x180002bd3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002bd8  mov     rdi, rax
0x180002bdb  mov     dword ptr [rax+18h], 0
0x180002be2  xorps   xmm0, xmm0
0x180002be5  xor     eax, eax
0x180002be7  movups  xmmword ptr [rdi+20h], xmm0
0x180002beb  movups  xmmword ptr [rdi+30h], xmm0
0x180002bef  mov     [rdi+40h], rax
0x180002bf3  mov     [rdi+48h], al
0x180002bf6  mov     [rdi+8], rax
0x180002bfa  mov     [rdi+10h], rax
0x180002bfe  lea     rcx, [rdi+50h]; void *
0x180002c02  xor     edx, edx; Val
0x180002c04  mov     r8d, 0A50h; Size
0x180002c0a  call    memset_0
0x180002c0f  mov     qword ptr [rdi+0AA0h], 0
0x180002c1a  mov     qword ptr [rdi+0AA8h], 0
0x180002c25  mov     dword ptr [rdi+0AB0h], 0
0x180002c2f  xor     eax, eax
0x180002c31  mov     [rdi+0AB8h], rax
0x180002c38  mov     [rdi+0AC0h], rax
0x180002c3f  mov     [rdi+0AC8h], rax
0x180002c46  mov     [rdi+0AD0h], rax
0x180002c4d  mov     [rdi+0AD8h], rax
0x180002c54  mov     [rdi+0AE0h], rax
0x180002c5b  lea     rax, ??_7?$CComObject@VCWerEventTraceExtender@@@ATL@@6B@; const ATL::CComObject<CWerEventTraceExtender>::`vftable'
0x180002c62  mov     [rdi], rax
0x180002c65  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002c6c  mov     rax, [rcx]
0x180002c6f  mov     rax, [rax+8]
0x180002c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c78  mov     [rsp+38h+arg_10], rdi
0x180002c7d  jmp     short loc_180002C8D
0x180002c7f  mov     r14, [rsp+38h+arg_0]
0x180002c84  mov     esi, [rsp+38h+arg_8]
0x180002c88  mov     rdi, [rsp+38h+arg_10]
0x180002c8d  test    rdi, rdi
0x180002c90  jz      short loc_180002CC2
0x180002c92  lea     rcx, [rdi+20h]; this
0x180002c96  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002c9b  mov     esi, eax
0x180002c9d  test    eax, eax
0x180002c9f  js      short loc_180002CA9
0x180002ca1  mov     byte ptr [rdi+48h], 1
0x180002ca5  xor     esi, esi
0x180002ca7  jmp     short loc_180002CC2
0x180002ca9  mov     rdx, [rdi]
0x180002cac  mov     rax, [rdx+88h]
0x180002cb3  mov     edx, 1
0x180002cb8  mov     rcx, rdi
0x180002cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc0  xor     edi, edi
0x180002cc2  mov     [r14], rdi
0x180002cc5  mov     eax, esi
0x180002cc7  mov     rsi, [rsp+38h+arg_18]
0x180002ccc  add     rsp, 20h
0x180002cd0  pop     r15
0x180002cd2  pop     r14
0x180002cd4  pop     rdi
0x180002cd5  retn
```
