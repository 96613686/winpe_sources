# AhpTraceFixMsi

- ea: `0x18003b78c`
- end: `0x18003b9f5`
- name: `AhpTraceFixMsi`
- size: `617`
- prototype: `void __fastcall(__int64, __int64, int, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003ba40`

## callees

- `0x18000f114`
- `0x18002fc78`
- `0x18003b78c`
- `0x1800591b0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18003b9c3`
- `ntdll!EtwEventWrite` at `0x18003b9c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b9d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b9d1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003b82e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18003b82e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003b84e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003b84e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18003b870`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18003b870`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b81a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003b81a`

## string_xrefs

- `0x18003b83c`: `Failed to open process.`
- `0x18003b7fe`: `AhpTraceFixMsi`
- `0x18003b887`: `AhpTraceFixMsi`
- `0x18003b8ba`: `AhpTraceFixMsi`

## pseudocode

```c
void __fastcall AhpTraceFixMsi(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 a5, int a6)
{
  __int64 v9; // rsi
  DWORD v10; // ebx
  HANDLE CurrentProcess; // rax
  void *v12; // rbx
  int v13; // eax
  const char *v14; // r9
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  int v19; // ecx
  __int64 *v20; // rdx
  LPFILETIME lpUserTime; // [rsp+20h] [rbp-B9h]
  struct _FILETIME ExitTime; // [rsp+30h] [rbp-A9h] BYREF
  struct _FILETIME CreationTime; // [rsp+38h] [rbp-A1h] BYREF
  GUID Guid; // [rsp+40h] [rbp-99h] BYREF
  GUID v25; // [rsp+50h] [rbp-89h] BYREF
  _QWORD v26[13]; // [rsp+60h] [rbp-79h] BYREF
  int v27; // [rsp+C8h] [rbp-11h]
  int v28; // [rsp+CCh] [rbp-Dh]
  __int64 v29; // [rsp+D0h] [rbp-9h]
  int v30; // [rsp+D8h] [rbp-1h]
  int v31; // [rsp+DCh] [rbp+3h]
  int v32; // [rsp+140h] [rbp+67h] BYREF

  v32 = a3;
  CreationTime = 0;
  ExitTime = 0;
  Guid = 0;
  v25 = 0;
  if ( !a6 || (a3 & 0x4000000) == 0 )
  {
    if ( !a4 )
    {
      AslLogCallPrintf(1, "AhpTraceFixMsi", 1140, "Guid not found.");
      return;
    }
    v9 = a2 + 32;
    v10 = *(_DWORD *)(a2 + 32);
    if ( v10 == GetCurrentProcessId() )
    {
      v12 = 0;
      CurrentProcess = GetCurrentProcess();
    }
    else
    {
      CurrentProcess = OpenProcess(0x1000u, 0, v10);
      v12 = CurrentProcess;
      if ( !CurrentProcess )
      {
        AslLogCallPrintf(1, "AhpTraceFixMsi", 1149, "Failed to open process.");
        return;
      }
    }
    if ( GetProcessTimes(CurrentProcess, &CreationTime, &ExitTime, &ExitTime, &ExitTime) )
    {
      v13 = AslGuidFromString(&Guid);
      if ( v13 >= 0 )
      {
        v13 = AslGuidFromString(&v25);
        if ( v13 >= 0 )
        {
          v16 = *(_QWORD *)(a2 + 24);
          v26[2] = &CreationTime;
          v26[0] = v9;
          v26[6] = &v32;
          v17 = -1;
          v26[1] = 4;
          v26[8] = &Guid;
          v26[10] = &v25;
          v18 = -1;
          v26[3] = 8;
          v26[4] = a4;
          v26[5] = 16;
          v26[7] = 4;
          v26[9] = 16;
          v26[11] = 16;
          do
            ++v18;
          while ( *(_WORD *)(v16 + 2 * v18) );
          v26[12] = v16;
          v27 = 2 * v18 + 2;
          v28 = 0;
          if ( a5 )
          {
            do
              ++v17;
            while ( *(_WORD *)(a5 + 2 * v17) );
            v19 = 2 * v17 + 2;
          }
          else
          {
            v19 = 0;
          }
          v20 = AE_COMPATIBILITY_MSI_OS;
          v29 = a5;
          v30 = v19;
          if ( (v32 & 0x4000000) == 0 )
            v20 = AE_COMPATIBILITY_MSI;
          v31 = 0;
          EtwEventWrite(a1, v20, 8, v26, lpUserTime);
          goto LABEL_26;
        }
        v14 = "Bad PackageCode [%x]";
        v15 = 1171;
      }
      else
      {
        v14 = "Bad ProductCode [%x]";
        v15 = 1165;
      }
      LODWORD(lpUserTime) = v13;
      AslLogCallPrintf(1, "AhpTraceFixMsi", v15, v14, lpUserTime);
    }
    else
    {
      AslLogCallPrintf(1, "AhpTraceFixMsi", 1159, "GetProcessTimes failed.");
    }
LABEL_26:
    if ( v12 )
      CloseHandle(v12);
  }
}

```

