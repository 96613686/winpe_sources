# winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetMany(uint,winrt::array_view<winrt::hstring>)

- ea: `0x180010d58`
- end: `0x180010e23`
- name: `?GetMany@?$vector_view_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@QEBAIIU?$array_view@Uhstring@winrt@@@2@@Z`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180010af0`
- `0x180010b70`

## callees

- `0x18000509c`
- `0x180005108`
- `0x180010d58`
- `0x1800139ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010e0d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180010e0d`

## pseudocode

```c
__int64 __fastcall winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetMany(
        __int64 a1,
        struct winrt::impl::hstring_header *a2,
        __int64 a3)
{
  __int64 v3; // r9
  __int64 v5; // rax
  __int64 v6; // rcx
  unsigned int v8; // ebp
  __int64 v9; // rax
  unsigned int v10; // ecx
  unsigned int v11; // r14d
  volatile signed __int32 **v12; // rbx
  winrt::impl **i; // rsi
  struct winrt::impl::hstring_header *v14; // rax
  volatile signed __int32 *v15; // rdi
  struct winrt::impl::hstring_header *v16; // r15
  int v17; // eax
  HANDLE ProcessHeap; // rax

  v3 = a1 + 16;
  if ( !a1 )
    v3 = 56;
  v5 = a1 + 8;
  if ( !a1 )
    v5 = 48;
  v6 = (__int64)(*(_QWORD *)v3 - *(_QWORD *)v5) >> 3;
  if ( (unsigned int)a2 >= (unsigned int)v6 )
    return 0;
  v8 = *(_DWORD *)(a3 + 8);
  v9 = a1 + 8;
  v10 = v6 - (_DWORD)a2;
  if ( v8 >= v10 )
    v8 = v10;
  v11 = v8;
  if ( !a1 )
    v9 = 48;
  if ( v8 )
  {
    v12 = *(volatile signed __int32 ***)a3;
    for ( i = (winrt::impl **)(*(_QWORD *)v9 + 8LL * (unsigned int)a2); ; ++i )
    {
      v14 = winrt::impl::duplicate_hstring(*i, a2);
      v15 = *v12;
      v16 = v14;
      if ( *v12 )
      {
        v17 = _InterlockedDecrement(v15 + 6);
        if ( v17 )
        {
          if ( v17 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v15);
        }
      }
      *v12 = (volatile signed __int32 *)v16;
      if ( !--v11 )
        break;
      ++v12;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180010d58  push    rbx
0x180010d5a  push    rbp
0x180010d5b  push    rsi
0x180010d5c  push    rdi
0x180010d5d  push    r14
0x180010d5f  push    r15
0x180010d61  sub     rsp, 28h
0x180010d65  test    rcx, rcx
0x180010d68  lea     r9, [rcx+10h]
0x180010d6c  mov     r10, rcx
0x180010d6f  mov     eax, 38h ; '8'
0x180010d74  cmovz   r9, rax
0x180010d78  mov     r11d, 30h ; '0'
0x180010d7e  lea     rax, [rcx+8]
0x180010d82  cmovz   rax, r11
0x180010d86  mov     rcx, [r9]
0x180010d89  sub     rcx, [rax]
0x180010d8c  sar     rcx, 3
0x180010d90  cmp     edx, ecx
0x180010d92  jb      short loc_180010D98
0x180010d94  xor     eax, eax
0x180010d96  jmp     short loc_180010E16
0x180010d98  mov     ebp, [r8+8]
0x180010d9c  lea     rax, [r10+8]
0x180010da0  sub     ecx, edx
0x180010da2  cmp     ebp, ecx
0x180010da4  cmovnb  ebp, ecx
0x180010da7  test    r10, r10
0x180010daa  mov     r14d, ebp
0x180010dad  cmovz   rax, r11
0x180010db1  test    ebp, ebp
0x180010db3  jz      short loc_180010E14
0x180010db5  mov     rax, [rax]
0x180010db8  mov     rbx, [r8]
0x180010dbb  mov     ecx, edx
0x180010dbd  lea     rsi, [rax+rcx*8]
0x180010dc1  mov     rcx, [rsi]; this
0x180010dc4  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180010dc9  mov     rdi, [rbx]
0x180010dcc  mov     r15, rax
0x180010dcf  test    rdi, rdi
0x180010dd2  jz      short loc_180010DFA
0x180010dd4  or      eax, 0FFFFFFFFh
0x180010dd7  lock xadd [rdi+18h], eax
0x180010ddc  sub     eax, 1
0x180010ddf  jnz     short loc_180010DF6
0x180010de1  nop
0x180010de2  call    WINRT_IMPL_GetProcessHeap
0x180010de7  mov     rcx, rax; hHeap
0x180010dea  mov     r8, rdi; lpMem
0x180010ded  xor     edx, edx; dwFlags
0x180010def  call    WINRT_IMPL_HeapFree
0x180010df4  jmp     short loc_180010DFA
0x180010df6  test    eax, eax
0x180010df8  js      short loc_180010E0D
0x180010dfa  mov     [rbx], r15
0x180010dfd  add     r14d, 0FFFFFFFFh
0x180010e01  jz      short loc_180010E14
0x180010e03  add     rbx, 8
0x180010e07  add     rsi, 8
0x180010e0b  jmp     short loc_180010DC1
0x180010e0d  call    cs:__imp_abort
0x180010e14  mov     eax, ebp
0x180010e16  add     rsp, 28h
0x180010e1a  pop     r15
0x180010e1c  pop     r14
0x180010e1e  pop     rdi
0x180010e1f  pop     rsi
0x180010e20  pop     rbp
0x180010e21  pop     rbx
0x180010e22  retn
```
