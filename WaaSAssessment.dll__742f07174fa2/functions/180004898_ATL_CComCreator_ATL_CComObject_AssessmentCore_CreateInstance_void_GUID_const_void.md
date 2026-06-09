# ATL::CComCreator<ATL::CComObject<AssessmentCore>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004898`
- end: `0x180004a3c`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VAssessmentCore@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004870`

## callees

- `0x1800021a4`
- `0x180004898`
- `0x180004d6c`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<AssessmentCore>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v6; // esi
  char *v7; // rax
  char *v8; // rbx
  signed __int32 v9; // eax
  int v10; // ecx
  int v11; // eax
  signed __int32 v12; // eax
  char *v15; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (char *)operator new(0x920u);
    v8 = v7;
    if ( v7 )
    {
      *((_DWORD *)v7 + 2) = 0;
      *((_OWORD *)v7 + 1) = 0;
      *((_OWORD *)v7 + 2) = 0;
      *((_QWORD *)v7 + 6) = 0;
      v7[56] = 0;
      *((_QWORD *)v7 + 26) = &DeviceAttributes::`vftable';
      *((_DWORD *)v7 + 18) = 30;
      *((_DWORD *)v7 + 19) = 15;
      *((_DWORD *)v7 + 20) = 5;
      *((_DWORD *)v7 + 21) = 90;
      *((_DWORD *)v7 + 22) = 60;
      *(_QWORD *)(v7 + 92) = 30;
      *((_QWORD *)v7 + 290) = 0;
      *((_QWORD *)v7 + 24) = 0;
      *((_QWORD *)v7 + 25) = 0;
      *(_QWORD *)v7 = &ATL::CComObject<AssessmentCore>::`vftable';
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
      v9 = *((_DWORD *)v8 + 2);
    while ( v9 != 0x7FFFFFFF && v9 != _InterlockedCompareExchange((volatile signed __int32 *)v8 + 2, v9 + 1, v9) );
    v10 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v8 + 16));
    if ( v10 >= 0 )
      v8[56] = 1;
    v11 = 0;
    if ( v10 < 0 )
      v11 = v10;
    v6 = 0;
    if ( v11 < 0 )
      v6 = v11;
    do
      v12 = *((_DWORD *)v8 + 2);
    while ( v12 != 0x7FFFFFFF && v12 != _InterlockedCompareExchange((volatile signed __int32 *)v8 + 2, v12 - 1, v12) );
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(char *, __int64, _QWORD *))v8)(v8, v4, v3)) != 0 )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v8 + 272LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180004898  mov     [rsp+arg_10], r8
0x18000489d  mov     [rsp+arg_8], rdx
0x1800048a2  mov     [rsp+arg_0], rcx
0x1800048a7  push    rbx
0x1800048a8  push    rsi
0x1800048a9  push    r12
0x1800048ab  push    r14
0x1800048ad  push    r15
0x1800048af  sub     rsp, 20h
0x1800048b3  mov     r14, r8
0x1800048b6  mov     r15, rdx
0x1800048b9  test    r8, r8
0x1800048bc  jnz     short loc_1800048C8
0x1800048be  mov     eax, 80004003h
0x1800048c3  jmp     loc_180004A2F
0x1800048c8  mov     qword ptr [r8], 0
0x1800048cf  mov     esi, 8007000Eh
0x1800048d4  mov     dword ptr [rsp+48h+arg_0], esi
0x1800048d8  mov     [rsp+48h+arg_18], 0
0x1800048e1  mov     ecx, 920h; Size
0x1800048e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800048eb  mov     rbx, rax
0x1800048ee  test    rbx, rbx
0x1800048f1  jz      loc_180004986
0x1800048f7  mov     dword ptr [rax+8], 0
0x1800048fe  xorps   xmm0, xmm0
0x180004901  xor     eax, eax
0x180004903  movups  xmmword ptr [rbx+10h], xmm0
0x180004907  movups  xmmword ptr [rbx+20h], xmm0
0x18000490b  mov     [rbx+30h], rax
0x18000490f  mov     [rbx+38h], al
0x180004912  lea     rax, ??_7DeviceAttributes@@6B@; const DeviceAttributes::`vftable'
0x180004919  mov     [rbx+0D0h], rax
0x180004920  mov     eax, 1Eh
0x180004925  mov     [rbx+48h], eax
0x180004928  mov     dword ptr [rbx+4Ch], 0Fh
0x18000492f  mov     dword ptr [rbx+50h], 5
0x180004936  mov     dword ptr [rbx+54h], 5Ah ; 'Z'
0x18000493d  mov     dword ptr [rbx+58h], 3Ch ; '<'
0x180004944  mov     [rbx+5Ch], rax
0x180004948  mov     qword ptr [rbx+910h], 0
0x180004953  mov     qword ptr [rbx+0C0h], 0
0x18000495e  mov     qword ptr [rbx+0C8h], 0
0x180004969  lea     rax, ??_7?$CComObject@VAssessmentCore@@@ATL@@6B@; const ATL::CComObject<AssessmentCore>::`vftable'
0x180004970  mov     [rbx], rax
0x180004973  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000497a  mov     rax, [rcx]
0x18000497d  mov     rax, [rax+8]
0x180004981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004986  mov     [rsp+48h+arg_18], rbx
0x18000498b  jmp     short loc_1800049A0
0x18000498d  mov     r14, [rsp+48h+arg_10]
0x180004992  mov     r15, [rsp+48h+arg_8]
0x180004997  mov     esi, dword ptr [rsp+48h+arg_0]
0x18000499b  mov     rbx, [rsp+48h+arg_18]
0x1800049a0  test    rbx, rbx
0x1800049a3  jz      loc_180004A2D
0x1800049a9  mov     r12d, 7FFFFFFFh
0x1800049af  jmp     short loc_1800049BB
0x1800049b1  lea     ecx, [rax+1]
0x1800049b4  lock cmpxchg [rbx+8], ecx
0x1800049b9  jz      short loc_1800049C3
0x1800049bb  mov     eax, [rbx+8]
0x1800049be  cmp     eax, r12d
0x1800049c1  jnz     short loc_1800049B1
0x1800049c3  lea     rcx, [rbx+10h]; this
0x1800049c7  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800049cc  mov     ecx, eax
0x1800049ce  test    eax, eax
0x1800049d0  js      short loc_1800049D6
0x1800049d2  mov     byte ptr [rbx+38h], 1
0x1800049d6  xor     eax, eax
0x1800049d8  test    ecx, ecx
0x1800049da  cmovs   eax, ecx
0x1800049dd  xor     esi, esi
0x1800049df  test    eax, eax
0x1800049e1  cmovs   esi, eax
0x1800049e4  jmp     short loc_1800049F0
0x1800049e6  lea     ecx, [rax-1]
0x1800049e9  lock cmpxchg [rbx+8], ecx
0x1800049ee  jz      short loc_1800049F8
0x1800049f0  mov     eax, [rbx+8]
0x1800049f3  cmp     eax, r12d
0x1800049f6  jnz     short loc_1800049E6
0x1800049f8  test    esi, esi
0x1800049fa  jnz     short loc_180004A16
0x1800049fc  mov     rax, [rbx]
0x1800049ff  mov     r8, r14
0x180004a02  mov     rdx, r15
0x180004a05  mov     rcx, rbx
0x180004a08  mov     rax, [rax]
0x180004a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a10  mov     esi, eax
0x180004a12  test    eax, eax
0x180004a14  jz      short loc_180004A2D
0x180004a16  mov     r8, [rbx]
0x180004a19  mov     edx, 1
0x180004a1e  mov     rcx, rbx
0x180004a21  mov     rax, [r8+110h]
0x180004a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a2d  mov     eax, esi
0x180004a2f  add     rsp, 20h
0x180004a33  pop     r15
0x180004a35  pop     r14
0x180004a37  pop     r12
0x180004a39  pop     rsi
0x180004a3a  pop     rbx
0x180004a3b  retn
```
