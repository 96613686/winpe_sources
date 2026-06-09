# CBrowserCap::CBrowserCap(void)

- ea: `0x180007358`
- end: `0x1800073cf`
- name: `??0CBrowserCap@@QEAA@XZ`
- size: `119`
- prototype: `CBrowserCap *__fastcall(CBrowserCap *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800039c4`
- `0x180003b20`
- `0x180007968`
- `0x180008fa8`

## callees

- `0x1800037f4`
- `0x180004480`
- `0x180007358`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CBrowserCap *__fastcall CBrowserCap::CBrowserCap(CBrowserCap *this)
{
  char *v2; // rcx
  int v3; // eax

  *((_DWORD *)this + 4) = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_BYTE *)this + 64) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 11) = 0;
  v2 = (char *)this + 104;
  *(_OWORD *)v2 = 0;
  *((_OWORD *)v2 + 1) = 0;
  *((_QWORD *)v2 + 4) = 0;
  v3 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)v2);
  if ( v3 < 0 )
    ATL::AtlThrowImpl(v3);
  return this;
}

```

## disassembly

```asm
0x180007358  mov     [rsp+arg_0], rcx
0x18000735d  push    rbx
0x18000735e  sub     rsp, 20h
0x180007362  mov     rbx, rcx
0x180007365  mov     dword ptr [rcx+10h], 0
0x18000736c  xorps   xmm0, xmm0
0x18000736f  xor     eax, eax
0x180007371  movups  xmmword ptr [rcx+18h], xmm0
0x180007375  movups  xmmword ptr [rcx+28h], xmm0
0x180007379  mov     [rcx+38h], rax
0x18000737d  mov     [rcx+40h], al
0x180007380  mov     [rcx+48h], rax
0x180007384  lea     rax, [rcx+50h]
0x180007388  mov     [rsp+28h+arg_8], rax
0x18000738d  mov     qword ptr [rax], 0
0x180007394  mov     qword ptr [rax+10h], 0
0x18000739c  mov     qword ptr [rax+8], 0
0x1800073a4  lea     rcx, [rax+18h]; this
0x1800073a8  xor     eax, eax
0x1800073aa  movups  xmmword ptr [rcx], xmm0
0x1800073ad  movups  xmmword ptr [rcx+10h], xmm0
0x1800073b1  mov     [rcx+20h], rax
0x1800073b5  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800073ba  test    eax, eax
0x1800073bc  js      short loc_1800073C7
0x1800073be  mov     rax, rbx
0x1800073c1  add     rsp, 20h
0x1800073c5  pop     rbx
0x1800073c6  retn
0x1800073c7  mov     ecx, eax; int
0x1800073c9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
