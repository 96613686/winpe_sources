# QueueRequest

- ea: `0x1800dc330`
- end: `0x1800dc4c0`
- name: `QueueRequest`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800da7b0`
- `0x1800da9b0`
- `0x1800dbb68`
- `0x1800dc1f4`
- `0x1800dc330`
- `0x1801503e0`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1800dc433`
- `KERNEL32!WaitForSingleObject` at `0x1800dc433`
- `KERNEL32!ReleaseSemaphore` at `0x1800dc489`
- `KERNEL32!ReleaseSemaphore` at `0x1800dc489`
- `KERNEL32!TlsSetValue` at `0x1800dc37a`
- `KERNEL32!TlsSetValue` at `0x1800dc388`
- `KERNEL32!TlsSetValue` at `0x1800dc37a`
- `KERNEL32!TlsSetValue` at `0x1800dc388`
- `KERNEL32!GetCurrentThread` at `0x1800dc3fc`
- `KERNEL32!GetCurrentThread` at `0x1800dc3fc`
- `KERNEL32!LeaveCriticalSection` at `0x1800dc466`
- `KERNEL32!LeaveCriticalSection` at `0x1800dc475`
- `KERNEL32!LeaveCriticalSection` at `0x1800dc466`
- `KERNEL32!LeaveCriticalSection` at `0x1800dc475`
- `KERNEL32!EnterCriticalSection` at `0x1800dc448`
- `KERNEL32!EnterCriticalSection` at `0x1800dc448`
- `ADVAPI32!OpenThreadToken` at `0x1800dc40f`
- `ADVAPI32!OpenThreadToken` at `0x1800dc40f`
- `ole32!CoCreateGuid` at `0x1800dc3da`
- `ole32!CoCreateGuid` at `0x1800dc3da`
- `onetnative!ULSCorrelationGetVisibleID` at `0x1800dc3b6`
- `onetnative!ULSCorrelationGetVisibleID` at `0x1800dc3b6`
- `onetnative!ULSGetOverrideTraceLevel` at `0x1800dc3e4`
- `onetnative!ULSGetOverrideTraceLevel` at `0x1800dc3e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall QueueRequest(__int64 a1, __int64 a2, int a3)
{
  struct COWSThreadHandler *v6; // r14
  int v7; // r15d
  char v8; // al
  int v9; // ecx
  unsigned int v10; // ebx
  HANDLE CurrentThread; // rax
  _BYTE v13[32]; // [rsp+30h] [rbp-31h] BYREF
  _QWORD v14[2]; // [rsp+50h] [rbp-11h] BYREF
  int v15; // [rsp+60h] [rbp-1h]
  HANDLE TokenHandle; // [rsp+68h] [rbp+7h] BYREF
  GUID pguid; // [rsp+70h] [rbp+Fh] BYREF
  int v18; // [rsp+80h] [rbp+1Fh] BYREF

  CBackupTlsSlots::CBackupTlsSlots((CBackupTlsSlots *)v13);
  TlsSetValue(dword_1802AF500, 0);
  TlsSetValue(dwTlsIndex, 0);
  v6 = qword_1802B0430;
  v7 = 1;
  v14[0] = a1;
  v14[1] = a2;
  v15 = a3;
  pguid = (GUID)xmmword_180176AD0;
  ULSCorrelationGetVisibleID(&pguid);
  if ( !*(_QWORD *)&pguid.Data1 && !*(_QWORD *)pguid.Data4 )
    CoCreateGuid(&pguid);
  v8 = ULSGetOverrideTraceLevel(&v18);
  v9 = v18;
  v10 = 0;
  if ( !v8 )
    v9 = 10;
  v18 = v9;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) && (unsigned int)sub_1800DC1F4((char *)v6 + 64, v14) )
  {
    while ( WaitForSingleObject(*((HANDLE *)v6 + 26), 0) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 136));
      if ( *((_DWORD *)v6 + 4) >= *((_DWORD *)v6 + 3) )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 136));
        break;
      }
      v7 = sub_1800DBB68(v6);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 136));
    }
    ReleaseSemaphore(*((HANDLE *)v6 + 23), 1, 0);
    v10 = v7;
  }
  CBackupTlsSlots::~CBackupTlsSlots((CBackupTlsSlots *)v13);
  return v10;
}

```

## disassembly

