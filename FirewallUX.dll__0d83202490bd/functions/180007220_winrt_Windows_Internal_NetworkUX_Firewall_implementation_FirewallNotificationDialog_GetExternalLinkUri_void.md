# winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::GetExternalLinkUri(void)

- ea: `0x180007220`
- end: `0x180007263`
- name: `?GetExternalLinkUri@FirewallNotificationDialog@implementation@Firewall@NetworkUX@Internal@Windows@winrt@@UEBA?BUhstring@7@XZ`
- size: `67`
- prototype: `struct winrt::impl::shared_hstring_header **__fastcall(__int64, struct winrt::impl::shared_hstring_header **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b058`
- `0x18000bbe8`

## string_xrefs

- `0x18000723c`: `https://go.microsoft.com/fwlink/?linkid=2204770`

## pseudocode

```c
struct winrt::impl::shared_hstring_header **__fastcall winrt::Windows::Internal::NetworkUX::Firewall::implementation::FirewallNotificationDialog::GetExternalLinkUri(
        __int64 a1,
        struct winrt::impl::shared_hstring_header **a2)
{
  struct winrt::impl::shared_hstring_header *v3; // rbx

  v3 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x2F, (unsigned int)a2);
  memcpy_s((char *)v3 + 28, 0x5Eu, L"https://go.microsoft.com/fwlink/?linkid=2204770", 0x5Eu);
  *a2 = v3;
  return a2;
}

```

## disassembly

```asm
0x180007220  mov     [rsp+arg_0], rbx
0x180007225  push    rdi
0x180007226  sub     rsp, 30h
0x18000722a  mov     ecx, 2Fh ; '/'; this
0x18000722f  mov     rdi, rdx
0x180007232  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x180007237  mov     edx, 5Eh ; '^'; DestinationSize
0x18000723c  lea     r8, aHttpsGoMicroso; "https://go.microsoft.com/fwlink/?linkid"...
0x180007243  mov     r9d, edx; SourceSize
0x180007246  mov     rbx, rax
0x180007249  lea     rcx, [rax+1Ch]; Destination
0x18000724d  call    memcpy_s
0x180007252  mov     [rdi], rbx
0x180007255  mov     rax, rdi
0x180007258  mov     rbx, [rsp+38h+arg_0]
0x18000725d  add     rsp, 30h
0x180007261  pop     rdi
0x180007262  retn
```
