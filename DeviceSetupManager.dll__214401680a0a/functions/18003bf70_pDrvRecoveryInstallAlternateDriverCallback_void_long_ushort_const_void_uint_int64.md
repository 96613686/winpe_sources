# pDrvRecoveryInstallAlternateDriverCallback(void *,long,ushort const *,void *,uint,__int64)

- ea: `0x18003bf70`
- end: `0x18003c055`
- name: `?pDrvRecoveryInstallAlternateDriverCallback@@YAHPEAXJPEBG0I_J@Z`
- size: `229`
- prototype: `__int64 __fastcall(void *, __int64, const unsigned __int16 *, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180007720`
- `0x18001af70`
- `0x18001ba48`
- `0x18003bf70`

## import_xrefs

- `DEVRTL!DevRtlWriteTextLog` at `0x18003bfeb`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003bfeb`
- `drvstore!DriverStoreUpdateDevicesW` at `0x18003c010`
- `drvstore!DriverStoreUpdateDevicesW` at `0x18003c010`

## pseudocode

```c
__int64 __fastcall pDrvRecoveryInstallAlternateDriverCallback(
        void *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        void *a4,
        unsigned int a5,
        unsigned int *a6)
{
  int updated; // eax
  __int64 v8; // r8
  unsigned __int16 v10[208]; // [rsp+30h] [rbp-1B8h] BYREF

  memset_0(v10, 0, 0x192u);
  if ( (int)StringCchCopyW(v10, 0xC9u, a3) >= 0 )
  {
    DevRtlWriteTextLog(*(_QWORD *)(*((_QWORD *)a6 + 1) + 560LL), 512, 65540, "Updating device %ws.", a3);
    v8 = *a6;
    LODWORD(v8) = v8 | 0x100000;
    updated = DriverStoreUpdateDevicesW(*(_QWORD *)(*((_QWORD *)a6 + 1) + 8LL), 0, v8, 0, v10);
    if ( updated == 3010 )
    {
      a6[4] = 1;
      updated = 0;
    }
  }
  else
  {
    updated = 13;
  }
  if ( !a6[5] )
    a6[5] = updated;
  return 1;
}

```

## disassembly

```asm
0x18003bf70  mov     [rsp+arg_0], rbx
0x18003bf75  push    rdi
0x18003bf76  sub     rsp, 1E0h
0x18003bf7d  mov     rax, cs:__security_cookie
0x18003bf84  xor     rax, rsp
0x18003bf87  mov     [rsp+1E8h+var_18], rax
0x18003bf8f  mov     rbx, [rsp+1E8h+arg_28]
0x18003bf97  lea     rcx, [rsp+1E8h+var_1B8]; void *
0x18003bf9c  mov     rdi, r8
0x18003bf9f  xor     edx, edx; Val
0x18003bfa1  mov     r8d, 192h; Size
0x18003bfa7  call    memset_0
0x18003bfac  mov     r8, rdi; unsigned __int16 *
0x18003bfaf  lea     rcx, [rsp+1E8h+var_1B8]; unsigned __int16 *
0x18003bfb4  mov     edx, 0C9h; unsigned __int64
0x18003bfb9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003bfbe  test    eax, eax
0x18003bfc0  jns     short loc_18003BFC9
0x18003bfc2  mov     eax, 0Dh
0x18003bfc7  jmp     short loc_18003C026
0x18003bfc9  mov     rcx, [rbx+8]
0x18003bfcd  lea     r9, aUpdatingDevice; "Updating device %ws."
0x18003bfd4  mov     edx, 200h
0x18003bfd9  mov     [rsp+1E8h+var_1C8], rdi
0x18003bfde  mov     r8d, 10004h
0x18003bfe4  mov     rcx, [rcx+230h]
0x18003bfeb  call    cs:__imp_DevRtlWriteTextLog
0x18003bff1  mov     rcx, [rbx+8]
0x18003bff5  lea     rax, [rsp+1E8h+var_1B8]
0x18003bffa  mov     r8d, [rbx]
0x18003bffd  xor     r9d, r9d
0x18003c000  bts     r8d, 14h
0x18003c005  mov     [rsp+1E8h+var_1C8], rax
0x18003c00a  xor     edx, edx
0x18003c00c  mov     rcx, [rcx+8]
0x18003c010  call    cs:__imp_DriverStoreUpdateDevicesW
0x18003c016  cmp     eax, 0BC2h
0x18003c01b  jnz     short loc_18003C026
0x18003c01d  mov     dword ptr [rbx+10h], 1
0x18003c024  xor     eax, eax
0x18003c026  cmp     dword ptr [rbx+14h], 0
0x18003c02a  jnz     short loc_18003C02F
0x18003c02c  mov     [rbx+14h], eax
0x18003c02f  mov     eax, 1
0x18003c034  mov     rcx, [rsp+1E8h+var_18]
0x18003c03c  xor     rcx, rsp; StackCookie
0x18003c03f  call    __security_check_cookie
0x18003c044  mov     rbx, [rsp+1E8h+arg_0]
0x18003c04c  add     rsp, 1E0h
0x18003c053  pop     rdi
0x18003c054  retn
```
