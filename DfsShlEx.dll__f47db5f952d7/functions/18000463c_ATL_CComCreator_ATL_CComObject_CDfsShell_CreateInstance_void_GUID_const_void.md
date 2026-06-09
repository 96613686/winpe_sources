# ATL::CComCreator<ATL::CComObject<CDfsShell>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000463c`
- end: `0x18000471d`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCDfsShell@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004410`

## callees

- `0x180001164`
- `0x1800028e4`
- `0x18000463c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CDfsShell>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rdi
  __int64 v4; // r14
  unsigned int v6; // esi
  CDfsShell *v7; // rax
  CDfsShell *v8; // rbx
  CDfsShell *v11; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CDfsShell *)operator new(0x140u);
    v8 = v7;
    if ( v7 )
    {
      CDfsShell::CDfsShell(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CDfsShell>::`vftable'{for `IShellExtInit'};
      *((_QWORD *)v8 + 1) = &ATL::CComObject<CDfsShell>::`vftable'{for `IShellPropSheetExt'};
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v11 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v6 = -2147024882;
    v8 = v11;
  }
  if ( v8 )
  {
    v6 = (**(__int64 (__fastcall ***)(CDfsShell *, __int64, _QWORD *))v8)(v8, v4, v3);
    if ( v6 )
      (*(void (__fastcall **)(CDfsShell *, __int64))(*(_QWORD *)v8 + 32LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x18000463c  mov     [rsp+arg_10], r8
0x180004641  mov     [rsp+arg_8], rdx
0x180004646  mov     [rsp+arg_0], rcx
0x18000464b  push    rbx
0x18000464c  push    rsi
0x18000464d  push    rdi
0x18000464e  push    r14
0x180004650  sub     rsp, 28h
0x180004654  mov     rdi, r8
0x180004657  mov     r14, rdx
0x18000465a  test    r8, r8
0x18000465d  jnz     short loc_180004669
0x18000465f  mov     eax, 80004003h
0x180004664  jmp     loc_180004713
0x180004669  mov     qword ptr [r8], 0
0x180004670  mov     esi, 8007000Eh
0x180004675  mov     dword ptr [rsp+48h+arg_0], esi
0x180004679  mov     [rsp+48h+arg_18], 0
0x180004682  mov     ecx, 140h; Size
0x180004687  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000468c  mov     rbx, rax
0x18000468f  test    rbx, rbx
0x180004692  jz      short loc_1800046C4
0x180004694  mov     rcx, rax; this
0x180004697  call    ??0CDfsShell@@QEAA@XZ; CDfsShell::CDfsShell(void)
0x18000469c  lea     rax, ??_7?$CComObject@VCDfsShell@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<CDfsShell>::`vftable'{for `IShellExtInit'}
0x1800046a3  mov     [rbx], rax
0x1800046a6  lea     rax, ??_7?$CComObject@VCDfsShell@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComObject<CDfsShell>::`vftable'{for `IShellPropSheetExt'}
0x1800046ad  mov     [rbx+8], rax
0x1800046b1  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800046b8  mov     rax, [rcx]
0x1800046bb  mov     rax, [rax+8]
0x1800046bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046c4  mov     [rsp+48h+arg_18], rbx
0x1800046c9  jmp     short loc_1800046DE
0x1800046cb  mov     rdi, [rsp+48h+arg_10]
0x1800046d0  mov     r14, [rsp+48h+arg_8]
0x1800046d5  mov     esi, dword ptr [rsp+48h+arg_0]
0x1800046d9  mov     rbx, [rsp+48h+arg_18]
0x1800046de  test    rbx, rbx
0x1800046e1  jz      short loc_180004711
0x1800046e3  mov     rax, [rbx]
0x1800046e6  mov     r8, rdi
0x1800046e9  mov     rdx, r14
0x1800046ec  mov     rcx, rbx
0x1800046ef  mov     rax, [rax]
0x1800046f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046f7  mov     esi, eax
0x1800046f9  test    eax, eax
0x1800046fb  jz      short loc_180004711
0x1800046fd  mov     rdx, [rbx]
0x180004700  mov     rax, [rdx+20h]
0x180004704  mov     edx, 1
0x180004709  mov     rcx, rbx
0x18000470c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004711  mov     eax, esi
0x180004713  add     rsp, 28h
0x180004717  pop     r14
0x180004719  pop     rdi
0x18000471a  pop     rsi
0x18000471b  pop     rbx
0x18000471c  retn
```
