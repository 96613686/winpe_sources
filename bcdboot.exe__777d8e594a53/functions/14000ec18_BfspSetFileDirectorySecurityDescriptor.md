# BfspSetFileDirectorySecurityDescriptor

- ea: `0x14000ec18`
- end: `0x14000ed3e`
- name: `BfspSetFileDirectorySecurityDescriptor`
- size: `294`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int, const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140009fd4`
- `0x14000b57c`

## callees

- `0x140003368`
- `0x14000e628`
- `0x14000ea4c`
- `0x14000ec18`
- `0x14000ed44`

## import_xrefs

- `msvcrt!swprintf_s` at `0x14000eca7`
- `msvcrt!swprintf_s` at `0x14000eca7`
- `KERNEL32!SetLastError` at `0x14000ed23`
- `KERNEL32!SetLastError` at `0x14000ed23`
- `KERNEL32!GetLastError` at `0x14000ec7a`
- `KERNEL32!GetLastError` at `0x14000ecc0`
- `KERNEL32!GetLastError` at `0x14000ec7a`
- `KERNEL32!GetLastError` at `0x14000ecc0`
- `KERNEL32!HeapFree` at `0x14000ed07`
- `KERNEL32!HeapFree` at `0x14000ed07`
- `KERNEL32!HeapAlloc` at `0x14000ec51`
- `KERNEL32!HeapAlloc` at `0x14000ec51`
- `KERNEL32!GetProcessHeap` at `0x14000ec3b`
- `KERNEL32!GetProcessHeap` at `0x14000ecf9`
- `KERNEL32!GetProcessHeap` at `0x14000ec3b`
- `KERNEL32!GetProcessHeap` at `0x14000ecf9`
- `KERNEL32!LocalFree` at `0x14000ed17`
- `KERNEL32!LocalFree` at `0x14000ed17`

## string_xrefs

- `0x14000ece5`: `BfspSetSecurityDescriptor(%s) failed! Last Error = %#x`

## pseudocode

```c
__int64 __fastcall BfspSetFileDirectorySecurityDescriptor(LPCWSTR lpFileName, int a2, const wchar_t *a3)
{
  HANDLE ProcessHeap; // rax
  DWORD v7; // ebx
  wchar_t *v8; // rsi
  unsigned int UserSidString; // edi
  DWORD LastError; // eax
  HANDLE v11; // rax
  HLOCAL hMem; // [rsp+68h] [rbp+20h] BYREF

  hMem = 0;
  ProcessHeap = GetProcessHeap();
  v7 = 8;
  v8 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, 0x400u);
  if ( v8 )
  {
    if ( a2 || (UserSidString = BfspGetUserSidString((LPWSTR *)&hMem)) != 0 )
    {
      swprintf_s(v8, 0x200u, a3);
      v7 = 0;
      UserSidString = BfspSetSecurityDescriptor(lpFileName, v8);
      if ( !UserSidString )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError != 2 )
        {
          if ( LastError == 5 || LastError - 32 <= 1 )
            BfspPrintFileOwnerProcess(lpFileName);
          BfspLogMessage(4, L"BfspSetSecurityDescriptor(%s) failed! Last Error = %#x", lpFileName, v7);
        }
      }
    }
    else
    {
      v7 = GetLastError();
    }
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v8);
  }
  else
  {
    UserSidString = 0;
  }
  if ( hMem )
    LocalFree(hMem);
  if ( !UserSidString )
    SetLastError(v7);
  return UserSidString;
}

```

## disassembly

