# ProcessFileSections(ushort const *,ushort const *,uint (*)(void *,uint,unsigned __int64,unsigned __int64))

- ea: `0x18000d90c`
- end: `0x18000da27`
- name: `?ProcessFileSections@@YAJPEBG0P6AIPEAXI_K2@Z@Z`
- size: `283`
- prototype: `__int64 __fastcall(PCWSTR SectionName, PCWSTR SourceRootPath, PSP_FILE_CALLBACK_W MsgHandler)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18000d6cc`
- `0x1800108a0`

## callees

- `0x18000c574`
- `0x18000d90c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000d951`
- `KERNEL32!GetLastError` at `0x18000d9d6`
- `KERNEL32!GetLastError` at `0x18000d951`
- `KERNEL32!GetLastError` at `0x18000d9d6`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x18000d9cc`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x18000d9cc`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x18000da08`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x18000da08`
- `SETUPAPI!SetupInitDefaultQueueCallbackEx` at `0x18000d942`
- `SETUPAPI!SetupInitDefaultQueueCallbackEx` at `0x18000d942`

## pseudocode

```c
__int64 __fastcall ProcessFileSections(PCWSTR SectionName, PCWSTR SourceRootPath, PSP_FILE_CALLBACK_W MsgHandler)
{
  PVOID Context; // rax
  void *v7; // rdi
  signed int LastError; // ebx

  AdvWriteToLog(L"ProcessFileSections: Sec=%1\r\n", SectionName);
  Context = SetupInitDefaultQueueCallbackEx(0, HWND_MESSAGE|0x2LL, 0, 0, 0);
  v7 = Context;
  if ( Context == (PVOID)-1LL )
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
  }
  else
  {
    if ( SetupInstallFromInfSectionW(0, InfHandle, SectionName, 0x10u, 0, SourceRootPath, 4u, MsgHandler, Context, 0, 0) )
    {
      LastError = 0;
    }
    else
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
    }
    SetupTermDefaultQueueCallback(v7);
  }
  AdvWriteToLog(L"ProcessFileSections: End hr=0x%1!x!\r\n", (unsigned int)LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000d90c  push    rbx
0x18000d90e  push    rbp
0x18000d90f  push    rsi
0x18000d910  push    rdi
0x18000d911  sub     rsp, 68h
0x18000d915  mov     rbp, rdx
0x18000d918  mov     rbx, rcx
0x18000d91b  mov     rdx, rcx
0x18000d91e  mov     rsi, r8
0x18000d921  lea     rcx, aProcessfilesec_0; "ProcessFileSections: Sec=%1\r\n"
0x18000d928  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000d92d  xor     r9d, r9d; Reserved1
0x18000d930  mov     [rsp+88h+Reserved2], 0; Reserved2
0x18000d939  xor     r8d, r8d; ProgressMessage
0x18000d93c  or      rdx, 0FFFFFFFFFFFFFFFFh; AlternateProgressWindow
0x18000d940  xor     ecx, ecx; OwnerWindow
0x18000d942  call    cs:__imp_SetupInitDefaultQueueCallbackEx
0x18000d948  mov     rdi, rax
0x18000d94b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d94f  jnz     short loc_18000D988
0x18000d951  call    cs:__imp_GetLastError
0x18000d957  mov     ecx, 0E0000000h
0x18000d95c  mov     ebx, eax
0x18000d95e  and     eax, ecx
0x18000d960  cmp     eax, ecx
0x18000d962  jnz     short loc_18000D972
0x18000d964  movzx   ebx, bx
0x18000d967  or      ebx, 800F0000h
0x18000d96d  jmp     loc_18000DA0E
0x18000d972  test    ebx, ebx
0x18000d974  jle     loc_18000DA0E
0x18000d97a  movzx   ebx, bx
0x18000d97d  or      ebx, 80070000h
0x18000d983  jmp     loc_18000DA0E
0x18000d988  mov     rdx, cs:InfHandle; InfHandle
0x18000d98f  mov     r9d, 10h; Flags
0x18000d995  mov     [rsp+88h+DeviceInfoData], 0; DeviceInfoData
0x18000d99e  mov     r8, rbx; SectionName
0x18000d9a1  mov     [rsp+88h+DeviceInfoSet], 0; DeviceInfoSet
0x18000d9aa  xor     ecx, ecx; Owner
0x18000d9ac  mov     [rsp+88h+Context], rdi; Context
0x18000d9b1  mov     [rsp+88h+MsgHandler], rsi; MsgHandler
0x18000d9b6  mov     [rsp+88h+CopyFlags], 4; CopyFlags
0x18000d9be  mov     [rsp+88h+SourceRootPath], rbp; SourceRootPath
0x18000d9c3  mov     [rsp+88h+Reserved2], 0; RelativeKeyRoot
0x18000d9cc  call    cs:__imp_SetupInstallFromInfSectionW
0x18000d9d2  test    eax, eax
0x18000d9d4  jnz     short loc_18000DA03
0x18000d9d6  call    cs:__imp_GetLastError
0x18000d9dc  mov     ecx, 0E0000000h
0x18000d9e1  mov     ebx, eax
0x18000d9e3  and     eax, ecx
0x18000d9e5  cmp     eax, ecx
0x18000d9e7  jnz     short loc_18000D9F4
0x18000d9e9  movzx   ebx, bx
0x18000d9ec  or      ebx, 800F0000h
0x18000d9f2  jmp     short loc_18000DA05
0x18000d9f4  test    ebx, ebx
0x18000d9f6  jle     short loc_18000DA05
0x18000d9f8  movzx   ebx, bx
0x18000d9fb  or      ebx, 80070000h
0x18000da01  jmp     short loc_18000DA05
0x18000da03  xor     ebx, ebx
0x18000da05  mov     rcx, rdi; Context
0x18000da08  call    cs:__imp_SetupTermDefaultQueueCallback
0x18000da0e  mov     edx, ebx
0x18000da10  lea     rcx, aProcessfilesec; "ProcessFileSections: End hr=0x%1!x!\r\n"
0x18000da17  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000da1c  mov     eax, ebx
0x18000da1e  add     rsp, 68h
0x18000da22  pop     rdi
0x18000da23  pop     rsi
0x18000da24  pop     rbp
0x18000da25  pop     rbx
0x18000da26  retn
```
