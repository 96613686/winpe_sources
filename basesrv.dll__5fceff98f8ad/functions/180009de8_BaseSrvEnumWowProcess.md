# BaseSrvEnumWowProcess

- ea: `0x180009de8`
- end: `0x18000a088`
- name: `BaseSrvEnumWowProcess`
- size: `672`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000abe0`

## callees

- `0x180008da4`
- `0x180009de8`
- `0x18000abb4`
- `0x18000b400`
- `0x18000db1d`

## import_xrefs

- `ntdll!NtClose` at `0x180009f13`
- `ntdll!NtClose` at `0x180009fb4`
- `ntdll!NtClose` at `0x18000a039`
- `ntdll!NtClose` at `0x180009f13`
- `ntdll!NtClose` at `0x180009fb4`
- `ntdll!NtClose` at `0x18000a039`
- `ntdll!RtlEnterCriticalSection` at `0x180009e63`
- `ntdll!RtlEnterCriticalSection` at `0x180009ebc`
- `ntdll!RtlEnterCriticalSection` at `0x180009f4c`
- `ntdll!RtlEnterCriticalSection` at `0x180009e63`
- `ntdll!RtlEnterCriticalSection` at `0x180009ebc`
- `ntdll!RtlEnterCriticalSection` at `0x180009f4c`
- `ntdll!RtlLeaveCriticalSection` at `0x180009ea5`
- `ntdll!RtlLeaveCriticalSection` at `0x180009efe`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a057`
- `ntdll!RtlLeaveCriticalSection` at `0x180009ea5`
- `ntdll!RtlLeaveCriticalSection` at `0x180009efe`
- `ntdll!RtlLeaveCriticalSection` at `0x18000a057`
- `CSRSRV!CsrRevertToSelf` at `0x18000a063`
- `CSRSRV!CsrRevertToSelf` at `0x18000a063`
- `CSRSRV!CsrImpersonateClient` at `0x180009f28`
- `CSRSRV!CsrImpersonateClient` at `0x180009f28`

## pseudocode

