# ATL::CComCreator<ATL::CComObject<CDsmRefreshTask>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000cf58`
- end: `0x18000d09c`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCDsmRefreshTask@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `324`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cf30`

## callees

- `0x18000137c`
- `0x180008efc`
- `0x18000cf58`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CDsmRefreshTask>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  signed __int32 v9; // eax
  int v10; // ecx
  int v11; // eax
  signed __int32 v12; // eax

  if ( !a3 )
    return 2147500035LL;
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
    *(_QWORD *)v7 = &ATL::CComObject<CDsmRefreshTask>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
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
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 56LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000cf58  mov     [rsp+arg_10], r8
0x18000cf5d  mov     [rsp+arg_8], rdx
0x18000cf62  mov     [rsp+arg_0], rcx
0x18000cf67  push    rbx
0x18000cf68  push    rsi
0x18000cf69  push    rdi
0x18000cf6a  push    r14
0x18000cf6c  push    r15
0x18000cf6e  sub     rsp, 20h
0x18000cf72  mov     rsi, r8
0x18000cf75  mov     r14, rdx
0x18000cf78  test    r8, r8
0x18000cf7b  jnz     short loc_18000CF87
0x18000cf7d  mov     eax, 80004003h
0x18000cf82  jmp     loc_18000D090
0x18000cf87  mov     qword ptr [r8], 0
0x18000cf8e  mov     edi, 8007000Eh
0x18000cf93  mov     dword ptr [rsp+48h+arg_0], edi
0x18000cf97  mov     [rsp+48h+arg_18], 0
0x18000cfa0  mov     ecx, 40h ; '@'; Size
0x18000cfa5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cfaa  mov     rbx, rax
0x18000cfad  test    rbx, rbx
0x18000cfb0  jz      short loc_18000CFEA
0x18000cfb2  mov     dword ptr [rax+8], 0
0x18000cfb9  xorps   xmm0, xmm0
0x18000cfbc  xor     eax, eax
0x18000cfbe  movups  xmmword ptr [rbx+10h], xmm0
0x18000cfc2  movups  xmmword ptr [rbx+20h], xmm0
0x18000cfc6  mov     [rbx+30h], rax
0x18000cfca  mov     [rbx+38h], al
0x18000cfcd  lea     rax, ??_7?$CComObject@VCDsmRefreshTask@@@ATL@@6B@; const ATL::CComObject<CDsmRefreshTask>::`vftable'
0x18000cfd4  mov     [rbx], rax
0x18000cfd7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000cfde  mov     rax, [rcx]
0x18000cfe1  mov     rax, [rax+8]
0x18000cfe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfea  mov     [rsp+48h+arg_18], rbx
0x18000cfef  jmp     short loc_18000D004
0x18000cff1  mov     rsi, [rsp+48h+arg_10]
0x18000cff6  mov     r14, [rsp+48h+arg_8]
0x18000cffb  mov     edi, dword ptr [rsp+48h+arg_0]
0x18000cfff  mov     rbx, [rsp+48h+arg_18]
0x18000d004  test    rbx, rbx
0x18000d007  jz      loc_18000D08E
0x18000d00d  mov     r15d, 7FFFFFFFh
0x18000d013  jmp     short loc_18000D01F
0x18000d015  lea     ecx, [rax+1]
0x18000d018  lock cmpxchg [rbx+8], ecx
0x18000d01d  jz      short loc_18000D027
0x18000d01f  mov     eax, [rbx+8]
0x18000d022  cmp     eax, r15d
0x18000d025  jnz     short loc_18000D015
0x18000d027  lea     rcx, [rbx+10h]; this
0x18000d02b  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000d030  mov     ecx, eax
0x18000d032  test    eax, eax
0x18000d034  js      short loc_18000D03A
0x18000d036  mov     byte ptr [rbx+38h], 1
0x18000d03a  xor     eax, eax
0x18000d03c  test    ecx, ecx
0x18000d03e  cmovs   eax, ecx
0x18000d041  xor     edi, edi
0x18000d043  test    eax, eax
0x18000d045  cmovs   edi, eax
0x18000d048  jmp     short loc_18000D054
0x18000d04a  lea     ecx, [rax-1]
0x18000d04d  lock cmpxchg [rbx+8], ecx
0x18000d052  jz      short loc_18000D05C
0x18000d054  mov     eax, [rbx+8]
0x18000d057  cmp     eax, r15d
0x18000d05a  jnz     short loc_18000D04A
0x18000d05c  test    edi, edi
0x18000d05e  jnz     short loc_18000D07A
0x18000d060  mov     rax, [rbx]
0x18000d063  mov     r8, rsi
0x18000d066  mov     rdx, r14
0x18000d069  mov     rcx, rbx
0x18000d06c  mov     rax, [rax]
0x18000d06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d074  mov     edi, eax
0x18000d076  test    eax, eax
0x18000d078  jz      short loc_18000D08E
0x18000d07a  mov     r8, [rbx]
0x18000d07d  mov     edx, 1
0x18000d082  mov     rcx, rbx
0x18000d085  mov     rax, [r8+38h]
0x18000d089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d08e  mov     eax, edi
0x18000d090  add     rsp, 20h
0x18000d094  pop     r15
0x18000d096  pop     r14
0x18000d098  pop     rdi
0x18000d099  pop     rsi
0x18000d09a  pop     rbx
0x18000d09b  retn
```
