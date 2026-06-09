# InCritSecWithDeadLockDetection::InCritSecWithDeadLockDetection(CWSManCriticalSection *)

- ea: `0x180019650`
- end: `0x180019944`
- name: `??0InCritSecWithDeadLockDetection@@QEAA@PEAVCWSManCriticalSection@@@Z`
- size: `756`
- prototype: `InCritSecWithDeadLockDetection *__fastcall(InCritSecWithDeadLockDetection *this, DWORD *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180019490`
- `0x18007b2b0`
- `0x1800f0978`

## callees

- `0x180019650`
- `0x1800ea400`
- `0x180103850`
- `0x18011349c`
- `0x18011e370`
- `0x18011e3c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800198b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800196e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800197cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800196d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019786`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800196d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019786`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800196c0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019775`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800196c0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180019775`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800196a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18001975a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800196a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x18001975a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
InCritSecWithDeadLockDetection *__fastcall InCritSecWithDeadLockDetection::InCritSecWithDeadLockDetection(
        InCritSecWithDeadLockDetection *this,
        DWORD *a2)
{
  int v2; // r12d
  __int64 v5; // rsi
  __int64 v6; // r15
  HANDLE v7; // rax
  void *v8; // r13
  DWORD LastError; // eax
  __int64 v10; // r8
  int v11; // r13d
  __int64 v12; // r8
  HANDLE v13; // rax
  DWORD v14; // r13d
  bool v15; // zf
  DWORD v16; // r13d
  PVOID *v17; // rcx
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  DWORD v21; // [rsp+80h] [rbp+8h]
  int v22; // [rsp+88h] [rbp+10h]
  HANDLE hObject; // [rsp+90h] [rbp+18h]

  v2 = 0;
  *((_QWORD *)this + 1) = a2;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &InCritSecWithDeadLockDetection::`vftable';
  if ( !a2 )
  {
    *((_DWORD *)this + 5) = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_72e16b1785543df0970091bada6f0ddb_Traceguids, this, 0);
    return this;
  }
  if ( *a2 )
  {
    SetLastError(*a2);
    if ( *a2 )
    {
      SetLastError(*a2);
      *((_DWORD *)this + 5) = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        WPP_SF_qq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_72e16b1785543df0970091bada6f0ddb_Traceguids,
          this,
          *((_QWORD *)this + 1));
    }
    return this;
  }
  v5 = *((_QWORD *)a2 + 2);
  v6 = -1;
  v7 = OpenThread(0x100000u, 0, 0xFFFFFFFF);
  v8 = v7;
  if ( v7 )
  {
    v21 = WaitForSingleObject(v7, 0);
    CloseHandle(v8);
  }
  else
  {
    v21 = 0;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      WPP_SF_IL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v10, -1, LastError);
    v2 = 1;
  }
  v11 = 0;
  while ( !(unsigned int)CWSManCriticalSection::TryAcquire(*((CWSManCriticalSection **)this + 1)) )
  {
    if ( v11 >= 6000 )
      goto LABEL_30;
    v22 = v11 + 1;
    v5 = *(_QWORD *)(*((_QWORD *)this + 1) + 16LL);
    v13 = OpenThread(0x100000u, 0, v5);
    hObject = v13;
    if ( v13 )
    {
      v14 = WaitForSingleObject(v13, 0x32u);
      CloseHandle(hObject);
      if ( v14 >= 2 )
      {
        if ( v14 == -1 )
          goto LABEL_30;
        v15 = v14 == 128;
        goto LABEL_19;
      }
      if ( v21 <= 1 )
      {
        v15 = v6 == v5;
LABEL_19:
        if ( v15 )
          goto LABEL_30;
      }
      v2 = 0;
      v21 = v14;
      v6 = v5;
      goto LABEL_10;
    }
    v16 = GetLastError();
    v17 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_72e16b1785543df0970091bada6f0ddb_Traceguids);
      v17 = (PVOID *)WPP_GLOBAL_Control;
    }
    ++v2;
    if ( v6 == v5 && v2 > 1 )
    {
      if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 7) & 0x1000) != 0 )
        WPP_SF_IL(v17[2], 12, v12, v5, v16);
      v6 = v5;
LABEL_30:
      *((_DWORD *)this + 5) = 1;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        v19 = 13;
LABEL_36:
        WPP_SF_qqII(v18[2], v19, v12, this, *((_QWORD *)this + 1), v6, v5);
        return this;
      }
      return this;
    }
LABEL_10:
    v11 = v22;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
  {
    v19 = 14;
    goto LABEL_36;
  }
  return this;
}

