# CStreamPull::OnReadError(long)

- ea: `0x18001b3c0`
- end: `0x18001b45f`
- name: `?OnReadError@CStreamPull@@UEAAXJ@Z`
- size: `159`
- prototype: `void __fastcall(CStreamPull *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001b3c0`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001b423`
- `KERNEL32!LeaveCriticalSection` at `0x18001b423`
- `KERNEL32!EnterCriticalSection` at `0x18001b3ef`
- `KERNEL32!EnterCriticalSection` at `0x18001b3ef`

## pseudocode

```c
void __fastcall CStreamPull::OnReadError(CStreamPull *this, int a2)
{
  __int64 v2; // rbx
  __int64 v4; // rsi
  __int64 v5; // rcx

  v2 = a2;
  if ( a2 != -2147220953 )
  {
    v4 = *((_QWORD *)this + 23);
    EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v4 + 80) + 296LL));
    v5 = *(_QWORD *)(*(_QWORD *)(v4 + 80) + 104LL);
    if ( v5 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v5 + 24LL))(v5, 3, v2);
    LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(v4 + 80) + 296LL));
    (*(void (__fastcall **)(CStreamPull *))(*(_QWORD *)this + 32LL))(this);
    (*(void (__fastcall **)(CStreamPull *, _QWORD))(*(_QWORD *)this + 40LL))(this, (unsigned int)v2);
    *((_DWORD *)this + 43) = v2;
  }
}

```

## disassembly

```asm
0x18001b3c0  mov     [rsp+arg_0], rbx
0x18001b3c5  mov     [rsp+arg_8], rsi
0x18001b3ca  push    rdi
0x18001b3cb  sub     rsp, 30h
0x18001b3cf  movsxd  rbx, edx
0x18001b3d2  mov     rdi, rcx
0x18001b3d5  cmp     ebx, 80040227h
0x18001b3db  jz      short loc_18001B44F
0x18001b3dd  mov     rsi, [rcx+0B8h]
0x18001b3e4  mov     rcx, [rsi+50h]
0x18001b3e8  add     rcx, 128h; lpCriticalSection
0x18001b3ef  call    cs:__imp_EnterCriticalSection
0x18001b3f5  mov     rax, [rsi+50h]
0x18001b3f9  mov     rcx, [rax+68h]
0x18001b3fd  test    rcx, rcx
0x18001b400  jz      short loc_18001B418
0x18001b402  mov     rax, [rcx]
0x18001b405  xor     r9d, r9d
0x18001b408  mov     r8, rbx
0x18001b40b  mov     rax, [rax+18h]
0x18001b40f  lea     edx, [r9+3]
0x18001b413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b418  mov     rcx, [rsi+50h]
0x18001b41c  add     rcx, 128h; lpCriticalSection
0x18001b423  call    cs:__imp_LeaveCriticalSection
0x18001b429  mov     rax, [rdi]
0x18001b42c  mov     rcx, rdi
0x18001b42f  mov     rax, [rax+20h]
0x18001b433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b438  mov     rax, [rdi]
0x18001b43b  mov     edx, ebx
0x18001b43d  mov     rcx, rdi
0x18001b440  mov     rax, [rax+28h]
0x18001b444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b449  mov     [rdi+0ACh], ebx
0x18001b44f  mov     rbx, [rsp+38h+arg_0]
0x18001b454  mov     rsi, [rsp+38h+arg_8]
0x18001b459  add     rsp, 30h
0x18001b45d  pop     rdi
0x18001b45e  retn
```