```asm
0x1800dc330  mov     rax, rsp
0x1800dc333  push    rbp
0x1800dc334  push    rsi
0x1800dc335  push    rdi
0x1800dc336  push    r14
0x1800dc338  push    r15
0x1800dc33a  lea     rbp, [rax-5Fh]
0x1800dc33e  sub     rsp, 90h
0x1800dc345  mov     [rbp+57h+var_90], 0FFFFFFFFFFFFFFFEh
0x1800dc34d  mov     [rax+20h], rbx
0x1800dc351  mov     rax, cs:__security_cookie
0x1800dc358  xor     rax, rsp
0x1800dc35b  mov     [rbp+57h+var_30], rax
0x1800dc35f  mov     esi, r8d
0x1800dc362  mov     rdi, rdx
0x1800dc365  mov     rbx, rcx
0x1800dc368  lea     rcx, [rbp+57h+var_88]; this
0x1800dc36c  call    ??0CBackupTlsSlots@@QEAA@XZ; CBackupTlsSlots::CBackupTlsSlots(void)
0x1800dc371  nop
0x1800dc372  xor     edx, edx; lpTlsValue
0x1800dc374  mov     ecx, cs:dword_1802AF500; dwTlsIndex
0x1800dc37a  call    cs:TlsSetValue
0x1800dc380  xor     edx, edx; lpTlsValue
0x1800dc382  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x1800dc388  call    cs:TlsSetValue
0x1800dc38e  mov     r14, cs:qword_1802B0430
0x1800dc395  mov     r15d, 1
0x1800dc39b  mov     [rbp+57h+var_68], rbx
0x1800dc39f  mov     [rbp+57h+var_60], rdi
0x1800dc3a3  mov     [rbp+57h+var_58], esi
0x1800dc3a6  movups  xmm0, cs:xmmword_180176AD0
0x1800dc3ad  movdqu  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x1800dc3b2  lea     rcx, [rbp+57h+pguid]
0x1800dc3b6  call    cs:ULSCorrelationGetVisibleID
0x1800dc3bc  mov     rax, qword ptr [rbp+57h+pguid.Data1]
0x1800dc3c0  cmp     rax, qword ptr cs:xmmword_180176AD0
0x1800dc3c7  jnz     short loc_1800DC3E0
0x1800dc3c9  mov     rax, qword ptr [rbp+57h+pguid.Data4]
0x1800dc3cd  cmp     rax, qword ptr cs:xmmword_180176AD0+8
0x1800dc3d4  jnz     short loc_1800DC3E0
0x1800dc3d6  lea     rcx, [rbp+57h+pguid]; pguid
0x1800dc3da  call    cs:CoCreateGuid
0x1800dc3e0  lea     rcx, [rbp+57h+var_38]
0x1800dc3e4  call    cs:ULSGetOverrideTraceLevel
0x1800dc3ea  mov     ecx, [rbp+57h+var_38]
0x1800dc3ed  mov     edx, 0Ah
0x1800dc3f2  xor     ebx, ebx
0x1800dc3f4  test    al, al
0x1800dc3f6  cmovz   ecx, edx
0x1800dc3f9  mov     [rbp+57h+var_38], ecx
0x1800dc3fc  call    cs:GetCurrentThread
0x1800dc402  mov     rcx, rax; ThreadHandle
0x1800dc405  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800dc409  lea     edx, [rbx+0Ch]; DesiredAccess
0x1800dc40c  mov     r8d, r15d; OpenAsSelf
0x1800dc40f  call    cs:OpenThreadToken
0x1800dc415  test    eax, eax
0x1800dc417  jz      short loc_1800DC492
0x1800dc419  lea     rcx, [r14+40h]
0x1800dc41d  lea     rdx, [rbp+57h+var_68]
0x1800dc421  call    sub_1800DC1F4
0x1800dc426  test    eax, eax
0x1800dc428  jz      short loc_1800DC492
0x1800dc42a  xor     edx, edx; dwMilliseconds
0x1800dc42c  mov     rcx, [r14+0D0h]; hHandle
0x1800dc433  call    cs:WaitForSingleObject
0x1800dc439  cmp     eax, 1
0x1800dc43c  jb      short loc_1800DC47B
0x1800dc43e  lea     rbx, [r14+88h]
0x1800dc445  mov     rcx, rbx; lpCriticalSection
0x1800dc448  call    cs:EnterCriticalSection
0x1800dc44e  mov     eax, [r14+0Ch]
0x1800dc452  cmp     [r14+10h], eax
0x1800dc456  jge     short loc_1800DC46E
0x1800dc458  mov     rcx, r14; struct COWSThreadHandler *
0x1800dc45b  call    sub_1800DBB68
0x1800dc460  mov     r15d, eax
0x1800dc463  mov     rcx, rbx; lpCriticalSection
0x1800dc466  call    cs:LeaveCriticalSection
0x1800dc46c  jmp     short loc_1800DC42A
0x1800dc46e  lea     rcx, [r14+88h]; lpCriticalSection
0x1800dc475  call    cs:LeaveCriticalSection
0x1800dc47b  xor     r8d, r8d; lpPreviousCount
0x1800dc47e  lea     edx, [r8+1]; lReleaseCount
0x1800dc482  mov     rcx, [r14+0B8h]; hSemaphore
0x1800dc489  call    cs:ReleaseSemaphore
0x1800dc48f  mov     ebx, r15d
0x1800dc492  lea     rcx, [rbp+57h+var_88]; this
0x1800dc496  call    ??1CBackupTlsSlots@@QEAA@XZ; CBackupTlsSlots::~CBackupTlsSlots(void)
0x1800dc49b  mov     eax, ebx
0x1800dc49d  mov     rcx, [rbp+57h+var_30]
0x1800dc4a1  xor     rcx, rsp
0x1800dc4a4  call    sub_1801503E0
0x1800dc4a9  mov     rbx, [rsp+0B0h+arg_18]
0x1800dc4b1  add     rsp, 90h
0x1800dc4b8  pop     r15
0x1800dc4ba  pop     r14
0x1800dc4bc  pop     rdi
0x1800dc4bd  pop     rsi
0x1800dc4be  pop     rbp
0x1800dc4bf  retn
```
