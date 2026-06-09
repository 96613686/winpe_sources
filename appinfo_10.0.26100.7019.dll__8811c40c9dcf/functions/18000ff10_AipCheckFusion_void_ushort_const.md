# AipCheckFusion(void *,ushort const *)

- ea: `0x18000ff10`
- end: `0x18001011a`
- name: `?AipCheckFusion@@YAEPEAXPEBG@Z`
- size: `522`
- prototype: `unsigned __int8 __fastcall(void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x18000f990`

## callees

- `0x18000ff10`
- `0x180042950`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800100e3`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800100d4`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800100d4`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000ffb9`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000ffb9`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000ff87`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000ff87`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18001004f`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18001004f`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxSettingsW` at `0x18001008e`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxSettingsW` at `0x18001008e`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800100bd`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800100bd`
- `ntdll!LdrResSearchResource` at `0x18001002e`
- `ntdll!LdrResSearchResource` at `0x18001002e`

## pseudocode

```c
_BOOL8 __fastcall AipCheckFusion(void *a1, const unsigned __int16 *a2)
{
  bool v2; // di
  HANDLE FileMappingW; // rax
  void *v4; // rsi
  HMODULE v5; // rax
  HMODULE v6; // rbx
  HANDLE v7; // rbp
  __int64 v9; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v10; // [rsp+48h] [rbp-A0h] BYREF
  ACTCTXW pActCtx; // [rsp+50h] [rbp-98h] BYREF
  _QWORD v12[3]; // [rsp+88h] [rbp-60h] BYREF
  WCHAR pvBuffer[8]; // [rsp+A0h] [rbp-48h] BYREF

  pActCtx.lpSource = a2;
  v10 = 0;
  v9 = 0;
  pActCtx.cbSize = 56;
  pActCtx.lpResourceName = (LPCWSTR)1;
  v2 = 0;
  pActCtx.dwFlags = 8;
  *(_OWORD *)&pActCtx.wProcessorArchitecture = 0;
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
0x18000ff10  push    rsi
0x18000ff12  push    rdi
0x18000ff13  push    r14
0x18000ff15  push    r15
0x18000ff17  sub     rsp, 0C8h
0x18000ff1e  mov     rax, cs:__security_cookie
0x18000ff25  xor     rax, rsp
0x18000ff28  mov     [rsp+0E8h+var_38], rax
0x18000ff30  xor     r14d, r14d
0x18000ff33  mov     [rsp+0E8h+pActCtx.lpSource], rdx
0x18000ff38  xorps   xmm0, xmm0
0x18000ff3b  mov     [rsp+0E8h+lpName], r14; lpName
0x18000ff40  xorps   xmm1, xmm1
0x18000ff43  mov     [rsp+0E8h+dwMaximumSizeLow], r14d; dwMaximumSizeLow
0x18000ff48  mov     r15d, 1
0x18000ff4e  mov     [rsp+0E8h+var_A0], r14
0x18000ff53  xor     r9d, r9d; dwMaximumSizeHigh
0x18000ff56  mov     [rsp+0E8h+var_A8], r14
0x18000ff5b  xor     edx, edx; lpFileMappingAttributes
0x18000ff5d  mov     [rsp+0E8h+pActCtx.cbSize], 38h ; '8'
0x18000ff65  mov     r8d, 11000002h; flProtect
0x18000ff6b  mov     [rsp+0E8h+pActCtx.lpResourceName], r15
0x18000ff70  xor     dil, dil
0x18000ff73  mov     [rsp+0E8h+pActCtx.dwFlags], 8
0x18000ff7b  movdqu  xmmword ptr [rsp+0E8h+pActCtx.wProcessorArchitecture], xmm0
0x18000ff81  movdqu  xmmword ptr [rsp+0E8h+pActCtx.lpApplicationName], xmm1
0x18000ff87  call    cs:__imp_CreateFileMappingW
0x18000ff8e  nop     dword ptr [rax+rax+00h]
0x18000ff93  mov     rsi, rax
0x18000ff96  test    rax, rax
0x18000ff99  jz      loc_1800100F7
0x18000ff9f  xor     r9d, r9d; dwFileOffsetLow
0x18000ffa2  mov     [rsp+0E8h+arg_10], rbx
0x18000ffaa  xor     r8d, r8d; dwFileOffsetHigh
0x18000ffad  mov     qword ptr [rsp+0E8h+dwMaximumSizeLow], r14; dwNumberOfBytesToMap
0x18000ffb2  lea     edx, [r14+4]; dwDesiredAccess
0x18000ffb6  mov     rcx, rax; hFileMappingObject
0x18000ffb9  call    cs:__imp_MapViewOfFile
0x18000ffc0  nop     dword ptr [rax+rax+00h]
0x18000ffc5  mov     rbx, rax
0x18000ffc8  test    rax, rax
0x18000ffcb  jz      loc_1800100E0
0x18000ffd1  or      [rsp+0E8h+pActCtx.dwFlags], 80h
0x18000ffd9  lea     r9d, [r14+30h]
0x18000ffdd  mov     [rsp+0E8h+pActCtx.hModule], rax
0x18000ffe5  lea     r8d, [r14+3]
0x18000ffe9  mov     [rsp+0E8h+var_B0], r14
0x18000ffee  lea     rax, [rsp+0E8h+var_A8]
0x18000fff3  mov     [rsp+0E8h+pdwWrittenOrRequired], r14
0x18000fff8  lea     rdx, [rsp+0E8h+var_60]
0x180010000  mov     [rsp+0E8h+lpName], rax
0x180010005  mov     rcx, rbx
0x180010008  lea     rax, [rsp+0E8h+var_A0]
0x18001000d  mov     [rsp+0E8h+var_60], 18h
0x180010019  mov     qword ptr [rsp+0E8h+dwMaximumSizeLow], rax
0x18001001e  mov     [rsp+0E8h+var_58], r15
0x180010026  mov     [rsp+0E8h+var_50], r14
0x18001002e  call    cs:__imp_LdrResSearchResource
0x180010035  nop     dword ptr [rax+rax+00h]
0x18001003a  test    eax, eax
0x18001003c  js      loc_1800100D1
0x180010042  lea     rcx, [rsp+0E8h+pActCtx]; pActCtx
0x180010047  mov     [rsp+0E8h+var_28], rbp
0x18001004f  call    cs:__imp_CreateActCtxW
0x180010056  nop     dword ptr [rax+rax+00h]
0x18001005b  mov     rbp, rax
0x18001005e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010062  jz      short loc_1800100C9
0x180010064  mov     [rsp+0E8h+pdwWrittenOrRequired], r14; pdwWrittenOrRequired
0x180010069  lea     rax, [rsp+0E8h+pvBuffer]
0x180010071  mov     [rsp+0E8h+lpName], 8; dwBuffer
0x18001007a  lea     r9, settingName; "autoElevate"
0x180010081  xor     r8d, r8d; settingsNameSpace
0x180010084  mov     qword ptr [rsp+0E8h+dwMaximumSizeLow], rax; pvBuffer
0x180010089  mov     rdx, rbp; hActCtx
0x18001008c  xor     ecx, ecx; dwFlags
0x18001008e  call    cs:__imp_QueryActCtxSettingsW
0x180010095  nop     dword ptr [rax+rax+00h]
0x18001009a  test    eax, eax
0x18001009c  jz      short loc_1800100BA
0x18001009e  movzx   eax, [rsp+0E8h+pvBuffer]
0x1800100a6  mov     ecx, 0FFDFh
0x1800100ab  sub     ax, 54h ; 'T'
0x1800100af  movzx   edi, dil
0x1800100b3  test    cx, ax
0x1800100b6  cmovz   edi, r15d
0x1800100ba  mov     rcx, rbp; hActCtx
0x1800100bd  call    cs:__imp_ReleaseActCtx
0x1800100c4  nop     dword ptr [rax+rax+00h]
0x1800100c9  mov     rbp, [rsp+0E8h+var_28]
0x1800100d1  mov     rcx, rbx; lpBaseAddress
0x1800100d4  call    cs:__imp_UnmapViewOfFile
0x1800100db  nop     dword ptr [rax+rax+00h]
0x1800100e0  mov     rcx, rsi; hObject
0x1800100e3  call    cs:__imp_CloseHandle
0x1800100ea  nop     dword ptr [rax+rax+00h]
0x1800100ef  mov     rbx, [rsp+0E8h+arg_10]
0x1800100f7  movzx   eax, dil
0x1800100fb  mov     rcx, [rsp+0E8h+var_38]
0x180010103  xor     rcx, rsp; StackCookie
0x180010106  call    __security_check_cookie
0x18001010b  add     rsp, 0C8h
0x180010112  pop     r15
0x180010114  pop     r14
0x180010116  pop     rdi
0x180010117  pop     rsi
0x180010118  retn
```
