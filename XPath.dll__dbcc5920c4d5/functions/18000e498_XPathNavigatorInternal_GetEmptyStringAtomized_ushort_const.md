# XPathNavigatorInternal::GetEmptyStringAtomized(ushort const * *)

- ea: `0x18000e498`
- end: `0x18000e4fc`
- name: `?GetEmptyStringAtomized@XPathNavigatorInternal@@AEAAJPEAPEBG@Z`
- size: `100`
- prototype: `__int64 __fastcall(XPathNavigatorInternal *__hidden this, const unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e504`
- `0x18000e54c`

## callees

- `0x1800020b4`
- `0x18000e498`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall XPathNavigatorInternal::GetEmptyStringAtomized(
        XPathNavigatorInternal *this,
        const unsigned __int16 **a2)
{
  __int64 v2; // rcx
  int v4; // ebx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_QWORD *)this;
  v6 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v2 + 24LL))(v2, &v6);
  if ( v4 >= 0 )
    v4 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 **))(*(_QWORD *)v6 + 24LL))(
           v6,
           &qword_180016F98,
           a2);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e498  mov     [rsp+arg_8], rbx
0x18000e49d  push    rdi
0x18000e49e  sub     rsp, 20h
0x18000e4a2  mov     rcx, [rcx]
0x18000e4a5  mov     rdi, rdx
0x18000e4a8  mov     [rsp+28h+arg_0], 0
0x18000e4b1  lea     rdx, [rsp+28h+arg_0]
0x18000e4b6  mov     rax, [rcx]
0x18000e4b9  mov     rax, [rax+18h]
0x18000e4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4c2  mov     ebx, eax
0x18000e4c4  test    eax, eax
0x18000e4c6  js      short loc_18000E4E5
0x18000e4c8  mov     rcx, [rsp+28h+arg_0]
0x18000e4cd  lea     rdx, qword_180016F98
0x18000e4d4  mov     r8, rdi
0x18000e4d7  mov     rax, [rcx]
0x18000e4da  mov     rax, [rax+18h]
0x18000e4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4e3  mov     ebx, eax
0x18000e4e5  lea     rcx, [rsp+28h+arg_0]
0x18000e4ea  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000e4ef  mov     eax, ebx
0x18000e4f1  mov     rbx, [rsp+28h+arg_8]
0x18000e4f6  add     rsp, 20h
0x18000e4fa  pop     rdi
0x18000e4fb  retn
```
