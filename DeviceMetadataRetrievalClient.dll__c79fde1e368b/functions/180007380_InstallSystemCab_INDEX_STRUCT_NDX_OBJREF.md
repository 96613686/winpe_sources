# InstallSystemCab(_INDEX_STRUCT *,NDX_OBJREF *)

- ea: `0x180007380`
- end: `0x180007684`
- name: `?InstallSystemCab@@YAKPEAU_INDEX_STRUCT@@PEAUNDX_OBJREF@@@Z`
- size: `772`
- prototype: `__int64 __fastcall(struct _INDEX_STRUCT *, struct NDX_OBJREF *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180012650`

## callees

- `0x1800030c4`
- `0x180003514`
- `0x180004d70`
- `0x180004e2c`
- `0x180007380`
- `0x180007ea0`
- `0x180007f3c`
- `0x18000c398`
- `0x18000ede8`
- `0x1800135cc`
- `0x180013700`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800075fc`
- `KERNEL32!GetProcessHeap` at `0x180007615`
- `KERNEL32!GetProcessHeap` at `0x18000762e`
- `KERNEL32!GetProcessHeap` at `0x180007647`
- `KERNEL32!GetProcessHeap` at `0x1800075fc`
- `KERNEL32!GetProcessHeap` at `0x180007615`
- `KERNEL32!GetProcessHeap` at `0x18000762e`
- `KERNEL32!GetProcessHeap` at `0x180007647`
- `KERNEL32!HeapFree` at `0x18000760a`
- `KERNEL32!HeapFree` at `0x180007623`
- `KERNEL32!HeapFree` at `0x18000763c`
- `KERNEL32!HeapFree` at `0x180007655`
- `KERNEL32!HeapFree` at `0x18000760a`
- `KERNEL32!HeapFree` at `0x180007623`
- `KERNEL32!HeapFree` at `0x18000763c`
- `KERNEL32!HeapFree` at `0x180007655`
- `KERNEL32!GetLastError` at `0x180007584`
- `KERNEL32!GetLastError` at `0x1800075a6`
- `KERNEL32!GetLastError` at `0x180007584`
- `KERNEL32!GetLastError` at `0x1800075a6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800073e7`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800073e7`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800075f1`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800075f1`
- `DEVRTL!NdxTableSetPropertyValue` at `0x180007556`
- `DEVRTL!NdxTableSetPropertyValue` at `0x18000757a`
- `DEVRTL!NdxTableSetPropertyValue` at `0x18000759e`
- `DEVRTL!NdxTableSetPropertyValue` at `0x180007556`
- `DEVRTL!NdxTableSetPropertyValue` at `0x18000757a`
- `DEVRTL!NdxTableSetPropertyValue` at `0x18000759e`

## pseudocode

