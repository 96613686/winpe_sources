# WfpObjectManagerInitialize

- ea: `0x18001f610`
- end: `0x18001f6c3`
- name: `WfpObjectManagerInitialize`
- size: `179`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001bdd0`

## callees

- `0x180004904`
- `0x18000c9b4`
- `0x18001f5d8`
- `0x18001f610`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x18001f62b`
- `ntoskrnl!KeInitializeSpinLock` at `0x18001f62b`
- `ntoskrnl!RtlCreateHashTable` at `0x18001f64f`
- `ntoskrnl!RtlCreateHashTable` at `0x18001f64f`

## string_xrefs

- `0x18001f688`: `WfpHashtableCreate`
- `0x18001f679`: `WfpHashtableCreateEx`
- `0x18001f665`: `RtlCreateHashTable`

## pseudocode

```c
__int64 __fastcall WfpObjectManagerInitialize(char *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rax
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+30h] [rbp+8h] BYREF

  *((_WORD *)a1 + 8) = 0;
  a1[120] = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)a1 + 8);
  *a1 = 1;
  HashTable = (PRTL_DYNAMIC_HASH_TABLE)(a1 + 24);
  v2 = 0;
  if ( RtlCreateHashTable(&HashTable, 0, 0)
    || (v4 = WfpReportSysErrorAsNtStatus(v3, (int)"RtlCreateHashTable", -1073741801), (v2 = v4) == 0) )
  {
    a1[1] = 1;
  }
  else
  {
    WfpReportError(v4, (int)"WfpHashtableCreateEx");
    WfpReportError(v2, (int)"WfpHashtableCreate");
    WfpObjectManagerClose(a1);
    WfpReportError(v2, (int)"WfpObjectManagerInitialize");
  }
  return v2;
}

```

## disassembly

```asm
0x18001f610  mov     [rsp+arg_8], rbx
0x18001f615  push    rdi
0x18001f616  sub     rsp, 20h
0x18001f61a  mov     rdi, rcx
0x18001f61d  mov     word ptr [rcx+10h], 0
0x18001f623  mov     byte ptr [rcx+78h], 0
0x18001f627  add     rcx, 40h ; '@'; SpinLock
0x18001f62b  call    cs:__imp_KeInitializeSpinLock
0x18001f632  nop     dword ptr [rax+rax+00h]
0x18001f637  lea     rax, [rdi+18h]
0x18001f63b  mov     byte ptr [rdi], 1
0x18001f63e  xor     r8d, r8d; Flags
0x18001f641  mov     [rsp+28h+HashTable], rax
0x18001f646  xor     edx, edx; Shift
0x18001f648  lea     rcx, [rsp+28h+HashTable]; HashTable
0x18001f64d  xor     ebx, ebx
0x18001f64f  call    cs:__imp_RtlCreateHashTable
0x18001f656  nop     dword ptr [rax+rax+00h]
0x18001f65b  test    al, al
0x18001f65d  jnz     short loc_18001F6B0
0x18001f65f  mov     r8d, 0C0000017h
0x18001f665  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x18001f66c  call    WfpReportSysErrorAsNtStatus
0x18001f671  mov     rbx, rax
0x18001f674  test    rax, rax
0x18001f677  jz      short loc_18001F6B0
0x18001f679  lea     rdx, aWfphashtablecr_0; "WfpHashtableCreateEx"
0x18001f680  mov     rcx, rax
0x18001f683  call    WfpReportError
0x18001f688  lea     rdx, aWfphashtablecr; "WfpHashtableCreate"
0x18001f68f  mov     rcx, rbx
0x18001f692  call    WfpReportError
0x18001f697  mov     rcx, rdi; void *
0x18001f69a  call    WfpObjectManagerClose
0x18001f69f  lea     rdx, aWfpobjectmanag; "WfpObjectManagerInitialize"
0x18001f6a6  mov     rcx, rbx
0x18001f6a9  call    WfpReportError
0x18001f6ae  jmp     short loc_18001F6B4
0x18001f6b0  mov     byte ptr [rdi+1], 1
0x18001f6b4  mov     rax, rbx
0x18001f6b7  mov     rbx, [rsp+28h+arg_8]
0x18001f6bc  add     rsp, 20h
0x18001f6c0  pop     rdi
0x18001f6c1  retn
```
