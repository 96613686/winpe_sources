# Windows::AutoThreadMode::~AutoThreadMode(void)

- ea: `0x1800419bc`
- end: `0x1800419f5`
- name: `??1AutoThreadMode@Windows@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(Windows::AutoThreadMode *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800431a8`

## callees

- `0x1800419bc`
- `0x180043840`

## import_xrefs

- `KERNEL32!SetThreadErrorMode` at `0x1800419d8`
- `KERNEL32!SetThreadErrorMode` at `0x1800419d8`
- `KERNEL32!GetThreadErrorMode` at `0x1800419c4`
- `KERNEL32!GetThreadErrorMode` at `0x1800419c4`

## pseudocode

```c
void __fastcall Windows::AutoThreadMode::~AutoThreadMode(DWORD *this)
{
  DWORD v1; // ebx
  wil::details::in1diag3 *v2; // rcx

  v1 = *this;
  if ( v1 != GetThreadErrorMode() && !SetThreadErrorMode(v1, 0) )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
}

```

## disassembly

```asm
0x1800419bc  push    rbx
0x1800419be  sub     rsp, 20h
0x1800419c2  mov     ebx, [rcx]
0x1800419c4  call    cs:__imp_GetThreadErrorMode
0x1800419cb  nop     dword ptr [rax+rax+00h]
0x1800419d0  cmp     ebx, eax
0x1800419d2  jz      short loc_1800419E8
0x1800419d4  xor     edx, edx; lpOldMode
0x1800419d6  mov     ecx, ebx; dwNewMode
0x1800419d8  call    cs:__imp_SetThreadErrorMode
0x1800419df  nop     dword ptr [rax+rax+00h]
0x1800419e4  test    eax, eax
0x1800419e6  jz      short loc_1800419EF
0x1800419e8  add     rsp, 20h
0x1800419ec  pop     rbx
0x1800419ed  retn
0x1800419ef  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
