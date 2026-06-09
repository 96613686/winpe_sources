# CCbsStringArray::CopyAndAdd(wchar_t const *)

- ea: `0x1400072a8`
- end: `0x14000730a`
- name: `?CopyAndAdd@CCbsStringArray@@QEAAJPEB_W@Z`
- size: `98`
- prototype: `__int64 __fastcall(CCbsStringArray *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1400089c0`

## callees

- `0x140001fcc`
- `0x1400072a8`
- `0x140007334`
- `0x140011884`

## pseudocode

```c
__int64 __fastcall CCbsStringArray::CopyAndAdd(CCbsStringArray *this, const wchar_t *a2)
{
  __int64 result; // rax
  int v4; // ebx
  wchar_t *v5; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v5 = 0;
  result = SczAllocFromSz(&v5, a2);
  if ( (int)result >= 0 )
  {
    v4 = CCbsArrayBase<wchar_t *,CCbsStringArray>::InsertAt(this, &v5, *((_QWORD *)this + 3));
    if ( v4 >= 0 )
    {
      return 0;
    }
    else
    {
      if ( v5 )
        operator delete(v5 - 4);
      return (unsigned int)v4;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400072a8  push    rbx
0x1400072aa  sub     rsp, 20h
0x1400072ae  mov     rbx, rcx
0x1400072b1  test    rdx, rdx
0x1400072b4  jnz     short loc_1400072BD
0x1400072b6  mov     eax, 80070057h
0x1400072bb  jmp     short loc_140007304
0x1400072bd  lea     rcx, [rsp+28h+arg_8]
0x1400072c2  mov     [rsp+28h+arg_8], 0
0x1400072cb  call    SczAllocFromSz
0x1400072d0  test    eax, eax
0x1400072d2  js      short loc_140007304
0x1400072d4  mov     r8, [rbx+18h]
0x1400072d8  lea     rdx, [rsp+28h+arg_8]
0x1400072dd  mov     rcx, rbx
0x1400072e0  call    ?InsertAt@?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@QEAAJAEBQEA_W_K@Z; CCbsArrayBase<wchar_t *,CCbsStringArray>::InsertAt(wchar_t * const &,unsigned __int64)
0x1400072e5  mov     ebx, eax
0x1400072e7  test    eax, eax
0x1400072e9  jns     short loc_140007302
0x1400072eb  mov     rcx, [rsp+28h+arg_8]
0x1400072f0  test    rcx, rcx
0x1400072f3  jz      short loc_1400072FE
0x1400072f5  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1400072f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400072fe  mov     eax, ebx
0x140007300  jmp     short loc_140007304
0x140007302  xor     eax, eax
0x140007304  add     rsp, 20h
0x140007308  pop     rbx
0x140007309  retn
```