```c
__int64 __fastcall BaseSrvEnumWowProcess(unsigned int *a1)
{
  size_t v1; // r8
  void *v3; // rcx
  __int64 v4; // rcx
  int SharedWowRecordByPid; // ebx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 result; // rax
  unsigned int v11; // r15d
  __int64 *v12; // r12
  __int64 v13; // r14
  __int64 v14; // rbx
  HANDLE v15; // rax
  _QWORD *v16; // r12
  _QWORD *v17; // rbx
  __int64 v18; // rcx
  HANDLE Handle; // [rsp+50h] [rbp+30h] BYREF
  __int64 v20; // [rsp+58h] [rbp+38h] BYREF
  __int64 v21; // [rsp+60h] [rbp+40h] BYREF

  v1 = a1[26];
  v3 = (void *)*((_QWORD *)a1 + 12);
  v20 = 0;
  v21 = 0;
  Handle = 0;
  memset_0(v3, 0, v1);
  v4 = *a1;
  if ( (_DWORD)v4 )
  {
    if ( (int)BaseSrvCheckProcessAccess(v4, 1, &Handle) >= 0 )
    {
      if ( a1[26] == 16 )
      {
        RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
        SharedWowRecordByPid = BaseSrvGetSharedWowRecordByPid(*a1, &v20);
        if ( SharedWowRecordByPid >= 0 )
        {
          v6 = *((_QWORD *)a1 + 12);
          v7 = v20;
          *(_DWORD *)v6 = *(_DWORD *)(v20 + 24);
          *(_DWORD *)(v6 + 4) = 1;
          *(_QWORD *)(v6 + 8) = *(_QWORD *)(v7 + 88);
        }
        RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
        if ( SharedWowRecordByPid < 0 )
        {
          RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
          SharedWowRecordByPid = BaseSrvGetConsoleRecordByPid(*a1, &v21);
          if ( SharedWowRecordByPid >= 0 )
          {
            v8 = *((_QWORD *)a1 + 12);
            v9 = v21;
            *(_DWORD *)v8 = *(_DWORD *)(v21 + 56);
            *(_DWORD *)(v8 + 4) = 0;
            *(_QWORD *)(v8 + 8) = *(_QWORD *)(v9 + 88);
          }
          RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
        }
      }
      else
      {
        SharedWowRecordByPid = -1073741811;
      }
    }
    else
    {
      SharedWowRecordByPid = -1073741790;
    }
    if ( Handle )
      NtClose(Handle);
    return (unsigned int)SharedWowRecordByPid;
  }
  else if ( (unsigned __int8)CsrImpersonateClient(0) )
  {
    v11 = 0;
    RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
    v12 = (__int64 *)gWowHead;
    v13 = *((_QWORD *)a1 + 12);
    if ( gWowHead )
    {
      v14 = gWowHead;
      do
      {
        if ( (int)BaseSrvCheckProcessAccess(*(unsigned int *)(v14 + 24), 0, &Handle) >= 0 )
        {
          v11 += 16;
          if ( v11 <= a1[26] )
          {
            *(_DWORD *)v13 = *(_DWORD *)(v14 + 24);
            *(_DWORD *)(v13 + 4) = 1;
            *(_QWORD *)(v13 + 8) = *(_QWORD *)(v14 + 88);
            v13 += 16;
          }
        }
        v15 = Handle;
        v14 = *v12;
        v12 = (__int64 *)*v12;
        if ( Handle )
        {
          NtClose(Handle);
          v15 = 0;
          Handle = 0;
        }
      }
      while ( v14 );
    }
    else
    {
      v15 = Handle;
    }
    v16 = DOSHead;
    if ( DOSHead )
    {
      v17 = DOSHead;
      do
      {
        v18 = v17[9];
        if ( v18 && *(_QWORD *)(v18 + 56) )
        {
          if ( (int)BaseSrvCheckProcessAccess(*((unsigned int *)v17 + 14), 0, &Handle) >= 0 )
          {
            v11 += 16;
            if ( v11 <= a1[26] )
            {
              *(_DWORD *)v13 = *((_DWORD *)v17 + 14);
              *(_DWORD *)(v13 + 4) = 0;
              *(_QWORD *)(v13 + 8) = v17[11];
              v13 += 16;
            }
          }
          v15 = Handle;
        }
        v17 = (_QWORD *)*v16;
        v16 = (_QWORD *)*v16;
        if ( v15 )
        {
          NtClose(v15);
          v15 = 0;
          Handle = 0;
        }
      }
      while ( v17 );
    }
    RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
    CsrRevertToSelf();
    result = 0;
    a1[26] = v11;
  }
  else
  {
    return 3221225637LL;
  }
  return result;
}

```

## disassembly

