# IndexedFiltering::IndexManager::NotifySourceOfChange(uint,USOID const &,_SQLCEPROPVAL *,unsigned __int64)

- ea: `0x180013c20`
- end: `0x180013c99`
- name: `?NotifySourceOfChange@IndexManager@IndexedFiltering@@MEAAJIAEBUUSOID@@PEAU_SQLCEPROPVAL@@_K@Z`
- size: `121`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexManager *__hidden this, unsigned int, const struct USOID *, struct _SQLCEPROPVAL *, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update`

## callees

- `0x180002da8`
- `0x1800086a0`
- `0x180013c20`
- `0x180022010`

## string_xrefs

- `0x180013c44`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`
- `0x180013c7b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indexmanager.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexManager::NotifySourceOfChange(
        IndexedFiltering::IndexManager *this,
        unsigned int a2,
        const struct USOID *a3,
        struct _SQLCEPROPVAL *a4,
        unsigned __int64 a5)
{
  __int64 v8; // rdi
  int v9; // eax
  unsigned int v10; // ebx

  v8 = a2;
  if ( a2 >= *((_DWORD *)this + 28) || !a4 )
    Log_AssertionEvent(
      this,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      897);
  v9 = (*(__int64 (__fastcall **)(_QWORD, const struct USOID *, struct _SQLCEPROPVAL *, unsigned __int64))(**((_QWORD **)this + v8 + 9) + 40LL))(
         *((_QWORD *)this + v8 + 9),
         a3,
         a4,
         a5);
  v10 = v9;
  if ( v9 < 0 )
    Log_HREvent(
      (unsigned int)v9,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indexmanager.cpp",
      903);
  return v10;
}

```

## disassembly

```asm
0x180013c20  push    rbx
0x180013c22  push    rbp
0x180013c23  push    rsi
0x180013c24  push    rdi
0x180013c25  sub     rsp, 38h
0x180013c29  mov     rbx, r9
0x180013c2c  mov     rbp, r8
0x180013c2f  mov     rsi, rcx
0x180013c32  mov     edi, edx
0x180013c34  cmp     edx, [rcx+70h]
0x180013c37  jnb     short loc_180013C3E
0x180013c39  test    rbx, rbx
0x180013c3c  jnz     short loc_180013C50
0x180013c3e  mov     r8d, 381h
0x180013c44  lea     rdx, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013c4b  call    Log_AssertionEvent
0x180013c50  mov     rcx, [rsi+rdi*8+48h]
0x180013c55  mov     r8, rbx
0x180013c58  mov     r9, [rsp+58h+arg_20]
0x180013c60  mov     rdx, rbp
0x180013c63  mov     rax, [rcx]
0x180013c66  mov     rax, [rax+28h]
0x180013c6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c6f  mov     ebx, eax
0x180013c71  test    eax, eax
0x180013c73  jns     short loc_180013C8E
0x180013c75  mov     r9d, 387h
0x180013c7b  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180013c82  mov     edx, 1
0x180013c87  mov     ecx, eax
0x180013c89  call    Log_HREvent
0x180013c8e  mov     eax, ebx
0x180013c90  add     rsp, 38h
0x180013c94  pop     rdi
0x180013c95  pop     rsi
0x180013c96  pop     rbp
0x180013c97  pop     rbx
0x180013c98  retn
```
