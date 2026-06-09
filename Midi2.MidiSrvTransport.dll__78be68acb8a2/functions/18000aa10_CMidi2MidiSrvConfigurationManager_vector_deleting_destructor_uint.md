# CMidi2MidiSrvConfigurationManager::`vector deleting destructor'(uint)

- ea: `0x18000aa10`
- end: `0x18000aa78`
- name: `??_ECMidi2MidiSrvConfigurationManager@@UEAAPEAXI@Z`
- size: `104`
- prototype: `void *__fastcall(CMidi2MidiSrvConfigurationManager *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callees

- `0x180002494`
- `0x18000aa10`
- `0x18000d190`

## pseudocode

```c
CMidi2MidiSrvConfigurationManager *__fastcall CMidi2MidiSrvConfigurationManager::`vector deleting destructor'(
        CMidi2MidiSrvConfigurationManager *this,
        char a2)
{
  CMidiXProc **v2; // rdi
  CMidiXProc *v5; // rsi

  v2 = (CMidiXProc **)*((_QWORD *)this + 3);
  if ( v2 )
  {
    v5 = v2[2];
    if ( v5 )
    {
      CMidiXProc::~CMidiXProc(v2[2]);
      operator delete(v5);
    }
    operator delete(v2);
  }
  *((_DWORD *)this + 5) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000aa10  push    rbx
0x18000aa12  push    rbp
0x18000aa13  push    rsi
0x18000aa14  push    rdi
0x18000aa15  sub     rsp, 28h
0x18000aa19  mov     rdi, [rcx+18h]
0x18000aa1d  mov     ebp, edx
0x18000aa1f  mov     rbx, rcx
0x18000aa22  test    rdi, rdi
0x18000aa25  jz      short loc_18000AA52
0x18000aa27  mov     rsi, [rdi+10h]
0x18000aa2b  test    rsi, rsi
0x18000aa2e  jz      short loc_18000AA45
0x18000aa30  mov     rcx, rsi; this
0x18000aa33  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x18000aa38  mov     edx, 90h
0x18000aa3d  mov     rcx, rsi; Block
0x18000aa40  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000aa45  mov     edx, 20h ; ' '
0x18000aa4a  mov     rcx, rdi; Block
0x18000aa4d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000aa52  mov     dword ptr [rbx+14h], 0C0000001h
0x18000aa59  test    bpl, 1
0x18000aa5d  jz      short loc_18000AA6C
0x18000aa5f  mov     edx, 38h ; '8'
0x18000aa64  mov     rcx, rbx; Block
0x18000aa67  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000aa6c  mov     rax, rbx
0x18000aa6f  add     rsp, 28h
0x18000aa73  pop     rdi
0x18000aa74  pop     rsi
0x18000aa75  pop     rbp
0x18000aa76  pop     rbx
0x18000aa77  retn
```
