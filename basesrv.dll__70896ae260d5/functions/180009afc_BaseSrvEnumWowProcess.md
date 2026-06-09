# BaseSrvEnumWowProcess

- ea: `0x180009afc`
- end: `0x180009d9c`
- name: `BaseSrvEnumWowProcess`
- size: `672`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a960`

## callees

- `0x180008ab0`
- `0x180009afc`
- `0x18000a92c`
- `0x18000b160`
- `0x18000d713`

## import_xrefs

- `ntdll!NtClose` at `0x180009c1a`
- `ntdll!NtClose` at `0x180009cbd`
- `ntdll!NtClose` at `0x180009d4c`
- `ntdll!NtClose` at `0x180009c1a`
- `ntdll!NtClose` at `0x180009cbd`
- `ntdll!NtClose` at `0x180009d4c`
- `ntdll!RtlEnterCriticalSection` at `0x180009b6e`
- `ntdll!RtlEnterCriticalSection` at `0x180009bc7`
- `ntdll!RtlEnterCriticalSection` at `0x180009c50`
- `ntdll!RtlEnterCriticalSection` at `0x180009b6e`
- `ntdll!RtlEnterCriticalSection` at `0x180009bc7`
- `ntdll!RtlEnterCriticalSection` at `0x180009c50`
- `ntdll!RtlLeaveCriticalSection` at `0x180009bb0`
- `ntdll!RtlLeaveCriticalSection` at `0x180009c05`
- `ntdll!RtlLeaveCriticalSection` at `0x180009d6d`
- `ntdll!RtlLeaveCriticalSection` at `0x180009bb0`
- `ntdll!RtlLeaveCriticalSection` at `0x180009c05`
- `ntdll!RtlLeaveCriticalSection` at `0x180009d6d`
- `CSRSRV!CsrRevertToSelf` at `0x180009d79`
- `CSRSRV!CsrRevertToSelf` at `0x180009d79`
- `CSRSRV!CsrImpersonateClient` at `0x180009c2f`
- `CSRSRV!CsrImpersonateClient` at `0x180009c2f`

## pseudocode

```c
__int64 __fastcall BaseSrvEnumWowProcess(unsigned int *a1)
{
  size_t v1; // r8
  void *v3; // rcx
  unsigned int v4; // r14d
  __int64 v5; // rcx
  int SharedWowRecordByPid; // ebx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  int v11; // eax
  __int64 result; // rax
  _QWORD *v13; // rbx
  __int64 v14; // r15
  __int64 v15; // r13
  __int64 v16; // r12
  HANDLE v17; // rax
  _QWORD *v18; // rbx
  _QWORD *v19; // r15
  _QWORD *v20; // r13
  _DWORD *v21; // r12
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  HANDLE Handle; // [rsp+60h] [rbp+40h] BYREF
  __int64 v26; // [rsp+68h] [rbp+48h] BYREF
  __int64 v27; // [rsp+70h] [rbp+50h] BYREF

  v1 = a1[26];
  v3 = (void *)*((_QWORD *)a1 + 12);
  v4 = 0;
  Handle = 0;
  v26 = 0;
  v27 = 0;
  memset_0(v3, 0, v1);
  v5 = *a1;
  if ( (_DWORD)v5 )
  {
    if ( (int)BaseSrvCheckProcessAccess(v5, 1, &Handle) >= 0 )
    {
      if ( a1[26] == 16 )
      {
        RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
        SharedWowRecordByPid = BaseSrvGetSharedWowRecordByPid(*a1, &v26);
        if ( SharedWowRecordByPid >= 0 )
        {
          v7 = *((_QWORD *)a1 + 12);
          v8 = v26;
          *(_DWORD *)v7 = *(_DWORD *)(v26 + 24);
          *(_DWORD *)(v7 + 4) = 1;
          *(_QWORD *)(v7 + 8) = *(_QWORD *)(v8 + 88);
        }
        RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
        if ( SharedWowRecordByPid < 0 )
        {
          RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
          SharedWowRecordByPid = BaseSrvGetConsoleRecordByPid(*a1, &v27);
          if ( SharedWowRecordByPid >= 0 )
          {
            v9 = *((_QWORD *)a1 + 12);
            v10 = v27;
            v11 = *(_DWORD *)(v27 + 56);
            *(_DWORD *)(v9 + 4) = 0;
            *(_DWORD *)v9 = v11;
            *(_QWORD *)(v9 + 8) = *(_QWORD *)(v10 + 88);
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
    RtlEnterCriticalSection(&BaseSrvVDMCriticalSection);
    v13 = (_QWORD *)gWowHead;
    v14 = *((_QWORD *)a1 + 12);
    if ( gWowHead )
    {
      v15 = gWowHead;
      v16 = gWowHead;
      do
      {
        if ( (int)BaseSrvCheckProcessAccess(*(unsigned int *)(v15 + 24), 0, &Handle) >= 0 )
        {
          v4 += 16;
          if ( v4 <= a1[26] )
          {
            *(_DWORD *)v14 = *(_DWORD *)(v15 + 24);
            *(_DWORD *)(v14 + 4) = 1;
            *(_QWORD *)(v14 + 8) = *(_QWORD *)(v16 + 88);
            v14 += 16;
          }
        }
        v17 = Handle;
        v13 = (_QWORD *)*v13;
        v15 = (__int64)v13;
        if ( Handle )
        {
          NtClose(Handle);
          v17 = 0;
          Handle = 0;
        }
        v16 = (__int64)v13;
      }
      while ( v13 );
    }
    else
    {
      v17 = Handle;
    }
    v18 = DOSHead;
    if ( DOSHead )
    {
      v19 = (_QWORD *)(v14 + 8);
      v20 = DOSHead;
      v21 = DOSHead;
      do
      {
        v22 = v20[9];
        if ( v22 && *(_QWORD *)(v22 + 56) )
        {
          if ( (int)BaseSrvCheckProcessAccess((unsigned int)v21[14], 0, &Handle) >= 0 )
          {
            v4 += 16;
            if ( v4 <= a1[26] )
            {
              v23 = v21[14];
              *((_DWORD *)v19 - 1) = 0;
              *((_DWORD *)v19 - 2) = v23;
              *v19 = v18[11];
              v19 += 2;
            }
          }
          v17 = Handle;
        }
        v18 = (_QWORD *)*v18;
        v20 = v18;
        if ( v17 )
        {
          NtClose(v17);
          v17 = 0;
          Handle = 0;
        }
        v21 = v18;
      }
      while ( v18 );
    }
    RtlLeaveCriticalSection(&BaseSrvVDMCriticalSection);
    CsrRevertToSelf(v24);
    result = 0;
    a1[26] = v4;
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
0x180009afc  push    rbp
0x180009afe  push    rbx
0x180009aff  push    rdi
0x180009b00  push    r12
0x180009b02  push    r13
0x180009b04  push    r14
0x180009b06  push    r15
0x180009b08  mov     rbp, rsp
0x180009b0b  sub     rsp, 20h
0x180009b0f  mov     r8d, [rcx+68h]; Size
0x180009b13  mov     rdi, rcx
0x180009b16  mov     rcx, [rcx+60h]; void *
0x180009b1a  xor     r14d, r14d
0x180009b1d  and     [rbp+Handle], r14
0x180009b21  xor     edx, edx; Val
0x180009b23  and     [rbp+arg_8], 0
0x180009b28  and     [rbp+arg_10], 0
0x180009b2d  call    memset_0
0x180009b32  mov     ecx, [rdi]
0x180009b34  test    ecx, ecx
0x180009b36  jz      loc_180009C2D
0x180009b3c  lea     r8, [rbp+Handle]
0x180009b40  lea     edx, [r14+1]
0x180009b44  call    BaseSrvCheckProcessAccess
0x180009b49  test    eax, eax
0x180009b4b  jns     short loc_180009B57
0x180009b4d  mov     ebx, 0C0000022h
0x180009b52  jmp     loc_180009C11
0x180009b57  cmp     dword ptr [rdi+68h], 10h
0x180009b5b  jz      short loc_180009B67
0x180009b5d  mov     ebx, 0C000000Dh
0x180009b62  jmp     loc_180009C11
0x180009b67  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009b6e  call    cs:__imp_RtlEnterCriticalSection
0x180009b75  nop     dword ptr [rax+rax+00h]
0x180009b7a  mov     ecx, [rdi]
0x180009b7c  lea     rdx, [rbp+arg_8]
0x180009b80  call    BaseSrvGetSharedWowRecordByPid
0x180009b85  mov     ebx, eax
0x180009b87  test    eax, eax
0x180009b89  js      short loc_180009BA9
0x180009b8b  mov     r8, [rdi+60h]
0x180009b8f  mov     rdx, [rbp+arg_8]
0x180009b93  mov     ecx, [rdx+18h]
0x180009b96  mov     [r8], ecx
0x180009b99  mov     dword ptr [r8+4], 1
0x180009ba1  mov     rcx, [rdx+58h]
0x180009ba5  mov     [r8+8], rcx
0x180009ba9  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009bb0  call    cs:__imp_RtlLeaveCriticalSection
0x180009bb7  nop     dword ptr [rax+rax+00h]
0x180009bbc  test    ebx, ebx
0x180009bbe  jns     short loc_180009C11
0x180009bc0  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009bc7  call    cs:__imp_RtlEnterCriticalSection
0x180009bce  nop     dword ptr [rax+rax+00h]
0x180009bd3  mov     ecx, [rdi]
0x180009bd5  lea     rdx, [rbp+arg_10]
0x180009bd9  call    BaseSrvGetConsoleRecordByPid
0x180009bde  mov     ebx, eax
0x180009be0  test    eax, eax
0x180009be2  js      short loc_180009BFE
0x180009be4  mov     r8, [rdi+60h]
0x180009be8  mov     rdx, [rbp+arg_10]
0x180009bec  mov     eax, [rdx+38h]
0x180009bef  and     [r8+4], r14d
0x180009bf3  mov     [r8], eax
0x180009bf6  mov     rax, [rdx+58h]
0x180009bfa  mov     [r8+8], rax
0x180009bfe  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009c05  call    cs:__imp_RtlLeaveCriticalSection
0x180009c0c  nop     dword ptr [rax+rax+00h]
0x180009c11  mov     rcx, [rbp+Handle]; Handle
0x180009c15  test    rcx, rcx
0x180009c18  jz      short loc_180009C26
0x180009c1a  call    cs:__imp_NtClose
0x180009c21  nop     dword ptr [rax+rax+00h]
0x180009c26  mov     eax, ebx
0x180009c28  jmp     loc_180009D8B
0x180009c2d  xor     ecx, ecx
0x180009c2f  call    cs:__imp_CsrImpersonateClient
0x180009c36  nop     dword ptr [rax+rax+00h]
0x180009c3b  test    al, al
0x180009c3d  jnz     short loc_180009C49
0x180009c3f  mov     eax, 0C00000A5h
0x180009c44  jmp     loc_180009D8B
0x180009c49  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009c50  call    cs:__imp_RtlEnterCriticalSection
0x180009c57  nop     dword ptr [rax+rax+00h]
0x180009c5c  mov     rbx, cs:gWowHead
0x180009c63  mov     r15, [rdi+60h]
0x180009c67  test    rbx, rbx
0x180009c6a  jz      short loc_180009CD9
0x180009c6c  mov     r13, rbx
0x180009c6f  mov     r12, rbx
0x180009c72  mov     ecx, [r13+18h]
0x180009c76  lea     r8, [rbp+Handle]
0x180009c7a  xor     edx, edx
0x180009c7c  call    BaseSrvCheckProcessAccess
0x180009c81  test    eax, eax
0x180009c83  js      short loc_180009CAB
0x180009c85  add     r14d, 10h
0x180009c89  cmp     r14d, [rdi+68h]
0x180009c8d  ja      short loc_180009CAB
0x180009c8f  mov     eax, [r13+18h]
0x180009c93  mov     [r15], eax
0x180009c96  mov     dword ptr [r15+4], 1
0x180009c9e  mov     rax, [r12+58h]
0x180009ca3  mov     [r15+8], rax
0x180009ca7  add     r15, 10h
0x180009cab  mov     rax, [rbp+Handle]
0x180009caf  mov     rbx, [rbx]
0x180009cb2  mov     r13, rbx
0x180009cb5  test    rax, rax
0x180009cb8  jz      short loc_180009CCF
0x180009cba  mov     rcx, rax; Handle
0x180009cbd  call    cs:__imp_NtClose
0x180009cc4  nop     dword ptr [rax+rax+00h]
0x180009cc9  xor     eax, eax
0x180009ccb  mov     [rbp+Handle], rax
0x180009ccf  mov     r12, rbx
0x180009cd2  test    rbx, rbx
0x180009cd5  jnz     short loc_180009C72
0x180009cd7  jmp     short loc_180009CDD
0x180009cd9  mov     rax, [rbp+Handle]
0x180009cdd  mov     rbx, cs:DOSHead
0x180009ce4  test    rbx, rbx
0x180009ce7  jz      short loc_180009D66
0x180009ce9  add     r15, 8
0x180009ced  mov     r13, rbx
0x180009cf0  mov     r12, rbx
0x180009cf3  mov     rcx, [r13+48h]
0x180009cf7  test    rcx, rcx
0x180009cfa  jz      short loc_180009D3E
0x180009cfc  cmp     qword ptr [rcx+38h], 0
0x180009d01  jz      short loc_180009D3E
0x180009d03  mov     ecx, [r12+38h]
0x180009d08  lea     r8, [rbp+Handle]
0x180009d0c  xor     edx, edx
0x180009d0e  call    BaseSrvCheckProcessAccess
0x180009d13  test    eax, eax
0x180009d15  js      short loc_180009D3A
0x180009d17  add     r14d, 10h
0x180009d1b  cmp     r14d, [rdi+68h]
0x180009d1f  ja      short loc_180009D3A
0x180009d21  mov     eax, [r12+38h]
0x180009d26  and     dword ptr [r15-4], 0
0x180009d2b  mov     [r15-8], eax
0x180009d2f  mov     rax, [rbx+58h]
0x180009d33  mov     [r15], rax
0x180009d36  add     r15, 10h
0x180009d3a  mov     rax, [rbp+Handle]
0x180009d3e  mov     rbx, [rbx]
0x180009d41  mov     r13, rbx
0x180009d44  test    rax, rax
0x180009d47  jz      short loc_180009D5E
0x180009d49  mov     rcx, rax; Handle
0x180009d4c  call    cs:__imp_NtClose
0x180009d53  nop     dword ptr [rax+rax+00h]
0x180009d58  xor     eax, eax
0x180009d5a  mov     [rbp+Handle], rax
0x180009d5e  mov     r12, rbx
0x180009d61  test    rbx, rbx
0x180009d64  jnz     short loc_180009CF3
0x180009d66  lea     rcx, BaseSrvVDMCriticalSection; CriticalSection
0x180009d6d  call    cs:__imp_RtlLeaveCriticalSection
0x180009d74  nop     dword ptr [rax+rax+00h]
0x180009d79  call    cs:__imp_CsrRevertToSelf
0x180009d80  nop     dword ptr [rax+rax+00h]
0x180009d85  xor     eax, eax
0x180009d87  mov     [rdi+68h], r14d
0x180009d8b  add     rsp, 20h
0x180009d8f  pop     r15
0x180009d91  pop     r14
0x180009d93  pop     r13
0x180009d95  pop     r12
0x180009d97  pop     rdi
0x180009d98  pop     rbx
0x180009d99  pop     rbp
0x180009d9a  retn
```
