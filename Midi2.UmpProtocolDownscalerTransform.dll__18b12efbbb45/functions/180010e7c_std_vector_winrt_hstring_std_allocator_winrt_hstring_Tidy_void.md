# std::vector<winrt::hstring,std::allocator<winrt::hstring>>::_Tidy(void)

- ea: `0x180010e7c`
- end: `0x180010f47`
- name: `?_Tidy@?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@AEAAXXZ`
- size: `203`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000c450`
- `0x18000d01c`
- `0x18000d360`
- `0x18000d800`

## callees

- `0x180002e94`
- `0x180003ab0`
- `0x180003b1c`
- `0x180010e7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010f0e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010f0e`

## pseudocode

```c
void __fastcall std::vector<winrt::hstring>::_Tidy(__int64 a1)
{
  volatile signed __int32 **v1; // rbx
  volatile signed __int32 **v3; // rbp
  volatile signed __int32 *v4; // rsi
  int v5; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 **v7; // rcx
  volatile signed __int32 **v8; // rax

  v1 = *(volatile signed __int32 ***)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(volatile signed __int32 ***)(a1 + 8);
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
    v7 = *(volatile signed __int32 ***)a1;
    if ( (unsigned __int64)(8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3)) < 0x1000 )
    {
      v8 = *(volatile signed __int32 ***)a1;
    }
    else
    {
      v8 = (volatile signed __int32 **)*(v7 - 1);
      if ( (unsigned __int64)((char *)v7 - (char *)v8 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v8);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180010e7c  push    rbx
0x180010e7e  push    rbp
0x180010e7f  push    rsi
0x180010e80  push    rdi
0x180010e81  sub     rsp, 28h
0x180010e85  mov     rbx, [rcx]
0x180010e88  mov     rdi, rcx
0x180010e8b  test    rbx, rbx
0x180010e8e  jz      loc_180010F3E
0x180010e94  mov     rbp, [rcx+8]
0x180010e98  jmp     short loc_180010ED3
0x180010e9a  mov     rsi, [rbx]
0x180010e9d  test    rsi, rsi
0x180010ea0  jz      short loc_180010ECF
0x180010ea2  or      eax, 0FFFFFFFFh
0x180010ea5  lock xadd [rsi+18h], eax
0x180010eaa  sub     eax, 1
0x180010ead  jnz     short loc_180010EC4
0x180010eaf  nop
0x180010eb0  call    WINRT_IMPL_GetProcessHeap
0x180010eb5  mov     rcx, rax; hHeap
0x180010eb8  mov     r8, rsi; lpMem
0x180010ebb  xor     edx, edx; dwFlags
0x180010ebd  call    WINRT_IMPL_HeapFree
0x180010ec2  jmp     short loc_180010EC8
0x180010ec4  test    eax, eax
0x180010ec6  js      short loc_180010F0E
0x180010ec8  mov     qword ptr [rbx], 0
0x180010ecf  add     rbx, 8
0x180010ed3  cmp     rbx, rbp
0x180010ed6  jnz     short loc_180010E9A
0x180010ed8  mov     rcx, [rdi]
0x180010edb  mov     rax, [rdi+10h]
0x180010edf  sub     rax, rcx
0x180010ee2  sar     rax, 3
0x180010ee6  lea     rdx, ds:0[rax*8]
0x180010eee  cmp     rdx, 1000h
0x180010ef5  jb      short loc_180010F1C
0x180010ef7  mov     rax, [rcx-8]
0x180010efb  sub     rcx, rax
0x180010efe  sub     rcx, 8
0x180010f02  cmp     rcx, 1Fh
0x180010f06  ja      short loc_180010F15
0x180010f08  add     rdx, 27h ; '''
0x180010f0c  jmp     short loc_180010F1F
0x180010f0e  call    cs:__imp_abort
0x180010f15  mov     ecx, 5
0x180010f1a  int     29h; Win8: RtlFailFast(ecx)
0x180010f1c  mov     rax, rcx
0x180010f1f  mov     rcx, rax; Block
0x180010f22  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180010f27  mov     qword ptr [rdi], 0
0x180010f2e  mov     qword ptr [rdi+8], 0
0x180010f36  mov     qword ptr [rdi+10h], 0
0x180010f3e  add     rsp, 28h
0x180010f42  pop     rdi
0x180010f43  pop     rsi
0x180010f44  pop     rbp
0x180010f45  pop     rbx
0x180010f46  retn
```
