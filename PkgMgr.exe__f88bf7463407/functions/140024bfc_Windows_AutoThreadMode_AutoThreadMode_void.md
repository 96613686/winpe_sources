# Windows::AutoThreadMode::~AutoThreadMode(void)

- ea: `0x140024bfc`
- end: `0x140024c28`
- name: `??1AutoThreadMode@Windows@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(Windows::AutoThreadMode *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140025fb0`

## callees

- `0x1400062a4`
- `0x140024bfc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x140024c12`
- `api-ms-win-core-errorhandling-l1-1-3!SetThreadErrorMode` at `0x140024c12`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x140024c04`
- `api-ms-win-core-errorhandling-l1-1-3!GetThreadErrorMode` at `0x140024c04`

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
0x140024bfc  push    rbx
0x140024bfe  sub     rsp, 20h
0x140024c02  mov     ebx, [rcx]
0x140024c04  call    cs:__imp_GetThreadErrorMode
0x140024c0a  cmp     ebx, eax
0x140024c0c  jz      short loc_140024C1C
0x140024c0e  xor     edx, edx; lpOldMode
0x140024c10  mov     ecx, ebx; dwNewMode
0x140024c12  call    cs:__imp_SetThreadErrorMode
0x140024c18  test    eax, eax
0x140024c1a  jz      short loc_140024C22
0x140024c1c  add     rsp, 20h
0x140024c20  pop     rbx
0x140024c21  retn
0x140024c22  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
