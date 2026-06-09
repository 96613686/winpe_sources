# BfspServiceDebuggerFiles

- ea: `0x18004b980`
- end: `0x18004bc8d`
- name: `BfspServiceDebuggerFiles`
- size: `781`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x180049234`

## callees

- `0x1800078b0`
- `0x18001bd50`
- `0x18001bddc`
- `0x1800466c0`
- `0x18004a678`
- `0x18004b980`
- `0x18004cdd4`
- `0x1800513d4`
- `0x1800515f4`
- `0x180059278`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18004bb40`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18004bb40`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bc18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bc2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bc45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bc5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bc18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bc2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bc45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004bc5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ba93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bc0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bc1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bc37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bc50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ba93`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bc0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bc1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bc37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004bc50`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004baa7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004baa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bbb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bbb5`
- `KERNEL32!GetPrivateProfileSectionW` at `0x18004bad8`
- `KERNEL32!GetPrivateProfileSectionW` at `0x18004bad8`

## string_xrefs

- `0x18004bab5`: `ServiceDebuggerFiles: Failed to allocate config buffer`
- `0x18004ba6b`: `ServiceDebuggerFiles: %ws does not exist`
- `0x18004bb80`: `Copying boot debugging files from %ws to %ws (%ws)`
- `0x18004bbcc`: `Error copying boot debugging files from %ws to %ws (%ws). Last Error = %#x`
- `0x18004baf7`: `ServiceDebuggerFiles: ConfigBuffer is too small`

## pseudocode

