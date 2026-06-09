# NfsUpCallpPasswdGroupRefreshGroupIfNeeded

- ea: `0x140011614`
- end: `0x1400117f7`
- name: `NfsUpCallpPasswdGroupRefreshGroupIfNeeded`
- size: `483`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x140010be4`
- `0x140011e80`

## callees

- `0x140011440`
- `0x1400114ac`
- `0x140011614`
- `0x1400120d4`
- `0x140018350`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x1400117d0`
- `ADVAPI32!EventWrite` at `0x1400117d0`
- `ADVAPI32!EventEnabled` at `0x1400117b1`
- `ADVAPI32!EventEnabled` at `0x1400117b1`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14001165d`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14001165d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001175c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14001175c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140011732`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140011732`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400116af`
- `KERNEL32!ReleaseSRWLockShared` at `0x1400116af`
- `KERNEL32!AcquireSRWLockShared` at `0x14001168c`
- `KERNEL32!AcquireSRWLockShared` at `0x14001168c`
- `KERNEL32!GetLastError` at `0x140011667`
- `KERNEL32!GetLastError` at `0x140011667`
- `ntdll!RtlFreeHeap` at `0x14001174b`
- `ntdll!RtlFreeHeap` at `0x14001174b`

## string_xrefs

- `0x140011640`: `%SystemRoot%\System32\drivers\etc\group`

## pseudocode

```c
__int64 __fastcall NfsUpCallpPasswdGroupRefreshGroupIfNeeded(__int64 a1, __int64 a2)
{
  void *Ptr; // rbx
  DWORD LastError; // eax
  unsigned int refreshed; // esi
  char v6; // r14
  __int64 v7; // rcx
  __int64 *v8; // rbx
  __int64 v9; // rax
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Dst[264]; // [rsp+30h] [rbp-D0h] BYREF

  Ptr = 0;
  UserData.Ptr = 0;
  if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\drivers\\etc\\group", Dst, 0x105u) )
  {
    LastError = NfsUpCallpPasswdGroupQueryLastWriteTime(Dst, &UserData);
    Ptr = (void *)UserData.Ptr;
  }
  else
  {
    LastError = GetLastError();
  }
  refreshed = LastError;
  if ( LastError )
    goto LABEL_34;
  AcquireSRWLockShared((PSRWLOCK)a2);
  if ( !*(_QWORD *)(a2 + 16)
    || *(_DWORD *)(a2 + 32) != (_DWORD)Ptr
    || (v6 = 0, *(_DWORD *)(a2 + 36) != HIDWORD(UserData.Ptr)) )
  {
    v6 = 1;
  }
  ReleaseSRWLockShared((PSRWLOCK)a2);
  if ( v6 )
  {
    refreshed = NfsUpCallpPasswdGroupRefreshGroup(v7, (RTL_SRWLOCK *)a2, Dst, Ptr);
    if ( refreshed )
    {
LABEL_34:
      if ( *(_QWORD *)(a2 + 16) )
      {
        switch ( refreshed )
        {
          case 2u:
            v8 = EVENT_NFS_SERVICE_PASSWDGROUP_FILE_NOT_FOUND;
            break;
          case 8u:
            v8 = EVENT_NFS_SERVICE_PASSWDGROUP_NOT_ENOUGH_MEMORY;
            break;
          case 0xDu:
            v8 = 0;
            break;
          case 0xDFu:
            v8 = EVENT_NFS_SERVICE_PASSWDGROUP_FILE_TOO_LARGE;
            break;
          case 0xE8u:
            v8 = EVENT_NFS_SERVICE_PASSWDGROUP_NO_DATA;
            break;
          default:
            v8 = (__int64 *)&EVENT_NFS_SERVICE_PASSWDGROUP_LOAD_FAILED;
            break;
        }
        AcquireSRWLockExclusive((PSRWLOCK)a2);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)(a2 + 16));
        *(_QWORD *)(a2 + 16) = 0;
        *(_QWORD *)(a2 + 32) = 0;
        ReleaseSRWLockExclusive((PSRWLOCK)a2);
        if ( *(_QWORD *)(a2 + 40) )
          SendMapCacheRefreshIoctlToDriver();
        if ( v8 )
        {
          UserData.Ptr = (ULONGLONG)Dst;
          v9 = -1;
          do
            ++v9;
          while ( Dst[v9] );
          UserData.Size = 2 * v9 + 2;
          UserData.Reserved = 0;
          if ( RegHandle )
          {
            if ( EventEnabled(RegHandle, (PCEVENT_DESCRIPTOR)v8) )
              EventWrite(RegHandle, (PCEVENT_DESCRIPTOR)v8, 1u, &UserData);
          }
        }
      }
    }
  }
  return refreshed;
}

```

