# CASFIndexObjectv2::RemoveAllIndexBlocks(void)

- ea: `0x1800057f0`
- end: `0x1800058f1`
- name: `?RemoveAllIndexBlocks@CASFIndexObjectv2@@UEAAJXZ`
- size: `257`
- prototype: `__int64 __fastcall(CASFIndexObjectv2 *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x1800043cc`
- `0x1800049b8`
- `0x1800057f0`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFIndexObjectv2::RemoveAllIndexBlocks(struct IWMSCriticalSection **this)
{
  unsigned int v2; // ebp
  unsigned int i; // esi
  __int64 v4; // r14
  _BYTE v6[8]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v7; // [rsp+28h] [rbp-30h] BYREF

  CAutoCritSec::CAutoCritSec((CAutoCritSec *)v6, this[4]);
  v2 = *((_DWORD *)this + 76);
  for ( i = 0; i < v2; ++i )
  {
    v7 = 0;
    v4 = CTDynArray<IASFIndexBlock *,20>::operator[](this + 11, i);
    if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v4)(v4, &IID_IASFIndexBlockPriv, &v7) >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 32LL))(v7);
      if ( v7 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        v7 = 0;
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::FreeList((__int64)(this + 11));
  *((_DWORD *)this + 76) = 0;
  *((_DWORD *)this + 113) = 0;
  CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v6);
  return 0;
}

```

## disassembly

```asm
0x1800057f0  mov     [rsp+arg_8], rbx
0x1800057f5  mov     [rsp+arg_10], rbp
0x1800057fa  push    rsi
0x1800057fb  push    rdi
0x1800057fc  push    r14
0x1800057fe  sub     rsp, 40h
0x180005802  mov     rax, cs:__security_cookie
0x180005809  xor     rax, rsp
0x18000580c  mov     [rsp+58h+var_28], rax
0x180005811  mov     rdx, [rcx+20h]; struct IWMSCriticalSection *
0x180005815  mov     rdi, rcx
0x180005818  lea     rcx, [rsp+58h+var_38]; this
0x18000581d  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180005822  mov     ebp, [rdi+130h]
0x180005828  xor     esi, esi
0x18000582a  test    ebp, ebp
0x18000582c  jz      short loc_1800058A8
0x18000582e  mov     edx, esi
0x180005830  mov     [rsp+58h+var_30], 0
0x180005839  lea     rcx, [rdi+58h]
0x18000583d  call    ??A?$CTDynArray@PEAUIASFIndexBlock@@$0BE@@@QEBAPEAUIASFIndexBlock@@K@Z; CTDynArray<IASFIndexBlock *,20>::operator[](ulong)
0x180005842  mov     r14, rax
0x180005845  lea     r8, [rsp+58h+var_30]
0x18000584a  lea     rdx, IID_IASFIndexBlockPriv
0x180005851  mov     rcx, [rax]
0x180005854  mov     rax, [rcx]
0x180005857  mov     rcx, r14
0x18000585a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000585f  test    eax, eax
0x180005861  js      short loc_180005893
0x180005863  mov     rcx, [rsp+58h+var_30]
0x180005868  mov     rdx, [rcx]
0x18000586b  mov     rax, [rdx+20h]
0x18000586f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005874  mov     rcx, [rsp+58h+var_30]
0x180005879  test    rcx, rcx
0x18000587c  jz      short loc_180005893
0x18000587e  mov     rax, [rcx]
0x180005881  mov     rax, [rax+10h]
0x180005885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000588a  mov     [rsp+58h+var_30], 0
0x180005893  mov     rax, [r14]
0x180005896  mov     rcx, r14
0x180005899  mov     rax, [rax+10h]
0x18000589d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058a2  inc     esi
0x1800058a4  cmp     esi, ebp
0x1800058a6  jb      short loc_18000582E
0x1800058a8  lea     rcx, [rdi+58h]
0x1800058ac  call    ?FreeList@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJH@Z; CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::FreeList(int)
0x1800058b1  mov     dword ptr [rdi+130h], 0
0x1800058bb  lea     rcx, [rsp+58h+var_38]; this
0x1800058c0  mov     dword ptr [rdi+1C4h], 0
0x1800058ca  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800058cf  xor     eax, eax
0x1800058d1  mov     rcx, [rsp+58h+var_28]
0x1800058d6  xor     rcx, rsp; StackCookie
0x1800058d9  call    __security_check_cookie
0x1800058de  mov     rbx, [rsp+58h+arg_8]
0x1800058e3  mov     rbp, [rsp+58h+arg_10]
0x1800058e8  add     rsp, 40h
0x1800058ec  pop     r14
0x1800058ee  pop     rdi
0x1800058ef  pop     rsi
0x1800058f0  retn
```
