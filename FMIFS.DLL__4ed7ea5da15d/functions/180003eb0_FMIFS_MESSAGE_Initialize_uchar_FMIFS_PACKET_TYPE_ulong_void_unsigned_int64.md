# FMIFS_MESSAGE::Initialize(uchar (*)(_FMIFS_PACKET_TYPE,ulong,void *),unsigned __int64)

- ea: `0x180003eb0`
- end: `0x180003ed7`
- name: `?Initialize@FMIFS_MESSAGE@@UEAAEP6AEW4_FMIFS_PACKET_TYPE@@KPEAX@Z_K@Z`
- size: `39`
- prototype: `unsigned __int8 __fastcall(FMIFS_MESSAGE *__hidden this, unsigned __int8 (__high *)(enum _FMIFS_PACKET_TYPE, unsigned int, void *), unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004ca0`
- `0x180005240`
- `0x1800058a0`
- `0x180008ba0`

## callees

- `0x180003eb0`

## import_xrefs

- `ulib!?Initialize@MESSAGE@@QEAAEXZ` at `0x180003ec8`
- `ulib!?Initialize@MESSAGE@@QEAAEXZ` at `0x180003ec8`

## pseudocode

```c
unsigned __int8 __fastcall FMIFS_MESSAGE::Initialize(
        MESSAGE *this,
        unsigned __int8 (__high *a2)(enum _FMIFS_PACKET_TYPE, unsigned int, void *),
        __int64 a3)
{
  this[10].UpdateCompleteMessage.InterfaceIndex = 0;
  *((_QWORD *)&this[8].InterfaceIndex + 1) = a2;
  *(_QWORD *)(&this[9].InterfaceIndex + 1) = a3;
  if ( a2 )
    return MESSAGE::Initialize(this);
  else
    return 0;
}

```

## disassembly

```asm
0x180003eb0  sub     rsp, 28h
0x180003eb4  mov     dword ptr [rcx+78h], 0
0x180003ebb  mov     [rcx+68h], rdx
0x180003ebf  mov     [rcx+70h], r8
0x180003ec3  test    rdx, rdx
0x180003ec6  jz      short loc_180003ED0
0x180003ec8  call    cs:__imp_?Initialize@MESSAGE@@QEAAEXZ; MESSAGE::Initialize(void)
0x180003ece  jmp     short loc_180003ED2
0x180003ed0  xor     al, al
0x180003ed2  add     rsp, 28h
0x180003ed6  retn
```
