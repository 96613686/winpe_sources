# CAxInstaller::CAxInstaller(void)

- ea: `0x180005cec`
- end: `0x180005d9d`
- name: `??0CAxInstaller@@QEAA@XZ`
- size: `177`
- prototype: `CAxInstaller *__fastcall(CAxInstaller *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000a4e4`
- `0x18000a600`

## callees

- `0x180003208`
- `0x180005cec`
- `0x1800069ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CAxInstaller *__fastcall CAxInstaller::CAxInstaller(CAxInstaller *this)
{
  char *v2; // rcx
  int v3; // eax

  *((_DWORD *)this + 4) = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_BYTE *)this + 64) = 0;
  v2 = (char *)this + 592;
  *(_OWORD *)v2 = 0;
  *((_OWORD *)v2 + 1) = 0;
  *((_QWORD *)v2 + 4) = 0;
  v3 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)v2);
  if ( v3 < 0 )
    ATL::AtlThrowImpl(v3);
  *((_QWORD *)this + 79) = 0;
  *((_QWORD *)this + 80) = 0;
  *((_QWORD *)this + 81) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_DWORD *)this + 166) = -1;
  *((_WORD *)this + 36) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 89) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_DWORD *)this + 168) = 0;
  *((_DWORD *)this + 176) = 0;
  return this;
}

```

## disassembly

```asm
0x180005cec  mov     [rsp+arg_0], rcx
0x180005cf1  push    rbx
0x180005cf2  sub     rsp, 20h
0x180005cf6  mov     rbx, rcx
0x180005cf9  mov     dword ptr [rcx+10h], 0
0x180005d00  xorps   xmm0, xmm0
0x180005d03  xor     eax, eax
0x180005d05  movups  xmmword ptr [rcx+18h], xmm0
0x180005d09  movups  xmmword ptr [rcx+28h], xmm0
0x180005d0d  mov     [rcx+38h], rax
0x180005d11  mov     [rcx+40h], al
0x180005d14  add     rcx, 250h; this
0x180005d1b  movups  xmmword ptr [rcx], xmm0
0x180005d1e  movups  xmmword ptr [rcx+10h], xmm0
0x180005d22  mov     [rcx+20h], rax
0x180005d26  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180005d2b  test    eax, eax
0x180005d2d  jns     short loc_180005D37
0x180005d2f  mov     ecx, eax; int
0x180005d31  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005d37  mov     qword ptr [rbx+278h], 0
0x180005d42  mov     qword ptr [rbx+280h], 0
0x180005d4d  mov     qword ptr [rbx+288h], 0
0x180005d58  mov     qword ptr [rbx+290h], 0
0x180005d63  mov     dword ptr [rbx+298h], 0FFFFFFFFh
0x180005d6d  xor     eax, eax
0x180005d6f  mov     [rbx+48h], ax
0x180005d73  mov     [rbx+2A8h], rax
0x180005d7a  mov     [rbx+2C8h], rax
0x180005d81  mov     [rbx+2B8h], rax
0x180005d88  mov     [rbx+2A0h], eax
0x180005d8e  mov     [rbx+2C0h], eax
0x180005d94  mov     rax, rbx
0x180005d97  add     rsp, 20h
0x180005d9b  pop     rbx
0x180005d9c  retn
```
