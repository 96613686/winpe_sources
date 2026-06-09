# _anonymous_namespace_::ActionEvent::CopyData

- ea: `0x18001a090`
- end: `0x18001a12c`
- name: `_anonymous_namespace_::ActionEvent::CopyData`
- size: `156`
- prototype: `__int64 __fastcall(Action *, struct _TASK_ACTION **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c9e0`
- `0x18000e970`
- `0x18001a040`
- `0x18001a090`
- `0x18001a378`

## import_xrefs

- `msvcrt!malloc` at `0x18001a0b3`
- `msvcrt!malloc` at `0x18001a0b3`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::ActionEvent::CopyData(Action *a1, struct _TASK_ACTION **a2)
{
  int v4; // eax
  struct _TASK_ACTION *v5; // rdi
  int v6; // ebx
  _QWORD *v7; // rax
  __int64 v8; // rcx
  unsigned __int16 *v9; // rcx

  v4 = Action::CopyData(a1, a2);
  v5 = *a2;
  v6 = v4;
  if ( *a2 )
  {
    v7 = malloc(0x10u);
    *((_QWORD *)v5 + 1) = v7;
    if ( !v7 )
    {
      if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v8, MemoryAllocationError, 16);
      goto LABEL_5;
    }
    v7[1] = 0;
    v9 = (unsigned __int16 *)*((_QWORD *)a1 + 21);
    if ( v9 )
    {
      *(_QWORD *)(*((_QWORD *)v5 + 1) + 8LL) = StrDup(v9);
      if ( !*(_QWORD *)(*((_QWORD *)v5 + 1) + 8LL) )
      {
LABEL_5:
        v6 = -2147024882;
LABEL_9:
        Action::FreeData((void ***)v5);
        *a2 = 0;
        return (unsigned int)v6;
      }
    }
  }
  if ( v6 < 0 )
    goto LABEL_9;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001a090  push    rbx
0x18001a092  push    rbp
0x18001a093  push    rsi
0x18001a094  push    rdi
0x18001a095  sub     rsp, 28h
0x18001a099  mov     rsi, rdx
0x18001a09c  mov     rbp, rcx
0x18001a09f  call    ?CopyData@Action@@UEAAJPEAPEAU_TASK_ACTION@@@Z; Action::CopyData(_TASK_ACTION * *)
0x18001a0a4  mov     rdi, [rsi]
0x18001a0a7  mov     ebx, eax
0x18001a0a9  test    rdi, rdi
0x18001a0ac  jz      short loc_18001A10E
0x18001a0ae  mov     ecx, 10h; Size
0x18001a0b3  call    cs:__imp_malloc
0x18001a0b9  mov     [rdi+8], rax
0x18001a0bd  test    rax, rax
0x18001a0c0  jnz     short loc_18001A0E2
0x18001a0c2  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 2
0x18001a0c9  jz      short loc_18001A0DB
0x18001a0cb  lea     r8d, [rax+10h]
0x18001a0cf  lea     rdx, MemoryAllocationError
0x18001a0d6  call    McTemplateU0q_EventWriteTransfer
0x18001a0db  mov     ebx, 8007000Eh
0x18001a0e0  jmp     short loc_18001A112
0x18001a0e2  mov     qword ptr [rax+8], 0
0x18001a0ea  mov     rcx, [rbp+0A8h]; Src
0x18001a0f1  test    rcx, rcx
0x18001a0f4  jz      short loc_18001A10E
0x18001a0f6  call    ?StrDup@@YAPEAGPEAG@Z; StrDup(ushort *)
0x18001a0fb  mov     rcx, [rdi+8]
0x18001a0ff  mov     [rcx+8], rax
0x18001a103  mov     rax, [rdi+8]
0x18001a107  cmp     qword ptr [rax+8], 0
0x18001a10c  jz      short loc_18001A0DB
0x18001a10e  test    ebx, ebx
0x18001a110  jns     short loc_18001A121
0x18001a112  mov     rcx, rdi; Block
0x18001a115  call    ?FreeData@Action@@SAJPEAU_TASK_ACTION@@@Z; Action::FreeData(_TASK_ACTION *)
0x18001a11a  mov     qword ptr [rsi], 0
0x18001a121  mov     eax, ebx
0x18001a123  add     rsp, 28h
0x18001a127  pop     rdi
0x18001a128  pop     rsi
0x18001a129  pop     rbp
0x18001a12a  pop     rbx
0x18001a12b  retn
```
