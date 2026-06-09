# CASFLibrary::NotifyReadDataUnit(uchar *,ulong,ushort,_ASF_DATA_DESCRIPTOR *)

- ea: `0x180008e60`
- end: `0x180008f63`
- name: `?NotifyReadDataUnit@CASFLibrary@@UEAAJPEAEKGPEAU_ASF_DATA_DESCRIPTOR@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(CASFLibrary *__hidden this, unsigned __int8 *, unsigned int, unsigned __int16, struct _ASF_DATA_DESCRIPTOR *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180007910`
- `0x180008e60`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFLibrary::NotifyReadDataUnit(
        CASFLibrary *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int16 a4,
        struct _ASF_DATA_DESCRIPTOR *a5)
{
  __int64 result; // rax
  unsigned int v10; // edi
  unsigned int i; // ebx
  __int64 v12; // rax
  _BYTE v13[8]; // [rsp+30h] [rbp-58h] BYREF
  struct IWMSCriticalSection *v14; // [rsp+38h] [rbp-50h] BYREF

  v14 = 0;
  result = (*(__int64 (__fastcall **)(char *, struct IWMSCriticalSection **))(*((_QWORD *)this - 1) + 24LL))(
             (char *)this - 8,
             &v14);
  if ( (int)result >= 0 )
  {
    CAutoCritSec::CAutoCritSec((CAutoCritSec *)v13, v14);
    if ( v14 )
    {
      (*(void (__fastcall **)(struct IWMSCriticalSection *))(*(_QWORD *)v14 + 16LL))(v14);
      v14 = 0;
    }
    v10 = *((_DWORD *)this + 128);
    for ( i = 0; i < v10; ++i )
    {
      if ( CTDynArray<IASFReadWriteTracker *,20>::operator[]((char *)this + 296, i) )
      {
        v12 = CTDynArray<IASFReadWriteTracker *,20>::operator[]((char *)this + 296, i);
        (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, _QWORD, struct _ASF_DATA_DESCRIPTOR *))(*(_QWORD *)v12 + 88LL))(
          v12,
          a2,
          a3,
          a4,
          a5);
      }
    }
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v13);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008e60  push    rbx
0x180008e62  push    rbp
0x180008e63  push    rsi
0x180008e64  push    rdi
0x180008e65  push    r12
0x180008e67  push    r14
0x180008e69  push    r15
0x180008e6b  sub     rsp, 50h
0x180008e6f  mov     rax, cs:__security_cookie
0x180008e76  xor     rax, rsp
0x180008e79  mov     [rsp+88h+var_48], rax
0x180008e7e  mov     r12, [rsp+88h+arg_20]
0x180008e86  mov     rsi, rcx
0x180008e89  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180008e8d  mov     [rsp+88h+var_50], 0
0x180008e96  mov     rbp, rdx
0x180008e99  movzx   r15d, r9w
0x180008e9d  lea     rdx, [rsp+88h+var_50]
0x180008ea2  mov     r14d, r8d
0x180008ea5  mov     rax, [rcx]
0x180008ea8  mov     rax, [rax+18h]
0x180008eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eb1  test    eax, eax
0x180008eb3  js      loc_180008F47
0x180008eb9  mov     rdx, [rsp+88h+var_50]; struct IWMSCriticalSection *
0x180008ebe  lea     rcx, [rsp+88h+var_58]; this
0x180008ec3  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180008ec8  mov     rcx, [rsp+88h+var_50]
0x180008ecd  test    rcx, rcx
0x180008ed0  jz      short loc_180008EE7
0x180008ed2  mov     rax, [rcx]
0x180008ed5  mov     rax, [rax+10h]
0x180008ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ede  mov     [rsp+88h+var_50], 0
0x180008ee7  mov     edi, [rsi+200h]
0x180008eed  xor     ebx, ebx
0x180008eef  test    edi, edi
0x180008ef1  jz      short loc_180008F3B
0x180008ef3  mov     edx, ebx
0x180008ef5  lea     rcx, [rsi+128h]
0x180008efc  call    ??A?$CTDynArray@PEAUIASFReadWriteTracker@@$0BE@@@QEBAPEAUIASFReadWriteTracker@@K@Z; CTDynArray<IASFReadWriteTracker *,20>::operator[](ulong)
0x180008f01  test    rax, rax
0x180008f04  jz      short loc_180008F35
0x180008f06  mov     edx, ebx
0x180008f08  lea     rcx, [rsi+128h]
0x180008f0f  call    ??A?$CTDynArray@PEAUIASFReadWriteTracker@@$0BE@@@QEBAPEAUIASFReadWriteTracker@@K@Z; CTDynArray<IASFReadWriteTracker *,20>::operator[](ulong)
0x180008f14  mov     r10, rax
0x180008f17  mov     [rsp+88h+var_68], r12
0x180008f1c  movzx   r9d, r15w
0x180008f20  mov     r8d, r14d
0x180008f23  mov     rdx, rbp
0x180008f26  mov     rcx, [rax]
0x180008f29  mov     rax, [rcx+58h]
0x180008f2d  mov     rcx, r10
0x180008f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f35  inc     ebx
0x180008f37  cmp     ebx, edi
0x180008f39  jb      short loc_180008EF3
0x180008f3b  lea     rcx, [rsp+88h+var_58]; this
0x180008f40  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180008f45  xor     eax, eax
0x180008f47  mov     rcx, [rsp+88h+var_48]
0x180008f4c  xor     rcx, rsp; StackCookie
0x180008f4f  call    __security_check_cookie
0x180008f54  add     rsp, 50h
0x180008f58  pop     r15
0x180008f5a  pop     r14
0x180008f5c  pop     r12
0x180008f5e  pop     rdi
0x180008f5f  pop     rsi
0x180008f60  pop     rbp
0x180008f61  pop     rbx
0x180008f62  retn
```
