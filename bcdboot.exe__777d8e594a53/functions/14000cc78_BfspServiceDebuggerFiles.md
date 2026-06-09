# BfspServiceDebuggerFiles

- ea: `0x14000cc78`
- end: `0x14000cfb9`
- name: `BfspServiceDebuggerFiles`
- size: `833`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x140009fd4`

## callees

- `0x140002b7c`
- `0x140003bf8`
- `0x14000b57c`
- `0x14000cc78`
- `0x14000e628`
- `0x14000f50c`
- `0x14000f72c`
- `0x14002661e`
- `0x140026650`

## import_xrefs

- `msvcrt!wcsrchr` at `0x14000ce6c`
- `msvcrt!wcsrchr` at `0x14000ce6c`
- `KERNEL32!GetLastError` at `0x14000cee1`
- `KERNEL32!GetLastError` at `0x14000cee1`
- `KERNEL32!HeapFree` at `0x14000cf44`
- `KERNEL32!HeapFree` at `0x14000cf58`
- `KERNEL32!HeapFree` at `0x14000cf71`
- `KERNEL32!HeapFree` at `0x14000cf8a`
- `KERNEL32!HeapFree` at `0x14000cf44`
- `KERNEL32!HeapFree` at `0x14000cf58`
- `KERNEL32!HeapFree` at `0x14000cf71`
- `KERNEL32!HeapFree` at `0x14000cf8a`
- `KERNEL32!HeapAlloc` at `0x14000cd9f`
- `KERNEL32!HeapAlloc` at `0x14000cd9f`
- `KERNEL32!GetProcessHeap` at `0x14000cd8b`
- `KERNEL32!GetProcessHeap` at `0x14000cf36`
- `KERNEL32!GetProcessHeap` at `0x14000cf4a`
- `KERNEL32!GetProcessHeap` at `0x14000cf63`
- `KERNEL32!GetProcessHeap` at `0x14000cf7c`
- `KERNEL32!GetProcessHeap` at `0x14000cd8b`
- `KERNEL32!GetProcessHeap` at `0x14000cf36`
- `KERNEL32!GetProcessHeap` at `0x14000cf4a`
- `KERNEL32!GetProcessHeap` at `0x14000cf63`
- `KERNEL32!GetProcessHeap` at `0x14000cf7c`
- `KERNEL32!GetPrivateProfileSectionW` at `0x14000cdd2`
- `KERNEL32!GetPrivateProfileSectionW` at `0x14000cdd2`

## string_xrefs

- `0x14000cd63`: `ServiceDebuggerFiles: %ws does not exist`
- `0x14000cdaf`: `ServiceDebuggerFiles: Failed to allocate config buffer`
- `0x14000ceac`: `Copying boot debugging files from %ws to %ws (%ws)`
- `0x14000cdf2`: `ServiceDebuggerFiles: ConfigBuffer is too small`
- `0x14000cef8`: `Error copying boot debugging files from %ws to %ws (%ws). Last Error = %#x`

## pseudocode

