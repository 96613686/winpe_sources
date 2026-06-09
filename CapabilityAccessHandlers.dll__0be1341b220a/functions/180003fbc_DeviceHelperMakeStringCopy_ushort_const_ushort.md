# _DeviceHelperMakeStringCopy(ushort const *,ushort * *)

- ea: `0x180003fbc`
- end: `0x18000400f`
- name: `?_DeviceHelperMakeStringCopy@@YAJPEBGPEAPEAG@Z`
- size: `83`
- prototype: `int __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002cd8`
- `0x180003e68`
- `0x180013168`

## callees

- `0x180003fbc`
- `0x18000968c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003fe2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180003fe2`

## pseudocode

```c
int __fastcall _DeviceHelperMakeStringCopy(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 v2; // rbx
  unsigned __int16 *v5; // rax

  v2 = -1;
  do
    ++v2;
  while ( a1[v2] );
  v5 = (unsigned __int16 *)CoTaskMemAlloc(2 * v2 + 2);
  *a2 = v5;
  if ( v5 )
    return StringCchCopyW(v5, v2 + 1, a1);
  else
    return -2147024882;
}

```

## disassembly

```asm
0x180003fbc  push    rbx
0x180003fbe  push    rbp
0x180003fbf  push    rsi
0x180003fc0  push    rdi
0x180003fc1  sub     rsp, 28h
0x180003fc5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003fc9  mov     rsi, rdx
0x180003fcc  xor     ebp, ebp
0x180003fce  mov     rdi, rcx
0x180003fd1  inc     rbx
0x180003fd4  cmp     [rcx+rbx*2], bp
0x180003fd8  jnz     short loc_180003FD1
0x180003fda  lea     rcx, ds:2[rbx*2]; cb
0x180003fe2  call    cs:__imp_CoTaskMemAlloc
0x180003fe8  mov     [rsi], rax
0x180003feb  test    rax, rax
0x180003fee  jnz     short loc_180003FF7
0x180003ff0  mov     eax, 8007000Eh
0x180003ff5  jmp     short loc_180004006
0x180003ff7  lea     rdx, [rbx+1]; unsigned __int64
0x180003ffb  mov     r8, rdi; unsigned __int16 *
0x180003ffe  mov     rcx, rax; unsigned __int16 *
0x180004001  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004006  add     rsp, 28h
0x18000400a  pop     rdi
0x18000400b  pop     rsi
0x18000400c  pop     rbp
0x18000400d  pop     rbx
0x18000400e  retn
```
