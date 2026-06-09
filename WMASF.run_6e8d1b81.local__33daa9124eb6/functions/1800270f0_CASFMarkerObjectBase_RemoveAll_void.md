# CASFMarkerObjectBase::RemoveAll(void)

- ea: `0x1800270f0`
- end: `0x18002720a`
- name: `?RemoveAll@CASFMarkerObjectBase@@UEAAJXZ`
- size: `282`
- prototype: `__int64 __fastcall(CASFMarkerObjectBase *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x1800049b8`
- `0x180004a1c`
- `0x1800266c0`
- `0x1800270f0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFMarkerObjectBase::RemoveAll(struct IWMSCriticalSection **this)
{
  unsigned int v2; // ebx
  unsigned int v3; // ebp
  unsigned int i; // esi
  int (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rax
  __int64 v6; // rax
  _BYTE v8[8]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+28h] [rbp-40h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v8, this[4]);
  if ( this[5] )
  {
    CTSparseBlock<unsigned long,CASFMarkerObjectBase::INDEX_SPECIFIER,20,0>::FreeList(this + 10);
    *((_DWORD *)this + 52) = 0;
    v3 = *((_DWORD *)this + 108);
    for ( i = 0; i < v3; ++i )
    {
      v9 = 0;
      v5 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))CTDynArray<IASFMarker *,20>::operator[](this + 27, i);
      if ( (**v5)(v5, &IID_IASFMarkerPriv, &v9) >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 32LL))(v9);
        if ( v9 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          v9 = 0;
        }
      }
      v6 = CTDynArray<IASFMarker *,20>::operator[](this + 27, i);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::FreeList((__int64)(this + 27));
    *((_DWORD *)this + 108) = 0;
    v2 = 0;
  }
  else
  {
    v2 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v8);
  return v2;
}

```

## disassembly

```asm
0x1800270f0  push    rbx
0x1800270f2  push    rbp
0x1800270f3  push    rsi
0x1800270f4  push    rdi
0x1800270f5  sub     rsp, 48h
0x1800270f9  mov     rax, cs:__security_cookie
0x180027100  xor     rax, rsp
0x180027103  mov     [rsp+68h+var_38], rax
0x180027108  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x18002710c  mov     rdi, rcx
0x18002710f  lea     rcx, [rsp+68h+var_48]; this
0x180027114  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180027119  cmp     qword ptr [rdi+28h], 0
0x18002711e  jnz     short loc_18002712A
0x180027120  mov     ebx, 0C00D07F6h
0x180027125  jmp     loc_1800271E8
0x18002712a  lea     rcx, [rdi+50h]
0x18002712e  call    ?FreeList@?$CTSparseBlock@KUINDEX_SPECIFIER@CASFMarkerObjectBase@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,CASFMarkerObjectBase::INDEX_SPECIFIER,20,0>::FreeList(int)
0x180027133  mov     dword ptr [rdi+0D0h], 0
0x18002713d  lea     rbx, [rdi+0D8h]
0x180027144  mov     ebp, [rdi+1B0h]
0x18002714a  xor     esi, esi
0x18002714c  test    ebp, ebp
0x18002714e  jz      loc_1800271D4
0x180027154  mov     edx, esi
0x180027156  mov     [rsp+68h+var_40], 0
0x18002715f  mov     rcx, rbx
0x180027162  call    ??A?$CTDynArray@PEAUIASFMarker@@$0BE@@@QEBAPEAUIASFMarker@@K@Z; CTDynArray<IASFMarker *,20>::operator[](ulong)
0x180027167  mov     rcx, rax
0x18002716a  lea     r8, [rsp+68h+var_40]
0x18002716f  lea     rdx, IID_IASFMarkerPriv
0x180027176  mov     rax, [rax]
0x180027179  mov     rax, [rax]
0x18002717c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027181  test    eax, eax
0x180027183  js      short loc_1800271B5
0x180027185  mov     rcx, [rsp+68h+var_40]
0x18002718a  mov     rax, [rcx]
0x18002718d  mov     rax, [rax+20h]
0x180027191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027196  mov     rcx, [rsp+68h+var_40]
0x18002719b  test    rcx, rcx
0x18002719e  jz      short loc_1800271B5
0x1800271a0  mov     rax, [rcx]
0x1800271a3  mov     rax, [rax+10h]
0x1800271a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271ac  mov     [rsp+68h+var_40], 0
0x1800271b5  mov     edx, esi
0x1800271b7  mov     rcx, rbx
0x1800271ba  call    ??A?$CTDynArray@PEAUIASFMarker@@$0BE@@@QEBAPEAUIASFMarker@@K@Z; CTDynArray<IASFMarker *,20>::operator[](ulong)
0x1800271bf  mov     rcx, rax
0x1800271c2  mov     rax, [rax]
0x1800271c5  mov     rax, [rax+10h]
0x1800271c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271ce  inc     esi
0x1800271d0  cmp     esi, ebp
0x1800271d2  jb      short loc_180027154
0x1800271d4  mov     rcx, rbx
0x1800271d7  call    ?FreeList@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::FreeList(int)
0x1800271dc  mov     dword ptr [rbx+0D8h], 0
0x1800271e6  xor     ebx, ebx
0x1800271e8  lea     rcx, [rsp+68h+var_48]; this
0x1800271ed  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800271f2  mov     eax, ebx
0x1800271f4  mov     rcx, [rsp+68h+var_38]
0x1800271f9  xor     rcx, rsp; StackCookie
0x1800271fc  call    __security_check_cookie
0x180027201  add     rsp, 48h
0x180027205  pop     rdi
0x180027206  pop     rsi
0x180027207  pop     rbp
0x180027208  pop     rbx
0x180027209  retn
```
