# Microsoft::Windows::Autopilot::AutoPilotStringFile::WriteToFile(ushort const *,ushort const *)

- ea: `0x18002672c`
- end: `0x180026853`
- name: `?WriteToFile@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBG0@Z`
- size: `295`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001d1c0`

## callees

- `0x180010744`
- `0x18002672c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002679b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026835`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002679b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026835`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800267dd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002681b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800267dd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002681b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026758`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180026758`

## string_xrefs

- `0x180026777`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`
- `0x1800267f7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x18002672c  mov     rax, rsp
0x18002672f  mov     [rax+8], rbx
0x180026733  push    rbp
0x180026734  push    rsi
0x180026735  push    rdi
0x180026736  sub     rsp, 40h
0x18002673a  xor     ebp, ebp
0x18002673c  mov     rsi, rdx
0x18002673f  mov     [rax-28h], rbp
0x180026743  xor     r9d, r9d; lpSecurityAttributes
0x180026746  mov     [rax-30h], ebp
0x180026749  xor     r8d, r8d; dwShareMode
0x18002674c  mov     edx, 10000000h; dwDesiredAccess
0x180026751  mov     dword ptr [rax-38h], 2
0x180026758  call    cs:__imp_CreateFileW
0x18002675f  nop     dword ptr [rax+rax+00h]
0x180026764  mov     rbx, rax
0x180026767  inc     rax
0x18002676a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180026770  jnz     short loc_1800267AC
0x180026772  mov     rcx, [rsp+58h]; this
0x180026777  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002677e  mov     edx, 98h; void *
0x180026783  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026788  mov     edi, eax
0x18002678a  lea     rax, [rbx-1]
0x18002678e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180026792  ja      loc_180026843
0x180026798  mov     rcx, rbx; hObject
0x18002679b  call    cs:__imp_CloseHandle
0x1800267a2  nop     dword ptr [rax+rax+00h]
0x1800267a7  jmp     loc_180026843
0x1800267ac  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800267b0  inc     rdi
0x1800267b3  cmp     [rsi+rdi*2], bp
0x1800267b7  jnz     short loc_1800267B0
0x1800267b9  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800267be  mov     [rsp+58h+NumberOfBytesWritten], ebp
0x1800267c2  mov     r8d, 2; nNumberOfBytesToWrite
0x1800267c8  mov     [rsp+58h+Buffer], 0FEFFh
0x1800267d0  lea     rdx, [rsp+58h+Buffer]; lpBuffer
0x1800267d5  mov     [rsp+58h+lpOverlapped], rbp; lpOverlapped
0x1800267da  mov     rcx, rbx; hFile
0x1800267dd  call    cs:__imp_WriteFile
0x1800267e4  nop     dword ptr [rax+rax+00h]
0x1800267e9  test    eax, eax
0x1800267eb  jnz     short loc_180026807
0x1800267ed  mov     edx, 0A2h; void *
0x1800267f2  mov     rcx, [rsp+58h]; this
0x1800267f7  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800267fe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026803  mov     edi, eax
0x180026805  jmp     short loc_180026798
0x180026807  lea     r8d, [rdi+rdi]; nNumberOfBytesToWrite
0x18002680b  mov     [rsp+58h+lpOverlapped], rbp; lpOverlapped
0x180026810  lea     r9, [rsp+58h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180026815  mov     rdx, rsi; lpBuffer
0x180026818  mov     rcx, rbx; hFile
0x18002681b  call    cs:__imp_WriteFile
0x180026822  nop     dword ptr [rax+rax+00h]
0x180026827  test    eax, eax
0x180026829  jnz     short loc_180026832
0x18002682b  mov     edx, 0A5h
0x180026830  jmp     short loc_1800267F2
0x180026832  mov     rcx, rbx; hObject
0x180026835  call    cs:__imp_CloseHandle
0x18002683c  nop     dword ptr [rax+rax+00h]
0x180026841  mov     edi, ebp
0x180026843  mov     rbx, [rsp+58h+arg_0]
0x180026848  mov     eax, edi
0x18002684a  add     rsp, 40h
0x18002684e  pop     rdi
0x18002684f  pop     rsi
0x180026850  pop     rbp
0x180026851  retn
```
