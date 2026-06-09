# WinSAT::StorageDevice::StorageDevice(bool &,mlib::handle_ostreamT<ushort,std::char_traits<ushort>> &)

- ea: `0x14006046c`
- end: `0x14006051a`
- name: `??0StorageDevice@WinSAT@@QEAA@AEA_NAEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(WinSAT::StorageDevice *this)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140011164`
- `0x14006099c`
- `0x140061270`
- `0x14006237c`
- `0x1400640c8`

## callees

- `0x140005f10`
- `0x14006046c`
- `0x140060888`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1400604fd`
- `KERNEL32!CreateEventW` at `0x1400604fd`
- `KERNEL32!InitializeSListHead` at `0x1400604ba`
- `KERNEL32!InitializeSListHead` at `0x1400604ba`
- `msvcrt!_aligned_malloc` at `0x1400604a8`
- `msvcrt!_aligned_malloc` at `0x1400604a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
WinSAT::StorageDevice *__fastcall WinSAT::StorageDevice::StorageDevice(
        WinSAT::StorageDevice *this,
        __int64 a2,
        __int64 a3)
{
  union _SLIST_HEADER *v6; // rax

  *(_QWORD *)this = &WinSAT::StorageDevice::`vftable';
  *((_DWORD *)this + 4) = 0;
  *((_DWORD *)this + 5) = 0;
  v6 = (union _SLIST_HEADER *)_aligned_malloc(0x10u, 0x10u);
  *((_QWORD *)this + 1) = v6;
  if ( v6 )
    InitializeSListHead(v6);
  *((_QWORD *)this + 3) = a3;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>((char *)this + 32);
  *((_QWORD *)this + 9) = -1;
  *((_QWORD *)this + 10) = 0;
  *((_BYTE *)this + 93) = 0;
  *((_QWORD *)this + 12) = a2;
  *((_BYTE *)this + 112) = 0;
  WinSAT::StorageDevice::Close(this);
  *((_QWORD *)this + 10) = CreateEventW(0, 0, 0, 0);
  return this;
}

```

## disassembly

```asm
0x14006046c  mov     [rsp+arg_8], rbx
0x140060471  mov     [rsp+arg_10], rsi
0x140060476  mov     [rsp+arg_0], rcx
0x14006047b  push    rdi
0x14006047c  sub     rsp, 20h
0x140060480  mov     rdi, r8
0x140060483  mov     rsi, rdx
0x140060486  mov     rbx, rcx
0x140060489  lea     rax, ??_7StorageDevice@WinSAT@@6B@; const WinSAT::StorageDevice::`vftable'
0x140060490  mov     [rcx], rax
0x140060493  mov     dword ptr [rcx+10h], 0
0x14006049a  mov     dword ptr [rcx+14h], 0
0x1400604a1  mov     ecx, 10h; Size
0x1400604a6  mov     edx, ecx; Alignment
0x1400604a8  call    cs:__imp__aligned_malloc
0x1400604ae  mov     [rbx+8], rax
0x1400604b2  test    rax, rax
0x1400604b5  jz      short loc_1400604C1
0x1400604b7  mov     rcx, rax; ListHead
0x1400604ba  call    cs:__imp_InitializeSListHead
0x1400604c0  nop
0x1400604c1  mov     [rbx+18h], rdi
0x1400604c5  lea     rcx, [rbx+20h]
0x1400604c9  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@XZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(void)
0x1400604ce  nop
0x1400604cf  mov     qword ptr [rbx+48h], 0FFFFFFFFFFFFFFFFh
0x1400604d7  mov     qword ptr [rbx+50h], 0
0x1400604df  mov     byte ptr [rbx+5Dh], 0
0x1400604e3  mov     [rbx+60h], rsi
0x1400604e7  mov     byte ptr [rbx+70h], 0
0x1400604eb  mov     rcx, rbx; this
0x1400604ee  call    ?Close@StorageDevice@WinSAT@@QEAAXXZ; WinSAT::StorageDevice::Close(void)
0x1400604f3  xor     r9d, r9d; lpName
0x1400604f6  xor     r8d, r8d; bInitialState
0x1400604f9  xor     edx, edx; bManualReset
0x1400604fb  xor     ecx, ecx; lpEventAttributes
0x1400604fd  call    cs:__imp_CreateEventW
0x140060503  mov     [rbx+50h], rax
0x140060507  mov     rax, rbx
0x14006050a  mov     rbx, [rsp+28h+arg_8]
0x14006050f  mov     rsi, [rsp+28h+arg_10]
0x140060514  add     rsp, 20h
0x140060518  pop     rdi
0x140060519  retn
```
