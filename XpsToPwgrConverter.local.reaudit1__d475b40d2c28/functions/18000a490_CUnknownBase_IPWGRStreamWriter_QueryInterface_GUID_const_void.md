# CUnknownBase<IPWGRStreamWriter>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a490`
- end: `0x18000a4fb`
- name: `?QueryInterface@?$CUnknownBase@UIPWGRStreamWriter@@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a490`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CUnknownBase<IPWGRStreamWriter>::QueryInterface(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  unsigned int v3; // ebx

  if ( a3 )
  {
    if ( *a2 == *(_QWORD *)&IID_IUnknown.Data1 && a2[1] == *(_QWORD *)IID_IUnknown.Data4
      || *a2 == *(_QWORD *)&GUID_70a98149_a555_492e_84e1_9cb0be95d71b.Data1
      && a2[1] == *(_QWORD *)GUID_70a98149_a555_492e_84e1_9cb0be95d71b.Data4 )
    {
      *a3 = a1;
      v3 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    }
    else
    {
      *a3 = 0;
      return (unsigned int)-2147467262;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v3;
}

```

## disassembly

```asm
0x18000a490  push    rbx
0x18000a492  sub     rsp, 20h
0x18000a496  test    r8, r8
0x18000a499  jnz     short loc_18000A4A2
0x18000a49b  mov     ebx, 80004003h
0x18000a4a0  jmp     short loc_18000A4F3
0x18000a4a2  mov     rax, [rdx]
0x18000a4a5  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x18000a4ac  jnz     short loc_18000A4BB
0x18000a4ae  mov     rax, [rdx+8]
0x18000a4b2  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18000a4b9  jz      short loc_18000A4D4
0x18000a4bb  mov     rax, [rdx]
0x18000a4be  cmp     rax, qword ptr cs:_GUID_70a98149_a555_492e_84e1_9cb0be95d71b.Data1
0x18000a4c5  jnz     short loc_18000A4E7
0x18000a4c7  mov     rax, [rdx+8]
0x18000a4cb  cmp     rax, qword ptr cs:_GUID_70a98149_a555_492e_84e1_9cb0be95d71b.Data4
0x18000a4d2  jnz     short loc_18000A4E7
0x18000a4d4  mov     [r8], rcx
0x18000a4d7  xor     ebx, ebx
0x18000a4d9  mov     rax, [rcx]
0x18000a4dc  mov     rax, [rax+8]
0x18000a4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4e5  jmp     short loc_18000A4F3
0x18000a4e7  mov     qword ptr [r8], 0
0x18000a4ee  mov     ebx, 80004002h
0x18000a4f3  mov     eax, ebx
0x18000a4f5  add     rsp, 20h
0x18000a4f9  pop     rbx
0x18000a4fa  retn
```
