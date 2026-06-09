# Microsoft::Windows::Autopilot::AutoPilotStringFile::WriteToFile(ushort const *,ushort const *)

- ea: `0x18002588c`
- end: `0x180025994`
- name: `?WriteToFile@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBG0@Z`
- size: `264`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001ca58`

## callees

- `0x1800105d4`
- `0x18002588c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800258f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002597d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800258f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002597d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180025931`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180025969`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180025931`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180025969`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800258b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800258b8`

## string_xrefs

- `0x1800258d1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x180025945`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStringFile::WriteToFile(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  char *FileW; // rbx
  const char *v4; // r9
  unsigned int LastError; // edi
  __int64 v6; // rdi
  const char *v7; // r9
  __int64 v8; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp+18h] BYREF
  int Buffer; // [rsp+78h] [rbp+20h] BYREF

  FileW = (char *)CreateFileW(a1, 0x10000000u, 0, 0, 2u, 0, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    NumberOfBytesWritten = 0;
    Buffer = 65279;
    if ( WriteFile(FileW, &Buffer, 2u, &NumberOfBytesWritten, 0) )
    {
      if ( WriteFile(FileW, a2, 2 * v6, &NumberOfBytesWritten, 0) )
      {
        CloseHandle(FileW);
        return 0;
      }
      v8 = 165;
    }
    else
    {
      v8 = 162;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v8,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
                  v7);
    goto LABEL_3;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x98,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
                v4);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
LABEL_3:
    CloseHandle(FileW);
  return LastError;
}

```

## disassembly

```asm
0x18002588c  mov     rax, rsp
0x18002588f  mov     [rax+8], rbx
0x180025893  push    rbp
0x180025894  push    rsi
0x180025895  push    rdi
0x180025896  sub     rsp, 40h
0x18002589a  xor     ebp, ebp
0x18002589c  mov     rsi, rdx
0x18002589f  mov     [rax-28h], rbp
0x1800258a3  xor     r9d, r9d; lpSecurityAttributes
0x1800258a6  mov     [rax-30h], ebp
0x1800258a9  xor     r8d, r8d; dwShareMode
0x1800258ac  mov     edx, 10000000h; dwDesiredAccess
0x1800258b1  mov     dword ptr [rax-38h], 2
0x1800258b8  call    cs:__imp_CreateFileW
0x1800258be  mov     rbx, rax
0x1800258c1  inc     rax
0x1800258c4  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800258ca  jnz     short loc_180025900
0x1800258cc  mov     rcx, [rsp+58h]; this
0x1800258d1  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800258d8  mov     edx, 98h; void *
0x1800258dd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800258e2  mov     edi, eax
0x1800258e4  lea     rax, [rbx-1]
0x1800258e8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800258ec  ja      loc_180025985
0x1800258f2  mov     rcx, rbx; hObject
0x1800258f5  call    cs:__imp_CloseHandle
0x1800258fb  jmp     loc_180025985
0x180025900  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180025904  inc     rdi
0x180025907  cmp     [rsi+rdi*2], bp
0x18002590b  jnz     short loc_180025904
0x18002590d  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180025912  mov     [rsp+58h+NumberOfBytesWritten], ebp
0x180025916  mov     r8d, 2; nNumberOfBytesToWrite
0x18002591c  mov     [rsp+58h+Buffer], 0FEFFh
0x180025924  lea     rdx, [rsp+58h+Buffer]; lpBuffer
0x180025929  mov     [rsp+58h+lpOverlapped], rbp; lpOverlapped
0x18002592e  mov     rcx, rbx; hFile
0x180025931  call    cs:__imp_WriteFile
0x180025937  test    eax, eax
0x180025939  jnz     short loc_180025955
0x18002593b  mov     edx, 0A2h; void *
0x180025940  mov     rcx, [rsp+58h]; this
0x180025945  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002594c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025951  mov     edi, eax
0x180025953  jmp     short loc_1800258F2
0x180025955  lea     r8d, [rdi+rdi]; nNumberOfBytesToWrite
0x180025959  mov     [rsp+58h+lpOverlapped], rbp; lpOverlapped
0x18002595e  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180025963  mov     rdx, rsi; lpBuffer
0x180025966  mov     rcx, rbx; hFile
0x180025969  call    cs:__imp_WriteFile
0x18002596f  test    eax, eax
0x180025971  jnz     short loc_18002597A
0x180025973  mov     edx, 0A5h
0x180025978  jmp     short loc_180025940
0x18002597a  mov     rcx, rbx; hObject
0x18002597d  call    cs:__imp_CloseHandle
0x180025983  mov     edi, ebp
0x180025985  mov     rbx, [rsp+58h+arg_0]
0x18002598a  mov     eax, edi
0x18002598c  add     rsp, 40h
0x180025990  pop     rdi
0x180025991  pop     rsi
0x180025992  pop     rbp
0x180025993  retn
```
