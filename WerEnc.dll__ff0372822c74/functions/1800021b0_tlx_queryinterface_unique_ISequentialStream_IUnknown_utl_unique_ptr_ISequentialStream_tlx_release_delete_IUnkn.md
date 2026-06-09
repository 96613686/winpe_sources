# tlx::queryinterface_unique<ISequentialStream,IUnknown>(utl::unique_ptr<ISequentialStream,tlx::release_delete> *,IUnknown &,_GUID const &)

- ea: `0x1800021b0`
- end: `0x18000223d`
- name: `??$queryinterface_unique@UISequentialStream@@UIUnknown@@@tlx@@YAJPEAV?$unique_ptr@UISequentialStream@@Urelease_delete@tlx@@@utl@@AEAUIUnknown@@AEBU_GUID@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002440`

## callees

- `0x1800021b0`
- `0x180003010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall tlx::queryinterface_unique<ISequentialStream,IUnknown>(
        __int64 *a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  __int64 (__fastcall *v3)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v4; // r8
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  __int64 *v9; // [rsp+28h] [rbp-20h]

  v3 = **a2;
  v8 = 0;
  v9 = a1;
  v4 = *a1;
  *a1 = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = v3(a2, &GUID_0c733a30_2a1c_11ce_ade5_00aa0044773d, &v8);
  if ( v8 )
  {
    v6 = *v9;
    *v9 = v8;
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x1800021b0  mov     [rsp+arg_0], rbx
0x1800021b5  push    rdi
0x1800021b6  sub     rsp, 40h
0x1800021ba  mov     rbx, rdx
0x1800021bd  mov     rax, [rdx]
0x1800021c0  mov     rdi, [rax]
0x1800021c3  mov     [rsp+48h+var_28], 0
0x1800021cc  mov     [rsp+48h+var_20], rcx
0x1800021d1  mov     r8, [rcx]
0x1800021d4  mov     qword ptr [rcx], 0
0x1800021db  test    r8, r8
0x1800021de  jz      short loc_1800021F0
0x1800021e0  mov     rax, [r8]
0x1800021e3  mov     rcx, r8
0x1800021e6  mov     rax, [rax+10h]
0x1800021ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021ef  nop
0x1800021f0  lea     r8, [rsp+48h+var_28]
0x1800021f5  lea     rdx, _GUID_0c733a30_2a1c_11ce_ade5_00aa0044773d
0x1800021fc  mov     rcx, rbx
0x1800021ff  mov     rax, rdi
0x180002202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002207  mov     ebx, eax
0x180002209  mov     r8, [rsp+48h+var_28]
0x18000220e  test    r8, r8
0x180002211  jz      short loc_180002230
0x180002213  mov     rdx, [rsp+48h+var_20]
0x180002218  mov     rcx, [rdx]
0x18000221b  mov     [rdx], r8
0x18000221e  test    rcx, rcx
0x180002221  jz      short loc_180002230
0x180002223  mov     rax, [rcx]
0x180002226  mov     rax, [rax+10h]
0x18000222a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000222f  nop
0x180002230  mov     eax, ebx
0x180002232  mov     rbx, [rsp+48h+arg_0]
0x180002237  add     rsp, 40h
0x18000223b  pop     rdi
0x18000223c  retn
```
