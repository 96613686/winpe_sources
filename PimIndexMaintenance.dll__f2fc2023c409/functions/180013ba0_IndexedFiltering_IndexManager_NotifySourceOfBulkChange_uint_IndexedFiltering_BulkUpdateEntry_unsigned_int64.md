# IndexedFiltering::IndexManager::NotifySourceOfBulkChange(uint,IndexedFiltering::BulkUpdateEntry *,unsigned __int64)

- ea: `0x180013ba0`
- end: `0x180013c1a`
- name: `?NotifySourceOfBulkChange@IndexManager@IndexedFiltering@@MEAAJIPEAUBulkUpdateEntry@2@_K@Z`
- size: `122`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexManager *__hidden this, unsigned int, struct IndexedFiltering::BulkUpdateEntry *, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x180013ba0`
- `0x180022010`

## string_xrefs

- `0x180013bc9`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180013bf8`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexManager::NotifySourceOfBulkChange(
        IndexedFiltering::IndexManager *this,
        unsigned int a2,
        struct IndexedFiltering::BulkUpdateEntry *a3,
        __int64 a4)
{
  __int64 v7; // rsi
  int v8; // eax
  unsigned int v9; // ebx

  v7 = a2;
  if ( a2 >= *((_DWORD *)this + 28) || !a3 || !a4 )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      952);
  v8 = (*(__int64 (__fastcall **)(_QWORD, struct IndexedFiltering::BulkUpdateEntry *, __int64))(**((_QWORD **)this
                                                                                                 + v7
                                                                                                 + 9)
                                                                                              + 56LL))(
         *((_QWORD *)this + v7 + 9),
         a3,
         a4);
  v9 = v8;
  if ( v8 >= 0 )
    return 0;
  Log_HREvent(
    (unsigned int)v8,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
    956);
  return v9;
}

```

## disassembly

```asm
0x180013ba0  push    rbx
0x180013ba2  push    rbp
0x180013ba3  push    rsi
0x180013ba4  push    rdi
0x180013ba5  sub     rsp, 38h
0x180013ba9  mov     rbx, r9
0x180013bac  mov     rdi, r8
0x180013baf  mov     rbp, rcx
0x180013bb2  mov     esi, edx
0x180013bb4  cmp     edx, [rcx+70h]
0x180013bb7  jnb     short loc_180013BC3
0x180013bb9  test    r8, r8
0x180013bbc  jz      short loc_180013BC3
0x180013bbe  test    rbx, rbx
0x180013bc1  jnz     short loc_180013BD5
0x180013bc3  mov     r8d, 3B8h
0x180013bc9  lea     rdx, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013bd0  call    Log_AssertionEvent
0x180013bd5  mov     rcx, [rbp+rsi*8+48h]
0x180013bda  mov     r8, rbx
0x180013bdd  mov     rdx, rdi
0x180013be0  mov     rax, [rcx]
0x180013be3  mov     rax, [rax+38h]
0x180013be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bec  mov     ebx, eax
0x180013bee  test    eax, eax
0x180013bf0  jns     short loc_180013C0F
0x180013bf2  mov     r9d, 3BCh
0x180013bf8  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013bff  mov     edx, 1
0x180013c04  mov     ecx, eax
0x180013c06  call    Log_HREvent
0x180013c0b  mov     eax, ebx
0x180013c0d  jmp     short loc_180013C11
0x180013c0f  xor     eax, eax
0x180013c11  add     rsp, 38h
0x180013c15  pop     rdi
0x180013c16  pop     rsi
0x180013c17  pop     rbp
0x180013c18  pop     rbx
0x180013c19  retn
```
