# FMIFS_CHKMSG::Initialize(uchar (*)(_FMIFS_PACKET_TYPE,ulong,void *))

- ea: `0x180003c60`
- end: `0x180003c8c`
- name: `?Initialize@FMIFS_CHKMSG@@UEAAEP6AEW4_FMIFS_PACKET_TYPE@@KPEAX@Z@Z`
- size: `44`
- prototype: `unsigned __int8 __fastcall(FMIFS_CHKMSG *__hidden this, unsigned __int8 (__high *)(enum _FMIFS_PACKET_TYPE, unsigned int, void *))`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007270`
- `0x180007610`

## callees

- `0x180003c60`

## import_xrefs

- `ulib!?Initialize@MESSAGE@@QEAAEXZ` at `0x180003c84`

## pseudocode

```c
unsigned __int8 __fastcall FMIFS_CHKMSG::Initialize(
        FMIFS_CHKMSG *this,
        unsigned __int8 (__high *a2)(enum _FMIFS_PACKET_TYPE, unsigned int, void *))
{
  unsigned __int8 result; // al

  result = 0;
  *((_QWORD *)this + 16) = 2;
  *((_QWORD *)this + 17) = 0;
  *((_DWORD *)this + 30) = 0;
  *((_QWORD *)this + 13) = a2;
  *((_QWORD *)this + 14) = 0;
  if ( a2 )
    return MESSAGE::Initialize((MESSAGE *)this);
  return result;
}

```

## disassembly

```asm
0x180003c60  xor     eax, eax
0x180003c62  mov     qword ptr [rcx+80h], 2
0x180003c6d  mov     [rcx+88h], rax
0x180003c74  mov     [rcx+78h], eax
0x180003c77  mov     [rcx+68h], rdx
0x180003c7b  mov     [rcx+70h], rax
0x180003c7f  test    rdx, rdx
0x180003c82  jz      short locret_180003C8B
0x180003c84  jmp     cs:__imp_?Initialize@MESSAGE@@QEAAEXZ; MESSAGE::Initialize(void)
0x180003c8b  retn
```
