# Windows::AI::IsolationEnvironment::ProvisionResult::~ProvisionResult(void)

- ea: `0x180020fa0`
- end: `0x180021028`
- name: `??1ProvisionResult@IsolationEnvironment@AI@Windows@@UEAA@XZ`
- size: `136`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022b10`

## callees

- `0x180012ad0`
- `0x180020e6c`
- `0x180020fa0`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020ff0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021002`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020fc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020ff0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180021002`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::AI::IsolationEnvironment::ProvisionResult::~ProvisionResult(HSTRING *this)
{
  HSTRING v2; // rcx
  __int64 v3; // rcx

  std::vector<Microsoft::WRL::Wrappers::HString>::~vector<Microsoft::WRL::Wrappers::HString>((__int64)(this + 13));
  WindowsDeleteString(this[11]);
  this[11] = 0;
  WindowsDeleteString(this[10]);
  this[10] = 0;
  v2 = this[9];
  if ( v2 )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v2 + 16LL))(v2);
  WindowsDeleteString(this[8]);
  this[8] = 0;
  WindowsDeleteString(this[7]);
  this[7] = 0;
  v3 = (__int64)this[5];
  if ( v3 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(2 * v3);
}

```

## disassembly

```asm
0x180020fa0  push    rbx
0x180020fa2  sub     rsp, 20h
0x180020fa6  mov     rbx, rcx
0x180020fa9  add     rcx, 68h ; 'h'
0x180020fad  call    ??1?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::Wrappers::HString>::~vector<Microsoft::WRL::Wrappers::HString>(void)
0x180020fb2  mov     rcx, [rbx+58h]; string
0x180020fb6  call    cs:__imp_WindowsDeleteString
0x180020fbc  mov     qword ptr [rbx+58h], 0
0x180020fc4  mov     rcx, [rbx+50h]; string
0x180020fc8  call    cs:__imp_WindowsDeleteString
0x180020fce  mov     qword ptr [rbx+50h], 0
0x180020fd6  mov     rcx, [rbx+48h]
0x180020fda  test    rcx, rcx
0x180020fdd  jz      short loc_180020FEC
0x180020fdf  mov     rax, [rcx]
0x180020fe2  mov     rax, [rax+10h]
0x180020fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020feb  nop
0x180020fec  mov     rcx, [rbx+40h]; string
0x180020ff0  call    cs:__imp_WindowsDeleteString
0x180020ff6  mov     qword ptr [rbx+40h], 0
0x180020ffe  mov     rcx, [rbx+38h]; string
0x180021002  call    cs:__imp_WindowsDeleteString
0x180021008  mov     qword ptr [rbx+38h], 0
0x180021010  mov     rcx, [rbx+28h]
0x180021014  test    rcx, rcx
0x180021017  jns     short loc_180021022
0x180021019  add     rcx, rcx
0x18002101c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180021021  nop
0x180021022  add     rsp, 20h
0x180021026  pop     rbx
0x180021027  retn
```
