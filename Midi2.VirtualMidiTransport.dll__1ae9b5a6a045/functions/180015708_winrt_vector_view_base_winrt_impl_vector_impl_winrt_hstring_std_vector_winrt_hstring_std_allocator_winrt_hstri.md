# winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetMany(uint,winrt::array_view<winrt::hstring>)

- ea: `0x180015708`
- end: `0x1800157d3`
- name: `?GetMany@?$vector_view_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@QEBAIIU?$array_view@Uhstring@winrt@@@2@@Z`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800154a0`
- `0x180015520`

## callees

- `0x180004718`
- `0x180004784`
- `0x180015708`
- `0x1800194c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800157bd`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800157bd`

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
0x180015708  push    rbx
0x18001570a  push    rbp
0x18001570b  push    rsi
0x18001570c  push    rdi
0x18001570d  push    r14
0x18001570f  push    r15
0x180015711  sub     rsp, 28h
0x180015715  test    rcx, rcx
0x180015718  lea     r9, [rcx+10h]
0x18001571c  mov     r10, rcx
0x18001571f  mov     eax, 38h ; '8'
0x180015724  cmovz   r9, rax
0x180015728  mov     r11d, 30h ; '0'
0x18001572e  lea     rax, [rcx+8]
0x180015732  cmovz   rax, r11
0x180015736  mov     rcx, [r9]
0x180015739  sub     rcx, [rax]
0x18001573c  sar     rcx, 3
0x180015740  cmp     edx, ecx
0x180015742  jb      short loc_180015748
0x180015744  xor     eax, eax
0x180015746  jmp     short loc_1800157C6
0x180015748  mov     ebp, [r8+8]
0x18001574c  lea     rax, [r10+8]
0x180015750  sub     ecx, edx
0x180015752  cmp     ebp, ecx
0x180015754  cmovnb  ebp, ecx
0x180015757  test    r10, r10
0x18001575a  mov     r14d, ebp
0x18001575d  cmovz   rax, r11
0x180015761  test    ebp, ebp
0x180015763  jz      short loc_1800157C4
0x180015765  mov     rax, [rax]
0x180015768  mov     rbx, [r8]
0x18001576b  mov     ecx, edx
0x18001576d  lea     rsi, [rax+rcx*8]
0x180015771  mov     rcx, [rsi]; this
0x180015774  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180015779  mov     rdi, [rbx]
0x18001577c  mov     r15, rax
0x18001577f  test    rdi, rdi
0x180015782  jz      short loc_1800157AA
0x180015784  or      eax, 0FFFFFFFFh
0x180015787  lock xadd [rdi+18h], eax
0x18001578c  sub     eax, 1
0x18001578f  jnz     short loc_1800157A6
0x180015791  nop
0x180015792  call    WINRT_IMPL_GetProcessHeap
0x180015797  mov     rcx, rax; hHeap
0x18001579a  mov     r8, rdi; lpMem
0x18001579d  xor     edx, edx; dwFlags
0x18001579f  call    WINRT_IMPL_HeapFree
0x1800157a4  jmp     short loc_1800157AA
0x1800157a6  test    eax, eax
0x1800157a8  js      short loc_1800157BD
0x1800157aa  mov     [rbx], r15
0x1800157ad  add     r14d, 0FFFFFFFFh
0x1800157b1  jz      short loc_1800157C4
0x1800157b3  add     rbx, 8
0x1800157b7  add     rsi, 8
0x1800157bb  jmp     short loc_180015771
0x1800157bd  call    cs:__imp_abort
0x1800157c4  mov     eax, ebp
0x1800157c6  add     rsp, 28h
0x1800157ca  pop     r15
0x1800157cc  pop     r14
0x1800157ce  pop     rdi
0x1800157cf  pop     rsi
0x1800157d0  pop     rbp
0x1800157d1  pop     rbx
0x1800157d2  retn
```
