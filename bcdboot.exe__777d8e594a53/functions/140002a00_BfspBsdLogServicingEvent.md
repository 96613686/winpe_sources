# BfspBsdLogServicingEvent

- ea: `0x140002a00`
- end: `0x140002b1b`
- name: `BfspBsdLogServicingEvent`
- size: `283`
- prototype: `int __fastcall(LPCWSTR lpFileName, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x140009fd4`

## callees

- `0x140002a00`
- `0x140003a48`
- `0x14000e628`
- `0x140026650`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140002a7a`
- `KERNEL32!CreateFileW` at `0x140002a7a`
- `ntdll!NtClose` at `0x140002ae9`
- `ntdll!NtClose` at `0x140002ae9`

## pseudocode

```c
int __fastcall BfspBsdLogServicingEvent(LPCWSTR lpFileName, int a2)
{
  HANDLE FileW; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  int v7; // eax
  __int64 v9; // [rsp+40h] [rbp-40h] BYREF
  int v10; // [rsp+48h] [rbp-38h]
  __int128 v11; // [rsp+50h] [rbp-30h] BYREF
  __int128 v12; // [rsp+60h] [rbp-20h]
  __int64 v13; // [rsp+70h] [rbp-10h]

  v13 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  BfspLogMessage(2, L"Logging boot file servicing to bootstat log %ws.", lpFileName);
  FileW = CreateFileW(lpFileName, 0xC0000000, 1u, 0, 3u, 6u, 0);
  BootstatHandle = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    *((_QWORD *)&v12 + 1) = 0x100000034LL;
    HIDWORD(v13) = 83;
    v10 = a2;
    v9 = MEMORY[0x7FFE0014];
    v7 = BsdLogWriteEvent(v6, v5, &v11, &v9);
    if ( v7 < 0 )
      BfspLogMessage(3, L"Failed to log servicing event to bootstat %ws. Status: 0x%x\n", lpFileName, (unsigned int)v7);
    LODWORD(FileW) = (_DWORD)BootstatHandle;
    if ( BootstatHandle != (HANDLE)-1LL )
    {
      LODWORD(FileW) = NtClose(BootstatHandle);
      BootstatHandle = (HANDLE)-1LL;
    }
  }
  return (int)FileW;
}

```

## disassembly

```asm
0x140002a00  mov     [rsp-8+arg_10], rbx
0x140002a05  mov     [rsp-8+arg_18], rdi
0x140002a0a  push    rbp
0x140002a0b  mov     rbp, rsp
0x140002a0e  sub     rsp, 80h
0x140002a15  mov     rax, cs:__security_cookie
0x140002a1c  xor     rax, rsp
0x140002a1f  mov     [rbp+var_8], rax
0x140002a23  xor     eax, eax
0x140002a25  xorps   xmm0, xmm0
0x140002a28  mov     edi, edx
0x140002a2a  mov     [rbp+var_10], rax
0x140002a2e  mov     rbx, rcx
0x140002a31  mov     [rbp+var_40], rax
0x140002a35  mov     r8, rcx
0x140002a38  mov     [rbp+var_38], eax
0x140002a3b  lea     ecx, [rax+2]
0x140002a3e  lea     rdx, aLoggingBootFil; "Logging boot file servicing to bootstat"...
0x140002a45  movups  [rbp+var_30], xmm0
0x140002a49  movups  [rbp+var_20], xmm0
0x140002a4d  call    BfspLogMessage
0x140002a52  xor     r9d, r9d; lpSecurityAttributes
0x140002a55  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x140002a5e  mov     [rsp+80h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x140002a66  mov     edx, 0C0000000h; dwDesiredAccess
0x140002a6b  mov     rcx, rbx; lpFileName
0x140002a6e  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x140002a76  lea     r8d, [r9+1]; dwShareMode
0x140002a7a  call    cs:__imp_CreateFileW
0x140002a80  mov     cs:BootstatHandle, rax
0x140002a87  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140002a8b  jz      short loc_140002AFA
0x140002a8d  mov     dword ptr [rbp+var_20+8], 34h ; '4'
0x140002a94  lea     r9, [rbp+var_40]
0x140002a98  mov     dword ptr [rbp+var_20+0Ch], 1
0x140002a9f  lea     r8, [rbp+var_30]
0x140002aa3  mov     dword ptr [rbp+var_10+4], 53h ; 'S'
0x140002aaa  mov     eax, 7FFE0014h
0x140002aaf  mov     [rbp+var_38], edi
0x140002ab2  mov     rax, [rax]
0x140002ab5  mov     [rbp+var_40], rax
0x140002ab9  call    BsdLogWriteEvent
0x140002abe  test    eax, eax
0x140002ac0  jns     short loc_140002AD9
0x140002ac2  mov     r9d, eax
0x140002ac5  lea     rdx, aFailedToLogSer; "Failed to log servicing event to bootst"...
0x140002acc  mov     r8, rbx
0x140002acf  mov     ecx, 3
0x140002ad4  call    BfspLogMessage
0x140002ad9  mov     rax, cs:BootstatHandle
0x140002ae0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140002ae4  jz      short loc_140002AFA
0x140002ae6  mov     rcx, rax; Handle
0x140002ae9  call    cs:__imp_NtClose
0x140002aef  mov     cs:BootstatHandle, 0FFFFFFFFFFFFFFFFh
0x140002afa  mov     rcx, [rbp+var_8]
0x140002afe  xor     rcx, rsp; StackCookie
0x140002b01  call    __security_check_cookie
0x140002b06  lea     r11, [rsp+80h+var_s0]
0x140002b0e  mov     rbx, [r11+20h]
0x140002b12  mov     rdi, [r11+28h]
0x140002b16  mov     rsp, r11
0x140002b19  pop     rbp
0x140002b1a  retn
```
