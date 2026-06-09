# CTouchSelectionHandle::~CTouchSelectionHandle(void)

- ea: `0x1800da2a8`
- end: `0x1800da31f`
- name: `??1CTouchSelectionHandle@@UEAA@XZ`
- size: `119`
- prototype: `void __fastcall(CTouchSelectionHandle *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800da280`
- `0x1801fa6d0`

## callees

- `0x1800da2a8`
- `0x18012a57c`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x1800da2f6`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x1800da2f6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!UnregisterClassW` at `0x1800da30c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!UnregisterClassW` at `0x1800da30c`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800da2ee`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1800da2ee`

## pseudocode

```c
void __fastcall CTouchSelectionHandle::~CTouchSelectionHandle(CTouchSelectionHandle *this)
{
  void *v2; // rcx
  HWND v3; // rcx

  *(_QWORD *)this = &CTouchSelectionHandle::`vftable';
  v2 = (void *)*((_QWORD *)this + 10);
  if ( v2 )
    DeleteObject(v2);
  v3 = (HWND)*((_QWORD *)this + 9);
  if ( v3 )
    DestroyWindow(v3);
  if ( CTouchSelectionHandle::s_ClassAtom && UnregisterClassW(L"RichEditGripperWnd", hinstRE) )
    CTouchSelectionHandle::s_ClassAtom = 0;
  CTouchTracker::~CTouchTracker(this);
}

```

## disassembly

```asm
0x1800da2a8  mov     [rsp+arg_0], rbx
0x1800da2ad  push    rdi
0x1800da2ae  sub     rsp, 20h
0x1800da2b2  lea     rax, ??_7CTouchSelectionHandle@@6B@; const CTouchSelectionHandle::`vftable'
0x1800da2b9  mov     rbx, rcx
0x1800da2bc  mov     [rcx], rax
0x1800da2bf  xor     edi, edi
0x1800da2c1  mov     rcx, [rcx+50h]; ho
0x1800da2c5  test    rcx, rcx
0x1800da2c8  jnz     short loc_1800DA2EE
0x1800da2ca  mov     rcx, [rbx+48h]; hWnd
0x1800da2ce  test    rcx, rcx
0x1800da2d1  jnz     short loc_1800DA2F6
0x1800da2d3  cmp     cs:?s_ClassAtom@CTouchSelectionHandle@@1GA, di; ushort CTouchSelectionHandle::s_ClassAtom
0x1800da2da  jnz     short loc_1800DA2FE
0x1800da2dc  mov     rcx, rbx; this
0x1800da2df  mov     rbx, [rsp+28h+arg_0]
0x1800da2e4  add     rsp, 20h
0x1800da2e8  pop     rdi
0x1800da2e9  jmp     ??1CTouchTracker@@UEAA@XZ; CTouchTracker::~CTouchTracker(void)
0x1800da2ee  call    cs:__imp_DeleteObject
0x1800da2f4  jmp     short loc_1800DA2CA
0x1800da2f6  call    cs:__imp_DestroyWindow
0x1800da2fc  jmp     short loc_1800DA2D3
0x1800da2fe  mov     rdx, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; hInstance
0x1800da305  lea     rcx, aRicheditgrippe; "RichEditGripperWnd"
0x1800da30c  call    cs:__imp_UnregisterClassW
0x1800da312  test    eax, eax
0x1800da314  jz      short loc_1800DA2DC
0x1800da316  mov     cs:?s_ClassAtom@CTouchSelectionHandle@@1GA, di; ushort CTouchSelectionHandle::s_ClassAtom
0x1800da31d  jmp     short loc_1800DA2DC
```
