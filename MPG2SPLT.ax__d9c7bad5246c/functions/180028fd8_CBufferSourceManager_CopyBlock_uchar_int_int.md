# CBufferSourceManager::CopyBlock(uchar *,int,int *)

- ea: `0x180028fd8`
- end: `0x180029038`
- name: `?CopyBlock@CBufferSourceManager@@IEAAHPEAEHPEAH@Z`
- size: `96`
- prototype: `__int64 __fastcall(CBufferSourceManager *__hidden this, unsigned __int8 *, int, int *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180029040`
- `0x180029b4c`
- `0x18002a2f0`
- `0x18002a480`
- `0x18002a9a0`

## callees

- `0x180028fd8`
- `0x180033dfd`

## pseudocode

```c
__int64 __fastcall CBufferSourceManager::CopyBlock(CBufferSourceManager *this, unsigned __int8 *a2, int a3, int *a4)
{
  __int64 v5; // rbp
  int v7; // esi
  __int64 result; // rax

  v5 = a3;
  if ( *((_QWORD *)this + 11) )
  {
    v7 = *((_DWORD *)this + 22) + *((_DWORD *)this + 24) - *((_DWORD *)this + 26);
    *a4 = v7;
    if ( a3 >= 0 && a3 <= v7 )
    {
      memcpy_0(*((void **)this + 13), a2, a3);
      result = 1;
      *((_QWORD *)this + 13) += v5;
      *a4 = v7 - v5;
      return result;
    }
  }
  else
  {
    *a4 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180028fd8  push    rbx
0x180028fda  push    rbp
0x180028fdb  push    rsi
0x180028fdc  push    rdi
0x180028fdd  push    r14
0x180028fdf  sub     rsp, 20h
0x180028fe3  cmp     qword ptr [rcx+58h], 0
0x180028fe8  mov     r14, r9
0x180028feb  movsxd  rbp, r8d
0x180028fee  mov     rdi, rcx
0x180028ff1  jz      short loc_180029024
0x180028ff3  mov     esi, [rcx+60h]
0x180028ff6  sub     esi, [rcx+68h]
0x180028ff9  add     esi, [rcx+58h]
0x180028ffc  mov     [r9], esi
0x180028fff  test    r8d, r8d
0x180029002  js      short loc_18002902B
0x180029004  cmp     ebp, esi
0x180029006  jg      short loc_18002902B
0x180029008  mov     rcx, [rcx+68h]; void *
0x18002900c  mov     r8, rbp; Size
0x18002900f  call    memcpy_0
0x180029014  sub     esi, ebp
0x180029016  mov     eax, 1
0x18002901b  add     [rdi+68h], rbp
0x18002901f  mov     [r14], esi
0x180029022  jmp     short loc_18002902D
0x180029024  mov     dword ptr [r9], 0
0x18002902b  xor     eax, eax
0x18002902d  add     rsp, 20h
0x180029031  pop     r14
0x180029033  pop     rdi
0x180029034  pop     rsi
0x180029035  pop     rbp
0x180029036  pop     rbx
0x180029037  retn
```
