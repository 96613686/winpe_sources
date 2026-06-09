# CVideoObject::Clean(void)

- ea: `0x18001953c`
- end: `0x1800195c0`
- name: `?Clean@CVideoObject@@QEAAXXZ`
- size: `132`
- prototype: `void __fastcall(CVideoObject *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001863c`
- `0x180018f04`
- `0x18002ebbc`
- `0x180037980`

## callees

- `0x18001953c`
- `0x18002aae4`
- `0x18002ee08`

## pseudocode

```c
void __fastcall CVideoObject::Clean(CVideoObject *this, unsigned int a2)
{
  CPictureCYUV420 *v3; // rcx
  CPictureCYUV420 *v4; // rcx
  CPictureCYUV420 *v5; // rcx
  void *v6; // rcx

  v3 = (CPictureCYUV420 *)*((_QWORD *)this + 146);
  if ( v3 )
    CPictureCYUV420::`scalar deleting destructor'(v3, a2);
  v4 = (CPictureCYUV420 *)*((_QWORD *)this + 147);
  *((_QWORD *)this + 146) = 0;
  if ( v4 )
  {
    CPictureCYUV420::`scalar deleting destructor'(v4, a2);
    *((_QWORD *)this + 147) = 0;
  }
  v5 = (CPictureCYUV420 *)*((_QWORD *)this + 148);
  if ( v5 )
  {
    CPictureCYUV420::`scalar deleting destructor'(v5, a2);
    *((_QWORD *)this + 148) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 144);
  if ( v6 )
    operator delete(v6);
  *((_QWORD *)this + 144) = 0;
}

```

## disassembly

```asm
0x18001953c  push    rbx
0x18001953e  sub     rsp, 20h
0x180019542  mov     rbx, rcx
0x180019545  mov     rcx, [rcx+490h]; this
0x18001954c  test    rcx, rcx
0x18001954f  jz      short loc_180019556
0x180019551  call    ??_GCPictureCYUV420@@QEAAPEAXI@Z; CPictureCYUV420::`scalar deleting destructor'(uint)
0x180019556  mov     rcx, [rbx+498h]; this
0x18001955d  mov     qword ptr [rbx+490h], 0
0x180019568  test    rcx, rcx
0x18001956b  jz      short loc_18001957D
0x18001956d  call    ??_GCPictureCYUV420@@QEAAPEAXI@Z; CPictureCYUV420::`scalar deleting destructor'(uint)
0x180019572  mov     qword ptr [rbx+498h], 0
0x18001957d  mov     rcx, [rbx+4A0h]; this
0x180019584  test    rcx, rcx
0x180019587  jz      short loc_180019599
0x180019589  call    ??_GCPictureCYUV420@@QEAAPEAXI@Z; CPictureCYUV420::`scalar deleting destructor'(uint)
0x18001958e  mov     qword ptr [rbx+4A0h], 0
0x180019599  mov     rcx, [rbx+480h]; Block
0x1800195a0  test    rcx, rcx
0x1800195a3  jz      short loc_1800195AF
0x1800195a5  mov     edx, 70h ; 'p'
0x1800195aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800195af  mov     qword ptr [rbx+480h], 0
0x1800195ba  add     rsp, 20h
0x1800195be  pop     rbx
0x1800195bf  retn
```
