# CHXSmartScreen::App::~App(void)

- ea: `0x14000bb54`
- end: `0x14000bbc1`
- name: `??1App@CHXSmartScreen@@AE$AAA@XZ`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000fa10`

## callees

- `0x14000bb54`
- `0x14000bbc8`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000bb65`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000bb65`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CHXSmartScreen::App::~App(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
  v2 = *(_QWORD *)(a1 + 160);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *(_QWORD *)(a1 + 152);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *(_QWORD *)(a1 + 96);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return Windows::UI::Xaml::Application::~Application(a1 + 8);
}

```

## disassembly

```asm
0x14000bb54  mov     [rsp+arg_0], rcx
0x14000bb59  push    rbx
0x14000bb5a  sub     rsp, 20h
0x14000bb5e  mov     rbx, rcx
0x14000bb61  add     rcx, 70h ; 'p'; lpCriticalSection
0x14000bb65  call    cs:__imp_DeleteCriticalSection
0x14000bb6b  mov     rcx, [rbx+0A0h]
0x14000bb72  test    rcx, rcx
0x14000bb75  jz      short loc_14000BB84
0x14000bb77  mov     rax, [rcx]
0x14000bb7a  mov     rax, [rax+10h]
0x14000bb7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bb83  nop
0x14000bb84  mov     rcx, [rbx+98h]
0x14000bb8b  test    rcx, rcx
0x14000bb8e  jz      short loc_14000BB9D
0x14000bb90  mov     rax, [rcx]
0x14000bb93  mov     rax, [rax+10h]
0x14000bb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bb9c  nop
0x14000bb9d  mov     rcx, [rbx+60h]
0x14000bba1  test    rcx, rcx
0x14000bba4  jz      short loc_14000BBB3
0x14000bba6  mov     rax, [rcx]
0x14000bba9  mov     rax, [rax+10h]
0x14000bbad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bbb2  nop
0x14000bbb3  lea     rcx, [rbx+8]
0x14000bbb7  add     rsp, 20h
0x14000bbbb  pop     rbx
0x14000bbbc  jmp     ??1Application@Xaml@UI@Windows@@IE$AAA@XZ; Windows::UI::Xaml::Application::~Application(void)
```
