# CStructuredReconstructor::ProcessAJunction(CScanner::CJunction *)

- ea: `0x100445830`
- end: `0x1004458bd`
- name: `?ProcessAJunction@CStructuredReconstructor@@UEAAJPEAVCJunction@CScanner@@@Z`
- size: `141`
- prototype: `__int64 __fastcall(CStructuredReconstructor *__hidden this, struct CScanner::CJunction *)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x10043ba10`
- `0x10043bce0`
- `0x100445830`

## pseudocode

```c
__int64 __fastcall CStructuredReconstructor::ProcessAJunction(
        CStructuredReconstructor *this,
        struct CScanner::CJunction *a2)
{
  __int64 result; // rax
  bool v4; // zf
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  *((_QWORD *)this + 12) = a2;
  result = CReconstructor::ProcessStrokeChains(this);
  if ( (int)result >= 0 )
  {
    _mm_lfence();
    result = CReconstructor::ProcessFillChains(this);
    if ( (int)result >= 0 )
    {
      _mm_lfence();
      if ( !*(_BYTE *)(*((_QWORD *)this + 12) + 90LL) )
      {
        _mm_lfence();
        v4 = *((_BYTE *)this + 144) == 0;
        v5 = *(_QWORD *)(*((_QWORD *)this + 12) + 72LL);
        if ( !v4 )
        {
          _mm_lfence();
          result = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 3) + 16LL))(
                     *((_QWORD *)this + 3),
                     4);
          if ( (int)result < 0 )
            return result;
          *((_BYTE *)this + 144) = 0;
        }
        _mm_lfence();
        return (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *))(**((_QWORD **)this + 3) + 64LL))(
                 *((_QWORD *)this + 3),
                 **((_QWORD **)this + 12),
                 1,
                 &v5);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x100445830  push    rbx
0x100445832  sub     rsp, 20h
0x100445836  mov     rbx, rcx
0x100445839  mov     [rcx+60h], rdx
0x10044583d  call    ?ProcessStrokeChains@CReconstructor@@IEAAJXZ; CReconstructor::ProcessStrokeChains(void)
0x100445842  test    eax, eax
0x100445844  js      short loc_1004458B7
0x100445846  lfence
0x100445849  mov     rcx, rbx; this
0x10044584c  call    ?ProcessFillChains@CReconstructor@@IEAAJXZ; CReconstructor::ProcessFillChains(void)
0x100445851  test    eax, eax
0x100445853  js      short loc_1004458B7
0x100445855  lfence
0x100445858  mov     rcx, [rbx+60h]
0x10044585c  cmp     byte ptr [rcx+5Ah], 0
0x100445860  jnz     short loc_1004458B7
0x100445862  lfence
0x100445865  cmp     byte ptr [rbx+90h], 0
0x10044586c  mov     rax, [rbx+60h]
0x100445870  mov     rcx, [rax+48h]
0x100445874  mov     [rsp+28h+arg_0], rcx
0x100445879  jz      short loc_100445898
0x10044587b  lfence
0x10044587e  mov     rcx, [rbx+18h]
0x100445882  mov     edx, 4
0x100445887  mov     rax, [rcx]
0x10044588a  call    qword ptr [rax+10h]
0x10044588d  test    eax, eax
0x10044588f  js      short loc_1004458B7
0x100445891  mov     byte ptr [rbx+90h], 0
0x100445898  lfence
0x10044589b  mov     rcx, [rbx+18h]
0x10044589f  lea     r9, [rsp+28h+arg_0]
0x1004458a4  mov     rdx, [rbx+60h]
0x1004458a8  mov     r8d, 1
0x1004458ae  mov     rax, [rcx]
0x1004458b1  mov     rdx, [rdx]
0x1004458b4  call    qword ptr [rax+40h]
0x1004458b7  add     rsp, 20h
0x1004458bb  pop     rbx
0x1004458bc  retn
```
