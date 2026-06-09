# CASFLibrary::AddTracker(IASFReadWriteTracker *)

- ea: `0x180007b70`
- end: `0x180007c8c`
- name: `?AddTracker@CASFLibrary@@UEAAJPEAUIASFReadWriteTracker@@@Z`
- size: `284`
- prototype: `__int64 __fastcall(CASFLibrary *__hidden this, struct IASFReadWriteTracker *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180007910`
- `0x180007b70`
- `0x180009854`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFLibrary::AddTracker(CASFLibrary *this, struct IASFReadWriteTracker *a2)
{
  __int64 result; // rax
  unsigned int v5; // ebx
  unsigned int v6; // ebp
  unsigned int v7; // edi
  char *v8; // rcx
  _BYTE v9[8]; // [rsp+20h] [rbp-38h] BYREF
  struct IWMSCriticalSection *v10; // [rsp+28h] [rbp-30h] BYREF

  v10 = 0;
  result = (*(__int64 (__fastcall **)(char *, struct IWMSCriticalSection **))(*((_QWORD *)this + 1) + 24LL))(
             (char *)this + 8,
             &v10);
  if ( (int)result >= 0 )
  {
    CAutoCritSec::CAutoCritSec((CAutoCritSec *)v9, v10);
    if ( v10 )
    {
      (*(void (__fastcall **)(struct IWMSCriticalSection *))(*(_QWORD *)v10 + 16LL))(v10);
      v10 = 0;
    }
    if ( a2 )
    {
      v6 = *((_DWORD *)this + 132);
      v7 = 0;
      v5 = 1;
      while ( 1 )
      {
        v8 = (char *)this + 312;
        if ( v7 >= v6 )
          break;
        if ( a2 == (struct IASFReadWriteTracker *)CTDynArray<IASFReadWriteTracker *,20>::operator[]((__int64)v8, v7) )
          goto LABEL_6;
        ++v7;
      }
      if ( (int)CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::SetValue(
                  v8,
                  *((unsigned int *)this + 132),
                  a2) < 0 )
      {
        CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v9);
        return 2147549183LL;
      }
      else
      {
        ++*((_DWORD *)this + 132);
        (*(void (__fastcall **)(struct IASFReadWriteTracker *))(*(_QWORD *)a2 + 8LL))(a2);
        CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v9);
        return 0;
      }
    }
    else
    {
      v5 = -2147024809;
LABEL_6:
      CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v9);
      return v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007b70  mov     r11, rsp
0x180007b73  mov     [r11+18h], rbx
0x180007b77  mov     [r11+20h], rbp
0x180007b7b  push    rsi
0x180007b7c  push    rdi
0x180007b7d  push    r14
0x180007b7f  sub     rsp, 40h
0x180007b83  mov     rax, cs:__security_cookie
0x180007b8a  xor     rax, rsp
0x180007b8d  mov     [rsp+58h+var_28], rax
0x180007b92  mov     rsi, rcx
0x180007b95  mov     qword ptr [r11-30h], 0
0x180007b9d  add     rcx, 8
0x180007ba1  mov     r14, rdx
0x180007ba4  lea     rdx, [r11-30h]
0x180007ba8  mov     rax, [rcx]
0x180007bab  mov     rax, [rax+18h]
0x180007baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bb4  test    eax, eax
0x180007bb6  js      loc_180007C6C
0x180007bbc  mov     rdx, [rsp+58h+var_30]; struct IWMSCriticalSection *
0x180007bc1  lea     rcx, [rsp+58h+var_38]; this
0x180007bc6  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x180007bcb  mov     rcx, [rsp+58h+var_30]
0x180007bd0  test    rcx, rcx
0x180007bd3  jz      short loc_180007BEA
0x180007bd5  mov     rax, [rcx]
0x180007bd8  mov     rax, [rax+10h]
0x180007bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007be1  mov     [rsp+58h+var_30], 0
0x180007bea  test    r14, r14
0x180007bed  jnz     short loc_180007C02
0x180007bef  mov     ebx, 80070057h
0x180007bf4  lea     rcx, [rsp+58h+var_38]; this
0x180007bf9  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180007bfe  mov     eax, ebx
0x180007c00  jmp     short loc_180007C6C
0x180007c02  mov     ebp, [rsi+210h]
0x180007c08  xor     edi, edi
0x180007c0a  lea     ebx, [rdi+1]
0x180007c0d  lea     rcx, [rsi+138h]
0x180007c14  cmp     edi, ebp
0x180007c16  jnb     short loc_180007C28
0x180007c18  mov     edx, edi
0x180007c1a  call    ??A?$CTDynArray@PEAUIASFReadWriteTracker@@$0BE@@@QEBAPEAUIASFReadWriteTracker@@K@Z; CTDynArray<IASFReadWriteTracker *,20>::operator[](ulong)
0x180007c1f  cmp     r14, rax
0x180007c22  jz      short loc_180007BF4
0x180007c24  add     edi, ebx
0x180007c26  jmp     short loc_180007C0D
0x180007c28  mov     edx, [rsi+210h]
0x180007c2e  mov     r8, r14
0x180007c31  call    ?SetValue@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJKPEAUIASFReadWriteTracker@@@Z; CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::SetValue(ulong,IASFReadWriteTracker *)
0x180007c36  test    eax, eax
0x180007c38  js      short loc_180007C5D
0x180007c3a  add     [rsi+210h], ebx
0x180007c40  mov     rcx, r14
0x180007c43  mov     rax, [r14]
0x180007c46  mov     rax, [rax+8]
0x180007c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c4f  lea     rcx, [rsp+58h+var_38]; this
0x180007c54  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180007c59  xor     eax, eax
0x180007c5b  jmp     short loc_180007C6C
0x180007c5d  lea     rcx, [rsp+58h+var_38]; this
0x180007c62  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x180007c67  mov     eax, 8000FFFFh
0x180007c6c  mov     rcx, [rsp+58h+var_28]
0x180007c71  xor     rcx, rsp; StackCookie
0x180007c74  call    __security_check_cookie
0x180007c79  mov     rbx, [rsp+58h+arg_10]
0x180007c7e  mov     rbp, [rsp+58h+arg_18]
0x180007c83  add     rsp, 40h
0x180007c87  pop     r14
0x180007c89  pop     rdi
0x180007c8a  pop     rsi
0x180007c8b  retn
```
