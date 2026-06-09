# CLogMgr::CreateInstance2(CLogMgr * *,IUnknown *)

- ea: `0x1800062a0`
- end: `0x1800062fa`
- name: `?CreateInstance2@CLogMgr@@SAJPEAPEAV1@PEAUIUnknown@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(struct CLogMgr **, struct IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008890`

## callees

- `0x1800012c0`
- `0x180005d78`
- `0x1800062a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLogMgr::CreateInstance2(struct CLogMgr **a1, struct IUnknown *a2)
{
  CLogMgr *v3; // rax
  unsigned int v4; // edx
  unsigned int v5; // edx

  if ( a2 )
  {
    v3 = (CLogMgr *)operator new(0x290u);
    if ( v3 )
      v3 = CLogMgr::CLogMgr(v3, v4);
  }
  else
  {
    v3 = (CLogMgr *)operator new(0x290u);
    if ( v3 )
      v3 = CLogMgr::CLogMgr(v3, v5);
  }
  *a1 = v3;
  return v3 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x1800062a0  push    rbx
0x1800062a2  sub     rsp, 20h
0x1800062a6  mov     rbx, rcx
0x1800062a9  mov     ecx, 290h; Size
0x1800062ae  test    rdx, rdx
0x1800062b1  jz      short loc_1800062CD
0x1800062b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800062b8  mov     [rsp+28h+arg_0], rax
0x1800062bd  test    rax, rax
0x1800062c0  jz      short loc_1800062CB
0x1800062c2  mov     rcx, rax; this
0x1800062c5  call    ??0CLogMgr@@QEAA@XZ; CLogMgr::CLogMgr(void)
0x1800062ca  nop
0x1800062cb  jmp     short loc_1800062E5
0x1800062cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800062d2  mov     [rsp+28h+arg_0], rax
0x1800062d7  test    rax, rax
0x1800062da  jz      short loc_1800062E5
0x1800062dc  mov     rcx, rax; this
0x1800062df  call    ??0CLogMgr@@QEAA@XZ; CLogMgr::CLogMgr(void)
0x1800062e4  nop
0x1800062e5  mov     [rbx], rax
0x1800062e8  neg     rax
0x1800062eb  sbb     eax, eax
0x1800062ed  not     eax
0x1800062ef  and     eax, 8007000Eh
0x1800062f4  add     rsp, 20h
0x1800062f8  pop     rbx
0x1800062f9  retn
```
