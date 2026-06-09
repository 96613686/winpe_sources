# FAX_AnswerCall

- ea: `0x140016de0`
- end: `0x1400170d7`
- name: `FAX_AnswerCall`
- size: `759`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140016de0`
- `0x140047d20`
- `0x140051dec`
- `0x14007ab38`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140017001`
- `KERNEL32!GetLastError` at `0x140017076`
- `KERNEL32!GetLastError` at `0x14001709c`
- `KERNEL32!GetLastError` at `0x140017001`
- `KERNEL32!GetLastError` at `0x140017076`
- `KERNEL32!GetLastError` at `0x14001709c`
- `KERNEL32!LocalFree` at `0x1400170c6`
- `KERNEL32!LocalFree` at `0x1400170c6`
- `KERNEL32!EnterCriticalSection` at `0x140016f2a`
- `KERNEL32!EnterCriticalSection` at `0x140016f2a`
- `KERNEL32!LeaveCriticalSection` at `0x140016f90`
- `KERNEL32!LeaveCriticalSection` at `0x140016f90`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140017062`
- `KERNEL32!PostQueuedCompletionStatus` at `0x140017062`
- `KERNEL32!LocalAlloc` at `0x140016fed`
- `KERNEL32!LocalAlloc` at `0x140016fed`

## pseudocode

```c
__int64 __fastcall FAX_AnswerCall(__int64 a1, unsigned int a2)
{
  unsigned __int64 v2; // rsi
  __int64 result; // rax
  CMapDeviceId *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // eax
  DWORD_PTR v7; // rax
  DWORD LastError; // ebx
  __int64 v9; // r9
  struct _OVERLAPPED *v10; // rax
  struct _OVERLAPPED *v11; // rdi
  HANDLE v12; // rcx
  DWORD v13; // eax
  unsigned int v14; // [rsp+50h] [rbp+18h] BYREF
  int v15; // [rsp+58h] [rbp+20h] BYREF

  v2 = a2;
  v14 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 589, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  v15 = 0;
  result = FaxSvcAccessCheck(0x2000000u, &v15, &v14, 1);
  if ( !(_DWORD)result )
  {
    if ( (v14 & 0xE03FF) == 0 )
      return 5;
    if ( !(unsigned int)CanAccessUnAssignedFaxes(v14, 1) )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 5;
      }
      v5 = 590;
      goto LABEL_12;
    }
    v14 = 0;
    v6 = IsLocalRPCConnectionNP(&v14);
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 591, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v6);
      }
      return 5;
    }
    if ( !v14 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 5;
      }
      v5 = 592;
LABEL_12:
      WPP_SF_(*((_QWORD *)v4 + 2), v5, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
      return 5;
    }
    EnterCriticalSection(&g_CsLine);
    v7 = g_TapiLinesListHead;
    if ( g_TapiLinesListHead )
    {
      while ( (DWORD_PTR *)v7 != &g_TapiLinesListHead )
      {
        if ( *(_DWORD *)(v7 + 24) == (_DWORD)v2 )
        {
          if ( !v7 )
            break;
          v9 = *(unsigned int *)(v7 + 72);
          if ( (_DWORD)v9 == 537919488 )
          {
            v10 = (struct _OVERLAPPED *)LocalAlloc(0x40u, 0x28u);
            v11 = v10;
            if ( v10 )
            {
              v12 = g_TapiCompletionPort;
              LastError = 0;
              v10->Pointer = (PVOID)v2;
              if ( !PostQueuedCompletionStatus(v12, 0x28u, 0x80000005, v10) )
              {
                LastError = GetLastError();
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v13 = GetLastError();
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    596,
                    &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                    v13);
                }
                LocalFree(v11);
              }
            }
            else
            {
              LastError = GetLastError();
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 595, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
              }
            }
          }
          else
          {
            LastError = 170;
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 594, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v9);
            }
          }
          goto LABEL_34;
        }
        v7 = *(_QWORD *)v7;
      }
    }
    LastError = 87;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        593,
        &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
        (unsigned int)v2);
    }
LABEL_34:
    LeaveCriticalSection(&g_CsLine);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x140016de0  mov     [rsp+arg_0], rbx
