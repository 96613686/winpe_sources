# ATL::CComTypeInfoHolder::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x140006e74`
- end: `0x140006ede`
- name: `?GetTypeInfo@CComTypeInfoHolder@ATL@@QEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *this, int, LCID, struct ITypeInfo **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006e40`
- `0x140006e60`

## callees

- `0x1400069fc`
- `0x140006e74`
- `0x140017010`

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
0x140006e74  mov     [rsp+arg_0], rbx
0x140006e79  push    rdi
0x140006e7a  sub     rsp, 20h
0x140006e7e  mov     rdi, r9
0x140006e81  mov     rbx, rcx
0x140006e84  test    edx, edx
0x140006e86  jz      short loc_140006E8F
0x140006e88  mov     eax, 8002000Bh
0x140006e8d  jmp     short loc_140006ED3
0x140006e8f  test    rdi, rdi
0x140006e92  jnz     short loc_140006E9B
0x140006e94  mov     ecx, 80004003h
0x140006e99  jmp     short loc_140006ED1
0x140006e9b  xor     ecx, ecx
0x140006e9d  cmp     [rbx+18h], rcx
0x140006ea1  jnz     short loc_140006EB0
0x140006ea3  mov     edx, r8d; lcid
0x140006ea6  mov     rcx, rbx; this
0x140006ea9  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x140006eae  mov     ecx, eax
0x140006eb0  mov     rax, [rbx+18h]
0x140006eb4  mov     [rdi], rax
0x140006eb7  mov     rdx, [rbx+18h]
0x140006ebb  test    rdx, rdx
0x140006ebe  jz      short loc_140006ED1
0x140006ec0  mov     rax, [rdx]
0x140006ec3  mov     rcx, rdx
0x140006ec6  mov     rax, [rax+8]
0x140006eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ecf  xor     ecx, ecx
0x140006ed1  mov     eax, ecx
0x140006ed3  mov     rbx, [rsp+28h+arg_0]
0x140006ed8  add     rsp, 20h
0x140006edc  pop     rdi
0x140006edd  retn
```