```

## disassembly

```asm
0x180019650  push    rbx
0x180019652  push    rsi
0x180019653  push    rdi
0x180019654  push    r12
0x180019656  push    r13
0x180019658  push    r14
0x18001965a  push    r15
0x18001965c  sub     rsp, 40h
0x180019660  xor     r12d, r12d
0x180019663  mov     [rcx+8], rdx
0x180019667  mov     [rcx+10h], r12
0x18001966b  lea     rax, ??_7InCritSecWithDeadLockDetection@@6B@; const InCritSecWithDeadLockDetection::`vftable'
0x180019672  mov     [rcx], rax
0x180019675  mov     rsi, rdx
0x180019678  mov     rbx, rcx
0x18001967b  test    rdx, rdx
0x18001967e  jz      loc_1800198F0
0x180019684  mov     ecx, [rdx]; dwErrCode
0x180019686  test    ecx, ecx
0x180019688  jnz     loc_1800198AA
0x18001968e  mov     rsi, [rdx+10h]
0x180019692  or      r8d, 0FFFFFFFFh; dwThreadId
0x180019696  xor     edx, edx; bInheritHandle
0x180019698  mov     ecx, 100000h; dwDesiredAccess
0x18001969d  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800196a1  call    cs:__imp_OpenThread
0x1800196a7  lea     r14, WPP_GLOBAL_Control
0x1800196ae  mov     edi, 1000h
0x1800196b3  mov     r13, rax
0x1800196b6  test    rax, rax
0x1800196b9  jz      short loc_1800196D8
0x1800196bb  xor     edx, edx; dwMilliseconds
0x1800196bd  mov     rcx, rax; hHandle
0x1800196c0  call    cs:__imp_WaitForSingleObject
0x1800196c6  mov     rcx, r13; hObject
0x1800196c9  mov     [rsp+78h+arg_0], eax
0x1800196d0  call    cs:__imp_CloseHandle
0x1800196d6  jmp     short loc_180019712
0x1800196d8  mov     [rsp+78h+arg_0], r12d
0x1800196e0  call    cs:__imp_GetLastError
0x1800196e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196ed  cmp     rcx, r14
0x1800196f0  jz      short loc_18001970C
0x1800196f2  test    [rcx+1Ch], edi
0x1800196f5  jz      short loc_18001970C
0x1800196f7  mov     rcx, [rcx+10h]
0x1800196fb  mov     edx, 0Ah
0x180019700  mov     r9, r15
0x180019703  mov     dword ptr [rsp+78h+var_58], eax
0x180019707  call    WPP_SF_IL
0x18001970c  mov     r12d, 1
0x180019712  xor     r13d, r13d
0x180019715  jmp     short loc_18001971F
0x180019717  mov     r13d, [rsp+78h+arg_8]
0x18001971f  mov     rcx, [rbx+8]; this
0x180019723  call    ?TryAcquire@CWSManCriticalSection@@QEAAHXZ; CWSManCriticalSection::TryAcquire(void)
0x180019728  test    eax, eax
0x18001972a  jnz     loc_180019868
0x180019730  cmp     r13d, 1770h
0x180019737  jge     loc_180019841
0x18001973d  mov     rax, [rbx+8]
0x180019741  inc     r13d
0x180019744  xor     edx, edx; bInheritHandle
0x180019746  mov     [rsp+78h+arg_8], r13d
0x18001974e  mov     ecx, 100000h; dwDesiredAccess
0x180019753  mov     rsi, [rax+10h]
0x180019757  mov     r8d, esi; dwThreadId
0x18001975a  call    cs:__imp_OpenThread
0x180019760  mov     [rsp+78h+hObject], rax
0x180019768  test    rax, rax
0x18001976b  jz      short loc_1800197CB
0x18001976d  mov     edx, 32h ; '2'; dwMilliseconds
0x180019772  mov     rcx, rax; hHandle
0x180019775  call    cs:__imp_WaitForSingleObject
0x18001977b  mov     rcx, [rsp+78h+hObject]; hObject
0x180019783  mov     r13d, eax
0x180019786  call    cs:__imp_CloseHandle
0x18001978c  cmp     r13d, 2
0x180019790  jb      short loc_1800197A5
0x180019792  cmp     r13d, 0FFFFFFFFh
0x180019796  jz      loc_180019841
0x18001979c  cmp     r13d, 80h
0x1800197a3  jmp     short loc_1800197B2
0x1800197a5  cmp     [rsp+78h+arg_0], 1
0x1800197ad  ja      short loc_1800197B8
0x1800197af  cmp     r15, rsi
0x1800197b2  jz      loc_180019841
0x1800197b8  xor     r12d, r12d
0x1800197bb  mov     [rsp+78h+arg_0], r13d
0x1800197c3  mov     r15, rsi
0x1800197c6  jmp     loc_180019717
0x1800197cb  call    cs:__imp_GetLastError
0x1800197d1  mov     r13d, eax
0x1800197d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800197db  cmp     rcx, r14
0x1800197de  jz      short loc_180019808
0x1800197e0  test    [rcx+1Ch], edi
0x1800197e3  jz      short loc_180019808
0x1800197e5  mov     rcx, [rcx+10h]
0x1800197e9  lea     r8, WPP_72e16b1785543df0970091bada6f0ddb_Traceguids
0x1800197f0  mov     edx, 0Bh
0x1800197f5  mov     dword ptr [rsp+78h+var_58], eax
0x1800197f9  mov     r9d, esi
0x1800197fc  call    WPP_SF_Dd
0x180019801  mov     rcx, cs:WPP_GLOBAL_Control
0x180019808  inc     r12d
0x18001980b  cmp     r15, rsi
0x18001980e  jnz     loc_180019717
0x180019814  cmp     r12d, 1
0x180019818  jle     loc_180019717
0x18001981e  cmp     rcx, r14
0x180019821  jz      short loc_18001983E
0x180019823  test    [rcx+1Ch], edi
0x180019826  jz      short loc_18001983E
0x180019828  mov     rcx, [rcx+10h]
0x18001982c  mov     edx, 0Ch
0x180019831  mov     r9, rsi
0x180019834  mov     dword ptr [rsp+78h+var_58], r13d
0x180019839  call    WPP_SF_IL
0x18001983e  mov     r15, rsi
0x180019841  mov     dword ptr [rbx+14h], 1
0x180019848  mov     rcx, cs:WPP_GLOBAL_Control
0x18001984f  cmp     rcx, r14
0x180019852  jz      loc_180019931
0x180019858  test    [rcx+1Ch], edi
0x18001985b  jz      loc_180019931
0x180019861  mov     edx, 0Dh
0x180019866  jmp     short loc_180019886
0x180019868  mov     rcx, cs:WPP_GLOBAL_Control
0x18001986f  cmp     rcx, r14
0x180019872  jz      loc_180019931
0x180019878  test    [rcx+1Ch], edi
0x18001987b  jz      loc_180019931
0x180019881  mov     edx, 0Eh
0x180019886  mov     rax, [rbx+8]
0x18001988a  mov     r9, rbx
0x18001988d  mov     rcx, [rcx+10h]
0x180019891  mov     [rsp+78h+var_48], rsi
0x180019896  mov     [rsp+78h+var_50], r15
0x18001989b  mov     [rsp+78h+var_58], rax
0x1800198a0  call    WPP_SF_qqII
0x1800198a5  jmp     loc_180019931
0x1800198aa  call    cs:__imp_SetLastError
0x1800198b0  mov     ecx, [rsi]; dwErrCode
0x1800198b2  test    ecx, ecx
0x1800198b4  jz      short loc_180019931
0x1800198b6  call    cs:__imp_SetLastError
0x1800198bc  mov     dword ptr [rbx+14h], 1
0x1800198c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198ca  lea     r14, WPP_GLOBAL_Control
0x1800198d1  cmp     rcx, r14
0x1800198d4  jz      short loc_180019931
0x1800198d6  mov     edi, 1000h
0x1800198db  test    [rcx+1Ch], edi
0x1800198de  jz      short loc_180019931
0x1800198e0  mov     rax, [rbx+8]
0x1800198e4  mov     edx, 10h
0x1800198e9  mov     [rsp+78h+var_58], rax
0x1800198ee  jmp     short loc_18001991E
0x1800198f0  mov     dword ptr [rcx+14h], 1
0x1800198f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800198fe  lea     r14, WPP_GLOBAL_Control
0x180019905  cmp     rcx, r14
0x180019908  jz      short loc_180019931
0x18001990a  mov     edi, 1000h
0x18001990f  test    [rcx+1Ch], edi
0x180019912  jz      short loc_180019931
0x180019914  mov     edx, 0Fh
0x180019919  mov     [rsp+78h+var_58], rsi
0x18001991e  mov     rcx, [rcx+10h]
0x180019922  lea     r8, WPP_72e16b1785543df0970091bada6f0ddb_Traceguids
0x180019929  mov     r9, rbx
0x18001992c  call    WPP_SF_qq
0x180019931  mov     rax, rbx
0x180019934  add     rsp, 40h
0x180019938  pop     r15
0x18001993a  pop     r14
0x18001993c  pop     r13
0x18001993e  pop     r12
0x180019940  pop     rdi
0x180019941  pop     rsi
0x180019942  pop     rbx
0x180019943  retn
```
