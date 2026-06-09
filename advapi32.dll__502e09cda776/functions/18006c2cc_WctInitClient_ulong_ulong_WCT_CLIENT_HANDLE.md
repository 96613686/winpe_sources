# WctInitClient(ulong,ulong,_WCT_CLIENT_HANDLE *)

- ea: `0x18006c2cc`
- end: `0x18006c429`
- name: `?WctInitClient@@YAKKKPEAU_WCT_CLIENT_HANDLE@@@Z`
- size: `349`
- prototype: `unsigned int __fastcall(DWORD dwThreadId, unsigned int, struct _WCT_CLIENT_HANDLE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18006abb0`
- `0x18006be58`

## callees

- `0x18003fb18`
- `0x18003fd04`
- `0x18006a878`
- `0x18006c2cc`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18006c38e`
- `ntdll!NtQueryInformationThread` at `0x18006c38e`
- `ntdll!RtlNtStatusToDosError` at `0x18006c3d0`
- `ntdll!RtlNtStatusToDosError` at `0x18006c3d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18006c352`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18006c352`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006c3b5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18006c3b5`
- `KERNEL32!GetLastError` at `0x18006c366`
- `KERNEL32!GetLastError` at `0x18006c366`

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
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18006c2cc  mov     rax, rsp
0x18006c2cf  mov     [rax+8], rbx
0x18006c2d3  mov     [rax+18h], rbp
0x18006c2d7  mov     [rax+10h], edx
0x18006c2da  push    rdi
0x18006c2db  sub     rsp, 60h
0x18006c2df  xorps   xmm0, xmm0
0x18006c2e2  mov     ebx, ecx
0x18006c2e4  movups  xmmword ptr [rax-38h], xmm0
0x18006c2e8  mov     rdi, r8
0x18006c2eb  mov     dword ptr [rax+10h], 0
0x18006c2f2  movups  xmmword ptr [rax-28h], xmm0
0x18006c2f6  movups  xmmword ptr [rax-18h], xmm0
0x18006c2fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c301  lea     rbp, WPP_GLOBAL_Control
0x18006c308  cmp     rcx, rbp
0x18006c30b  jz      short loc_18006C328
0x18006c30d  test    byte ptr [rcx+1Ch], 4
0x18006c311  jz      short loc_18006C328
0x18006c313  mov     rcx, [rcx+10h]
0x18006c317  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18006c31e  mov     edx, 0Ch
0x18006c323  call    WPP_SF_
0x18006c328  test    ebx, ebx
0x18006c32a  jnz     short loc_18006C336
0x18006c32c  mov     ebx, 57h ; 'W'
0x18006c331  jmp     loc_18006C3E2
0x18006c336  xor     edx, edx; bInheritHandle
0x18006c338  mov     [rdi+18h], rbx
0x18006c33c  mov     r8d, ebx; dwThreadId
0x18006c33f  mov     qword ptr [rdi+10h], 0
0x18006c347  mov     qword ptr [rdi+8], 0
0x18006c34f  lea     ecx, [rdx+48h]; dwDesiredAccess
0x18006c352  call    cs:__imp_OpenThread
0x18006c359  nop     dword ptr [rax+rax+00h]
0x18006c35e  mov     [rdi], rax
0x18006c361  test    rax, rax
0x18006c364  jnz     short loc_18006C374
0x18006c366  call    cs:__imp_GetLastError
0x18006c36d  nop     dword ptr [rax+rax+00h]
0x18006c372  jmp     short loc_18006C3DC
0x18006c374  lea     rcx, [rsp+68h+arg_8]
0x18006c379  mov     r9d, 30h ; '0'; ThreadInformationLength
0x18006c37f  mov     [rsp+68h+ReturnLength], rcx; ReturnLength
0x18006c384  lea     r8, [rsp+68h+ThreadInformation]; ThreadInformation
0x18006c389  mov     rcx, rax; ThreadHandle
0x18006c38c  xor     edx, edx; ThreadInformationClass
0x18006c38e  call    cs:__imp_NtQueryInformationThread
0x18006c395  nop     dword ptr [rax+rax+00h]
0x18006c39a  test    eax, eax
0x18006c39c  js      short loc_18006C3CE
0x18006c39e  cmp     [rsp+68h+arg_8], 30h ; '0'
0x18006c3a3  jnz     short loc_18006C3CE
0x18006c3a5  mov     r8, qword ptr [rsp+68h+dwProcessId]; dwProcessId
0x18006c3aa  xor     edx, edx; bInheritHandle
0x18006c3ac  mov     ecx, 450h; dwDesiredAccess
0x18006c3b1  mov     [rdi+10h], r8
0x18006c3b5  call    cs:__imp_OpenProcess
0x18006c3bc  nop     dword ptr [rax+rax+00h]
0x18006c3c1  mov     [rdi+8], rax
0x18006c3c5  test    rax, rax
0x18006c3c8  jz      short loc_18006C366
0x18006c3ca  xor     ebx, ebx
0x18006c3cc  jmp     short loc_18006C3EA
0x18006c3ce  mov     ecx, eax; Status
0x18006c3d0  call    cs:__imp_RtlNtStatusToDosError
0x18006c3d7  nop     dword ptr [rax+rax+00h]
0x18006c3dc  mov     ebx, eax
0x18006c3de  test    eax, eax
0x18006c3e0  jz      short loc_18006C3EA
0x18006c3e2  mov     rcx, rdi; struct _WCT_CLIENT_HANDLE *
0x18006c3e5  call    ?WctFreeClient@@YAXPEAU_WCT_CLIENT_HANDLE@@@Z; WctFreeClient(_WCT_CLIENT_HANDLE *)
0x18006c3ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c3f1  cmp     rcx, rbp
0x18006c3f4  jz      short loc_18006C414
0x18006c3f6  test    byte ptr [rcx+1Ch], 4
0x18006c3fa  jz      short loc_18006C414
0x18006c3fc  mov     rcx, [rcx+10h]
0x18006c400  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18006c407  mov     edx, 0Dh
0x18006c40c  mov     r9d, ebx
0x18006c40f  call    WPP_SF_d
0x18006c414  lea     r11, [rsp+68h+var_8]
0x18006c419  mov     eax, ebx
0x18006c41b  mov     rbx, [r11+10h]
0x18006c41f  mov     rbp, [r11+20h]
0x18006c423  mov     rsp, r11
0x18006c426  pop     rdi
0x18006c427  retn
```
