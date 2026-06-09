# ATL::CComObject<CBindingCallback>::CreateInstance(ATL::CComObject<CBindingCallback> * *)

- ea: `0x180020dec`
- end: `0x180020e6c`
- name: `?CreateInstance@?$CComObject@VCBindingCallback@@@ATL@@SAJPEAPEAV12@@Z`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022108`

## callees

- `0x180001d94`
- `0x18000a1c0`
- `0x180020dec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CBindingCallback>::CreateInstance(unsigned __int8 **a1, unsigned int a2)
{
  __int64 result; // rax
  unsigned __int8 *v4; // rax
  unsigned __int8 *v5; // rbx
  unsigned int v6; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v4 = MMMAlloc(0x20u, a2);
  try
  {
    v5 = v4;
    if ( v4 )
    {
      ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>((_DWORD *)v4 + 2);
      *((_QWORD *)v5 + 3) = 0;
      *(_QWORD *)v5 = &ATL::CComObject<CBindingCallback>::`vftable';
      _InterlockedIncrement(&dword_1800454E8);
    }
    else
    {
      v5 = 0;
    }
    result = v5 == 0 ? 0x8007000E : 0;
    *a1 = v5;
  }
  catch ( long v6 )
  {
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180020dec  mov     [rsp+arg_8], rbx
0x180020df1  push    rdi
0x180020df2  sub     rsp, 30h
0x180020df6  mov     rdi, rcx
0x180020df9  test    rcx, rcx
0x180020dfc  jnz     short loc_180020E05
0x180020dfe  mov     eax, 80004003h
0x180020e03  jmp     short loc_180020E61
0x180020e05  mov     qword ptr [rcx], 0
0x180020e0c  mov     ecx, 20h ; ' '; unsigned int
0x180020e11  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180020e16  mov     rbx, rax
0x180020e19  mov     [rsp+38h+arg_0], rax
0x180020e1e  test    rax, rax
0x180020e21  jz      short loc_180020E47
0x180020e23  lea     rcx, [rax+8]
0x180020e27  call    ??0?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::CComObjectRootEx<ATL::CComMultiThreadModel>(void)
0x180020e2c  mov     qword ptr [rbx+18h], 0
0x180020e34  lea     rax, ??_7?$CComObject@VCBindingCallback@@@ATL@@6B@; const ATL::CComObject<CBindingCallback>::`vftable'
0x180020e3b  mov     [rbx], rax
0x180020e3e  lock inc cs:dword_1800454E8
0x180020e45  jmp     short loc_180020E49
0x180020e47  xor     ebx, ebx
0x180020e49  mov     rax, rbx
0x180020e4c  neg     rax
0x180020e4f  sbb     eax, eax
0x180020e51  not     eax
0x180020e53  and     eax, 8007000Eh
0x180020e58  mov     [rdi], rbx
0x180020e5b  jmp     short loc_180020E61
0x180020e5d  mov     eax, [rsp+38h+var_18]
0x180020e61  mov     rbx, [rsp+38h+arg_8]
0x180020e66  add     rsp, 30h
0x180020e6a  pop     rdi
0x180020e6b  retn
```
