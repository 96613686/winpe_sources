# FwDiagCopyString

- ea: `0x1800084a0`
- end: `0x180008534`
- name: `FwDiagCopyString`
- size: `148`
- prototype: `__int64 __fastcall(_WORD *Src, _QWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180007c80`
- `0x180007d60`
- `0x180008040`
- `0x1800082b0`
- `0x180008320`
- `0x180008440`

## callees

- `0x180002576`
- `0x1800084a0`

## import_xrefs

- `FirewallAPI!FwAlloc` at `0x1800084d8`
- `FirewallAPI!FwAlloc` at `0x1800084d8`

## pseudocode

```c
__int64 __fastcall FwDiagCopyString(_WORD *Src, _QWORD *a2)
{
  __int64 v4; // rax
  size_t v6; // rsi
  void *v7; // rax
  __int64 result; // rax

  if ( Src )
  {
    v4 = -1;
    while ( Src[++v4] != 0 )
      ;
    v6 = 2 * v4 + 2;
    v7 = (void *)FwAlloc(v6);
    *a2 = v7;
    if ( v7 )
    {
      memcpy_0(v7, Src, v6);
      return 0;
    }
    else
    {
      return 8;
    }
  }
  else
  {
    result = 0;
    *a2 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800084a0  mov     [rsp+arg_0], rbx
0x1800084a5  mov     [rsp+arg_8], rsi
0x1800084aa  push    rdi
0x1800084ab  sub     rsp, 20h
0x1800084af  mov     rdi, rdx
0x1800084b2  mov     rbx, rcx
0x1800084b5  test    rcx, rcx
0x1800084b8  jz      short loc_18000851B
0x1800084ba  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800084c1  cmp     word ptr [rcx+rax*2+2], 0
0x1800084c7  lea     rax, [rax+1]
0x1800084cb  jnz     short loc_1800084C1
0x1800084cd  lea     rsi, ds:2[rax*2]
0x1800084d5  mov     rcx, rsi
0x1800084d8  call    cs:__imp_FwAlloc
0x1800084de  mov     [rdi], rax
0x1800084e1  test    rax, rax
0x1800084e4  jnz     short loc_1800084FB
0x1800084e6  mov     eax, 8
0x1800084eb  mov     rbx, [rsp+28h+arg_0]
0x1800084f0  mov     rsi, [rsp+28h+arg_8]
0x1800084f5  add     rsp, 20h
0x1800084f9  pop     rdi
0x1800084fa  retn
0x1800084fb  mov     r8, rsi; Size
0x1800084fe  mov     rdx, rbx; Src
0x180008501  mov     rcx, rax; void *
0x180008504  call    memcpy_0
0x180008509  xor     eax, eax
0x18000850b  mov     rbx, [rsp+28h+arg_0]
0x180008510  mov     rsi, [rsp+28h+arg_8]
0x180008515  add     rsp, 20h
0x180008519  pop     rdi
0x18000851a  retn
0x18000851b  mov     rbx, [rsp+28h+arg_0]
0x180008520  xor     eax, eax
0x180008522  mov     rsi, [rsp+28h+arg_8]
0x180008527  mov     qword ptr [rdx], 0
0x18000852e  add     rsp, 20h
0x180008532  pop     rdi
0x180008533  retn
```
