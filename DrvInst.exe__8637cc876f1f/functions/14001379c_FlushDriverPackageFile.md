# FlushDriverPackageFile

- ea: `0x14001379c`
- end: `0x1400138a8`
- name: `FlushDriverPackageFile`
- size: `268`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x1400138b0`

## callees

- `0x14001379c`

## import_xrefs

- `ntdll!NtFlushBuffersFileEx` at `0x14001384f`
- `ntdll!NtFlushBuffersFileEx` at `0x14001384f`
- `ntdll!RtlNtStatusToDosError` at `0x14001385b`
- `ntdll!RtlNtStatusToDosError` at `0x14001385b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001380d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001380d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013890`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140013890`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013888`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140013888`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400137fe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400137fe`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400137d0`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001382f`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001387f`
- `DEVRTL!DevRtlWriteTextLog` at `0x1400137d0`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001382f`
- `DEVRTL!DevRtlWriteTextLog` at `0x14001387f`

## pseudocode

```c
_BOOL8 __fastcall FlushDriverPackageFile(LPCWSTR lpFileName, unsigned int a2, __int64 a3)
{
  HANDLE FileW; // rdi
  DWORD v7; // ebx
  NTSTATUS v8; // eax
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-50h]
  _OWORD v11[3]; // [rsp+40h] [rbp-38h] BYREF

  v11[0] = 0;
  DevRtlWriteTextLog(a3, 1, 6, "Flushing %ws to disk.", lpFileName);
  FileW = CreateFileW(lpFileName, 0x40000000u, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LODWORD(dwFlagsAndAttributes) = GetLastError();
    v7 = dwFlagsAndAttributes;
    DevRtlWriteTextLog(a3, 1, 6, "Could not get handle to %ws. Error = 0x%08X", lpFileName, dwFlagsAndAttributes);
  }
  else
  {
    v7 = 0;
    v8 = NtFlushBuffersFileEx(FileW, a2, 0, 0, v11);
    if ( v8 < 0 )
    {
      LODWORD(dwFlagsAndAttributes) = RtlNtStatusToDosError(v8);
      v7 = dwFlagsAndAttributes;
      DevRtlWriteTextLog(a3, 1, 6, "Unable to flush %ws to disk. Error = 0x%08X", lpFileName, dwFlagsAndAttributes);
    }
    CloseHandle(FileW);
  }
  SetLastError(v7);
  return v7 == 0;
}

```

## disassembly

```asm
0x14001379c  push    rbx
0x14001379e  push    rbp
0x14001379f  push    rsi
0x1400137a0  push    rdi
0x1400137a1  push    r14
0x1400137a3  sub     rsp, 50h
0x1400137a7  mov     rbp, r8
0x1400137aa  mov     qword ptr [rsp+78h+dwCreationDisposition], rcx
0x1400137af  mov     r14d, edx
0x1400137b2  lea     r9, aFlushingWsToDi; "Flushing %ws to disk."
0x1400137b9  mov     edx, 1
0x1400137be  mov     rsi, rcx
0x1400137c1  xorps   xmm0, xmm0
0x1400137c4  mov     rcx, rbp
0x1400137c7  movups  [rsp+78h+var_38], xmm0
0x1400137cc  lea     r8d, [rdx+5]
0x1400137d0  call    cs:__imp_DevRtlWriteTextLog
0x1400137d6  xor     r9d, r9d; lpSecurityAttributes
0x1400137d9  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1400137e2  mov     dword ptr [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400137ea  mov     edx, 40000000h; dwDesiredAccess
0x1400137ef  mov     rcx, rsi; lpFileName
0x1400137f2  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x1400137fa  lea     r8d, [r9+1]; dwShareMode
0x1400137fe  call    cs:__imp_CreateFileW
0x140013804  mov     rdi, rax
0x140013807  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001380b  jnz     short loc_140013837
0x14001380d  call    cs:__imp_GetLastError
0x140013813  mov     dword ptr [rsp+78h+dwFlagsAndAttributes], eax
0x140013817  lea     r9, aCouldNotGetHan; "Could not get handle to %ws. Error = 0x"...
0x14001381e  mov     rcx, rbp
0x140013821  mov     qword ptr [rsp+78h+dwCreationDisposition], rsi
0x140013826  lea     edx, [rdi+2]
0x140013829  mov     ebx, eax
0x14001382b  lea     r8d, [rdi+7]
0x14001382f  call    cs:__imp_DevRtlWriteTextLog
0x140013835  jmp     short loc_14001388E
0x140013837  lea     rax, [rsp+78h+var_38]
0x14001383c  xor     r9d, r9d
0x14001383f  xor     r8d, r8d
0x140013842  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x140013847  mov     edx, r14d
0x14001384a  mov     rcx, rdi
0x14001384d  xor     ebx, ebx
0x14001384f  call    cs:__imp_NtFlushBuffersFileEx
0x140013855  test    eax, eax
0x140013857  jns     short loc_140013885
0x140013859  mov     ecx, eax; Status
0x14001385b  call    cs:__imp_RtlNtStatusToDosError
0x140013861  mov     edx, 1
0x140013866  mov     dword ptr [rsp+78h+dwFlagsAndAttributes], eax
0x14001386a  lea     r9, aUnableToFlushW; "Unable to flush %ws to disk. Error = 0x"...
0x140013871  mov     qword ptr [rsp+78h+dwCreationDisposition], rsi
0x140013876  mov     rcx, rbp
0x140013879  mov     ebx, eax
0x14001387b  lea     r8d, [rdx+5]
0x14001387f  call    cs:__imp_DevRtlWriteTextLog
0x140013885  mov     rcx, rdi; hObject
0x140013888  call    cs:__imp_CloseHandle
0x14001388e  mov     ecx, ebx; dwErrCode
0x140013890  call    cs:__imp_SetLastError
0x140013896  xor     eax, eax
0x140013898  test    ebx, ebx
0x14001389a  setz    al
0x14001389d  add     rsp, 50h
0x1400138a1  pop     r14
0x1400138a3  pop     rdi
0x1400138a4  pop     rsi
0x1400138a5  pop     rbp
0x1400138a6  pop     rbx
0x1400138a7  retn
```
