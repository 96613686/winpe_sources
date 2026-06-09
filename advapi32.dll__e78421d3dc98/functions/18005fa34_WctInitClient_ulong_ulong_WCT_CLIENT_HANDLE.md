# WctInitClient(ulong,ulong,_WCT_CLIENT_HANDLE *)

- ea: `0x18005fa34`
- end: `0x18005fb72`
- name: `?WctInitClient@@YAKKKPEAU_WCT_CLIENT_HANDLE@@@Z`
- size: `318`
- prototype: `unsigned int __fastcall(DWORD dwThreadId, unsigned int, struct _WCT_CLIENT_HANDLE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005e430`
- `0x18005f5fc`

## callees

- `0x18003b57c`
- `0x18003b748`
- `0x18005e11c`
- `0x18005fa34`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18005faea`
- `ntdll!NtQueryInformationThread` at `0x18005faea`
- `ntdll!RtlNtStatusToDosError` at `0x18005fb20`
- `ntdll!RtlNtStatusToDosError` at `0x18005fb20`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18005faba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18005faba`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005fb0b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005fb0b`
- `KERNEL32!GetLastError` at `0x18005fac8`
- `KERNEL32!GetLastError` at `0x18005fac8`

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
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
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
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_4c32fa7a72a13340317baef891270170_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18005fa34  mov     rax, rsp
0x18005fa37  mov     [rax+8], rbx
0x18005fa3b  mov     [rax+18h], rbp
0x18005fa3f  mov     [rax+10h], edx
0x18005fa42  push    rdi
0x18005fa43  sub     rsp, 60h
0x18005fa47  xorps   xmm0, xmm0
0x18005fa4a  mov     ebx, ecx
0x18005fa4c  movups  xmmword ptr [rax-38h], xmm0
0x18005fa50  mov     rdi, r8
0x18005fa53  mov     dword ptr [rax+10h], 0
0x18005fa5a  movups  xmmword ptr [rax-28h], xmm0
0x18005fa5e  movups  xmmword ptr [rax-18h], xmm0
0x18005fa62  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fa69  lea     rbp, WPP_GLOBAL_Control
0x18005fa70  cmp     rcx, rbp
0x18005fa73  jz      short loc_18005FA90
0x18005fa75  test    byte ptr [rcx+1Ch], 4
0x18005fa79  jz      short loc_18005FA90
0x18005fa7b  mov     rcx, [rcx+10h]
0x18005fa7f  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005fa86  mov     edx, 0Ch
0x18005fa8b  call    WPP_SF_
0x18005fa90  test    ebx, ebx
0x18005fa92  jnz     short loc_18005FA9E
0x18005fa94  mov     ebx, 57h ; 'W'
0x18005fa99  jmp     loc_18005FB2C
0x18005fa9e  xor     edx, edx; bInheritHandle
0x18005faa0  mov     [rdi+18h], rbx
0x18005faa4  mov     r8d, ebx; dwThreadId
0x18005faa7  mov     qword ptr [rdi+10h], 0
0x18005faaf  mov     qword ptr [rdi+8], 0
0x18005fab7  lea     ecx, [rdx+48h]; dwDesiredAccess
0x18005faba  call    cs:__imp_OpenThread
0x18005fac0  mov     [rdi], rax
0x18005fac3  test    rax, rax
0x18005fac6  jnz     short loc_18005FAD0
0x18005fac8  call    cs:__imp_GetLastError
0x18005face  jmp     short loc_18005FB26
0x18005fad0  lea     rcx, [rsp+68h+arg_8]
0x18005fad5  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18005fadb  mov     [rsp+68h+ReturnLength], rcx; ReturnLength
0x18005fae0  lea     r8, [rsp+68h+ThreadInformation]; ThreadInformation
0x18005fae5  mov     rcx, rax; ThreadHandle
0x18005fae8  xor     edx, edx; ThreadInformationClass
0x18005faea  call    cs:__imp_NtQueryInformationThread
0x18005faf0  test    eax, eax
0x18005faf2  js      short loc_18005FB1E
0x18005faf4  cmp     [rsp+68h+arg_8], 30h ; '0'
0x18005faf9  jnz     short loc_18005FB1E
0x18005fafb  mov     r8, qword ptr [rsp+68h+dwProcessId]; dwProcessId
0x18005fb00  xor     edx, edx; bInheritHandle
0x18005fb02  mov     ecx, 450h; dwDesiredAccess
0x18005fb07  mov     [rdi+10h], r8
0x18005fb0b  call    cs:__imp_OpenProcess
0x18005fb11  mov     [rdi+8], rax
0x18005fb15  test    rax, rax
0x18005fb18  jz      short loc_18005FAC8
0x18005fb1a  xor     ebx, ebx
0x18005fb1c  jmp     short loc_18005FB34
0x18005fb1e  mov     ecx, eax; Status
0x18005fb20  call    cs:__imp_RtlNtStatusToDosError
0x18005fb26  mov     ebx, eax
0x18005fb28  test    eax, eax
0x18005fb2a  jz      short loc_18005FB34
0x18005fb2c  mov     rcx, rdi; struct _WCT_CLIENT_HANDLE *
0x18005fb2f  call    ?WctFreeClient@@YAXPEAU_WCT_CLIENT_HANDLE@@@Z; WctFreeClient(_WCT_CLIENT_HANDLE *)
0x18005fb34  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fb3b  cmp     rcx, rbp
0x18005fb3e  jz      short loc_18005FB5E
0x18005fb40  test    byte ptr [rcx+1Ch], 4
0x18005fb44  jz      short loc_18005FB5E
0x18005fb46  mov     rcx, [rcx+10h]
0x18005fb4a  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18005fb51  mov     edx, 0Dh
0x18005fb56  mov     r9d, ebx
0x18005fb59  call    WPP_SF_d
0x18005fb5e  lea     r11, [rsp+68h+var_8]
0x18005fb63  mov     eax, ebx
0x18005fb65  mov     rbx, [r11+10h]
0x18005fb69  mov     rbp, [r11+20h]
0x18005fb6d  mov     rsp, r11
0x18005fb70  pop     rdi
0x18005fb71  retn
```