0x140016de5  mov     [rsp+arg_8], rsi
0x140016dea  push    rdi
0x140016deb  push    r12
0x140016ded  push    r15
0x140016def  sub     rsp, 20h
0x140016df3  mov     esi, edx
0x140016df5  mov     [rsp+38h+arg_10], 0
0x140016dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e04  lea     r15, WPP_GLOBAL_Control
0x140016e0b  lea     r12, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x140016e12  cmp     rcx, r15
0x140016e15  jz      short loc_140016E34
0x140016e17  test    byte ptr [rcx+1Ch], 4
0x140016e1b  jz      short loc_140016E34
0x140016e1d  cmp     byte ptr [rcx+19h], 5
0x140016e21  jb      short loc_140016E34
0x140016e23  mov     rcx, [rcx+10h]
0x140016e27  mov     edx, 24Dh
0x140016e2c  mov     r8, r12
0x140016e2f  call    WPP_SF_
0x140016e34  mov     ebx, 1
0x140016e39  mov     [rsp+38h+arg_18], 0
0x140016e41  mov     r9d, ebx; int
0x140016e44  lea     r8, [rsp+38h+arg_10]; unsigned int *
0x140016e49  lea     rdx, [rsp+38h+arg_18]; int *
0x140016e4e  mov     ecx, 2000000h; unsigned int
0x140016e53  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x140016e58  test    eax, eax
0x140016e5a  jnz     short loc_140016EA1
0x140016e5c  mov     ecx, [rsp+38h+arg_10]; unsigned int
0x140016e60  test    ecx, 0E03FFh
0x140016e66  jz      short loc_140016E9C
0x140016e68  mov     edx, ebx; int
0x140016e6a  call    ?CanAccessUnAssignedFaxes@@YAHKH@Z; CanAccessUnAssignedFaxes(ulong,int)
0x140016e6f  test    eax, eax
0x140016e71  jnz     short loc_140016EB6
0x140016e73  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e7a  cmp     rcx, r15
0x140016e7d  jz      short loc_140016E9C
0x140016e7f  test    byte ptr [rcx+1Ch], 4
0x140016e83  jz      short loc_140016E9C
0x140016e85  cmp     byte ptr [rcx+19h], 2
0x140016e89  jb      short loc_140016E9C
0x140016e8b  mov     edx, 24Eh
0x140016e90  mov     rcx, [rcx+10h]
0x140016e94  mov     r8, r12
0x140016e97  call    WPP_SF_
0x140016e9c  mov     eax, 5
0x140016ea1  mov     rbx, [rsp+38h+arg_0]
0x140016ea6  mov     rsi, [rsp+38h+arg_8]
0x140016eab  add     rsp, 20h
0x140016eaf  pop     r15
0x140016eb1  pop     r12
0x140016eb3  pop     rdi
0x140016eb4  retn
0x140016eb6  lea     rcx, [rsp+38h+arg_10]
0x140016ebb  mov     [rsp+38h+arg_10], 0
0x140016ec3  call    IsLocalRPCConnectionNP
0x140016ec8  test    eax, eax
0x140016eca  jz      short loc_140016EFA
0x140016ecc  mov     rcx, cs:WPP_GLOBAL_Control
0x140016ed3  cmp     rcx, r15
0x140016ed6  jz      short loc_140016E9C
0x140016ed8  test    byte ptr [rcx+1Ch], 4
0x140016edc  jz      short loc_140016E9C
0x140016ede  cmp     byte ptr [rcx+19h], 2
0x140016ee2  jb      short loc_140016E9C
0x140016ee4  mov     rcx, [rcx+10h]
0x140016ee8  mov     edx, 24Fh
0x140016eed  mov     r9d, eax
0x140016ef0  mov     r8, r12
0x140016ef3  call    WPP_SF_d
0x140016ef8  jmp     short loc_140016E9C
0x140016efa  cmp     [rsp+38h+arg_10], 0
0x140016eff  jnz     short loc_140016F23
0x140016f01  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f08  cmp     rcx, r15
0x140016f0b  jz      short loc_140016E9C
0x140016f0d  test    byte ptr [rcx+1Ch], 4
0x140016f11  jz      short loc_140016E9C
0x140016f13  cmp     byte ptr [rcx+19h], 2
0x140016f17  jb      short loc_140016E9C
0x140016f19  mov     edx, 250h
0x140016f1e  jmp     loc_140016E90
0x140016f23  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140016f2a  call    cs:__imp_EnterCriticalSection
0x140016f31  nop     dword ptr [rax+rax+00h]
0x140016f36  mov     rax, cs:?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x140016f3d  test    rax, rax
0x140016f40  jz      short loc_140016F58
0x140016f42  lea     rcx, ?g_TapiLinesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_TapiLinesListHead
0x140016f49  jmp     short loc_140016F53
0x140016f4b  cmp     [rax+18h], esi
0x140016f4e  jz      short loc_140016FA3
0x140016f50  mov     rax, [rax]
0x140016f53  cmp     rax, rcx
0x140016f56  jnz     short loc_140016F4B
0x140016f58  mov     ebx, 57h ; 'W'
0x140016f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f64  cmp     rcx, r15
0x140016f67  jz      short loc_140016F89
0x140016f69  test    byte ptr [rcx+1Ch], 4
0x140016f6d  jz      short loc_140016F89
0x140016f6f  cmp     byte ptr [rcx+19h], 2
0x140016f73  jb      short loc_140016F89
0x140016f75  mov     rcx, [rcx+10h]
0x140016f79  mov     edx, 251h
0x140016f7e  mov     r9d, esi
0x140016f81  mov     r8, r12
0x140016f84  call    WPP_SF_d
0x140016f89  lea     rcx, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140016f90  call    cs:__imp_LeaveCriticalSection
0x140016f97  nop     dword ptr [rax+rax+00h]
0x140016f9c  mov     eax, ebx
0x140016f9e  jmp     loc_140016EA1
0x140016fa3  test    rax, rax
0x140016fa6  jz      short loc_140016F58
0x140016fa8  mov     r9d, [rax+48h]
0x140016fac  cmp     r9d, 20100000h
0x140016fb3  jz      short loc_140016FE5
0x140016fb5  mov     ebx, 0AAh
0x140016fba  mov     rcx, cs:WPP_GLOBAL_Control
0x140016fc1  cmp     rcx, r15
0x140016fc4  jz      short loc_140016F89
0x140016fc6  test    byte ptr [rcx+1Ch], 4
0x140016fca  jz      short loc_140016F89
0x140016fcc  cmp     byte ptr [rcx+19h], 2
0x140016fd0  jb      short loc_140016F89
0x140016fd2  mov     rcx, [rcx+10h]
0x140016fd6  mov     edx, 252h
0x140016fdb  mov     r8, r12
0x140016fde  call    WPP_SF_d
0x140016fe3  jmp     short loc_140016F89
0x140016fe5  mov     edx, 28h ; '('; uBytes
0x140016fea  lea     ecx, [rdx+18h]; uFlags
0x140016fed  call    cs:__imp_LocalAlloc
0x140016ff4  nop     dword ptr [rax+rax+00h]
0x140016ff9  mov     rdi, rax
0x140016ffc  test    rax, rax
0x140016fff  jnz     short loc_140017049
0x140017001  call    cs:__imp_GetLastError
0x140017008  nop     dword ptr [rax+rax+00h]
0x14001700d  mov     ebx, eax
0x14001700f  mov     rcx, cs:WPP_GLOBAL_Control
0x140017016  cmp     rcx, r15
0x140017019  jz      loc_140016F89
0x14001701f  test    byte ptr [rcx+1Ch], 4
0x140017023  jz      loc_140016F89
0x140017029  cmp     byte ptr [rcx+19h], 2
0x14001702d  jb      loc_140016F89
0x140017033  mov     rcx, [rcx+10h]
0x140017037  mov     edx, 253h
0x14001703c  mov     r8, r12
0x14001703f  call    WPP_SF_
0x140017044  jmp     loc_140016F89
0x140017049  mov     rcx, cs:?g_TapiCompletionPort@@3PEAXEA; CompletionPort
0x140017050  xor     ebx, ebx
0x140017052  mov     r9, rdi; lpOverlapped
0x140017055  mov     [rax+10h], rsi
0x140017059  mov     r8d, 80000005h; dwCompletionKey
0x14001705f  lea     edx, [rbx+28h]; dwNumberOfBytesTransferred
0x140017062  call    cs:__imp_PostQueuedCompletionStatus
0x140017069  nop     dword ptr [rax+rax+00h]
0x14001706e  test    eax, eax
0x140017070  jnz     loc_140016F89
0x140017076  call    cs:__imp_GetLastError
0x14001707d  nop     dword ptr [rax+rax+00h]
0x140017082  mov     ebx, eax
0x140017084  mov     rax, cs:WPP_GLOBAL_Control
0x14001708b  cmp     rax, r15
0x14001708e  jz      short loc_1400170C3
0x140017090  test    byte ptr [rax+1Ch], 4
0x140017094  jz      short loc_1400170C3
0x140017096  cmp     byte ptr [rax+19h], 2
0x14001709a  jb      short loc_1400170C3
0x14001709c  call    cs:__imp_GetLastError
0x1400170a3  nop     dword ptr [rax+rax+00h]
0x1400170a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400170af  mov     edx, 254h
0x1400170b4  mov     r9d, eax
0x1400170b7  mov     r8, r12
0x1400170ba  mov     rcx, [rcx+10h]
0x1400170be  call    WPP_SF_d
0x1400170c3  mov     rcx, rdi; hMem
0x1400170c6  call    cs:__imp_LocalFree
0x1400170cd  nop     dword ptr [rax+rax+00h]
0x1400170d2  jmp     loc_140016F89
```
