# GpdCreateCachedBinaryDataFromMemory

- ea: `0x1800720e0`
- end: `0x18007219f`
- name: `GpdCreateCachedBinaryDataFromMemory`
- size: `191`
- prototype: `_OWORD *__fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800278e0`

## callees

- `0x180007150`
- `0x18003e45c`
- `0x1800720e0`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18007210c`
- `KERNEL32!LocalAlloc` at `0x18007210c`
- `KERNEL32!SetLastError` at `0x180072180`
- `KERNEL32!SetLastError` at `0x180072180`

## string_xrefs

- `0x18007216f`: `GpdCreateCachedBinaryDataFromMemory`

## pseudocode

```c
_OWORD *__fastcall GpdCreateCachedBinaryDataFromMemory(__int64 a1, unsigned int a2)
{
  _OWORD *v4; // rax
  _OWORD *v5; // rbx

  if ( a2 >= 0xE0 )
  {
    v4 = LocalAlloc(0, 0xF8u);
    v5 = v4;
    if ( v4 )
    {
      *v4 = *(_OWORD *)a1;
      v4[1] = *(_OWORD *)(a1 + 16);
      v4[2] = *(_OWORD *)(a1 + 32);
      v4[3] = *(unsigned __int64 *)(a1 + 48);
      *((_QWORD *)v4 + 8) = 0;
      *((_QWORD *)v4 + 9) = a1;
      *((_DWORD *)v4 + 20) = a2;
      if ( (unsigned int)BInitBUDPointers((__int64)v4) )
        return v5;
    }
    WriteDbgTraceErrorGpd((__int64)"GpdCreateCachedBinaryDataFromMemory", "Out of memory");
  }
  else
  {
    WriteDbgTraceErrorGpd((__int64)"GpdCreateCachedBinaryDataFromMemory", "Invalid binary GPD data");
  }
  SetLastError(0xDu);
  return 0;
}

```

## disassembly

```asm
0x1800720e0  mov     [rsp+arg_0], rbx
0x1800720e5  mov     [rsp+arg_8], rsi
0x1800720ea  push    rdi
0x1800720eb  sub     rsp, 20h
0x1800720ef  mov     esi, edx
0x1800720f1  mov     rdi, rcx
0x1800720f4  cmp     edx, 0E0h
0x1800720fa  jnb     short loc_180072105
0x1800720fc  lea     rdx, aInvalidBinaryG; "Invalid binary GPD data"
0x180072103  jmp     short loc_18007216F
0x180072105  mov     edx, 0F8h; uBytes
0x18007210a  xor     ecx, ecx; uFlags
0x18007210c  call    cs:__imp_LocalAlloc
0x180072113  nop     dword ptr [rax+rax+00h]
0x180072118  mov     rbx, rax
0x18007211b  test    rax, rax
0x18007211e  jz      short loc_180072168
0x180072120  movups  xmm0, xmmword ptr [rdi]
0x180072123  mov     rcx, rax
0x180072126  movups  xmmword ptr [rax], xmm0
0x180072129  movups  xmm1, xmmword ptr [rdi+10h]
0x18007212d  movups  xmmword ptr [rax+10h], xmm1
0x180072131  movups  xmm0, xmmword ptr [rdi+20h]
0x180072135  movups  xmmword ptr [rax+20h], xmm0
0x180072139  movsd   xmm1, qword ptr [rdi+30h]
0x18007213e  movsd   qword ptr [rax+30h], xmm1
0x180072143  mov     qword ptr [rax+38h], 0
0x18007214b  mov     qword ptr [rax+40h], 0
0x180072153  mov     [rax+48h], rdi
0x180072157  mov     [rax+50h], esi
0x18007215a  call    BInitBUDPointers
0x18007215f  test    eax, eax
0x180072161  jz      short loc_180072168
0x180072163  mov     rax, rbx
0x180072166  jmp     short loc_18007218E
0x180072168  lea     rdx, aOutOfMemory; "Out of memory"
0x18007216f  lea     rcx, aGpdcreatecache; "GpdCreateCachedBinaryDataFromMemory"
0x180072176  call    WriteDbgTraceErrorGpd
0x18007217b  mov     ecx, 0Dh; dwErrCode
0x180072180  call    cs:__imp_SetLastError
0x180072187  nop     dword ptr [rax+rax+00h]
0x18007218c  xor     eax, eax
0x18007218e  mov     rbx, [rsp+28h+arg_0]
0x180072193  mov     rsi, [rsp+28h+arg_8]
0x180072198  add     rsp, 20h
0x18007219c  pop     rdi
0x18007219d  retn
```
