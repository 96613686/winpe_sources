# winrt::clear_factory_cache(void)

- ea: `0x180013ae0`
- end: `0x180013b90`
- name: `?clear_factory_cache@winrt@@YAXXZ`
- size: `176`
- prototype: `void __fastcall(winrt *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007150`
- `0x180030930`

## callees

- `0x180013ae0`
- `0x180034ef0`
- `0x18003970f`
- `0x18003bed0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::clear_factory_cache(winrt *this)
{
  PSLIST_ENTRY v1; // r8
  struct _SLIST_ENTRY *Next; // rdi
  struct _SLIST_ENTRY *v3; // r9
  __int128 v4; // rt0
  unsigned __int8 v5; // tt

  v1 = WINRT_IMPL_InterlockedFlushSList(&`winrt::impl::get_factory_cache'::`2'::cache);
  if ( v1 )
  {
    do
    {
      Next = v1->Next;
      v3 = v1[-1].Next;
      if ( v3 )
      {
        v4 = (unsigned __int64)v1[-1].Next;
        v5 = _InterlockedCompareExchange128((volatile signed __int64 *)&v1[-1], 0, 0, (signed __int64 *)&v4);
        if ( v5 != 0 )
          ((void (__fastcall *)(struct _SLIST_ENTRY *))v3->Next[1].Next)(v3);
      }
      v1 = Next;
    }
    while ( Next );
  }
}

```

## disassembly

```asm
0x180013ae0  sub     rsp, 48h
0x180013ae4  mov     rax, cs:__security_cookie
0x180013aeb  xor     rax, rsp
0x180013aee  mov     [rsp+48h+var_18], rax
0x180013af3  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180013afa  call    WINRT_IMPL_InterlockedFlushSList
0x180013aff  mov     r8, rax
0x180013b02  test    rax, rax
0x180013b05  jz      short loc_180013B7E
0x180013b07  mov     [rsp+48h+arg_8], rsi
0x180013b0c  xor     esi, esi
0x180013b0e  mov     [rsp+48h+var_8], rdi
0x180013b13  mov     [rsp+48h+arg_0], rbx
0x180013b18  nop     dword ptr [rax+rax+00000000h]
0x180013b20  mov     rdi, [r8]
0x180013b23  mov     r9, [r8-10h]
0x180013b27  test    r9, r9
0x180013b2a  jz      short loc_180013B67
0x180013b2c  xor     ecx, ecx
0x180013b2e  mov     [rsp+48h+var_28], r9
0x180013b33  xor     ebx, ebx
0x180013b35  mov     [rsp+48h+var_20], rsi
0x180013b3a  mov     rax, r9
0x180013b3d  mov     rdx, rsi
0x180013b40  lock cmpxchg16b xmmword ptr [r8-10h]
0x180013b46  mov     [rsp+48h+var_28], rax
0x180013b4b  setz    al
0x180013b4e  mov     [rsp+48h+var_20], rdx
0x180013b53  cmp     al, 1
0x180013b55  jnz     short loc_180013B67
0x180013b57  mov     rax, [r9]
0x180013b5a  mov     rcx, r9
0x180013b5d  mov     rax, [rax+10h]
0x180013b61  call    cs:__guard_dispatch_icall_fptr
0x180013b67  mov     r8, rdi
0x180013b6a  test    rdi, rdi
0x180013b6d  jnz     short loc_180013B20
0x180013b6f  mov     rdi, [rsp+48h+var_8]
0x180013b74  mov     rsi, [rsp+48h+arg_8]
0x180013b79  mov     rbx, [rsp+48h+arg_0]
0x180013b7e  mov     rcx, [rsp+48h+var_18]
0x180013b83  xor     rcx, rsp; StackCookie
0x180013b86  call    __security_check_cookie
0x180013b8b  add     rsp, 48h
0x180013b8f  retn
```
