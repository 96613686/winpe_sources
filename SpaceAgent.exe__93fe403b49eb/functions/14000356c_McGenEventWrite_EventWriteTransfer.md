# McGenEventWrite_EventWriteTransfer

- ea: `0x14000356c`
- end: `0x1400035b9`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x1400035c0`
- `0x140009924`
- `0x14000b828`
- `0x14000b934`
- `0x14000ba08`
- `0x14000bb78`
- `0x14000f6f8`
- `0x14000f818`
- `0x14000f8fc`
- `0x14000fa50`
- `0x1400137e8`
- `0x140013914`
- `0x140013a08`
- `0x140013b54`

## callees

- `0x14000356c`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x1400035ae`
- `ADVAPI32!EventWriteTransfer` at `0x1400035ae`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        REGHANDLE *a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    UserData->Ptr = (ULONGLONG)v5;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EventWriteTransfer(*a1, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x14000356c  sub     rsp, 38h
0x140003570  mov     r8, [rcx+8]
0x140003574  mov     rax, [rsp+38h+arg_20]
0x140003579  test    r8, r8
0x14000357c  jnz     short loc_140003586
0x14000357e  mov     [rax], r8
0x140003581  xor     r10d, r10d
0x140003584  jmp     short loc_140003593
0x140003586  mov     [rax], r8
0x140003589  mov     r10d, 2
0x14000358f  movzx   r8d, word ptr [r8]
0x140003593  mov     [rax+8], r8d
0x140003597  xor     r8d, r8d; ActivityId
0x14000359a  mov     [rsp+38h+UserData], rax; UserData
0x14000359f  mov     [rax+0Ch], r10d
0x1400035a3  mov     rcx, [rcx]; RegHandle
0x1400035a6  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x1400035ab  xor     r9d, r9d; RelatedActivityId
0x1400035ae  call    cs:__imp_EventWriteTransfer
0x1400035b4  add     rsp, 38h
0x1400035b8  retn
```
