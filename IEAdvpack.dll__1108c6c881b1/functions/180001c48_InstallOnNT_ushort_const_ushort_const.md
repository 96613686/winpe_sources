# InstallOnNT(ushort const *,ushort const *)

- ea: `0x180001c48`
- end: `0x180001db4`
- name: `?InstallOnNT@@YAJPEBG0@Z`
- size: `364`
- prototype: `__int64 __fastcall(PCWSTR SectionName, PCWSTR SourceRootPath)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000616c`

## callees

- `0x180001c48`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180001ce2`
- `KERNEL32!GetLastError` at `0x180001d77`
- `KERNEL32!GetLastError` at `0x180001ce2`
- `KERNEL32!GetLastError` at `0x180001d77`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x180001cd8`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x180001d6d`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x180001cd8`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x180001d6d`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180001d10`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180001d20`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180001d10`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180001d20`
- `SETUPAPI!SetupInitDefaultQueueCallbackEx` at `0x180001c7b`
- `SETUPAPI!SetupInitDefaultQueueCallbackEx` at `0x180001c7b`

## pseudocode

```c
__int64 __fastcall InstallOnNT(PCWSTR SectionName, PCWSTR SourceRootPath)
{
  PVOID Context; // rax
  void *v5; // rdi
  signed int LastError; // ebx
  UINT v7; // r9d

  Context = SetupInitDefaultQueueCallbackEx(0, (HWND)-(__int64)(word_1800257D2 != 0), 0, 0, 0);
  v5 = Context;
  if ( !Context )
    goto LABEL_11;
  if ( !SetupInstallFromInfSectionW(
          0,
          InfHandle,
          SectionName,
          0x10u,
          0,
          SourceRootPath,
          4u,
          MyFileQueueCallback2,
          Context,
          0,
          0) )
  {
    LastError = GetLastError();
    if ( (LastError & 0xE0000000) == 0xE0000000 )
    {
      LastError = (unsigned __int16)LastError | 0x800F0000;
    }
    else if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
    }
    SetupTermDefaultQueueCallback(v5);
    return (unsigned int)LastError;
  }
  LastError = 0;
  SetupTermDefaultQueueCallback(v5);
  v7 = 6;
  if ( ctx >= 3u )
    v7 = 262;
  if ( !SetupInstallFromInfSectionW(0, InfHandle, SectionName, v7, HKEY_LOCAL_MACHINE, 0, 0, 0, 0, 0, 0) )
  {
LABEL_11:
    LastError = GetLastError();
    if ( (LastError & 0xE0000000) == 0xE0000000 )
    {
      return (unsigned __int16)LastError | 0x800F0000;
    }
    else if ( LastError > 0 )
    {
      return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180001c48  mov     [rsp+arg_0], rbx
0x180001c4d  mov     [rsp+arg_8], rsi
0x180001c52  push    rdi
0x180001c53  sub     rsp, 60h
0x180001c57  movzx   eax, cs:word_1800257D2
0x180001c5e  mov     rbx, rdx
0x180001c61  neg     ax
0x180001c64  mov     [rsp+68h+Reserved2], 0; Reserved2
0x180001c6d  mov     rsi, rcx
0x180001c70  sbb     rdx, rdx; AlternateProgressWindow
0x180001c73  xor     r9d, r9d; Reserved1
0x180001c76  xor     r8d, r8d; ProgressMessage
0x180001c79  xor     ecx, ecx; OwnerWindow
0x180001c7b  call    cs:__imp_SetupInitDefaultQueueCallbackEx
0x180001c81  mov     rdi, rax
0x180001c84  test    rax, rax
0x180001c87  jz      loc_180001D77
0x180001c8d  mov     rdx, cs:InfHandle; InfHandle
0x180001c94  mov     r9d, 10h; Flags
0x180001c9a  mov     [rsp+68h+DeviceInfoData], 0; DeviceInfoData
0x180001ca3  mov     r8, rsi; SectionName
0x180001ca6  mov     [rsp+68h+DeviceInfoSet], 0; DeviceInfoSet
0x180001caf  xor     ecx, ecx; Owner
0x180001cb1  mov     [rsp+68h+Context], rax; Context
0x180001cb6  lea     rax, ?MyFileQueueCallback2@@YAIPEAXI_K1@Z; MyFileQueueCallback2(void *,uint,unsigned __int64,unsigned __int64)
0x180001cbd  mov     [rsp+68h+MsgHandler], rax; MsgHandler
0x180001cc2  mov     [rsp+68h+CopyFlags], 4; CopyFlags
0x180001cca  mov     [rsp+68h+SourceRootPath], rbx; SourceRootPath
0x180001ccf  mov     [rsp+68h+Reserved2], 0; RelativeKeyRoot
0x180001cd8  call    cs:__imp_SetupInstallFromInfSectionW
0x180001cde  test    eax, eax
0x180001ce0  jnz     short loc_180001D1B
0x180001ce2  call    cs:__imp_GetLastError
0x180001ce8  mov     ecx, 0E0000000h
0x180001ced  mov     ebx, eax
0x180001cef  and     eax, ecx
0x180001cf1  cmp     eax, ecx
0x180001cf3  jnz     short loc_180001D00
0x180001cf5  movzx   ebx, bx
0x180001cf8  or      ebx, 800F0000h
0x180001cfe  jmp     short loc_180001D0D
0x180001d00  test    ebx, ebx
0x180001d02  jle     short loc_180001D0D
0x180001d04  movzx   ebx, bx
0x180001d07  or      ebx, 80070000h
0x180001d0d  mov     rcx, rdi; Context
0x180001d10  call    cs:__imp_SetupTermDefaultQueueCallback
0x180001d16  jmp     loc_180001DA2
0x180001d1b  mov     rcx, rdi; Context
0x180001d1e  xor     ebx, ebx
0x180001d20  call    cs:__imp_SetupTermDefaultQueueCallback
0x180001d26  cmp     cs:?ctx@@3UADVCONTEXTW@@A, 3; ADVCONTEXTW ctx
0x180001d2e  lea     r9d, [rbx+6]
0x180001d32  mov     rdx, cs:InfHandle; InfHandle
0x180001d39  mov     eax, 106h
0x180001d3e  mov     [rsp+68h+DeviceInfoData], rbx; DeviceInfoData
0x180001d43  cmovnb  r9d, eax; Flags
0x180001d47  mov     [rsp+68h+DeviceInfoSet], rbx; DeviceInfoSet
0x180001d4c  xor     ecx, ecx; Owner
0x180001d4e  mov     [rsp+68h+Context], rbx; Context
0x180001d53  mov     r8, rsi; SectionName
0x180001d56  mov     [rsp+68h+MsgHandler], rbx; MsgHandler
0x180001d5b  mov     [rsp+68h+CopyFlags], ebx; CopyFlags
0x180001d5f  mov     [rsp+68h+SourceRootPath], rbx; SourceRootPath
0x180001d64  mov     [rsp+68h+Reserved2], 0FFFFFFFF80000002h; RelativeKeyRoot
0x180001d6d  call    cs:__imp_SetupInstallFromInfSectionW
0x180001d73  test    eax, eax
0x180001d75  jnz     short loc_180001DA2
0x180001d77  call    cs:__imp_GetLastError
0x180001d7d  mov     ecx, 0E0000000h
0x180001d82  mov     ebx, eax
0x180001d84  and     eax, ecx
0x180001d86  cmp     eax, ecx
0x180001d88  jnz     short loc_180001D95
0x180001d8a  movzx   ebx, bx
0x180001d8d  or      ebx, 800F0000h
0x180001d93  jmp     short loc_180001DA2
0x180001d95  test    ebx, ebx
0x180001d97  jle     short loc_180001DA2
0x180001d99  movzx   ebx, bx
0x180001d9c  or      ebx, 80070000h
0x180001da2  mov     rsi, [rsp+68h+arg_8]
0x180001da7  mov     eax, ebx
0x180001da9  mov     rbx, [rsp+68h+arg_0]
0x180001dae  add     rsp, 60h
0x180001db2  pop     rdi
0x180001db3  retn
```
