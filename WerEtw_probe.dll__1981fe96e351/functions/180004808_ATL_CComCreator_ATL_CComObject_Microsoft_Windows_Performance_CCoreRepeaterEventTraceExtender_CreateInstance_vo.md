# ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004808`
- end: `0x1800048f1`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800087fc`

## callees

- `0x1800018a0`
- `0x180004808`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  _DWORD *v5; // rdi
  unsigned int v6; // r14d
  _DWORD *v7; // [rsp+40h] [rbp+8h]

  v3 = a3;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v5 = operator new(0x28u);
    v5[6] = 0;
    *((_QWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 2) = 0;
    v5[8] = 0;
    *(_QWORD *)v5 = &ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v7 = v5;
  }
  catch ( ... )
  {
    v3 = a3;
    v6 = -2147024882;
    v5 = v7;
  }
  if ( v5 )
  {
    v6 = (**(__int64 (__fastcall ***)(void *, GUID *, _QWORD *))v5)(v5, &GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33, v3);
    if ( v6 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v5 + 136LL))(v5, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x180004808  mov     [rsp+arg_10], r8
0x18000480d  mov     [rsp+arg_8], rdx
0x180004812  mov     [rsp+arg_0], rcx
0x180004817  push    rsi
0x180004818  push    rdi
0x180004819  push    r14
0x18000481b  sub     rsp, 20h
0x18000481f  mov     rsi, r8
0x180004822  test    r8, r8
0x180004825  jnz     short loc_180004831
0x180004827  mov     eax, 80004003h
0x18000482c  jmp     loc_1800048E8
0x180004831  mov     qword ptr [r8], 0
0x180004838  mov     r14d, 8007000Eh
0x18000483e  mov     dword ptr [rsp+38h+arg_8], r14d
0x180004843  mov     [rsp+38h+arg_0], 0
0x18000484c  mov     ecx, 28h ; '('; Size
0x180004851  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004856  mov     rdi, rax
0x180004859  mov     dword ptr [rax+18h], 0
0x180004860  mov     qword ptr [rax+8], 0
0x180004868  mov     qword ptr [rax+10h], 0
0x180004870  mov     dword ptr [rax+20h], 0
0x180004877  lea     rax, ??_7?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@6B@; const ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vftable'
0x18000487e  mov     [rdi], rax
0x180004881  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004888  mov     rax, [rcx]
0x18000488b  mov     rax, [rax+8]
0x18000488f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004894  mov     [rsp+38h+arg_0], rdi
0x180004899  jmp     short loc_1800048AA
0x18000489b  mov     rsi, [rsp+38h+arg_10]
0x1800048a0  mov     r14d, dword ptr [rsp+38h+arg_8]
0x1800048a5  mov     rdi, [rsp+38h+arg_0]
0x1800048aa  test    rdi, rdi
0x1800048ad  jz      short loc_1800048E5
0x1800048af  mov     rax, [rdi]
0x1800048b2  mov     r8, rsi
0x1800048b5  lea     rdx, _GUID_0d6ec135_e30c_4264_b3d0_f203840b3e33
0x1800048bc  mov     rcx, rdi
0x1800048bf  mov     rax, [rax]
0x1800048c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048c7  mov     r14d, eax
0x1800048ca  test    eax, eax
0x1800048cc  jz      short loc_1800048E5
0x1800048ce  mov     rdx, [rdi]
0x1800048d1  mov     rax, [rdx+88h]
0x1800048d8  mov     edx, 1
0x1800048dd  mov     rcx, rdi
0x1800048e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048e5  mov     eax, r14d
0x1800048e8  add     rsp, 20h
0x1800048ec  pop     r14
0x1800048ee  pop     rdi
0x1800048ef  pop     rsi
0x1800048f0  retn
```