```asm
0x180009de8  mov     [rsp-28h+arg_18], rbx
0x180009ded  push    rbp
0x180009dee  push    rdi
0x180009def  push    r12
0x180009df1  push    r14
0x180009df3  push    r15
0x180009df5  mov     rbp, rsp
0x180009df8  sub     rsp, 20h
0x180009dfc  mov     r8d, [rcx+68h]; Size
0x180009e00  mov     rdi, rcx
0x180009e03  mov     rcx, [rcx+60h]; void *
0x180009e07  xor     edx, edx; Val
0x180009e09  mov     [rbp+arg_8], 0
0x180009e11  mov     [rbp+arg_10], 0
0x180009e19  mov     [rbp+Handle], 0
0x180009e21  call    memset_0
0x180009e26  mov     ecx, [rdi]
0x180009e28  test    ecx, ecx
0x180009e2a  jz      loc_180009F26
0x180009e30  lea     r8, [rbp+Handle]
0x180009e34  mov     edx, 1
0x180009e39  call    BaseSrvCheckProcessAccess
0x180009e3e  test    eax, eax
0x180009e40  jns     short loc_180009E4C
0x180009e42  mov     ebx, 0C0000022h
0x180009e47  jmp     loc_180009F0A
0x180009e4c  cmp     dword ptr [rdi+68h], 10h
0x180009e50  jz      short loc_180009E5C
0x180009e52  mov     ebx, 0C000000Dh
0x180009e57  jmp     loc_180009F0A
0x180009e5c  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009e63  call    cs:__imp_RtlEnterCriticalSection
0x180009e6a  nop     dword ptr [rax+rax+00h]
0x180009e6f  mov     ecx, [rdi]
0x180009e71  lea     rdx, [rbp+arg_8]
0x180009e75  call    BaseSrvGetSharedWowRecordByPid
0x180009e7a  mov     ebx, eax
0x180009e7c  test    eax, eax
0x180009e7e  js      short loc_180009E9E
0x180009e80  mov     r8, [rdi+60h]
0x180009e84  mov     rdx, [rbp+arg_8]
0x180009e88  mov     ecx, [rdx+18h]
0x180009e8b  mov     [r8], ecx
0x180009e8e  mov     dword ptr [r8+4], 1
0x180009e96  mov     rcx, [rdx+58h]
0x180009e9a  mov     [r8+8], rcx
0x180009e9e  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009ea5  call    cs:__imp_RtlLeaveCriticalSection
0x180009eac  nop     dword ptr [rax+rax+00h]
0x180009eb1  test    ebx, ebx
0x180009eb3  jns     short loc_180009F0A
0x180009eb5  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009ebc  call    cs:__imp_RtlEnterCriticalSection
0x180009ec3  nop     dword ptr [rax+rax+00h]
0x180009ec8  mov     ecx, [rdi]
0x180009eca  lea     rdx, [rbp+arg_10]
0x180009ece  call    BaseSrvGetConsoleRecordByPid
0x180009ed3  mov     ebx, eax
0x180009ed5  test    eax, eax
0x180009ed7  js      short loc_180009EF7
0x180009ed9  mov     r8, [rdi+60h]
0x180009edd  mov     rdx, [rbp+arg_10]
0x180009ee1  mov     eax, [rdx+38h]
0x180009ee4  mov     [r8], eax
0x180009ee7  mov     dword ptr [r8+4], 0
0x180009eef  mov     rax, [rdx+58h]
0x180009ef3  mov     [r8+8], rax
0x180009ef7  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009efe  call    cs:__imp_RtlLeaveCriticalSection
0x180009f05  nop     dword ptr [rax+rax+00h]
0x180009f0a  mov     rcx, [rbp+Handle]; Handle
0x180009f0e  test    rcx, rcx
0x180009f11  jz      short loc_180009F1F
0x180009f13  call    cs:__imp_NtClose
0x180009f1a  nop     dword ptr [rax+rax+00h]
0x180009f1f  mov     eax, ebx
0x180009f21  jmp     loc_18000A075
0x180009f26  xor     ecx, ecx
0x180009f28  call    cs:__imp_CsrImpersonateClient
0x180009f2f  nop     dword ptr [rax+rax+00h]
0x180009f34  test    al, al
0x180009f36  jnz     short loc_180009F42
0x180009f38  mov     eax, 0C00000A5h
0x180009f3d  jmp     loc_18000A075
0x180009f42  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009f49  xor     r15d, r15d
0x180009f4c  call    cs:__imp_RtlEnterCriticalSection
0x180009f53  nop     dword ptr [rax+rax+00h]
0x180009f58  mov     r12, cs:gWowHead
0x180009f5f  mov     r14, [rdi+60h]
0x180009f63  test    r12, r12
0x180009f66  jz      short loc_180009FCD
0x180009f68  mov     rbx, r12
0x180009f6b  mov     ecx, [rbx+18h]
0x180009f6e  lea     r8, [rbp+Handle]
0x180009f72  xor     edx, edx
0x180009f74  call    BaseSrvCheckProcessAccess
0x180009f79  test    eax, eax
0x180009f7b  js      short loc_180009FA1
0x180009f7d  add     r15d, 10h
0x180009f81  cmp     r15d, [rdi+68h]
0x180009f85  ja      short loc_180009FA1
0x180009f87  mov     eax, [rbx+18h]
0x180009f8a  mov     [r14], eax
0x180009f8d  mov     dword ptr [r14+4], 1
0x180009f95  mov     rax, [rbx+58h]
0x180009f99  mov     [r14+8], rax
0x180009f9d  add     r14, 10h
0x180009fa1  mov     rax, [rbp+Handle]
0x180009fa5  mov     rbx, [r12]
0x180009fa9  mov     r12, rbx
0x180009fac  test    rax, rax
0x180009faf  jz      short loc_180009FC6
0x180009fb1  mov     rcx, rax; Handle
0x180009fb4  call    cs:__imp_NtClose
0x180009fbb  nop     dword ptr [rax+rax+00h]
0x180009fc0  xor     eax, eax
0x180009fc2  mov     [rbp+Handle], rax
0x180009fc6  test    rbx, rbx
0x180009fc9  jnz     short loc_180009F6B
0x180009fcb  jmp     short loc_180009FD1
0x180009fcd  mov     rax, [rbp+Handle]
0x180009fd1  mov     r12, cs:DOSHead
0x180009fd8  test    r12, r12
0x180009fdb  jz      short loc_18000A050
0x180009fdd  mov     rbx, r12
0x180009fe0  mov     rcx, [rbx+48h]
0x180009fe4  test    rcx, rcx
0x180009fe7  jz      short loc_18000A02A
0x180009fe9  cmp     qword ptr [rcx+38h], 0
0x180009fee  jz      short loc_18000A02A
0x180009ff0  mov     ecx, [rbx+38h]
0x180009ff3  lea     r8, [rbp+Handle]
0x180009ff7  xor     edx, edx
0x180009ff9  call    BaseSrvCheckProcessAccess
0x180009ffe  test    eax, eax
0x18000a000  js      short loc_18000A026
0x18000a002  add     r15d, 10h
0x18000a006  cmp     r15d, [rdi+68h]
0x18000a00a  ja      short loc_18000A026
0x18000a00c  mov     eax, [rbx+38h]
0x18000a00f  mov     [r14], eax
0x18000a012  mov     dword ptr [r14+4], 0
0x18000a01a  mov     rax, [rbx+58h]
0x18000a01e  mov     [r14+8], rax
0x18000a022  add     r14, 10h
0x18000a026  mov     rax, [rbp+Handle]
0x18000a02a  mov     rbx, [r12]
0x18000a02e  mov     r12, rbx
0x18000a031  test    rax, rax
0x18000a034  jz      short loc_18000A04B
0x18000a036  mov     rcx, rax; Handle
0x18000a039  call    cs:__imp_NtClose
0x18000a040  nop     dword ptr [rax+rax+00h]
0x18000a045  xor     eax, eax
0x18000a047  mov     [rbp+Handle], rax
0x18000a04b  test    rbx, rbx
0x18000a04e  jnz     short loc_180009FE0
0x18000a050  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x18000a057  call    cs:__imp_RtlLeaveCriticalSection
0x18000a05e  nop     dword ptr [rax+rax+00h]
0x18000a063  call    cs:__imp_CsrRevertToSelf
0x18000a06a  nop     dword ptr [rax+rax+00h]
0x18000a06f  xor     eax, eax
0x18000a071  mov     [rdi+68h], r15d
0x18000a075  mov     rbx, [rsp+20h+arg_18]
0x18000a07a  add     rsp, 20h
0x18000a07e  pop     r15
0x18000a080  pop     r14
0x18000a082  pop     r12
0x18000a084  pop     rdi
0x18000a085  pop     rbp
0x18000a086  retn
```
