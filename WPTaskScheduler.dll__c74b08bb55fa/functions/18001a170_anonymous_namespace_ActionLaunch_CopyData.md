# _anonymous_namespace_::ActionLaunch::CopyData

- ea: `0x18001a170`
- end: `0x18001a245`
- name: `_anonymous_namespace_::ActionLaunch::CopyData`
- size: `213`
- prototype: `__int64 __fastcall(Action *, struct _TASK_ACTION **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000c9e0`
- `0x18000e970`
- `0x18001a040`
- `0x18001a170`
- `0x18001a378`

## import_xrefs

- `msvcrt!malloc` at `0x18001a198`
- `msvcrt!malloc` at `0x18001a198`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::ActionLaunch::CopyData(Action *a1, struct _TASK_ACTION **a2)
{
  int v4; // eax
  struct _TASK_ACTION *v5; // rdi
  int v6; // ebx
  _QWORD *v7; // rax
  __int64 v8; // rcx
  unsigned __int16 *v9; // rcx
  unsigned __int16 *v10; // rcx

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
    *v7 = 0;
    *(_QWORD *)(*((_QWORD *)v5 + 1) + 8LL) = 0;
    v9 = (unsigned __int16 *)*((_QWORD *)a1 + 20);
    if ( v9 )
    {
      **((_QWORD **)v5 + 1) = StrDup(v9);
      if ( !**((_QWORD **)v5 + 1) )
        goto LABEL_5;
    }
    if ( v6 < 0 )
      goto LABEL_13;
    v10 = (unsigned __int16 *)*((_QWORD *)a1 + 21);
    if ( v10 )
    {
      *(_QWORD *)(*((_QWORD *)v5 + 1) + 8LL) = StrDup(v10);
      if ( !*(_QWORD *)(*((_QWORD *)v5 + 1) + 8LL) )
      {
LABEL_5:
        v6 = -2147024882;
LABEL_13:
        Action::FreeData(v5);
        *a2 = 0;
      }
    }
  }
  else if ( v4 < 0 )
  {
    goto LABEL_13;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001a170  push    rbx
0x18001a172  push    rsi
0x18001a173  push    rdi
0x18001a174  push    r14
0x18001a176  sub     rsp, 28h
0x18001a17a  mov     r14, rdx
0x18001a17d  mov     rsi, rcx
0x18001a180  call    ?CopyData@Action@@UEAAJPEAPEAU_TASK_ACTION@@@Z; Action::CopyData(_TASK_ACTION * *)
0x18001a185  mov     rdi, [r14]
0x18001a188  mov     ebx, eax
0x18001a18a  test    rdi, rdi
0x18001a18d  jz      loc_18001A226
0x18001a193  mov     ecx, 10h; Size
0x18001a198  call    cs:__imp_malloc
0x18001a19e  mov     [rdi+8], rax
0x18001a1a2  test    rax, rax
0x18001a1a5  jnz     short loc_18001A1C7
0x18001a1a7  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 2
0x18001a1ae  jz      short loc_18001A1C0
0x18001a1b0  lea     r8d, [rax+10h]
0x18001a1b4  lea     rdx, MemoryAllocationError
0x18001a1bb  call    McTemplateU0q_EventWriteTransfer
0x18001a1c0  mov     ebx, 8007000Eh
0x18001a1c5  jmp     short loc_18001A22A
0x18001a1c7  mov     qword ptr [rax], 0
0x18001a1ce  mov     rax, [rdi+8]
0x18001a1d2  mov     qword ptr [rax+8], 0
0x18001a1da  mov     rcx, [rsi+0A0h]; Src
0x18001a1e1  test    rcx, rcx
0x18001a1e4  jz      short loc_18001A1FC
0x18001a1e6  call    ?StrDup@@YAPEAGPEAG@Z; StrDup(ushort *)
0x18001a1eb  mov     rcx, [rdi+8]
0x18001a1ef  mov     [rcx], rax
0x18001a1f2  mov     rax, [rdi+8]
0x18001a1f6  cmp     qword ptr [rax], 0
0x18001a1fa  jz      short loc_18001A1C0
0x18001a1fc  test    ebx, ebx
0x18001a1fe  js      short loc_18001A22A
0x18001a200  mov     rcx, [rsi+0A8h]; Src
0x18001a207  test    rcx, rcx
0x18001a20a  jz      short loc_18001A239
0x18001a20c  call    ?StrDup@@YAPEAGPEAG@Z; StrDup(ushort *)
0x18001a211  mov     rcx, [rdi+8]
0x18001a215  mov     [rcx+8], rax
0x18001a219  mov     rax, [rdi+8]
0x18001a21d  cmp     qword ptr [rax+8], 0
0x18001a222  jnz     short loc_18001A239
0x18001a224  jmp     short loc_18001A1C0
0x18001a226  test    ebx, ebx
0x18001a228  jns     short loc_18001A239
0x18001a22a  mov     rcx, rdi; Block
0x18001a22d  call    ?FreeData@Action@@SAJPEAU_TASK_ACTION@@@Z; Action::FreeData(_TASK_ACTION *)
0x18001a232  mov     qword ptr [r14], 0
0x18001a239  mov     eax, ebx
0x18001a23b  add     rsp, 28h
0x18001a23f  pop     r14
0x18001a241  pop     rdi
0x18001a242  pop     rsi
0x18001a243  pop     rbx
0x18001a244  retn
```
