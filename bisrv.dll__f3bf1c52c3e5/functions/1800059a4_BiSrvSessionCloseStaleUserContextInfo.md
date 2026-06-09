# BiSrvSessionCloseStaleUserContextInfo

- ea: `0x1800059a4`
- end: `0x180005b80`
- name: `BiSrvSessionCloseStaleUserContextInfo`
- size: `476`
- prototype: `char __fastcall(ULONG SessionId)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004dd70`

## callees

- `0x1800059a4`
- `0x180006300`
- `0x1800066cc`
- `0x180006aa0`
- `0x180006dc0`
- `0x180007014`
- `0x1800121b0`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180005af0`
- `ntdll!RtlReleaseSRWLockShared` at `0x180005af0`
- `ntdll!RtlValidSid` at `0x180005a3f`
- `ntdll!RtlValidSid` at `0x180005a3f`
- `ntdll!RtlCopySid` at `0x180005a6a`
- `ntdll!RtlCopySid` at `0x180005ab9`
- `ntdll!RtlCopySid` at `0x180005ad4`
- `ntdll!RtlCopySid` at `0x180005a6a`
- `ntdll!RtlCopySid` at `0x180005ab9`
- `ntdll!RtlCopySid` at `0x180005ad4`

## pseudocode

```c
char __fastcall BiSrvSessionCloseStaleUserContextInfo(ULONG SessionId)
{
  char v2; // si
  __int64 v3; // rdi
  __int64 v4; // r15
  _QWORD *ThreadLocalStoragePointer; // r12
  __int64 i; // rbx
  __int64 FirstUserContextInfo; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  int v10; // ebx
  _BYTE Sid[80]; // [rsp+30h] [rbp-99h] BYREF
  _BYTE DestinationSid[80]; // [rsp+80h] [rbp-49h] BYREF

  memset_0(DestinationSid, 0, 0x44u);
  v2 = 0;
  v3 = 0;
  memset_0(Sid, 0, 0x44u);
  v4 = (unsigned int)tls_index;
  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
LABEL_2:
  if ( !v2 )
  {
LABEL_18:
    v2 = 1;
    BipSyncAcquireLock((struct _BI_LOCK *)BipSessionLock);
  }
  for ( i = qword_1800C4400; (__int64 *)i != &qword_1800C4400; i = *(_QWORD *)i )
  {
    if ( *(_DWORD *)(i + 56) == SessionId )
    {
      if ( RtlValidSid(Sid) )
      {
        if ( !v3 )
          return BipSyncReleaseLock(BipSessionLock, 0);
      }
      else
      {
        FirstUserContextInfo = BipSessionGetFirstUserContextInfo(i);
        if ( !FirstUserContextInfo )
          return BipSyncReleaseLock(BipSessionLock, 0);
        RtlCopySid(0x44u, Sid, (PSID)(*(_QWORD *)(FirstUserContextInfo + 72) + 36LL));
      }
      v8 = BipUserContextInfoFind(SessionId, Sid);
      v3 = v8;
      if ( !v8 )
      {
        memset_0(Sid, 0, 0x44u);
        goto LABEL_2;
      }
      v9 = *(_QWORD *)(v8 + 32);
      v3 = 0;
      if ( v9 != *(_QWORD *)(v8 + 48) + 16LL )
        v3 = v9 - 32;
      RtlCopySid(0x44u, DestinationSid, Sid);
      if ( v3 )
        RtlCopySid(0x44u, Sid, (PSID)(*(_QWORD *)(v3 + 72) + 36LL));
      v10 = ~(1 << dword_1800C46D8);
      RtlReleaseSRWLockShared(BipSessionLock);
      *(_DWORD *)(ThreadLocalStoragePointer[v4] + 4LL) &= v10;
      if ( (int)BipSystemUserQueryUserContextToken(SessionId, DestinationSid) < 0 )
        BipUserContextInfoDestroy(SessionId, DestinationSid);
      goto LABEL_18;
    }
  }
  return BipSyncReleaseLock(BipSessionLock, 0);
}

