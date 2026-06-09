# sub_14001AEAC

- ea: `0x14001aeac`
- end: `0x14001aef2`
- name: `sub_14001AEAC`
- size: `70`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001ad90`
- `0x14001af00`
- `0x14001b2a0`

## callees

- `0x14001aeac`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14001aee1`
- `KERNEL32!SetEvent` at `0x14001aee1`
- `KERNEL32!GetCurrentThreadId` at `0x14001aed0`
- `KERNEL32!GetCurrentThreadId` at `0x14001aed0`

## pseudocode

```c
char __fastcall sub_14001AEAC(__int64 a1)
{
  DWORD CurrentThreadId; // eax
  int v3; // ebx

  LOBYTE(CurrentThreadId) = *(_BYTE *)(a1 + 3080);
  if ( !(_BYTE)CurrentThreadId )
  {
    v3 = *(_DWORD *)(a1 + 3064);
    *(_BYTE *)(a1 + 3080) = 1;
    CurrentThreadId = GetCurrentThreadId();
    if ( v3 != CurrentThreadId )
      LOBYTE(CurrentThreadId) = SetEvent(*(HANDLE *)(a1 + 3072));
  }
  return CurrentThreadId;
}

```

## disassembly

```asm
0x14001aeac  mov     [rsp+arg_0], rbx
0x14001aeb1  push    rdi
0x14001aeb2  sub     rsp, 20h
0x14001aeb6  mov     al, [rcx+0C08h]
0x14001aebc  mov     rdi, rcx
0x14001aebf  test    al, al
0x14001aec1  jnz     short loc_14001AEE7
0x14001aec3  mov     ebx, [rcx+0BF8h]
0x14001aec9  mov     byte ptr [rcx+0C08h], 1
0x14001aed0  call    cs:GetCurrentThreadId
0x14001aed6  cmp     ebx, eax
0x14001aed8  jz      short loc_14001AEE7
0x14001aeda  mov     rcx, [rdi+0C00h]; hEvent
0x14001aee1  call    cs:SetEvent
0x14001aee7  mov     rbx, [rsp+28h+arg_0]
0x14001aeec  add     rsp, 20h
0x14001aef0  pop     rdi
0x14001aef1  retn
```
