# ShellProvider::GetObjectInfo(ushort const *,ulong &,ulong &)

- ea: `0x1801b6370`
- end: `0x1801b6705`
- name: `?GetObjectInfo@ShellProvider@@AEAAHPEBGAEAK1@Z`
- size: `917`
- prototype: `int(ShellProvider *__hidden this, const unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1801b6dc4`

## callees

- `0x1800621e0`
- `0x180071400`
- `0x180112380`
- `0x1801123a8`
- `0x1801b6370`
- `0x1801ba152`
- `0x1801ba1b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b64c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b6566`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b64c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801b6566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b646e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b65dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6415`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b646e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6533`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b65dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6669`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801b65cb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801b65cb`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1801b662a`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x1801b662a`
- `api-ms-win-core-job-l2-1-0!OpenJobObjectW` at `0x1801b63e9`
- `api-ms-win-core-job-l2-1-0!OpenJobObjectW` at `0x1801b63e9`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x1801b644a`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x1801b6510`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x1801b644a`
- `api-ms-win-core-job-l2-1-0!QueryInformationJobObject` at `0x1801b6510`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShellProvider::GetObjectInfo(
        ShellProvider *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  HANDLE v7; // rax
  void *v8; // rbx
  DWORD LastError; // eax
  __int64 v10; // rdx
  unsigned int v11; // esi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  DWORD v14; // r14d
  unsigned int *v15; // rdi
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  unsigned int i; // r14d
  HANDLE v20; // rbx
  DWORD v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  HANDLE v24; // [rsp+30h] [rbp-79h] BYREF
  HANDLE v25; // [rsp+38h] [rbp-71h] BYREF
  _OWORD JobObjectInformation[2]; // [rsp+40h] [rbp-69h] BYREF
  __int128 v27; // [rsp+60h] [rbp-49h]
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+70h] [rbp-39h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_b60bdead82443c7f6980630edf2d3038_Traceguids);
  *a3 = 0;
  *a4 = 0;
  v7 = OpenJobObjectW(4u, 0, a2);
  v8 = v7;
  v25 = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      goto LABEL_30;
    LastError = GetLastError();
    v10 = 116;
    goto LABEL_24;
  }
  memset(JobObjectInformation, 0, sizeof(JobObjectInformation));
  v27 = 0;
  v11 = 1;
  if ( !QueryInformationJobObject(v7, JobObjectBasicAccountingInformation, JobObjectInformation, 0x30u, 0) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      goto LABEL_30;
    LastError = GetLastError();
    v10 = 117;
    goto LABEL_24;
  }
  if ( DWORD2(v27) )
  {
    v14 = 8 * DWORD2(v27) + 8;
    v15 = (unsigned int *)WSManMemory::Alloc(v14, 0, 0);
    if ( v15 )
    {
      *v15 = DWORD2(v27);
      if ( !QueryInformationJobObject(v8, JobObjectBasicProcessIdList, v15, v14, 0) )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
          goto LABEL_30;
        LastError = GetLastError();
        v10 = 120;
LABEL_24:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_b60bdead82443c7f6980630edf2d3038_Traceguids, LastError);
LABEL_30:
        AutoCleanup<AutoHandle,void *>::ReleasePtr(&v25);
        return 0;
      }
      if ( *v15 <= v15[1] )
      {
        *a4 = 0;
        for ( i = 0; i < *v15; ++i )
        {
          v20 = OpenProcess(0x400u, 0, v15[2 * i + 2]);
          v24 = v20;
          if ( v20 )
          {
            memset_0(&ppsmemCounters, 0, 0x50u);
            if ( !K32GetProcessMemoryInfo(v20, &ppsmemCounters, 0x50u) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              {
                v21 = GetLastError();
                v23 = 123;
                v22 = WPP_GLOBAL_Control;
LABEL_44:
                WPP_SF_d(v22[2], v23, WPP_b60bdead82443c7f6980630edf2d3038_Traceguids, v21);
              }
LABEL_45:
              AutoCleanup<AutoHandle,void *>::ReleasePtr(&v24);
              v11 = 0;
              goto LABEL_50;
            }
            *a4 += ppsmemCounters.WorkingSetSize >> 20;
          }
          else
          {
            v21 = GetLastError();
            if ( v21 != 2 )
            {
              v22 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              {
                v23 = 122;
                goto LABEL_44;
              }
              goto LABEL_45;
            }
          }
          AutoCleanup<AutoHandle,void *>::ReleasePtr(&v24);
        }
        *a3 = DWORD2(v27) - 1;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
          goto LABEL_50;
        v13 = 124;
        goto LABEL_49;
      }
      SetLastError(0x1Fu);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        goto LABEL_30;
      v17 = 121;
    }
    else
    {
      SetLastError(0xEu);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        goto LABEL_30;
      v17 = 119;
    }
    WPP_SF_(v16[2], v17, WPP_b60bdead82443c7f6980630edf2d3038_Traceguids);
    goto LABEL_30;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    goto LABEL_50;
  v13 = 118;
LABEL_49:
  WPP_SF_(v12[2], v13, WPP_b60bdead82443c7f6980630edf2d3038_Traceguids);
LABEL_50:
  AutoCleanup<AutoHandle,void *>::ReleasePtr(&v25);
  return v11;
}

```