```asm
0x14000ec18  mov     [rsp+arg_0], rbx
0x14000ec1d  mov     [rsp+arg_8], rbp
0x14000ec22  push    rsi
0x14000ec23  push    rdi
0x14000ec24  push    r14
0x14000ec26  sub     rsp, 30h
0x14000ec2a  mov     r14, r8
0x14000ec2d  mov     [rsp+48h+hMem], 0
0x14000ec36  mov     edi, edx
0x14000ec38  mov     rbp, rcx
0x14000ec3b  call    cs:__imp_GetProcessHeap
0x14000ec41  mov     ebx, 8
0x14000ec46  mov     r8d, 400h; dwBytes
0x14000ec4c  mov     rcx, rax; hHeap
0x14000ec4f  mov     edx, ebx; dwFlags
0x14000ec51  call    cs:__imp_HeapAlloc
0x14000ec57  mov     rsi, rax
0x14000ec5a  test    rax, rax
0x14000ec5d  jnz     short loc_14000EC66
0x14000ec5f  xor     edi, edi
0x14000ec61  jmp     loc_14000ED0D
0x14000ec66  test    edi, edi
0x14000ec68  jnz     short loc_14000EC8B
0x14000ec6a  lea     rcx, [rsp+48h+hMem]; StringSid
0x14000ec6f  call    BfspGetUserSidString
0x14000ec74  mov     edi, eax
0x14000ec76  test    eax, eax
0x14000ec78  jnz     short loc_14000EC84
0x14000ec7a  call    cs:__imp_GetLastError
0x14000ec80  mov     ebx, eax
0x14000ec82  jmp     short loc_14000ECF9
0x14000ec84  mov     r9, [rsp+48h+hMem]
0x14000ec89  jmp     short loc_14000EC92
0x14000ec8b  lea     r9, aS1580956008885; "S-1-5-80-956008885-3418522649-183103804"...
0x14000ec92  mov     [rsp+48h+var_20], r9
0x14000ec97  mov     r8, r14; Format
0x14000ec9a  mov     edx, 200h; BufferCount
0x14000ec9f  mov     [rsp+48h+var_28], r9
0x14000eca4  mov     rcx, rsi; Buffer
0x14000eca7  call    cs:__imp_swprintf_s
0x14000ecad  mov     rdx, rsi; StringSecurityDescriptor
0x14000ecb0  mov     rcx, rbp; lpFileName
0x14000ecb3  xor     ebx, ebx
0x14000ecb5  call    BfspSetSecurityDescriptor
0x14000ecba  mov     edi, eax
0x14000ecbc  test    eax, eax
0x14000ecbe  jnz     short loc_14000ECF9
0x14000ecc0  call    cs:__imp_GetLastError
0x14000ecc6  mov     ebx, eax
0x14000ecc8  cmp     eax, 2
0x14000eccb  jz      short loc_14000ECF9
0x14000eccd  cmp     eax, 5
0x14000ecd0  jz      short loc_14000ECDA
0x14000ecd2  add     eax, 0FFFFFFE0h
0x14000ecd5  cmp     eax, 1
0x14000ecd8  ja      short loc_14000ECE2
0x14000ecda  mov     rcx, rbp; lpFileName
0x14000ecdd  call    BfspPrintFileOwnerProcess
0x14000ece2  mov     r9d, ebx
0x14000ece5  lea     rdx, aBfspsetsecurit; "BfspSetSecurityDescriptor(%s) failed! L"...
0x14000ecec  mov     r8, rbp
0x14000ecef  mov     ecx, 4
0x14000ecf4  call    BfspLogMessage
0x14000ecf9  call    cs:__imp_GetProcessHeap
0x14000ecff  mov     r8, rsi; lpMem
0x14000ed02  xor     edx, edx; dwFlags
0x14000ed04  mov     rcx, rax; hHeap
0x14000ed07  call    cs:__imp_HeapFree
0x14000ed0d  mov     rcx, [rsp+48h+hMem]; hMem
0x14000ed12  test    rcx, rcx
0x14000ed15  jz      short loc_14000ED1D
0x14000ed17  call    cs:__imp_LocalFree
0x14000ed1d  test    edi, edi
0x14000ed1f  jnz     short loc_14000ED29
0x14000ed21  mov     ecx, ebx; dwErrCode
0x14000ed23  call    cs:__imp_SetLastError
0x14000ed29  mov     rbx, [rsp+48h+arg_0]
0x14000ed2e  mov     eax, edi
0x14000ed30  mov     rbp, [rsp+48h+arg_8]
0x14000ed35  add     rsp, 30h
0x14000ed39  pop     r14
0x14000ed3b  pop     rdi
0x14000ed3c  pop     rsi
0x14000ed3d  retn
```
