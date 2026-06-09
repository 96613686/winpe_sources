# WdipWriteParameterToFile(__WDIP_PARAMETER *,void *)

- ea: `0x1800180f4`
- end: `0x180018369`
- name: `?WdipWriteParameterToFile@@YAJPEAU__WDIP_PARAMETER@@PEAX@Z`
- size: `629`
- prototype: `__int64 __fastcall(LPCVOID lpBuffer, HANDLE hFile)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018848`

## callees

- `0x180009090`
- `0x180010fbc`
- `0x180017a60`
- `0x1800180f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018166`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018166`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001815c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180018350`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001815c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180018350`

## string_xrefs

- `0x180018325`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x18001832c`: `WdipWriteParameterToFile`

## pseudocode

```c
__int64 __fastcall WdipWriteParameterToFile(char *lpBuffer, HANDLE hFile)
{
  unsigned int v4; // ebx
  int Args; // eax
  int v6; // r8d
  unsigned __int64 v7; // rdx
  signed int LastError; // eax
  unsigned __int64 v10; // [rsp+38h] [rbp-8h] BYREF
  DWORD Buffer; // [rsp+80h] [rbp+40h] BYREF
  union _LARGE_INTEGER NewFilePointer; // [rsp+88h] [rbp+48h] BYREF

  v10 = 0;
  Buffer = 0;
  NewFilePointer.QuadPart = 0;
  if ( !lpBuffer )
  {
    v4 = -2147024809;
    LOBYTE(Args) = 87;
    v6 = 891;
LABEL_31:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipWriteParameterToFile",
      v6,
      (int)L"Error = %d",
      Args);
    SetFilePointerEx(hFile, NewFilePointer, 0, 0);
    return v4;
  }
  if ( !SetFilePointerEx(hFile, 0, &NewFilePointer, 1u) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( (v4 & 0x80000000) != 0 )
    {
      v6 = 902;
      LOBYTE(Args) = v4;
      goto LABEL_31;
    }
  }
  Args = StringCchLengthW(*((const unsigned __int16 **)lpBuffer + 6), v7, &v10);
  v4 = Args;
  if ( Args < 0 )
  {
    v6 = 908;
    goto LABEL_31;
  }
  if ( v10 > 0xFFFFFFFF )
  {
    v4 = -2147024362;
    v6 = 911;
    LOBYTE(Args) = 22;
    goto LABEL_31;
  }
  Buffer = 2 * v10 + 2;
  Args = WdipWriteFile(hFile, lpBuffer, 0x10u);
  v4 = Args;
  if ( Args < 0 )
  {
    v6 = 921;
    goto LABEL_31;
  }
  Args = WdipWriteFile(hFile, lpBuffer + 16, 0x10u);
  v4 = Args;
  if ( Args < 0 )
  {
    v6 = 929;
    goto LABEL_31;
  }
  Args = WdipWriteFile(hFile, lpBuffer + 32, 4u);
  v4 = Args;
  if ( Args < 0 )
  {
    v6 = 937;
    goto LABEL_31;
  }
  Args = WdipWriteFile(hFile, lpBuffer + 36, 4u);
  v4 = Args;
  if ( Args < 0 )
  {
    v6 = 945;
    goto LABEL_31;
  }
  Args = WdipWriteFile(hFile, lpBuffer + 44, 4u);
  v4 = Args;
  if ( Args < 0 )
  {
    v6 = 953;
    goto LABEL_31;
  }
  Args = WdipWriteFile(hFile, &Buffer, 4u);
  v4 = Args;
  if ( Args < 0 )
  {
    v6 = 961;
    goto LABEL_31;
  }
  Args = WdipWriteFile(hFile, *((LPCVOID *)lpBuffer + 6), Buffer);
  v4 = Args;
  if ( Args < 0 )
  {
    v6 = 969;
    goto LABEL_31;
  }
  Args = WdipWriteFile(hFile, lpBuffer + 40, 4u);
  v4 = Args;
  if ( Args < 0 )
  {
    v6 = 977;
    goto LABEL_31;
  }
  Args = WdipWriteFile(hFile, *((LPCVOID *)lpBuffer + 7), *((_DWORD *)lpBuffer + 10));
  v4 = Args;
  if ( Args < 0 )
  {
    v6 = 985;
    goto LABEL_31;
  }
  return v4;
}

```

## disassembly

