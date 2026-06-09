# UACIndicatorControlHost::Deactivate(void)

- ea: `0x18001a4c0`
- end: `0x18001a500`
- name: `?Deactivate@UACIndicatorControlHost@@QEAAXXZ`
- size: `64`
- prototype: `void __fastcall(UACIndicatorControlHost *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180030750`

## callees

- `0x18001a4c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a4ec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001a4ec`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostThreadMessageW` at `0x18001a4dd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostThreadMessageW` at `0x18001a4dd`

## pseudocode

```c
void __fastcall UACIndicatorControlHost::Deactivate(UACIndicatorControlHost *this)
{
  if ( *((_QWORD *)this + 1) )
  {
    PostThreadMessageW(*((_DWORD *)this + 4), 0x12u, 0, 0);
    WaitForSingleObject(*((HANDLE *)this + 1), 0x1388u);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18001a4c0  push    rbx
0x18001a4c2  sub     rsp, 20h
0x18001a4c6  cmp     qword ptr [rcx+8], 0
0x18001a4cb  mov     rbx, rcx
0x18001a4ce  jz      short loc_18001A4FA
0x18001a4d0  mov     ecx, [rcx+10h]; idThread
0x18001a4d3  xor     r9d, r9d; lParam
0x18001a4d6  xor     r8d, r8d; wParam
0x18001a4d9  lea     edx, [r9+12h]; Msg
0x18001a4dd  call    cs:__imp_PostThreadMessageW
0x18001a4e3  mov     rcx, [rbx+8]; hHandle
0x18001a4e7  mov     edx, 1388h; dwMilliseconds
0x18001a4ec  call    cs:__imp_WaitForSingleObject
0x18001a4f2  mov     qword ptr [rbx+8], 0
0x18001a4fa  add     rsp, 20h
0x18001a4fe  pop     rbx
0x18001a4ff  retn
```
