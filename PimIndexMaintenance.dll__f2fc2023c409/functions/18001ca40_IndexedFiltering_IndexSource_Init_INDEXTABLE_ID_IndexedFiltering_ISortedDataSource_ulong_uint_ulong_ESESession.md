# IndexedFiltering::IndexSource::Init(_INDEXTABLE_ID,IndexedFiltering::ISortedDataSource *,ulong *,uint,ulong,ESESession *)

- ea: `0x18001ca40`
- end: `0x18001cb28`
- name: `?Init@IndexSource@IndexedFiltering@@MEAAJW4_INDEXTABLE_ID@@PEAUISortedDataSource@2@PEAKIKPEAVESESession@@@Z`
- size: `232`
- prototype: `int __high(enum _INDEXTABLE_ID, struct IndexedFiltering::ISortedDataSource *, unsigned int *, unsigned int, unsigned int, struct ESESession *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000502c`
- `0x1800086a0`
- `0x18001ca40`
- `0x18001cb30`
- `0x1800211f2`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cacb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cacb`

## string_xrefs

- `0x18001ca6b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexsource.cpp`
- `0x18001ca8c`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexsource.cpp`
- `0x18001cab2`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexsource.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexSource::Init(
        __int64 a1,
        int a2,
        struct IUnknown *a3,
        const void *a4,
        unsigned int a5,
        int a6,
        __int64 a7)
{
  HLOCAL v11; // rax
  __int64 v12; // r8

  if ( !a5 )
    Log_AssertionEvent(
      a1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexsource.cpp",
      744);
  if ( (a6 & 0xFFFFFFC0) != 0 )
    Log_AssertionEvent(
      a1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexsource.cpp",
      745);
  *(_QWORD *)(a1 + 96) = a7;
  *(_DWORD *)(a1 + 92) = a2;
  if ( a2 == -1 )
    Log_AssertionEvent(
      a1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexsource.cpp",
      750);
  *(_DWORD *)(a1 + 64) = a5;
  v11 = LocalAlloc(0, 4LL * a5);
  *(_QWORD *)(a1 + 56) = v11;
  if ( v11 )
  {
    memcpy_0(v11, a4, 4LL * *(unsigned int *)(a1 + 64));
    *(_DWORD *)(a1 + 48) = a6;
    if ( *(struct IUnknown **)(a1 + 40) != a3 )
      ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 40), a3);
    return 0;
  }
  else
  {
    Log_HREvent_7(2147942414LL, 0, v12, 755);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001ca40  push    rbx
0x18001ca42  push    rbp
0x18001ca43  push    rsi
0x18001ca44  push    rdi
0x18001ca45  push    r14
0x18001ca47  push    r15
0x18001ca49  sub     rsp, 38h
0x18001ca4d  mov     r14d, [rsp+68h+arg_20]
0x18001ca55  mov     r15, r9
0x18001ca58  mov     rsi, r8
0x18001ca5b  mov     edi, edx
0x18001ca5d  mov     rbx, rcx
0x18001ca60  test    r14d, r14d
0x18001ca63  jnz     short loc_18001CA77
0x18001ca65  mov     r8d, 2E8h
0x18001ca6b  lea     rdx, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001ca72  call    Log_AssertionEvent
0x18001ca77  mov     ebp, [rsp+68h+arg_28]
0x18001ca7e  test    ebp, 0FFFFFFC0h
0x18001ca84  jz      short loc_18001CA98
0x18001ca86  mov     r8d, 2E9h
0x18001ca8c  lea     rdx, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001ca93  call    Log_AssertionEvent
0x18001ca98  mov     rax, [rsp+68h+arg_30]
0x18001caa0  mov     [rbx+60h], rax
0x18001caa4  mov     [rbx+5Ch], edi
0x18001caa7  cmp     edi, 0FFFFFFFFh
0x18001caaa  jnz     short loc_18001CABE
0x18001caac  mov     r8d, 2EEh
0x18001cab2  lea     rdx, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001cab9  call    Log_AssertionEvent
0x18001cabe  mov     rdx, r14
0x18001cac1  mov     [rbx+40h], r14d
0x18001cac5  shl     rdx, 2; uBytes
0x18001cac9  xor     ecx, ecx; uFlags
0x18001cacb  call    cs:__imp_LocalAlloc
0x18001cad1  mov     [rbx+38h], rax
0x18001cad5  test    rax, rax
0x18001cad8  jnz     short loc_18001CAF2
0x18001cada  mov     ebx, 8007000Eh
0x18001cadf  xor     edx, edx
0x18001cae1  mov     ecx, ebx
0x18001cae3  mov     r9d, 2F3h
0x18001cae9  call    Log_HREvent_7
0x18001caee  mov     eax, ebx
0x18001caf0  jmp     short loc_18001CB1B
0x18001caf2  mov     r8d, [rbx+40h]
0x18001caf6  mov     rdx, r15; Src
0x18001caf9  shl     r8, 2; Size
0x18001cafd  mov     rcx, rax; void *
0x18001cb00  call    memcpy_0
0x18001cb05  lea     rcx, [rbx+28h]; struct IUnknown **
0x18001cb09  mov     [rbx+30h], ebp
0x18001cb0c  cmp     [rcx], rsi
0x18001cb0f  jz      short loc_18001CB19
0x18001cb11  mov     rdx, rsi; struct IUnknown *
0x18001cb14  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18001cb19  xor     eax, eax
0x18001cb1b  add     rsp, 38h
0x18001cb1f  pop     r15
0x18001cb21  pop     r14
0x18001cb23  pop     rdi
0x18001cb24  pop     rsi
0x18001cb25  pop     rbp
0x18001cb26  pop     rbx
0x18001cb27  retn
```