```c
__int64 __fastcall BfspServiceDebuggerFiles(__int64 a1)
{
  WCHAR *v2; // r13
  WCHAR *v3; // rsi
  unsigned __int16 *v4; // rbx
  WCHAR *v5; // r15
  const wchar_t *Value; // rax
  int v7; // ebp
  const WCHAR *v8; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v10; // rax
  DWORD PrivateProfileSectionW; // eax
  DWORD v12; // ebp
  const wchar_t *v13; // rdi
  __int64 v14; // r12
  wchar_t *v15; // rax
  const unsigned __int16 *v16; // r14
  __int64 v17; // rax
  HANDLE v18; // rax
  HANDLE v19; // rax
  HANDLE v20; // rax
  HANDLE v21; // rax
  __int64 v23; // [rsp+28h] [rbp-290h]
  BOOL v24; // [rsp+40h] [rbp-278h]
  const WCHAR *v25; // [rsp+48h] [rbp-270h]
  unsigned __int16 v26[264]; // [rsp+50h] [rbp-268h] BYREF

  BfspLogMessage(2, L"Servicing debugger files");
  v2 = (WCHAR *)BfspEnvExpandString(a1, L"|SYSPART|\\|DEST|");
  if ( v2 )
  {
    v3 = 0;
    v4 = 0;
    v25 = (const WCHAR *)BfspEnvExpandString(a1, L"|SOURCE|\\BootDebuggerFiles.ini");
    v5 = (WCHAR *)v25;
    if ( v25 )
    {
      v4 = (unsigned __int16 *)BfspEnvExpandString(a1, L"|SYSROOT|");
      if ( v4 )
      {
        Value = (const wchar_t *)BfspEnvGetValue(a1, L"FWTYPE");
        v7 = wcsncmp_0(Value, L"EFI", 4u);
        v24 = BfspEnvGetValue(a1, L"ACLS") != 0;
        if ( (unsigned int)BfspFileExists(v25) )
        {
          v8 = L"BootDebuggerFiles.UEFI";
          if ( v7 )
            v8 = L"BootDebuggerFiles.PCAT";
          ProcessHeap = GetProcessHeap();
          v10 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0x4000u);
          v3 = v10;
          if ( v10 )
          {
            PrivateProfileSectionW = GetPrivateProfileSectionW(v8, v10, 0x2000u, v25);
            v12 = PrivateProfileSectionW;
            if ( PrivateProfileSectionW )
            {
              if ( PrivateProfileSectionW >= 0x1FFE )
                BfspLogMessage(4, L"ServiceDebuggerFiles: ConfigBuffer is too small");
              v13 = v3;
              do
              {
                if ( !*v13 )
                  break;
                v14 = -1;
                do
                  ++v14;
                while ( v13[v14] );
                StringCchCopyW(v26, 0x104u, v4);
                v15 = wcsrchr(v13, 0x5Cu);
                if ( v15 )
                {
                  v16 = v15 + 1;
                  *v15 = 0;
                  StringCchCatW(v26, 0x104u, v13);
                }
                else
                {
                  v16 = v13;
                }
                BfspLogMessage(2, L"Copying boot debugging files from %ws to %ws (%ws)", v26, v2, v16);
                if ( !(unsigned int)BfspCopyBootFileDirectory((__int64)v26, 0, v2, v16, 0, v24, 0, 0) )
                {
                  LODWORD(v23) = GetLastError();
                  BfspLogMessage(
                    4,
                    L"Error copying boot debugging files from %ws to %ws (%ws). Last Error = %#x",
                    v26,
                    v2,
                    v16,
                    v23);
                }
                v17 = (unsigned int)(v14 + 1);
                v13 += v17;
                v12 -= v17;
              }
              while ( v12 );
              BfspLogMessage(2, L"Done servicing debugger files.");
              v5 = (WCHAR *)v25;
            }
            else
            {
              BfspLogMessage(2, L"List of debugger files is empty");
            }
          }
          else
          {
            BfspLogMessage(4, L"ServiceDebuggerFiles: Failed to allocate config buffer");
          }
        }
        else
        {
          BfspLogMessage(3, L"ServiceDebuggerFiles: %ws does not exist", v25);
        }
      }
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v5);
    }
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v2);
    if ( v3 )
    {
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v3);
    }
    if ( v4 )
    {
      v21 = GetProcessHeap();
      HeapFree(v21, 0, v4);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18004b980  push    rbx
0x18004b982  push    rbp
0x18004b983  push    rsi
0x18004b984  push    rdi
0x18004b985  push    r12
0x18004b987  push    r13
0x18004b989  push    r14
0x18004b98b  push    r15
0x18004b98d  sub     rsp, 278h
0x18004b994  mov     rax, cs:__security_cookie
0x18004b99b  xor     rax, rsp
0x18004b99e  mov     [rsp+2B8h+var_58], rax
0x18004b9a6  mov     rdi, rcx
0x18004b9a9  lea     rdx, aServicingDebug; "Servicing debugger files"
0x18004b9b0  mov     ecx, 2
0x18004b9b5  call    BfspLogMessage
0x18004b9ba  lea     rdx, aSyspartDest; "|SYSPART|\\|DEST|"
0x18004b9c1  mov     rcx, rdi
0x18004b9c4  call    BfspEnvExpandString
0x18004b9c9  xor     r14d, r14d
0x18004b9cc  mov     r13, rax
0x18004b9cf  test    rax, rax
0x18004b9d2  jz      loc_18004BC64
0x18004b9d8  lea     rdx, aSourceBootdebu; "|SOURCE|\\BootDebuggerFiles.ini"
0x18004b9df  mov     rcx, rdi
0x18004b9e2  mov     esi, r14d
0x18004b9e5  mov     ebx, r14d
0x18004b9e8  call    BfspEnvExpandString
0x18004b9ed  mov     [rsp+2B8h+var_270], rax
0x18004b9f2  mov     r15, rax
0x18004b9f5  test    rax, rax
0x18004b9f8  jz      loc_18004BC1E
0x18004b9fe  lea     rdx, aSysroot; "|SYSROOT|"
0x18004ba05  mov     rcx, rdi
0x18004ba08  call    BfspEnvExpandString
0x18004ba0d  mov     rbx, rax
0x18004ba10  test    rax, rax
0x18004ba13  jz      loc_18004BC0A
0x18004ba19  lea     rdx, aFwtype; "FWTYPE"
0x18004ba20  mov     rcx, rdi
0x18004ba23  call    BfspEnvGetValue
0x18004ba28  lea     r12d, [r14+4]
0x18004ba2c  mov     rcx, rax; String1
0x18004ba2f  mov     r8d, r12d; MaxCount
0x18004ba32  lea     rdx, aEfi; "EFI"
0x18004ba39  call    wcsncmp_0
0x18004ba3e  lea     rdx, aAcls; "ACLS"
0x18004ba45  mov     rcx, rdi
0x18004ba48  mov     ebp, eax
0x18004ba4a  call    BfspEnvGetValue
0x18004ba4f  mov     ecx, r14d
0x18004ba52  test    rax, rax
0x18004ba55  setnz   cl
0x18004ba58  mov     [rsp+2B8h+var_278], ecx
0x18004ba5c  mov     rcx, r15
0x18004ba5f  call    BfspFileExists
0x18004ba64  test    eax, eax
0x18004ba66  jnz     short loc_18004BA7F
0x18004ba68  mov     r8, r15
0x18004ba6b  lea     rdx, aServicedebugge_0; "ServiceDebuggerFiles: %ws does not exis"...
0x18004ba72  lea     ecx, [rax+3]
0x18004ba75  call    BfspLogMessage
0x18004ba7a  jmp     loc_18004BC0A
0x18004ba7f  lea     rax, AppName; "BootDebuggerFiles.PCAT"
0x18004ba86  test    ebp, ebp
0x18004ba88  lea     rdi, aBootdebuggerfi_0; "BootDebuggerFiles.UEFI"
0x18004ba8f  cmovnz  rdi, rax
0x18004ba93  call    cs:__imp_GetProcessHeap
0x18004ba99  mov     edx, 8; dwFlags
0x18004ba9e  mov     r8d, 4000h; dwBytes
0x18004baa4  mov     rcx, rax; hHeap
0x18004baa7  call    cs:__imp_HeapAlloc
0x18004baad  mov     rsi, rax
0x18004bab0  test    rax, rax
0x18004bab3  jnz     short loc_18004BAC9
0x18004bab5  lea     rdx, aServicedebugge; "ServiceDebuggerFiles: Failed to allocat"...
0x18004babc  mov     ecx, r12d
0x18004babf  call    BfspLogMessage
0x18004bac4  jmp     loc_18004BC0A
0x18004bac9  mov     r9, r15; lpFileName
0x18004bacc  mov     r8d, 2000h; nSize
0x18004bad2  mov     rdx, rsi; lpReturnedString
0x18004bad5  mov     rcx, rdi; lpAppName
0x18004bad8  call    cs:__imp_GetPrivateProfileSectionW
0x18004bade  mov     ebp, eax
0x18004bae0  test    eax, eax
0x18004bae2  jnz     short loc_18004BAF0
0x18004bae4  lea     rdx, aListOfDebugger; "List of debugger files is empty"
0x18004baeb  lea     ecx, [rax+2]
0x18004baee  jmp     short loc_18004BABF
0x18004baf0  cmp     eax, 1FFEh
0x18004baf5  jb      short loc_18004BB06
0x18004baf7  lea     rdx, aServicedebugge_1; "ServiceDebuggerFiles: ConfigBuffer is t"...
0x18004bafe  mov     ecx, r12d
0x18004bb01  call    BfspLogMessage
0x18004bb06  mov     r15d, [rsp+2B8h+var_278]
0x18004bb0b  mov     rdi, rsi
0x18004bb0e  cmp     [rdi], r14w
0x18004bb12  jz      loc_18004BBF4
0x18004bb18  or      r12, 0FFFFFFFFFFFFFFFFh
0x18004bb1c  inc     r12
0x18004bb1f  cmp     [rdi+r12*2], r14w
0x18004bb24  jnz     short loc_18004BB1C
0x18004bb26  mov     r8, rbx; unsigned __int16 *
0x18004bb29  lea     rcx, [rsp+2B8h+var_268]; unsigned __int16 *
0x18004bb2e  mov     edx, 104h; unsigned __int64
0x18004bb33  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004bb38  mov     edx, 5Ch ; '\'; Ch
0x18004bb3d  mov     rcx, rdi; Str
0x18004bb40  call    cs:__imp_wcsrchr
0x18004bb46  mov     r14, rax
0x18004bb49  test    rax, rax
0x18004bb4c  jz      short loc_18004BB6B
0x18004bb4e  xor     ecx, ecx
0x18004bb50  add     r14, 2
0x18004bb54  mov     [rax], cx
0x18004bb57  mov     r8, rdi; unsigned __int16 *
0x18004bb5a  lea     rcx, [rsp+2B8h+var_268]; unsigned __int16 *
0x18004bb5f  mov     edx, 104h; unsigned __int64
0x18004bb64  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004bb69  jmp     short loc_18004BB6E
0x18004bb6b  mov     r14, rdi
0x18004bb6e  mov     r9, r13
0x18004bb71  mov     [rsp+2B8h+var_298], r14
0x18004bb76  lea     r8, [rsp+2B8h+var_268]
0x18004bb7b  mov     ecx, 2
0x18004bb80  lea     rdx, aCopyingBootDeb; "Copying boot debugging files from %ws t"...
0x18004bb87  call    BfspLogMessage
0x18004bb8c  xor     eax, eax
0x18004bb8e  lea     rcx, [rsp+2B8h+var_268]
0x18004bb93  mov     [rsp+2B8h+var_280], eax
0x18004bb97  mov     r9, r14
0x18004bb9a  mov     [rsp+2B8h+var_288], eax
0x18004bb9e  mov     r8, r13
0x18004bba1  mov     dword ptr [rsp+2B8h+var_290], r15d
0x18004bba6  xor     edx, edx
0x18004bba8  mov     dword ptr [rsp+2B8h+var_298], eax
0x18004bbac  call    BfspCopyBootFileDirectory
0x18004bbb1  test    eax, eax
0x18004bbb3  jnz     short loc_18004BBDD
0x18004bbb5  call    cs:__imp_GetLastError
0x18004bbbb  mov     dword ptr [rsp+2B8h+var_290], eax
0x18004bbbf  mov     r9, r13
0x18004bbc2  lea     r8, [rsp+2B8h+var_268]
0x18004bbc7  mov     [rsp+2B8h+var_298], r14
0x18004bbcc  lea     rdx, aErrorCopyingBo; "Error copying boot debugging files from"...
0x18004bbd3  mov     ecx, 4
0x18004bbd8  call    BfspLogMessage
0x18004bbdd  lea     eax, [r12+1]
0x18004bbe2  mov     r14d, 0
0x18004bbe8  lea     rdi, [rdi+rax*2]
0x18004bbec  sub     ebp, eax
0x18004bbee  jnz     loc_18004BB0E
0x18004bbf4  lea     rdx, aDoneServicingD; "Done servicing debugger files."
0x18004bbfb  mov     ecx, 2
0x18004bc00  call    BfspLogMessage
0x18004bc05  mov     r15, [rsp+2B8h+var_270]
0x18004bc0a  call    cs:__imp_GetProcessHeap
0x18004bc10  mov     r8, r15; lpMem
0x18004bc13  xor     edx, edx; dwFlags
0x18004bc15  mov     rcx, rax; hHeap
0x18004bc18  call    cs:__imp_HeapFree
0x18004bc1e  call    cs:__imp_GetProcessHeap
0x18004bc24  mov     r8, r13; lpMem
0x18004bc27  xor     edx, edx; dwFlags
0x18004bc29  mov     rcx, rax; hHeap
0x18004bc2c  call    cs:__imp_HeapFree
0x18004bc32  test    rsi, rsi
0x18004bc35  jz      short loc_18004BC4B
0x18004bc37  call    cs:__imp_GetProcessHeap
0x18004bc3d  mov     r8, rsi; lpMem
0x18004bc40  xor     edx, edx; dwFlags
0x18004bc42  mov     rcx, rax; hHeap
0x18004bc45  call    cs:__imp_HeapFree
0x18004bc4b  test    rbx, rbx
0x18004bc4e  jz      short loc_18004BC64
0x18004bc50  call    cs:__imp_GetProcessHeap
0x18004bc56  mov     r8, rbx; lpMem
0x18004bc59  xor     edx, edx; dwFlags
0x18004bc5b  mov     rcx, rax; hHeap
0x18004bc5e  call    cs:__imp_HeapFree
0x18004bc64  mov     eax, 1
0x18004bc69  mov     rcx, [rsp+2B8h+var_58]
0x18004bc71  xor     rcx, rsp; StackCookie
0x18004bc74  call    __security_check_cookie
0x18004bc79  add     rsp, 278h
0x18004bc80  pop     r15
0x18004bc82  pop     r14
0x18004bc84  pop     r13
0x18004bc86  pop     r12
0x18004bc88  pop     rdi
0x18004bc89  pop     rsi
0x18004bc8a  pop     rbp
0x18004bc8b  pop     rbx
0x18004bc8c  retn
```
