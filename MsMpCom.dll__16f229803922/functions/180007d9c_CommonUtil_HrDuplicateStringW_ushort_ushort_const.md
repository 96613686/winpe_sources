# CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)

- ea: `0x180007d9c`
- end: `0x180007de4`
- name: `?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z`
- size: `72`
- prototype: `int(CommonUtil *__hidden this, unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000627c`
- `0x180006f68`
- `0x1800070b8`

## callees

- `0x180001cf2`
- `0x180006ce4`
- `0x180007d9c`

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
0x180007d9c  push    rbx
0x180007d9e  push    rbp
0x180007d9f  push    rsi
0x180007da0  push    rdi
0x180007da1  sub     rsp, 28h
0x180007da5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007da9  mov     rbx, rdx
0x180007dac  xor     ebp, ebp
0x180007dae  mov     rdi, rcx
0x180007db1  inc     rax
0x180007db4  cmp     [rdx+rax*2], bp
0x180007db8  jnz     short loc_180007DB1
0x180007dba  lea     rsi, [rax+1]
0x180007dbe  mov     rdx, rsi
0x180007dc1  call    ??$MpNewBuffer@G@CommonUtil@@YAJPEAPEAG_K@Z; CommonUtil::MpNewBuffer<ushort>(ushort * *,unsigned __int64)
0x180007dc6  test    eax, eax
0x180007dc8  js      short loc_180007DDB
0x180007dca  mov     rcx, [rdi]; void *
0x180007dcd  lea     r8, [rsi+rsi]; Size
0x180007dd1  mov     rdx, rbx; Src
0x180007dd4  call    memmove_0
0x180007dd9  mov     eax, ebp
0x180007ddb  add     rsp, 28h
0x180007ddf  pop     rdi
0x180007de0  pop     rsi
0x180007de1  pop     rbp
0x180007de2  pop     rbx
0x180007de3  retn
```
