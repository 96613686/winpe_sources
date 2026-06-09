# Windows::Compat::Inventory::GetMoreData::CaptureAslLogging(void)

- ea: `0x14000dc94`
- end: `0x14000dded`
- name: `?CaptureAslLogging@GetMoreData@Inventory@Compat@Windows@@QEAAJXZ`
- size: `345`
- prototype: `signed int __fastcall(Windows::Compat::Inventory::GetMoreData *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000c2f8`

## callees

- `0x140001e34`
- `0x140001e90`
- `0x14000dc94`
- `0x1400151b0`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14000dd96`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x14000dd96`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x14000dd76`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x14000dd76`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x14000dd58`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x14000dd58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dd03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dd03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dcf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dda5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ddcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dcf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000dda5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ddcd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dcfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000dcfb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateNamedPipeA` at `0x14000dcd9`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CreateNamedPipeA` at `0x14000dcd9`

## string_xrefs

- `0x14000ddaf`: `CreateNamedPipe failed [%d]`
- `0x14000ddbc`: `Windows::Compat::Inventory::GetMoreData::CaptureAslLogging`

## pseudocode

```c
signed int __fastcall Windows::Compat::Inventory::GetMoreData::CaptureAslLogging(
        Windows::Compat::Inventory::GetMoreData *this)
{
  char *NamedPipeA; // rsi
  char *v3; // r14
  DWORD LastError; // ebx
  int v5; // ebx
  _DWORD *v6; // rsi
  _QWORD *v7; // rax
  __int64 v8; // rax
  _DWORD *v9; // rcx
  signed int result; // eax
  DWORD v11; // [rsp+20h] [rbp-38h]

  NamedPipeA = (char *)CreateNamedPipeA("\\\\.\\pipe\\GmdAslLogger", 1u, 0xEu, 0xFFu, 0, 0x104u, 0, 0);
  v3 = (char *)*((_QWORD *)this + 2);
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 2) = NamedPipeA;
  if ( (unsigned __int64)(NamedPipeA - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v11 = GetLastError();
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::GetMoreData::CaptureAslLogging",
      356,
      "CreateNamedPipe failed [%d]",
      v11);
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v5 = 0;
    v6 = operator new(0x10u);
    v7 = operator new(8u);
    *v7 = this;
    v8 = _o__beginthreadex(
           0,
           0,
           std::thread::_Invoke_std::tuple__lambda_b1869bd9891c80d61737e8e479659c54____0_,
           v7,
           0,
           v6 + 2);
    *(_QWORD *)v6 = v8;
    if ( v8 )
    {
      v9 = *(_DWORD **)this;
      *(_QWORD *)this = v6;
      if ( v9 )
      {
        if ( v9[2] )
        {
          _o_terminate();
          __debugbreak();
        }
        operator delete(v9);
      }
    }
    else
    {
      v6[2] = 0;
      std::_Throw_Cpp_error(6);
      return (int)v6;
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x14000dc94  mov     rax, rsp
0x14000dc97  mov     [rax+18h], rbx
0x14000dc9b  push    rsi
0x14000dc9c  push    rdi
0x14000dc9d  push    r14
0x14000dc9f  sub     rsp, 40h
0x14000dca3  mov     rdi, rcx
0x14000dca6  mov     qword ptr [rax-20h], 0
0x14000dcae  mov     dword ptr [rax-28h], 0
0x14000dcb5  mov     dword ptr [rax-30h], 104h
0x14000dcbc  mov     dword ptr [rax-38h], 0
0x14000dcc3  mov     edx, 1; dwOpenMode
0x14000dcc8  mov     r9d, 0FFh; nMaxInstances
0x14000dcce  lea     r8d, [rdx+0Dh]; dwPipeMode
0x14000dcd2  lea     rcx, Name; "\\\\.\\pipe\\GmdAslLogger"
0x14000dcd9  call    cs:__imp_CreateNamedPipeA
0x14000dcdf  mov     rsi, rax
0x14000dce2  mov     r14, [rdi+10h]
0x14000dce6  lea     rdx, [r14-1]
0x14000dcea  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14000dcee  ja      short loc_14000DD09
0x14000dcf0  call    cs:__imp_GetLastError
0x14000dcf6  mov     ebx, eax
0x14000dcf8  mov     rcx, r14; hObject
0x14000dcfb  call    cs:__imp_CloseHandle
0x14000dd01  mov     ecx, ebx; dwErrCode
0x14000dd03  call    cs:__imp_SetLastError
0x14000dd09  mov     [rdi+10h], rsi
0x14000dd0d  lea     rax, [rsi-1]
0x14000dd11  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000dd15  ja      loc_14000DDA5
0x14000dd1b  xor     ebx, ebx
0x14000dd1d  lea     ecx, [rbx+10h]; Size
0x14000dd20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000dd25  mov     rsi, rax
0x14000dd28  mov     [rsp+58h+arg_0], rax
0x14000dd2d  lea     ecx, [rbx+8]; Size
0x14000dd30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000dd35  mov     [rax], rdi
0x14000dd38  mov     [rsp+58h+arg_8], rax
0x14000dd3d  lea     r14, [rsi+8]
0x14000dd41  mov     [rsp+58h+var_30], r14
0x14000dd46  mov     [rsp+58h+var_38], ebx
0x14000dd4a  mov     r9, rax
0x14000dd4d  lea     r8, std__thread___Invoke_std__tuple__lambda_b1869bd9891c80d61737e8e479659c54____0_
0x14000dd54  xor     edx, edx
0x14000dd56  xor     ecx, ecx
0x14000dd58  call    cs:__imp__o__beginthreadex
0x14000dd5e  mov     [rsi], rax
0x14000dd61  test    rax, rax
0x14000dd64  jz      short loc_14000DD8A
0x14000dd66  mov     rcx, [rdi]; void *
0x14000dd69  mov     [rdi], rsi
0x14000dd6c  test    rcx, rcx
0x14000dd6f  jz      short loc_14000DD88
0x14000dd71  cmp     [rcx+8], ebx
0x14000dd74  jz      short loc_14000DD7D
0x14000dd76  call    cs:__imp__o_terminate
0x14000dd7c  int     3; Trap to Debugger
0x14000dd7d  mov     edx, 10h; unsigned __int64
0x14000dd82  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000dd87  nop
0x14000dd88  jmp     short loc_14000DDA1
0x14000dd8a  mov     dword ptr [r14], 0
0x14000dd91  mov     ecx, 6
0x14000dd96  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x14000dd9c  nop
0x14000dd9d  mov     ebx, dword ptr [rsp+58h+arg_0]
0x14000dda1  mov     eax, ebx
0x14000dda3  jmp     short loc_14000DDDF
0x14000dda5  call    cs:__imp_GetLastError
0x14000ddab  mov     [rsp+58h+var_38], eax
0x14000ddaf  lea     r9, aCreatenamedpip; "CreateNamedPipe failed [%d]"
0x14000ddb6  mov     r8d, 164h
0x14000ddbc  lea     rdx, aWindowsCompatI_1; "Windows::Compat::Inventory::GetMoreData"...
0x14000ddc3  mov     ecx, 1
0x14000ddc8  call    AslLogCallPrintf
0x14000ddcd  call    cs:__imp_GetLastError
0x14000ddd3  test    eax, eax
0x14000ddd5  jle     short loc_14000DDDF
0x14000ddd7  movzx   eax, ax
0x14000ddda  or      eax, 80070000h
0x14000dddf  mov     rbx, [rsp+58h+arg_10]
0x14000dde4  add     rsp, 40h
0x14000dde8  pop     r14
0x14000ddea  pop     rdi
0x14000ddeb  pop     rsi
0x14000ddec  retn
```