## disassembly

```asm
0x18003b78c  mov     [rsp-8+arg_10], r8d
0x18003b791  push    rbp
0x18003b792  push    rbx
0x18003b793  push    rsi
0x18003b794  push    rdi
0x18003b795  push    r12
0x18003b797  push    r14
0x18003b799  push    r15
0x18003b79b  lea     rbp, [rsp-17h]
0x18003b7a0  sub     rsp, 0F0h
0x18003b7a7  mov     rax, cs:__security_cookie
0x18003b7ae  xor     rax, rsp
0x18003b7b1  mov     [rbp+47h+var_40], rax
0x18003b7b5  xor     r12d, r12d
0x18003b7b8  xorps   xmm0, xmm0
0x18003b7bb  xorps   xmm1, xmm1
0x18003b7be  mov     r14, r9
0x18003b7c1  mov     rdi, rdx
0x18003b7c4  mov     r15, rcx
0x18003b7c7  mov     qword ptr [rsp+120h+CreationTime.dwLowDateTime], r12
0x18003b7cc  mov     qword ptr [rsp+120h+ExitTime.dwLowDateTime], r12
0x18003b7d1  movups  xmmword ptr [rsp+120h+Guid.Data1], xmm0
0x18003b7d6  movups  xmmword ptr [rsp+120h+var_D0.Data1], xmm1
0x18003b7db  cmp     [rbp+47h+arg_28], r12d
0x18003b7df  jz      short loc_18003B7EC
0x18003b7e1  bt      r8d, 1Ah
0x18003b7e6  jb      loc_18003B9D7
0x18003b7ec  test    r14, r14
0x18003b7ef  jnz     short loc_18003B814
0x18003b7f1  lea     r9, aGuidNotFound; "Guid not found."
0x18003b7f8  mov     r8d, 474h
0x18003b7fe  lea     rdx, aAhptracefixmsi; "AhpTraceFixMsi"
0x18003b805  mov     ecx, 1
0x18003b80a  call    AslLogCallPrintf
0x18003b80f  jmp     loc_18003B9D7
0x18003b814  lea     rsi, [rdx+20h]
0x18003b818  mov     ebx, [rsi]
0x18003b81a  call    cs:__imp_GetCurrentProcessId
0x18003b820  cmp     ebx, eax
0x18003b822  jz      short loc_18003B84B
0x18003b824  mov     r8d, ebx; dwProcessId
0x18003b827  xor     edx, edx; bInheritHandle
0x18003b829  mov     ecx, 1000h; dwDesiredAccess
0x18003b82e  call    cs:__imp_OpenProcess
0x18003b834  mov     rbx, rax
0x18003b837  test    rax, rax
0x18003b83a  jnz     short loc_18003B854
0x18003b83c  lea     r9, aFailedToOpenPr; "Failed to open process."
0x18003b843  mov     r8d, 47Dh
0x18003b849  jmp     short loc_18003B7FE
0x18003b84b  mov     rbx, r12
0x18003b84e  call    cs:__imp_GetCurrentProcess
0x18003b854  lea     rcx, [rsp+120h+ExitTime]
0x18003b859  mov     [rsp+120h+lpUserTime], rcx; lpUserTime
0x18003b85e  lea     r9, [rsp+120h+ExitTime]; lpKernelTime
0x18003b863  mov     rcx, rax; hProcess
0x18003b866  lea     r8, [rsp+120h+ExitTime]; lpExitTime
0x18003b86b  lea     rdx, [rsp+120h+CreationTime]; lpCreationTime
0x18003b870  call    cs:__imp_GetProcessTimes
0x18003b876  test    eax, eax
0x18003b878  jnz     short loc_18003B89B
0x18003b87a  lea     r9, aGetprocesstime; "GetProcessTimes failed."
0x18003b881  mov     r8d, 487h
0x18003b887  lea     rdx, aAhptracefixmsi; "AhpTraceFixMsi"
0x18003b88e  lea     ecx, [rax+1]
0x18003b891  call    AslLogCallPrintf
0x18003b896  jmp     loc_18003B9C9
0x18003b89b  mov     rdx, [rdi+8]
0x18003b89f  lea     rcx, [rsp+120h+Guid]; Guid
0x18003b8a4  call    AslGuidFromString
0x18003b8a9  test    eax, eax
0x18003b8ab  jns     short loc_18003B8D4
0x18003b8ad  lea     r9, aBadProductcode; "Bad ProductCode [%x]"
0x18003b8b4  mov     r8d, 48Dh
0x18003b8ba  lea     rdx, aAhptracefixmsi; "AhpTraceFixMsi"
0x18003b8c1  mov     dword ptr [rsp+120h+lpUserTime], eax
0x18003b8c5  mov     ecx, 1
0x18003b8ca  call    AslLogCallPrintf
0x18003b8cf  jmp     loc_18003B9C9
0x18003b8d4  mov     rdx, [rdi+10h]
0x18003b8d8  lea     rcx, [rsp+120h+var_D0]; Guid
0x18003b8dd  call    AslGuidFromString
0x18003b8e2  test    eax, eax
0x18003b8e4  jns     short loc_18003B8F5
0x18003b8e6  lea     r9, aBadPackagecode; "Bad PackageCode [%x]"
0x18003b8ed  mov     r8d, 493h
0x18003b8f3  jmp     short loc_18003B8BA
0x18003b8f5  mov     rdx, [rdi+18h]
0x18003b8f9  lea     rax, [rsp+120h+CreationTime]
0x18003b8fe  mov     [rbp+47h+var_B0], rax
0x18003b902  mov     r8d, 8
0x18003b908  lea     rax, [rbp+47h+arg_10]
0x18003b90c  mov     [rbp+47h+var_C0], rsi
0x18003b910  mov     [rbp+47h+var_90], rax
0x18003b914  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003b918  lea     rax, [rsp+120h+Guid]
0x18003b91d  mov     [rbp+47h+var_B8], 4
0x18003b925  mov     [rbp+47h+var_80], rax
0x18003b929  lea     rax, [rsp+120h+var_D0]
0x18003b92e  mov     [rbp+47h+var_70], rax
0x18003b932  mov     rax, rcx
0x18003b935  mov     [rbp+47h+var_A8], r8
0x18003b939  mov     [rbp+47h+var_A0], r14
0x18003b93d  mov     [rbp+47h+var_98], 10h
0x18003b945  mov     [rbp+47h+var_88], 4
0x18003b94d  mov     [rbp+47h+var_78], 10h
0x18003b955  mov     [rbp+47h+var_68], 10h
0x18003b95d  inc     rax
0x18003b960  cmp     [rdx+rax*2], r12w
0x18003b965  jnz     short loc_18003B95D
0x18003b967  lea     eax, ds:2[rax*2]
0x18003b96e  mov     [rbp+47h+var_60], rdx
0x18003b972  mov     [rbp+47h+var_58], eax
0x18003b975  mov     rax, [rbp+47h+arg_20]
0x18003b979  mov     [rbp+47h+var_54], r12d
0x18003b97d  test    rax, rax
0x18003b980  jz      short loc_18003B995
0x18003b982  inc     rcx
0x18003b985  cmp     [rax+rcx*2], r12w
0x18003b98a  jnz     short loc_18003B982
0x18003b98c  lea     ecx, ds:2[rcx*2]
0x18003b993  jmp     short loc_18003B998
0x18003b995  mov     ecx, r12d
0x18003b998  test    [rbp+47h+arg_10], 4000000h
0x18003b99f  lea     rdx, AE_COMPATIBILITY_MSI_OS
0x18003b9a6  mov     [rbp+47h+var_50], rax
0x18003b9aa  lea     r9, [rbp+47h+var_C0]
0x18003b9ae  lea     rax, AE_COMPATIBILITY_MSI
0x18003b9b5  mov     [rbp+47h+var_48], ecx
0x18003b9b8  cmovz   rdx, rax
0x18003b9bc  mov     [rbp+47h+var_44], r12d
0x18003b9c0  mov     rcx, r15
0x18003b9c3  call    cs:__imp_EtwEventWrite
0x18003b9c9  test    rbx, rbx
0x18003b9cc  jz      short loc_18003B9D7
0x18003b9ce  mov     rcx, rbx; hObject
0x18003b9d1  call    cs:__imp_CloseHandle
0x18003b9d7  mov     rcx, [rbp+47h+var_40]
0x18003b9db  xor     rcx, rsp; StackCookie
0x18003b9de  call    __security_check_cookie
0x18003b9e3  add     rsp, 0F0h
0x18003b9ea  pop     r15
0x18003b9ec  pop     r14
0x18003b9ee  pop     r12
0x18003b9f0  pop     rdi
0x18003b9f1  pop     rsi
0x18003b9f2  pop     rbx
0x18003b9f3  pop     rbp
0x18003b9f4  retn
```
