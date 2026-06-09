# CReconstructor::ProcessAJunction(CScanner::CJunction *)

- ea: `0x10043b9a0`
- end: `0x10043ba06`
- name: `?ProcessAJunction@CReconstructor@@UEAAJPEAVCJunction@CScanner@@@Z`
- size: `102`
- prototype: `__int64 __fastcall(CReconstructor *__hidden this, struct CScanner::CJunction *)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x10043b9a0`
- `0x10043ba10`
- `0x10043bce0`

## pseudocode

```c
__int64 __fastcall CReconstructor::ProcessAJunction(CReconstructor *this, struct CScanner::CJunction *a2)
{
  __int64 result; // rax
  _QWORD *v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  *((_QWORD *)this + 12) = a2;
  result = CReconstructor::ProcessFillChains(this);
  if ( (int)result >= 0 && !*((_BYTE *)this + 107) )
  {
    _mm_lfence();
    result = CReconstructor::ProcessStrokeChains(this);
    if ( (int)result >= 0 )
    {
      _mm_lfence();
      if ( !*(_BYTE *)(*((_QWORD *)this + 12) + 90LL) )
      {
        _mm_lfence();
        v4 = (_QWORD *)*((_QWORD *)this + 12);
        v5 = *((_QWORD *)this + 3);
        v6 = v4[9];
        return (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v5 + 64LL))(v5, *v4, 1, &v6);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x10043b9a0  push    rbx
0x10043b9a2  sub     rsp, 20h
0x10043b9a6  mov     rbx, rcx
0x10043b9a9  mov     [rcx+60h], rdx
0x10043b9ad  call    ?ProcessFillChains@CReconstructor@@IEAAJXZ; CReconstructor::ProcessFillChains(void)
0x10043b9b2  test    eax, eax
0x10043b9b4  js      short loc_10043BA00
0x10043b9b6  cmp     byte ptr [rbx+6Bh], 0
0x10043b9ba  jnz     short loc_10043BA00
0x10043b9bc  lfence
0x10043b9bf  mov     rcx, rbx; this
0x10043b9c2  call    ?ProcessStrokeChains@CReconstructor@@IEAAJXZ; CReconstructor::ProcessStrokeChains(void)
0x10043b9c7  test    eax, eax
0x10043b9c9  js      short loc_10043BA00
0x10043b9cb  lfence
0x10043b9ce  mov     rcx, [rbx+60h]
0x10043b9d2  cmp     byte ptr [rcx+5Ah], 0
0x10043b9d6  jnz     short loc_10043BA00
0x10043b9d8  lfence
0x10043b9db  mov     rdx, [rbx+60h]
0x10043b9df  lea     r9, [rsp+28h+arg_0]
0x10043b9e4  mov     rcx, [rbx+18h]
0x10043b9e8  mov     r8d, 1
0x10043b9ee  mov     rax, [rdx+48h]
0x10043b9f2  mov     [rsp+28h+arg_0], rax
0x10043b9f7  mov     rax, [rcx]
0x10043b9fa  mov     rdx, [rdx]
0x10043b9fd  call    qword ptr [rax+40h]
0x10043ba00  add     rsp, 20h
0x10043ba04  pop     rbx
0x10043ba05  retn
```
