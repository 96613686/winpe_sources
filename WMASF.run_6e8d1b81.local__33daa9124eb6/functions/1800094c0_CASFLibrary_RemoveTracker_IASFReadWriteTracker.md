# CASFLibrary::RemoveTracker(IASFReadWriteTracker *)

- ea: `0x1800094c0`
- end: `0x1800095e0`
- name: `?RemoveTracker@CASFLibrary@@UEAAJPEAUIASFReadWriteTracker@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(CASFLibrary *__hidden this, struct IASFReadWriteTracker *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800015d0`
- `0x1800021dc`
- `0x18000220c`
- `0x180007910`
- `0x1800094c0`
- `0x1800095e8`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFLibrary::RemoveTracker(CASFLibrary *this, struct IASFReadWriteTracker *a2)
{
  __int64 result; // rax
  unsigned int v5; // ebx
  unsigned int v6; // ebp
  unsigned int i; // ebx
  int v8; // esi
  _BYTE v9[8]; // [rsp+20h] [rbp-48h] BYREF
  struct IWMSCriticalSection *v10; // [rsp+28h] [rbp-40h] BYREF

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
      for ( i = 0; ; ++i )
      {
        if ( i >= v6 )
        {
          v5 = -1072887824;
          goto LABEL_17;
        }
        if ( a2 == (struct IASFReadWriteTracker *)CTDynArray<IASFReadWriteTracker *,20>::operator[](
                                                    (__int64)this + 312,
                                                    i) )
          break;
      }
      if ( i + 1 <= *((_DWORD *)this + 132) )
      {
        v8 = 0;
        while ( (int)CTSparseBlock<unsigned long,IASFReadWriteTracker *,20,0>::RemoveValue((char *)this + 312, i) >= 0 )
        {
          --*((_DWORD *)this + 132);
          if ( ++v8 )
          {
            (*(void (__fastcall **)(struct IASFReadWriteTracker *))(*(_QWORD *)a2 + 16LL))(a2);
            v5 = 0;
            goto LABEL_17;
          }
        }
      }
      v5 = -2147418113;
    }
    else
    {
      v5 = -2147024809;
    }
LABEL_17:
    CAutoCritSec::~CAutoCritSec((CAutoCritSec *)v9);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800094c0  mov     [rsp+arg_10], rbx
0x1800094c5  push    rbp
0x1800094c6  push    rsi
0x1800094c7  push    rdi
0x1800094c8  push    r14
0x1800094ca  push    r15
0x1800094cc  sub     rsp, 40h
0x1800094d0  mov     rax, cs:__security_cookie
0x1800094d7  xor     rax, rsp
0x1800094da  mov     [rsp+68h+var_38], rax
0x1800094df  mov     r15, rcx
0x1800094e2  mov     [rsp+68h+var_40], 0
0x1800094eb  add     rcx, 8
0x1800094ef  mov     r14, rdx
0x1800094f2  lea     rdx, [rsp+68h+var_40]
0x1800094f7  mov     rax, [rcx]
0x1800094fa  mov     rax, [rax+18h]
0x1800094fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009503  test    eax, eax
0x180009505  js      loc_1800095BF
0x18000950b  mov     rdx, [rsp+68h+var_40]; struct IWMSCriticalSection *
0x180009510  lea     rcx, [rsp+68h+var_48]; this
0x180009515  call    ??0CAutoCritSec@@QEAA@PEAUIWMSCriticalSection@@@Z; CAutoCritSec::CAutoCritSec(IWMSCriticalSection *)
0x18000951a  mov     rcx, [rsp+68h+var_40]
0x18000951f  test    rcx, rcx
0x180009522  jz      short loc_180009539
0x180009524  mov     rax, [rcx]
0x180009527  mov     rax, [rax+10h]
0x18000952b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009530  mov     [rsp+68h+var_40], 0
0x180009539  test    r14, r14
0x18000953c  jnz     short loc_180009545
0x18000953e  mov     ebx, 80070057h
0x180009543  jmp     short loc_1800095B3
0x180009545  mov     ebp, [r15+210h]
0x18000954c  xor     ebx, ebx
0x18000954e  cmp     ebx, ebp
0x180009550  jnb     short loc_1800095AE
0x180009552  lea     rdi, [r15+138h]
0x180009559  mov     edx, ebx
0x18000955b  mov     rcx, rdi
0x18000955e  lea     esi, [rbx+1]
0x180009561  call    ??A?$CTDynArray@PEAUIASFReadWriteTracker@@$0BE@@@QEBAPEAUIASFReadWriteTracker@@K@Z; CTDynArray<IASFReadWriteTracker *,20>::operator[](ulong)
0x180009566  cmp     r14, rax
0x180009569  jz      short loc_18000956F
0x18000956b  mov     ebx, esi
0x18000956d  jmp     short loc_18000954E
0x18000956f  cmp     esi, [rdi+0D8h]
0x180009575  ja      short loc_1800095A7
0x180009577  xor     esi, esi
0x180009579  mov     edx, ebx
0x18000957b  mov     rcx, rdi
0x18000957e  call    ?RemoveValue@?$CTSparseBlock@KPEAUIASFReadWriteTracker@@$0BE@$0A@@@QEAAJK@Z; CTSparseBlock<ulong,IASFReadWriteTracker *,20,0>::RemoveValue(ulong)
0x180009583  test    eax, eax
0x180009585  js      short loc_1800095A7
0x180009587  dec     dword ptr [rdi+0D8h]
0x18000958d  inc     esi
0x18000958f  cmp     esi, 1
0x180009592  jb      short loc_180009579
0x180009594  mov     rax, [r14]
0x180009597  mov     rcx, r14
0x18000959a  mov     rax, [rax+10h]
0x18000959e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095a3  xor     ebx, ebx
0x1800095a5  jmp     short loc_1800095B3
0x1800095a7  mov     ebx, 8000FFFFh
0x1800095ac  jmp     short loc_1800095B3
0x1800095ae  mov     ebx, 0C00D07F0h
0x1800095b3  lea     rcx, [rsp+68h+var_48]; this
0x1800095b8  call    ??1CAutoCritSec@@QEAA@XZ; CAutoCritSec::~CAutoCritSec(void)
0x1800095bd  mov     eax, ebx
0x1800095bf  mov     rcx, [rsp+68h+var_38]
0x1800095c4  xor     rcx, rsp; StackCookie
0x1800095c7  call    __security_check_cookie
0x1800095cc  mov     rbx, [rsp+68h+arg_10]
0x1800095d4  add     rsp, 40h
0x1800095d8  pop     r15
0x1800095da  pop     r14
0x1800095dc  pop     rdi
0x1800095dd  pop     rsi
0x1800095de  pop     rbp
0x1800095df  retn
```
