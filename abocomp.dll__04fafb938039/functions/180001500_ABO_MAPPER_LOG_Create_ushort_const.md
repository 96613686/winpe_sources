# ABO_MAPPER_LOG::Create(ushort const *)

- ea: `0x180001500`
- end: `0x18000157b`
- name: `?Create@ABO_MAPPER_LOG@@QEAAJPEBG@Z`
- size: `123`
- prototype: `__int64 __fastcall(ABO_MAPPER_LOG *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callers

- `0x180001010`

## callees

- `0x180001500`
- `0x1800270a4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000392d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000392d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003998`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003963`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180003963`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000398a`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000398a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001573`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001573`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000390d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000390d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001551`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001551`

## string_xrefs

- `0x180001531`: `System\CurrentControlSet\Services\IISADMIN\Parameters`

## pseudocode

```c
__int64 __fastcall ABO_MAPPER_LOG::Create(ABO_MAPPER_LOG *this, const unsigned __int16 *a2)
{
  ABO_MAPPER_LOG *v2; // rdi
  unsigned int v3; // ebx
  void *v5; // rcx
  HANDLE FileW; // rax
  const unsigned __int16 *v7; // rdx
  ABO_MAPPER_LOG *v8; // rcx
  int v9; // eax
  signed int LastError; // eax
  DWORD Type; // [rsp+60h] [rbp+8h] BYREF
  int v12; // [rsp+64h] [rbp+Ch]
  DWORD cbData; // [rsp+68h] [rbp+10h] BYREF
  int v14; // [rsp+6Ch] [rbp+14h]
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  v14 = HIDWORD(a2);
  v12 = HIDWORD(this);
  v2 = g_pAboLog;
  hKey = 0;
  Type = 0;
  cbData = 0;
  v3 = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\IISADMIN\\Parameters",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"EnableABOMapperLog", 0, &Type, (LPBYTE)v2 + 16, &cbData) )
    {
      if ( *((_DWORD *)v2 + 4) )
      {
        v5 = (void *)*((_QWORD *)v2 + 1);
        if ( v5 != (void *)-1LL )
        {
          CloseHandle(v5);
          *((_QWORD *)v2 + 1) = -1;
        }
        FileW = CreateFileW(L"abomapper.log", 0x40000000u, 1u, 0, 4u, 0x80u, 0);
        *((_QWORD *)v2 + 1) = FileW;
        if ( FileW == (HANDLE)-1LL )
          goto LABEL_13;
        v9 = ABO_MAPPER_LOG::SetAdminACLOnLogFile(v8, v7);
        if ( v9 >= 0 )
          v3 = v9;
        if ( !SetFilePointerEx(*((HANDLE *)v2 + 1), 0, 0, 2u) )
        {
LABEL_13:
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180001500  mov     rax, rsp
0x180001503  mov     [rax+10h], rdx
0x180001507  mov     [rax+8], rcx
0x18000150b  push    rbx
0x18000150c  push    rsi
0x18000150d  push    rdi
0x18000150e  sub     rsp, 40h
0x180001512  mov     rdi, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; ABO_MAPPER_LOG * g_pAboLog
0x180001519  mov     r9d, 20019h; samDesired
0x18000151f  mov     qword ptr [rax+18h], 0
0x180001527  xor     r8d, r8d; ulOptions
0x18000152a  mov     dword ptr [rax+8], 0
0x180001531  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\II"...
0x180001538  mov     dword ptr [rax+10h], 0
0x18000153f  lea     rax, [rax+18h]
0x180001543  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000154a  mov     [rsp+58h+phkResult], rax; phkResult
0x18000154f  xor     ebx, ebx
0x180001551  call    cs:__imp_RegOpenKeyExW
0x180001557  test    eax, eax
0x180001559  jz      loc_1800038DE
0x18000155f  mov     rcx, [rsp+58h+hKey]; hKey
0x180001564  test    rcx, rcx
0x180001567  jnz     short loc_180001573
0x180001569  mov     eax, ebx
0x18000156b  add     rsp, 40h
0x18000156f  pop     rdi
0x180001570  pop     rsi
0x180001571  pop     rbx
0x180001572  retn
0x180001573  call    cs:__imp_RegCloseKey
0x180001579  jmp     short loc_180001569
0x1800038de  mov     rcx, [rsp+58h+hKey]; hKey
0x1800038e3  lea     rax, [rsp+58h+cbData]
0x1800038e8  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800038ed  lea     rsi, [rdi+10h]
0x1800038f1  lea     r9, [rsp+58h+Type]; lpType
0x1800038f6  mov     [rsp+58h+phkResult], rsi; lpData
0x1800038fb  xor     r8d, r8d; lpReserved
0x1800038fe  mov     [rsp+58h+cbData], 4
0x180003906  lea     rdx, ValueName; "EnableABOMapperLog"
0x18000390d  call    cs:__imp_RegQueryValueExW
0x180003913  test    eax, eax
0x180003915  jnz     loc_18000155F
0x18000391b  cmp     [rsi], ebx
0x18000391d  jz      loc_18000155F
0x180003923  mov     rcx, [rdi+8]; hObject
0x180003927  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000392b  jz      short loc_18000393B
0x18000392d  call    cs:__imp_CloseHandle
0x180003933  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18000393b  xor     r9d, r9d; lpSecurityAttributes
0x18000393e  mov     [rsp+58h+hTemplateFile], rbx; hTemplateFile
0x180003943  mov     dword ptr [rsp+58h+lpcbData], 80h; dwFlagsAndAttributes
0x18000394b  lea     rcx, pObjectName; "abomapper.log"
0x180003952  mov     edx, 40000000h; dwDesiredAccess
0x180003957  mov     dword ptr [rsp+58h+phkResult], 4; dwCreationDisposition
0x18000395f  lea     r8d, [r9+1]; dwShareMode
0x180003963  call    cs:__imp_CreateFileW
0x180003969  mov     [rdi+8], rax
0x18000396d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003971  jz      short loc_180003998
0x180003973  call    ?SetAdminACLOnLogFile@ABO_MAPPER_LOG@@QEAAJPEBG@Z; ABO_MAPPER_LOG::SetAdminACLOnLogFile(ushort const *)
0x180003978  mov     rcx, [rdi+8]; hFile
0x18000397c  test    eax, eax
0x18000397e  cmovns  ebx, eax
0x180003981  xor     edx, edx; liDistanceToMove
0x180003983  xor     r8d, r8d; lpNewFilePointer
0x180003986  lea     r9d, [rdx+2]; dwMoveMethod
0x18000398a  call    cs:__imp_SetFilePointerEx
0x180003990  test    eax, eax
0x180003992  jnz     loc_18000155F
0x180003998  call    cs:__imp_GetLastError
0x18000399e  mov     ebx, eax
0x1800039a0  test    eax, eax
0x1800039a2  jle     loc_18000155F
0x1800039a8  movzx   ebx, ax
0x1800039ab  or      ebx, 80070000h
0x1800039b1  jmp     loc_18000155F
```
