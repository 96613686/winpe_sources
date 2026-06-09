# PimIMService::GetIndexManager(int,int,IndexedFiltering::IIndexManager * *)

- ea: `0x180006f48`
- end: `0x180006ffd`
- name: `?GetIndexManager@PimIMService@@AEAAJHHPEAPEAUIIndexManager@IndexedFiltering@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(struct IndexedFiltering::IIndexManager **this, __int64, int, struct IndexedFiltering::IIndexManager **)`
- caller_count: `7`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000568c`
- `0x180006070`
- `0x180007630`
- `0x180008060`
- `0x18000936c`
- `0x18000b674`
- `0x18000bb20`

## callees

- `0x180002da8`
- `0x18000428c`
- `0x180006f48`
- `0x1800086a0`
- `0x180022010`

## string_xrefs

- `0x180006f87`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x180006fae`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::GetIndexManager(
        struct IndexedFiltering::IIndexManager **this,
        __int64 a2,
        int a3,
        struct IndexedFiltering::IIndexManager **a4)
{
  int v6; // eax
  unsigned int v7; // edi
  struct IndexedFiltering::IIndexManager *v9; // rbx
  _QWORD v10[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( !a3
    || this[58]
    || (v6 = (*((__int64 (__fastcall **)(struct IndexedFiltering::IIndexManager **))*this + 14))(this), v7 = v6, v6 >= 0) )
  {
    if ( !this[58] )
      Log_AssertionEvent(
        this,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        820);
    v9 = this[58];
    if ( v9 )
      (*(void (__fastcall **)(struct IndexedFiltering::IIndexManager *))(*(_QWORD *)v9 + 8LL))(v9);
    v10[0] = 0;
    *a4 = v9;
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v10);
    return 0;
  }
  else
  {
    Log_HREvent(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      815);
    return v7;
  }
}

```

## disassembly

```asm
0x180006f48  mov     [rsp+arg_0], rbx
0x180006f4d  mov     [rsp+arg_8], rsi
0x180006f52  push    rdi
0x180006f53  sub     rsp, 40h
0x180006f57  mov     rsi, r9
0x180006f5a  mov     rbx, rcx
0x180006f5d  test    r8d, r8d
0x180006f60  jz      short loc_180006F9E
0x180006f62  lea     r8, [rcx+1D0h]
0x180006f69  cmp     qword ptr [r8], 0
0x180006f6d  jnz     short loc_180006F9E
0x180006f6f  mov     rax, [rcx]
0x180006f72  mov     rax, [rax+70h]
0x180006f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f7b  mov     edi, eax
0x180006f7d  test    eax, eax
0x180006f7f  jns     short loc_180006F9E
0x180006f81  mov     r9d, 32Fh
0x180006f87  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180006f8e  mov     edx, 1
0x180006f93  mov     ecx, eax
0x180006f95  call    Log_HREvent
0x180006f9a  mov     eax, edi
0x180006f9c  jmp     short loc_180006FED
0x180006f9e  cmp     qword ptr [rbx+1D0h], 0
0x180006fa6  jnz     short loc_180006FBA
0x180006fa8  mov     r8d, 334h
0x180006fae  lea     rdx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180006fb5  call    Log_AssertionEvent
0x180006fba  mov     rbx, [rbx+1D0h]
0x180006fc1  test    rbx, rbx
0x180006fc4  jz      short loc_180006FD5
0x180006fc6  mov     rax, [rbx]
0x180006fc9  mov     rcx, rbx
0x180006fcc  mov     rax, [rax+8]
0x180006fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fd5  lea     rcx, [rsp+48h+var_18]
0x180006fda  mov     [rsp+48h+var_18], 0
0x180006fe3  mov     [rsi], rbx
0x180006fe6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006feb  xor     eax, eax
0x180006fed  mov     rbx, [rsp+48h+arg_0]
0x180006ff2  mov     rsi, [rsp+48h+arg_8]
0x180006ff7  add     rsp, 40h
0x180006ffb  pop     rdi
0x180006ffc  retn
```
