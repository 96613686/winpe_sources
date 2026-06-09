# _anonymous_namespace_::ActionWNF::CopyData

- ea: `0x18001a250`
- end: `0x18001a313`
- name: `_anonymous_namespace_::ActionWNF::CopyData`
- size: `195`
- prototype: `__int64 __fastcall(__int64, struct _TASK_ACTION **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000cc50`
- `0x18000e970`
- `0x18001a040`
- `0x18001a250`
- `0x18001a378`

## import_xrefs

- `msvcrt!malloc` at `0x18001a278`
- `msvcrt!malloc` at `0x18001a278`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::ActionWNF::CopyData(__int64 a1, struct _TASK_ACTION **a2)
{
  int v4; // eax
  struct _TASK_ACTION *v5; // rdi
  int v6; // ebx
  _QWORD *v7; // rax
  __int64 v8; // rcx
  unsigned __int8 *v9; // rcx

  v4 = Action::CopyData((Action *)a1, a2);
  v5 = *a2;
  v6 = v4;
  if ( *a2 )
  {
    v7 = malloc(0x18u);
    *((_QWORD *)v5 + 1) = v7;
    if ( !v7 )
    {
      if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v8, MemoryAllocationError, 24);
      goto LABEL_5;
    }
    v7[2] = 0;
    *(_DWORD *)(*((_QWORD *)v5 + 1) + 8LL) = *(_DWORD *)(a1 + 168);
    **((_QWORD **)v5 + 1) = *(_QWORD *)(a1 + 160);
    v9 = *(unsigned __int8 **)(a1 + 176);
    if ( v9 )
    {
      *(_QWORD *)(*((_QWORD *)v5 + 1) + 16LL) = Duplicate(v9, *(unsigned int *)(a1 + 168));
      if ( !*(_QWORD *)(*((_QWORD *)v5 + 1) + 16LL) )
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
0x18001a250  push    rbx
0x18001a252  push    rsi
0x18001a253  push    rdi
0x18001a254  push    r14
0x18001a256  sub     rsp, 28h
0x18001a25a  mov     r14, rdx
0x18001a25d  mov     rsi, rcx
0x18001a260  call    ?CopyData@Action@@UEAAJPEAPEAU_TASK_ACTION@@@Z; Action::CopyData(_TASK_ACTION * *)
0x18001a265  mov     rdi, [r14]
0x18001a268  mov     ebx, eax
0x18001a26a  test    rdi, rdi
0x18001a26d  jz      loc_18001A2F4
0x18001a273  mov     ecx, 18h; Size
0x18001a278  call    cs:__imp_malloc
0x18001a27e  mov     [rdi+8], rax
0x18001a282  test    rax, rax
0x18001a285  jnz     short loc_18001A2A7
0x18001a287  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 2
0x18001a28e  jz      short loc_18001A2A0
0x18001a290  lea     r8d, [rax+18h]
0x18001a294  lea     rdx, MemoryAllocationError
0x18001a29b  call    McTemplateU0q_EventWriteTransfer
0x18001a2a0  mov     ebx, 8007000Eh
0x18001a2a5  jmp     short loc_18001A2F8
0x18001a2a7  mov     qword ptr [rax+10h], 0
0x18001a2af  mov     rcx, [rdi+8]
0x18001a2b3  mov     eax, [rsi+0A8h]
0x18001a2b9  mov     [rcx+8], eax
0x18001a2bc  mov     rcx, [rdi+8]
0x18001a2c0  mov     rax, [rsi+0A0h]
0x18001a2c7  mov     [rcx], rax
0x18001a2ca  mov     rcx, [rsi+0B0h]; Src
0x18001a2d1  test    rcx, rcx
0x18001a2d4  jz      short loc_18001A2F4
0x18001a2d6  mov     edx, [rsi+0A8h]; Size
0x18001a2dc  call    ?Duplicate@@YAPEAEPEAE_K@Z; Duplicate(uchar *,unsigned __int64)
0x18001a2e1  mov     rcx, [rdi+8]
0x18001a2e5  mov     [rcx+10h], rax
0x18001a2e9  mov     rax, [rdi+8]
0x18001a2ed  cmp     qword ptr [rax+10h], 0
0x18001a2f2  jz      short loc_18001A2A0
0x18001a2f4  test    ebx, ebx
0x18001a2f6  jns     short loc_18001A307
0x18001a2f8  mov     rcx, rdi; Block
0x18001a2fb  call    ?FreeData@Action@@SAJPEAU_TASK_ACTION@@@Z; Action::FreeData(_TASK_ACTION *)
0x18001a300  mov     qword ptr [r14], 0
0x18001a307  mov     eax, ebx
0x18001a309  add     rsp, 28h
0x18001a30d  pop     r14
0x18001a30f  pop     rdi
0x18001a310  pop     rsi
0x18001a311  pop     rbx
0x18001a312  retn
```
