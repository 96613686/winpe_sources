# ATL::CComObject<CPimcContext>::CreateInstance(ATL::CComObject<CPimcContext> * *)

- ea: `0x18000a0d4`
- end: `0x18000a161`
- name: `?CreateInstance@?$CComObject@VCPimcContext@@@ATL@@SAJPEAPEAV12@@Z`
- size: `141`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800082f0`

## callees

- `0x18000a0d4`
- `0x18000a328`
- `0x18000d438`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<CPimcContext>::CreateInstance(__int64 *a1)
{
  __int64 *v1; // rbx
  unsigned int v3; // edi
  void *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // [rsp+20h] [rbp-18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  try
  {
    v4 = operator new(0x140u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v4 )
      v5 = ATL::CComObject<CPimcContext>::CComObject<CPimcContext>(v4);
    else
      v5 = 0;
    v6 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v6;
  }
  if ( v5 )
  {
    *(_DWORD *)(v5 + 8) = *(_DWORD *)(v5 + 8);
    v3 = 0;
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x18000a0d4  mov     [rsp+arg_18], rbx
0x18000a0d9  mov     [rsp+arg_0], rcx
0x18000a0de  push    rdi
0x18000a0df  sub     rsp, 30h
0x18000a0e3  mov     rbx, rcx
0x18000a0e6  test    rcx, rcx
0x18000a0e9  jnz     short loc_18000A0F2
0x18000a0eb  mov     eax, 80004003h
0x18000a0f0  jmp     short loc_18000A156
0x18000a0f2  and     qword ptr [rcx], 0
0x18000a0f6  mov     edi, 8007000Eh
0x18000a0fb  mov     [rsp+38h+arg_8], edi
0x18000a0ff  and     [rsp+38h+var_18], 0
0x18000a105  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a10c  mov     ecx, 140h; unsigned __int64
0x18000a111  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a116  mov     [rsp+38h+arg_10], rax
0x18000a11b  test    rax, rax
0x18000a11e  jz      short loc_18000A12D
0x18000a120  mov     rcx, rax
0x18000a123  call    ??0?$CComObject@VCPimcContext@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CPimcContext>::CComObject<CPimcContext>(void *)
0x18000a128  mov     rcx, rax
0x18000a12b  jmp     short loc_18000A12F
0x18000a12d  xor     ecx, ecx
0x18000a12f  mov     [rsp+38h+var_18], rcx
0x18000a134  jmp     short loc_18000A144
0x18000a136  mov     rbx, [rsp+38h+arg_0]
0x18000a13b  mov     edi, [rsp+38h+arg_8]
0x18000a13f  mov     rcx, [rsp+38h+var_18]
0x18000a144  test    rcx, rcx
0x18000a147  jz      short loc_18000A151
0x18000a149  mov     eax, [rcx+8]
0x18000a14c  mov     [rcx+8], eax
0x18000a14f  xor     edi, edi
0x18000a151  mov     [rbx], rcx
0x18000a154  mov     eax, edi
0x18000a156  mov     rbx, [rsp+38h+arg_18]
0x18000a15b  add     rsp, 30h
0x18000a15f  pop     rdi
0x18000a160  retn
```