```c
__int64 __fastcall BfspServiceDebuggerFiles(_QWORD *a1)
{
  wchar_t *v2; // r13
  WCHAR *v3; // rbp
  wchar_t *v4; // rbx
  WCHAR *v5; // r15
  const wchar_t *Value; // rax
  int v7; // esi
  const WCHAR *v8; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v10; // rax
  DWORD PrivateProfileSectionW; // eax
  DWORD v12; // r14d
  const wchar_t *v13; // rdi
  __int64 v14; // r12
  __int64 v15; // rcx
  wchar_t *v16; // rax
  wchar_t *v17; // r8
  __int64 v18; // rdx
  wchar_t *v19; // rcx
  wchar_t *v20; // rax
  const wchar_t *v21; // rsi
  __int64 v22; // rax
  HANDLE v23; // rax
  HANDLE v24; // rax
  HANDLE v25; // rax
  HANDLE v26; // rax
  __int64 v28; // [rsp+28h] [rbp-290h]
  BOOL v29; // [rsp+40h] [rbp-278h]
  wchar_t *v30; // [rsp+48h] [rbp-270h]
  wchar_t pszDest[264]; // [rsp+50h] [rbp-268h] BYREF

  BfspLogMessage(2, L"Servicing debugger files");
  v2 = BfspEnvExpandString((__int64)a1, L"|SYSPART|\\|DEST|");
  if ( v2 )
  {
    v3 = 0;
    v4 = 0;
    v30 = BfspEnvExpandString((__int64)a1, L"|SOURCE|\\BootDebuggerFiles.ini");
    v5 = v30;
    if ( v30 )
    {
      v4 = BfspEnvExpandString((__int64)a1, L"|SYSROOT|");
      if ( v4 )
      {
        Value = (const wchar_t *)BfspEnvGetValue(a1, L"FWTYPE");
        v7 = wcsncmp_0(Value, L"EFI", 4u);
        v29 = BfspEnvGetValue(a1, L"ACLS") != 0;
        if ( (unsigned int)BfspFileExists(v30) )
        {
          v8 = L"BootDebuggerFiles.UEFI";
          if ( v7 )
            v8 = L"BootDebuggerFiles.PCAT";
          ProcessHeap = GetProcessHeap();
          v10 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 0x4000u);
          v3 = v10;
          if ( v10 )
          {
            PrivateProfileSectionW = GetPrivateProfileSectionW(v8, v10, 0x2000u, v30);
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
                v15 = 2147483646;
                v16 = pszDest;
                v17 = v4;
                v18 = 260;
                do
                {
                  if ( !v15 )
                    break;
                  if ( !*v17 )
                    break;
                  *v16++ = *v17++;
                  --v15;
                  --v18;
                }
                while ( v18 );
                v19 = v16 - 1;
                if ( v18 )
                  v19 = v16;
                *v19 = 0;
                v20 = wcsrchr(v13, 0x5Cu);
                if ( v20 )
                {
                  v21 = v20 + 1;
                  *v20 = 0;
                  StringCchCatW(pszDest, 0x104u, v13);
                }
                else
                {
                  v21 = v13;
                }
                BfspLogMessage(2, L"Copying boot debugging files from %ws to %ws (%ws)", pszDest, v2, v21);
                if ( !(unsigned int)BfspCopyBootFileDirectory((__int64)pszDest, 0, v2, v21, 0, v29, 0, 0) )
                {
                  LODWORD(v28) = GetLastError();
                  BfspLogMessage(
                    4,
                    L"Error copying boot debugging files from %ws to %ws (%ws). Last Error = %#x",
                    pszDest,
                    v2,
                    v21,
                    v28);
                }
                v22 = (unsigned int)(v14 + 1);
                v13 += v22;
                v12 -= v22;
              }
              while ( v12 );
              BfspLogMessage(2, L"Done servicing debugger files.");
              v5 = v30;
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
          BfspLogMessage(3, L"ServiceDebuggerFiles: %ws does not exist", v30);
        }
      }
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v5);
    }
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v2);
    if ( v3 )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v3);
    }
    if ( v4 )
    {
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v4);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14000cc78  push    rbx
0x14000cc7a  push    rbp
0x14000cc7b  push    rsi
0x14000cc7c  push    rdi
0x14000cc7d  push    r12
0x14000cc7f  push    r13
0x14000cc81  push    r14
0x14000cc83  push    r15
0x14000cc85  sub     rsp, 278h
0x14000cc8c  mov     rax, cs:__security_cookie
0x14000cc93  xor     rax, rsp
0x14000cc96  mov     [rsp+2B8h+var_58], rax
0x14000cc9e  mov     rdi, rcx
0x14000cca1  lea     rdx, aServicingDebug; "Servicing debugger files"
0x14000cca8  mov     ecx, 2
0x14000ccad  call    BfspLogMessage
0x14000ccb2  lea     rdx, aSyspartDest; "|SYSPART|\\|DEST|"
0x14000ccb9  mov     rcx, rdi
0x14000ccbc  call    BfspEnvExpandString
0x14000ccc1  xor     esi, esi
0x14000ccc3  mov     r13, rax
0x14000ccc6  test    rax, rax
0x14000ccc9  jz      loc_14000CF90
0x14000cccf  lea     rdx, aSourceBootdebu; "|SOURCE|\\BootDebuggerFiles.ini"
0x14000ccd6  mov     rcx, rdi
0x14000ccd9  mov     ebp, esi
0x14000ccdb  mov     ebx, esi
0x14000ccdd  call    BfspEnvExpandString
0x14000cce2  mov     [rsp+2B8h+var_270], rax
0x14000cce7  mov     r15, rax
0x14000ccea  test    rax, rax
0x14000cced  jz      loc_14000CF4A
0x14000ccf3  lea     rdx, aSysroot; "|SYSROOT|"
0x14000ccfa  mov     rcx, rdi
0x14000ccfd  call    BfspEnvExpandString
0x14000cd02  mov     rbx, rax
0x14000cd05  test    rax, rax
0x14000cd08  jz      loc_14000CF36
0x14000cd0e  lea     rdx, aFwtype; "FWTYPE"
0x14000cd15  mov     rcx, rdi
0x14000cd18  call    BfspEnvGetValue
0x14000cd1d  lea     r12d, [rsi+4]
0x14000cd21  mov     rcx, rax; String1
0x14000cd24  mov     r8d, r12d; MaxCount
0x14000cd27  lea     rdx, aEfi; "EFI"
0x14000cd2e  call    wcsncmp_0
0x14000cd33  lea     rdx, aAcls; "ACLS"
0x14000cd3a  mov     rcx, rdi
0x14000cd3d  mov     esi, eax
0x14000cd3f  call    BfspEnvGetValue
0x14000cd44  xor     r14d, r14d
0x14000cd47  mov     ecx, r14d
0x14000cd4a  test    rax, rax
0x14000cd4d  setnz   cl
0x14000cd50  mov     [rsp+2B8h+var_278], ecx
0x14000cd54  mov     rcx, r15
0x14000cd57  call    BfspFileExists
0x14000cd5c  test    eax, eax
0x14000cd5e  jnz     short loc_14000CD77
0x14000cd60  mov     r8, r15
0x14000cd63  lea     rdx, aServicedebugge_0; "ServiceDebuggerFiles: %ws does not exis"...
0x14000cd6a  lea     ecx, [rbp+3]
0x14000cd6d  call    BfspLogMessage
0x14000cd72  jmp     loc_14000CF36
0x14000cd77  lea     rax, AppName; "BootDebuggerFiles.PCAT"
0x14000cd7e  test    esi, esi
0x14000cd80  lea     rdi, aBootdebuggerfi_0; "BootDebuggerFiles.UEFI"
0x14000cd87  cmovnz  rdi, rax
0x14000cd8b  call    cs:__imp_GetProcessHeap
0x14000cd91  mov     edx, 8; dwFlags
0x14000cd96  mov     r8d, 4000h; dwBytes
0x14000cd9c  mov     rcx, rax; hHeap
0x14000cd9f  call    cs:__imp_HeapAlloc
0x14000cda5  xor     esi, esi
0x14000cda7  mov     rbp, rax
0x14000cdaa  test    rax, rax
0x14000cdad  jnz     short loc_14000CDC3
0x14000cdaf  lea     rdx, aServicedebugge; "ServiceDebuggerFiles: Failed to allocat"...
0x14000cdb6  mov     ecx, r12d
0x14000cdb9  call    BfspLogMessage
0x14000cdbe  jmp     loc_14000CF36
0x14000cdc3  mov     r9, r15; lpFileName
0x14000cdc6  mov     r8d, 2000h; nSize
0x14000cdcc  mov     rdx, rbp; lpReturnedString
0x14000cdcf  mov     rcx, rdi; lpAppName
0x14000cdd2  call    cs:__imp_GetPrivateProfileSectionW
0x14000cdd8  mov     r14d, eax
0x14000cddb  test    eax, eax
0x14000cddd  jnz     short loc_14000CDEB
0x14000cddf  lea     rdx, aListOfDebugger; "List of debugger files is empty"
0x14000cde6  lea     ecx, [rax+2]
0x14000cde9  jmp     short loc_14000CDB9
0x14000cdeb  cmp     eax, 1FFEh
0x14000cdf0  jb      short loc_14000CE01
0x14000cdf2  lea     rdx, aServicedebugge_1; "ServiceDebuggerFiles: ConfigBuffer is t"...
0x14000cdf9  mov     ecx, r12d
0x14000cdfc  call    BfspLogMessage
0x14000ce01  mov     r15d, [rsp+2B8h+var_278]
0x14000ce06  mov     rdi, rbp
0x14000ce09  cmp     [rdi], si
0x14000ce0c  jz      loc_14000CF20
0x14000ce12  or      r12, 0FFFFFFFFFFFFFFFFh
0x14000ce16  inc     r12
0x14000ce19  cmp     [rdi+r12*2], si
0x14000ce1e  jnz     short loc_14000CE16
0x14000ce20  mov     ecx, 7FFFFFFEh
0x14000ce25  lea     rax, [rsp+2B8h+pszDest]
0x14000ce2a  mov     r8, rbx
0x14000ce2d  mov     edx, 104h
0x14000ce32  test    rcx, rcx
0x14000ce35  jz      short loc_14000CE56
0x14000ce37  movzx   r9d, word ptr [r8]
0x14000ce3b  test    r9w, r9w
0x14000ce3f  jz      short loc_14000CE56
0x14000ce41  mov     [rax], r9w
0x14000ce45  add     r8, 2
0x14000ce49  add     rax, 2
0x14000ce4d  dec     rcx
0x14000ce50  sub     rdx, 1
0x14000ce54  jnz     short loc_14000CE32
0x14000ce56  test    rdx, rdx
0x14000ce59  lea     rcx, [rax-2]
0x14000ce5d  mov     edx, 5Ch ; '\'; Ch
0x14000ce62  cmovnz  rcx, rax
0x14000ce66  mov     [rcx], si
0x14000ce69  mov     rcx, rdi; Str
0x14000ce6c  call    cs:__imp_wcsrchr
0x14000ce72  mov     rsi, rax
0x14000ce75  test    rax, rax
0x14000ce78  jz      short loc_14000CE97
0x14000ce7a  xor     ecx, ecx
0x14000ce7c  add     rsi, 2
0x14000ce80  mov     [rax], cx
0x14000ce83  mov     r8, rdi; pszSrc
0x14000ce86  lea     rcx, [rsp+2B8h+pszDest]; pszDest
0x14000ce8b  mov     edx, 104h; cchDest
0x14000ce90  call    StringCchCatW
0x14000ce95  jmp     short loc_14000CE9A
0x14000ce97  mov     rsi, rdi
0x14000ce9a  mov     r9, r13
0x14000ce9d  mov     [rsp+2B8h+var_298], rsi
0x14000cea2  lea     r8, [rsp+2B8h+pszDest]
0x14000cea7  mov     ecx, 2
0x14000ceac  lea     rdx, aCopyingBootDeb; "Copying boot debugging files from %ws t"...
0x14000ceb3  call    BfspLogMessage
0x14000ceb8  xor     eax, eax
0x14000ceba  lea     rcx, [rsp+2B8h+pszDest]
0x14000cebf  mov     [rsp+2B8h+var_280], eax
0x14000cec3  mov     r9, rsi
0x14000cec6  mov     [rsp+2B8h+var_288], eax
0x14000ceca  mov     r8, r13
0x14000cecd  mov     dword ptr [rsp+2B8h+var_290], r15d
0x14000ced2  xor     edx, edx
0x14000ced4  mov     dword ptr [rsp+2B8h+var_298], eax
0x14000ced8  call    BfspCopyBootFileDirectory
0x14000cedd  test    eax, eax
0x14000cedf  jnz     short loc_14000CF09
0x14000cee1  call    cs:__imp_GetLastError
0x14000cee7  mov     dword ptr [rsp+2B8h+var_290], eax
0x14000ceeb  mov     r9, r13
0x14000ceee  lea     r8, [rsp+2B8h+pszDest]
0x14000cef3  mov     [rsp+2B8h+var_298], rsi
0x14000cef8  lea     rdx, aErrorCopyingBo; "Error copying boot debugging files from"...
0x14000ceff  mov     ecx, 4
0x14000cf04  call    BfspLogMessage
0x14000cf09  lea     eax, [r12+1]
0x14000cf0e  mov     esi, 0
0x14000cf13  lea     rdi, [rdi+rax*2]
0x14000cf17  sub     r14d, eax
0x14000cf1a  jnz     loc_14000CE09
0x14000cf20  lea     rdx, aDoneServicingD; "Done servicing debugger files."
0x14000cf27  mov     ecx, 2
0x14000cf2c  call    BfspLogMessage
0x14000cf31  mov     r15, [rsp+2B8h+var_270]
0x14000cf36  call    cs:__imp_GetProcessHeap
0x14000cf3c  mov     r8, r15; lpMem
0x14000cf3f  xor     edx, edx; dwFlags
0x14000cf41  mov     rcx, rax; hHeap
0x14000cf44  call    cs:__imp_HeapFree
0x14000cf4a  call    cs:__imp_GetProcessHeap
0x14000cf50  mov     r8, r13; lpMem
0x14000cf53  xor     edx, edx; dwFlags
0x14000cf55  mov     rcx, rax; hHeap
0x14000cf58  call    cs:__imp_HeapFree
0x14000cf5e  test    rbp, rbp
0x14000cf61  jz      short loc_14000CF77
0x14000cf63  call    cs:__imp_GetProcessHeap
0x14000cf69  mov     r8, rbp; lpMem
0x14000cf6c  xor     edx, edx; dwFlags
0x14000cf6e  mov     rcx, rax; hHeap
0x14000cf71  call    cs:__imp_HeapFree
0x14000cf77  test    rbx, rbx
0x14000cf7a  jz      short loc_14000CF90
0x14000cf7c  call    cs:__imp_GetProcessHeap
0x14000cf82  mov     r8, rbx; lpMem
0x14000cf85  xor     edx, edx; dwFlags
0x14000cf87  mov     rcx, rax; hHeap
0x14000cf8a  call    cs:__imp_HeapFree
0x14000cf90  mov     eax, 1
0x14000cf95  mov     rcx, [rsp+2B8h+var_58]
0x14000cf9d  xor     rcx, rsp; StackCookie
0x14000cfa0  call    __security_check_cookie
0x14000cfa5  add     rsp, 278h
0x14000cfac  pop     r15
0x14000cfae  pop     r14
0x14000cfb0  pop     r13
0x14000cfb2  pop     r12
0x14000cfb4  pop     rdi
0x14000cfb5  pop     rsi
0x14000cfb6  pop     rbp
0x14000cfb7  pop     rbx
0x14000cfb8  retn
```
