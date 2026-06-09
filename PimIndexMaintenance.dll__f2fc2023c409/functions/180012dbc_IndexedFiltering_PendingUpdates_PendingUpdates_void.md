# IndexedFiltering::PendingUpdates::~PendingUpdates(void)

- ea: `0x180012dbc`
- end: `0x180012e49`
- name: `??1PendingUpdates@IndexedFiltering@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(IndexedFiltering::PendingUpdates *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180012d0c`
- `0x180014810`

## callees

- `0x1800086a0`
- `0x18000c51c`
- `0x180012dbc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012df4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012df4`

## string_xrefs

- `0x180012e05`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\IndexManager.h`

## pseudocode

```c
void __fastcall IndexedFiltering::PendingUpdates::~PendingUpdates(IndexedFiltering::PendingUpdates *this)
{
  unsigned __int64 v1; // rsi
  unsigned __int64 v3; // rdi
  __int64 v4; // rbp
  __int64 v5; // rcx
  __int64 v6; // rax

  v1 = 0;
  v3 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 1) - *(_QWORD *)this) >> 3);
  if ( v3 )
  {
    do
    {
      v4 = 5 * v1;
      if ( LocalFree(*(HLOCAL *)(*(_QWORD *)this + 40 * v1 + 16)) )
        Log_AssertionEvent(
          v5,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\IndexManager.h",
          44);
      ++v1;
      *(_QWORD *)(*(_QWORD *)this + 8 * v4 + 16) = 0;
      v6 = *(_QWORD *)this;
      *(_QWORD *)(v6 + 8 * v4) = 0;
      *(_DWORD *)(v6 + 8 * v4 + 8) = 0;
    }
    while ( v1 < v3 );
  }
  *((_QWORD *)this + 1) = *(_QWORD *)this;
  utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(this);
}

```

## disassembly

```asm
0x180012dbc  push    rbx
0x180012dbe  push    rbp
0x180012dbf  push    rsi
0x180012dc0  push    rdi
0x180012dc1  sub     rsp, 28h
0x180012dc5  mov     rdi, [rcx+8]
0x180012dc9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180012dd3  sub     rdi, [rcx]
0x180012dd6  xor     esi, esi
0x180012dd8  sar     rdi, 3
0x180012ddc  mov     rbx, rcx
0x180012ddf  imul    rdi, rax
0x180012de3  test    rdi, rdi
0x180012de6  jz      short loc_180012E32
0x180012de8  mov     rcx, [rbx]
0x180012deb  lea     rbp, [rsi+rsi*4]
0x180012def  mov     rcx, [rcx+rbp*8+10h]; hMem
0x180012df4  call    cs:__imp_LocalFree
0x180012dfa  test    rax, rax
0x180012dfd  jz      short loc_180012E11
0x180012dff  mov     r8d, 2Ch ; ','
0x180012e05  lea     rdx, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180012e0c  call    Log_AssertionEvent
0x180012e11  mov     rax, [rbx]
0x180012e14  xor     ecx, ecx
0x180012e16  inc     rsi
0x180012e19  mov     qword ptr [rax+rbp*8+10h], 0
0x180012e22  mov     rax, [rbx]
0x180012e25  mov     [rax+rbp*8], rcx
0x180012e29  mov     [rax+rbp*8+8], ecx
0x180012e2d  cmp     rsi, rdi
0x180012e30  jb      short loc_180012DE8
0x180012e32  mov     rax, [rbx]
0x180012e35  mov     rcx, rbx
0x180012e38  mov     [rbx+8], rax
0x180012e3c  add     rsp, 28h
0x180012e40  pop     rdi
0x180012e41  pop     rsi
0x180012e42  pop     rbp
0x180012e43  pop     rbx
0x180012e44  jmp     ?_Uninit@?$vector@URunOnToken@IndexedFiltering@@V?$allocator@URunOnToken@IndexedFiltering@@@utl@@@utl@@AEAAXXZ; utl::vector<IndexedFiltering::RunOnToken,utl::allocator<IndexedFiltering::RunOnToken>>::_Uninit(void)
```
