# NDFRepairExecutionClosure::~NDFRepairExecutionClosure(void)

- ea: `0x18000c3c8`
- end: `0x18000c3f2`
- name: `??1NDFRepairExecutionClosure@@UEAA@XZ`
- size: `42`
- prototype: `void __fastcall(NDFRepairExecutionClosure *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180008140`
- `0x18000c770`
- `0x18001094e`

## callees

- `0x18000c3c8`

## pseudocode

```c
void __fastcall NDFRepairExecutionClosure::~NDFRepairExecutionClosure(NDFRepairExecutionClosure *this)
{
  _DWORD *v1; // rax

  v1 = (_DWORD *)*((_QWORD *)this + 3);
  if ( *((_DWORD *)this + 10) )
    *v1 = 1;
  else
    *v1 = 2;
  **((_DWORD **)this + 2) = 0;
  *(_QWORD *)this = &Visitor<tagRepairInfo *>::`vftable';
}

```

## disassembly

```asm
0x18000c3c8  mov     rax, [rcx+18h]
0x18000c3cc  xor     edx, edx
0x18000c3ce  cmp     [rcx+28h], edx
0x18000c3d1  jz      short loc_18000C3DB
0x18000c3d3  mov     dword ptr [rax], 1
0x18000c3d9  jmp     short loc_18000C3E1
0x18000c3db  mov     dword ptr [rax], 2
0x18000c3e1  mov     rax, [rcx+10h]
0x18000c3e5  mov     [rax], edx
0x18000c3e7  lea     rax, ??_7?$Visitor@PEAUtagRepairInfo@@@@6B@; const Visitor<tagRepairInfo *>::`vftable'
0x18000c3ee  mov     [rcx], rax
0x18000c3f1  retn
```
