# HidForceFeedbackEffectManager::~HidForceFeedbackEffectManager(void)

- ea: `0x180010294`
- end: `0x180010305`
- name: `??1HidForceFeedbackEffectManager@@UEAA@XZ`
- size: `113`
- prototype: `void __fastcall(HidForceFeedbackEffectManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800108a0`

## callees

- `0x180010294`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800102b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800102b0`

## pseudocode

```c
void __fastcall HidForceFeedbackEffectManager::~HidForceFeedbackEffectManager(HidForceFeedbackEffectManager *this)
{
  HSTRING v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &HidForceFeedbackEffectManager::`vftable';
  v2 = (HSTRING)*((_QWORD *)this + 1);
  if ( v2 )
  {
    WindowsDeleteString(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = *((_QWORD *)this + 5);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 5) = 0;
  }
  v4 = *((_QWORD *)this + 3);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x180010294  push    rbx
0x180010296  sub     rsp, 20h
0x18001029a  lea     rax, ??_7HidForceFeedbackEffectManager@@6B@; const HidForceFeedbackEffectManager::`vftable'
0x1800102a1  mov     rbx, rcx
0x1800102a4  mov     [rcx], rax
0x1800102a7  mov     rcx, [rcx+8]; string
0x1800102ab  test    rcx, rcx
0x1800102ae  jz      short loc_1800102C4
0x1800102b0  call    cs:__imp_WindowsDeleteString
0x1800102b7  nop     dword ptr [rax+rax+00h]
0x1800102bc  mov     qword ptr [rbx+8], 0
0x1800102c4  mov     rcx, [rbx+28h]
0x1800102c8  test    rcx, rcx
0x1800102cb  jz      short loc_1800102E1
0x1800102cd  mov     rax, [rcx]
0x1800102d0  mov     rax, [rax+10h]
0x1800102d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102d9  mov     qword ptr [rbx+28h], 0
0x1800102e1  mov     rcx, [rbx+18h]
0x1800102e5  test    rcx, rcx
0x1800102e8  jz      short loc_1800102FE
0x1800102ea  mov     rax, [rcx]
0x1800102ed  mov     rax, [rax+10h]
0x1800102f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102f6  mov     qword ptr [rbx+18h], 0
0x1800102fe  add     rsp, 20h
0x180010302  pop     rbx
0x180010303  retn
```
