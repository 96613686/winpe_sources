# AipCheckFusion(void *,ushort const *)

- ea: `0x180010040`
- end: `0x18001024a`
- name: `?AipCheckFusion@@YAEPEAXPEBG@Z`
- size: `522`
- prototype: `unsigned __int8 __fastcall(void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x18000fac0`

## callees

- `0x180010040`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010213`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010213`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180010204`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180010204`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800100b7`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800100b7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800100e9`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800100e9`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18001017f`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18001017f`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800101ed`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800101ed`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxSettingsW` at `0x1800101be`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxSettingsW` at `0x1800101be`
- `ntdll!LdrResSearchResource` at `0x18001015e`
- `ntdll!LdrResSearchResource` at `0x18001015e`

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
0x180010040  push    rsi
0x180010042  push    rdi
0x180010043  push    r14
0x180010045  push    r15
0x180010047  sub     rsp, 0C8h
0x18001004e  mov     rax, cs:__security_cookie
0x180010055  xor     rax, rsp
0x180010058  mov     [rsp+0E8h+var_38], rax
0x180010060  xor     r14d, r14d
0x180010063  mov     [rsp+0E8h+pActCtx.lpSource], rdx
0x180010068  xorps   xmm0, xmm0
0x18001006b  mov     [rsp+0E8h+lpName], r14; lpName
0x180010070  xorps   xmm1, xmm1
0x180010073  mov     [rsp+0E8h+dwMaximumSizeLow], r14d; dwMaximumSizeLow
0x180010078  mov     r15d, 1
0x18001007e  mov     [rsp+0E8h+var_A0], r14
0x180010083  xor     r9d, r9d; dwMaximumSizeHigh
0x180010086  mov     [rsp+0E8h+var_A8], r14
0x18001008b  xor     edx, edx; lpFileMappingAttributes
0x18001008d  mov     [rsp+0E8h+pActCtx.cbSize], 38h ; '8'
0x180010095  mov     r8d, 11000002h; flProtect
0x18001009b  mov     [rsp+0E8h+pActCtx.lpResourceName], r15
0x1800100a0  xor     dil, dil
0x1800100a3  mov     [rsp+0E8h+pActCtx.dwFlags], 8
0x1800100ab  movdqu  xmmword ptr [rsp+0E8h+pActCtx.wProcessorArchitecture], xmm0
0x1800100b1  movdqu  xmmword ptr [rsp+0E8h+pActCtx.lpApplicationName], xmm1
0x1800100b7  call    cs:__imp_CreateFileMappingW
0x1800100be  nop     dword ptr [rax+rax+00h]
0x1800100c3  mov     rsi, rax
0x1800100c6  test    rax, rax
0x1800100c9  jz      loc_180010227
0x1800100cf  xor     r9d, r9d; dwFileOffsetLow
0x1800100d2  mov     [rsp+0E8h+arg_10], rbx
0x1800100da  xor     r8d, r8d; dwFileOffsetHigh
0x1800100dd  mov     qword ptr [rsp+0E8h+dwMaximumSizeLow], r14; dwNumberOfBytesToMap
0x1800100e2  lea     edx, [r14+4]; dwDesiredAccess
0x1800100e6  mov     rcx, rax; hFileMappingObject
0x1800100e9  call    cs:__imp_MapViewOfFile
0x1800100f0  nop     dword ptr [rax+rax+00h]
0x1800100f5  mov     rbx, rax
0x1800100f8  test    rax, rax
0x1800100fb  jz      loc_180010210
0x180010101  or      [rsp+0E8h+pActCtx.dwFlags], 80h
0x180010109  lea     r9d, [r14+30h]
0x18001010d  mov     [rsp+0E8h+pActCtx.hModule], rax
0x180010115  lea     r8d, [r14+3]
0x180010119  mov     [rsp+0E8h+var_B0], r14
0x18001011e  lea     rax, [rsp+0E8h+var_A8]
0x180010123  mov     [rsp+0E8h+pdwWrittenOrRequired], r14
0x180010128  lea     rdx, [rsp+0E8h+var_60]
0x180010130  mov     [rsp+0E8h+lpName], rax
0x180010135  mov     rcx, rbx
0x180010138  lea     rax, [rsp+0E8h+var_A0]
0x18001013d  mov     [rsp+0E8h+var_60], 18h
0x180010149  mov     qword ptr [rsp+0E8h+dwMaximumSizeLow], rax
0x18001014e  mov     [rsp+0E8h+var_58], r15
0x180010156  mov     [rsp+0E8h+var_50], r14
0x18001015e  call    cs:__imp_LdrResSearchResource
0x180010165  nop     dword ptr [rax+rax+00h]
0x18001016a  test    eax, eax
0x18001016c  js      loc_180010201
0x180010172  lea     rcx, [rsp+0E8h+pActCtx]; pActCtx
0x180010177  mov     [rsp+0E8h+var_28], rbp
0x18001017f  call    cs:__imp_CreateActCtxW
0x180010186  nop     dword ptr [rax+rax+00h]
0x18001018b  mov     rbp, rax
0x18001018e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010192  jz      short loc_1800101F9
0x180010194  mov     [rsp+0E8h+pdwWrittenOrRequired], r14; pdwWrittenOrRequired
0x180010199  lea     rax, [rsp+0E8h+pvBuffer]
0x1800101a1  mov     [rsp+0E8h+lpName], 8; dwBuffer
0x1800101aa  lea     r9, settingName; "autoElevate"
0x1800101b1  xor     r8d, r8d; settingsNameSpace
0x1800101b4  mov     qword ptr [rsp+0E8h+dwMaximumSizeLow], rax; pvBuffer
0x1800101b9  mov     rdx, rbp; hActCtx
0x1800101bc  xor     ecx, ecx; dwFlags
0x1800101be  call    cs:__imp_QueryActCtxSettingsW
0x1800101c5  nop     dword ptr [rax+rax+00h]
0x1800101ca  test    eax, eax
0x1800101cc  jz      short loc_1800101EA
0x1800101ce  movzx   eax, [rsp+0E8h+pvBuffer]
0x1800101d6  mov     ecx, 0FFDFh
0x1800101db  sub     ax, 54h ; 'T'
0x1800101df  movzx   edi, dil
0x1800101e3  test    cx, ax
0x1800101e6  cmovz   edi, r15d
0x1800101ea  mov     rcx, rbp; hActCtx
0x1800101ed  call    cs:__imp_ReleaseActCtx
0x1800101f4  nop     dword ptr [rax+rax+00h]
0x1800101f9  mov     rbp, [rsp+0E8h+var_28]
0x180010201  mov     rcx, rbx; lpBaseAddress
0x180010204  call    cs:__imp_UnmapViewOfFile
0x18001020b  nop     dword ptr [rax+rax+00h]
0x180010210  mov     rcx, rsi; hObject
0x180010213  call    cs:__imp_CloseHandle
0x18001021a  nop     dword ptr [rax+rax+00h]
0x18001021f  mov     rbx, [rsp+0E8h+arg_10]
0x180010227  movzx   eax, dil
0x18001022b  mov     rcx, [rsp+0E8h+var_38]
0x180010233  xor     rcx, rsp; StackCookie
0x180010236  call    __security_check_cookie
0x18001023b  add     rsp, 0C8h
0x180010242  pop     r15
0x180010244  pop     r14
0x180010246  pop     rdi
0x180010247  pop     rsi
0x180010248  retn
```
