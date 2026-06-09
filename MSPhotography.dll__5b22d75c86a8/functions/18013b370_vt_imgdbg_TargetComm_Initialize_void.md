# vt::imgdbg::TargetComm::Initialize(void)

- ea: `0x18013b370`
- end: `0x18013b484`
- name: `?Initialize@TargetComm@imgdbg@vt@@AEAAXXZ`
- size: `276`
- prototype: `void __fastcall(vt::imgdbg::TargetComm *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18013b2f0`

## callees

- `0x180002420`
- `0x18013b24c`
- `0x18013b284`
- `0x18013b370`
- `0x18013ebf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013b3ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013b3ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18013b398`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18013b430`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18013b398`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18013b430`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18013b412`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18013b412`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18013b3d8`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18013b3d8`

## string_xrefs

- `0x18013b453`: `Error in CreateFileMapping()\n`

## pseudocode

```c
void __fastcall vt::imgdbg::TargetComm::Initialize(vt::imgdbg::TargetComm *this)
{
  DWORD CurrentProcessId; // eax
  const unsigned __int16 *v2; // rdx
  __int64 v3; // rbx
  wchar_t *v4; // rcx
  WCHAR Name[256]; // [rsp+30h] [rbp-218h] BYREF

  if ( !`vt::imgdbg::TargetComm::GetInstance'::`2'::instance )
  {
    CurrentProcessId = GetCurrentProcessId();
    swprintf_s<256>(Name, L"_%s_%u_", L"IDV", CurrentProcessId);
    hFileMappingObject = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x7800Cu, Name);
    if ( !hFileMappingObject || GetLastError() == 183 )
    {
      v4 = L"Error in CreateFileMapping()\n";
    }
    else
    {
      *(&hFileMappingObject + 1) = MapViewOfFile(hFileMappingObject, 0xF001Fu, 0, 0, 0);
      v3 = (__int64)*(&hFileMappingObject + 1);
      if ( *(&hFileMappingObject + 1) )
      {
        *(_DWORD *)v3 = GetCurrentProcessId();
        *(_QWORD *)(v3 + 4) = 8;
        dword_180160A20 = 0;
        `vt::imgdbg::TargetComm::GetInstance'::`2'::instance = 1;
        return;
      }
      v4 = L"Error in MapViewOfFile()\n";
    }
    vt::MFDebugLog((vt *)v4, v2);
    vt::imgdbg::TargetComm::CleanUp((vt::imgdbg::TargetComm *)&`vt::imgdbg::TargetComm::GetInstance'::`2'::instance);
  }
}

```

## disassembly

```asm
0x18013b370  push    rbx
0x18013b372  sub     rsp, 240h
0x18013b379  mov     rax, cs:__security_cookie
0x18013b380  xor     rax, rsp
0x18013b383  mov     [rsp+248h+var_18], rax
0x18013b38b  cmp     cs:?instance@?1??GetInstance@TargetComm@imgdbg@vt@@CAAEAV234@XZ@4V234@A, 0; vt::imgdbg::TargetComm `vt::imgdbg::TargetComm::GetInstance(void)'::`2'::instance
0x18013b392  jnz     loc_18013B46B
0x18013b398  call    cs:__imp_GetCurrentProcessId
0x18013b39e  mov     r9d, eax
0x18013b3a1  lea     r8, aIdv; "IDV"
0x18013b3a8  lea     rdx, aSU; "_%s_%u_"
0x18013b3af  lea     rcx, [rsp+248h+Name]
0x18013b3b4  call    ??$swprintf_s@$0BAA@@@YAHAEAY0BAA@GPEBGZZ; swprintf_s<256>(ushort (&)[256],ushort const *,...)
0x18013b3b9  xor     r9d, r9d; dwMaximumSizeHigh
0x18013b3bc  lea     rax, [rsp+248h+Name]
0x18013b3c1  mov     [rsp+248h+lpName], rax; lpName
0x18013b3c6  xor     edx, edx; lpFileMappingAttributes
0x18013b3c8  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18013b3cc  mov     [rsp+248h+dwMaximumSizeLow], 7800Ch; dwMaximumSizeLow
0x18013b3d4  lea     r8d, [r9+4]; flProtect
0x18013b3d8  call    cs:__imp_CreateFileMappingW
0x18013b3de  mov     qword ptr cs:hFileMappingObject, rax
0x18013b3e5  test    rax, rax
0x18013b3e8  jz      short loc_18013B453
0x18013b3ea  call    cs:__imp_GetLastError
0x18013b3f0  cmp     eax, 0B7h
0x18013b3f5  jz      short loc_18013B453
0x18013b3f7  mov     rcx, qword ptr cs:hFileMappingObject; hFileMappingObject
0x18013b3fe  xor     r9d, r9d; dwFileOffsetLow
0x18013b401  xor     r8d, r8d; dwFileOffsetHigh
0x18013b404  mov     qword ptr [rsp+248h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x18013b40d  mov     edx, 0F001Fh; dwDesiredAccess
0x18013b412  call    cs:__imp_MapViewOfFile
0x18013b418  mov     qword ptr cs:hFileMappingObject+8, rax
0x18013b41f  mov     rbx, rax
0x18013b422  test    rax, rax
0x18013b425  jnz     short loc_18013B430
0x18013b427  lea     rcx, aErrorInMapview; "Error in MapViewOfFile()\n"
0x18013b42e  jmp     short loc_18013B45A
0x18013b430  call    cs:__imp_GetCurrentProcessId
0x18013b436  mov     [rbx], eax
0x18013b438  mov     qword ptr [rbx+4], 8
0x18013b440  mov     cs:dword_180160A20, 0
0x18013b44a  mov     cs:?instance@?1??GetInstance@TargetComm@imgdbg@vt@@CAAEAV234@XZ@4V234@A, 1; vt::imgdbg::TargetComm `vt::imgdbg::TargetComm::GetInstance(void)'::`2'::instance
0x18013b451  jmp     short loc_18013B46B
0x18013b453  lea     rcx, aErrorInCreatef; "Error in CreateFileMapping()\n"
0x18013b45a  call    ?MFDebugLog@vt@@YAXPEBGZZ; vt::MFDebugLog(ushort const *,...)
0x18013b45f  lea     rcx, ?instance@?1??GetInstance@TargetComm@imgdbg@vt@@CAAEAV234@XZ@4V234@A; this
0x18013b466  call    ?CleanUp@TargetComm@imgdbg@vt@@AEAAXXZ; vt::imgdbg::TargetComm::CleanUp(void)
0x18013b46b  mov     rcx, [rsp+248h+var_18]
0x18013b473  xor     rcx, rsp; StackCookie
0x18013b476  call    __security_check_cookie
0x18013b47b  add     rsp, 240h
0x18013b482  pop     rbx
0x18013b483  retn
```