```

## disassembly

```asm
0x1800059a4  push    rbp
0x1800059a6  push    rbx
0x1800059a7  push    rsi
0x1800059a8  push    rdi
0x1800059a9  push    r12
0x1800059ab  push    r13
0x1800059ad  push    r14
0x1800059af  push    r15
0x1800059b1  lea     rbp, [rsp-1Fh]
0x1800059b6  sub     rsp, 0E8h
0x1800059bd  mov     rax, cs:__security_cookie
0x1800059c4  xor     rax, rsp
0x1800059c7  mov     [rbp+57h+var_50], rax
0x1800059cb  mov     r14d, ecx
0x1800059ce  mov     r13d, 44h ; 'D'
0x1800059d4  mov     r8d, r13d; Size
0x1800059d7  lea     rcx, [rbp+57h+DestinationSid]; void *
0x1800059db  xor     edx, edx; Val
0x1800059dd  call    memset_0
0x1800059e2  mov     r8d, r13d; Size
0x1800059e5  mov     [rsp+120h+var_100], 0
0x1800059ee  xor     edx, edx; Val
0x1800059f0  lea     rcx, [rsp+120h+Sid]; void *
0x1800059f5  xor     sil, sil
0x1800059f8  xor     edi, edi
0x1800059fa  call    memset_0
0x1800059ff  mov     r15d, cs:_tls_index
0x180005a06  mov     r12, gs:58h
0x180005a0f  test    sil, sil
0x180005a12  jz      loc_180005B23
0x180005a18  mov     rbx, cs:qword_1800C4400
0x180005a1f  lea     rax, qword_1800C4400
0x180005a26  cmp     rbx, rax
0x180005a29  jz      loc_180005B4D
0x180005a2f  cmp     [rbx+38h], r14d
0x180005a33  jz      short loc_180005A3A
0x180005a35  mov     rbx, [rbx]
0x180005a38  jmp     short loc_180005A1F
0x180005a3a  lea     rcx, [rsp+120h+Sid]; Sid
0x180005a3f  call    cs:__imp_RtlValidSid
0x180005a45  test    al, al
0x180005a47  jnz     short loc_180005A72
0x180005a49  mov     rcx, rbx
0x180005a4c  call    BipSessionGetFirstUserContextInfo
0x180005a51  test    rax, rax
0x180005a54  jz      loc_180005B4D
0x180005a5a  mov     r8, [rax+48h]
0x180005a5e  lea     rdx, [rsp+120h+Sid]; DestinationSid
0x180005a63  add     r8, 24h ; '$'; SourceSid
0x180005a67  mov     ecx, r13d; DestinationSidLength
0x180005a6a  call    cs:__imp_RtlCopySid
0x180005a70  jmp     short loc_180005A7B
0x180005a72  test    rdi, rdi
0x180005a75  jz      loc_180005B4D
0x180005a7b  lea     rdx, [rsp+120h+Sid]
0x180005a80  mov     ecx, r14d
0x180005a83  call    BipUserContextInfoFind
0x180005a88  mov     rdi, rax
0x180005a8b  test    rax, rax
0x180005a8e  jz      loc_180005B39
0x180005a94  mov     rdx, [rax+20h]
0x180005a98  lea     r8, [rsp+120h+Sid]; SourceSid
0x180005a9d  mov     rcx, [rax+30h]
0x180005aa1  xor     edi, edi
0x180005aa3  add     rcx, 10h
0x180005aa7  cmp     rdx, rcx
0x180005aaa  mov     ecx, r13d; DestinationSidLength
0x180005aad  lea     rax, [rdx-20h]
0x180005ab1  lea     rdx, [rbp+57h+DestinationSid]; DestinationSid
0x180005ab5  cmovnz  rdi, rax
0x180005ab9  call    cs:__imp_RtlCopySid
0x180005abf  test    rdi, rdi
0x180005ac2  jz      short loc_180005ADA
0x180005ac4  mov     r8, [rdi+48h]
0x180005ac8  lea     rdx, [rsp+120h+Sid]; DestinationSid
0x180005acd  add     r8, 24h ; '$'; SourceSid
0x180005ad1  mov     ecx, r13d; DestinationSidLength
0x180005ad4  call    cs:__imp_RtlCopySid
0x180005ada  mov     ecx, cs:dword_1800C46D8
0x180005ae0  mov     ebx, 1
0x180005ae5  shl     ebx, cl
0x180005ae7  lea     rcx, BipSessionLock
0x180005aee  not     ebx
0x180005af0  call    cs:__imp_RtlReleaseSRWLockShared
0x180005af6  mov     rax, [r12+r15*8]
0x180005afa  lea     r8, [rsp+120h+var_100]
0x180005aff  mov     ecx, 4
0x180005b04  lea     rdx, [rbp+57h+DestinationSid]; Sid1
0x180005b08  and     [rcx+rax], ebx
0x180005b0b  mov     ecx, r14d; SessionId
0x180005b0e  call    BipSystemUserQueryUserContextToken
0x180005b13  test    eax, eax
0x180005b15  jns     short loc_180005B23
0x180005b17  lea     rdx, [rbp+57h+DestinationSid]
0x180005b1b  mov     ecx, r14d
0x180005b1e  call    BipUserContextInfoDestroy
0x180005b23  xor     edx, edx
0x180005b25  lea     rcx, BipSessionLock; struct _BI_LOCK *
0x180005b2c  mov     sil, 1
0x180005b2f  call    BipSyncAcquireLock
0x180005b34  jmp     loc_180005A18
0x180005b39  mov     r8, r13; Size
0x180005b3c  lea     rcx, [rsp+120h+Sid]; void *
0x180005b41  xor     edx, edx; Val
0x180005b43  call    memset_0
0x180005b48  jmp     loc_180005A0F
0x180005b4d  test    sil, sil
0x180005b50  jz      short loc_180005B60
0x180005b52  xor     edx, edx
0x180005b54  lea     rcx, BipSessionLock
0x180005b5b  call    BipSyncReleaseLock
0x180005b60  mov     rcx, [rbp+57h+var_50]
0x180005b64  xor     rcx, rsp; StackCookie
0x180005b67  call    __security_check_cookie
0x180005b6c  add     rsp, 0E8h
0x180005b73  pop     r15
0x180005b75  pop     r14
0x180005b77  pop     r13
0x180005b79  pop     r12
0x180005b7b  pop     rdi
0x180005b7c  pop     rsi
0x180005b7d  pop     rbx
0x180005b7e  pop     rbp
0x180005b7f  retn
```
