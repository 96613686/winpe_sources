# Windows::UI::Composition::Traverser::NamedEffect::~NamedEffect(void)

- ea: `0x18000b3b0`
- end: `0x18000b3eb`
- name: `??1NamedEffect@Traverser@Composition@UI@Windows@@QEAA@XZ`
- size: `59`
- prototype: `void __fastcall(Windows::UI::Composition::Traverser::NamedEffect *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b230`
- `0x18000b2e8`

## callees

- `0x18000b3b0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b3c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b3c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::UI::Composition::Traverser::NamedEffect::~NamedEffect(
        Windows::UI::Composition::Traverser::NamedEffect *this)
{
  HSTRING v2; // rcx
  __int64 v3; // rcx

  v2 = (HSTRING)*((_QWORD *)this + 1);
  if ( v2 )
    WindowsDeleteString(v2);
  v3 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    *(_QWORD *)this = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
}

```

## disassembly

```asm
0x18000b3b0  push    rbx
0x18000b3b2  sub     rsp, 20h
0x18000b3b6  mov     rbx, rcx
0x18000b3b9  mov     rcx, [rcx+8]; string
0x18000b3bd  test    rcx, rcx
0x18000b3c0  jz      short loc_18000B3C9
0x18000b3c2  call    cs:__imp_WindowsDeleteString
0x18000b3c8  nop
0x18000b3c9  mov     rcx, [rbx]
0x18000b3cc  test    rcx, rcx
0x18000b3cf  jz      short loc_18000B3E5
0x18000b3d1  mov     qword ptr [rbx], 0
0x18000b3d8  mov     rax, [rcx]
0x18000b3db  mov     rax, [rax+10h]
0x18000b3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3e4  nop
0x18000b3e5  add     rsp, 20h
0x18000b3e9  pop     rbx
0x18000b3ea  retn
```
