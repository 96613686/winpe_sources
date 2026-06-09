# winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand::~PopupCommand(void)

- ea: `0x18000f298`
- end: `0x18000f303`
- name: `??1PopupCommand@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UEAA@XZ`
- size: `107`
- prototype: `void __fastcall(winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000fa60`

## callees

- `0x180002d55`
- `0x180002d91`
- `0x1800058ec`
- `0x18000b5d0`
- `0x18000f298`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f2fc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f2fc`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand::~PopupCommand(
        winrt::Windows::Internal::NetworkUX::Firewall::implementation::PopupCommand *this)
{
  _QWORD *v2; // rcx
  volatile signed __int32 *v3; // rdi
  int v4; // eax
  HANDLE ProcessHeap; // rax

  v2 = (_QWORD *)((char *)this + 40);
  if ( *v2 )
    winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(v2);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  if ( v3 )
  {
    v4 = _InterlockedDecrement(v3 + 6);
    if ( v4 )
    {
      if ( v4 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v3);
    }
    *((_QWORD *)this + 4) = 0;
  }
  winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,IClassFactory>::~root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,IClassFactory>((char *)this + 8);
}

```

## disassembly

```asm
0x18000f298  mov     [rsp+arg_0], rbx
0x18000f29d  push    rdi
0x18000f29e  sub     rsp, 20h
0x18000f2a2  mov     rbx, rcx
0x18000f2a5  add     rcx, 28h ; '('
0x18000f2a9  cmp     qword ptr [rcx], 0
0x18000f2ad  jz      short loc_18000F2B4
0x18000f2af  call    ?unconditional_release_ref@?$com_ptr@UFirewallWarningDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialog>::unconditional_release_ref(void)
0x18000f2b4  mov     rdi, [rbx+20h]
0x18000f2b8  test    rdi, rdi
0x18000f2bb  jz      short loc_18000F2E5
0x18000f2bd  or      eax, 0FFFFFFFFh
0x18000f2c0  lock xadd [rdi+18h], eax
0x18000f2c5  sub     eax, 1
0x18000f2c8  jnz     short loc_18000F2F8
0x18000f2ca  nop
0x18000f2cb  call    WINRT_IMPL_GetProcessHeap
0x18000f2d0  mov     rcx, rax; hHeap
0x18000f2d3  mov     r8, rdi; lpMem
0x18000f2d6  xor     edx, edx; dwFlags
0x18000f2d8  call    WINRT_IMPL_HeapFree
0x18000f2dd  mov     qword ptr [rbx+20h], 0
0x18000f2e5  lea     rcx, [rbx+8]
0x18000f2e9  mov     rbx, [rsp+28h+arg_0]
0x18000f2ee  add     rsp, 20h
0x18000f2f2  pop     rdi
0x18000f2f3  jmp     ??1?$root_implements@UFirewallWarningDialogFactory@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UIClassFactory@@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,IClassFactory>::~root_implements<winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallWarningDialogFactory,IClassFactory>(void)
0x18000f2f8  test    eax, eax
0x18000f2fa  jns     short loc_18000F2DD
0x18000f2fc  call    cs:__imp_abort
```
