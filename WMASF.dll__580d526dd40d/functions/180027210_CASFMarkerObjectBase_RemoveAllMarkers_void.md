# CASFMarkerObjectBase::RemoveAllMarkers(void)

- ea: `0x180027210`
- end: `0x180027324`
- name: `?RemoveAllMarkers@CASFMarkerObjectBase@@UEAAJXZ`
- size: `276`
- prototype: `__int64 __fastcall(CASFMarkerObjectBase *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x1800049b8`
- `0x1800266c0`
- `0x180027210`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFMarkerObjectBase::RemoveAllMarkers(struct IWMSCriticalSection **this)
{
  unsigned int v2; // ebx
  unsigned int v3; // esi
  unsigned int v4; // edi
  char *i; // rbx
  int (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rax
  __int64 v7; // rax
  _BYTE v9[8]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+28h] [rbp-20h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v9, this[4]);
  if ( this[5] )
  {
    v3 = *((_DWORD *)this + 108);
    v4 = 0;
    for ( i = (char *)(this + 27); v4 < v3; ++v4 )
    {
      v10 = 0;
      v6 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))CTDynArray<IASFMarker *,20>::operator[](i, v4);
      if ( (**v6)(v6, &IID_IASFMarkerPriv, &v10) >= 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10);
        if ( v10 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          v10 = 0;
        }
      }
      v7 = CTDynArray<IASFMarker *,20>::operator[](i, v4);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::FreeList((__int64)i);
    *((_DWORD *)i + 54) = 0;
    v2 = 0;
  }
  else
  {
    v2 = -1072887818;
  }
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v9);
  return v2;
}

```

## disassembly

```asm
0x180027210  mov     [rsp+arg_8], rbx
0x180027215  mov     [rsp+arg_10], rsi
0x18002721a  push    rdi
0x18002721b  sub     rsp, 40h
0x18002721f  mov     rax, cs:__security_cookie
0x180027226  xor     rax, rsp
0x180027229  mov     [rsp+48h+var_18], rax
0x18002722e  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180027232  mov     rbx, rcx
0x180027235  lea     rcx, [rsp+48h+var_28]; this
0x18002723a  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18002723f  cmp     qword ptr [rbx+28h], 0
0x180027244  jnz     short loc_180027250
0x180027246  mov     ebx, 0C00D07F6h
0x18002724b  jmp     loc_1800272FB
0x180027250  mov     esi, [rbx+1B0h]
0x180027256  xor     edi, edi
0x180027258  add     rbx, 0D8h
0x18002725f  test    esi, esi
0x180027261  jz      loc_1800272E7
0x180027267  mov     edx, edi
0x180027269  mov     [rsp+48h+var_20], 0
0x180027272  mov     rcx, rbx
0x180027275  call    ??A?$CTDynArray@PEAUIASFMarker@@$0BE@@@QEBAPEAUIASFMarker@@K@Z; CTDynArray<IASFMarker *,20>::operator[](ulong)
0x18002727a  mov     rcx, rax
0x18002727d  lea     r8, [rsp+48h+var_20]
0x180027282  lea     rdx, IID_IASFMarkerPriv
0x180027289  mov     rax, [rax]
0x18002728c  mov     rax, [rax]
0x18002728f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027294  test    eax, eax
0x180027296  js      short loc_1800272C8
0x180027298  mov     rcx, [rsp+48h+var_20]
0x18002729d  mov     rax, [rcx]
0x1800272a0  mov     rax, [rax+20h]
0x1800272a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272a9  mov     rcx, [rsp+48h+var_20]
0x1800272ae  test    rcx, rcx
0x1800272b1  jz      short loc_1800272C8
0x1800272b3  mov     rax, [rcx]
0x1800272b6  mov     rax, [rax+10h]
0x1800272ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272bf  mov     [rsp+48h+var_20], 0
0x1800272c8  mov     edx, edi
0x1800272ca  mov     rcx, rbx
0x1800272cd  call    ??A?$CTDynArray@PEAUIASFMarker@@$0BE@@@QEBAPEAUIASFMarker@@K@Z; CTDynArray<IASFMarker *,20>::operator[](ulong)
0x1800272d2  mov     rcx, rax
0x1800272d5  mov     rax, [rax]
0x1800272d8  mov     rax, [rax+10h]
0x1800272dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272e1  inc     edi
0x1800272e3  cmp     edi, esi
0x1800272e5  jb      short loc_180027267
0x1800272e7  mov     rcx, rbx
0x1800272ea  call    ?FreeList@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::FreeList(int)
0x1800272ef  mov     dword ptr [rbx+0D8h], 0
0x1800272f9  xor     ebx, ebx
0x1800272fb  lea     rcx, [rsp+48h+var_28]; this
0x180027300  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180027305  mov     eax, ebx
0x180027307  mov     rcx, [rsp+48h+var_18]
0x18002730c  xor     rcx, rsp; StackCookie
0x18002730f  call    __security_check_cookie
0x180027314  mov     rbx, [rsp+48h+arg_8]
0x180027319  mov     rsi, [rsp+48h+arg_10]
0x18002731e  add     rsp, 40h
0x180027322  pop     rdi
0x180027323  retn
```
