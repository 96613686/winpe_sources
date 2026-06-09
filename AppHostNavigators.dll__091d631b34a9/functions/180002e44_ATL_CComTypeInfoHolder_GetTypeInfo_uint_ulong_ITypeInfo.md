# ATL::CComTypeInfoHolder::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180002e44`
- end: `0x180002eae`
- name: `?GetTypeInfo@CComTypeInfoHolder@ATL@@QEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, unsigned int, unsigned int, struct ITypeInfo **)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002e30`
- `0x180005170`
- `0x180006210`
- `0x180006e30`
- `0x180008060`
- `0x1800093d0`
- `0x1800097f0`

## callees

- `0x180002ae0`
- `0x180002e44`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTypeInfo(
        ATL::CComTypeInfoHolder *this,
        int a2,
        LCID a3,
        struct ITypeInfo **a4)
{
  unsigned int TI; // ecx
  __int64 v8; // rdx

  if ( a2 )
    return 2147614731LL;
  if ( a4 )
  {
    TI = 0;
    if ( !*((_QWORD *)this + 3) )
      TI = ATL::CComTypeInfoHolder::GetTI(this, a3);
    *a4 = (struct ITypeInfo *)*((_QWORD *)this + 3);
    v8 = *((_QWORD *)this + 3);
    if ( v8 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(*((_QWORD *)this + 3));
      return 0;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return TI;
}

```

## disassembly

```asm
0x180002e44  mov     [rsp+arg_0], rbx
0x180002e49  push    rdi
0x180002e4a  sub     rsp, 20h
0x180002e4e  mov     rdi, r9
0x180002e51  mov     rbx, rcx
0x180002e54  test    edx, edx
0x180002e56  jz      short loc_180002E5F
0x180002e58  mov     eax, 8002000Bh
0x180002e5d  jmp     short loc_180002EA3
0x180002e5f  test    rdi, rdi
0x180002e62  jnz     short loc_180002E6B
0x180002e64  mov     ecx, 80004003h
0x180002e69  jmp     short loc_180002EA1
0x180002e6b  xor     ecx, ecx
0x180002e6d  cmp     [rbx+18h], rcx
0x180002e71  jnz     short loc_180002E80
0x180002e73  mov     edx, r8d; lcid
0x180002e76  mov     rcx, rbx; this
0x180002e79  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180002e7e  mov     ecx, eax
0x180002e80  mov     rax, [rbx+18h]
0x180002e84  mov     [rdi], rax
0x180002e87  mov     rdx, [rbx+18h]
0x180002e8b  test    rdx, rdx
0x180002e8e  jz      short loc_180002EA1
0x180002e90  mov     rax, [rdx]
0x180002e93  mov     rcx, rdx
0x180002e96  mov     rax, [rax+8]
0x180002e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e9f  xor     ecx, ecx
0x180002ea1  mov     eax, ecx
0x180002ea3  mov     rbx, [rsp+28h+arg_0]
0x180002ea8  add     rsp, 20h
0x180002eac  pop     rdi
0x180002ead  retn
```
