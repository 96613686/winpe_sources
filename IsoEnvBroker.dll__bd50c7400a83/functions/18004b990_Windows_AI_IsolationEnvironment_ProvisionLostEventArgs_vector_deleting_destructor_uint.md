# Windows::AI::IsolationEnvironment::ProvisionLostEventArgs::`vector deleting destructor'(uint)

- ea: `0x18004b990`
- end: `0x18004b9f5`
- name: `??_EProvisionLostEventArgs@IsolationEnvironment@AI@Windows@@UEAAPEAXI@Z`
- size: `101`
- prototype: `HSTRING *__fastcall(HSTRING *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800029cc`
- `0x180012ad0`
- `0x18004b990`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b9b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b9b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HSTRING *__fastcall Windows::AI::IsolationEnvironment::ProvisionLostEventArgs::`vector deleting destructor'(
        HSTRING *this,
        char a2)
{
  __int64 v4; // rcx

  WindowsDeleteString(this[7]);
  this[7] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
  v4 = (__int64)this[4];
  if ( v4 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(2 * v4);
  if ( (a2 & 1) != 0 )
    operator delete(this, (const struct std::nothrow_t *)0x40);
  return this;
}

```

## disassembly

```asm
0x18004b990  mov     [rsp+arg_0], rbx
0x18004b995  push    rdi
0x18004b996  sub     rsp, 20h
0x18004b99a  mov     rbx, rcx
0x18004b99d  mov     edi, edx
0x18004b99f  mov     rcx, [rcx+38h]; string
0x18004b9a3  call    cs:__imp_WindowsDeleteString
0x18004b9a9  mov     qword ptr [rbx+38h], 0
0x18004b9b1  mov     rcx, [rbx+30h]; string
0x18004b9b5  call    cs:__imp_WindowsDeleteString
0x18004b9bb  mov     qword ptr [rbx+30h], 0
0x18004b9c3  mov     rcx, [rbx+20h]
0x18004b9c7  test    rcx, rcx
0x18004b9ca  jns     short loc_18004B9D4
0x18004b9cc  add     rcx, rcx
0x18004b9cf  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18004b9d4  test    dil, 1
0x18004b9d8  jz      short loc_18004B9E7
0x18004b9da  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x18004b9df  mov     rcx, rbx; void *
0x18004b9e2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004b9e7  mov     rax, rbx
0x18004b9ea  mov     rbx, [rsp+28h+arg_0]
0x18004b9ef  add     rsp, 20h
0x18004b9f3  pop     rdi
0x18004b9f4  retn
```
