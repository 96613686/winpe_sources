# CEventsBase::Report(ulong,int,ushort,...)

- ea: `0x18001b4e0`
- end: `0x18001b766`
- name: `?Report@CEventsBase@@QEAAXKHGZZ`
- size: `646`
- prototype: `void(void **this, DWORD, int, WORD, ...)`
- caller_count: `15`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800049d0`
- `0x180005f2c`
- `0x180007410`
- `0x180008724`
- `0x18000ac90`
- `0x18000b7e8`
- `0x18000d11c`
- `0x18000d1f4`
- `0x18000d2d8`
- `0x18000d44c`
- `0x18000d524`
- `0x18000d5fc`
- `0x18000d6e0`
- `0x18000d734`
- `0x18001b1a0`

## callees

- `0x1800016d0`
- `0x180002024`
- `0x180012dac`
- `0x18001b1a0`
- `0x18001b4e0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b627`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b627`
- `ADVAPI32!ReportEventW` at `0x18001b61e`
- `ADVAPI32!ReportEventW` at `0x18001b61e`
- `ADVAPI32!OpenEventLogW` at `0x18001b5d2`
- `ADVAPI32!OpenEventLogW` at `0x18001b5d2`
- `ADVAPI32!CloseEventLog` at `0x18001b630`
- `ADVAPI32!CloseEventLog` at `0x18001b630`

## pseudocode

```c
void CEventsBase::Report(void **this, DWORD a2, int a3, WORD a4, ...)
{
  void *lpUserSid; // rbx
  va_list v8; // r8
  char v9; // di
  WORD v10; // r14
  unsigned int v11; // edx
  __int64 v12; // rcx
  int v13; // edx
  HANDLE v14; // r15
  LPCWSTR Strings; // [rsp+60h] [rbp-49h] BYREF
  __int64 v16; // [rsp+68h] [rbp-41h]
  __int64 v17; // [rsp+70h] [rbp-39h]
  __int64 v18; // [rsp+78h] [rbp-31h]
  __int64 v19; // [rsp+80h] [rbp-29h]
  va_list va; // [rsp+130h] [rbp+87h] BYREF

  va_start(va, a4);
  LODWORD(lpUserSid) = a4;
  memset_0(&Strings, 0, 0x50u);
  if ( (unsigned int)lpUserSid > 0xA )
    return;
  if ( a2 / 0x64 == 1 )
  {
    v10 = 1;
  }
  else
  {
    if ( a2 / 0x64 != 2 )
    {
      if ( a2 / 0x64 == 3 )
      {
        v9 = 4;
        v10 = 4;
      }
      else
      {
        if ( a2 / 0x64 != 4 )
          return;
        v9 = 4;
        v10 = 4;
      }
      goto LABEL_11;
    }
    v10 = 2;
  }
  v9 = 2;
LABEL_11:
  if ( a3 && v10 == 1 )
  {
    v10 = 2;
    v9 = 2;
  }
  if ( (_WORD)lpUserSid )
  {
    va_copy(v8, va);
    v11 = 0;
    do
    {
      v12 = v11;
      v8 += 8;
      ++v11;
      (&Strings)[v12] = (LPCWSTR)*((_QWORD *)v8 - 1);
    }
    while ( v11 < (unsigned int)lpUserSid );
  }
  if ( a2 < 0x190 || (v13 = *(_DWORD *)&gDebugLevel, (gDebugLevel & 6) != 0) )
  {
    v14 = OpenEventLogW(0, L"Application Management Group Policy");
    if ( !v14 )
      return;
    lpUserSid = AppmgmtGetUserSid(*this);
    ReportEventW(v14, v10, 0, a2, lpUserSid, a4, 0, &Strings, 0);
    LocalFree(lpUserSid);
    CloseEventLog(v14);
    v13 = *(_DWORD *)&gDebugLevel;
    LOWORD(lpUserSid) = a4;
  }
  if ( a2 != 401 )
  {
    if ( (_WORD)lpUserSid )
    {
      switch ( (unsigned __int16)lpUserSid )
      {
        case 1u:
          _DebugMsg(v9 | 8, a2, Strings);
          break;
        case 2u:
          _DebugMsg(v9 | 8, a2, Strings, v16);
          break;
        case 3u:
          _DebugMsg(v9 | 8, a2, Strings, v16, v17);
          break;
        case 4u:
          _DebugMsg(v9 | 8, a2, Strings, v16, v17, v18);
          break;
        case 5u:
          _DebugMsg(v9 | 8, a2, Strings, v16, v17, v18, v19);
          break;
        default:
          if ( v13 )
            _DebugMsg(12, 0xBB8u, L"CEvents::Report called with more params then expected!\n");
          break;
      }
    }
    else
    {
      _DebugMsg(v9 | 8, a2, v8);
    }
  }
}

```

## disassembly

