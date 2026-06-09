# std::_Func_impl_no_alloc<_lambda_f25c37099038263181b5186a3fa41b37_,void,>::_Copy(void *)

- ea: `0x180011a90`
- end: `0x180011ad3`
- name: `?_Copy@?$_Func_impl_no_alloc@V_lambda_f25c37099038263181b5186a3fa41b37_@@X$$V@std@@EEBAPEAV?$_Func_base@X$$V@2@PEAX@Z`
- size: `67`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010298`

## callees

- `0x180011a90`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl_no_alloc<_lambda_f25c37099038263181b5186a3fa41b37_,void,>::_Copy(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v2; // rax

  *a2 = &std::_Func_impl_no_alloc<_lambda_f25c37099038263181b5186a3fa41b37_,void,>::`vftable';
  a2[1] = a1[1];
  a2[2] = 0;
  a2[3] = 0;
  v2 = a1[3];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  a2[2] = a1[2];
  a2[3] = a1[3];
  return a2;
}

```

## disassembly

```asm
0x180011a90  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_f25c37099038263181b5186a3fa41b37_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_f25c37099038263181b5186a3fa41b37_,void,>::`vftable'
0x180011a97  mov     [rdx], rax
0x180011a9a  mov     rax, [rcx+8]
0x180011a9e  mov     [rdx+8], rax
0x180011aa2  mov     qword ptr [rdx+10h], 0
0x180011aaa  mov     qword ptr [rdx+18h], 0
0x180011ab2  mov     rax, [rcx+18h]
0x180011ab6  test    rax, rax
0x180011ab9  jz      short loc_180011ABF
0x180011abb  lock inc dword ptr [rax+8]
0x180011abf  mov     rax, [rcx+10h]
0x180011ac3  mov     [rdx+10h], rax
0x180011ac7  mov     rax, [rcx+18h]
0x180011acb  mov     [rdx+18h], rax
0x180011acf  mov     rax, rdx
0x180011ad2  retn
```
