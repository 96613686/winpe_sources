# WctInitClient(ulong,ulong,_WCT_CLIENT_HANDLE *)

- ea: `0x18005eaf8`
- end: `0x18005ec36`
- name: `?WctInitClient@@YAKKKPEAU_WCT_CLIENT_HANDLE@@@Z`
- size: `318`
- prototype: `unsigned int __fastcall(DWORD dwThreadId, unsigned int, struct _WCT_CLIENT_HANDLE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005d2e0`
- `0x18005e154`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x18005cd40`
- `0x18005eaf8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18005eb7e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18005eb7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eb8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eb8c`
- `ntdll!RtlNtStatusToDosError` at `0x18005ebe4`
- `ntdll!RtlNtStatusToDosError` at `0x18005ebe4`
- `ntdll!NtQueryInformationThread` at `0x18005ebae`
- `ntdll!NtQueryInformationThread` at `0x18005ebae`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005ebcf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005ebcf`

## pseudocode

```c
__int64 __fastcall WctInitClient(DWORD dwThreadId, __int64 a2, struct _WCT_CLIENT_HANDLE *a3)
{
  __int64 v3; // rbx
  unsigned int v5; // ebx
  HANDLE v6; // rax
  DWORD LastError; // eax
  int v8; // eax
  DWORD v9; // r8d
  HANDLE v10; // rax
  __int128 ThreadInformation; // [rsp+30h] [rbp-38h] BYREF
  __int128 dwProcessId; // [rsp+40h] [rbp-28h]
  __int128 v14; // [rsp+50h] [rbp-18h]
  ULONG ReturnLength; // [rsp+78h] [rbp+10h] BYREF

  v3 = dwThreadId;
  ThreadInformation = 0;
  ReturnLength = 0;
  dwProcessId = 0;
  v14 = 0;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  if ( !(_DWORD)v3 )
  {
    v5 = 87;
LABEL_14:
    WctFreeClient(a3);
    goto LABEL_15;
  }
  *((_QWORD *)a3 + 3) = v3;
  *((_QWORD *)a3 + 2) = 0;
  *((_QWORD *)a3 + 1) = 0;
  v6 = OpenThread(0x48u, 0, v3);
  *(_QWORD *)a3 = v6;
  if ( !v6 )
  {
LABEL_7:
    LastError = GetLastError();
    goto LABEL_13;
  }
  v8 = NtQueryInformationThread(v6, ThreadBasicInformation, &ThreadInformation, 0x30u, &ReturnLength);
  if ( v8 >= 0 && ReturnLength == 48 )
  {
    v9 = dwProcessId;
    *((_QWORD *)a3 + 2) = dwProcessId;
    v10 = OpenProcess(0x450u, 0, v9);
    *((_QWORD *)a3 + 1) = v10;
    if ( v10 )
    {
      v5 = 0;
      goto LABEL_15;
    }
    goto LABEL_7;
  }
  LastError = RtlNtStatusToDosError(v8);
LABEL_13:
  v5 = LastError;
  if ( LastError )
    goto LABEL_14;
LABEL_15:
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18005eaf8  mov     rax, rsp
0x18005eafb  mov     [rax+8], rbx
0x18005eaff  mov     [rax+18h], rbp
0x18005eb03  mov     [rax+10h], edx
0x18005eb06  push    rdi
0x18005eb07  sub     rsp, 60h
0x18005eb0b  xorps   xmm0, xmm0
0x18005eb0e  mov     ebx, ecx
0x18005eb10  movups  xmmword ptr [rax-38h], xmm0
0x18005eb14  mov     rdi, r8
0x18005eb17  mov     dword ptr [rax+10h], 0
0x18005eb1e  movups  xmmword ptr [rax-28h], xmm0
0x18005eb22  movups  xmmword ptr [rax-18h], xmm0
0x18005eb26  mov     rcx, cs:WPP_GLOBAL_Control
0x18005eb2d  lea     rbp, WPP_GLOBAL_Control
0x18005eb34  cmp     rcx, rbp
0x18005eb37  jz      short loc_18005EB54
0x18005eb39  test    byte ptr [rcx+1Ch], 4
0x18005eb3d  jz      short loc_18005EB54
0x18005eb3f  mov     rcx, [rcx+10h]
0x18005eb43  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005eb4a  mov     edx, 0Ch
0x18005eb4f  call    WPP_SF_
0x18005eb54  test    ebx, ebx
0x18005eb56  jnz     short loc_18005EB62
0x18005eb58  mov     ebx, 57h ; 'W'
0x18005eb5d  jmp     loc_18005EBF0
0x18005eb62  xor     edx, edx; bInheritHandle
0x18005eb64  mov     [rdi+18h], rbx
0x18005eb68  mov     r8d, ebx; dwThreadId
0x18005eb6b  mov     qword ptr [rdi+10h], 0
0x18005eb73  mov     qword ptr [rdi+8], 0
0x18005eb7b  lea     ecx, [rdx+48h]; dwDesiredAccess
0x18005eb7e  call    cs:__imp_OpenThread
0x18005eb84  mov     [rdi], rax
0x18005eb87  test    rax, rax
0x18005eb8a  jnz     short loc_18005EB94
0x18005eb8c  call    cs:__imp_GetLastError
0x18005eb92  jmp     short loc_18005EBEA
0x18005eb94  lea     rcx, [rsp+68h+arg_8]
0x18005eb99  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18005eb9f  mov     [rsp+68h+ReturnLength], rcx; ReturnLength
0x18005eba4  lea     r8, [rsp+68h+ThreadInformation]; ThreadInformation
0x18005eba9  mov     rcx, rax; ThreadHandle
0x18005ebac  xor     edx, edx; ThreadInformationClass
0x18005ebae  call    cs:__imp_NtQueryInformationThread
0x18005ebb4  test    eax, eax
0x18005ebb6  js      short loc_18005EBE2
0x18005ebb8  cmp     [rsp+68h+arg_8], 30h ; '0'
0x18005ebbd  jnz     short loc_18005EBE2
0x18005ebbf  mov     r8, qword ptr [rsp+68h+dwProcessId]; dwProcessId
0x18005ebc4  xor     edx, edx; bInheritHandle
0x18005ebc6  mov     ecx, 450h; dwDesiredAccess
0x18005ebcb  mov     [rdi+10h], r8
0x18005ebcf  call    cs:__imp_OpenProcess
0x18005ebd5  mov     [rdi+8], rax
0x18005ebd9  test    rax, rax
0x18005ebdc  jz      short loc_18005EB8C
0x18005ebde  xor     ebx, ebx
0x18005ebe0  jmp     short loc_18005EBF8
0x18005ebe2  mov     ecx, eax; Status
0x18005ebe4  call    cs:__imp_RtlNtStatusToDosError
0x18005ebea  mov     ebx, eax
0x18005ebec  test    eax, eax
0x18005ebee  jz      short loc_18005EBF8
0x18005ebf0  mov     rcx, rdi; struct _WCT_CLIENT_HANDLE *
0x18005ebf3  call    ?WctFreeClient@@YAXPEAU_WCT_CLIENT_HANDLE@@@Z; WctFreeClient(_WCT_CLIENT_HANDLE *)
0x18005ebf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ebff  cmp     rcx, rbp
0x18005ec02  jz      short loc_18005EC22
0x18005ec04  test    byte ptr [rcx+1Ch], 4
0x18005ec08  jz      short loc_18005EC22
0x18005ec0a  mov     rcx, [rcx+10h]
0x18005ec0e  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18005ec15  mov     edx, 0Dh
0x18005ec1a  mov     r9d, ebx
0x18005ec1d  call    WPP_SF_d
0x18005ec22  lea     r11, [rsp+68h+var_8]
0x18005ec27  mov     eax, ebx
0x18005ec29  mov     rbx, [r11+10h]
0x18005ec2d  mov     rbp, [r11+20h]
0x18005ec31  mov     rsp, r11
0x18005ec34  pop     rdi
0x18005ec35  retn
```