```c
__int64 __fastcall InstallSystemCab(struct _INDEX_STRUCT *a1, struct NDX_OBJREF *a2)
{
  WCHAR *v4; // rdi
  WCHAR *v5; // r14
  unsigned __int16 *ObjectName; // r13
  unsigned __int16 *ObjectString; // r15
  DWORD LastError; // ebx
  const WCHAR *v9; // rax
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rax
  unsigned __int64 v15; // r12
  HANDLE ProcessHeap; // rax
  HANDLE v17; // rax
  HANDLE v18; // rax
  HANDLE v19; // rax
  __int64 v21; // [rsp+30h] [rbp-58h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-50h]
  _BYTE v23[16]; // [rsp+40h] [rbp-48h] BYREF

  LODWORD(v21) = 0;
  v4 = 0;
  v5 = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2);
  if ( *(_DWORD *)a1 != 1229866053 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1, a2);
  SRWLock = (PSRWLOCK)((char *)a1 + 32);
  AcquireSRWLockExclusive((PSRWLOCK)a1 + 4);
  ObjectName = MemGetObjectName(a2);
  if ( !ObjectName )
  {
    ObjectString = 0;
LABEL_9:
    LastError = 13;
    goto LABEL_36;
  }
  ObjectString = MemGetObjectString(a2, 3);
  if ( !ObjectString )
    goto LABEL_9;
  v5 = MemGetObjectString(a2, 0);
  if ( !v5 )
    goto LABEL_9;
  v9 = MemMallocAndCat(*((const unsigned __int16 **)a1 + 2), L"\\", ObjectString, L"\\", ObjectName, 0, v21, SRWLock);
  v4 = (WCHAR *)v9;
  if ( v9 )
  {
    if ( (unsigned int)FSMakeDirPathExist_StringSecurityDescriptor(v9, 0) )
    {
      if ( (Microsoft_Windows_UserPnpEnableBits & 4) != 0 )
        McGenEventWrite_EventWriteTransfer(userpnp_Context, DMRC_START_UNPACK_PACKAGE, v10, 1, v23);
      LastError = CabUnzip(v5, v4, 0, 0);
      if ( (Microsoft_Windows_UserPnpEnableBits & 4) != 0 )
        McGenEventWrite_EventWriteTransfer(userpnp_Context, DMRC_STOP_UNPACK_PACKAGE, v13, 1, v23);
      if ( LastError )
      {
        if ( LastError == 18
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, v5);
        }
        FSRemoveDirPath(v4);
      }
      else
      {
        v14 = -1;
        do
          ++v14;
        while ( v4[v14] );
        v15 = 2 * v14 + 2;
        if ( v15 > 0xFFFFFFFF )
          MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11);
        if ( (unsigned int)NdxTableSetPropertyValue(a2, 2, v4, (unsigned int)v15) )
        {
          LODWORD(v21) = 1;
          if ( !(unsigned int)NdxTableSetPropertyValue(a2, 1, &v21, 4) )
          {
            LastError = GetLastError();
            NdxTableSetPropertyValue(a2, 2, &dword_18001752C, 2);
          }
        }
        else
        {
          LastError = GetLastError();
        }
      }
    }
    else
    {
      LastError = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, v4);
    }
  }
  else
  {
    LastError = 8;
  }
LABEL_36:
  ReleaseSRWLockExclusive(SRWLock);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  if ( ObjectName )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, ObjectName);
  }
  if ( ObjectString )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, ObjectString);
  }
  if ( v5 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
  return LastError;
}

```

## disassembly

