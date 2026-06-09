# ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)

- ea: `0x1400074dc`
- end: `0x14000756a`
- name: `?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z`
- size: `142`
- prototype: `bool __fastcall(void (__fastcall ****)(_QWORD, GUID *, __int64 *), void (__fastcall ***)(_QWORD, GUID *, __int64 *))`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400069fc`

## callees

- `0x1400035c8`
- `0x1400074dc`
- `0x140017010`

## pseudocode

```c
bool __fastcall ATL::CComPtrBase<ITypeInfo>::IsEqualObject(
        void (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        void (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
{
  void (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rcx
  bool v5; // bl
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v3 = *a1;
  if ( !v3 )
    return a2 == 0;
  if ( !a2 )
    return 0;
  v7 = 0;
  v6 = 0;
  (**v3)(v3, &GUID_00000000_0000_0000_c000_000000000046, &v7);
  (**a2)(a2, &GUID_00000000_0000_0000_c000_000000000046, &v6);
  v5 = v7 == v6;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  return v5;
}

```

## disassembly

```asm
0x1400074dc  push    rbx
0x1400074de  sub     rsp, 20h
0x1400074e2  mov     rbx, rdx
0x1400074e5  mov     rcx, [rcx]
0x1400074e8  test    rcx, rcx
0x1400074eb  jnz     short loc_1400074F5
0x1400074ed  test    rdx, rdx
0x1400074f0  setz    al
0x1400074f3  jmp     short loc_140007564
0x1400074f5  test    rbx, rbx
0x1400074f8  jz      short loc_140007562
0x1400074fa  mov     [rsp+28h+arg_10], 0
0x140007503  mov     [rsp+28h+arg_0], 0
0x14000750c  mov     rax, [rcx]
0x14000750f  lea     r8, [rsp+28h+arg_10]
0x140007514  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14000751b  mov     rax, [rax]
0x14000751e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007523  mov     rax, [rbx]
0x140007526  lea     r8, [rsp+28h+arg_0]
0x14000752b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140007532  mov     rcx, rbx
0x140007535  mov     rax, [rax]
0x140007538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000753d  mov     rax, [rsp+28h+arg_0]
0x140007542  cmp     [rsp+28h+arg_10], rax
0x140007547  setz    bl
0x14000754a  lea     rcx, [rsp+28h+arg_0]
0x14000754f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140007554  lea     rcx, [rsp+28h+arg_10]
0x140007559  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14000755e  mov     al, bl
0x140007560  jmp     short loc_140007564
0x140007562  xor     al, al
0x140007564  add     rsp, 20h
0x140007568  pop     rbx
0x140007569  retn
```