```asm
0x18001b4e0  mov     [rsp-8+arg_18], r9w
0x18001b4e6  push    rbp
0x18001b4e7  push    rbx
0x18001b4e8  push    rsi
0x18001b4e9  push    rdi
0x18001b4ea  push    r12
0x18001b4ec  push    r13
0x18001b4ee  push    r14
0x18001b4f0  push    r15
0x18001b4f2  lea     rbp, [rsp-1Fh]
0x18001b4f7  sub     rsp, 0C8h
0x18001b4fe  mov     rax, cs:__security_cookie
0x18001b505  xor     rax, rsp
0x18001b508  mov     [rbp+57h+var_50], rax
0x18001b50c  mov     r15d, r8d
0x18001b50f  movzx   ebx, r9w
0x18001b513  mov     esi, edx
0x18001b515  mov     r12, rcx
0x18001b518  xor     r13d, r13d
0x18001b51b  lea     rcx, [rbp+57h+Strings]; void *
0x18001b51f  xor     edx, edx; Val
0x18001b521  lea     r8d, [r13+50h]; Size
0x18001b525  call    memset_0
0x18001b52a  cmp     ebx, 0Ah
0x18001b52d  ja      loc_18001B746
0x18001b533  mov     eax, 51EB851Fh
0x18001b538  lea     r10d, [r13+1]
0x18001b53c  mul     esi
0x18001b53e  lea     eax, [r13+2]
0x18001b542  shr     edx, 5
0x18001b545  sub     edx, r10d
0x18001b548  jz      short loc_18001B576
0x18001b54a  sub     edx, r10d
0x18001b54d  jz      short loc_18001B570
0x18001b54f  sub     edx, r10d
0x18001b552  jz      short loc_18001B566
0x18001b554  cmp     edx, r10d
0x18001b557  jnz     loc_18001B746
0x18001b55d  lea     edi, [rax+2]
0x18001b560  movzx   r14d, di
0x18001b564  jmp     short loc_18001B57C
0x18001b566  mov     edi, 4
0x18001b56b  mov     r14d, edi
0x18001b56e  jmp     short loc_18001B57C
0x18001b570  movzx   r14d, ax
0x18001b574  jmp     short loc_18001B57A
0x18001b576  movzx   r14d, r10w
0x18001b57a  mov     edi, eax
0x18001b57c  test    r15d, r15d
0x18001b57f  jz      short loc_18001B58D
0x18001b581  cmp     r10w, r14w
0x18001b585  jnz     short loc_18001B58D
0x18001b587  movzx   r14d, ax
0x18001b58b  mov     edi, eax
0x18001b58d  test    bx, bx
0x18001b590  jz      short loc_18001B5B6
0x18001b592  lea     r8, [rbp+57h+arg_20]
0x18001b599  mov     edx, r13d
0x18001b59c  test    ebx, ebx
0x18001b59e  jz      short loc_18001B5B6
0x18001b5a0  mov     ecx, edx
0x18001b5a2  lea     r8, [r8+8]
0x18001b5a6  mov     rax, [r8-8]
0x18001b5aa  add     edx, r10d
0x18001b5ad  mov     [rbp+rcx*8+57h+Strings], rax
0x18001b5b2  cmp     edx, ebx
0x18001b5b4  jb      short loc_18001B5A0
0x18001b5b6  cmp     esi, 190h
0x18001b5bc  jb      short loc_18001B5C9
0x18001b5be  mov     edx, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x18001b5c4  test    dl, 6
0x18001b5c7  jz      short loc_18001B640
0x18001b5c9  lea     rdx, SourceName; "Application Management Group Policy"
0x18001b5d0  xor     ecx, ecx; lpUNCServerName
0x18001b5d2  call    cs:__imp_OpenEventLogW
0x18001b5d8  mov     r15, rax
0x18001b5db  test    rax, rax
0x18001b5de  jz      loc_18001B746
0x18001b5e4  mov     rcx, [r12]; void *
0x18001b5e8  call    ?AppmgmtGetUserSid@@YAPEAXPEAX@Z; AppmgmtGetUserSid(void *)
0x18001b5ed  movzx   ecx, [rbp+57h+arg_18]
0x18001b5f1  mov     rbx, rax
0x18001b5f4  mov     [rsp+100h+lpRawData], r13; lpRawData
0x18001b5f9  lea     rax, [rbp+57h+Strings]
0x18001b5fd  mov     [rsp+100h+lpStrings], rax; lpStrings
0x18001b602  xor     r8d, r8d; wCategory
0x18001b605  mov     [rsp+100h+dwDataSize], r13d; dwDataSize
0x18001b60a  mov     r9d, esi; dwEventID
0x18001b60d  mov     [rsp+100h+wNumStrings], cx; wNumStrings
0x18001b612  movzx   edx, r14w; wType
0x18001b616  mov     rcx, r15; hEventLog
0x18001b619  mov     [rsp+100h+lpUserSid], rbx; lpUserSid
0x18001b61e  call    cs:__imp_ReportEventW
0x18001b624  mov     rcx, rbx; hMem
0x18001b627  call    cs:__imp_LocalFree
0x18001b62d  mov     rcx, r15; hEventLog
0x18001b630  call    cs:__imp_CloseEventLog
0x18001b636  mov     edx, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x18001b63c  movzx   ebx, [rbp+57h+arg_18]
0x18001b640  cmp     esi, 191h
0x18001b646  jz      loc_18001B746
0x18001b64c  movzx   ecx, bx
0x18001b64f  test    ecx, ecx
0x18001b651  jz      loc_18001B73A
0x18001b657  sub     ecx, 1
0x18001b65a  jz      loc_18001B728
0x18001b660  sub     ecx, 1
0x18001b663  jz      loc_18001B712
0x18001b669  sub     ecx, 1
0x18001b66c  jz      loc_18001B6F3
0x18001b672  sub     ecx, 1
0x18001b675  jz      short loc_18001B6CB
0x18001b677  cmp     ecx, 1
0x18001b67a  jz      short loc_18001B69A
0x18001b67c  test    edx, edx
0x18001b67e  jz      loc_18001B746
0x18001b684  lea     r8, aCeventsReportC; "CEvents::Report called with more params"...
0x18001b68b  mov     edx, 0BB8h
0x18001b690  mov     ecx, 0Ch
0x18001b695  jmp     loc_18001B733
0x18001b69a  mov     rax, [rbp+57h+var_80]
0x18001b69e  or      edi, 8
0x18001b6a1  mov     r9, [rbp+57h+var_98]
0x18001b6a5  mov     edx, esi; unsigned int
0x18001b6a7  mov     r8, [rbp+57h+Strings]
0x18001b6ab  mov     ecx, edi; unsigned int
0x18001b6ad  mov     qword ptr [rsp+100h+dwDataSize], rax
0x18001b6b2  mov     rax, [rbp+57h+var_88]
0x18001b6b6  mov     qword ptr [rsp+100h+wNumStrings], rax
0x18001b6bb  mov     rax, [rbp+57h+var_90]
0x18001b6bf  mov     [rsp+100h+lpUserSid], rax
0x18001b6c4  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001b6c9  jmp     short loc_18001B746
0x18001b6cb  mov     rax, [rbp+57h+var_88]
0x18001b6cf  or      edi, 8
0x18001b6d2  mov     r9, [rbp+57h+var_98]
0x18001b6d6  mov     edx, esi; unsigned int
0x18001b6d8  mov     r8, [rbp+57h+Strings]
0x18001b6dc  mov     ecx, edi; unsigned int
0x18001b6de  mov     qword ptr [rsp+100h+wNumStrings], rax
0x18001b6e3  mov     rax, [rbp+57h+var_90]
0x18001b6e7  mov     [rsp+100h+lpUserSid], rax
0x18001b6ec  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001b6f1  jmp     short loc_18001B746
0x18001b6f3  mov     rax, [rbp+57h+var_90]
0x18001b6f7  or      edi, 8
0x18001b6fa  mov     r9, [rbp+57h+var_98]
0x18001b6fe  mov     ecx, edi; unsigned int
0x18001b700  mov     r8, [rbp+57h+Strings]
0x18001b704  mov     edx, esi; unsigned int
0x18001b706  mov     [rsp+100h+lpUserSid], rax
0x18001b70b  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001b710  jmp     short loc_18001B746
0x18001b712  mov     r9, [rbp+57h+var_98]
0x18001b716  or      edi, 8
0x18001b719  mov     r8, [rbp+57h+Strings]
0x18001b71d  mov     ecx, edi; unsigned int
0x18001b71f  mov     edx, esi; unsigned int
0x18001b721  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001b726  jmp     short loc_18001B746
0x18001b728  mov     r8, [rbp+57h+Strings]
0x18001b72c  or      edi, 8
0x18001b72f  mov     ecx, edi; unsigned int
0x18001b731  mov     edx, esi; unsigned int
0x18001b733  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001b738  jmp     short loc_18001B746
0x18001b73a  or      edi, 8
0x18001b73d  mov     edx, esi; unsigned int
0x18001b73f  mov     ecx, edi; unsigned int
0x18001b741  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x18001b746  mov     rcx, [rbp+57h+var_50]
0x18001b74a  xor     rcx, rsp; StackCookie
0x18001b74d  call    __security_check_cookie
0x18001b752  add     rsp, 0C8h
0x18001b759  pop     r15
0x18001b75b  pop     r14
0x18001b75d  pop     r13
0x18001b75f  pop     r12
0x18001b761  pop     rdi
0x18001b762  pop     rsi
0x18001b763  pop     rbx
0x18001b764  pop     rbp
0x18001b765  retn
```
