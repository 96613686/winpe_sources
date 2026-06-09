# AhpTraceFix

- ea: `0x18000708c`
- end: `0x18000741d`
- name: `AhpTraceFix`
- size: `913`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008474`
- `0x180011be0`

## callees

- `0x180001310`
- `0x1800013b0`
- `0x1800013ec`
- `0x18000708c`
- `0x18000f114`
- `0x18002907c`
- `0x18002d634`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!wcsrchr` at `0x180007351`
- `ntdll!wcsrchr` at `0x180007351`
- `ntdll!EtwEventWrite` at `0x180007339`
- `ntdll!EtwEventWrite` at `0x180007339`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073f4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000714e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000714e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000716e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000716e`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18000718c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x18000718c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007137`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007233`

## string_xrefs

- `0x18000715c`: `Failed to open process.`

## pseudocode

```c
unsigned int __fastcall AhpTraceFix(
        __int64 a1,
        const wchar_t *a2,
        DWORD a3,
        int a4,
        unsigned int *a5,
        __int64 a6,
        int a7)
{
  unsigned int *v7; // r15
  __int64 v8; // r12
  unsigned int result; // eax
  HANDLE CurrentProcess; // rax
  void *v13; // r14
  DWORD LastError; // eax
  __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // ecx
  __int64 *v18; // rdx
  wchar_t *v19; // rax
  __int64 v20; // r8
  wchar_t *v21; // r9
  __int64 v22; // r9
  LPFILETIME lpUserTime; // [rsp+20h] [rbp-E0h]
  DWORD dwProcessId; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+78h] [rbp-88h] BYREF
  struct _FILETIME ExitTime; // [rsp+80h] [rbp-80h] BYREF
  _FILETIME CreationTime; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v28[9]; // [rsp+90h] [rbp-70h] BYREF
  int v29; // [rsp+D8h] [rbp-28h]
  int v30; // [rsp+DCh] [rbp-24h]
  __int64 v31; // [rsp+E0h] [rbp-20h]
  int v32; // [rsp+E8h] [rbp-18h]
  int v33; // [rsp+ECh] [rbp-14h]
  char v34[32]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned int *v35; // [rsp+110h] [rbp+10h]
  __int64 v36; // [rsp+118h] [rbp+18h]
  __int64 *v37; // [rsp+120h] [rbp+20h]
  __int64 v38; // [rsp+128h] [rbp+28h]
  char v39[16]; // [rsp+130h] [rbp+30h] BYREF
  char v40[16]; // [rsp+140h] [rbp+40h] BYREF
  wchar_t pszDest[48]; // [rsp+150h] [rbp+50h] BYREF
  int v42; // [rsp+228h] [rbp+128h] BYREF

  v42 = a4;
  v7 = a5;
  v8 = a6;
  v25 = a1;
  dwProcessId = a3;
  CreationTime = 0;
  ExitTime = 0;
  result = (unsigned int)memset_0(pszDest, 0, sizeof(pszDest));
  if ( (!a7 || (a4 & 0x4000000) == 0) && (a4 & 0x82) == 0 )
  {
    if ( v7 )
    {
      if ( dwProcessId == GetCurrentProcessId() )
      {
        v13 = 0;
        CurrentProcess = GetCurrentProcess();
      }
      else
      {
        CurrentProcess = OpenProcess(0x1000u, 0, dwProcessId);
        v13 = CurrentProcess;
        if ( !CurrentProcess )
          return AslLogCallPrintf(1, "AhpTraceFix", 495, "Failed to open process.");
      }
      if ( GetProcessTimes(CurrentProcess, &CreationTime, &ExitTime, &ExitTime, &ExitTime) )
      {
        LODWORD(lpUserTime) = *((unsigned __int16 *)v7 + 2);
        if ( StringCchPrintfW(
               pszDest,
               0x30u,
               L"{%08lx-%04hx-%04hx-%02hx%02hx-%02hx%02hx%02hx%02hx%02hx%02hx}",
               *v7,
               lpUserTime,
               *((unsigned __int16 *)v7 + 3),
               *((unsigned __int8 *)v7 + 8),
               *((unsigned __int8 *)v7 + 9),
               *((unsigned __int8 *)v7 + 10),
               *((unsigned __int8 *)v7 + 11),
               *((unsigned __int8 *)v7 + 12),
               *((unsigned __int8 *)v7 + 13),
               *((unsigned __int8 *)v7 + 14),
               *((unsigned __int8 *)v7 + 15)) >= 0 )
        {
          result = AhpIsSdbFixEventBlackListed(pszDest);
          if ( !result )
          {
            v28[1] = 4;
            v28[0] = &dwProcessId;
            v15 = -1;
            v28[3] = 8;
            v28[2] = &CreationTime;
            v28[6] = &v42;
            v16 = -1;
            v28[4] = v7;
            v28[5] = 16;
            v28[7] = 4;
            v28[8] = a2;
            do
              ++v16;
            while ( a2[v16] );
            v30 = 0;
            v29 = 2 * v16 + 2;
            if ( v8 )
            {
              do
                ++v15;
              while ( *(_WORD *)(v8 + 2 * v15) );
              v17 = 2 * v15 + 2;
            }
            else
            {
              v17 = 0;
            }
            v31 = v8;
            v32 = v17;
            v33 = 0;
            if ( (v42 & 0x4000000) != 0 )
            {
              v18 = AE_COMPATIBILITY_FIX_OS;
            }
            else
            {
              v18 = AE_COMPATIBILITY_FIX_2;
              if ( (v42 & 0x80000000) == 0 )
                v18 = AE_COMPATIBILITY_FIX;
            }
            result = EtwEventWrite(v25, v18, 6, v28);
            if ( (v42 & 0x80000000) == 0 )
            {
              v19 = wcsrchr(a2, 0x5Cu);
              v21 = v19 + 1;
              if ( !v19 )
                v21 = 0;
              result = dword_1800803E0;
              if ( (unsigned int)dword_1800803E0 > 5 )
              {
                result = tlgKeywordOn(&dword_1800803E0, 0x400000000000LL, v20, v21);
                if ( (_BYTE)result )
                {
                  LODWORD(v25) = v42;
                  v35 = v7;
                  v37 = &v25;
                  v36 = 16;
                  v38 = 4;
                  tlgCreate1Sz_wchar_t(v39, v22);
                  tlgCreate1Sz_wchar_t(v40, v8);
                  result = tlgWriteTransfer_EventWriteTransfer(&dword_1800803E0, byte_180077A41, 0, 0, 6, v34);
                }
              }
            }
          }
        }
        else
        {
          LastError = GetLastError();
          result = AslLogCallPrintf(1, "AhpTraceFix", 529, "Convert guid failed, %d", LastError);
        }
      }
      else
      {
        result = AslLogCallPrintf(1, "AhpTraceFix", 505, "GetProcessTimes failed.");
      }
      if ( v13 )
        return CloseHandle(v13);
    }
    else
    {
      return AslLogCallPrintf(1, "AhpTraceFix", 486, "Guid not found.");
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000708c  mov     [rsp-8+arg_18], r9d
0x180007091  push    rbp
0x180007092  push    rbx
0x180007093  push    rsi
0x180007094  push    rdi
0x180007095  push    r12
0x180007097  push    r13
0x180007099  push    r14
0x18000709b  push    r15
0x18000709d  lea     rbp, [rsp-0C8h]
0x1800070a5  sub     rsp, 1C8h
0x1800070ac  mov     rax, cs:__security_cookie
0x1800070b3  xor     rax, rsp
0x1800070b6  mov     [rbp+100h+var_50], rax
0x1800070bd  mov     r15, [rbp+100h+arg_20]
0x1800070c4  xor     edi, edi
0x1800070c6  mov     r12, [rbp+100h+arg_28]
0x1800070cd  mov     r13, rdx
0x1800070d0  mov     [rsp+200h+var_188], rcx
0x1800070d5  xor     edx, edx; Val
0x1800070d7  mov     [rsp+200h+dwProcessId], r8d
0x1800070dc  lea     rcx, [rbp+100h+pszDest]; void *
0x1800070e0  lea     r8d, [rdi+60h]; Size
0x1800070e4  mov     qword ptr [rbp+100h+CreationTime.dwLowDateTime], rdi
0x1800070e8  mov     ebx, r9d
0x1800070eb  mov     qword ptr [rbp+100h+ExitTime.dwLowDateTime], rdi
0x1800070ef  call    memset_0
0x1800070f4  cmp     [rbp+100h+arg_30], edi
0x1800070fa  jz      short loc_180007106
0x1800070fc  bt      ebx, 1Ah
0x180007100  jb      loc_1800073FA
0x180007106  test    bl, 82h
0x180007109  jnz     loc_1800073FA
0x18000710f  test    r15, r15
0x180007112  jnz     short loc_180007137
0x180007114  lea     r9, aGuidNotFound; "Guid not found."
0x18000711b  mov     r8d, 1E6h
0x180007121  lea     rdx, aAhptracefix; "AhpTraceFix"
0x180007128  mov     ecx, 1
0x18000712d  call    AslLogCallPrintf
0x180007132  jmp     loc_1800073FA
0x180007137  call    cs:__imp_GetCurrentProcessId
0x18000713d  mov     r8d, [rsp+200h+dwProcessId]; dwProcessId
0x180007142  cmp     r8d, eax
0x180007145  jz      short loc_18000716B
0x180007147  xor     edx, edx; bInheritHandle
0x180007149  mov     ecx, 1000h; dwDesiredAccess
0x18000714e  call    cs:__imp_OpenProcess
0x180007154  mov     r14, rax
0x180007157  test    rax, rax
0x18000715a  jnz     short loc_180007174
0x18000715c  lea     r9, aFailedToOpenPr; "Failed to open process."
0x180007163  mov     r8d, 1EFh
0x180007169  jmp     short loc_180007121
0x18000716b  mov     r14, rdi
0x18000716e  call    cs:__imp_GetCurrentProcess
0x180007174  lea     rcx, [rbp+100h+ExitTime]
0x180007178  mov     [rsp+200h+lpUserTime], rcx; lpUserTime
0x18000717d  lea     r9, [rbp+100h+ExitTime]; lpKernelTime
0x180007181  mov     rcx, rax; hProcess
0x180007184  lea     r8, [rbp+100h+ExitTime]; lpExitTime
0x180007188  lea     rdx, [rbp+100h+CreationTime]; lpCreationTime
0x18000718c  call    cs:__imp_GetProcessTimes
0x180007192  test    eax, eax
0x180007194  jnz     short loc_1800071B7
0x180007196  lea     r9, aGetprocesstime; "GetProcessTimes failed."
0x18000719d  mov     r8d, 1F9h
0x1800071a3  lea     rdx, aAhptracefix; "AhpTraceFix"
0x1800071aa  lea     ecx, [rax+1]
0x1800071ad  call    AslLogCallPrintf
0x1800071b2  jmp     loc_1800073EC
0x1800071b7  movzx   ecx, byte ptr [r15+0Eh]
0x1800071bc  movzx   edx, byte ptr [r15+0Dh]
0x1800071c1  movzx   r8d, byte ptr [r15+0Ch]
0x1800071c6  movzx   r9d, byte ptr [r15+0Bh]
0x1800071cb  movzx   eax, byte ptr [r15+0Fh]
0x1800071d0  movzx   r10d, byte ptr [r15+0Ah]
0x1800071d5  movzx   r11d, byte ptr [r15+9]
0x1800071da  movzx   ebx, byte ptr [r15+8]
0x1800071df  movzx   edi, word ptr [r15+6]
0x1800071e4  movzx   esi, word ptr [r15+4]
0x1800071e9  mov     [rsp+200h+var_198], eax
0x1800071ed  mov     [rsp+200h+var_1A0], ecx
0x1800071f1  lea     rcx, [rbp+100h+pszDest]; pszDest
0x1800071f5  mov     [rsp+200h+var_1A8], edx
0x1800071f9  mov     edx, 30h ; '0'; cchDest
0x1800071fe  mov     [rsp+200h+var_1B0], r8d
0x180007203  lea     r8, a08lx04hx04hx02; "{%08lx-%04hx-%04hx-%02hx%02hx-%02hx%02h"...
0x18000720a  mov     [rsp+200h+var_1B8], r9d
0x18000720f  mov     r9d, [r15]
0x180007212  mov     [rsp+200h+var_1C0], r10d
0x180007217  mov     [rsp+200h+var_1C8], r11d
0x18000721c  mov     [rsp+200h+var_1D0], ebx
0x180007220  mov     dword ptr [rsp+200h+var_1D8], edi
0x180007224  mov     dword ptr [rsp+200h+lpUserTime], esi
0x180007228  call    StringCchPrintfW
0x18000722d  xor     edi, edi
0x18000722f  test    eax, eax
0x180007231  jns     short loc_18000725E
0x180007233  call    cs:__imp_GetLastError
0x180007239  lea     r9, aConvertGuidFai; "Convert guid failed, %d"
0x180007240  mov     r8d, 211h
0x180007246  lea     rdx, aAhptracefix; "AhpTraceFix"
0x18000724d  mov     dword ptr [rsp+200h+lpUserTime], eax
0x180007251  lea     ecx, [rdi+1]
0x180007254  call    AslLogCallPrintf
0x180007259  jmp     loc_1800073EC
0x18000725e  lea     rcx, [rbp+100h+pszDest]; String1
0x180007262  call    AhpIsSdbFixEventBlackListed
0x180007267  test    eax, eax
0x180007269  jnz     loc_1800073EC
0x18000726f  lea     rax, [rsp+200h+dwProcessId]
0x180007274  mov     [rbp+100h+var_168], 4
0x18000727c  mov     [rbp+100h+var_170], rax
0x180007280  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007284  lea     rax, [rbp+100h+CreationTime]
0x180007288  mov     [rbp+100h+var_158], 8
0x180007290  mov     [rbp+100h+var_160], rax
0x180007294  lea     rax, [rbp+100h+arg_18]
0x18000729b  mov     [rbp+100h+var_140], rax
0x18000729f  mov     rax, rcx
0x1800072a2  mov     [rbp+100h+var_150], r15
0x1800072a6  mov     [rbp+100h+var_148], 10h
0x1800072ae  mov     [rbp+100h+var_138], 4
0x1800072b6  mov     [rbp+100h+var_130], r13
0x1800072ba  inc     rax
0x1800072bd  cmp     [r13+rax*2+0], di
0x1800072c3  jnz     short loc_1800072BA
0x1800072c5  mov     [rbp+100h+var_124], edi
0x1800072c8  lea     eax, ds:2[rax*2]
0x1800072cf  mov     [rbp+100h+var_128], eax
0x1800072d2  test    r12, r12
0x1800072d5  jz      short loc_1800072EA
0x1800072d7  inc     rcx
0x1800072da  cmp     [r12+rcx*2], di
0x1800072df  jnz     short loc_1800072D7
0x1800072e1  lea     ecx, ds:2[rcx*2]
0x1800072e8  jmp     short loc_1800072EC
0x1800072ea  mov     ecx, edi
0x1800072ec  test    [rbp+100h+arg_18], 4000000h
0x1800072f6  mov     ebx, 80000000h
0x1800072fb  mov     [rbp+100h+var_120], r12
0x1800072ff  mov     [rbp+100h+var_118], ecx
0x180007302  mov     [rbp+100h+var_114], edi
0x180007305  jz      short loc_180007310
0x180007307  lea     rdx, AE_COMPATIBILITY_FIX_OS
0x18000730e  jmp     short loc_180007328
0x180007310  test    [rbp+100h+arg_18], ebx
0x180007316  lea     rdx, AE_COMPATIBILITY_FIX_2
0x18000731d  lea     rax, AE_COMPATIBILITY_FIX
0x180007324  cmovz   rdx, rax
0x180007328  mov     rcx, [rsp+200h+var_188]
0x18000732d  lea     r9, [rbp+100h+var_170]
0x180007331  mov     esi, 6
0x180007336  mov     r8d, esi
0x180007339  call    cs:__imp_EtwEventWrite
0x18000733f  test    [rbp+100h+arg_18], ebx
0x180007345  jnz     loc_1800073EC
0x18000734b  lea     edx, [rsi+56h]; Ch
0x18000734e  mov     rcx, r13; Str
0x180007351  call    cs:__imp_wcsrchr
0x180007357  test    rax, rax
0x18000735a  lea     r9, [rax+2]
0x18000735e  cmovz   r9, rax
0x180007362  mov     eax, cs:dword_1800803E0
0x180007368  cmp     eax, 5
0x18000736b  jbe     short loc_1800073EC
0x18000736d  mov     rdx, 400000000000h
0x180007377  lea     rcx, dword_1800803E0
0x18000737e  call    _tlgKeywordOn
0x180007383  test    al, al
0x180007385  jz      short loc_1800073EC
0x180007387  mov     eax, [rbp+100h+arg_18]
0x18000738d  lea     rcx, [rbp+100h+var_D0]
0x180007391  mov     dword ptr [rsp+200h+var_188], eax
0x180007395  mov     rdx, r9
0x180007398  lea     rax, [rsp+200h+var_188]
0x18000739d  mov     [rbp+100h+var_F0], r15
0x1800073a1  mov     [rbp+100h+var_E0], rax
0x1800073a5  mov     [rbp+100h+var_E8], 10h
0x1800073ad  mov     [rbp+100h+var_D8], 4
0x1800073b5  call    _tlgCreate1Sz_wchar_t
0x1800073ba  mov     rdx, r12
0x1800073bd  lea     rcx, [rbp+100h+var_C0]
0x1800073c1  call    _tlgCreate1Sz_wchar_t
0x1800073c6  lea     r9, [rbp+100h+var_110]
0x1800073ca  xor     r8d, r8d
0x1800073cd  mov     [rsp+200h+var_1D8], r9
0x1800073d2  lea     rdx, byte_180077A41
0x1800073d9  xor     r9d, r9d
0x1800073dc  mov     dword ptr [rsp+200h+lpUserTime], esi
0x1800073e0  lea     rcx, dword_1800803E0
0x1800073e7  call    _tlgWriteTransfer_EventWriteTransfer
0x1800073ec  test    r14, r14
0x1800073ef  jz      short loc_1800073FA
0x1800073f1  mov     rcx, r14; hObject
0x1800073f4  call    cs:__imp_CloseHandle
0x1800073fa  mov     rcx, [rbp+100h+var_50]
0x180007401  xor     rcx, rsp; StackCookie
0x180007404  call    __security_check_cookie
0x180007409  add     rsp, 1C8h
0x180007410  pop     r15
0x180007412  pop     r14
0x180007414  pop     r13
0x180007416  pop     r12
0x180007418  pop     rdi
0x180007419  pop     rsi
0x18000741a  pop     rbx
0x18000741b  pop     rbp
0x18000741c  retn
```
