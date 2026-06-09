# BfspBsdLogServicingEvent

- ea: `0x180046544`
- end: `0x18004665f`
- name: `BfspBsdLogServicingEvent`
- size: `283`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180049234`

## callees

- `0x1800078b0`
- `0x180046544`
- `0x180047468`
- `0x18004cdd4`

## import_xrefs

- `ntdll!NtClose` at `0x18004662d`
- `ntdll!NtClose` at `0x18004662d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800465be`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800465be`

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
0x180046544  mov     [rsp-8+arg_10], rbx
0x180046549  mov     [rsp-8+arg_18], rdi
0x18004654e  push    rbp
0x18004654f  mov     rbp, rsp
0x180046552  sub     rsp, 80h
0x180046559  mov     rax, cs:__security_cookie
0x180046560  xor     rax, rsp
0x180046563  mov     [rbp+var_8], rax
0x180046567  xor     eax, eax
0x180046569  xorps   xmm0, xmm0
0x18004656c  mov     edi, edx
0x18004656e  mov     [rbp+var_10], rax
0x180046572  mov     rbx, rcx
0x180046575  mov     [rbp+var_40], rax
0x180046579  mov     r8, rcx
0x18004657c  mov     [rbp+var_38], eax
0x18004657f  lea     ecx, [rax+2]
0x180046582  lea     rdx, aLoggingBootFil; "Logging boot file servicing to bootstat"...
0x180046589  movups  [rbp+var_30], xmm0
0x18004658d  movups  [rbp+var_20], xmm0
0x180046591  call    BfspLogMessage
0x180046596  xor     r9d, r9d; lpSecurityAttributes
0x180046599  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x1800465a2  mov     [rsp+80h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x1800465aa  mov     edx, 0C0000000h; dwDesiredAccess
0x1800465af  mov     rcx, rbx; lpFileName
0x1800465b2  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x1800465ba  lea     r8d, [r9+1]; dwShareMode
0x1800465be  call    cs:__imp_CreateFileW
0x1800465c4  mov     cs:BootstatHandle, rax
0x1800465cb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800465cf  jz      short loc_18004663E
0x1800465d1  mov     dword ptr [rbp+var_20+8], 34h ; '4'
0x1800465d8  lea     r9, [rbp+var_40]
0x1800465dc  mov     dword ptr [rbp+var_20+0Ch], 1
0x1800465e3  lea     r8, [rbp+var_30]
0x1800465e7  mov     dword ptr [rbp+var_10+4], 53h ; 'S'
0x1800465ee  mov     eax, 7FFE0014h
0x1800465f3  mov     [rbp+var_38], edi
0x1800465f6  mov     rax, [rax]
0x1800465f9  mov     [rbp+var_40], rax
0x1800465fd  call    BsdLogWriteEvent
0x180046602  test    eax, eax
0x180046604  jns     short loc_18004661D
0x180046606  mov     r9d, eax
0x180046609  lea     rdx, aFailedToLogSer; "Failed to log servicing event to bootst"...
0x180046610  mov     r8, rbx
0x180046613  mov     ecx, 3
0x180046618  call    BfspLogMessage
0x18004661d  mov     rax, cs:BootstatHandle
0x180046624  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180046628  jz      short loc_18004663E
0x18004662a  mov     rcx, rax; Handle
0x18004662d  call    cs:__imp_NtClose
0x180046633  mov     cs:BootstatHandle, 0FFFFFFFFFFFFFFFFh
0x18004663e  mov     rcx, [rbp+var_8]
0x180046642  xor     rcx, rsp; StackCookie
0x180046645  call    __security_check_cookie
0x18004664a  lea     r11, [rsp+80h+var_s0]
0x180046652  mov     rbx, [r11+20h]
0x180046656  mov     rdi, [r11+28h]
0x18004665a  mov     rsp, r11
0x18004665d  pop     rbp
0x18004665e  retn
```
