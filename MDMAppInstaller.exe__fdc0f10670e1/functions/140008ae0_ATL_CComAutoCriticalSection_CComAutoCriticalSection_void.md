# ATL::CComAutoCriticalSection::CComAutoCriticalSection(void)

- ea: `0x140008ae0`
- end: `0x140008b13`
- name: `??0CComAutoCriticalSection@ATL@@QEAA@XZ`
- size: `51`
- prototype: `ATL::CComAutoCriticalSection *__fastcall(ATL::CComAutoCriticalSection *this)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001a20`
- `0x140001b80`
- `0x140015ff8`

## callees

- `0x140008ae0`
- `0x140009f58`
- `0x14000dbcc`

## pseudocode

```c
ATL::CComAutoCriticalSection *__fastcall ATL::CComAutoCriticalSection::CComAutoCriticalSection(
        ATL::CComAutoCriticalSection *this)
{
  int v2; // eax

  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_QWORD *)this + 4) = 0;
  v2 = ATL::CComCriticalSection::Init(this);
  if ( v2 < 0 )
    ATL::AtlThrowImpl(v2);
  return this;
}

```

## disassembly

```asm
0x140008ae0  push    rbx
0x140008ae2  sub     rsp, 20h
0x140008ae6  xorps   xmm0, xmm0
0x140008ae9  xor     eax, eax
0x140008aeb  movups  xmmword ptr [rcx], xmm0
0x140008aee  mov     rbx, rcx
0x140008af1  movups  xmmword ptr [rcx+10h], xmm0
0x140008af5  mov     [rcx+20h], rax
0x140008af9  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140008afe  test    eax, eax
0x140008b00  jns     short loc_140008B0A
0x140008b02  mov     ecx, eax; int
0x140008b04  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140008b0a  mov     rax, rbx
0x140008b0d  add     rsp, 20h
0x140008b11  pop     rbx
0x140008b12  retn
```
