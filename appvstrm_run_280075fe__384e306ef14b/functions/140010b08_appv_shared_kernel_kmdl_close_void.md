# appv::shared::kernel::kmdl::close(void)

- ea: `0x140010b08`
- end: `0x140010c5e`
- name: `?close@kmdl@kernel@shared@appv@@AEAAXXZ`
- size: `342`
- prototype: `void __fastcall(appv::shared::kernel::kmdl *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000fe80`
- `0x140010270`
- `0x1400105d8`
- `0x140010f00`

## callees

- `0x140010b08`
- `0x140015af0`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x140010b9a`
- `ntoskrnl!MmUnlockPages` at `0x140010b9a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140010c2a`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140010c2a`
- `ntoskrnl!IoGetCurrentProcess` at `0x140010b47`
- `ntoskrnl!IoGetCurrentProcess` at `0x140010b47`
- `ntoskrnl!KeStackAttachProcess` at `0x140010b61`
- `ntoskrnl!KeStackAttachProcess` at `0x140010b61`
- `ntoskrnl!IoFreeMdl` at `0x140010bb2`
- `ntoskrnl!IoFreeMdl` at `0x140010bb2`
- `ntoskrnl!MmUnmapLockedPages` at `0x140010b7d`
- `ntoskrnl!MmUnmapLockedPages` at `0x140010b7d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140010bd0`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140010bd0`
- `ntoskrnl!ObfDereferenceObject` at `0x140010be5`
- `ntoskrnl!ObfDereferenceObject` at `0x140010be5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010c04`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010c04`

## pseudocode

```c
void __fastcall appv::shared::kernel::kmdl::close(appv::shared::kernel::kmdl *this)
{
  struct _KPROCESS *v1; // rsi
  char v2; // di
  void *v4; // rcx
  bool v5; // zf
  struct _MDL *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rdx
  struct _PAGED_LOOKASIDE_LIST *v10; // rcx
  _KAPC_STATE ApcState; // [rsp+20h] [rbp-48h] BYREF

  v1 = (struct _KPROCESS *)*((_QWORD *)this + 7);
  v2 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  if ( v1 && IoGetCurrentProcess() != v1 )
  {
    KeStackAttachProcess(*((PRKPROCESS *)this + 7), &ApcState);
    v2 = 1;
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
    MmUnmapLockedPages(v4, *((PMDL *)this + 1));
  v5 = *(_BYTE *)this == 0;
  *((_QWORD *)this + 2) = 0;
  if ( !v5 )
    MmUnlockPages(*((PMDL *)this + 1));
  v6 = (struct _MDL *)*((_QWORD *)this + 1);
  *(_BYTE *)this = 0;
  if ( v6 )
    IoFreeMdl(v6);
  *((_QWORD *)this + 1) = 0;
  if ( v2 )
    KeUnstackDetachProcess(&ApcState);
  v7 = (void *)*((_QWORD *)this + 7);
  if ( v7 )
  {
    ObfDereferenceObject(v7);
    *((_QWORD *)this + 7) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 3);
  if ( v8 )
  {
    ExFreePoolWithTag(v8, 0);
    *((_QWORD *)this + 3) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 4);
  if ( v9 )
  {
    v10 = (struct _PAGED_LOOKASIDE_LIST *)*((_QWORD *)this + 5);
    if ( v10 )
    {
      ExFreeToPagedLookasideList(v10, v9);
      *((_QWORD *)this + 5) = 0;
    }
  }
}

```

## disassembly

