# Windows::AutoThreadMode::~AutoThreadMode(void)

- ea: `0x18003eaa0`
- end: `0x18003ead9`
- name: `??1AutoThreadMode@Windows@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(DWORD *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18003fdac`

## callees

- `0x18003d9e8`
- `0x18003eaa0`

## import_xrefs

- `KERNEL32!SetThreadErrorMode` at `0x18003eabc`
- `KERNEL32!SetThreadErrorMode` at `0x18003eabc`
- `KERNEL32!GetThreadErrorMode` at `0x18003eaa8`
- `KERNEL32!GetThreadErrorMode` at `0x18003eaa8`

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
0x18003eaa0  push    rbx
0x18003eaa2  sub     rsp, 20h
0x18003eaa6  mov     ebx, [rcx]
0x18003eaa8  call    cs:__imp_GetThreadErrorMode
0x18003eaaf  nop     dword ptr [rax+rax+00h]
0x18003eab4  cmp     ebx, eax
0x18003eab6  jz      short loc_18003EACC
0x18003eab8  xor     edx, edx; lpOldMode
0x18003eaba  mov     ecx, ebx; dwNewMode
0x18003eabc  call    cs:__imp_SetThreadErrorMode
0x18003eac3  nop     dword ptr [rax+rax+00h]
0x18003eac8  test    eax, eax
0x18003eaca  jz      short loc_18003EAD3
0x18003eacc  add     rsp, 20h
0x18003ead0  pop     rbx
0x18003ead1  retn
0x18003ead3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
