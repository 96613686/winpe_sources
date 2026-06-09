# winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::WindowsUpdateGetAdministratorResult>::make_weak_ref(void)

- ea: `0x1800170cc`
- end: `0x1800171bd`
- name: `?make_weak_ref@?$root_implements@UWindowsUpdateGetAdministratorResult@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@AEAAPEAUIWeakReferenceSource@23@XZ`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180017968`

## callees

- `0x180002cf0`
- `0x1800170cc`
- `0x180017be4`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsUpdateGetAdministratorResult,winrt::Windows::Management::Update::WindowsUpdateGetAdministratorResult>::make_weak_ref(
        volatile signed __int64 *a1)
{
  signed __int64 v1; // rdi
  unsigned __int64 v4; // rbx
  __int64 v5; // rax
  bool v6; // zf
  __int64 v7; // rax
  __int64 v8; // rbx
  unsigned __int64 v9; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_QWORD *)a1 + 1);
  if ( v1 >= 0 )
  {
    v4 = (unsigned __int64)operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
    if ( v4 )
    {
      v5 = (*(__int64 (__fastcall **)(volatile signed __int64 *))(*a1 + 24))(a1);
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *(_QWORD *)(v4 + 8) = &winrt::impl::weak_source<1,1>::`vftable';
      *(_QWORD *)v4 = &winrt::impl::weak_ref<1,1>::`vftable';
      *(_DWORD *)(v4 + 24) = v1;
      *(_DWORD *)(v4 + 28) = 1;
      *(_QWORD *)(v4 + 16) = v5;
    }
    else
    {
      v4 = 0;
    }
    v9 = v4;
    if ( v4 )
    {
      while ( 1 )
      {
        v7 = _InterlockedCompareExchange64(a1 + 1, (v4 >> 1) | 0x8000000000000000uLL, v1);
        v6 = v1 == v7;
        v1 = v7;
        if ( v6 )
          break;
        if ( v7 < 0 )
        {
          _InterlockedIncrement((volatile signed __int32 *)(2 * v7 + 24));
          v8 = 2 * v7 + 8;
          winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(&v9);
          return v8;
        }
        _InterlockedExchange((volatile __int32 *)(v4 + 24), v7);
      }
      _InterlockedIncrement((volatile signed __int32 *)(v4 + 24));
      return v4 + 8;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    _InterlockedIncrement((volatile signed __int32 *)(2 * v1 + 24));
    return 2 * v1 + 8;
  }
}

```

## disassembly

```asm
0x1800170cc  mov     [rsp+arg_8], rbx
0x1800170d1  mov     [rsp+arg_10], rsi
0x1800170d6  push    rdi
0x1800170d7  sub     rsp, 20h
0x1800170db  mov     rdi, [rcx+8]
0x1800170df  mov     rsi, rcx
0x1800170e2  test    rdi, rdi
0x1800170e5  jns     short loc_1800170F9
0x1800170e7  lock inc dword ptr [rdi+rdi+18h]
0x1800170ec  lea     rax, ds:8[rdi*2]
0x1800170f4  jmp     loc_1800171AC
0x1800170f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017100  mov     ecx, 20h ; ' '; unsigned __int64
0x180017105  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001710a  mov     rbx, rax
0x18001710d  test    rax, rax
0x180017110  jz      short loc_18001714D
0x180017112  mov     rax, [rsi]
0x180017115  mov     rcx, rsi
0x180017118  mov     rax, [rax+18h]
0x18001711c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017121  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180017128  lea     rcx, ??_7?$weak_source@$00$00@impl@winrt@@6B@; const winrt::impl::weak_source<1,1>::`vftable'
0x18001712f  mov     [rbx+8], rcx
0x180017133  lea     rcx, ??_7?$weak_ref@$00$00@impl@winrt@@6B@; const winrt::impl::weak_ref<1,1>::`vftable'
0x18001713a  mov     [rbx], rcx
0x18001713d  mov     [rbx+18h], edi
0x180017140  mov     dword ptr [rbx+1Ch], 1
0x180017147  mov     [rbx+10h], rax
0x18001714b  jmp     short loc_18001714F
0x18001714d  xor     ebx, ebx
0x18001714f  mov     [rsp+28h+arg_0], rbx
0x180017154  test    rbx, rbx
0x180017157  jz      short loc_1800171AA
0x180017159  mov     rcx, rbx
0x18001715c  mov     rax, 8000000000000000h
0x180017166  shr     rcx, 1
0x180017169  or      rcx, rax
0x18001716c  mov     rax, rdi
0x18001716f  lock cmpxchg [rsi+8], rcx
0x180017175  mov     rdi, rax
0x180017178  jz      short loc_1800171A0
0x18001717a  test    rax, rax
0x18001717d  js      short loc_180017184
0x18001717f  xchg    eax, [rbx+18h]
0x180017182  jmp     short loc_18001716C
0x180017184  lock inc dword ptr [rax+rax+18h]
0x180017189  lea     rcx, [rsp+28h+arg_0]
0x18001718e  lea     rbx, ds:8[rax*2]
0x180017196  call    ?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)
0x18001719b  mov     rax, rbx
0x18001719e  jmp     short loc_1800171AC
0x1800171a0  lock inc dword ptr [rbx+18h]
0x1800171a4  lea     rax, [rbx+8]
0x1800171a8  jmp     short loc_1800171AC
0x1800171aa  xor     eax, eax
0x1800171ac  mov     rbx, [rsp+28h+arg_8]
0x1800171b1  mov     rsi, [rsp+28h+arg_10]
0x1800171b6  add     rsp, 20h
0x1800171ba  pop     rdi
0x1800171bb  retn
```
