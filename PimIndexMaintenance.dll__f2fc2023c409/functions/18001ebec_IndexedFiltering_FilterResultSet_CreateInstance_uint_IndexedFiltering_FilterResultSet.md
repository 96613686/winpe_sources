# IndexedFiltering::FilterResultSet::CreateInstance(uint,IndexedFiltering::FilterResultSet * *)

- ea: `0x18001ebec`
- end: `0x18001ed57`
- name: `?CreateInstance@FilterResultSet@IndexedFiltering@@SAJIPEAPEAV12@@Z`
- size: `363`
- prototype: `__int64 __fastcall(unsigned int, struct IndexedFiltering::FilterResultSet **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800152b0`

## callees

- `0x1800012fc`
- `0x180002da8`
- `0x18001ebec`
- `0x18001f388`
- `0x18001f3c8`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ec9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ecde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ec9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ecde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ecec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ecec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ecb2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001ecb2`

## string_xrefs

- `0x18001ec0b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\filterresultset.cpp`
- `0x18001ecc2`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\filterresultset.cpp`
- `0x18001ecfc`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\filterresultset.cpp`
- `0x18001ed30`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\filterresultset.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::FilterResultSet::CreateInstance(
        unsigned int a1,
        struct IndexedFiltering::FilterResultSet **a2)
{
  int v4; // ebx
  _QWORD *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rdi
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  LPVOID v11; // rax
  __int64 v12; // rdx
  HANDLE v13; // rax

  if ( a2 )
  {
    v5 = operator new(0x28u);
    v8 = v5;
    if ( v5 )
    {
      *v5 = &IndexedFiltering::IFilterResultSet::`vftable';
      v5[1] = &_CUnknownBase::`vftable';
      *((_DWORD *)v5 + 4) = 1;
      *v5 = &IndexedFiltering::FilterResultSet::`vftable'{for `IndexedFiltering::IFilterResultSet'};
      v5[1] = &IndexedFiltering::FilterResultSet::`vftable'{for `CUnknownPrivate'};
      v5[3] = 0;
      v5[4] = 0;
      if ( *((_DWORD *)v5 + 4) != 1 )
        Log_AssertionEvent_5(v7, v6, 155);
      *((_DWORD *)v8 + 8) = a1;
      v9 = (a1 >> 5) + 1;
      *((_DWORD *)v8 + 9) = v9;
      ProcessHeap = GetProcessHeap();
      v11 = HeapAlloc(ProcessHeap, 8u, 4LL * v9);
      if ( v11 )
      {
        v4 = 0;
        v8[3] = v11;
      }
      else
      {
        v4 = -2147024882;
        Log_HREvent_9(
          2147942414LL,
          v12,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\filterresultset.cpp",
          635);
      }
      v13 = GetProcessHeap();
      HeapFree(v13, 0, 0);
      if ( v4 >= 0 )
      {
        *a2 = (struct IndexedFiltering::FilterResultSet *)v8;
      }
      else
      {
        Log_HREvent(
          (unsigned int)v4,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\filterresultset.cpp",
          158);
        (*(void (__fastcall **)(_QWORD *, __int64))(v8[1] + 24LL))(v8 + 1, 1);
      }
    }
    else
    {
      v4 = -2147024882;
      Log_HREvent_9(
        2147942414LL,
        v6,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\filterresultset.cpp",
        154);
    }
  }
  else
  {
    v4 = -2147024809;
    Log_HREvent(
      2147942487LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\filterresultset.cpp",
      151);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001ebec  mov     [rsp+arg_0], rbx
0x18001ebf1  mov     [rsp+arg_8], rdi
0x18001ebf6  push    r14
0x18001ebf8  sub     rsp, 30h
0x18001ebfc  mov     r14, rdx
0x18001ebff  mov     ebx, ecx
0x18001ec01  test    rdx, rdx
0x18001ec04  jnz     short loc_18001EC28
0x18001ec06  mov     ebx, 80070057h
0x18001ec0b  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001ec12  mov     ecx, ebx
0x18001ec14  lea     edx, [r14+1]
0x18001ec18  mov     r9d, 97h
0x18001ec1e  call    Log_HREvent
0x18001ec23  jmp     loc_18001ED44
0x18001ec28  mov     ecx, 28h ; '('; Size
0x18001ec2d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ec32  mov     rdi, rax
0x18001ec35  test    rax, rax
0x18001ec38  jz      loc_18001ED2B
0x18001ec3e  lea     rax, ??_7IFilterResultSet@IndexedFiltering@@6B@; const IndexedFiltering::IFilterResultSet::`vftable'
0x18001ec45  mov     [rdi], rax
0x18001ec48  lea     rax, ??_7_CUnknownBase@@6B@; const _CUnknownBase::`vftable'
0x18001ec4f  mov     [rdi+8], rax
0x18001ec53  lea     rax, ??_7FilterResultSet@IndexedFiltering@@6BIFilterResultSet@1@@; const IndexedFiltering::FilterResultSet::`vftable'{for `IndexedFiltering::IFilterResultSet'}
0x18001ec5a  mov     dword ptr [rdi+10h], 1
0x18001ec61  mov     [rdi], rax
0x18001ec64  lea     rax, ??_7FilterResultSet@IndexedFiltering@@6BCUnknownPrivate@@@; const IndexedFiltering::FilterResultSet::`vftable'{for `CUnknownPrivate'}
0x18001ec6b  mov     [rdi+8], rax
0x18001ec6f  mov     qword ptr [rdi+18h], 0
0x18001ec77  mov     qword ptr [rdi+20h], 0
0x18001ec7f  mov     eax, [rdi+10h]
0x18001ec82  cmp     eax, 1
0x18001ec85  jz      short loc_18001EC92
0x18001ec87  mov     r8d, 9Bh
0x18001ec8d  call    Log_AssertionEvent_5
0x18001ec92  mov     [rdi+20h], ebx
0x18001ec95  shr     ebx, 5
0x18001ec98  inc     ebx
0x18001ec9a  mov     [rdi+24h], ebx
0x18001ec9d  call    cs:__imp_GetProcessHeap
0x18001eca3  mov     r8d, ebx
0x18001eca6  mov     edx, 8; dwFlags
0x18001ecab  shl     r8, 2; dwBytes
0x18001ecaf  mov     rcx, rax; hHeap
0x18001ecb2  call    cs:__imp_HeapAlloc
0x18001ecb8  test    rax, rax
0x18001ecbb  jnz     short loc_18001ECD8
0x18001ecbd  mov     ecx, 8007000Eh
0x18001ecc2  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001ecc9  mov     r9d, 27Bh
0x18001eccf  mov     ebx, ecx
0x18001ecd1  call    Log_HREvent_9
0x18001ecd6  jmp     short loc_18001ECDE
0x18001ecd8  xor     ebx, ebx
0x18001ecda  mov     [rdi+18h], rax
0x18001ecde  call    cs:__imp_GetProcessHeap
0x18001ece4  xor     r8d, r8d; lpMem
0x18001ece7  xor     edx, edx; dwFlags
0x18001ece9  mov     rcx, rax; hHeap
0x18001ecec  call    cs:__imp_HeapFree
0x18001ecf2  test    ebx, ebx
0x18001ecf4  jns     short loc_18001ED26
0x18001ecf6  mov     r9d, 9Eh
0x18001ecfc  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001ed03  mov     edx, 1
0x18001ed08  mov     ecx, ebx
0x18001ed0a  call    Log_HREvent
0x18001ed0f  lea     rcx, [rdi+8]
0x18001ed13  mov     edx, 1
0x18001ed18  mov     rax, [rcx]
0x18001ed1b  mov     rax, [rax+18h]
0x18001ed1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed24  jmp     short loc_18001ED44
0x18001ed26  mov     [r14], rdi
0x18001ed29  jmp     short loc_18001ED44
0x18001ed2b  mov     ecx, 8007000Eh
0x18001ed30  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001ed37  mov     r9d, 9Ah
0x18001ed3d  mov     ebx, ecx
0x18001ed3f  call    Log_HREvent_9
0x18001ed44  mov     rdi, [rsp+38h+arg_8]
0x18001ed49  mov     eax, ebx
0x18001ed4b  mov     rbx, [rsp+38h+arg_0]
0x18001ed50  add     rsp, 30h
0x18001ed54  pop     r14
0x18001ed56  retn
```
