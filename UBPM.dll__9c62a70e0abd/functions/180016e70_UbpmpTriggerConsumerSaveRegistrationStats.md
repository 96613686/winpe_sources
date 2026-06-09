# UbpmpTriggerConsumerSaveRegistrationStats

- ea: `0x180016e70`
- end: `0x180017102`
- name: `UbpmpTriggerConsumerSaveRegistrationStats`
- size: `658`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012b70`

## callees

- `0x180016e70`
- `0x1800182a0`
- `0x1800373c0`
- `0x180040260`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016eb9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180016eb9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016fc4`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180016fc4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016ec5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016ec5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016f2e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016f2e`

## pseudocode

```c
__int64 __fastcall UbpmpTriggerConsumerSaveRegistrationStats(
        __int64 a1,
        DWORD *a2,
        FILETIME *a3,
        __int64 *a4,
        FILETIME *a5)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx
  FILETIME v11; // rcx
  char v12; // bl
  DWORD dwLowDateTime; // r8d
  FILETIME v14; // rdx
  __int64 v15; // rax
  _QWORD *v17; // rcx
  int v18; // edx
  __int64 v19; // rax
  FILETIME FileTime1[5]; // [rsp+30h] [rbp-38h] BYREF

  memset(FileTime1, 0, 36);
  RtlAcquireSRWLockExclusive(a1 + 208);
  *(_DWORD *)(a1 + 216) = GetCurrentThreadId();
  v9 = UbpmStatsOperation(a1, 0, FileTime1);
  v10 = v9;
  if ( !v9 )
    goto LABEL_2;
  if ( v9 == 2 )
  {
    dwLowDateTime = *a2;
    FileTime1[0].dwLowDateTime = 3;
    if ( dwLowDateTime || a3->dwLowDateTime || a3->dwHighDateTime )
    {
      v11 = *a3;
      v12 = 1;
      *(FILETIME *)&FileTime1[1].dwHighDateTime = *a3;
      FileTime1[3].dwLowDateTime = dwLowDateTime;
      goto LABEL_11;
    }
LABEL_2:
    v11 = *(FILETIME *)&FileTime1[1].dwHighDateTime;
    if ( (a3->dwLowDateTime || a3->dwHighDateTime) && !FileTime1[1].dwHighDateTime && !FileTime1[2].dwLowDateTime )
      goto LABEL_10;
    v12 = 0;
    if ( (a3->dwLowDateTime || a3->dwHighDateTime) && (FileTime1[1].dwHighDateTime || FileTime1[2].dwLowDateTime) )
    {
      if ( CompareFileTime((const FILETIME *)&FileTime1[1].dwHighDateTime, a3) < 0 )
      {
LABEL_10:
        v11 = *a3;
        v12 = 1;
        dwLowDateTime = *a2;
        *(FILETIME *)&FileTime1[1].dwHighDateTime = *a3;
        FileTime1[3].dwLowDateTime = dwLowDateTime;
        goto LABEL_11;
      }
      v11 = *(FILETIME *)&FileTime1[1].dwHighDateTime;
    }
    dwLowDateTime = FileTime1[3].dwLowDateTime;
LABEL_11:
    if ( (a5->dwLowDateTime || a5->dwHighDateTime) && *a5 != *(_QWORD *)&FileTime1[3].dwHighDateTime )
    {
      v14 = *a5;
      v12 = 1;
      *(FILETIME *)&FileTime1[3].dwHighDateTime = *a5;
    }
    else
    {
      v14 = *(FILETIME *)&FileTime1[3].dwHighDateTime;
    }
    if ( (*(_DWORD *)a4 || *((_DWORD *)a4 + 1))
      && (*(_DWORD *)a4 != FileTime1[0].dwHighDateTime || *((_DWORD *)a4 + 1) != FileTime1[1].dwLowDateTime) )
    {
      v19 = *a4;
      *a2 = dwLowDateTime;
      *a3 = v11;
      *a5 = v14;
      *a4 = v19;
      *(_QWORD *)&FileTime1[0].dwHighDateTime = v19;
    }
    else
    {
      v15 = *(_QWORD *)&FileTime1[0].dwHighDateTime;
      *a2 = dwLowDateTime;
      *a3 = v11;
      *a5 = v14;
      *a4 = v15;
      if ( !v12 )
      {
        v10 = 0;
        goto LABEL_20;
      }
    }
    v10 = UbpmStatsOperation(a1, 1, FileTime1);
    if ( v10 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v18 = 157;
        goto LABEL_43;
      }
    }
    goto LABEL_20;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v18 = 156;
LABEL_43:
    WPP_SF_SL(
      v17[2],
      v18,
      (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
      *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL),
      *a2);
  }
LABEL_20:
  *(_DWORD *)(a1 + 216) = 0;
  RtlReleaseSRWLockExclusive(a1 + 208);
  return v10;
}

