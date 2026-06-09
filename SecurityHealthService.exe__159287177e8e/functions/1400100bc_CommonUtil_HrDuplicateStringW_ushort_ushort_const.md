# CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)

- ea: `0x1400100bc`
- end: `0x140010104`
- name: `?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z`
- size: `72`
- prototype: `__int64 __fastcall(void **this, unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003db4`
- `0x140004588`
- `0x14000ea5c`
- `0x14000eb7c`
- `0x140011260`

## callees

- `0x140005578`
- `0x1400100bc`
- `0x1400121ec`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrDuplicateStringW(void **this, unsigned __int16 **a2, const unsigned __int16 *a3)
{
  __int64 v3; // rax
  __int64 v6; // rsi
  __int64 result; // rax

  v3 = -1;
  do
    ++v3;
  while ( *((_WORD *)a2 + v3) );
  v6 = v3 + 1;
  result = CommonUtil::MpNewBuffer<unsigned short>(this, v3 + 1);
  if ( (int)result >= 0 )
  {
    memmove_0(*this, a2, 2 * v6);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400100bc  push    rbx
0x1400100be  push    rbp
0x1400100bf  push    rsi
0x1400100c0  push    rdi
0x1400100c1  sub     rsp, 28h
0x1400100c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400100c9  mov     rbx, rdx
0x1400100cc  xor     ebp, ebp
0x1400100ce  mov     rdi, rcx
0x1400100d1  inc     rax
0x1400100d4  cmp     [rdx+rax*2], bp
0x1400100d8  jnz     short loc_1400100D1
0x1400100da  lea     rsi, [rax+1]
0x1400100de  mov     rdx, rsi
0x1400100e1  call    ??$MpNewBuffer@G@CommonUtil@@YAJPEAPEAG_K@Z; CommonUtil::MpNewBuffer<ushort>(ushort * *,unsigned __int64)
0x1400100e6  test    eax, eax
0x1400100e8  js      short loc_1400100FB
0x1400100ea  mov     rcx, [rdi]; void *
0x1400100ed  lea     r8, [rsi+rsi]; Size
0x1400100f1  mov     rdx, rbx; Src
0x1400100f4  call    memmove_0
0x1400100f9  mov     eax, ebp
0x1400100fb  add     rsp, 28h
0x1400100ff  pop     rdi
0x140010100  pop     rsi
0x140010101  pop     rbp
0x140010102  pop     rbx
0x140010103  retn
```
