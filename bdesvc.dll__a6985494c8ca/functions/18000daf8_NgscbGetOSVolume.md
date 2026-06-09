# NgscbGetOSVolume

- ea: `0x18000daf8`
- end: `0x18000db9f`
- name: `NgscbGetOSVolume`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d408`
- `0x18000d904`
- `0x18003b560`
- `0x18003dc30`
- `0x18004c830`
- `0x18004d7f0`
- `0x18004f540`
- `0x18004f900`
- `0x1800591ec`
- `0x18005f8d4`
- `0x180065400`

## callees

- `0x18000daf8`
- `0x180024a18`
- `0x18002d9a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000db68`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18000db58`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18000db58`

## pseudocode

```c
__int64 __fastcall NgscbGetOSVolume(wchar_t *a1, size_t a2)
{
  HRESULT v3; // ebx
  __int64 v4; // r9
  WCHAR *v5; // rdi
  ULONG SystemWindowsDirectoryW; // eax
  signed int LastError; // eax
  size_t v9; // [rsp+20h] [rbp-18h]
  ULONG pulResult; // [rsp+48h] [rbp+10h] BYREF
  int v11; // [rsp+4Ch] [rbp+14h]
  size_t v12; // [rsp+50h] [rbp+18h] BYREF

  v11 = HIDWORD(a2);
  pulResult = 0;
  v12 = 0;
  v3 = StringCopyWorkerW(a1, a2, &v12, L"\\\\.\\", v9);
  if ( v3 >= 0 )
  {
    v3 = ULongLongToULong(260 - v12, &pulResult);
    if ( v3 >= 0 )
    {
      v5 = &a1[v4];
      SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(v5, pulResult);
      if ( SystemWindowsDirectoryW )
      {
        if ( SystemWindowsDirectoryW <= pulResult )
          v5[2] = 0;
      }
      else
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000daf8  mov     rax, rsp
0x18000dafb  mov     [rax+8], rbx
0x18000daff  mov     [rax+10h], rdx
0x18000db03  push    rdi
0x18000db04  sub     rsp, 30h
0x18000db08  lea     r9, pszSrc; "\\\\.\\"
0x18000db0f  mov     dword ptr [rax+10h], 0
0x18000db16  lea     r8, [rax+18h]; pcchNewDestLength
0x18000db1a  mov     qword ptr [rax+18h], 0
0x18000db22  mov     rdi, rcx
0x18000db25  call    StringCopyWorkerW
0x18000db2a  mov     ebx, eax
0x18000db2c  test    eax, eax
0x18000db2e  js      short loc_18000DB91
0x18000db30  mov     r9, [rsp+38h+arg_10]
0x18000db35  lea     rdx, [rsp+38h+pulResult]; pulResult
0x18000db3a  mov     ecx, 104h
0x18000db3f  sub     rcx, r9; ullOperand
0x18000db42  call    ULongLongToULong
0x18000db47  mov     ebx, eax
0x18000db49  test    eax, eax
0x18000db4b  js      short loc_18000DB91
0x18000db4d  mov     edx, [rsp+38h+pulResult]; uSize
0x18000db51  lea     rdi, [rdi+r9*2]
0x18000db55  mov     rcx, rdi; lpBuffer
0x18000db58  call    cs:__imp_GetSystemWindowsDirectoryW
0x18000db5f  nop     dword ptr [rax+rax+00h]
0x18000db64  test    eax, eax
0x18000db66  jnz     short loc_18000DB85
0x18000db68  call    cs:__imp_GetLastError
0x18000db6f  nop     dword ptr [rax+rax+00h]
0x18000db74  mov     ebx, eax
0x18000db76  test    eax, eax
0x18000db78  jle     short loc_18000DB91
0x18000db7a  movzx   ebx, ax
0x18000db7d  or      ebx, 80070000h
0x18000db83  jmp     short loc_18000DB91
0x18000db85  cmp     eax, [rsp+38h+pulResult]
0x18000db89  ja      short loc_18000DB91
0x18000db8b  xor     eax, eax
0x18000db8d  mov     [rdi+4], ax
0x18000db91  mov     eax, ebx
0x18000db93  mov     rbx, [rsp+38h+arg_0]
0x18000db98  add     rsp, 30h
0x18000db9c  pop     rdi
0x18000db9d  retn
```
