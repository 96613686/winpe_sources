# AMGetWideString

- ea: `0x180007214`
- end: `0x1800072b0`
- name: `AMGetWideString`
- size: `156`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180005130`
- `0x1800084a0`

## callees

- `0x180007214`
- `0x180033dfd`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000727a`
- `ole32!CoTaskMemAlloc` at `0x18000727a`

## pseudocode

```c
__int64 __fastcall AMGetWideString(_WORD *Src, _QWORD *a2)
{
  __int64 result; // rax
  _WORD *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rsi
  void *v8; // rax

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  if ( !Src )
    return 2147942487LL;
  v5 = Src;
  v6 = 50000;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  result = v6 == 0 ? 0x80070057 : 0;
  if ( v6 )
  {
    v7 = -(__int64)(v6 != 0) & (2 * (50000 - v6));
    v8 = CoTaskMemAlloc(v7 + 2);
    *a2 = v8;
    if ( v8 )
    {
      memcpy_0(v8, Src, v7 + 2);
      return 0;
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007214  push    rbx
0x180007216  push    rbp
0x180007217  push    rsi
0x180007218  push    rdi
0x180007219  sub     rsp, 28h
0x18000721d  xor     ebp, ebp
0x18000721f  mov     rdi, rdx
0x180007222  mov     rbx, rcx
0x180007225  test    rdx, rdx
0x180007228  jnz     short loc_180007231
0x18000722a  mov     eax, 80004003h
0x18000722f  jmp     short loc_1800072A7
0x180007231  mov     [rdx], rbp
0x180007234  test    rbx, rbx
0x180007237  jz      short loc_1800072A2
0x180007239  mov     edx, 0C350h
0x18000723e  mov     rax, rbx
0x180007241  mov     ecx, edx
0x180007243  cmp     [rax], bp
0x180007246  jz      short loc_180007252
0x180007248  add     rax, 2
0x18000724c  sub     rcx, 1
0x180007250  jnz     short loc_180007243
0x180007252  mov     rax, rcx
0x180007255  neg     rax
0x180007258  sbb     eax, eax
0x18000725a  not     eax
0x18000725c  and     eax, 80070057h
0x180007261  test    rcx, rcx
0x180007264  jz      short loc_1800072A7
0x180007266  sub     rdx, rcx
0x180007269  neg     rcx
0x18000726c  sbb     rax, rax
0x18000726f  lea     rsi, [rdx+rdx]
0x180007273  and     rsi, rax
0x180007276  lea     rcx, [rsi+2]; cb
0x18000727a  call    cs:__imp_CoTaskMemAlloc
0x180007280  mov     [rdi], rax
0x180007283  test    rax, rax
0x180007286  jnz     short loc_18000728F
0x180007288  mov     eax, 8007000Eh
0x18000728d  jmp     short loc_1800072A7
0x18000728f  lea     r8, [rsi+2]; Size
0x180007293  mov     rdx, rbx; Src
0x180007296  mov     rcx, rax; void *
0x180007299  call    memcpy_0
0x18000729e  xor     eax, eax
0x1800072a0  jmp     short loc_1800072A7
0x1800072a2  mov     eax, 80070057h
0x1800072a7  add     rsp, 28h
0x1800072ab  pop     rdi
0x1800072ac  pop     rsi
0x1800072ad  pop     rbp
0x1800072ae  pop     rbx
0x1800072af  retn
```
