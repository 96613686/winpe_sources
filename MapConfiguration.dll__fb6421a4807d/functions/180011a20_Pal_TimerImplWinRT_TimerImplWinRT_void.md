# Pal::TimerImplWinRT::~TimerImplWinRT(void)

- ea: `0x180011a20`
- end: `0x180011a64`
- name: `??1TimerImplWinRT@Pal@@UEAA@XZ`
- size: `68`
- prototype: `void __fastcall(Pal::TimerImplWinRT *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012b70`

## callees

- `0x180011a20`
- `0x180013da8`
- `0x180015bd0`
- `0x18001a79c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180011a5d`

## pseudocode

```c
void __fastcall Pal::TimerImplWinRT::~TimerImplWinRT(Pal::TimerImplWinRT *this, __int64 a2)
{
  std::_Ref_count_base *v3; // rcx

  *(_QWORD *)this = &Pal::TimerImplWinRT::`vftable';
  LOBYTE(a2) = 1;
  std::_Atomic_storage<bool,1>::store((char *)this + 8, a2);
  Pal::TimerImplWinRT::cancel(this);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 8);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180011a20  push    rbx
0x180011a22  sub     rsp, 20h
0x180011a26  mov     rbx, rcx
0x180011a29  lea     rax, ??_7TimerImplWinRT@Pal@@6B@; const Pal::TimerImplWinRT::`vftable'
0x180011a30  mov     [rcx], rax
0x180011a33  add     rcx, 8
0x180011a37  mov     dl, 1
0x180011a39  call    ?store@?$_Atomic_storage@_N$00@std@@QEAAX_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::store(bool,std::memory_order)
0x180011a3e  mov     rcx, rbx; this
0x180011a41  call    ?cancel@TimerImplWinRT@Pal@@UEAAXXZ; Pal::TimerImplWinRT::cancel(void)
0x180011a46  mov     rcx, [rbx+40h]; this
0x180011a4a  test    rcx, rcx
0x180011a4d  jz      short loc_180011A54
0x180011a4f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011a54  lea     rcx, [rbx+10h]
0x180011a58  add     rsp, 20h
0x180011a5c  pop     rbx
0x180011a5d  jmp     cs:__imp_DeleteCriticalSection
```
