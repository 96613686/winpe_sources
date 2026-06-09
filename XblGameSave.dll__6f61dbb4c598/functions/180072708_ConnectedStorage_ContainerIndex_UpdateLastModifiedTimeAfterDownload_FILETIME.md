# ConnectedStorage::ContainerIndex::UpdateLastModifiedTimeAfterDownload(_FILETIME *)

- ea: `0x180072708`
- end: `0x18007275a`
- name: `?UpdateLastModifiedTimeAfterDownload@ContainerIndex@ConnectedStorage@@QEBAXPEAU_FILETIME@@@Z`
- size: `82`
- prototype: `void(ConnectedStorage::ContainerIndex *__hidden this, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180071808`

## callees

- `0x18000cb9c`
- `0x180072708`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072753`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180072730`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180072730`

## pseudocode

```c
void __fastcall ConnectedStorage::ContainerIndex::UpdateLastModifiedTimeAfterDownload(
        ConnectedStorage::ContainerIndex *this,
        struct _FILETIME *a2,
        char *a3)
{
  LPCRITICAL_SECTION v5[3]; // [rsp+20h] [rbp-18h] BYREF

  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)v5,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 64),
    a3);
  if ( CompareFileTime((const FILETIME *)this + 16, a2) < 0 )
    *((struct _FILETIME *)this + 16) = *a2;
  LeaveCriticalSection(v5[0]);
}

```

## disassembly

```asm
0x180072708  mov     [rsp+arg_0], rbx
0x18007270d  push    rdi
0x18007270e  sub     rsp, 30h
0x180072712  mov     rdi, rdx
0x180072715  mov     rbx, rcx
0x180072718  lea     rdx, [rcx+40h]; struct ConnectedStorage::Mutex *
0x18007271c  lea     rcx, [rsp+38h+var_18]; this
0x180072721  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180072726  mov     rdx, rdi; lpFileTime2
0x180072729  lea     rcx, [rbx+80h]; lpFileTime1
0x180072730  call    cs:__imp_CompareFileTime
0x180072736  test    eax, eax
0x180072738  jns     short loc_180072744
0x18007273a  mov     rax, [rdi]
0x18007273d  mov     [rbx+80h], rax
0x180072744  mov     rcx, [rsp+38h+var_18]
0x180072749  mov     rbx, [rsp+38h+arg_0]
0x18007274e  add     rsp, 30h
0x180072752  pop     rdi
0x180072753  jmp     cs:__imp_LeaveCriticalSection
```
