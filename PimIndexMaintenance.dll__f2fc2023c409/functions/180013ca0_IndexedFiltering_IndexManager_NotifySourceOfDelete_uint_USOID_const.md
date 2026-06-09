# IndexedFiltering::IndexManager::NotifySourceOfDelete(uint,USOID const &)

- ea: `0x180013ca0`
- end: `0x180013d1f`
- name: `?NotifySourceOfDelete@IndexManager@IndexedFiltering@@MEAAJIAEBUUSOID@@@Z`
- size: `127`
- prototype: `int(IndexedFiltering::IndexManager *__hidden this, unsigned int, const struct USOID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x180013b80`
- `0x180013ca0`
- `0x180022010`

## string_xrefs

- `0x180013cce`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180013cfa`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexManager::NotifySourceOfDelete(
        IndexedFiltering::IndexManager *this,
        unsigned int a2,
        const struct USOID *a3)
{
  __int64 v4; // rdi
  int v6; // eax
  unsigned int v7; // ebx

  v4 = a2;
  if ( a2 >= *((_DWORD *)this + 28) || (unsigned int)IsEmptyUsOid(a3) )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      925);
  v6 = (*(__int64 (__fastcall **)(_QWORD, const struct USOID *))(**((_QWORD **)this + v4 + 9) + 48LL))(
         *((_QWORD *)this + v4 + 9),
         a3);
  v7 = v6;
  if ( v6 < 0 )
    Log_HREvent(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      928);
  return v7;
}

```

## disassembly

```asm
0x180013ca0  mov     [rsp+arg_0], rbx
0x180013ca5  mov     [rsp+arg_8], rsi
0x180013caa  push    rdi
0x180013cab  sub     rsp, 30h
0x180013caf  mov     rbx, r8
0x180013cb2  mov     edi, edx
0x180013cb4  mov     rsi, rcx
0x180013cb7  cmp     edx, [rcx+70h]
0x180013cba  jnb     short loc_180013CC8
0x180013cbc  mov     rcx, rbx; struct USOID *
0x180013cbf  call    ?IsEmptyUsOid@@YAHAEBUUSOID@@@Z; IsEmptyUsOid(USOID const &)
0x180013cc4  test    eax, eax
0x180013cc6  jz      short loc_180013CDA
0x180013cc8  mov     r8d, 39Dh
0x180013cce  lea     rdx, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013cd5  call    Log_AssertionEvent
0x180013cda  mov     rcx, [rsi+rdi*8+48h]
0x180013cdf  mov     rdx, rbx
0x180013ce2  mov     rax, [rcx]
0x180013ce5  mov     rax, [rax+30h]
0x180013ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cee  mov     ebx, eax
0x180013cf0  test    eax, eax
0x180013cf2  jns     short loc_180013D0D
0x180013cf4  mov     r9d, 3A0h
0x180013cfa  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013d01  mov     edx, 1
0x180013d06  mov     ecx, eax
0x180013d08  call    Log_HREvent
0x180013d0d  mov     rsi, [rsp+38h+arg_8]
0x180013d12  mov     eax, ebx
0x180013d14  mov     rbx, [rsp+38h+arg_0]
0x180013d19  add     rsp, 30h
0x180013d1d  pop     rdi
0x180013d1e  retn
```