```asm
0x1800180f4  mov     [rsp-28h+arg_8], rbx
0x1800180f9  push    rbp
0x1800180fa  push    rsi
0x1800180fb  push    rdi
0x1800180fc  push    r12
0x1800180fe  push    r14
0x180018100  mov     rbp, rsp
0x180018103  sub     rsp, 40h
0x180018107  mov     [rbp+arg_0], 0
0x18001810e  mov     rsi, rdx
0x180018111  mov     [rbp+var_8], 0
0x180018119  mov     rdi, rcx
0x18001811c  mov     [rbp+Buffer], 0
0x180018123  mov     qword ptr [rbp+liDistanceToMove], 0
0x18001812b  mov     qword ptr [rbp+NewFilePointer], 0
0x180018133  test    rcx, rcx
0x180018136  jnz     short loc_18001814B
0x180018138  mov     ebx, 80070057h
0x18001813d  lea     eax, [rcx+57h]
0x180018140  mov     r8d, 37Bh
0x180018146  jmp     loc_180018325
0x18001814b  mov     rdx, qword ptr [rbp+liDistanceToMove]; liDistanceToMove
0x18001814f  lea     r8, [rbp+NewFilePointer]; lpNewFilePointer
0x180018153  mov     r9d, 1; dwMoveMethod
0x180018159  mov     rcx, rsi; hFile
0x18001815c  call    cs:__imp_SetFilePointerEx
0x180018162  test    eax, eax
0x180018164  jnz     short loc_18001818D
0x180018166  call    cs:__imp_GetLastError
0x18001816c  mov     ebx, eax
0x18001816e  test    eax, eax
0x180018170  jle     short loc_18001817B
0x180018172  movzx   ebx, ax
0x180018175  or      ebx, 80070000h
0x18001817b  test    ebx, ebx
0x18001817d  jns     short loc_18001818D
0x18001817f  mov     r8d, 386h
0x180018185  movzx   eax, bx
0x180018188  jmp     loc_180018325
0x18001818d  mov     rcx, [rdi+30h]; unsigned __int16 *
0x180018191  lea     r8, [rbp+var_8]; unsigned __int64 *
0x180018195  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001819a  mov     ebx, eax
0x18001819c  test    eax, eax
0x18001819e  jns     short loc_1800181AE
0x1800181a0  mov     r8d, 38Ch
0x1800181a6  movzx   eax, ax
0x1800181a9  jmp     loc_180018325
0x1800181ae  mov     rax, [rbp+var_8]
0x1800181b2  mov     ecx, 0FFFFFFFFh
0x1800181b7  cmp     rax, rcx
0x1800181ba  ja      loc_180018315
0x1800181c0  lea     eax, ds:2[rax*2]
0x1800181c7  mov     r14d, 10h
0x1800181cd  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800181d0  mov     [rbp+Buffer], eax
0x1800181d3  lea     r9, [rbp+arg_0]
0x1800181d7  mov     rdx, rdi; lpBuffer
0x1800181da  mov     rcx, rsi; hFile
0x1800181dd  call    WdipWriteFile
0x1800181e2  mov     ebx, eax
0x1800181e4  test    eax, eax
0x1800181e6  jns     short loc_1800181F0
0x1800181e8  mov     r8d, 399h
0x1800181ee  jmp     short loc_1800181A6
0x1800181f0  lea     rdx, [rdi+10h]; lpBuffer
0x1800181f4  mov     r8d, r14d; nNumberOfBytesToWrite
0x1800181f7  lea     r9, [rbp+arg_0]
0x1800181fb  mov     rcx, rsi; hFile
0x1800181fe  call    WdipWriteFile
0x180018203  mov     ebx, eax
0x180018205  test    eax, eax
0x180018207  jns     short loc_180018211
0x180018209  mov     r8d, 3A1h
0x18001820f  jmp     short loc_1800181A6
0x180018211  mov     r12d, 4
0x180018217  lea     rdx, [rdi+20h]; lpBuffer
0x18001821b  mov     r8d, r12d; nNumberOfBytesToWrite
0x18001821e  lea     r9, [rbp+arg_0]
0x180018222  mov     rcx, rsi; hFile
0x180018225  call    WdipWriteFile
0x18001822a  mov     ebx, eax
0x18001822c  test    eax, eax
0x18001822e  jns     short loc_18001823B
0x180018230  mov     r8d, 3A9h
0x180018236  jmp     loc_1800181A6
0x18001823b  lea     rdx, [rdi+24h]; lpBuffer
0x18001823f  mov     r8d, r12d; nNumberOfBytesToWrite
0x180018242  lea     r9, [rbp+arg_0]
0x180018246  mov     rcx, rsi; hFile
0x180018249  call    WdipWriteFile
0x18001824e  mov     ebx, eax
0x180018250  test    eax, eax
0x180018252  jns     short loc_18001825F
0x180018254  mov     r8d, 3B1h
0x18001825a  jmp     loc_1800181A6
0x18001825f  lea     rdx, [rdi+2Ch]; lpBuffer
0x180018263  mov     r8d, r12d; nNumberOfBytesToWrite
0x180018266  lea     r9, [rbp+arg_0]
0x18001826a  mov     rcx, rsi; hFile
0x18001826d  call    WdipWriteFile
0x180018272  mov     ebx, eax
0x180018274  test    eax, eax
0x180018276  jns     short loc_180018283
0x180018278  mov     r8d, 3B9h
0x18001827e  jmp     loc_1800181A6
0x180018283  lea     r9, [rbp+arg_0]
0x180018287  mov     r8d, r12d; nNumberOfBytesToWrite
0x18001828a  lea     rdx, [rbp+Buffer]; lpBuffer
0x18001828e  mov     rcx, rsi; hFile
0x180018291  call    WdipWriteFile
0x180018296  mov     ebx, eax
0x180018298  test    eax, eax
0x18001829a  jns     short loc_1800182A7
0x18001829c  mov     r8d, 3C1h
0x1800182a2  jmp     loc_1800181A6
0x1800182a7  mov     r8d, [rbp+Buffer]; nNumberOfBytesToWrite
0x1800182ab  lea     r9, [rbp+arg_0]
0x1800182af  mov     rdx, [rdi+30h]; lpBuffer
0x1800182b3  mov     rcx, rsi; hFile
0x1800182b6  call    WdipWriteFile
0x1800182bb  mov     ebx, eax
0x1800182bd  test    eax, eax
0x1800182bf  jns     short loc_1800182CC
0x1800182c1  mov     r8d, 3C9h
0x1800182c7  jmp     loc_1800181A6
0x1800182cc  lea     r9, [rbp+arg_0]
0x1800182d0  mov     r8d, r12d; nNumberOfBytesToWrite
0x1800182d3  lea     rdx, [rdi+28h]; lpBuffer
0x1800182d7  mov     rcx, rsi; hFile
0x1800182da  call    WdipWriteFile
0x1800182df  mov     ebx, eax
0x1800182e1  test    eax, eax
0x1800182e3  jns     short loc_1800182F0
0x1800182e5  mov     r8d, 3D1h
0x1800182eb  jmp     loc_1800181A6
0x1800182f0  mov     r8d, [rdi+28h]; nNumberOfBytesToWrite
0x1800182f4  lea     r9, [rbp+arg_0]
0x1800182f8  mov     rdx, [rdi+38h]; lpBuffer
0x1800182fc  mov     rcx, rsi; hFile
0x1800182ff  call    WdipWriteFile
0x180018304  mov     ebx, eax
0x180018306  test    eax, eax
0x180018308  jns     short loc_180018356
0x18001830a  mov     r8d, 3D9h
0x180018310  jmp     loc_1800181A6
0x180018315  mov     ebx, 80070216h
0x18001831a  mov     r8d, 38Fh; int
0x180018320  mov     eax, 216h
0x180018325  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18001832c  lea     rdx, aWdipwriteparam_2; "WdipWriteParameterToFile"
0x180018333  lea     r9, aErrorD; "Error = %d"
0x18001833a  mov     dword ptr [rsp+40h+Args], eax; Args
0x18001833e  call    WdipTraceError
0x180018343  mov     rdx, qword ptr [rbp+NewFilePointer]; liDistanceToMove
0x180018347  xor     r9d, r9d; dwMoveMethod
0x18001834a  xor     r8d, r8d; lpNewFilePointer
0x18001834d  mov     rcx, rsi; hFile
0x180018350  call    cs:__imp_SetFilePointerEx
0x180018356  mov     eax, ebx
0x180018358  mov     rbx, [rsp+40h+arg_8]
0x18001835d  add     rsp, 40h
0x180018361  pop     r14
0x180018363  pop     r12
0x180018365  pop     rdi
0x180018366  pop     rsi
0x180018367  pop     rbp
0x180018368  retn
```
