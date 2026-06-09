# FvepVolumeNameToCdoInfo

- ea: `0x180064e74`
- end: `0x180064f3c`
- name: `FvepVolumeNameToCdoInfo`
- size: `200`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180064098`

## callees

- `0x180064cb8`
- `0x180064e74`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180064f15`
- `KERNEL32!CloseHandle` at `0x180064f15`
- `KERNEL32!GetLastError` at `0x180064ee8`
- `KERNEL32!GetLastError` at `0x180064ee8`
- `KERNEL32!CreateFileW` at `0x180064ed9`
- `KERNEL32!CreateFileW` at `0x180064ed9`
- `ntdll!RtlSetThreadErrorMode` at `0x180064ea3`
- `ntdll!RtlSetThreadErrorMode` at `0x180064f21`
- `ntdll!RtlSetThreadErrorMode` at `0x180064ea3`
- `ntdll!RtlSetThreadErrorMode` at `0x180064f21`

## pseudocode

```c
__int64 __fastcall FvepVolumeNameToCdoInfo(LPCWSTR lpFileName)
{
  unsigned int v2; // ebx
  HANDLE FileW; // rax
  void *v4; // rdi
  signed int LastError; // eax
  ULONG NewMode; // [rsp+60h] [rbp+8h] BYREF

  NewMode = 0;
  RtlSetThreadErrorMode(0x10u, &NewMode);
  if ( lpFileName )
  {
    FileW = CreateFileW(lpFileName, 0, 3u, 0, 3u, 0, 0);
    v4 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v2 = FvepVolumeHandleToCdoInfo(FileW);
      CloseHandle(v4);
    }
  }
  else
  {
    v2 = -2147024809;
  }
  RtlSetThreadErrorMode(NewMode, 0);
  return v2;
}

```

## disassembly

```asm
0x180064e74  mov     rax, rsp
0x180064e77  mov     [rax+10h], rbx
0x180064e7b  mov     [rax+18h], rbp
0x180064e7f  push    rsi
0x180064e80  push    rdi
0x180064e81  push    r14
0x180064e83  sub     rsp, 40h
0x180064e87  mov     r14, rdx
0x180064e8a  mov     dword ptr [rax+8], 0
0x180064e91  mov     rbx, rcx
0x180064e94  lea     rdx, [rax+8]; OldMode
0x180064e98  mov     ecx, 10h; NewMode
0x180064e9d  mov     rsi, r9
0x180064ea0  mov     rbp, r8
0x180064ea3  call    cs:__imp_RtlSetThreadErrorMode
0x180064ea9  test    rbx, rbx
0x180064eac  jnz     short loc_180064EB5
0x180064eae  mov     ebx, 80070057h
0x180064eb3  jmp     short loc_180064F1B
0x180064eb5  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x180064ebe  mov     r8d, 3; dwShareMode
0x180064ec4  mov     [rsp+58h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180064ecc  xor     r9d, r9d; lpSecurityAttributes
0x180064ecf  xor     edx, edx; dwDesiredAccess
0x180064ed1  mov     [rsp+58h+dwCreationDisposition], r8d; dwCreationDisposition
0x180064ed6  mov     rcx, rbx; lpFileName
0x180064ed9  call    cs:__imp_CreateFileW
0x180064edf  mov     rdi, rax
0x180064ee2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180064ee6  jnz     short loc_180064EFF
0x180064ee8  call    cs:__imp_GetLastError
0x180064eee  mov     ebx, eax
0x180064ef0  test    eax, eax
0x180064ef2  jle     short loc_180064F1B
0x180064ef4  movzx   ebx, ax
0x180064ef7  or      ebx, 80070000h
0x180064efd  jmp     short loc_180064F1B
0x180064eff  mov     r9, rsi
0x180064f02  mov     r8, rbp
0x180064f05  mov     rdx, r14
0x180064f08  mov     rcx, rdi; hDevice
0x180064f0b  call    FvepVolumeHandleToCdoInfo
0x180064f10  mov     ebx, eax
0x180064f12  mov     rcx, rdi; hObject
0x180064f15  call    cs:__imp_CloseHandle
0x180064f1b  mov     ecx, [rsp+58h+NewMode]; NewMode
0x180064f1f  xor     edx, edx; OldMode
0x180064f21  call    cs:__imp_RtlSetThreadErrorMode
0x180064f27  mov     rbp, [rsp+58h+arg_10]
0x180064f2c  mov     eax, ebx
0x180064f2e  mov     rbx, [rsp+58h+arg_8]
0x180064f33  add     rsp, 40h
0x180064f37  pop     r14
0x180064f39  pop     rdi
0x180064f3a  pop     rsi
0x180064f3b  retn
```
