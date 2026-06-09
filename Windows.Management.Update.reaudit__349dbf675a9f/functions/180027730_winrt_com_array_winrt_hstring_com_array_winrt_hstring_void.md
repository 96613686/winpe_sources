# winrt::com_array<winrt::hstring>::~com_array<winrt::hstring>(void)

- ea: `0x180027730`
- end: `0x1800277c6`
- name: `??1?$com_array@Uhstring@winrt@@@winrt@@QEAA@XZ`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028770`
- `0x18002b030`

## callees

- `0x180008bf4`
- `0x180008c0c`
- `0x180008e5d`
- `0x180027730`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800277b9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800277b9`

## pseudocode

```c
void __fastcall winrt::com_array<winrt::hstring>::~com_array<winrt::hstring>(__int64 a1)
{
  volatile signed __int32 **v1; // rbx
  volatile signed __int32 **v3; // rbp
  volatile signed __int32 *v4; // rsi
  int v5; // eax
  HANDLE ProcessHeap; // rax

  v1 = *(volatile signed __int32 ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = &v1[*(unsigned int *)(a1 + 8)];
    while ( v1 != v3 )
    {
      v4 = *v1;
      if ( *v1 )
      {
        v5 = _InterlockedDecrement(v4 + 6);
        if ( v5 )
        {
          if ( v5 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v4);
        }
        *v1 = 0;
      }
      ++v1;
    }
    CoTaskMemFree_0(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
    *(_DWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180027730  mov     [rsp+arg_0], rbx
0x180027735  mov     [rsp+arg_8], rbp
0x18002773a  mov     [rsp+arg_10], rsi
0x18002773f  push    rdi
0x180027740  sub     rsp, 20h
0x180027744  mov     rbx, [rcx]
0x180027747  mov     rdi, rcx
0x18002774a  test    rbx, rbx
0x18002774d  jz      short loc_1800277A3
0x18002774f  mov     eax, [rcx+8]
0x180027752  lea     rbp, [rbx+rax*8]
0x180027756  jmp     short loc_18002778E
0x180027758  mov     rsi, [rbx]
0x18002775b  test    rsi, rsi
0x18002775e  jz      short loc_18002778A
0x180027760  or      eax, 0FFFFFFFFh
0x180027763  lock xadd [rsi+18h], eax
0x180027768  sub     eax, 1
0x18002776b  jnz     short loc_180027782
0x18002776d  nop
0x18002776e  call    WINRT_IMPL_GetProcessHeap
0x180027773  mov     rcx, rax; hHeap
0x180027776  mov     r8, rsi; lpMem
0x180027779  xor     edx, edx; dwFlags
0x18002777b  call    WINRT_IMPL_HeapFree
0x180027780  jmp     short loc_180027786
0x180027782  test    eax, eax
0x180027784  js      short loc_1800277B9
0x180027786  and     qword ptr [rbx], 0
0x18002778a  add     rbx, 8
0x18002778e  cmp     rbx, rbp
0x180027791  jnz     short loc_180027758
0x180027793  mov     rcx, [rdi]; pv
0x180027796  call    CoTaskMemFree_0
0x18002779b  and     qword ptr [rdi], 0
0x18002779f  and     dword ptr [rdi+8], 0
0x1800277a3  mov     rbx, [rsp+28h+arg_0]
0x1800277a8  mov     rbp, [rsp+28h+arg_8]
0x1800277ad  mov     rsi, [rsp+28h+arg_10]
0x1800277b2  add     rsp, 20h
0x1800277b6  pop     rdi
0x1800277b7  retn
0x1800277b9  call    cs:__imp_abort
```
