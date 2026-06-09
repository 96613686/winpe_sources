# Microsoft::Windows::Autopilot::AutoPilotStringFile::WriteToFileWithEncoding(ushort const *,ushort const *,Microsoft::Windows::Autopilot::AutoPilotStringFile::Encoding)

- ea: `0x18018027c`
- end: `0x180180370`
- name: `?WriteToFileWithEncoding@AutoPilotStringFile@Autopilot@Windows@Microsoft@@SAJPEBG0W4Encoding@1234@@Z`
- size: `244`
- prototype: `__int64 __fastcall(const WCHAR *, _WORD *, DWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18013dc6c`
- `0x1801acf44`
- `0x1801ae8e0`

## callees

- `0x180067a34`
- `0x18008cfa4`
- `0x18018027c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801802ac`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801802ac`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180180309`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180180344`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180180309`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180180344`

## string_xrefs

- `0x18018031d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotconfigurationfile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
0x18018027c  mov     rax, rsp
0x18018027f  mov     [rax+8], rbx
0x180180283  mov     [rax+18h], r8d
0x180180287  push    rbp
0x180180288  push    rsi
0x180180289  push    rdi
0x18018028a  sub     rsp, 50h
0x18018028e  xor     ebp, ebp
0x180180290  mov     rsi, rdx
0x180180293  mov     [rax-38h], rbp
0x180180297  xor     r9d, r9d; lpSecurityAttributes
0x18018029a  mov     [rax-40h], ebp
0x18018029d  xor     r8d, r8d; dwShareMode
0x1801802a0  mov     edx, 10000000h; dwDesiredAccess
0x1801802a5  mov     dword ptr [rax-48h], 2
0x1801802ac  call    cs:__imp_CreateFileW
0x1801802b2  mov     rbx, rax
0x1801802b5  mov     [rsp+68h+var_28], rax
0x1801802ba  inc     rax
0x1801802bd  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801802c3  jnz     short loc_1801802CC
0x1801802c5  mov     edx, 98h
0x1801802ca  jmp     short loc_180180318
0x1801802cc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801802d0  inc     rdi
0x1801802d3  cmp     [rsi+rdi*2], bp
0x1801802d7  jnz     short loc_1801802D0
0x1801802d9  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801802e1  mov     [rsp+68h+NumberOfBytesWritten], ebp
0x1801802e8  mov     r8d, 2; nNumberOfBytesToWrite
0x1801802ee  mov     [rsp+68h+Buffer], 0FEFFh
0x1801802f9  lea     rdx, [rsp+68h+Buffer]; lpBuffer
0x180180301  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x180180306  mov     rcx, rbx; hFile
0x180180309  call    cs:__imp_WriteFile
0x18018030f  test    eax, eax
0x180180311  jnz     short loc_18018032D
0x180180313  mov     edx, 0A2h; void *
0x180180318  mov     rcx, [rsp+68h]; this
0x18018031d  lea     r8, aOnecoreuapAdmi_152; "onecoreuap\\admin\\moderndeployment\\au"...
0x180180324  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180180329  mov     ebx, eax
0x18018032b  jmp     short loc_180180357
0x18018032d  lea     r8d, [rdi+rdi]; nNumberOfBytesToWrite
0x180180331  mov     [rsp+68h+lpOverlapped], rbp; lpOverlapped
0x180180336  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18018033e  mov     rdx, rsi; lpBuffer
0x180180341  mov     rcx, rbx; hFile
0x180180344  call    cs:__imp_WriteFile
0x18018034a  test    eax, eax
0x18018034c  jnz     short loc_180180355
0x18018034e  mov     edx, 0A5h
0x180180353  jmp     short loc_180180318
0x180180355  mov     ebx, ebp
0x180180357  lea     rcx, [rsp+68h+var_28]
0x18018035c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180180361  mov     eax, ebx
0x180180363  mov     rbx, [rsp+68h+arg_0]
0x180180368  add     rsp, 50h
0x18018036c  pop     rdi
0x18018036d  pop     rsi
0x18018036e  pop     rbp
0x18018036f  retn
```
