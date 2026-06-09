# Accommodation::~Accommodation(void)

- ea: `0x1400113b0`
- end: `0x14001150f`
- name: `??1Accommodation@@QEAA@XZ`
- size: `351`
- prototype: `void __fastcall(Accommodation *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000bdf4`
- `0x14000c27c`
- `0x14000c8b4`

## callees

- `0x1400113b0`
- `0x140017010`

## pseudocode

```c
void __fastcall Accommodation::~Accommodation(Accommodation *this)
{
  volatile signed __int32 *v2; // rdx
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rdx
  volatile signed __int32 *v5; // rdx
  volatile signed __int32 *v6; // rdx
  volatile signed __int32 *v7; // rdx
  volatile signed __int32 *v8; // rdx
  volatile signed __int32 *v9; // rdx
  volatile signed __int32 *v10; // rdx

  v2 = (volatile signed __int32 *)(*((_QWORD *)this + 9) - 24LL);
  if ( _InterlockedDecrement(v2 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v2 + 8LL))(*(_QWORD *)v2);
  v3 = (volatile signed __int32 *)(*((_QWORD *)this + 7) - 24LL);
  if ( _InterlockedDecrement(v3 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 8LL))(*(_QWORD *)v3);
  v4 = (volatile signed __int32 *)(*((_QWORD *)this + 6) - 24LL);
  if ( _InterlockedDecrement(v4 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
  v5 = (volatile signed __int32 *)(*((_QWORD *)this + 5) - 24LL);
  if ( _InterlockedDecrement(v5 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
  v6 = (volatile signed __int32 *)(*((_QWORD *)this + 4) - 24LL);
  if ( _InterlockedDecrement(v6 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v6 + 8LL))(*(_QWORD *)v6);
  v7 = (volatile signed __int32 *)(*((_QWORD *)this + 3) - 24LL);
  if ( _InterlockedDecrement(v7 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
  v8 = (volatile signed __int32 *)(*((_QWORD *)this + 2) - 24LL);
  if ( _InterlockedDecrement(v8 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
  v9 = (volatile signed __int32 *)(*((_QWORD *)this + 1) - 24LL);
  if ( _InterlockedDecrement(v9 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9);
  v10 = (volatile signed __int32 *)(*(_QWORD *)this - 24LL);
  if ( _InterlockedDecrement(v10 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
}

```

## disassembly

```asm
0x1400113b0  mov     [rsp+arg_0], rbx
0x1400113b5  push    rdi
0x1400113b6  sub     rsp, 20h
0x1400113ba  mov     rbx, rcx
0x1400113bd  mov     rdx, [rcx+48h]
0x1400113c1  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400113c5  or      edi, 0FFFFFFFFh
0x1400113c8  mov     eax, edi
0x1400113ca  lock xadd [rdx+10h], eax
0x1400113cf  add     eax, edi
0x1400113d1  test    eax, eax
0x1400113d3  jg      short loc_1400113E4
0x1400113d5  mov     rcx, [rdx]
0x1400113d8  mov     rax, [rcx]
0x1400113db  mov     rax, [rax+8]
0x1400113df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400113e4  mov     rdx, [rbx+38h]
0x1400113e8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400113ec  mov     eax, edi
0x1400113ee  lock xadd [rdx+10h], eax
0x1400113f3  add     eax, edi
0x1400113f5  test    eax, eax
0x1400113f7  jg      short loc_140011408
0x1400113f9  mov     rcx, [rdx]
0x1400113fc  mov     rax, [rcx]
0x1400113ff  mov     rax, [rax+8]
0x140011403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011408  mov     rdx, [rbx+30h]
0x14001140c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140011410  mov     eax, edi
0x140011412  lock xadd [rdx+10h], eax
0x140011417  add     eax, edi
0x140011419  test    eax, eax
0x14001141b  jg      short loc_14001142C
0x14001141d  mov     rcx, [rdx]
0x140011420  mov     rax, [rcx]
0x140011423  mov     rax, [rax+8]
0x140011427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001142c  mov     rdx, [rbx+28h]
0x140011430  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140011434  mov     eax, edi
0x140011436  lock xadd [rdx+10h], eax
0x14001143b  add     eax, edi
0x14001143d  test    eax, eax
0x14001143f  jg      short loc_140011450
0x140011441  mov     rcx, [rdx]
0x140011444  mov     rax, [rcx]
0x140011447  mov     rax, [rax+8]
0x14001144b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011450  mov     rdx, [rbx+20h]
0x140011454  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140011458  mov     eax, edi
0x14001145a  lock xadd [rdx+10h], eax
0x14001145f  add     eax, edi
0x140011461  test    eax, eax
0x140011463  jg      short loc_140011474
0x140011465  mov     rcx, [rdx]
0x140011468  mov     rax, [rcx]
0x14001146b  mov     rax, [rax+8]
0x14001146f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011474  mov     rdx, [rbx+18h]
0x140011478  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001147c  mov     eax, edi
0x14001147e  lock xadd [rdx+10h], eax
0x140011483  add     eax, edi
0x140011485  test    eax, eax
0x140011487  jg      short loc_140011498
0x140011489  mov     rcx, [rdx]
0x14001148c  mov     rax, [rcx]
0x14001148f  mov     rax, [rax+8]
0x140011493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011498  mov     rdx, [rbx+10h]
0x14001149c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400114a0  mov     eax, edi
0x1400114a2  lock xadd [rdx+10h], eax
0x1400114a7  add     eax, edi
0x1400114a9  test    eax, eax
0x1400114ab  jg      short loc_1400114BC
0x1400114ad  mov     rcx, [rdx]
0x1400114b0  mov     rax, [rcx]
0x1400114b3  mov     rax, [rax+8]
0x1400114b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400114bc  mov     rdx, [rbx+8]
0x1400114c0  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400114c4  mov     eax, edi
0x1400114c6  lock xadd [rdx+10h], eax
0x1400114cb  add     eax, edi
0x1400114cd  test    eax, eax
0x1400114cf  jg      short loc_1400114E0
0x1400114d1  mov     rcx, [rdx]
0x1400114d4  mov     rax, [rcx]
0x1400114d7  mov     rax, [rax+8]
0x1400114db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400114e0  mov     rdx, [rbx]
0x1400114e3  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400114e7  mov     eax, edi
0x1400114e9  lock xadd [rdx+10h], eax
0x1400114ee  add     eax, edi
0x1400114f0  test    eax, eax
0x1400114f2  jg      short loc_140011504
0x1400114f4  mov     rcx, [rdx]
0x1400114f7  mov     rax, [rcx]
0x1400114fa  mov     rax, [rax+8]
0x1400114fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011503  nop
0x140011504  mov     rbx, [rsp+28h+arg_0]
0x140011509  add     rsp, 20h
0x14001150d  pop     rdi
0x14001150e  retn
```
