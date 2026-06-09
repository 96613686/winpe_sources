# DpspWriteQueuedResolutionToFile(void *,INSTANCEINFO *)

- ea: `0x180013e68`
- end: `0x18001408a`
- name: `?DpspWriteQueuedResolutionToFile@@YAJPEAXPEAUINSTANCEINFO@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBuffer)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180014090`

## callees

- `0x180009090`
- `0x180013e68`
- `0x180017a60`
- `0x180018848`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ea7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f01`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013f79`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013fd5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013f79`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180013fd5`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180013ef7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180014075`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180013ef7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180014075`

## string_xrefs

- `0x180014055`: `DpspWriteQueuedResolutionToFile`

## pseudocode

```c
__int64 __fastcall DpspWriteQueuedResolutionToFile(HANDLE hFile, LPCVOID lpBuffer)
{
  signed int LastError; // eax
  signed int v5; // ebx
  int v6; // r8d
  int Args; // eax
  signed int v8; // eax
  __int64 v9; // rcx
  DWORD Buffer; // [rsp+70h] [rbp+30h] BYREF
  union _LARGE_INTEGER NewFilePointer; // [rsp+78h] [rbp+38h] BYREF

  Buffer = 0;
  NewFilePointer.QuadPart = 0;
  if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      v6 = 1191;
LABEL_6:
      LOBYTE(Args) = v5;
LABEL_29:
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
        (int)L"DpspWriteQueuedResolutionToFile",
        v6,
        (int)L"Error = %d",
        Args);
      SetFilePointerEx(hFile, NewFilePointer, 0, 0);
      return (unsigned int)v5;
    }
  }
  if ( !lpBuffer )
  {
    v5 = -2147024809;
    LOBYTE(Args) = 87;
    v6 = 1192;
    goto LABEL_29;
  }
  if ( !SetFilePointerEx(hFile, 0, &NewFilePointer, 1u) )
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    if ( v5 < 0 )
    {
      v6 = 1202;
      goto LABEL_6;
    }
  }
  Args = WdipWriteFile(hFile, lpBuffer, 0x4E0u);
  v5 = Args;
  if ( Args < 0 )
  {
    v6 = 1214;
    goto LABEL_29;
  }
  Args = WdipWriteFile(hFile, *((LPCVOID *)lpBuffer + 152), 0x10u);
  v5 = Args;
  if ( Args < 0 )
  {
    v6 = 1227;
    goto LABEL_29;
  }
  Buffer = GetLengthSid(*((PSID *)lpBuffer + 96));
  Args = WdipWriteFile(hFile, &Buffer, 4u);
  v5 = Args;
  if ( Args < 0 )
  {
    v6 = 1241;
    goto LABEL_29;
  }
  Args = WdipWriteFile(hFile, *((LPCVOID *)lpBuffer + 96), Buffer);
  v5 = Args;
  if ( Args < 0 )
  {
    v6 = 1249;
    goto LABEL_29;
  }
  Buffer = GetLengthSid(*((PSID *)lpBuffer + 95));
  Args = WdipWriteFile(hFile, &Buffer, 4u);
  v5 = Args;
  if ( Args < 0 )
  {
    v6 = 1263;
    goto LABEL_29;
  }
  Args = WdipWriteFile(hFile, *((LPCVOID *)lpBuffer + 95), Buffer);
  v5 = Args;
  if ( Args < 0 )
  {
    v6 = 1271;
    goto LABEL_29;
  }
  v9 = *((_QWORD *)lpBuffer + 153);
  if ( v9 )
  {
    Args = WdipWriteParameterCollectionToFile(v9, hFile);
    v5 = Args;
    if ( Args < 0 )
    {
      v6 = 1280;
      goto LABEL_29;
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180013e68  mov     [rsp-18h+arg_8], rbx
0x180013e6d  push    rbp
0x180013e6e  push    rsi
0x180013e6f  push    rdi
0x180013e70  mov     rbp, rsp
0x180013e73  sub     rsp, 40h
0x180013e77  lea     rax, [rcx+1]
0x180013e7b  mov     [rbp+Buffer], 0
0x180013e82  mov     [rbp+arg_0], 0
0x180013e89  mov     rdi, rdx
0x180013e8c  mov     qword ptr [rbp+NewFilePointer], 0
0x180013e94  mov     rsi, rcx
0x180013e97  mov     qword ptr [rbp+liDistanceToMove], 0
0x180013e9f  test    rax, 0FFFFFFFFFFFFFFFEh
0x180013ea5  jnz     short loc_180013ECE
0x180013ea7  call    cs:__imp_GetLastError
0x180013ead  mov     ebx, eax
0x180013eaf  test    eax, eax
0x180013eb1  jle     short loc_180013EBC
0x180013eb3  movzx   ebx, ax
0x180013eb6  or      ebx, 80070000h
0x180013ebc  test    ebx, ebx
0x180013ebe  jns     short loc_180013ECE
0x180013ec0  mov     r8d, 4A7h
0x180013ec6  movzx   eax, bx
0x180013ec9  jmp     loc_18001404A
0x180013ece  test    rdi, rdi
0x180013ed1  jnz     short loc_180013EE6
0x180013ed3  mov     ebx, 80070057h
0x180013ed8  lea     eax, [rdi+57h]
0x180013edb  mov     r8d, 4A8h
0x180013ee1  jmp     loc_18001404A
0x180013ee6  mov     rdx, qword ptr [rbp+liDistanceToMove]; liDistanceToMove
0x180013eea  lea     r8, [rbp+NewFilePointer]; lpNewFilePointer
0x180013eee  mov     r9d, 1; dwMoveMethod
0x180013ef4  mov     rcx, rsi; hFile
0x180013ef7  call    cs:__imp_SetFilePointerEx
0x180013efd  test    eax, eax
0x180013eff  jnz     short loc_180013F22
0x180013f01  call    cs:__imp_GetLastError
0x180013f07  mov     ebx, eax
0x180013f09  test    eax, eax
0x180013f0b  jle     short loc_180013F16
0x180013f0d  movzx   ebx, ax
0x180013f10  or      ebx, 80070000h
0x180013f16  test    ebx, ebx
0x180013f18  jns     short loc_180013F22
0x180013f1a  mov     r8d, 4B2h
0x180013f20  jmp     short loc_180013EC6
0x180013f22  lea     r9, [rbp+arg_0]
0x180013f26  mov     r8d, 4E0h; nNumberOfBytesToWrite
0x180013f2c  mov     rdx, rdi; lpBuffer
0x180013f2f  mov     rcx, rsi; hFile
0x180013f32  call    WdipWriteFile
0x180013f37  mov     ebx, eax
0x180013f39  test    eax, eax
0x180013f3b  jns     short loc_180013F48
0x180013f3d  mov     r8d, 4BEh
0x180013f43  jmp     loc_180014047
0x180013f48  mov     rdx, [rdi+4C0h]; lpBuffer
0x180013f4f  lea     r9, [rbp+arg_0]
0x180013f53  mov     r8d, 10h; nNumberOfBytesToWrite
0x180013f59  mov     rcx, rsi; hFile
0x180013f5c  call    WdipWriteFile
0x180013f61  mov     ebx, eax
0x180013f63  test    eax, eax
0x180013f65  jns     short loc_180013F72
0x180013f67  mov     r8d, 4CBh
0x180013f6d  jmp     loc_180014047
0x180013f72  mov     rcx, [rdi+300h]; pSid
0x180013f79  call    cs:__imp_GetLengthSid
0x180013f7f  lea     r9, [rbp+arg_0]
0x180013f83  mov     r8d, 4; nNumberOfBytesToWrite
0x180013f89  lea     rdx, [rbp+Buffer]; lpBuffer
0x180013f8d  mov     [rbp+Buffer], eax
0x180013f90  mov     rcx, rsi; hFile
0x180013f93  call    WdipWriteFile
0x180013f98  mov     ebx, eax
0x180013f9a  test    eax, eax
0x180013f9c  jns     short loc_180013FA9
0x180013f9e  mov     r8d, 4D9h
0x180013fa4  jmp     loc_180014047
0x180013fa9  mov     r8d, [rbp+Buffer]; nNumberOfBytesToWrite
0x180013fad  lea     r9, [rbp+arg_0]
0x180013fb1  mov     rdx, [rdi+300h]; lpBuffer
0x180013fb8  mov     rcx, rsi; hFile
0x180013fbb  call    WdipWriteFile
0x180013fc0  mov     ebx, eax
0x180013fc2  test    eax, eax
0x180013fc4  jns     short loc_180013FCE
0x180013fc6  mov     r8d, 4E1h
0x180013fcc  jmp     short loc_180014047
0x180013fce  mov     rcx, [rdi+2F8h]; pSid
0x180013fd5  call    cs:__imp_GetLengthSid
0x180013fdb  lea     r9, [rbp+arg_0]
0x180013fdf  mov     r8d, 4; nNumberOfBytesToWrite
0x180013fe5  lea     rdx, [rbp+Buffer]; lpBuffer
0x180013fe9  mov     [rbp+Buffer], eax
0x180013fec  mov     rcx, rsi; hFile
0x180013fef  call    WdipWriteFile
0x180013ff4  mov     ebx, eax
0x180013ff6  test    eax, eax
0x180013ff8  jns     short loc_180014002
0x180013ffa  mov     r8d, 4EFh
0x180014000  jmp     short loc_180014047
0x180014002  mov     r8d, [rbp+Buffer]; nNumberOfBytesToWrite
0x180014006  lea     r9, [rbp+arg_0]
0x18001400a  mov     rdx, [rdi+2F8h]; lpBuffer
0x180014011  mov     rcx, rsi; hFile
0x180014014  call    WdipWriteFile
0x180014019  mov     ebx, eax
0x18001401b  test    eax, eax
0x18001401d  jns     short loc_180014027
0x18001401f  mov     r8d, 4F7h
0x180014025  jmp     short loc_180014047
0x180014027  mov     rcx, [rdi+4C8h]
0x18001402e  test    rcx, rcx
0x180014031  jz      short loc_18001407B
0x180014033  mov     rdx, rsi
0x180014036  call    WdipWriteParameterCollectionToFile
0x18001403b  mov     ebx, eax
0x18001403d  test    eax, eax
0x18001403f  jns     short loc_18001407B
0x180014041  mov     r8d, 500h; int
0x180014047  movzx   eax, ax
0x18001404a  lea     r9, aErrorD; "Error = %d"
0x180014051  mov     dword ptr [rsp+40h+Args], eax; Args
0x180014055  lea     rdx, aDpspwritequeue; "DpspWriteQueuedResolutionToFile"
0x18001405c  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180014063  call    WdipTraceError
0x180014068  mov     rdx, qword ptr [rbp+NewFilePointer]; liDistanceToMove
0x18001406c  xor     r9d, r9d; dwMoveMethod
0x18001406f  xor     r8d, r8d; lpNewFilePointer
0x180014072  mov     rcx, rsi; hFile
0x180014075  call    cs:__imp_SetFilePointerEx
0x18001407b  mov     eax, ebx
0x18001407d  mov     rbx, [rsp+40h+arg_8]
0x180014082  add     rsp, 40h
0x180014086  pop     rdi
0x180014087  pop     rsi
0x180014088  pop     rbp
0x180014089  retn
```