```asm
0x140010b08  mov     [rsp+arg_8], rbx
0x140010b0d  mov     [rsp+arg_10], rsi
0x140010b12  push    rdi
0x140010b13  sub     rsp, 60h
0x140010b17  mov     rax, cs:__security_cookie
0x140010b1e  xor     rax, rsp
0x140010b21  mov     [rsp+68h+var_18], rax
0x140010b26  mov     rsi, [rcx+38h]
0x140010b2a  xorps   xmm0, xmm0
0x140010b2d  xor     dil, dil
0x140010b30  mov     rbx, rcx
0x140010b33  movups  xmmword ptr [rsp+68h+ApcState.ApcListHead.Flink], xmm0
0x140010b38  movups  xmmword ptr [rsp+68h+ApcState.ApcListHead.Flink+10h], xmm0
0x140010b3d  movups  xmmword ptr [rsp+68h+ApcState.Process], xmm0
0x140010b42  test    rsi, rsi
0x140010b45  jz      short loc_140010B70
0x140010b47  call    cs:__imp_IoGetCurrentProcess
0x140010b4e  nop     dword ptr [rax+rax+00h]
0x140010b53  cmp     rax, rsi
0x140010b56  jz      short loc_140010B70
0x140010b58  mov     rcx, [rbx+38h]; PROCESS
0x140010b5c  lea     rdx, [rsp+68h+ApcState]; ApcState
0x140010b61  call    cs:__imp_KeStackAttachProcess
0x140010b68  nop     dword ptr [rax+rax+00h]
0x140010b6d  mov     dil, 1
0x140010b70  mov     rcx, [rbx+10h]; BaseAddress
0x140010b74  test    rcx, rcx
0x140010b77  jz      short loc_140010B89
0x140010b79  mov     rdx, [rbx+8]; MemoryDescriptorList
0x140010b7d  call    cs:__imp_MmUnmapLockedPages
0x140010b84  nop     dword ptr [rax+rax+00h]
0x140010b89  cmp     byte ptr [rbx], 0
0x140010b8c  mov     qword ptr [rbx+10h], 0
0x140010b94  jz      short loc_140010BA6
0x140010b96  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140010b9a  call    cs:__imp_MmUnlockPages
0x140010ba1  nop     dword ptr [rax+rax+00h]
0x140010ba6  mov     rcx, [rbx+8]; Mdl
0x140010baa  mov     byte ptr [rbx], 0
0x140010bad  test    rcx, rcx
0x140010bb0  jz      short loc_140010BBE
0x140010bb2  call    cs:__imp_IoFreeMdl
0x140010bb9  nop     dword ptr [rax+rax+00h]
0x140010bbe  mov     qword ptr [rbx+8], 0
0x140010bc6  test    dil, dil
0x140010bc9  jz      short loc_140010BDC
0x140010bcb  lea     rcx, [rsp+68h+ApcState]; ApcState
0x140010bd0  call    cs:__imp_KeUnstackDetachProcess
0x140010bd7  nop     dword ptr [rax+rax+00h]
0x140010bdc  mov     rcx, [rbx+38h]; Object
0x140010be0  test    rcx, rcx
0x140010be3  jz      short loc_140010BF9
0x140010be5  call    cs:__imp_ObfDereferenceObject
0x140010bec  nop     dword ptr [rax+rax+00h]
0x140010bf1  mov     qword ptr [rbx+38h], 0
0x140010bf9  mov     rcx, [rbx+18h]; P
0x140010bfd  test    rcx, rcx
0x140010c00  jz      short loc_140010C18
0x140010c02  xor     edx, edx; Tag
0x140010c04  call    cs:__imp_ExFreePoolWithTag
0x140010c0b  nop     dword ptr [rax+rax+00h]
0x140010c10  mov     qword ptr [rbx+18h], 0
0x140010c18  mov     rdx, [rbx+20h]; Entry
0x140010c1c  test    rdx, rdx
0x140010c1f  jz      short loc_140010C3E
0x140010c21  mov     rcx, [rbx+28h]; Lookaside
0x140010c25  test    rcx, rcx
0x140010c28  jz      short loc_140010C3E
0x140010c2a  call    cs:__imp_ExFreeToPagedLookasideList
0x140010c31  nop     dword ptr [rax+rax+00h]
0x140010c36  mov     qword ptr [rbx+28h], 0
0x140010c3e  mov     rcx, [rsp+68h+var_18]
0x140010c43  xor     rcx, rsp; StackCookie
0x140010c46  call    __security_check_cookie
0x140010c4b  lea     r11, [rsp+68h+var_8]
0x140010c50  mov     rbx, [r11+18h]
0x140010c54  mov     rsi, [r11+20h]
0x140010c58  mov     rsp, r11
0x140010c5b  pop     rdi
0x140010c5c  retn
```
