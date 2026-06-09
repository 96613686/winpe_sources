# ATL::CComCreator<ATL::CComObject<CDsmAdminControl>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009498`
- end: `0x1800095dc`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCDsmAdminControl@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `324`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009470`

## callees

- `0x18000137c`
- `0x180008efc`
- `0x180009498`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CDsmAdminControl>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v6; // edi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  signed __int32 v9; // eax
  int v10; // ecx
  int v11; // eax
  signed __int32 v12; // eax
  _DWORD *v15; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = operator new(0x40u);
    v8 = v7;
    if ( v7 )
    {
      v7[2] = 0;
      *((_OWORD *)v7 + 1) = 0;
      *((_OWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 6) = 0;
      *((_BYTE *)v7 + 56) = 0;
      *(_QWORD *)v7 = &ATL::CComObject<CDsmAdminControl>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v15 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v15;
  }
  if ( v8 )
  {
    do
      v9 = v8[2];
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange(v8 + 2, v9 + 1, v9) );
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v8 + 4));
    if ( v10 >= 0 )
      *((_BYTE *)v8 + 56) = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    do
      v12 = v8[2];
    while ( v12 != 0x7FFFFFFF && v12 != _InterlockedCompareExchange(v8 + 2, v12 - 1, v12) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 56LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180009498  mov     [rsp+arg_10], r8
0x18000949d  mov     [rsp+arg_8], rdx
0x1800094a2  mov     [rsp+arg_0], rcx
0x1800094a7  push    rbx
0x1800094a8  push    rsi
0x1800094a9  push    rdi
0x1800094aa  push    r14
0x1800094ac  push    r15
0x1800094ae  sub     rsp, 20h
0x1800094b2  mov     rsi, r8
0x1800094b5  mov     r14, rdx
0x1800094b8  test    r8, r8
0x1800094bb  jnz     short loc_1800094C7
0x1800094bd  mov     eax, 80004003h
0x1800094c2  jmp     loc_1800095D0
0x1800094c7  mov     qword ptr [r8], 0
0x1800094ce  mov     edi, 8007000Eh
0x1800094d3  mov     dword ptr [rsp+48h+arg_0], edi
0x1800094d7  mov     [rsp+48h+arg_18], 0
0x1800094e0  mov     ecx, 40h ; '@'; Size
0x1800094e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800094ea  mov     rbx, rax
0x1800094ed  test    rbx, rbx
0x1800094f0  jz      short loc_18000952A
0x1800094f2  mov     dword ptr [rax+8], 0
0x1800094f9  xorps   xmm0, xmm0
0x1800094fc  xor     eax, eax
0x1800094fe  movups  xmmword ptr [rbx+10h], xmm0
0x180009502  movups  xmmword ptr [rbx+20h], xmm0
0x180009506  mov     [rbx+30h], rax
0x18000950a  mov     [rbx+38h], al
0x18000950d  lea     rax, ??_7?$CComObject@VCDsmAdminControl@@@ATL@@6B@; const ATL::CComObject<CDsmAdminControl>::`vftable'
0x180009514  mov     [rbx], rax
0x180009517  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000951e  mov     rax, [rcx]
0x180009521  mov     rax, [rax+8]
0x180009525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000952a  mov     [rsp+48h+arg_18], rbx
0x18000952f  jmp     short loc_180009544
0x180009531  mov     rsi, [rsp+48h+arg_10]
0x180009536  mov     r14, [rsp+48h+arg_8]
0x18000953b  mov     edi, dword ptr [rsp+48h+arg_0]
0x18000953f  mov     rbx, [rsp+48h+arg_18]
0x180009544  test    rbx, rbx
0x180009547  jz      loc_1800095CE
0x18000954d  mov     r15d, 7FFFFFFFh
0x180009553  jmp     short loc_18000955F
0x180009555  lea     ecx, [rax+1]
0x180009558  lock cmpxchg [rbx+8], ecx
0x18000955d  jz      short loc_180009567
0x18000955f  mov     eax, [rbx+8]
0x180009562  cmp     eax, r15d
0x180009565  jnz     short loc_180009555
0x180009567  lea     rcx, [rbx+10h]; this
0x18000956b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180009570  mov     ecx, eax
0x180009572  test    eax, eax
0x180009574  js      short loc_18000957A
0x180009576  mov     byte ptr [rbx+38h], 1
0x18000957a  xor     eax, eax
0x18000957c  test    ecx, ecx
0x18000957e  cmovs   eax, ecx
0x180009581  xor     edi, edi
0x180009583  test    eax, eax
0x180009585  cmovs   edi, eax
0x180009588  jmp     short loc_180009594
0x18000958a  lea     ecx, [rax-1]
0x18000958d  lock cmpxchg [rbx+8], ecx
0x180009592  jz      short loc_18000959C
0x180009594  mov     eax, [rbx+8]
0x180009597  cmp     eax, r15d
0x18000959a  jnz     short loc_18000958A
0x18000959c  test    edi, edi
0x18000959e  jnz     short loc_1800095BA
0x1800095a0  mov     rax, [rbx]
0x1800095a3  mov     r8, rsi
0x1800095a6  mov     rdx, r14
0x1800095a9  mov     rcx, rbx
0x1800095ac  mov     rax, [rax]
0x1800095af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095b4  mov     edi, eax
0x1800095b6  test    eax, eax
0x1800095b8  jz      short loc_1800095CE
0x1800095ba  mov     r8, [rbx]
0x1800095bd  mov     edx, 1
0x1800095c2  mov     rcx, rbx
0x1800095c5  mov     rax, [r8+38h]
0x1800095c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095ce  mov     eax, edi
0x1800095d0  add     rsp, 20h
0x1800095d4  pop     r15
0x1800095d6  pop     r14
0x1800095d8  pop     rdi
0x1800095d9  pop     rsi
0x1800095da  pop     rbx
0x1800095db  retn
```
