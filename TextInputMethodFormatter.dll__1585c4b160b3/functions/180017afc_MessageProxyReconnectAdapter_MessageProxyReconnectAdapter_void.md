# MessageProxyReconnectAdapter::~MessageProxyReconnectAdapter(void)

- ea: `0x180017afc`
- end: `0x180017b9c`
- name: `??1MessageProxyReconnectAdapter@@UEAA@XZ`
- size: `160`
- prototype: `void __fastcall(MessageProxyReconnectAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180017bb0`

## callees

- `0x180017afc`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017b09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017b09`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MessageProxyReconnectAdapter::~MessageProxyReconnectAdapter(HSTRING *this)
{
  HSTRING v2; // rcx
  HSTRING v3; // rcx
  HSTRING v4; // rcx
  HSTRING v5; // rcx

  WindowsDeleteString(this[11]);
  this[11] = 0;
  v2 = this[10];
  if ( v2 )
  {
    this[10] = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = this[9];
  if ( v3 )
  {
    this[9] = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = this[8];
  if ( v4 )
  {
    this[8] = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v4 + 16LL))(v4);
  }
  v5 = this[7];
  if ( v5 )
  {
    this[7] = 0;
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v5 + 16LL))(v5);
  }
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x180017afc  push    rbx
0x180017afe  sub     rsp, 20h
0x180017b02  mov     rbx, rcx
0x180017b05  mov     rcx, [rcx+58h]; string
0x180017b09  call    cs:__imp_WindowsDeleteString
0x180017b0f  mov     qword ptr [rbx+58h], 0
0x180017b17  mov     rcx, [rbx+50h]
0x180017b1b  test    rcx, rcx
0x180017b1e  jz      short loc_180017B35
0x180017b20  mov     qword ptr [rbx+50h], 0
0x180017b28  mov     rax, [rcx]
0x180017b2b  mov     rax, [rax+10h]
0x180017b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b34  nop
0x180017b35  mov     rcx, [rbx+48h]
0x180017b39  test    rcx, rcx
0x180017b3c  jz      short loc_180017B53
0x180017b3e  mov     qword ptr [rbx+48h], 0
0x180017b46  mov     rax, [rcx]
0x180017b49  mov     rax, [rax+10h]
0x180017b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b52  nop
0x180017b53  mov     rcx, [rbx+40h]
0x180017b57  test    rcx, rcx
0x180017b5a  jz      short loc_180017B71
0x180017b5c  mov     qword ptr [rbx+40h], 0
0x180017b64  mov     rax, [rcx]
0x180017b67  mov     rax, [rax+10h]
0x180017b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b70  nop
0x180017b71  mov     rcx, [rbx+38h]
0x180017b75  test    rcx, rcx
0x180017b78  jz      short loc_180017B8F
0x180017b7a  mov     qword ptr [rbx+38h], 0
0x180017b82  mov     rax, [rcx]
0x180017b85  mov     rax, [rax+10h]
0x180017b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b8e  nop
0x180017b8f  mov     dword ptr [rbx+14h], 0C0000001h
0x180017b96  add     rsp, 20h
0x180017b9a  pop     rbx
0x180017b9b  retn
```