## disassembly

```asm
0x1801b6370  mov     [rsp-8+arg_0], rbx
0x1801b6375  push    rbp
0x1801b6376  push    rsi
0x1801b6377  push    rdi
0x1801b6378  push    r12
0x1801b637a  push    r13
0x1801b637c  push    r14
0x1801b637e  push    r15
0x1801b6380  lea     rbp, [rsp-27h]
0x1801b6385  sub     rsp, 0D0h
0x1801b638c  mov     rax, cs:__security_cookie
0x1801b6393  xor     rax, rsp
0x1801b6396  mov     [rbp+57h+var_40], rax
0x1801b639a  mov     r15, r9
0x1801b639d  mov     r12, r8
0x1801b63a0  mov     rbx, rdx
0x1801b63a3  lea     rdi, WPP_GLOBAL_Control
0x1801b63aa  mov     r13d, 400h
0x1801b63b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b63b7  cmp     rcx, rdi
0x1801b63ba  jz      short loc_1801B63D7
0x1801b63bc  test    [rcx+1Ch], r13d
0x1801b63c0  jz      short loc_1801B63D7
0x1801b63c2  mov     edx, 73h ; 's'
0x1801b63c7  lea     r8, WPP_b60bdead82443c7f6980630edf2d3038_Traceguids
0x1801b63ce  mov     rcx, [rcx+10h]
0x1801b63d2  call    WPP_SF_
0x1801b63d7  xor     r14d, r14d
0x1801b63da  mov     [r12], r14d
0x1801b63de  mov     [r15], r14d
0x1801b63e1  mov     r8, rbx; lpName
0x1801b63e4  xor     edx, edx; bInheritHandle
0x1801b63e6  lea     ecx, [rdx+4]; dwDesiredAccess
0x1801b63e9  call    cs:__imp_OpenJobObjectW
0x1801b63ef  mov     rbx, rax
0x1801b63f2  mov     [rbp+57h+var_C8], rax
0x1801b63f6  test    rax, rax
0x1801b63f9  jnz     short loc_1801B6423
0x1801b63fb  mov     rax, cs:WPP_GLOBAL_Control
0x1801b6402  cmp     rax, rdi
0x1801b6405  jz      loc_1801B659B
0x1801b640b  test    [rax+1Ch], r13d
0x1801b640f  jz      loc_1801B659B
0x1801b6415  call    cs:__imp_GetLastError
0x1801b641b  lea     edx, [rbx+74h]
0x1801b641e  jmp     loc_1801B653E
0x1801b6423  xorps   xmm0, xmm0
0x1801b6426  movups  [rbp+57h+JobObjectInformation], xmm0
0x1801b642a  movups  [rbp+57h+var_B0], xmm0
0x1801b642e  movups  [rbp+57h+var_A0], xmm0
0x1801b6432  mov     [rsp+100h+lpReturnLength], r14; lpReturnLength
0x1801b6437  mov     r9d, 30h ; '0'; cbJobObjectInformationLength
0x1801b643d  lea     r8, [rbp+57h+JobObjectInformation]; lpJobObjectInformation
0x1801b6441  lea     esi, [r9-2Fh]
0x1801b6445  mov     edx, esi; JobObjectInformationClass
0x1801b6447  mov     rcx, rbx; hJob
0x1801b644a  call    cs:__imp_QueryInformationJobObject
0x1801b6450  test    eax, eax
0x1801b6452  jnz     short loc_1801B647C
0x1801b6454  mov     rax, cs:WPP_GLOBAL_Control
0x1801b645b  cmp     rax, rdi
0x1801b645e  jz      loc_1801B659B
0x1801b6464  test    [rax+1Ch], r13d
0x1801b6468  jz      loc_1801B659B
0x1801b646e  call    cs:__imp_GetLastError
0x1801b6474  lea     edx, [rsi+74h]
0x1801b6477  jmp     loc_1801B653E
0x1801b647c  mov     eax, dword ptr [rbp+57h+var_A0+8]
0x1801b647f  test    eax, eax
0x1801b6481  jnz     short loc_1801B64A5
0x1801b6483  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b648a  cmp     rcx, rdi
0x1801b648d  jz      loc_1801B66D3
0x1801b6493  test    [rcx+1Ch], r13d
0x1801b6497  jz      loc_1801B66D3
0x1801b649d  lea     edx, [rax+76h]
0x1801b64a0  jmp     loc_1801B66C2
0x1801b64a5  lea     r14d, ds:8[rax*8]
0x1801b64ad  mov     ecx, r14d
0x1801b64b0  xor     r8d, r8d
0x1801b64b3  xor     edx, edx
0x1801b64b5  call    ?Alloc@WSManMemory@@SAPEAX_KHW4_NitsFaultMode@@@Z; WSManMemory::Alloc(unsigned __int64,int,_NitsFaultMode)
0x1801b64ba  mov     rdi, rax
0x1801b64bd  test    rax, rax
0x1801b64c0  jnz     short loc_1801B64F4
0x1801b64c2  lea     ecx, [rax+0Eh]; dwErrCode
0x1801b64c5  call    cs:__imp_SetLastError
0x1801b64cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b64d2  lea     rdx, WPP_GLOBAL_Control
0x1801b64d9  cmp     rcx, rdx
0x1801b64dc  jz      loc_1801B659B
0x1801b64e2  test    [rcx+1Ch], r13d
0x1801b64e6  jz      loc_1801B659B
0x1801b64ec  lea     edx, [rdi+77h]
0x1801b64ef  jmp     loc_1801B658A
0x1801b64f4  mov     eax, dword ptr [rbp+57h+var_A0+8]
0x1801b64f7  mov     [rdi], eax
0x1801b64f9  mov     [rsp+100h+lpReturnLength], 0; lpReturnLength
0x1801b6502  mov     r9d, r14d; cbJobObjectInformationLength
0x1801b6505  mov     r8, rdi; lpJobObjectInformation
0x1801b6508  mov     edx, 3; JobObjectInformationClass
0x1801b650d  mov     rcx, rbx; hJob
0x1801b6510  call    cs:__imp_QueryInformationJobObject
0x1801b6516  test    eax, eax
0x1801b6518  jnz     short loc_1801B655A
0x1801b651a  mov     rax, cs:WPP_GLOBAL_Control
0x1801b6521  lea     rdx, WPP_GLOBAL_Control
0x1801b6528  cmp     rax, rdx
0x1801b652b  jz      short loc_1801B659B
0x1801b652d  test    [rax+1Ch], r13d
0x1801b6531  jz      short loc_1801B659B
0x1801b6533  call    cs:__imp_GetLastError
0x1801b6539  mov     edx, 78h ; 'x'
0x1801b653e  mov     r9d, eax
0x1801b6541  lea     r8, WPP_b60bdead82443c7f6980630edf2d3038_Traceguids
0x1801b6548  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b654f  mov     rcx, [rcx+10h]
0x1801b6553  call    WPP_SF_d
0x1801b6558  jmp     short loc_1801B659B
0x1801b655a  mov     eax, [rdi+4]
0x1801b655d  cmp     [rdi], eax
0x1801b655f  jbe     short loc_1801B65AB
0x1801b6561  mov     ecx, 1Fh; dwErrCode
0x1801b6566  call    cs:__imp_SetLastError
0x1801b656c  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b6573  lea     rdx, WPP_GLOBAL_Control
0x1801b657a  cmp     rcx, rdx
0x1801b657d  jz      short loc_1801B659B
0x1801b657f  test    [rcx+1Ch], r13d
0x1801b6583  jz      short loc_1801B659B
0x1801b6585  mov     edx, 79h ; 'y'
0x1801b658a  lea     r8, WPP_b60bdead82443c7f6980630edf2d3038_Traceguids
0x1801b6591  mov     rcx, [rcx+10h]
0x1801b6595  call    WPP_SF_
0x1801b659a  nop
0x1801b659b  lea     rcx, [rbp+57h+var_C8]
0x1801b659f  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1801b65a4  xor     eax, eax
0x1801b65a6  jmp     loc_1801B66DE
0x1801b65ab  mov     dword ptr [r15], 0
0x1801b65b2  xor     r14d, r14d
0x1801b65b5  cmp     r14d, [rdi]
0x1801b65b8  jnb     loc_1801B669B
0x1801b65be  movsxd  r8, r14d
0x1801b65c1  mov     r8d, [rdi+r8*8+8]; dwProcessId
0x1801b65c6  xor     edx, edx; bInheritHandle
0x1801b65c8  mov     ecx, r13d; dwDesiredAccess
0x1801b65cb  call    cs:__imp_OpenProcess
0x1801b65d1  mov     rbx, rax
0x1801b65d4  mov     [rbp+57h+var_D0], rax
0x1801b65d8  test    rax, rax
0x1801b65db  jnz     short loc_1801B660E
0x1801b65dd  call    cs:__imp_GetLastError
0x1801b65e3  cmp     eax, 2
0x1801b65e6  jz      short loc_1801B663F
0x1801b65e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b65ef  lea     rdx, WPP_GLOBAL_Control
0x1801b65f6  cmp     rcx, rdx
0x1801b65f9  jz      loc_1801B668E
0x1801b65ff  test    [rcx+1Ch], r13d
0x1801b6603  jz      loc_1801B668E
0x1801b6609  lea     edx, [rbx+7Ah]
0x1801b660c  jmp     short loc_1801B667B
0x1801b660e  xor     edx, edx; Val
0x1801b6610  lea     r8d, [rdx+50h]; Size
0x1801b6614  lea     rcx, [rbp+57h+ppsmemCounters]; void *
0x1801b6618  call    memset_0
0x1801b661d  mov     r8d, 50h ; 'P'; cb
0x1801b6623  lea     rdx, [rbp+57h+ppsmemCounters]; ppsmemCounters
0x1801b6627  mov     rcx, rbx; Process
0x1801b662a  call    cs:__imp_K32GetProcessMemoryInfo
0x1801b6630  test    eax, eax
0x1801b6632  jz      short loc_1801B6650
0x1801b6634  mov     rax, [rbp+57h+ppsmemCounters.WorkingSetSize]
0x1801b6638  shr     rax, 14h
0x1801b663c  add     [r15], eax
0x1801b663f  lea     rcx, [rbp+57h+var_D0]
0x1801b6643  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1801b6648  add     r14d, esi
0x1801b664b  jmp     loc_1801B65B5
0x1801b6650  mov     rax, cs:WPP_GLOBAL_Control
0x1801b6657  lea     rdx, WPP_GLOBAL_Control
0x1801b665e  cmp     rax, rdx
0x1801b6661  jz      short loc_1801B668E
0x1801b6663  test    [rax+1Ch], r13d
0x1801b6667  jz      short loc_1801B668E
0x1801b6669  call    cs:__imp_GetLastError
0x1801b666f  mov     edx, 7Bh ; '{'
0x1801b6674  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b667b  mov     r9d, eax
0x1801b667e  lea     r8, WPP_b60bdead82443c7f6980630edf2d3038_Traceguids
0x1801b6685  mov     rcx, [rcx+10h]
0x1801b6689  call    WPP_SF_d
0x1801b668e  lea     rcx, [rbp+57h+var_D0]
0x1801b6692  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1801b6697  xor     esi, esi
0x1801b6699  jmp     short loc_1801B66D3
0x1801b669b  mov     eax, dword ptr [rbp+57h+var_A0+8]
0x1801b669e  dec     eax
0x1801b66a0  mov     [r12], eax
0x1801b66a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1801b66ab  lea     rdx, WPP_GLOBAL_Control
0x1801b66b2  cmp     rcx, rdx
0x1801b66b5  jz      short loc_1801B66D3
0x1801b66b7  test    [rcx+1Ch], r13d
0x1801b66bb  jz      short loc_1801B66D3
0x1801b66bd  mov     edx, 7Ch ; '|'
0x1801b66c2  lea     r8, WPP_b60bdead82443c7f6980630edf2d3038_Traceguids
0x1801b66c9  mov     rcx, [rcx+10h]
0x1801b66cd  call    WPP_SF_
0x1801b66d2  nop
0x1801b66d3  lea     rcx, [rbp+57h+var_C8]
0x1801b66d7  call    ?ReleasePtr@?$AutoCleanup@VAutoHandle@@PEAX@@AEAAXXZ; AutoCleanup<AutoHandle,void *>::ReleasePtr(void)
0x1801b66dc  mov     eax, esi
0x1801b66de  mov     rcx, [rbp+57h+var_40]
0x1801b66e2  xor     rcx, rsp; StackCookie
0x1801b66e5  call    __security_check_cookie
0x1801b66ea  mov     rbx, [rsp+100h+arg_0]
0x1801b66f2  add     rsp, 0D0h
0x1801b66f9  pop     r15
0x1801b66fb  pop     r14
0x1801b66fd  pop     r13
0x1801b66ff  pop     r12
0x1801b6701  pop     rdi
0x1801b6702  pop     rsi
0x1801b6703  pop     rbp
0x1801b6704  retn
```
