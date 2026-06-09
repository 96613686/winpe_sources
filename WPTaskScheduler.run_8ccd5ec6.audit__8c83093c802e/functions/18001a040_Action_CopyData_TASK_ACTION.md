# Action::CopyData(_TASK_ACTION * *)

- ea: `0x18001a040`
- end: `0x18001a088`
- name: `?CopyData@Action@@UEAAJPEAPEAU_TASK_ACTION@@@Z`
- size: `72`
- prototype: `__int64 __fastcall(Action *__hidden this, struct _TASK_ACTION **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18001a090`
- `0x18001a170`
- `0x18001a250`

## callees

- `0x18001a040`

## import_xrefs

- `msvcrt!malloc` at `0x18001a061`
- `msvcrt!malloc` at `0x18001a061`

## pseudocode

```c
__int64 __fastcall Action::CopyData(Action *this, struct _TASK_ACTION **a2)
{
  struct _TASK_ACTION *v5; // rax

  if ( !a2 )
    return 2147500035LL;
  v5 = (struct _TASK_ACTION *)malloc(0x10u);
  if ( !v5 )
    return 2147942414LL;
  *(_DWORD *)v5 = *((_DWORD *)this + 18);
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x18001a040  mov     [rsp+arg_0], rbx
0x18001a045  push    rdi
0x18001a046  sub     rsp, 20h
0x18001a04a  mov     rbx, rdx
0x18001a04d  mov     rdi, rcx
0x18001a050  test    rdx, rdx
0x18001a053  jnz     short loc_18001A05C
0x18001a055  mov     eax, 80004003h
0x18001a05a  jmp     short loc_18001A07D
0x18001a05c  mov     ecx, 10h; Size
0x18001a061  call    cs:__imp_malloc
0x18001a067  test    rax, rax
0x18001a06a  jz      short loc_18001A078
0x18001a06c  mov     ecx, [rdi+48h]
0x18001a06f  mov     [rax], ecx
0x18001a071  mov     [rbx], rax
0x18001a074  xor     eax, eax
0x18001a076  jmp     short loc_18001A07D
0x18001a078  mov     eax, 8007000Eh
0x18001a07d  mov     rbx, [rsp+28h+arg_0]
0x18001a082  add     rsp, 20h
0x18001a086  pop     rdi
0x18001a087  retn
```
