# CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)

- ea: `0x180007ea0`
- end: `0x180007ee4`
- name: `??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z`
- size: `68`
- prototype: `CLogETWBlock *__fastcall(CLogETWBlock *__hidden this, const char *, int *, int *, unsigned int *)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000caa0`
- `0x18000d51c`
- `0x180013620`
- `0x1800136b0`
- `0x1800137d0`
- `0x180013860`
- `0x180013940`
- `0x180013a30`
- `0x180013ac0`
- `0x180013b50`
- `0x180013ec8`
- `0x180014088`
- `0x180014510`
- `0x180014750`
- `0x1800148fc`
- `0x180014c2c`
- `0x1800157d4`
- `0x180015c94`
- `0x18001640c`
- `0x1800167c8`
- `0x180016b9c`

## callees

- `0x180007d20`
- `0x180007ea0`

## pseudocode

```c
CLogETWBlock *__fastcall CLogETWBlock::CLogETWBlock(
        CLogETWBlock *this,
        const char *a2,
        int *a3,
        int *a4,
        unsigned int *a5)
{
  *((_QWORD *)this + 3) = a5;
  *(_QWORD *)this = a2;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = a4;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(this, Func_Start, a2);
  return this;
}

```

## disassembly

```asm
0x180007ea0  push    rbx
0x180007ea2  sub     rsp, 20h
0x180007ea6  mov     rax, [rsp+28h+arg_20]
0x180007eab  mov     rbx, rcx
0x180007eae  mov     [rcx+18h], rax
0x180007eb2  mov     [rcx], rdx
0x180007eb5  mov     qword ptr [rcx+8], 0
0x180007ebd  mov     [rcx+10h], r9
0x180007ec1  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x180007ec8  jnz     short loc_180007ED3
0x180007eca  mov     rax, rbx
0x180007ecd  add     rsp, 20h
0x180007ed1  pop     rbx
0x180007ed2  retn
0x180007ed3  mov     r8, rdx
0x180007ed6  lea     rdx, Func_Start
0x180007edd  call    McTemplateU0s_EtwEventWriteTransfer
0x180007ee2  jmp     short loc_180007ECA
```
