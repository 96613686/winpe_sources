# SvcGetStorageDeviceSize

- ea: `0x1800375c0`
- end: `0x18003761a`
- name: `SvcGetStorageDeviceSize`
- size: `90`
- prototype: `RPC_STATUS __fastcall(void *, const WCHAR *, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *lpTotalNumberOfFreeBytes)`
- caller_count: `11`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180024ac4`
- `0x18002af00`
- `0x18002b1a0`
- `0x18002f710`
- `0x18002f860`
- `0x180032088`
- `0x18003253c`
- `0x180034ad4`
- `0x180035128`
- `0x180038e54`
- `0x180039124`

## callees

- `0x18001a70c`
- `0x1800375c0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1800375f8`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1800375f8`
- `RPCRT4!RpcRevertToSelf` at `0x180037609`
- `RPCRT4!RpcRevertToSelf` at `0x180037609`
- `RPCRT4!RpcImpersonateClient` at `0x1800375d2`
- `RPCRT4!RpcImpersonateClient` at `0x1800375d2`

## pseudocode

```c
RPC_STATUS __fastcall SvcGetStorageDeviceSize(
        void *a1,
        const WCHAR *a2,
        union _ULARGE_INTEGER *a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *lpTotalNumberOfFreeBytes)
{
  RPC_STATUS result; // eax
  int LastHr; // ebx

  result = RpcImpersonateClient(a1);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    LastHr = 0;
    if ( !GetDiskFreeSpaceExW(a2, a3, a4, lpTotalNumberOfFreeBytes) )
      LastHr = GetLastHr();
    RpcRevertToSelf();
    return LastHr;
  }
  return result;
}

```

## disassembly

```asm
0x1800375c0  push    rbx
0x1800375c2  push    rbp
0x1800375c3  push    rsi
0x1800375c4  push    rdi
0x1800375c5  sub     rsp, 28h
0x1800375c9  mov     rdi, r9
0x1800375cc  mov     rsi, r8
0x1800375cf  mov     rbp, rdx
0x1800375d2  call    cs:__imp_RpcImpersonateClient
0x1800375d8  test    eax, eax
0x1800375da  jz      short loc_1800375E8
0x1800375dc  jle     short loc_180037611
0x1800375de  movzx   eax, ax
0x1800375e1  or      eax, 80070000h
0x1800375e6  jmp     short loc_180037611
0x1800375e8  mov     r9, [rsp+48h+lpTotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x1800375ed  mov     r8, rdi; lpTotalNumberOfBytes
0x1800375f0  mov     rdx, rsi; lpFreeBytesAvailableToCaller
0x1800375f3  mov     rcx, rbp; lpDirectoryName
0x1800375f6  xor     ebx, ebx
0x1800375f8  call    cs:__imp_GetDiskFreeSpaceExW
0x1800375fe  test    eax, eax
0x180037600  jnz     short loc_180037609
0x180037602  call    ?GetLastHr@@YAJXZ; GetLastHr(void)
0x180037607  mov     ebx, eax
0x180037609  call    cs:__imp_RpcRevertToSelf
0x18003760f  mov     eax, ebx
0x180037611  add     rsp, 28h
0x180037615  pop     rdi
0x180037616  pop     rsi
0x180037617  pop     rbp
0x180037618  pop     rbx
0x180037619  retn
```
