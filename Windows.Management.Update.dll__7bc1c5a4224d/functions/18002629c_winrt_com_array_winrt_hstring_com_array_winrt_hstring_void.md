# winrt::com_array<winrt::hstring>::~com_array<winrt::hstring>(void)

- ea: `0x18002629c`
- end: `0x18002631d`
- name: `??1?$com_array@Uhstring@winrt@@@winrt@@QEAA@XZ`
- size: `129`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027310`
- `0x180029088`

## callees

- `0x180008653`
- `0x18000866b`
- `0x1800088a9`
- `0x18002629c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180026316`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180026316`

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
0x18002629c  push    rbx
0x18002629e  push    rbp
0x18002629f  push    rsi
0x1800262a0  push    rdi
0x1800262a1  sub     rsp, 28h
0x1800262a5  mov     rbx, [rcx]
0x1800262a8  mov     rdi, rcx
0x1800262ab  test    rbx, rbx
0x1800262ae  jz      short loc_18002630D
0x1800262b0  mov     eax, [rcx+8]
0x1800262b3  lea     rbp, [rbx+rax*8]
0x1800262b7  jmp     short loc_1800262F2
0x1800262b9  mov     rsi, [rbx]
0x1800262bc  test    rsi, rsi
0x1800262bf  jz      short loc_1800262EE
0x1800262c1  or      eax, 0FFFFFFFFh
0x1800262c4  lock xadd [rsi+18h], eax
0x1800262c9  sub     eax, 1
0x1800262cc  jnz     short loc_1800262E3
0x1800262ce  nop
0x1800262cf  call    WINRT_IMPL_GetProcessHeap
0x1800262d4  mov     rcx, rax; hHeap
0x1800262d7  mov     r8, rsi; lpMem
0x1800262da  xor     edx, edx; dwFlags
0x1800262dc  call    WINRT_IMPL_HeapFree
0x1800262e1  jmp     short loc_1800262E7
0x1800262e3  test    eax, eax
0x1800262e5  js      short loc_180026316
0x1800262e7  mov     qword ptr [rbx], 0
0x1800262ee  add     rbx, 8
0x1800262f2  cmp     rbx, rbp
0x1800262f5  jnz     short loc_1800262B9
0x1800262f7  mov     rcx, [rdi]; pv
0x1800262fa  call    CoTaskMemFree_0
0x1800262ff  mov     qword ptr [rdi], 0
0x180026306  mov     dword ptr [rdi+8], 0
0x18002630d  add     rsp, 28h
0x180026311  pop     rdi
0x180026312  pop     rsi
0x180026313  pop     rbp
0x180026314  pop     rbx
0x180026315  retn
0x180026316  call    cs:__imp_abort
```
