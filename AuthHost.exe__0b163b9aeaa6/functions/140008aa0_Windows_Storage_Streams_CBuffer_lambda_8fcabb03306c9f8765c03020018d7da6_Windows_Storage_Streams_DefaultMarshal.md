# Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>::AddRef(void)

- ea: `0x140008aa0`
- end: `0x140008ae1`
- name: `?AddRef@?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@UEAAKXZ`
- size: `65`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008af0`
- `0x140008b00`
- `0x140008b10`
- `0x140008b20`

## callees

- `0x140005d90`
- `0x140008aa0`

## pseudocode

```c
__int64 __fastcall Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>::AddRef(
        __int64 a1,
        volatile int *a2)
{
  signed __int64 v2; // rax
  signed __int64 v3; // rtt

  v2 = *(_QWORD *)(a1 + 72);
  while ( v2 >= 0 )
  {
    if ( (_DWORD)v2 == 0x7FFFFFFF )
    {
      LODWORD(a2) = 0x7FFFFFFF;
      return (unsigned int)a2;
    }
    a2 = (volatile int *)(v2 + 1);
    v3 = v2;
    v2 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 72), v2 + 1, v2);
    if ( v3 == v2 )
      return (unsigned int)a2;
  }
  LODWORD(a2) = Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(2 * v2 + 16), a2);
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x140008aa0  sub     rsp, 28h
0x140008aa4  mov     rax, [rcx+48h]
0x140008aa8  mov     r8d, 7FFFFFFFh
0x140008aae  test    rax, rax
0x140008ab1  js      short loc_140008ACB
0x140008ab3  cmp     eax, r8d
0x140008ab6  jz      short loc_140008AC6
0x140008ab8  lea     rdx, [rax+1]
0x140008abc  lock cmpxchg [rcx+48h], rdx
0x140008ac2  jnz     short loc_140008AAE
0x140008ac4  jmp     short loc_140008ADA
0x140008ac6  mov     edx, r8d; volatile int *
0x140008ac9  jmp     short loc_140008ADA
0x140008acb  lea     rcx, ds:10h[rax*2]; this
0x140008ad3  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x140008ad8  mov     edx, eax
0x140008ada  mov     eax, edx
0x140008adc  add     rsp, 28h
0x140008ae0  retn
```
