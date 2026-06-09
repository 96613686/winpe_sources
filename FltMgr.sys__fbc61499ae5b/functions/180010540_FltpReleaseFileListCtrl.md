# FltpReleaseFileListCtrl

- ea: `0x180010540`
- end: `0x1800105b4`
- name: `FltpReleaseFileListCtrl`
- size: `116`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800015b0`
- `0x1800085f0`
- `0x18000e5e0`
- `0x18000fcd0`
- `0x180012610`
- `0x180060e80`
- `0x180062ba0`
- `0x180064920`
- `0x1800763c0`

## callees

- `0x180010540`
- `0x180014c10`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001057b`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001057b`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x180010565`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x180010565`

## pseudocode

```c
void __fastcall FltpReleaseFileListCtrl(char *Entry)
{
  if ( (byte_180040A42 & 1) != 0 )
    McTemplateU0spdd_EtwWriteTransfer(
      (_DWORD)Entry,
      (unsigned int)FileListCtrlSup_c769,
      (unsigned int)"FltpReleaseFileListCtrl",
      (_DWORD)Entry,
      *((_DWORD *)Entry + 16),
      *((_DWORD *)Entry + 17));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Entry + 17, 0xFFFFFFFF) == 1 )
  {
    ExCleanupAutoExpandPushLock(Entry + 72);
    ExFreeToNPagedLookasideList(&stru_18003F140, Entry);
  }
}

```

## disassembly

```asm
0x180010540  push    rbx
0x180010542  sub     rsp, 30h
0x180010546  test    cs:byte_180040A42, 1
0x18001054d  mov     rbx, rcx
0x180010550  jnz     short loc_18001058E
0x180010552  mov     eax, 0FFFFFFFFh
0x180010557  lock xadd [rbx+44h], eax
0x18001055c  cmp     eax, 1
0x18001055f  jnz     short loc_180010587
0x180010561  lea     rcx, [rbx+48h]
0x180010565  call    cs:__imp_ExCleanupAutoExpandPushLock
0x18001056c  nop     dword ptr [rax+rax+00h]
0x180010571  mov     rdx, rbx; Entry
0x180010574  lea     rcx, stru_18003F140; Lookaside
0x18001057b  call    cs:__imp_ExFreeToNPagedLookasideList
0x180010582  nop     dword ptr [rax+rax+00h]
0x180010587  add     rsp, 30h
0x18001058b  pop     rbx
0x18001058c  retn
0x18001058e  mov     eax, [rcx+44h]
0x180010591  lea     r8, aFltpreleasefil; "FltpReleaseFileListCtrl"
0x180010598  mov     [rsp+38h+var_10], eax
0x18001059c  lea     rdx, FileListCtrlSup_c769
0x1800105a3  mov     eax, [rcx+40h]
0x1800105a6  mov     r9, rbx
0x1800105a9  mov     [rsp+38h+var_18], eax
0x1800105ad  call    McTemplateU0spdd_EtwWriteTransfer
0x1800105b2  jmp     short loc_180010552
```
