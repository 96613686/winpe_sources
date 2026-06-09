# Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::~SecuredDirectory(void)

- ea: `0x18002e994`
- end: `0x18002eaa9`
- name: `??1SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@QEAA@XZ`
- size: `277`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *__hidden this)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001af30`
- `0x18001d180`
- `0x180024de8`
- `0x18002a80c`
- `0x18002d9a4`
- `0x180032470`
- `0x180036310`

## callees

- `0x18002e994`
- `0x1800315c8`
- `0x18004106c`
- `0x1800412ac`
- `0x18004b640`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002e9a9`
- `KERNEL32!CloseHandle` at `0x18002ea10`
- `KERNEL32!CloseHandle` at `0x18002ea2d`
- `KERNEL32!CloseHandle` at `0x18002ea4a`
- `KERNEL32!CloseHandle` at `0x18002ea6d`
- `KERNEL32!CloseHandle` at `0x18002e9a9`
- `KERNEL32!CloseHandle` at `0x18002ea10`
- `KERNEL32!CloseHandle` at `0x18002ea2d`
- `KERNEL32!CloseHandle` at `0x18002ea4a`
- `KERNEL32!CloseHandle` at `0x18002ea6d`
- `KERNEL32!DeleteCriticalSection` at `0x18002e9fe`
- `KERNEL32!DeleteCriticalSection` at `0x18002e9fe`
- `ADVAPI32!SetThreadToken` at `0x18002e9d1`
- `ADVAPI32!SetThreadToken` at `0x18002e9d1`
- `ADVAPI32!RevertToSelf` at `0x18002e9e3`
- `ADVAPI32!RevertToSelf` at `0x18002e9e3`

## pseudocode

```c
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::~SecuredDirectory(
        Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *this,
        void *a2)
{
  void *v3; // rcx
  void *v4; // rdx
  const unsigned __int16 *v5; // rdx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  volatile signed __int32 *v10; // rdx

  v3 = (void *)*((_QWORD *)this + 18);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 18) = 0;
  }
  if ( *((_BYTE *)this + 9) )
  {
    if ( *((_BYTE *)this + 8) )
    {
      DiagHubCommon::DeleteDirectory(*((HANDLE *)this + 20), a2);
    }
    else
    {
      v4 = (void *)*((_QWORD *)this + 2);
      if ( v4 && SetThreadToken(0, v4) )
      {
        DiagHubCommon::DeleteDirectory(*(DiagHubCommon **)this, v5);
        RevertToSelf();
      }
    }
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  v6 = (void *)*((_QWORD *)this + 20);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 20) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 19);
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 19) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 18);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 18) = 0;
  }
  ATL::CSid::~CSid((Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *)((char *)this + 24));
  v9 = (void *)*((_QWORD *)this + 2);
  if ( v9 )
  {
    CloseHandle(v9);
    *((_QWORD *)this + 2) = 0;
  }
  v10 = (volatile signed __int32 *)(*(_QWORD *)this - 24LL);
  if ( _InterlockedExchangeAdd(v10 + 4, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
  }
}

```

## disassembly

```asm
0x18002e994  push    rbx
0x18002e996  sub     rsp, 20h
0x18002e99a  mov     rbx, rcx
0x18002e99d  mov     rcx, [rcx+90h]; hObject
0x18002e9a4  test    rcx, rcx
0x18002e9a7  jz      short loc_18002E9BA
0x18002e9a9  call    cs:__imp_CloseHandle
0x18002e9af  mov     qword ptr [rbx+90h], 0
0x18002e9ba  cmp     byte ptr [rbx+9], 0
0x18002e9be  jz      short loc_18002E9F7
0x18002e9c0  cmp     byte ptr [rbx+8], 0
0x18002e9c4  jnz     short loc_18002E9EB
0x18002e9c6  mov     rdx, [rbx+10h]; Token
0x18002e9ca  test    rdx, rdx
0x18002e9cd  jz      short loc_18002E9F7
0x18002e9cf  xor     ecx, ecx; Thread
0x18002e9d1  call    cs:__imp_SetThreadToken
0x18002e9d7  test    eax, eax
0x18002e9d9  jz      short loc_18002E9F7
0x18002e9db  mov     rcx, [rbx]; this
0x18002e9de  call    ?DeleteDirectory@DiagHubCommon@@YAJPEBG_N@Z; DiagHubCommon::DeleteDirectory(ushort const *,bool)
0x18002e9e3  call    cs:__imp_RevertToSelf
0x18002e9e9  jmp     short loc_18002E9F7
0x18002e9eb  mov     rcx, [rbx+0A0h]; hFile
0x18002e9f2  call    ?DeleteDirectory@DiagHubCommon@@YAJPEAX_N@Z; DiagHubCommon::DeleteDirectory(void *,bool)
0x18002e9f7  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x18002e9fe  call    cs:__imp_DeleteCriticalSection
0x18002ea04  mov     rcx, [rbx+0A0h]; hObject
0x18002ea0b  test    rcx, rcx
0x18002ea0e  jz      short loc_18002EA21
0x18002ea10  call    cs:__imp_CloseHandle
0x18002ea16  mov     qword ptr [rbx+0A0h], 0
0x18002ea21  mov     rcx, [rbx+98h]; hObject
0x18002ea28  test    rcx, rcx
0x18002ea2b  jz      short loc_18002EA3E
0x18002ea2d  call    cs:__imp_CloseHandle
0x18002ea33  mov     qword ptr [rbx+98h], 0
0x18002ea3e  mov     rcx, [rbx+90h]; hObject
0x18002ea45  test    rcx, rcx
0x18002ea48  jz      short loc_18002EA5B
0x18002ea4a  call    cs:__imp_CloseHandle
0x18002ea50  mov     qword ptr [rbx+90h], 0
0x18002ea5b  lea     rcx, [rbx+18h]; this
0x18002ea5f  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002ea64  mov     rcx, [rbx+10h]; hObject
0x18002ea68  test    rcx, rcx
0x18002ea6b  jz      short loc_18002EA7B
0x18002ea6d  call    cs:__imp_CloseHandle
0x18002ea73  mov     qword ptr [rbx+10h], 0
0x18002ea7b  mov     rdx, [rbx]
0x18002ea7e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002ea82  or      eax, 0FFFFFFFFh
0x18002ea85  lock xadd [rdx+10h], eax
0x18002ea8a  sub     eax, 1
0x18002ea8d  jg      short loc_18002EAA3
0x18002ea8f  lfence
0x18002ea92  mov     rcx, [rdx]
0x18002ea95  mov     rax, [rcx]
0x18002ea98  mov     rax, [rax+8]
0x18002ea9c  call    cs:__guard_dispatch_icall_fptr
0x18002eaa2  nop
0x18002eaa3  add     rsp, 20h
0x18002eaa7  pop     rbx
0x18002eaa8  retn
```
