# Repair::Repair(ushort *,_GUID)

- ea: `0x18000f970`
- end: `0x18000f9d0`
- name: `??0Repair@@QEAA@PEAGU_GUID@@@Z`
- size: `96`
- prototype: `Repair *(Repair *__hidden this, unsigned __int16 *, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180002974`

## callees

- `0x18000d374`
- `0x18000e594`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Repair *__fastcall Repair::Repair(Repair *this, unsigned __int16 *a2, struct _GUID *a3)
{
  AttributeList::AttributeList((Repair *)((char *)this + 8));
  *(_QWORD *)this = &Repair::`vftable';
  *((_QWORD *)this + 4) = 0;
  *(struct _GUID *)((char *)this + 40) = *a3;
  AllocateAndLoadString((unsigned __int16 **)this + 4, a2);
  return this;
}

```

## disassembly

```asm
0x18000f970  mov     [rsp+arg_8], rbx
0x18000f975  mov     [rsp+arg_10], rsi
0x18000f97a  mov     [rsp+arg_0], rcx
0x18000f97f  push    rdi
0x18000f980  sub     rsp, 20h
0x18000f984  mov     rbx, r8
0x18000f987  mov     rdi, rdx
0x18000f98a  mov     rsi, rcx
0x18000f98d  add     rcx, 8; this
0x18000f991  call    ??0AttributeList@@QEAA@XZ; AttributeList::AttributeList(void)
0x18000f996  nop
0x18000f997  lea     rax, ??_7Repair@@6B@; const Repair::`vftable'
0x18000f99e  mov     [rsi], rax
0x18000f9a1  lea     rcx, [rsi+20h]; unsigned __int16 **
0x18000f9a5  mov     qword ptr [rcx], 0
0x18000f9ac  movaps  xmm0, xmmword ptr [rbx]
0x18000f9af  movdqu  xmmword ptr [rsi+28h], xmm0
0x18000f9b4  mov     rdx, rdi; unsigned __int16 *
0x18000f9b7  call    ?AllocateAndLoadString@@YAXPEAPEAGPEAG@Z; AllocateAndLoadString(ushort * *,ushort *)
0x18000f9bc  nop
0x18000f9bd  mov     rax, rsi
0x18000f9c0  mov     rbx, [rsp+28h+arg_8]
0x18000f9c5  mov     rsi, [rsp+28h+arg_10]
0x18000f9ca  add     rsp, 20h
0x18000f9ce  pop     rdi
0x18000f9cf  retn
```
