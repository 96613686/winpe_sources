# IndexedFiltering::IndexManager::AutoDataSourceTransaction::TakeLock(void)

- ea: `0x180013fac`
- end: `0x180014017`
- name: `?TakeLock@AutoDataSourceTransaction@IndexManager@IndexedFiltering@@QEAAJXZ`
- size: `107`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexManager::AutoDataSourceTransaction *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180014020`
- `0x1800144c0`
- `0x1800148a8`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x180013fac`
- `0x180022010`

## string_xrefs

- `0x180013fc5`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\IndexManager.h`
- `0x180013fec`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\lib\IndexManager.h`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexManager::AutoDataSourceTransaction::TakeLock(
        IndexedFiltering::IndexManager::AutoDataSourceTransaction *this)
{
  int v2; // eax
  unsigned int v3; // edi

  if ( *((_DWORD *)this + 5) )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\IndexManager.h",
      256);
  v2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 48LL))(*(_QWORD *)this);
  v3 = v2;
  if ( v2 >= 0 )
  {
    *((_DWORD *)this + 5) = 1;
    return 0;
  }
  else
  {
    Log_HREvent(
      (unsigned int)v2,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\lib\\IndexManager.h",
      257);
    return v3;
  }
}

```

## disassembly

```asm
0x180013fac  mov     [rsp+arg_0], rbx
0x180013fb1  push    rdi
0x180013fb2  sub     rsp, 30h
0x180013fb6  cmp     dword ptr [rcx+14h], 0
0x180013fba  mov     rbx, rcx
0x180013fbd  jz      short loc_180013FD1
0x180013fbf  mov     r8d, 100h
0x180013fc5  lea     rdx, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013fcc  call    Log_AssertionEvent
0x180013fd1  mov     rcx, [rbx]
0x180013fd4  mov     rax, [rcx]
0x180013fd7  mov     rax, [rax+30h]
0x180013fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fe0  mov     edi, eax
0x180013fe2  test    eax, eax
0x180013fe4  jns     short loc_180014003
0x180013fe6  mov     r9d, 101h
0x180013fec  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013ff3  mov     edx, 1
0x180013ff8  mov     ecx, eax
0x180013ffa  call    Log_HREvent
0x180013fff  mov     eax, edi
0x180014001  jmp     short loc_18001400C
0x180014003  mov     dword ptr [rbx+14h], 1
0x18001400a  xor     eax, eax
0x18001400c  mov     rbx, [rsp+38h+arg_0]
0x180014011  add     rsp, 30h
0x180014015  pop     rdi
0x180014016  retn
```
