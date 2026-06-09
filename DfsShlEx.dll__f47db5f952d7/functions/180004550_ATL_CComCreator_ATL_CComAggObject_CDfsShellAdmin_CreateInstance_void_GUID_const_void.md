# ATL::CComCreator<ATL::CComAggObject<CDfsShellAdmin>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004550`
- end: `0x180004636`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCDfsShellAdmin@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004430`

## callees

- `0x180001164`
- `0x180004550`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CDfsShellAdmin>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r14
  unsigned int v7; // edi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  _DWORD *v10; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = operator new(0x20u);
    v9 = v8;
    if ( v8 )
    {
      v8[2] = 0;
      *(_QWORD *)v8 = &ATL::CComAggObject<CDfsShellAdmin>::`vftable';
      *((_QWORD *)v8 + 2) = &ATL::CComContainedObject<CDfsShellAdmin>::`vftable';
      *((_QWORD *)v8 + 3) = a1;
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v10 = v9;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v7 = -2147024882;
    v9 = v10;
  }
  if ( v9 )
  {
    v7 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v9)(v9, v4, v3);
    if ( v7 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v9 + 24LL))(v9, 1);
  }
  return v7;
}

```

## disassembly

```asm
0x180004550  mov     [rsp+arg_10], r8
0x180004555  mov     [rsp+arg_8], rdx
0x18000455a  push    rbx
0x18000455b  push    rsi
0x18000455c  push    rdi
0x18000455d  push    r14
0x18000455f  push    r15
0x180004561  sub     rsp, 30h
0x180004565  mov     rsi, r8
0x180004568  mov     r14, rdx
0x18000456b  mov     r15, rcx
0x18000456e  test    r8, r8
0x180004571  jnz     short loc_18000457D
0x180004573  mov     eax, 80004003h
0x180004578  jmp     loc_18000462A
0x18000457d  mov     qword ptr [r8], 0
0x180004584  mov     edi, 8007000Eh
0x180004589  mov     [rsp+58h+arg_18], edi
0x18000458d  mov     [rsp+58h+var_38], 0
0x180004596  mov     ecx, 20h ; ' '; Size
0x18000459b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800045a0  mov     rbx, rax
0x1800045a3  test    rbx, rbx
0x1800045a6  jz      short loc_1800045DB
0x1800045a8  mov     dword ptr [rax+8], 0
0x1800045af  lea     rax, ??_7?$CComAggObject@VCDfsShellAdmin@@@ATL@@6B@; const ATL::CComAggObject<CDfsShellAdmin>::`vftable'
0x1800045b6  mov     [rbx], rax
0x1800045b9  lea     rax, ??_7?$CComContainedObject@VCDfsShellAdmin@@@ATL@@6B@; const ATL::CComContainedObject<CDfsShellAdmin>::`vftable'
0x1800045c0  mov     [rbx+10h], rax
0x1800045c4  mov     [rbx+18h], r15
0x1800045c8  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800045cf  mov     rax, [rcx]
0x1800045d2  mov     rax, [rax+8]
0x1800045d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045db  mov     [rsp+58h+var_38], rbx
0x1800045e0  jmp     short loc_1800045F5
0x1800045e2  mov     rsi, [rsp+58h+arg_10]
0x1800045e7  mov     r14, [rsp+58h+arg_8]
0x1800045ec  mov     edi, [rsp+58h+arg_18]
0x1800045f0  mov     rbx, [rsp+58h+var_38]
0x1800045f5  test    rbx, rbx
0x1800045f8  jz      short loc_180004628
0x1800045fa  mov     rax, [rbx]
0x1800045fd  mov     r8, rsi
0x180004600  mov     rdx, r14
0x180004603  mov     rcx, rbx
0x180004606  mov     rax, [rax]
0x180004609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000460e  mov     edi, eax
0x180004610  test    eax, eax
0x180004612  jz      short loc_180004628
0x180004614  mov     rdx, [rbx]
0x180004617  mov     rax, [rdx+18h]
0x18000461b  mov     edx, 1
0x180004620  mov     rcx, rbx
0x180004623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004628  mov     eax, edi
0x18000462a  add     rsp, 30h
0x18000462e  pop     r15
0x180004630  pop     r14
0x180004632  pop     rdi
0x180004633  pop     rsi
0x180004634  pop     rbx
0x180004635  retn
```
