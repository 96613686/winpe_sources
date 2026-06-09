# winrt::impl::removed_value<winrt::hstring,void>::~removed_value<winrt::hstring,void>(void)

- ea: `0x18001429c`
- end: `0x1800142f4`
- name: `??1?$removed_value@Uhstring@winrt@@X@impl@winrt@@QEAA@XZ`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180020622`

## callees

- `0x180004718`
- `0x180004784`
- `0x18001429c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800142ed`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800142ed`

## pseudocode

```c
void __fastcall winrt::impl::removed_value<winrt::hstring,void>::~removed_value<winrt::hstring,void>(__int64 a1)
{
  volatile signed __int32 *v2; // rdi
  int v3; // eax
  HANDLE ProcessHeap; // rax

  if ( *(_BYTE *)(a1 + 8) )
  {
    v2 = *(volatile signed __int32 **)a1;
    if ( *(_QWORD *)a1 )
    {
      v3 = _InterlockedDecrement(v2 + 6);
      if ( v3 )
      {
        if ( v3 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v2);
      }
      *(_QWORD *)a1 = 0;
    }
  }
}

```

## disassembly

```asm
0x18001429c  mov     [rsp+arg_0], rbx
0x1800142a1  push    rdi
0x1800142a2  sub     rsp, 20h
0x1800142a6  cmp     byte ptr [rcx+8], 0
0x1800142aa  mov     rbx, rcx
0x1800142ad  jz      short loc_1800142DE
0x1800142af  mov     rdi, [rcx]
0x1800142b2  test    rdi, rdi
0x1800142b5  jz      short loc_1800142DE
0x1800142b7  or      eax, 0FFFFFFFFh
0x1800142ba  lock xadd [rdi+18h], eax
0x1800142bf  sub     eax, 1
0x1800142c2  jnz     short loc_1800142E9
0x1800142c4  nop
0x1800142c5  call    WINRT_IMPL_GetProcessHeap
0x1800142ca  mov     rcx, rax; hHeap
0x1800142cd  mov     r8, rdi; lpMem
0x1800142d0  xor     edx, edx; dwFlags
0x1800142d2  call    WINRT_IMPL_HeapFree
0x1800142d7  mov     qword ptr [rbx], 0
0x1800142de  mov     rbx, [rsp+28h+arg_0]
0x1800142e3  add     rsp, 20h
0x1800142e7  pop     rdi
0x1800142e8  retn
0x1800142e9  test    eax, eax
0x1800142eb  jns     short loc_1800142D7
0x1800142ed  call    cs:__imp_abort
```
