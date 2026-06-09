# CoTaskMemAllocWStr(ushort * &,ushort const *)

- ea: `0x180018480`
- end: `0x1800184d5`
- name: `?CoTaskMemAllocWStr@@YAJAEAPEAGPEBG@Z`
- size: `85`
- prototype: `int(unsigned __int16 **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c820`

## callees

- `0x180018480`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800184c4`
- `msvcrt!wcscpy_s` at `0x1800184c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800184a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800184a6`

## pseudocode

```c
__int64 __fastcall CoTaskMemAllocWStr(unsigned __int16 **a1, const unsigned __int16 *a2)
{
  __int64 v2; // rax
  rsize_t v5; // rdi
  unsigned __int16 *v6; // rax

  v2 = -1;
  do
    ++v2;
  while ( a2[v2] );
  v5 = v2 + 1;
  v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * (v2 + 1));
  *a1 = v6;
  if ( !v6 )
    return 2147942414LL;
  wcscpy_s(v6, v5, a2);
  return 0;
}

```

## disassembly

```asm
0x180018480  push    rbx
0x180018482  push    rbp
0x180018483  push    rsi
0x180018484  push    rdi
0x180018485  sub     rsp, 28h
0x180018489  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001848d  mov     rbx, rdx
0x180018490  xor     ebp, ebp
0x180018492  mov     rsi, rcx
0x180018495  inc     rax
0x180018498  cmp     [rdx+rax*2], bp
0x18001849c  jnz     short loc_180018495
0x18001849e  lea     rdi, [rax+1]
0x1800184a2  lea     rcx, [rdi+rdi]; cb
0x1800184a6  call    cs:__imp_CoTaskMemAlloc
0x1800184ac  mov     [rsi], rax
0x1800184af  test    rax, rax
0x1800184b2  jnz     short loc_1800184BB
0x1800184b4  mov     eax, 8007000Eh
0x1800184b9  jmp     short loc_1800184CC
0x1800184bb  mov     r8, rbx; Source
0x1800184be  mov     rdx, rdi; SizeInWords
0x1800184c1  mov     rcx, rax; Destination
0x1800184c4  call    cs:__imp_wcscpy_s
0x1800184ca  xor     eax, eax
0x1800184cc  add     rsp, 28h
0x1800184d0  pop     rdi
0x1800184d1  pop     rsi
0x1800184d2  pop     rbp
0x1800184d3  pop     rbx
0x1800184d4  retn
```
