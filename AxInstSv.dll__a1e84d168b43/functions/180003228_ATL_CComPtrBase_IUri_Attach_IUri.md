# ATL::CComPtrBase<IUri>::Attach(IUri *)

- ea: `0x180003228`
- end: `0x18000325a`
- name: `?Attach@?$CComPtrBase@UIUri@@@ATL@@QEAAXPEAUIUri@@@Z`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002e78`
- `0x1800038dc`

## callees

- `0x180003228`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IUri>::Attach(__int64 *a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 result; // rax

  v4 = *a1;
  if ( v4 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *a1 = a2;
  return result;
}

```

## disassembly

```asm
0x180003228  mov     [rsp+arg_0], rbx
0x18000322d  push    rdi
0x18000322e  sub     rsp, 20h
0x180003232  mov     rdi, rdx
0x180003235  mov     rbx, rcx
0x180003238  mov     rcx, [rcx]
0x18000323b  test    rcx, rcx
0x18000323e  jz      short loc_18000324C
0x180003240  mov     rax, [rcx]
0x180003243  mov     rax, [rax+10h]
0x180003247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000324c  mov     [rbx], rdi
0x18000324f  mov     rbx, [rsp+28h+arg_0]
0x180003254  add     rsp, 20h
0x180003258  pop     rdi
0x180003259  retn
```