## disassembly

```asm
0x140011614  push    rbp
0x140011616  push    rbx
0x140011617  push    rsi
0x140011618  push    rdi
0x140011619  push    r14
0x14001161b  push    r15
0x14001161d  lea     rbp, [rsp-158h]
0x140011625  sub     rsp, 258h
0x14001162c  mov     rax, cs:__security_cookie
0x140011633  xor     rax, rsp
0x140011636  mov     [rbp+180h+var_40], rax
0x14001163d  mov     rdi, rdx
0x140011640  lea     rcx, Src; "%SystemRoot%\\System32\\drivers\\etc\\g"...
0x140011647  xor     r15d, r15d
0x14001164a  lea     rdx, [rsp+280h+Dst]; lpDst
0x14001164f  mov     ebx, r15d
0x140011652  mov     r8d, 105h; nSize
0x140011658  mov     [rsp+280h+UserData.Ptr], rbx
0x14001165d  call    cs:__imp_ExpandEnvironmentStringsW
0x140011663  test    eax, eax
0x140011665  jnz     short loc_14001166F
0x140011667  call    cs:__imp_GetLastError
0x14001166d  jmp     short loc_140011683
0x14001166f  lea     rdx, [rsp+280h+UserData]
0x140011674  lea     rcx, [rsp+280h+Dst]
0x140011679  call    NfsUpCallpPasswdGroupQueryLastWriteTime
0x14001167e  mov     rbx, [rsp+280h+UserData.Ptr]
0x140011683  mov     esi, eax
0x140011685  test    eax, eax
0x140011687  jnz     short loc_1400116D8
0x140011689  mov     rcx, rdi; SRWLock
0x14001168c  call    cs:__imp_AcquireSRWLockShared
0x140011692  cmp     [rdi+10h], r15
0x140011696  jz      short loc_1400116A9
0x140011698  cmp     [rdi+20h], ebx
0x14001169b  jnz     short loc_1400116A9
0x14001169d  mov     eax, dword ptr [rsp+280h+UserData.Ptr+4]
0x1400116a1  mov     r14b, r15b
0x1400116a4  cmp     [rdi+24h], eax
0x1400116a7  jz      short loc_1400116AC
0x1400116a9  mov     r14b, 1
0x1400116ac  mov     rcx, rdi; SRWLock
0x1400116af  call    cs:__imp_ReleaseSRWLockShared
0x1400116b5  test    r14b, r14b
0x1400116b8  jz      loc_1400117D6
0x1400116be  mov     r9, rbx
0x1400116c1  lea     r8, [rsp+280h+Dst]
0x1400116c6  mov     rdx, rdi
0x1400116c9  call    NfsUpCallpPasswdGroupRefreshGroup
0x1400116ce  mov     esi, eax
0x1400116d0  test    eax, eax
0x1400116d2  jz      loc_1400117D6
0x1400116d8  cmp     [rdi+10h], r15
0x1400116dc  jz      loc_1400117D6
0x1400116e2  mov     eax, esi
0x1400116e4  sub     eax, 2
0x1400116e7  jz      short loc_140011728
0x1400116e9  sub     eax, 6
0x1400116ec  jz      short loc_14001171F
0x1400116ee  sub     eax, 5
0x1400116f1  jz      short loc_14001171A
0x1400116f3  sub     eax, 0D2h
0x1400116f8  jz      short loc_140011711
0x1400116fa  cmp     eax, 9
0x1400116fd  jz      short loc_140011708
0x1400116ff  lea     rbx, EVENT_NFS_SERVICE_PASSWDGROUP_LOAD_FAILED
0x140011706  jmp     short loc_14001172F
0x140011708  lea     rbx, EVENT_NFS_SERVICE_PASSWDGROUP_NO_DATA
0x14001170f  jmp     short loc_14001172F
0x140011711  lea     rbx, EVENT_NFS_SERVICE_PASSWDGROUP_FILE_TOO_LARGE
0x140011718  jmp     short loc_14001172F
0x14001171a  mov     rbx, r15
0x14001171d  jmp     short loc_14001172F
0x14001171f  lea     rbx, EVENT_NFS_SERVICE_PASSWDGROUP_NOT_ENOUGH_MEMORY
0x140011726  jmp     short loc_14001172F
0x140011728  lea     rbx, EVENT_NFS_SERVICE_PASSWDGROUP_FILE_NOT_FOUND
0x14001172f  mov     rcx, rdi; SRWLock
0x140011732  call    cs:__imp_AcquireSRWLockExclusive
0x140011738  mov     rcx, gs:60h
0x140011741  xor     edx, edx; Flags
0x140011743  mov     r8, [rdi+10h]; P
0x140011747  mov     rcx, [rcx+30h]; HeapHandle
0x14001174b  call    cs:__imp_RtlFreeHeap
0x140011751  mov     rcx, rdi; SRWLock
0x140011754  mov     [rdi+10h], r15
0x140011758  mov     [rdi+20h], r15
0x14001175c  call    cs:__imp_ReleaseSRWLockExclusive
0x140011762  mov     rcx, [rdi+28h]
0x140011766  test    rcx, rcx
0x140011769  jz      short loc_140011770
0x14001176b  call    SendMapCacheRefreshIoctlToDriver
0x140011770  test    rbx, rbx
0x140011773  jz      short loc_1400117D6
0x140011775  lea     rax, [rsp+280h+Dst]
0x14001177a  mov     [rsp+280h+UserData.Ptr], rax
0x14001177f  lea     rcx, [rsp+280h+Dst]
0x140011784  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011788  inc     rax
0x14001178b  cmp     [rcx+rax*2], r15w
0x140011790  jnz     short loc_140011788
0x140011792  mov     rcx, cs:RegHandle; RegHandle
0x140011799  lea     eax, ds:2[rax*2]
0x1400117a0  mov     [rsp+280h+UserData.Size], eax
0x1400117a4  mov     dword ptr [rsp+280h+UserData.0Ch], r15d
0x1400117a9  test    rcx, rcx
0x1400117ac  jz      short loc_1400117D6
0x1400117ae  mov     rdx, rbx; EventDescriptor
0x1400117b1  call    cs:__imp_EventEnabled
0x1400117b7  test    al, al
0x1400117b9  jz      short loc_1400117D6
0x1400117bb  mov     rcx, cs:RegHandle; RegHandle
0x1400117c2  lea     r9, [rsp+280h+UserData]; UserData
0x1400117c7  mov     r8d, 1; UserDataCount
0x1400117cd  mov     rdx, rbx; EventDescriptor
0x1400117d0  call    cs:__imp_EventWrite
0x1400117d6  mov     eax, esi
0x1400117d8  mov     rcx, [rbp+180h+var_40]
0x1400117df  xor     rcx, rsp; StackCookie
0x1400117e2  call    __security_check_cookie
0x1400117e7  add     rsp, 258h
0x1400117ee  pop     r15
0x1400117f0  pop     r14
0x1400117f2  pop     rdi
0x1400117f3  pop     rsi
0x1400117f4  pop     rbx
0x1400117f5  pop     rbp
0x1400117f6  retn
```
