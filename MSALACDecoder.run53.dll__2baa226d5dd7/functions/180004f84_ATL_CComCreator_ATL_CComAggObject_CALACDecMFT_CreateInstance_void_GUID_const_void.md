# ATL::CComCreator<ATL::CComAggObject<CALACDecMFT>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004f84`
- end: `0x1800050a0`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCALACDecMFT@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004f70`

## callees

- `0x180001104`
- `0x180001ec4`
- `0x180004f84`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CALACDecMFT>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r15
  unsigned int v7; // esi
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  int v10; // eax
  _QWORD *v11; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0xF0u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *v8 = &ATL::CComAggObject<CALACDecMFT>::`vftable';
      CALACDecMFT::CALACDecMFT((CALACDecMFT *)(v8 + 3));
      v9[3] = &ATL::CComContainedObject<CALACDecMFT>::`vftable';
      v9[22] = a1;
      (*(void (__fastcall **)(ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v11 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v11;
  }
  if ( v9 )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD *))(v9[3] + 376LL))(v9 + 3);
    v7 = 0;
    if ( v10 < 0 )
      v7 = v10;
    if ( v7 || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, v4, v3)) != 0 )
      (*(void (__fastcall **)(_QWORD *, __int64))(*v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180004f84  mov     [rsp+arg_0], rbx
0x180004f89  mov     [rsp+arg_10], r8
0x180004f8e  mov     [rsp+arg_8], rdx
0x180004f93  push    rsi
0x180004f94  push    rdi
0x180004f95  push    r12
0x180004f97  push    r14
0x180004f99  push    r15
0x180004f9b  sub     rsp, 30h
0x180004f9f  mov     r14, r8
0x180004fa2  mov     r15, rdx
0x180004fa5  mov     r12, rcx
0x180004fa8  test    r8, r8
0x180004fab  jnz     short loc_180004FB7
0x180004fad  mov     eax, 80004003h
0x180004fb2  jmp     loc_18000508E
0x180004fb7  mov     qword ptr [r8], 0
0x180004fbe  mov     esi, 8007000Eh
0x180004fc3  mov     [rsp+58h+arg_18], esi
0x180004fc7  mov     [rsp+58h+var_38], 0
0x180004fd0  mov     ecx, 0F0h; Size
0x180004fd5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004fda  mov     rdi, rax
0x180004fdd  test    rdi, rdi
0x180004fe0  jz      short loc_180005021
0x180004fe2  mov     dword ptr [rax+8], 0
0x180004fe9  lea     rax, ??_7?$CComAggObject@VCALACDecMFT@@@ATL@@6B@; const ATL::CComAggObject<CALACDecMFT>::`vftable'
0x180004ff0  mov     [rdi], rax
0x180004ff3  lea     rcx, [rdi+18h]; this
0x180004ff7  call    ??0CALACDecMFT@@QEAA@XZ; CALACDecMFT::CALACDecMFT(void)
0x180004ffc  lea     rax, ??_7?$CComContainedObject@VCALACDecMFT@@@ATL@@6B@; const ATL::CComContainedObject<CALACDecMFT>::`vftable'
0x180005003  mov     [rdi+18h], rax
0x180005007  mov     [rdi+0B0h], r12
0x18000500e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005015  mov     rax, [rcx]
0x180005018  mov     rax, [rax+8]
0x18000501c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005021  mov     [rsp+58h+var_38], rdi
0x180005026  jmp     short loc_18000503B
0x180005028  mov     r14, [rsp+58h+arg_10]
0x18000502d  mov     r15, [rsp+58h+arg_8]
0x180005032  mov     esi, [rsp+58h+arg_18]
0x180005036  mov     rdi, [rsp+58h+var_38]
0x18000503b  test    rdi, rdi
0x18000503e  jz      short loc_18000508C
0x180005040  lea     rcx, [rdi+18h]
0x180005044  mov     rax, [rcx]
0x180005047  mov     rax, [rax+178h]
0x18000504e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005053  xor     esi, esi
0x180005055  test    eax, eax
0x180005057  cmovs   esi, eax
0x18000505a  test    esi, esi
0x18000505c  jnz     short loc_180005078
0x18000505e  mov     rax, [rdi]
0x180005061  mov     r8, r14
0x180005064  mov     rdx, r15
0x180005067  mov     rcx, rdi
0x18000506a  mov     rax, [rax]
0x18000506d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005072  mov     esi, eax
0x180005074  test    eax, eax
0x180005076  jz      short loc_18000508C
0x180005078  mov     rdx, [rdi]
0x18000507b  mov     rax, [rdx+18h]
0x18000507f  mov     edx, 1
0x180005084  mov     rcx, rdi
0x180005087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000508c  mov     eax, esi
0x18000508e  mov     rbx, [rsp+58h+arg_0]
0x180005093  add     rsp, 30h
0x180005097  pop     r15
0x180005099  pop     r14
0x18000509b  pop     r12
0x18000509d  pop     rdi
0x18000509e  pop     rsi
0x18000509f  retn
```
