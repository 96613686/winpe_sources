# ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)

- ea: `0x180002fec`
- end: `0x18000307a`
- name: `?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002ae0`

## callees

- `0x1800021a4`
- `0x180002fec`
- `0x180014010`

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
0x180002fec  push    rbx
0x180002fee  sub     rsp, 20h
0x180002ff2  mov     rbx, rdx
0x180002ff5  mov     rcx, [rcx]
0x180002ff8  test    rcx, rcx
0x180002ffb  jnz     short loc_180003005
0x180002ffd  test    rdx, rdx
0x180003000  setz    al
0x180003003  jmp     short loc_180003074
0x180003005  test    rbx, rbx
0x180003008  jz      short loc_180003072
0x18000300a  mov     [rsp+28h+arg_10], 0
0x180003013  mov     [rsp+28h+arg_0], 0
0x18000301c  mov     rax, [rcx]
0x18000301f  lea     r8, [rsp+28h+arg_10]
0x180003024  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000302b  mov     rax, [rax]
0x18000302e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003033  mov     rax, [rbx]
0x180003036  lea     r8, [rsp+28h+arg_0]
0x18000303b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180003042  mov     rcx, rbx
0x180003045  mov     rax, [rax]
0x180003048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000304d  mov     rax, [rsp+28h+arg_0]
0x180003052  cmp     [rsp+28h+arg_10], rax
0x180003057  setz    bl
0x18000305a  lea     rcx, [rsp+28h+arg_0]
0x18000305f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003064  lea     rcx, [rsp+28h+arg_10]
0x180003069  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000306e  mov     al, bl
0x180003070  jmp     short loc_180003074
0x180003072  xor     al, al
0x180003074  add     rsp, 20h
0x180003078  pop     rbx
0x180003079  retn
```
