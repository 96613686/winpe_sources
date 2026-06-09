# CASFLibrary::NotifyRead(uchar *,ulong,_GUID const &)

- ea: `0x180008d60`
- end: `0x180008e50`
- name: `?NotifyRead@CASFLibrary@@UEAAJPEAEKAEBU_GUID@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(CASFLibrary *__hidden this, unsigned __int8 *, unsigned int, const struct _GUID *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180007910`
- `0x180008d60`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFLibrary::NotifyRead(
        CASFLibrary *this,
        unsigned __int8 *a2,
        unsigned int a3,
        const struct _GUID *a4)
{
  __int64 result; // rax
  unsigned int v9; // edi
  unsigned int i; // ebx
  __int64 v11; // rax
  _BYTE v12[8]; // [rsp+30h] [rbp-58h] BYREF
  struct IWMSCriticalSection *v13; // [rsp+38h] [rbp-50h] BYREF

  v13 = 0;
  result = (*(__int64 (__fastcall **)(char *, struct IWMSCriticalSection **))(*((_QWORD *)this - 1) + 24LL))(
             (char *)this - 8,
             &v13);
  if ( (int)result >= 0 )
  {
    CAutoCritSec::CAutoCritSec((CAutoCritSec *)v12, v13);
    if ( v13 )
    {
      (*(void (__fastcall **)(struct IWMSCriticalSection *))(*(_QWORD *)v13 + 16LL))(v13);
      v13 = 0;
    }
    v9 = *((_DWORD *)this + 128);
    for ( i = 0; i < v9; ++i )
    {
      if ( CTDynArray<IASFReadWriteTracker *,20>::operator[]((char *)this + 296, i) )
      {
        v11 = CTDynArray<IASFReadWriteTracker *,20>::operator[]((char *)this + 296, i);
        (*(void (__fastcall **)(__int64, unsigned __int8 *, _QWORD, const struct _GUID *))(*(_QWORD *)v11 + 72LL))(
          v11,
          a2,
          a3,
          a4);
      }
    }
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v12);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008d60  push    rbx
0x180008d62  push    rbp
0x180008d63  push    rsi
0x180008d64  push    rdi
0x180008d65  push    r14
0x180008d67  push    r15
0x180008d69  sub     rsp, 58h
0x180008d6d  mov     rax, cs:__security_cookie
0x180008d74  xor     rax, rsp
0x180008d77  mov     [rsp+88h+var_48], rax
0x180008d7c  mov     rsi, rcx
0x180008d7f  mov     [rsp+88h+var_50], 0
0x180008d88  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180008d8c  mov     rbp, rdx
0x180008d8f  lea     rdx, [rsp+88h+var_50]
0x180008d94  mov     r15, r9
0x180008d97  mov     r14d, r8d
0x180008d9a  mov     rax, [rcx]
0x180008d9d  mov     rax, [rax+18h]
0x180008da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008da6  test    eax, eax
0x180008da8  js      loc_180008E36
0x180008dae  mov     rdx, [rsp+88h+var_50]; struct IWMSCriticalSection *
0x180008db3  lea     rcx, [rsp+88h+var_58]; this
0x180008db8  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180008dbd  mov     rcx, [rsp+88h+var_50]
0x180008dc2  test    rcx, rcx
0x180008dc5  jz      short loc_180008DDC
0x180008dc7  mov     rax, [rcx]
0x180008dca  mov     rax, [rax+10h]
0x180008dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dd3  mov     [rsp+88h+var_50], 0
0x180008ddc  mov     edi, [rsi+200h]
0x180008de2  xor     ebx, ebx
0x180008de4  test    edi, edi
0x180008de6  jz      short loc_180008E2A
0x180008de8  mov     edx, ebx
0x180008dea  lea     rcx, [rsi+128h]
0x180008df1  call    ??A?$CTDynArray@PEAUIASFReadWriteTracker@@$0BE@@@QEBAPEAUIASFReadWriteTracker@@K@Z; CTDynArray<IASFReadWriteTracker *,20>::operator[](ulong)
0x180008df6  test    rax, rax
0x180008df9  jz      short loc_180008E24
0x180008dfb  mov     edx, ebx
0x180008dfd  lea     rcx, [rsi+128h]
0x180008e04  call    ??A?$CTDynArray@PEAUIASFReadWriteTracker@@$0BE@@@QEBAPEAUIASFReadWriteTracker@@K@Z; CTDynArray<IASFReadWriteTracker *,20>::operator[](ulong)
0x180008e09  mov     r10, rax
0x180008e0c  mov     r9, r15
0x180008e0f  mov     r8d, r14d
0x180008e12  mov     rdx, rbp
0x180008e15  mov     rcx, [rax]
0x180008e18  mov     rax, [rcx+48h]
0x180008e1c  mov     rcx, r10
0x180008e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e24  inc     ebx
0x180008e26  cmp     ebx, edi
0x180008e28  jb      short loc_180008DE8
0x180008e2a  lea     rcx, [rsp+88h+var_58]; this
0x180008e2f  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180008e34  xor     eax, eax
0x180008e36  mov     rcx, [rsp+88h+var_48]
0x180008e3b  xor     rcx, rsp; StackCookie
0x180008e3e  call    __security_check_cookie
0x180008e43  add     rsp, 58h
0x180008e47  pop     r15
0x180008e49  pop     r14
0x180008e4b  pop     rdi
0x180008e4c  pop     rsi
0x180008e4d  pop     rbp
0x180008e4e  pop     rbx
0x180008e4f  retn
```