```

## disassembly

```asm
0x180016e70  push    rbp
0x180016e72  push    rbx
0x180016e73  push    rsi
0x180016e74  push    rdi
0x180016e75  push    r12
0x180016e77  push    r13
0x180016e79  push    r14
0x180016e7b  push    r15
0x180016e7d  mov     rbp, rsp
0x180016e80  sub     rsp, 68h
0x180016e84  mov     rax, cs:__security_cookie
0x180016e8b  xor     rax, rsp
0x180016e8e  mov     [rbp+var_10], rax
0x180016e92  mov     r14, [rbp+arg_20]
0x180016e96  xorps   xmm0, xmm0
0x180016e99  mov     r13, rcx
0x180016e9c  xor     eax, eax
0x180016e9e  add     rcx, 0D0h
0x180016ea5  mov     dword ptr [rbp+var_28+10h], eax
0x180016ea8  movups  xmmword ptr [rbp+FileTime1.dwLowDateTime], xmm0
0x180016eac  mov     r15, r9
0x180016eaf  mov     rsi, r8
0x180016eb2  movups  xmmword ptr [rbp+var_28], xmm0
0x180016eb6  mov     r12, rdx
0x180016eb9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180016ec0  nop     dword ptr [rax+rax+00h]
0x180016ec5  call    cs:__imp_GetCurrentThreadId
0x180016ecc  nop     dword ptr [rax+rax+00h]
0x180016ed1  lea     r8, [rbp+FileTime1]
0x180016ed5  xor     edx, edx
0x180016ed7  mov     rcx, r13
0x180016eda  mov     [r13+0D8h], eax
0x180016ee1  call    UbpmStatsOperation
0x180016ee6  mov     ebx, eax
0x180016ee8  test    eax, eax
0x180016eea  jnz     loc_180016FF9
0x180016ef0  mov     edx, [rsi]
0x180016ef2  mov     rcx, qword ptr [rbp+FileTime1.dwHighDateTime+8]
0x180016ef6  test    edx, edx
0x180016ef8  jz      short loc_180016F0D
0x180016efa  cmp     [rbp+FileTime1.dwHighDateTime+8], 0
0x180016efe  jnz     short loc_180016F13
0x180016f00  mov     rax, rcx
0x180016f03  shr     rax, 20h
0x180016f07  test    eax, eax
0x180016f09  jnz     short loc_180016F13
0x180016f0b  jmp     short loc_180016F42
0x180016f0d  cmp     dword ptr [rsi+4], 0
0x180016f11  jnz     short loc_180016EFA
0x180016f13  xor     bl, bl
0x180016f15  test    edx, edx
0x180016f17  jz      loc_180017052
0x180016f1d  cmp     [rbp+FileTime1.dwHighDateTime+8], 0
0x180016f21  jz      loc_18001705D
0x180016f27  mov     rdx, rsi; lpFileTime2
0x180016f2a  lea     rcx, [rbp+FileTime1.dwHighDateTime+8]; lpFileTime1
0x180016f2e  call    cs:__imp_CompareFileTime
0x180016f35  nop     dword ptr [rax+rax+00h]
0x180016f3a  test    eax, eax
0x180016f3c  jns     loc_18001706D
0x180016f42  mov     rcx, [rsi]
0x180016f45  mov     bl, 1
0x180016f47  mov     r8d, [r12]
0x180016f4b  mov     qword ptr [rbp+FileTime1.dwHighDateTime+8], rcx
0x180016f4f  mov     dword ptr [rbp+var_28+8], r8d
0x180016f53  mov     eax, [r14]
0x180016f56  test    eax, eax
0x180016f58  jnz     short loc_180016F60
0x180016f5a  cmp     [r14+4], eax
0x180016f5e  jz      short loc_180016F76
0x180016f60  cmp     eax, dword ptr [rbp+var_28+0Ch]
0x180016f63  jnz     loc_18001707A
0x180016f69  mov     eax, dword ptr [rbp+var_28+10h]
0x180016f6c  cmp     [r14+4], eax
0x180016f70  jnz     loc_18001707A
0x180016f76  mov     rdx, qword ptr [rbp+var_28+0Ch]
0x180016f7a  mov     eax, [r15]
0x180016f7d  test    eax, eax
0x180016f7f  jz      short loc_180016FF0
0x180016f81  cmp     eax, [rbp+FileTime1.dwHighDateTime]
0x180016f84  jnz     loc_180017088
0x180016f8a  mov     eax, [rbp+FileTime1.dwLowDateTime+8]
0x180016f8d  cmp     [r15+4], eax
0x180016f91  jnz     loc_180017088
0x180016f97  mov     rax, qword ptr [rbp+FileTime1.dwHighDateTime]
0x180016f9b  mov     [r12], r8d
0x180016f9f  mov     [rsi], rcx
0x180016fa2  mov     [r14], rdx
0x180016fa5  mov     [r15], rax
0x180016fa8  test    bl, bl
0x180016faa  jnz     loc_18001709C
0x180016fb0  xor     ebx, ebx
0x180016fb2  lea     rcx, [r13+0D0h]
0x180016fb9  mov     dword ptr [r13+0D8h], 0
0x180016fc4  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180016fcb  nop     dword ptr [rax+rax+00h]
0x180016fd0  mov     eax, ebx
0x180016fd2  mov     rcx, [rbp+var_10]
0x180016fd6  xor     rcx, rsp; StackCookie
0x180016fd9  call    __security_check_cookie
0x180016fde  add     rsp, 68h
0x180016fe2  pop     r15
0x180016fe4  pop     r14
0x180016fe6  pop     r13
0x180016fe8  pop     r12
0x180016fea  pop     rdi
0x180016feb  pop     rsi
0x180016fec  pop     rbx
0x180016fed  pop     rbp
0x180016fee  retn
0x180016ff0  cmp     dword ptr [r15+4], 0
0x180016ff5  jz      short loc_180016F97
0x180016ff7  jmp     short loc_180016F81
0x180016ff9  cmp     eax, 2
0x180016ffc  jz      short loc_180017021
0x180016ffe  mov     rcx, cs:WPP_GLOBAL_Control
0x180017005  lea     rax, WPP_GLOBAL_Control
0x18001700c  cmp     rcx, rax
0x18001700f  jz      short loc_180016FB2
0x180017011  test    byte ptr [rcx+1Ch], 1
0x180017015  jz      short loc_180016FB2
0x180017017  mov     edx, 9Ch
0x18001701c  jmp     loc_1800170DD
0x180017021  mov     r8d, [r12]
0x180017025  mov     [rbp+FileTime1.dwLowDateTime], 3
0x18001702c  test    r8d, r8d
0x18001702f  jnz     short loc_180017040
0x180017031  cmp     [rsi], r8d
0x180017034  jnz     short loc_180017040
0x180017036  cmp     [rsi+4], r8d
0x18001703a  jz      loc_180016EF0
0x180017040  mov     rcx, [rsi]
0x180017043  mov     bl, 1
0x180017045  mov     qword ptr [rbp+FileTime1.dwHighDateTime+8], rcx
0x180017049  mov     dword ptr [rbp+var_28+8], r8d
0x18001704d  jmp     loc_180016F53
0x180017052  cmp     dword ptr [rsi+4], 0
0x180017056  jz      short loc_180017071
0x180017058  jmp     loc_180016F1D
0x18001705d  mov     rax, rcx
0x180017060  shr     rax, 20h
0x180017064  test    eax, eax
0x180017066  jz      short loc_180017071
0x180017068  jmp     loc_180016F27
0x18001706d  mov     rcx, qword ptr [rbp+FileTime1.dwHighDateTime+8]
0x180017071  mov     r8d, dword ptr [rbp+var_28+8]
0x180017075  jmp     loc_180016F53
0x18001707a  mov     rdx, [r14]
0x18001707d  mov     bl, 1
0x18001707f  mov     qword ptr [rbp+var_28+0Ch], rdx
0x180017083  jmp     loc_180016F7A
0x180017088  mov     rax, [r15]
0x18001708b  mov     [r12], r8d
0x18001708f  mov     [rsi], rcx
0x180017092  mov     [r14], rdx
0x180017095  mov     [r15], rax
0x180017098  mov     qword ptr [rbp+FileTime1.dwHighDateTime], rax
0x18001709c  lea     r8, [rbp+FileTime1]
0x1800170a0  mov     edx, 1
0x1800170a5  mov     rcx, r13
0x1800170a8  call    UbpmStatsOperation
0x1800170ad  mov     ebx, eax
0x1800170af  test    eax, eax
0x1800170b1  jz      loc_180016FB2
0x1800170b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170be  lea     rax, WPP_GLOBAL_Control
0x1800170c5  cmp     rcx, rax
0x1800170c8  jz      loc_180016FB2
0x1800170ce  test    byte ptr [rcx+1Ch], 1
0x1800170d2  jz      loc_180016FB2
0x1800170d8  mov     edx, 9Dh
0x1800170dd  mov     r9, [r13+18h]
0x1800170e1  lea     r8, WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids
0x1800170e8  mov     eax, [r12]
0x1800170ec  mov     rcx, [rcx+10h]
0x1800170f0  mov     [rsp+68h+var_48], eax
0x1800170f4  mov     r9, [r9+8]
0x1800170f8  call    WPP_SF_SL
0x1800170fd  jmp     loc_180016FB2
```
