# AipCheckFusion(void *,ushort const *)

- ea: `0x18000fbe4`
- end: `0x18000fda1`
- name: `?AipCheckFusion@@YAEPEAXPEBG@Z`
- size: `445`
- prototype: `bool __fastcall(void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x18000f6d0`

## callees

- `0x18000fbe4`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fd76`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000fc64`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000fc64`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000fd6d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000fd6d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000fc8d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000fc8d`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18000fd07`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18000fd07`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxSettingsW` at `0x18000fd40`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxSettingsW` at `0x18000fd40`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18000fd64`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x18000fd64`
- `ntdll!LdrResSearchResource` at `0x18000fcf9`
- `ntdll!LdrResSearchResource` at `0x18000fcf9`

## pseudocode

```c
bool __fastcall AipCheckFusion(void *a1, const unsigned __int16 *a2)
{
  bool v2; // bl
  HANDLE FileMappingW; // rax
  void *v4; // r14
  HMODULE v5; // rax
  HMODULE v6; // rdi
  HANDLE v7; // rsi
  __int64 v9; // [rsp+40h] [rbp-49h] BYREF
  __int64 v10; // [rsp+48h] [rbp-41h] BYREF
  ACTCTXW pActCtx; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v12[3]; // [rsp+88h] [rbp-1h] BYREF
  WCHAR pvBuffer[8]; // [rsp+A0h] [rbp+17h] BYREF

  pActCtx.lpSource = a2;
  v10 = 0;
  pActCtx.lpResourceName = (LPCWSTR)1;
  v9 = 0;
  pActCtx.cbSize = 56;
  *(_OWORD *)&pActCtx.wProcessorArchitecture = 0;
  v2 = 0;
  pActCtx.dwFlags = 8;
  *(_OWORD *)&pActCtx.lpApplicationName = 0;
  FileMappingW = CreateFileMappingW(a1, 0, 0x11000002u, 0, 0, 0);
  v4 = FileMappingW;
  if ( FileMappingW )
  {
    v5 = (HMODULE)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
    v6 = v5;
    if ( v5 )
    {
      pActCtx.dwFlags |= 0x80u;
      pActCtx.hModule = v5;
      v12[0] = 24;
      v12[1] = 1;
      v12[2] = 0;
      v9 = 0;
      if ( (int)((__int64 (__fastcall *)(HMODULE, _QWORD *, __int64, __int64, __int64 *, __int64 *, _QWORD, _QWORD))LdrResSearchResource)(
                  v5,
                  v12,
                  3,
                  48,
                  &v10,
                  &v9,
                  0,
                  0) >= 0 )
      {
        v7 = CreateActCtxW(&pActCtx);
        if ( v7 != (HANDLE)-1LL )
        {
          if ( QueryActCtxSettingsW(0, v7, 0, L"autoElevate", pvBuffer, 8u, 0) )
            v2 = ((pvBuffer[0] - 84) & 0xFFDF) == 0;
          ReleaseActCtx(v7);
        }
      }
      UnmapViewOfFile(v6);
    }
    CloseHandle(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x18000fbe4  mov     [rsp-8+arg_10], rbx
0x18000fbe9  push    rbp
0x18000fbea  push    rsi
0x18000fbeb  push    rdi
0x18000fbec  push    r12
0x18000fbee  push    r14
0x18000fbf0  lea     rbp, [rsp-37h]
0x18000fbf5  sub     rsp, 0C0h
0x18000fbfc  mov     rax, cs:__security_cookie
0x18000fc03  xor     rax, rsp
0x18000fc06  mov     [rbp+57h+var_30], rax
0x18000fc0a  xorps   xmm0, xmm0
0x18000fc0d  mov     [rbp+57h+pActCtx.lpSource], rdx
0x18000fc11  xorps   xmm1, xmm1
0x18000fc14  mov     [rsp+0E0h+lpName], 0; lpName
0x18000fc1d  mov     r12d, 1
0x18000fc23  mov     [rbp+57h+var_98], 0
0x18000fc2b  xor     edx, edx; lpFileMappingAttributes
0x18000fc2d  mov     [rbp+57h+pActCtx.lpResourceName], r12
0x18000fc31  xor     r9d, r9d; dwMaximumSizeHigh
0x18000fc34  mov     [rbp+57h+var_A0], 0
0x18000fc3c  mov     r8d, 11000002h; flProtect
0x18000fc42  mov     [rbp+57h+pActCtx.cbSize], 38h ; '8'
0x18000fc49  movdqu  xmmword ptr [rbp+57h+pActCtx.wProcessorArchitecture], xmm0
0x18000fc4e  xor     bl, bl
0x18000fc50  mov     [rbp+57h+pActCtx.dwFlags], 8
0x18000fc57  movdqu  xmmword ptr [rbp+57h+pActCtx.lpApplicationName], xmm1
0x18000fc5c  mov     [rsp+0E0h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x18000fc64  call    cs:__imp_CreateFileMappingW
0x18000fc6a  mov     r14, rax
0x18000fc6d  test    rax, rax
0x18000fc70  jz      loc_18000FD7C
0x18000fc76  xor     r9d, r9d; dwFileOffsetLow
0x18000fc79  mov     qword ptr [rsp+0E0h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18000fc82  xor     r8d, r8d; dwFileOffsetHigh
0x18000fc85  lea     edx, [r12+3]; dwDesiredAccess
0x18000fc8a  mov     rcx, rax; hFileMappingObject
0x18000fc8d  call    cs:__imp_MapViewOfFile
0x18000fc93  mov     rdi, rax
0x18000fc96  test    rax, rax
0x18000fc99  jz      loc_18000FD73
0x18000fc9f  bts     [rbp+57h+pActCtx.dwFlags], 7
0x18000fca4  lea     r9d, [r12+2Fh]
0x18000fca9  mov     [rbp+57h+pActCtx.hModule], rax
0x18000fcad  lea     r8d, [r12+2]
0x18000fcb2  mov     [rsp+0E0h+var_A8], 0
0x18000fcbb  lea     rax, [rbp+57h+var_A0]
0x18000fcbf  mov     [rsp+0E0h+pdwWrittenOrRequired], 0
0x18000fcc8  lea     rdx, [rbp+57h+var_58]
0x18000fccc  mov     [rsp+0E0h+lpName], rax
0x18000fcd1  mov     rcx, rdi
0x18000fcd4  lea     rax, [rbp+57h+var_98]
0x18000fcd8  mov     [rbp+57h+var_58], 18h
0x18000fce0  mov     qword ptr [rsp+0E0h+dwMaximumSizeLow], rax
0x18000fce5  mov     [rbp+57h+var_50], r12
0x18000fce9  mov     [rbp+57h+var_48], 0
0x18000fcf1  mov     [rbp+57h+var_A0], 0
0x18000fcf9  call    cs:__imp_LdrResSearchResource
0x18000fcff  test    eax, eax
0x18000fd01  js      short loc_18000FD6A
0x18000fd03  lea     rcx, [rbp+57h+pActCtx]; pActCtx
0x18000fd07  call    cs:__imp_CreateActCtxW
0x18000fd0d  mov     rsi, rax
0x18000fd10  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fd14  jz      short loc_18000FD6A
0x18000fd16  mov     [rsp+0E0h+pdwWrittenOrRequired], 0; pdwWrittenOrRequired
0x18000fd1f  lea     rax, [rbp+57h+pvBuffer]
0x18000fd23  mov     [rsp+0E0h+lpName], 8; dwBuffer
0x18000fd2c  lea     r9, settingName; "autoElevate"
0x18000fd33  xor     r8d, r8d; settingsNameSpace
0x18000fd36  mov     qword ptr [rsp+0E0h+dwMaximumSizeLow], rax; pvBuffer
0x18000fd3b  mov     rdx, rsi; hActCtx
0x18000fd3e  xor     ecx, ecx; dwFlags
0x18000fd40  call    cs:__imp_QueryActCtxSettingsW
0x18000fd46  test    eax, eax
0x18000fd48  jz      short loc_18000FD61
0x18000fd4a  movzx   eax, [rbp+57h+pvBuffer]
0x18000fd4e  mov     ecx, 0FFDFh
0x18000fd53  sub     ax, 54h ; 'T'
0x18000fd57  movzx   ebx, bl
0x18000fd5a  test    cx, ax
0x18000fd5d  cmovz   ebx, r12d
0x18000fd61  mov     rcx, rsi; hActCtx
0x18000fd64  call    cs:__imp_ReleaseActCtx
0x18000fd6a  mov     rcx, rdi; lpBaseAddress
0x18000fd6d  call    cs:__imp_UnmapViewOfFile
0x18000fd73  mov     rcx, r14; hObject
0x18000fd76  call    cs:__imp_CloseHandle
0x18000fd7c  mov     al, bl
0x18000fd7e  mov     rcx, [rbp+57h+var_30]
0x18000fd82  xor     rcx, rsp; StackCookie
0x18000fd85  call    __security_check_cookie
0x18000fd8a  mov     rbx, [rsp+0E0h+arg_10]
0x18000fd92  add     rsp, 0C0h
0x18000fd99  pop     r14
0x18000fd9b  pop     r12
0x18000fd9d  pop     rdi
0x18000fd9e  pop     rsi
0x18000fd9f  pop     rbp
0x18000fda0  retn
```
