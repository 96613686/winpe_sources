# HttpApiCreateHandleHelper

- ea: `0x180004090`
- end: `0x180004303`
- name: `HttpApiCreateHandleHelper`
- size: `627`
- prototype: `__int64 __fastcall(int, int, int, int, STRSAFE_LPCWSTR, int, ULONG, ULONG, __int64, int, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180003760`
- `0x180003e20`
- `0x180004380`
- `0x18000a280`

## callees

- `0x180002e90`
- `0x180004090`
- `0x1800080e4`
- `0x18000b080`
- `0x18000bf60`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000426e`
- `ntdll!RtlNtStatusToDosError` at `0x18000426e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000419a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004172`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000419a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041d0`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180004164`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180004164`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800041e6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800041ef`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800041e6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800041ef`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000418c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18000418c`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800041ba`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800041ba`

## pseudocode

```c
__int64 __fastcall HttpApiCreateHandleHelper(
        int a1,
        unsigned int a2,
        int a3,
        int a4,
        STRSAFE_LPCWSTR pszSrc,
        int a6,
        ULONG a7,
        ULONG a8,
        __int64 a9,
        int a10,
        __int64 a11)
{
  int v15; // r14d
  __int64 v16; // rbp
  SC_HANDLE v17; // rax
  SC_HANDLE v18; // rbp
  DWORD LastError; // edi
  SC_HANDLE v20; // rax
  SC_HANDLE v21; // rsi
  NTSTATUS Handle; // esi
  ULONG v23; // eax
  unsigned int v24; // esi

  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_qllLLSLLLqLq(
      (_DWORD)pszSrc,
      HIWORD(a2),
      a3,
      a1,
      a2,
      SBYTE2(a2),
      a3,
      a4,
      (__int64)pszSrc,
      a6,
      a7,
      a8,
      a9,
      a10,
      a11);
  v15 = 0;
  v16 = 0x104000000001LL;
  while ( 1 )
  {
    if ( !v15 )
      goto LABEL_18;
    v17 = OpenSCManagerW(0, 0, 1u);
    v18 = v17;
    if ( v17 )
    {
      v20 = OpenServiceW(v17, L"HTTP", 0x14u);
      v21 = v20;
      if ( v20 )
      {
        LastError = QueryAndWaitForServiceStart(v20);
        if ( LastError )
        {
          if ( StartServiceW(v21, 0, 0) )
          {
            LastError = QueryAndWaitForServiceStart(v21);
          }
          else
          {
            LastError = GetLastError();
            if ( LastError == 1056 )
              LastError = 0;
          }
        }
        CloseServiceHandle(v21);
      }
      else
      {
        LastError = GetLastError();
      }
      CloseServiceHandle(v18);
    }
    else
    {
      LastError = GetLastError();
    }
    if ( LastError )
      break;
    v16 = 0x104000000001LL;
LABEL_18:
    Handle = HttpApiCreateHandle(a1, a2, a3, a4, pszSrc, a6, a7, a8, a9, a10, a11);
    v23 = RtlNtStatusToDosError(Handle);
    v24 = Handle + 1073741810;
    LastError = v23;
    if ( v24 <= 0x2C )
    {
      if ( _bittest64(&v16, (int)v24) )
      {
        if ( (unsigned int)++v15 < 2 )
          continue;
      }
    }
    break;
  }
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_d(1050, 18, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180004090  mov     r11, rsp
0x180004093  sub     rsp, 0A8h
0x18000409a  mov     [r11+8], rbx
0x18000409e  mov     ebx, edx
0x1800040a0  mov     [r11+10h], rbp
0x1800040a4  mov     [r11-10h], r12
0x1800040a8  mov     r12d, r8d
0x1800040ab  mov     [r11-18h], r13
0x1800040af  mov     r13, rcx
0x1800040b2  mov     [r11-20h], r14
0x1800040b6  mov     [r11-28h], r15
0x1800040ba  mov     r15d, r9d
0x1800040bd  test    cs:byte_1800126A3, 4
0x1800040c4  jz      short loc_180004134
0x1800040c6  mov     rcx, [rsp+0A8h+arg_50]
0x1800040ce  mov     [r11-38h], rcx
0x1800040d2  mov     ecx, [rsp+0A8h+arg_48]
0x1800040d9  mov     [rsp+0A8h+var_40], ecx
0x1800040dd  mov     rcx, [rsp+0A8h+arg_40]
0x1800040e5  mov     [r11-48h], rcx
0x1800040e9  mov     ecx, [rsp+0A8h+arg_38]
0x1800040f0  mov     [rsp+0A8h+var_50], ecx
0x1800040f4  mov     ecx, [rsp+0A8h+arg_30]
0x1800040fb  mov     dword ptr [rsp+0A8h+var_58], ecx
0x1800040ff  mov     ecx, [rsp+0A8h+arg_28]
0x180004106  mov     [rsp+0A8h+var_60], ecx
0x18000410a  mov     rcx, [rsp+0A8h+arg_20]
0x180004112  mov     [r11-68h], rcx
0x180004116  mov     [r11-70h], r9d
0x18000411a  mov     r9, r13
0x18000411d  mov     [r11-78h], r8d
0x180004121  shr     edx, 10h
0x180004124  movzx   eax, bx
0x180004127  mov     [rsp+0A8h+var_80], edx
0x18000412b  mov     dword ptr [rsp+0A8h+pszSrc], eax
0x18000412f  call    WPP_SF_qllLLSLLLqLq
0x180004134  mov     [rsp+0A8h+arg_10], rsi
0x18000413c  xor     r14d, r14d
0x18000413f  mov     [rsp+0A8h+var_8], rdi
0x180004147  mov     rbp, 104000000001h
0x180004151  test    r14d, r14d
0x180004154  jz      loc_180004207
0x18000415a  xor     edx, edx; lpDatabaseName
0x18000415c  xor     ecx, ecx; lpMachineName
0x18000415e  mov     r8d, 1; dwDesiredAccess
0x180004164  call    cs:__imp_OpenSCManagerW
0x18000416a  mov     rbp, rax
0x18000416d  test    rax, rax
0x180004170  jnz     short loc_18000417C
0x180004172  call    cs:__imp_GetLastError
0x180004178  mov     edi, eax
0x18000417a  jmp     short loc_1800041F5
0x18000417c  mov     r8d, 14h; dwDesiredAccess
0x180004182  lea     rdx, ServiceName; "HTTP"
0x180004189  mov     rcx, rbp; hSCManager
0x18000418c  call    cs:__imp_OpenServiceW
0x180004192  mov     rsi, rax
0x180004195  test    rax, rax
0x180004198  jnz     short loc_1800041A4
0x18000419a  call    cs:__imp_GetLastError
0x1800041a0  mov     edi, eax
0x1800041a2  jmp     short loc_1800041EC
0x1800041a4  mov     rcx, rsi; hService
0x1800041a7  call    QueryAndWaitForServiceStart
0x1800041ac  mov     edi, eax
0x1800041ae  test    eax, eax
0x1800041b0  jz      short loc_1800041E3
0x1800041b2  xor     r8d, r8d; lpServiceArgVectors
0x1800041b5  xor     edx, edx; dwNumServiceArgs
0x1800041b7  mov     rcx, rsi; hService
0x1800041ba  call    cs:__imp_StartServiceW
0x1800041c0  test    eax, eax
0x1800041c2  jz      short loc_1800041D0
0x1800041c4  mov     rcx, rsi; hService
0x1800041c7  call    QueryAndWaitForServiceStart
0x1800041cc  mov     edi, eax
0x1800041ce  jmp     short loc_1800041E3
0x1800041d0  call    cs:__imp_GetLastError
0x1800041d6  mov     edi, eax
0x1800041d8  xor     eax, eax
0x1800041da  cmp     edi, 420h
0x1800041e0  cmovz   edi, eax
0x1800041e3  mov     rcx, rsi; hSCObject
0x1800041e6  call    cs:__imp_CloseServiceHandle
0x1800041ec  mov     rcx, rbp; hSCObject
0x1800041ef  call    cs:__imp_CloseServiceHandle
0x1800041f5  test    edi, edi
0x1800041f7  jnz     loc_180004297
0x1800041fd  mov     rbp, 104000000001h
0x180004207  mov     rax, [rsp+0A8h+arg_50]
0x18000420f  mov     r9d, r15d; int
0x180004212  mov     [rsp+0A8h+var_58], rax; __int64
0x180004217  mov     r8d, r12d; int
0x18000421a  mov     eax, [rsp+0A8h+arg_48]
0x180004221  mov     edx, ebx; int
0x180004223  mov     [rsp+0A8h+var_60], eax; int
0x180004227  mov     rcx, r13; int
0x18000422a  mov     rax, [rsp+0A8h+arg_40]
0x180004232  mov     [rsp+0A8h+var_68], rax; __int64
0x180004237  mov     eax, [rsp+0A8h+arg_38]
0x18000423e  mov     [rsp+0A8h+var_70], eax; ULONG
0x180004242  mov     eax, [rsp+0A8h+arg_30]
0x180004249  mov     [rsp+0A8h+var_78], eax; ULONG
0x18000424d  mov     eax, [rsp+0A8h+arg_28]
0x180004254  mov     [rsp+0A8h+var_80], eax; int
0x180004258  mov     rax, [rsp+0A8h+arg_20]
0x180004260  mov     [rsp+0A8h+pszSrc], rax; pszSrc
0x180004265  call    HttpApiCreateHandle
0x18000426a  mov     ecx, eax; Status
0x18000426c  mov     esi, eax
0x18000426e  call    cs:__imp_RtlNtStatusToDosError
0x180004274  add     esi, 3FFFFFF2h
0x18000427a  mov     edi, eax
0x18000427c  cmp     esi, 2Ch ; ','
0x18000427f  ja      short loc_180004297
0x180004281  movsxd  rax, esi
0x180004284  bt      rbp, rax
0x180004288  jnb     short loc_180004297
0x18000428a  inc     r14d
0x18000428d  cmp     r14d, 2
0x180004291  jb      loc_180004151
0x180004297  test    cs:byte_1800126A3, 4
0x18000429e  mov     r15, [rsp+0A8h+var_28]
0x1800042a6  mov     r14, [rsp+0A8h+var_20]
0x1800042ae  mov     r13, [rsp+0A8h+var_18]
0x1800042b6  mov     r12, [rsp+0A8h+var_10]
0x1800042be  mov     rsi, [rsp+0A8h+arg_10]
0x1800042c6  mov     rbp, [rsp+0A8h+arg_8]
0x1800042ce  mov     rbx, [rsp+0A8h+arg_0]
0x1800042d6  jz      short loc_1800042F1
0x1800042d8  mov     edx, 12h
0x1800042dd  lea     r8, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids
0x1800042e4  mov     ecx, 41Ah
0x1800042e9  mov     r9d, edi
0x1800042ec  call    WPP_SF_d
0x1800042f1  mov     eax, edi
0x1800042f3  mov     rdi, [rsp+0A8h+var_8]
0x1800042fb  add     rsp, 0A8h
0x180004302  retn
```
