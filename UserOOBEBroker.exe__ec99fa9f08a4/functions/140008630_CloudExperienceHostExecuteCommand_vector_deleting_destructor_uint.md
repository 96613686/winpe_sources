# CloudExperienceHostExecuteCommand::`vector deleting destructor'(uint)

- ea: `0x140008630`
- end: `0x140008679`
- name: `??_ECloudExperienceHostExecuteCommand@@UEAAPEAXI@Z`
- size: `73`
- prototype: `void *__fastcall(CloudExperienceHostExecuteCommand *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140008630`
- `0x14000f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140008665`
- `msvcrt!??3@YAXPEAX@Z` at `0x140008665`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CloudExperienceHostExecuteCommand *__fastcall CloudExperienceHostExecuteCommand::`vector deleting destructor'(
        CloudExperienceHostExecuteCommand *this,
        char a2)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 3);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  *((_DWORD *)this + 5) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140008630  mov     [rsp+arg_0], rbx
0x140008635  push    rdi
0x140008636  sub     rsp, 20h
0x14000863a  mov     edi, edx
0x14000863c  mov     rbx, rcx
0x14000863f  mov     rcx, [rcx+18h]
0x140008643  test    rcx, rcx
0x140008646  jz      short loc_140008655
0x140008648  mov     rax, [rcx]
0x14000864b  mov     rax, [rax+10h]
0x14000864f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008654  nop
0x140008655  mov     dword ptr [rbx+14h], 0C0000001h
0x14000865c  test    dil, 1
0x140008660  jz      short loc_14000866B
0x140008662  mov     rcx, rbx
0x140008665  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000866b  mov     rax, rbx
0x14000866e  mov     rbx, [rsp+28h+arg_0]
0x140008673  add     rsp, 20h
0x140008677  pop     rdi
0x140008678  retn
```
