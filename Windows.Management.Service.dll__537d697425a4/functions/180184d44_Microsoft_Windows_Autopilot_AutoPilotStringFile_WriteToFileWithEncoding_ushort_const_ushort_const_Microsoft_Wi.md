# Microsoft::Windows::Autopilot::AutoPilotStringFile::WriteToFileWithEncoding(ushort const *,ushort const *,Microsoft::Windows::Autopilot::AutoPilotStringFile::Encoding)

- ea: `0x180184d44`
- end: `0x180184e4b`
- name: `?WriteToFileWithEncoding@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBG0W4Encoding@1234@@Z`
- size: `263`
- prototype: `static int __high(const unsigned __int16 *, const unsigned __int16 *, enum Microsoft::Windows::Autopilot::AutoPilotStringFile::Encoding)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180141d1c`
- `0x1801b2710`
- `0x1801b4164`

## callees

- `0x180067e34`
- `0x18008e088`
- `0x180184d44`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180184d74`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180184d74`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180184dd7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180184e18`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180184dd7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180184e18`

## string_xrefs

- `0x180184df1`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::AutoPilotStringFile::WriteToFileWithEncoding(
        const WCHAR *a1,
        _WORD *a2,
        DWORD a3)
{
  HANDLE FileW; // rbx
  const char *v5; // r9
  __int64 v6; // rdx
  __int64 v7; // rdi
  unsigned int LastError; // ebx
  HANDLE v10[5]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+18h] BYREF
  int Buffer; // [rsp+88h] [rbp+20h] BYREF

  NumberOfBytesWritten = a3;
  FileW = CreateFileW(a1, 0x10000000u, 0, 0, 2u, 0, 0);
  v10[0] = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    NumberOfBytesWritten = 0;
    Buffer = 65279;
    if ( WriteFile(FileW, &Buffer, 2u, &NumberOfBytesWritten, 0) )
    {
      if ( WriteFile(FileW, a2, 2 * v7, &NumberOfBytesWritten, 0) )
      {
        LastError = 0;
        goto LABEL_11;
      }
      v6 = 165;
    }
    else
    {
      v6 = 162;
    }
  }
  else
  {
    v6 = 152;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v6,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotconfigurationfile.cpp",
                v5);
LABEL_11:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v10);
  return LastError;
}

```

## disassembly

```asm
0x180184d44  mov     rax, rsp
0x180184d47  mov     [rax+8], rbx
0x180184d4b  mov     [rax+18h], r8d
0x180184d4f  push    rbp
0x180184d50  push    rsi
0x180184d51  push    rdi
0x180184d52  sub     rsp, 50h
0x180184d56  xor     ebp, ebp
0x180184d58  mov     rsi, rdx
0x180184d5b  mov     [rax-38h], rbp
0x180184d5f  xor     r9d, r9d; lpSecurityAttributes
0x180184d62  mov     [rax-40h], ebp
0x180184d65  xor     r8d, r8d; dwShareMode
0x180184d68  mov     edx, 10000000h; dwDesiredAccess
0x180184d6d  mov     dword ptr [rax-48h], 2
0x180184d74  call    cs:__imp_CreateFileW
0x180184d7b  nop     dword ptr [rax+rax+00h]
0x180184d80  mov     rbx, rax
0x180184d83  mov     [rsp+68h+var_28], rax
0x180184d88  inc     rax
0x180184d8b  test    rax, 0FFFFFFFFFFFFFFFEh
0x180184d91  jnz     short loc_180184D9A
0x180184d93  mov     edx, 98h
0x180184d98  jmp     short loc_180184DEC
0x180184d9a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180184d9e  inc     rdi
0x180184da1  cmp     [rsi+rdi*2], bp
0x180184da5  jnz     short loc_180184D9E
0x180184da7  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180184daf  mov     [rsp+68h+NumberOfBytesWritten], ebp
0x180184db6  mov     r8d, 2; nNumberOfBytesToWrite
0x180184dbc  mov     [rsp+68h+Buffer], 0FEFFh
0x180184dc7  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x180184dcf  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x180184dd4  mov     rcx, rbx; hFile
0x180184dd7  call    cs:__imp_WriteFile
0x180184dde  nop     dword ptr [rax+rax+00h]
0x180184de3  test    eax, eax
0x180184de5  jnz     short loc_180184E01
0x180184de7  mov     edx, 0A2h; void *
0x180184dec  mov     rcx, [rsp+68h]; this
0x180184df1  lea     r8, aOnecoreuapAdmi_152; "onecoreuap\\admin\\moderndeployment\\au"...
0x180184df8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180184dfd  mov     ebx, eax
0x180184dff  jmp     short loc_180184E31
0x180184e01  lea     r8d, [rdi+rdi]; nNumberOfBytesToWrite
0x180184e05  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x180184e0a  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180184e12  mov     rdx, rsi; lpBuffer
0x180184e15  mov     rcx, rbx; hFile
0x180184e18  call    cs:__imp_WriteFile
0x180184e1f  nop     dword ptr [rax+rax+00h]
0x180184e24  test    eax, eax
0x180184e26  jnz     short loc_180184E2F
0x180184e28  mov     edx, 0A5h
0x180184e2d  jmp     short loc_180184DEC
0x180184e2f  mov     ebx, ebp
0x180184e31  lea     rcx, [rsp+68h+var_28]
0x180184e36  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180184e3b  mov     eax, ebx
0x180184e3d  mov     rbx, [rsp+68h+arg_0]
0x180184e42  add     rsp, 50h
0x180184e46  pop     rdi
0x180184e47  pop     rsi
0x180184e48  pop     rbp
0x180184e49  retn
```
