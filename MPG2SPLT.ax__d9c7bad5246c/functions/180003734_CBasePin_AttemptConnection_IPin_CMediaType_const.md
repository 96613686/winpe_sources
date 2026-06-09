# CBasePin::AttemptConnection(IPin *,CMediaType const *)

- ea: `0x180003734`
- end: `0x180003846`
- name: `?AttemptConnection@CBasePin@@IEAAJPEAUIPin@@PEBVCMediaType@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(CBasePin *__hidden this, struct IPin *, const struct CMediaType *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003314`

## callees

- `0x180003734`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CBasePin::AttemptConnection(CBasePin *this, struct IPin *a2, const struct CMediaType *a3)
{
  int v6; // ebx
  __int64 v7; // rax
  int v8; // eax
  __int64 result; // rax
  __int64 v10; // rcx

  v6 = (*(__int64 (__fastcall **)(CBasePin *))(*(_QWORD *)this + 80LL))(this);
  v7 = *(_QWORD *)this;
  if ( v6 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(CBasePin *, const struct CMediaType *))(v7 + 64))(this, a3);
    v6 = v8;
    if ( v8 )
    {
      if ( v8 >= 0 || v8 == -2147467259 || v8 == -2147024809 )
        v6 = -2147220950;
    }
    else
    {
      *((_QWORD *)this + 6) = a2;
      ((void (__fastcall *)(struct IPin *))a2->lpVtbl->AddRef)(a2);
      v6 = (*(__int64 (__fastcall **)(CBasePin *, const struct CMediaType *))(*(_QWORD *)this + 72LL))(this, a3);
      if ( v6 >= 0 )
      {
        v6 = ((__int64 (__fastcall *)(struct IPin *, unsigned __int64, const struct CMediaType *))a2->lpVtbl->ReceiveConnection)(
               a2,
               ((unsigned __int64)this + 24) & -(__int64)(this != 0),
               a3);
        if ( v6 >= 0 )
        {
          result = (*(__int64 (__fastcall **)(CBasePin *, struct IPin *))(*(_QWORD *)this + 96LL))(this, a2);
          v6 = result;
          if ( (int)result >= 0 )
            return result;
          ((void (__fastcall *)(struct IPin *))a2->lpVtbl->Disconnect)(a2);
        }
      }
    }
    (*(void (__fastcall **)(CBasePin *))(*(_QWORD *)this + 88LL))(this);
    v10 = *((_QWORD *)this + 6);
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      *((_QWORD *)this + 6) = 0;
    }
  }
  else
  {
    (*(void (__fastcall **)(CBasePin *))(v7 + 88))(this);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003734  push    rbx
0x180003736  push    rbp
0x180003737  push    rsi
0x180003738  push    rdi
0x180003739  sub     rsp, 28h
0x18000373d  mov     rax, [rcx]
0x180003740  mov     rbp, r8
0x180003743  mov     rsi, rdx
0x180003746  mov     rdi, rcx
0x180003749  mov     rax, [rax+50h]
0x18000374d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003752  mov     ebx, eax
0x180003754  mov     rcx, rdi
0x180003757  mov     rax, [rdi]
0x18000375a  test    ebx, ebx
0x18000375c  jns     short loc_18000376C
0x18000375e  mov     rax, [rax+58h]
0x180003762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003767  jmp     loc_18000383B
0x18000376c  mov     rax, [rax+40h]
0x180003770  mov     rdx, rbp
0x180003773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003778  mov     ebx, eax
0x18000377a  test    eax, eax
0x18000377c  jnz     short loc_1800037FA
0x18000377e  mov     [rdi+30h], rsi
0x180003782  mov     rcx, rsi
0x180003785  mov     rax, [rsi]
0x180003788  mov     rax, [rax+8]
0x18000378c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003791  mov     rax, [rdi]
0x180003794  mov     rdx, rbp
0x180003797  mov     rcx, rdi
0x18000379a  mov     rax, [rax+48h]
0x18000379e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037a3  mov     ebx, eax
0x1800037a5  test    eax, eax
0x1800037a7  js      short loc_18000380F
0x1800037a9  mov     r9, [rsi]
0x1800037ac  lea     rcx, [rdi+18h]
0x1800037b0  mov     rax, rdi
0x1800037b3  mov     r8, rbp
0x1800037b6  neg     rax
0x1800037b9  mov     rax, [r9+20h]
0x1800037bd  sbb     rdx, rdx
0x1800037c0  and     rdx, rcx
0x1800037c3  mov     rcx, rsi
0x1800037c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037cb  mov     ebx, eax
0x1800037cd  test    eax, eax
0x1800037cf  js      short loc_18000380F
0x1800037d1  mov     rax, [rdi]
0x1800037d4  mov     rdx, rsi
0x1800037d7  mov     rcx, rdi
0x1800037da  mov     rax, [rax+60h]
0x1800037de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e3  mov     ebx, eax
0x1800037e5  test    eax, eax
0x1800037e7  jns     short loc_18000383D
0x1800037e9  mov     rax, [rsi]
0x1800037ec  mov     rcx, rsi
0x1800037ef  mov     rax, [rax+28h]
0x1800037f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f8  jmp     short loc_18000380F
0x1800037fa  jns     short loc_18000380A
0x1800037fc  cmp     eax, 80004005h
0x180003801  jz      short loc_18000380A
0x180003803  cmp     eax, 80070057h
0x180003808  jnz     short loc_18000380F
0x18000380a  mov     ebx, 8004022Ah
0x18000380f  mov     rax, [rdi]
0x180003812  mov     rcx, rdi
0x180003815  mov     rax, [rax+58h]
0x180003819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000381e  mov     rcx, [rdi+30h]
0x180003822  test    rcx, rcx
0x180003825  jz      short loc_18000383B
0x180003827  mov     rax, [rcx]
0x18000382a  mov     rax, [rax+10h]
0x18000382e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003833  mov     qword ptr [rdi+30h], 0
0x18000383b  mov     eax, ebx
0x18000383d  add     rsp, 28h
0x180003841  pop     rdi
0x180003842  pop     rsi
0x180003843  pop     rbp
0x180003844  pop     rbx
0x180003845  retn
```
