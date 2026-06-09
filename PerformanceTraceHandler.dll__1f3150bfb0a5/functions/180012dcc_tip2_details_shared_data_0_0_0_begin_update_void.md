# tip2::details::shared_data<0,0,0>::begin_update(void)

- ea: `0x180012dcc`
- end: `0x180012df8`
- name: `?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `44`
- prototype: `bool __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180010ca4`
- `0x1800125d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012ddc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012ddc`

## pseudocode

```c
bool __fastcall tip2::details::shared_data<0,0,0>::begin_update(__int64 a1)
{
  int v2; // eax

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  v2 = *(_DWORD *)(a1 + 64);
  ++*(_DWORD *)(a1 + 232);
  return (v2 & 0x100) == 0;
}

```

## disassembly

```asm
0x180012dcc  push    rbx
0x180012dce  sub     rsp, 20h
0x180012dd2  mov     rbx, rcx
0x180012dd5  add     rcx, 0C0h; lpCriticalSection
0x180012ddc  call    cs:__imp_EnterCriticalSection
0x180012de2  mov     eax, [rbx+40h]
0x180012de5  inc     dword ptr [rbx+0E8h]
0x180012deb  shr     eax, 8
0x180012dee  not     al
0x180012df0  and     al, 1
0x180012df2  add     rsp, 20h
0x180012df6  pop     rbx
0x180012df7  retn
```
