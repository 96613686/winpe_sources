# GameInputServerDevice::UpdateSystemButtonState(unsigned __int64)

- ea: `0x180042924`
- end: `0x180042967`
- name: `?UpdateSystemButtonState@GameInputServerDevice@@AEAAX_K@Z`
- size: `67`
- prototype: `void __fastcall(GameInputServerDevice *__hidden this, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18003bbd0`
- `0x18003d7e0`
- `0x18003d8d0`
- `0x18003d990`
- `0x180041ef8`

## callees

- `0x18002efb4`
- `0x180042924`

## pseudocode

```c
void __fastcall GameInputServerDevice::UpdateSystemButtonState(GameInputServerDevice *this, __int64 a2)
{
  int v2; // r9d

  v2 = (*((_BYTE *)this + 228) != 0) | (*((_BYTE *)this + 229) != 0 ? 2 : 0);
  if ( *((_DWORD *)this + 128) != v2 )
  {
    *((_DWORD *)this + 128) = v2;
    GameInputServer::AddSystemButtonStateToDeviceBuffers(*((_QWORD *)this + 8), a2, this);
  }
}

```

## disassembly

```asm
0x180042924  sub     rsp, 28h
0x180042928  mov     al, [rcx+0E5h]
0x18004292e  neg     al
0x180042930  sbb     r9d, r9d
0x180042933  xor     eax, eax
0x180042935  and     r9d, 2
0x180042939  cmp     [rcx+0E4h], al
0x18004293f  setnz   al
0x180042942  or      r9d, eax
0x180042945  cmp     [rcx+200h], r9d
0x18004294c  jz      short loc_180042961
0x18004294e  mov     [rcx+200h], r9d
0x180042955  mov     r8, rcx
0x180042958  mov     rcx, [rcx+40h]
0x18004295c  call    ?AddSystemButtonStateToDeviceBuffers@GameInputServer@@QEAAX_KPEAVGameInputServerDevice@@W4GameInputSystemButtons@@@Z; GameInputServer::AddSystemButtonStateToDeviceBuffers(unsigned __int64,GameInputServerDevice *,GameInputSystemButtons)
0x180042961  add     rsp, 28h
0x180042965  retn
```