```asm
0x180007380  mov     [rsp+arg_10], rbx
0x180007385  mov     [rsp+arg_18], rsi
0x18000738a  push    rdi
0x18000738b  push    r12
0x18000738d  push    r13
0x18000738f  push    r14
0x180007391  push    r15
0x180007393  sub     rsp, 60h
0x180007397  mov     rax, cs:__security_cookie
0x18000739e  xor     rax, rsp
0x1800073a1  mov     [rsp+88h+var_38], rax
0x1800073a6  xor     r12d, r12d
0x1800073a9  mov     rsi, rdx
0x1800073ac  mov     dword ptr [rsp+88h+var_58], r12d
0x1800073b1  mov     rbx, rcx
0x1800073b4  mov     edi, r12d
0x1800073b7  mov     r14d, r12d
0x1800073ba  test    rcx, rcx
0x1800073bd  jnz     short loc_1800073C4
0x1800073bf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800073c4  cmp     dword ptr [rbx], 494E4445h
0x1800073ca  jz      short loc_1800073D1
0x1800073cc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800073d1  test    rsi, rsi
0x1800073d4  jnz     short loc_1800073DB
0x1800073d6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800073db  lea     rax, [rbx+20h]
0x1800073df  mov     rcx, rax; SRWLock
0x1800073e2  mov     [rsp+88h+SRWLock], rax
0x1800073e7  call    cs:__imp_AcquireSRWLockExclusive
0x1800073ed  mov     rcx, rsi; struct NDX_OBJREF *
0x1800073f0  call    ?MemGetObjectName@@YAPEAGPEAUNDX_OBJREF@@@Z; MemGetObjectName(NDX_OBJREF *)
0x1800073f5  mov     r13, rax
0x1800073f8  test    rax, rax
0x1800073fb  jnz     short loc_18000740A
0x1800073fd  mov     r15, r12
0x180007400  mov     ebx, 0Dh
0x180007405  jmp     loc_1800075EC
0x18000740a  mov     edx, 3; int
0x18000740f  mov     rcx, rsi; struct NDX_OBJREF *
0x180007412  call    ?MemGetObjectString@@YAPEAGPEAUNDX_OBJREF@@J@Z; MemGetObjectString(NDX_OBJREF *,long)
0x180007417  mov     r15, rax
0x18000741a  test    rax, rax
0x18000741d  jz      short loc_180007400
0x18000741f  xor     edx, edx; int
0x180007421  mov     rcx, rsi; struct NDX_OBJREF *
0x180007424  call    ?MemGetObjectString@@YAPEAGPEAUNDX_OBJREF@@J@Z; MemGetObjectString(NDX_OBJREF *,long)
0x180007429  mov     r14, rax
0x18000742c  test    rax, rax
0x18000742f  jz      short loc_180007400
0x180007431  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180007435  lea     rdx, asc_180016E08; "\\"
0x18000743c  mov     r9, rdx
0x18000743f  mov     [rsp+88h+var_60], r12
0x180007444  mov     r8, r15
0x180007447  mov     [rsp+88h+var_68], r13
0x18000744c  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x180007451  mov     rdi, rax
0x180007454  test    rax, rax
0x180007457  jnz     short loc_180007461
0x180007459  lea     ebx, [rax+8]
0x18000745c  jmp     loc_1800075EC
0x180007461  xor     edx, edx; StringSecurityDescriptor
0x180007463  mov     rcx, rdi; lpFileName
0x180007466  call    FSMakeDirPathExist_StringSecurityDescriptor
0x18000746b  test    eax, eax
0x18000746d  jnz     short loc_1800074B0
0x18000746f  mov     ebx, r12d
0x180007472  mov     rcx, cs:WPP_GLOBAL_Control
0x180007479  lea     rax, WPP_GLOBAL_Control
0x180007480  cmp     rcx, rax
0x180007483  jz      loc_1800075EC
0x180007489  test    byte ptr [rcx+1Ch], 1
0x18000748d  jz      loc_1800075EC
0x180007493  mov     rcx, [rcx+10h]
0x180007497  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x18000749e  mov     edx, 24h ; '$'
0x1800074a3  mov     r9, rdi
0x1800074a6  call    WPP_SF_S
0x1800074ab  jmp     loc_1800075EC
0x1800074b0  test    cs:Microsoft_Windows_UserPnpEnableBits, 4
0x1800074b7  jz      short loc_1800074DC
0x1800074b9  lea     rax, [rsp+88h+var_48]
0x1800074be  mov     r9d, 1
0x1800074c4  lea     rdx, DMRC_START_UNPACK_PACKAGE
0x1800074cb  mov     [rsp+88h+var_68], rax
0x1800074d0  lea     rcx, userpnp_Context
0x1800074d7  call    McGenEventWrite_EventWriteTransfer
0x1800074dc  xor     r9d, r9d; void *
0x1800074df  xor     r8d, r8d; enum CAB_COMMAND (__high *)(const unsigned __int16 *, void *)
0x1800074e2  mov     rdx, rdi; LPCWSTR
0x1800074e5  mov     rcx, r14; lpFileName
0x1800074e8  call    ?CabUnzip@@YAKPEBG0P6A?AW4CAB_COMMAND@@0PEAX@Z1@Z; CabUnzip(ushort const *,ushort const *,CAB_COMMAND (*)(ushort const *,void *),void *)
0x1800074ed  test    cs:Microsoft_Windows_UserPnpEnableBits, 4
0x1800074f4  mov     ebx, eax
0x1800074f6  jz      short loc_18000751B
0x1800074f8  lea     rax, [rsp+88h+var_48]
0x1800074fd  mov     r9d, 1
0x180007503  lea     rdx, DMRC_STOP_UNPACK_PACKAGE
0x18000750a  mov     [rsp+88h+var_68], rax
0x18000750f  lea     rcx, userpnp_Context
0x180007516  call    McGenEventWrite_EventWriteTransfer
0x18000751b  test    ebx, ebx
0x18000751d  jnz     loc_1800075B0
0x180007523  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007527  inc     rax
0x18000752a  cmp     [rdi+rax*2], r12w
0x18000752f  jnz     short loc_180007527
0x180007531  lea     r12, ds:2[rax*2]
0x180007539  mov     eax, 0FFFFFFFFh
0x18000753e  cmp     r12, rax
0x180007541  jbe     short loc_180007548
0x180007543  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180007548  mov     r9d, r12d
0x18000754b  mov     r8, rdi
0x18000754e  mov     edx, 2
0x180007553  mov     rcx, rsi
0x180007556  call    cs:__imp_NdxTableSetPropertyValue
0x18000755c  test    eax, eax
0x18000755e  jz      short loc_1800075A6
0x180007560  mov     r9d, 4
0x180007566  mov     dword ptr [rsp+88h+var_58], 1
0x18000756e  lea     r8, [rsp+88h+var_58]
0x180007573  mov     rcx, rsi
0x180007576  lea     edx, [r9-3]
0x18000757a  call    cs:__imp_NdxTableSetPropertyValue
0x180007580  test    eax, eax
0x180007582  jnz     short loc_1800075EC
0x180007584  call    cs:__imp_GetLastError
0x18000758a  mov     edx, 2
0x18000758f  lea     r8, dword_18001752C
0x180007596  mov     r9d, edx
0x180007599  mov     rcx, rsi
0x18000759c  mov     ebx, eax
0x18000759e  call    cs:__imp_NdxTableSetPropertyValue
0x1800075a4  jmp     short loc_1800075EC
0x1800075a6  call    cs:__imp_GetLastError
0x1800075ac  mov     ebx, eax
0x1800075ae  jmp     short loc_1800075EC
0x1800075b0  cmp     ebx, 12h
0x1800075b3  jnz     short loc_1800075E4
0x1800075b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075bc  lea     rax, WPP_GLOBAL_Control
0x1800075c3  cmp     rcx, rax
0x1800075c6  jz      short loc_1800075E4
0x1800075c8  test    byte ptr [rcx+1Ch], 8
0x1800075cc  jz      short loc_1800075E4
0x1800075ce  mov     rcx, [rcx+10h]
0x1800075d2  lea     edx, [rbx+13h]
0x1800075d5  mov     r9, r14
0x1800075d8  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x1800075df  call    WPP_SF_S
0x1800075e4  mov     rcx, rdi
0x1800075e7  call    FSRemoveDirPath
0x1800075ec  mov     rcx, [rsp+88h+SRWLock]; SRWLock
0x1800075f1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800075f7  test    rdi, rdi
0x1800075fa  jz      short loc_180007610
0x1800075fc  call    cs:__imp_GetProcessHeap
0x180007602  mov     r8, rdi; lpMem
0x180007605  xor     edx, edx; dwFlags
0x180007607  mov     rcx, rax; hHeap
0x18000760a  call    cs:__imp_HeapFree
0x180007610  test    r13, r13
0x180007613  jz      short loc_180007629
0x180007615  call    cs:__imp_GetProcessHeap
0x18000761b  mov     r8, r13; lpMem
0x18000761e  xor     edx, edx; dwFlags
0x180007620  mov     rcx, rax; hHeap
0x180007623  call    cs:__imp_HeapFree
0x180007629  test    r15, r15
0x18000762c  jz      short loc_180007642
0x18000762e  call    cs:__imp_GetProcessHeap
0x180007634  mov     r8, r15; lpMem
0x180007637  xor     edx, edx; dwFlags
0x180007639  mov     rcx, rax; hHeap
0x18000763c  call    cs:__imp_HeapFree
0x180007642  test    r14, r14
0x180007645  jz      short loc_18000765B
0x180007647  call    cs:__imp_GetProcessHeap
0x18000764d  mov     r8, r14; lpMem
0x180007650  xor     edx, edx; dwFlags
0x180007652  mov     rcx, rax; hHeap
0x180007655  call    cs:__imp_HeapFree
0x18000765b  mov     eax, ebx
0x18000765d  mov     rcx, [rsp+88h+var_38]
0x180007662  xor     rcx, rsp; StackCookie
0x180007665  call    __security_check_cookie
0x18000766a  lea     r11, [rsp+88h+var_28]
0x18000766f  mov     rbx, [r11+40h]
0x180007673  mov     rsi, [r11+48h]
0x180007677  mov     rsp, r11
0x18000767a  pop     r15
0x18000767c  pop     r14
0x18000767e  pop     r13
0x180007680  pop     r12
0x180007682  pop     rdi
0x180007683  retn
```
