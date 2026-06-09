# ATL::CComCreator<ATL::CComAggObject<CMidi2SchedulerTransform>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004c34`
- end: `0x180004d3c`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCMidi2SchedulerTransform@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004c20`

## callees

- `0x180002050`
- `0x180004c34`
- `0x180005d08`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CMidi2SchedulerTransform>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  char *v7; // rbx
  int v8; // edi
  char *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = (char *)operator new(0x58u);
    *((_DWORD *)v7 + 2) = 0;
    *(_QWORD *)v7 = &ATL::CComAggObject<CMidi2SchedulerTransform>::`vftable';
    *(_OWORD *)(v7 + 40) = 0;
    *(_OWORD *)(v7 + 56) = 0;
    *((_QWORD *)v7 + 9) = 0;
    v7[80] = 0;
    *((_QWORD *)v7 + 3) = &ATL::CComContainedObject<CMidi2SchedulerTransform>::`vftable';
    *((_QWORD *)v7 + 4) = a1;
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)v7 + 1);
    if ( v8 < 0 || (v7[80] = 1, (v8 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0) )
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 24LL))(v7, 1);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004c34  mov     [rsp+arg_10], r8
0x180004c39  mov     [rsp+arg_8], rdx
0x180004c3e  push    rbx
0x180004c3f  push    rsi
0x180004c40  push    rdi
0x180004c41  push    r14
0x180004c43  push    r15
0x180004c45  sub     rsp, 30h
0x180004c49  mov     rsi, r8
0x180004c4c  mov     r14, rdx
0x180004c4f  mov     r15, rcx
0x180004c52  test    r8, r8
0x180004c55  jnz     short loc_180004C61
0x180004c57  mov     eax, 80004003h
0x180004c5c  jmp     loc_180004D30
0x180004c61  mov     qword ptr [r8], 0
0x180004c68  mov     edi, 8007000Eh
0x180004c6d  mov     [rsp+58h+arg_18], edi
0x180004c71  mov     [rsp+58h+var_38], 0
0x180004c7a  mov     ecx, 58h ; 'X'; Size
0x180004c7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c84  mov     rbx, rax
0x180004c87  mov     dword ptr [rax+8], 0
0x180004c8e  lea     rax, ??_7?$CComAggObject@VCMidi2SchedulerTransform@@@ATL@@6B@; const ATL::CComAggObject<CMidi2SchedulerTransform>::`vftable'
0x180004c95  mov     [rbx], rax
0x180004c98  xorps   xmm0, xmm0
0x180004c9b  xor     eax, eax
0x180004c9d  movups  xmmword ptr [rbx+28h], xmm0
0x180004ca1  movups  xmmword ptr [rbx+38h], xmm0
0x180004ca5  mov     [rbx+48h], rax
0x180004ca9  mov     [rbx+50h], al
0x180004cac  lea     rax, ??_7?$CComContainedObject@VCMidi2SchedulerTransform@@@ATL@@6B@; const ATL::CComContainedObject<CMidi2SchedulerTransform>::`vftable'
0x180004cb3  mov     [rbx+18h], rax
0x180004cb7  mov     [rbx+20h], r15
0x180004cbb  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004cc2  mov     rax, [rcx]
0x180004cc5  mov     rax, [rax+8]
0x180004cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cce  mov     [rsp+58h+var_38], rbx
0x180004cd3  jmp     short loc_180004CE8
0x180004cd5  mov     rsi, [rsp+58h+arg_10]
0x180004cda  mov     r14, [rsp+58h+arg_8]
0x180004cdf  mov     edi, [rsp+58h+arg_18]
0x180004ce3  mov     rbx, [rsp+58h+var_38]
0x180004ce8  test    rbx, rbx
0x180004ceb  jz      short loc_180004D2E
0x180004ced  lea     rcx, [rbx+28h]; this
0x180004cf1  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180004cf6  mov     edi, eax
0x180004cf8  test    eax, eax
0x180004cfa  js      short loc_180004D1A
0x180004cfc  mov     byte ptr [rbx+50h], 1
0x180004d00  mov     rax, [rbx]
0x180004d03  mov     r8, rsi
0x180004d06  mov     rdx, r14
0x180004d09  mov     rcx, rbx
0x180004d0c  mov     rax, [rax]
0x180004d0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d14  mov     edi, eax
0x180004d16  test    eax, eax
0x180004d18  jz      short loc_180004D2E
0x180004d1a  mov     rax, [rbx]
0x180004d1d  mov     edx, 1
0x180004d22  mov     rcx, rbx
0x180004d25  mov     rax, [rax+18h]
0x180004d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d2e  mov     eax, edi
0x180004d30  add     rsp, 30h
0x180004d34  pop     r15
0x180004d36  pop     r14
0x180004d38  pop     rdi
0x180004d39  pop     rsi
0x180004d3a  pop     rbx
0x180004d3b  retn
```
