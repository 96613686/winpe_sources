# DupConsoleUserToken(void * *)

- ea: `0x18001d9b0`
- end: `0x18001dbd7`
- name: `?DupConsoleUserToken@@YAKPEAPEAX@Z`
- size: `551`
- prototype: `__int64 __fastcall(PHANDLE phNewToken)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001d914`

## callees

- `0x18001d9b0`
- `0x18003af88`
- `0x18003b7b0`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001dab7`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001dab7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001da4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001da4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001da3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001da3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001db98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dad4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dad4`
- `ntdll!RtlGetActiveConsoleId` at `0x18001d9c2`
- `ntdll!RtlGetActiveConsoleId` at `0x18001d9c2`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x18001da89`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x18001da89`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DupConsoleUserToken(PHANDLE phNewToken)
{
  unsigned int ActiveConsoleId; // edi
  unsigned int v3; // ebx
  HANDLE v5; // rdi
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  DWORD LastError; // eax
  DWORD v10; // eax
  __int128 v11; // [rsp+30h] [rbp-28h] BYREF
  HANDLE hExistingToken; // [rsp+40h] [rbp-18h]
  int v13; // [rsp+60h] [rbp+8h] BYREF

  ActiveConsoleId = RtlGetActiveConsoleId();
  hExistingToken = 0;
  v13 = 0;
  v11 = 0;
  if ( !phNewToken || *phNewToken != (void *)-1LL )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_78b059fac4093813b2646cef9913e025_Traceguids);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_78b059fac4093813b2646cef9913e025_Traceguids, ActiveConsoleId);
  hExistingToken = 0;
  *(_QWORD *)&v11 = (int)GetCurrentProcessId();
  *((_QWORD *)&v11 + 1) = (int)GetCurrentThreadId();
  if ( !(unsigned __int8)IsWinStationQueryInformationWPresent() )
  {
    v3 = 50;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return v3;
    v7 = 13;
    v8 = 50;
    goto LABEL_18;
  }
  if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __int128 *, int, int *))WinStationQueryInformationW)(
                           0,
                           ActiveConsoleId,
                           14,
                           &v11,
                           24,
                           &v13) )
  {
    LastError = GetLastError();
    v3 = LastError;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return v3;
    v7 = 12;
    v8 = LastError;
LABEL_18:
    WPP_SF_d(v6[2], v7, WPP_78b059fac4093813b2646cef9913e025_Traceguids, v8);
    return v3;
  }
  v5 = hExistingToken;
  if ( DuplicateTokenEx(hExistingToken, 0, 0, SecurityImpersonation, TokenPrimary, phNewToken) )
  {
    v3 = 0;
  }
  else
  {
    v10 = GetLastError();
    v3 = v10;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_78b059fac4093813b2646cef9913e025_Traceguids, v10);
  }
  if ( v5 == (HANDLE)-1LL )
    return v3;
  CloseHandle(v5);
  return v3;
}

```

## disassembly

```asm
0x18001d9b0  mov     [rsp+arg_8], rbx
0x18001d9b5  mov     [rsp+arg_10], rsi
0x18001d9ba  push    rdi
0x18001d9bb  sub     rsp, 50h
0x18001d9bf  mov     rbx, rcx
0x18001d9c2  call    cs:__imp_RtlGetActiveConsoleId
0x18001d9c8  mov     edi, eax
0x18001d9ca  xorps   xmm0, xmm0
0x18001d9cd  xor     eax, eax
0x18001d9cf  mov     [rsp+58h+hExistingToken], rax
0x18001d9d4  mov     [rsp+58h+arg_0], eax
0x18001d9d8  movups  [rsp+58h+var_28], xmm0
0x18001d9dd  test    rbx, rbx
0x18001d9e0  jnz     short loc_18001DA0D
0x18001d9e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9e9  lea     rsi, WPP_GLOBAL_Control
0x18001d9f0  cmp     rcx, rsi
0x18001d9f3  jnz     loc_18001DB28
0x18001d9f9  xor     ebx, ebx
0x18001d9fb  mov     eax, ebx
0x18001d9fd  mov     rbx, [rsp+58h+arg_8]
0x18001da02  mov     rsi, [rsp+58h+arg_10]
0x18001da07  add     rsp, 50h
0x18001da0b  pop     rdi
0x18001da0c  retn
0x18001da0d  cmp     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x18001da11  jnz     short loc_18001D9E2
0x18001da13  mov     rcx, cs:WPP_GLOBAL_Control
0x18001da1a  lea     rsi, WPP_GLOBAL_Control
0x18001da21  cmp     rcx, rsi
0x18001da24  jz      short loc_18001DA30
0x18001da26  test    byte ptr [rcx+1Ch], 8
0x18001da2a  jnz     loc_18001DB4C
0x18001da30  xorps   xmm0, xmm0
0x18001da33  xor     eax, eax
0x18001da35  movups  [rsp+58h+var_28], xmm0
0x18001da3a  mov     [rsp+58h+hExistingToken], rax
0x18001da3f  call    cs:__imp_GetCurrentProcessId
0x18001da45  movsxd  rcx, eax
0x18001da48  mov     qword ptr [rsp+58h+var_28], rcx
0x18001da4d  call    cs:__imp_GetCurrentThreadId
0x18001da53  movsxd  rcx, eax
0x18001da56  mov     qword ptr [rsp+58h+var_28+8], rcx
0x18001da5b  call    IsWinStationQueryInformationWPresent
0x18001da60  test    al, al
0x18001da62  jz      loc_18001DAEC
0x18001da68  lea     rax, [rsp+58h+arg_0]
0x18001da6d  mov     r8d, 0Eh
0x18001da73  mov     [rsp+58h+phNewToken], rax
0x18001da78  lea     r9, [rsp+58h+var_28]
0x18001da7d  mov     edx, edi
0x18001da7f  mov     [rsp+58h+TokenType], 18h
0x18001da87  xor     ecx, ecx
0x18001da89  call    cs:__imp_WinStationQueryInformationW
0x18001da8f  test    al, al
0x18001da91  jz      loc_18001DB69
0x18001da97  mov     rdi, [rsp+58h+hExistingToken]
0x18001da9c  mov     r9d, 2; ImpersonationLevel
0x18001daa2  mov     rcx, rdi; hExistingToken
0x18001daa5  mov     [rsp+58h+phNewToken], rbx; phNewToken
0x18001daaa  xor     r8d, r8d; lpTokenAttributes
0x18001daad  mov     [rsp+58h+TokenType], 1; TokenType
0x18001dab5  xor     edx, edx; dwDesiredAccess
0x18001dab7  call    cs:__imp_DuplicateTokenEx
0x18001dabd  test    eax, eax
0x18001dabf  jz      loc_18001DB98
0x18001dac5  xor     ebx, ebx
0x18001dac7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001dacb  jz      loc_18001D9FB
0x18001dad1  mov     rcx, rdi; hObject
0x18001dad4  call    cs:__imp_CloseHandle
0x18001dada  mov     rsi, [rsp+58h+arg_10]
0x18001dadf  mov     eax, ebx
0x18001dae1  mov     rbx, [rsp+58h+arg_8]
0x18001dae6  add     rsp, 50h
0x18001daea  pop     rdi
0x18001daeb  retn
0x18001daec  mov     ebx, 32h ; '2'
0x18001daf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001daf8  cmp     rcx, rsi
0x18001dafb  jz      loc_18001D9FB
0x18001db01  test    byte ptr [rcx+1Ch], 2
0x18001db05  jz      loc_18001D9FB
0x18001db0b  mov     edx, 0Dh
0x18001db10  mov     r9d, ebx
0x18001db13  mov     rcx, [rcx+10h]
0x18001db17  lea     r8, WPP_78b059fac4093813b2646cef9913e025_Traceguids
0x18001db1e  call    WPP_SF_d
0x18001db23  jmp     loc_18001D9FB
0x18001db28  test    byte ptr [rcx+1Ch], 8
0x18001db2c  jz      loc_18001D9F9
0x18001db32  mov     rcx, [rcx+10h]
0x18001db36  lea     r8, WPP_78b059fac4093813b2646cef9913e025_Traceguids
0x18001db3d  mov     edx, 0Ah
0x18001db42  call    WPP_SF_
0x18001db47  jmp     loc_18001D9F9
0x18001db4c  mov     rcx, [rcx+10h]
0x18001db50  lea     r8, WPP_78b059fac4093813b2646cef9913e025_Traceguids
0x18001db57  mov     edx, 0Bh
0x18001db5c  mov     r9d, edi
0x18001db5f  call    WPP_SF_d
0x18001db64  jmp     loc_18001DA30
0x18001db69  call    cs:__imp_GetLastError
0x18001db6f  mov     ebx, eax
0x18001db71  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db78  cmp     rcx, rsi
0x18001db7b  jz      loc_18001D9FB
0x18001db81  test    byte ptr [rcx+1Ch], 2
0x18001db85  jz      loc_18001D9FB
0x18001db8b  mov     edx, 0Ch
0x18001db90  mov     r9d, eax
0x18001db93  jmp     loc_18001DB13
0x18001db98  call    cs:__imp_GetLastError
0x18001db9e  mov     ebx, eax
0x18001dba0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dba7  cmp     rcx, rsi
0x18001dbaa  jz      loc_18001DAC7
0x18001dbb0  test    byte ptr [rcx+1Ch], 2
0x18001dbb4  jz      loc_18001DAC7
0x18001dbba  mov     rcx, [rcx+10h]
0x18001dbbe  lea     r8, WPP_78b059fac4093813b2646cef9913e025_Traceguids
0x18001dbc5  mov     edx, 0Eh
0x18001dbca  mov     r9d, eax
0x18001dbcd  call    WPP_SF_d
0x18001dbd2  jmp     loc_18001DAC7
```
