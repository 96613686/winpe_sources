# UtcThrottle::Initialize(ushort const *)

- ea: `0x180028a24`
- end: `0x180028df6`
- name: `?Initialize@UtcThrottle@@QEAAKPEBG@Z`
- size: `978`
- prototype: `unsigned int __fastcall(UtcThrottle *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029258`
- `0x18002b894`
- `0x1801dd798`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x180011d94`
- `0x18001a2f4`
- `0x180028a24`
- `0x180028dfc`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180028bfe`
- `KERNEL32!CreateEventW` at `0x180028bfe`
- `KERNEL32!CreateSemaphoreW` at `0x180028c46`
- `KERNEL32!CreateSemaphoreW` at `0x180028c81`
- `KERNEL32!CreateSemaphoreW` at `0x180028c46`
- `KERNEL32!CreateSemaphoreW` at `0x180028c81`
- `KERNEL32!OpenWaitableTimerW` at `0x180028cf0`
- `KERNEL32!OpenWaitableTimerW` at `0x180028cf0`
- `KERNEL32!CreateWaitableTimerW` at `0x180028cc1`
- `KERNEL32!CreateWaitableTimerW` at `0x180028d3f`
- `KERNEL32!CreateWaitableTimerW` at `0x180028cc1`
- `KERNEL32!CreateWaitableTimerW` at `0x180028d3f`
- `KERNEL32!LocalFree` at `0x180028db0`
- `KERNEL32!LocalFree` at `0x180028db0`
- `KERNEL32!SetWaitableTimer` at `0x180028d87`
- `KERNEL32!SetWaitableTimer` at `0x180028d87`
- `KERNEL32!CloseHandle` at `0x180028d95`
- `KERNEL32!CloseHandle` at `0x180028d95`
- `KERNEL32!GetLastError` at `0x180028c0d`
- `KERNEL32!GetLastError` at `0x180028c54`
- `KERNEL32!GetLastError` at `0x180028c8f`
- `KERNEL32!GetLastError` at `0x180028cd4`
- `KERNEL32!GetLastError` at `0x180028cff`
- `KERNEL32!GetLastError` at `0x180028d4e`
- `KERNEL32!GetLastError` at `0x180028c0d`
- `KERNEL32!GetLastError` at `0x180028c54`
- `KERNEL32!GetLastError` at `0x180028c8f`
- `KERNEL32!GetLastError` at `0x180028cd4`
- `KERNEL32!GetLastError` at `0x180028cff`
- `KERNEL32!GetLastError` at `0x180028d4e`
- `KERNEL32!LeaveCriticalSection` at `0x180028dc3`
- `KERNEL32!LeaveCriticalSection` at `0x180028dc3`
- `KERNEL32!EnterCriticalSection` at `0x180028ac3`
- `KERNEL32!EnterCriticalSection` at `0x180028ac3`

## string_xrefs

- `0x180028bc8`: `Failed to initialize security descriptor [%d]`
- `0x180028c5e`: `Failed to create named semaphore [%d]`
- `0x180028c15`: `Failed to create event [%d]`
- `0x180028c95`: `Failed to create semaphore [%d]`
- `0x180028d05`: `Failed to open named timer [%d]`
- `0x180028d17`: `Failed to create named timer [%d]`
- `0x180028d54`: `Failed to create timer [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtcThrottle::Initialize(UtcThrottle *this, const unsigned __int16 *a2)
{
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  const wchar_t *v8; // r9
  WCHAR *v9; // rax
  wchar_t v10; // r10
  WCHAR *v11; // rcx
  unsigned int v12; // ebx
  const wchar_t *v13; // rcx
  WCHAR *v14; // rax
  wchar_t v15; // dx
  UtcThrottle *v16; // rcx
  DWORD LastError; // eax
  const char *v18; // r9
  __int64 v19; // r8
  HANDLE EventW; // rax
  HANDLE v21; // rax
  DWORD v22; // eax
  HANDLE v23; // rax
  HANDLE v24; // rax
  DWORD v25; // eax
  __int64 v26; // r8
  HANDLE v27; // rax
  const char *v28; // r9
  __int64 v29; // rcx
  LPVOID lpArgToCompletionRoutine; // [rsp+28h] [rbp-E0h]
  HLOCAL hMem; // [rsp+38h] [rbp-D0h] BYREF
  LARGE_INTEGER DueTime; // [rsp+40h] [rbp-C8h] BYREF
  struct _SECURITY_ATTRIBUTES SemaphoreAttributes; // [rsp+48h] [rbp-C0h] BYREF
  _SECURITY_DESCRIPTOR v35; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+88h] [rbp-80h]
  WCHAR TimerName[264]; // [rsp+98h] [rbp-70h] BYREF
  WCHAR Name[264]; // [rsp+2A8h] [rbp+1A0h] BYREF

  *(_QWORD *)&v35.Revision = -2;
  memset(&v35.Owner, 0, 32);
  v36 = 0;
  *(_QWORD *)&SemaphoreAttributes.nLength = 24;
  *(_QWORD *)&SemaphoreAttributes.bInheritHandle = 0;
  hMem = 0;
  memset_0(Name, 0, 0x208u);
  memset_0(TimerName, 0, 0x208u);
  SemaphoreAttributes.lpSecurityDescriptor = &v35.Owner;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  DueTime.QuadPart = (LONGLONG)this + 24;
  if ( *((_BYTE *)this + 64) )
    goto LABEL_45;
  v4 = 260;
  v5 = 260;
  if ( a2 )
  {
    if ( (int)StringCchPrintfW(Name, 0x104u, L"Global\\%lsSemaphore", a2) < 0
      || (int)StringCchPrintfW(TimerName, 0x104u, L"Global\\%lsTimer", a2) < 0 )
    {
LABEL_10:
      v12 = 14;
      goto LABEL_46;
    }
  }
  else
  {
    v6 = 2147483646;
    v7 = 2147483646;
    v8 = L"Global\\AmiUtcThrottlingSemaphore";
    v9 = Name;
    do
    {
      if ( !v7 )
        break;
      v10 = *v8;
      if ( !*v8 )
        break;
      ++v8;
      *v9++ = v10;
      --v7;
      --v5;
    }
    while ( v5 );
    v11 = v9 - 1;
    if ( v5 )
      v11 = v9;
    *v11 = 0;
    if ( !v5 )
      goto LABEL_10;
    v13 = L"Global\\AmiUtcThrottlingTimer2";
    v14 = TimerName;
    do
    {
      if ( !v6 )
        break;
      v15 = *v13;
      if ( !*v13 )
        break;
      ++v13;
      *v14++ = v15;
      --v6;
      --v4;
    }
    while ( v4 );
    v16 = (UtcThrottle *)(v14 - 1);
    if ( v4 )
      v16 = (UtcThrottle *)v14;
    *(_WORD *)v16 = 0;
    if ( !v4 )
      goto LABEL_10;
  }
  LastError = UtcThrottle::InitializeSecurityDesc(v16, (struct _SECURITY_DESCRIPTOR *)&v35.Owner, (struct _ACL **)&hMem);
  v12 = LastError;
  if ( LastError )
  {
    v18 = "Failed to initialize security descriptor [%d]";
    v19 = 123;
LABEL_23:
    LODWORD(lpArgToCompletionRoutine) = LastError;
    AslLogCallPrintf(1, "UtcThrottle::Initialize", v19, v18, lpArgToCompletionRoutine);
    goto LABEL_46;
  }
  if ( !*((_QWORD *)this + 2) )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 2) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v12 = LastError;
      v18 = "Failed to create event [%d]";
      v19 = 133;
      goto LABEL_23;
    }
  }
  if ( !*(_QWORD *)this )
  {
    v21 = CreateSemaphoreW(&SemaphoreAttributes, 20, 20, Name);
    *(_QWORD *)this = v21;
    if ( !v21 )
    {
      v22 = GetLastError();
      AslLogCallPrintf(3, "UtcThrottle::Initialize", 144, "Failed to create named semaphore [%d]", v22);
      v23 = CreateSemaphoreW(&SemaphoreAttributes, 20, 20, 0);
      *(_QWORD *)this = v23;
      if ( !v23 )
      {
        LastError = GetLastError();
        v18 = "Failed to create semaphore [%d]";
        v19 = 150;
LABEL_31:
        v12 = LastError;
        goto LABEL_23;
      }
    }
  }
  if ( *((_QWORD *)this + 1) )
    goto LABEL_44;
  v24 = CreateWaitableTimerW(&SemaphoreAttributes, 0, TimerName);
  *((_QWORD *)this + 1) = v24;
  if ( v24 )
  {
LABEL_42:
    DueTime.QuadPart = -10000000;
    if ( !SetWaitableTimer(v24, &DueTime, 0, 0, 0, 0) )
    {
      CloseHandle(*((HANDLE *)this + 1));
      *((_QWORD *)this + 1) = 0;
    }
    goto LABEL_44;
  }
  v25 = GetLastError();
  v26 = 183;
  if ( v25 == 183 )
  {
    v27 = OpenWaitableTimerW(0x100000u, 0, TimerName);
    *((_QWORD *)this + 1) = v27;
    if ( v27 )
      goto LABEL_39;
    v25 = GetLastError();
    v28 = "Failed to open named timer [%d]";
    v26 = 178;
    v29 = 1;
  }
  else
  {
    v28 = "Failed to create named timer [%d]";
    v29 = 3;
  }
  LODWORD(lpArgToCompletionRoutine) = v25;
  AslLogCallPrintf(v29, "UtcThrottle::Initialize", v26, v28, lpArgToCompletionRoutine);
LABEL_39:
  if ( !*((_QWORD *)this + 1) )
  {
    v24 = CreateWaitableTimerW(&SemaphoreAttributes, 0, 0);
    *((_QWORD *)this + 1) = v24;
    if ( !v24 )
    {
      LastError = GetLastError();
      v18 = "Failed to create timer [%d]";
      v19 = 197;
      goto LABEL_31;
    }
    goto LABEL_42;
  }
LABEL_44:
  *((_BYTE *)this + 64) = 1;
LABEL_45:
  v12 = 0;
LABEL_46:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( this != (UtcThrottle *)-24LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  return v12;
}

```

## disassembly

```asm
0x180028a24  mov     rax, rsp
0x180028a27  push    rbp
0x180028a28  push    rdi
0x180028a29  push    r12
0x180028a2b  push    r14
0x180028a2d  push    r15
0x180028a2f  lea     rbp, [rax-3E8h]
0x180028a36  sub     rsp, 4C0h
0x180028a3d  mov     qword ptr [rsp+4E0h+var_488.Revision], 0FFFFFFFFFFFFFFFEh
0x180028a46  mov     [rax+18h], rbx
0x180028a4a  mov     [rax+20h], rsi
0x180028a4e  mov     rax, cs:__security_cookie
0x180028a55  xor     rax, rsp
0x180028a58  mov     [rbp+3E0h+var_30], rax
0x180028a5f  mov     rsi, rdx
0x180028a62  mov     rdi, rcx
0x180028a65  xorps   xmm0, xmm0
0x180028a68  xor     eax, eax
0x180028a6a  movups  xmmword ptr [rsp+4E0h+var_488.Owner], xmm0
0x180028a6f  movups  xmmword ptr [rsp+4E0h+var_488.Sacl], xmm0
0x180028a74  mov     [rbp+3E0h+var_460], rax
0x180028a78  xor     r15d, r15d
0x180028a7b  mov     qword ptr [rsp+4E0h+SemaphoreAttributes.nLength], 18h
0x180028a84  mov     qword ptr [rsp+4E0h+SemaphoreAttributes.bInheritHandle], r15
0x180028a89  mov     [rsp+4E0h+hMem], r15
0x180028a8e  mov     ebx, 208h
0x180028a93  mov     r8d, ebx; Size
0x180028a96  xor     edx, edx; Val
0x180028a98  lea     rcx, [rbp+3E0h+Name]; void *
0x180028a9f  call    memset_0
0x180028aa4  mov     r8d, ebx; Size
0x180028aa7  xor     edx, edx; Val
0x180028aa9  lea     rcx, [rbp+3E0h+TimerName]; void *
0x180028aad  call    memset_0
0x180028ab2  lea     rax, [rsp+4E0h+var_488.Owner]
0x180028ab7  mov     [rsp+4E0h+SemaphoreAttributes.lpSecurityDescriptor], rax
0x180028abc  lea     r14, [rdi+18h]
0x180028ac0  mov     rcx, r14; lpCriticalSection
0x180028ac3  call    cs:__imp_EnterCriticalSection
0x180028ac9  mov     qword ptr [rsp+4E0h+DueTime], r14
0x180028ace  cmp     [rdi+40h], r15b
0x180028ad2  jnz     loc_180028DA3
0x180028ad8  lea     r12d, [r15+1]
0x180028adc  mov     ebx, 104h
0x180028ae1  mov     edx, ebx; unsigned __int64
0x180028ae3  test    rsi, rsi
0x180028ae6  jnz     loc_180028B7F
0x180028aec  mov     r8d, 7FFFFFFEh
0x180028af2  mov     ecx, r8d
0x180028af5  lea     r9, aGlobalAmiutcth_0; "Global\\AmiUtcThrottlingSemaphore"
0x180028afc  lea     rax, [rbp+3E0h+Name]
0x180028b03  test    rcx, rcx
0x180028b06  jz      short loc_180028B26
0x180028b08  movzx   r10d, word ptr [r9]
0x180028b0c  test    r10w, r10w
0x180028b10  jz      short loc_180028B26
0x180028b12  add     r9, 2
0x180028b16  mov     [rax], r10w
0x180028b1a  add     rax, 2
0x180028b1e  sub     rcx, r12
0x180028b21  sub     rdx, r12
0x180028b24  jnz     short loc_180028B03
0x180028b26  lea     rcx, [rax-2]
0x180028b2a  test    rdx, rdx
0x180028b2d  cmovnz  rcx, rax
0x180028b31  mov     [rcx], r15w
0x180028b35  jnz     short loc_180028B41
0x180028b37  mov     ebx, 0Eh
0x180028b3c  jmp     loc_180028DA6
0x180028b41  lea     rcx, aGlobalAmiutcth; "Global\\AmiUtcThrottlingTimer2"
0x180028b48  lea     rax, [rbp+3E0h+TimerName]
0x180028b4c  test    r8, r8
0x180028b4f  jz      short loc_180028B6C
0x180028b51  movzx   edx, word ptr [rcx]
0x180028b54  test    dx, dx
0x180028b57  jz      short loc_180028B6C
0x180028b59  add     rcx, 2
0x180028b5d  mov     [rax], dx
0x180028b60  add     rax, 2
0x180028b64  sub     r8, r12
0x180028b67  sub     rbx, r12
0x180028b6a  jnz     short loc_180028B4C
0x180028b6c  lea     rcx, [rax-2]
0x180028b70  test    rbx, rbx
0x180028b73  cmovnz  rcx, rax
0x180028b77  mov     [rcx], r15w
0x180028b7b  jnz     short loc_180028BB3
0x180028b7d  jmp     short loc_180028B37
0x180028b7f  mov     r9, rsi
0x180028b82  lea     r8, aGlobalLssemaph; "Global\\%lsSemaphore"
0x180028b89  lea     rcx, [rbp+3E0h+Name]; unsigned __int16 *
0x180028b90  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028b95  test    eax, eax
0x180028b97  js      short loc_180028B37
0x180028b99  mov     r9, rsi
0x180028b9c  lea     r8, aGlobalLstimer; "Global\\%lsTimer"
0x180028ba3  mov     rdx, rbx; unsigned __int64
0x180028ba6  lea     rcx, [rbp+3E0h+TimerName]; unsigned __int16 *
0x180028baa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028baf  test    eax, eax
0x180028bb1  js      short loc_180028B37
0x180028bb3  lea     r8, [rsp+4E0h+hMem]; struct _ACL **
0x180028bb8  lea     rdx, [rsp+4E0h+var_488.Owner]; struct _SECURITY_DESCRIPTOR *
0x180028bbd  call    ?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z; UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)
0x180028bc2  mov     ebx, eax
0x180028bc4  test    eax, eax
0x180028bc6  jz      short loc_180028BED
0x180028bc8  lea     r9, aFailedToInitia_0; "Failed to initialize security descripto"...
0x180028bcf  mov     r8d, 7Bh ; '{'
0x180028bd5  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x180028bdc  mov     dword ptr [rsp+4E0h+lpArgToCompletionRoutine], eax
0x180028be0  mov     ecx, r12d
0x180028be3  call    AslLogCallPrintf
0x180028be8  jmp     loc_180028DA6
0x180028bed  cmp     [rdi+10h], r15
0x180028bf1  jnz     short loc_180028C24
0x180028bf3  xor     r9d, r9d; lpName
0x180028bf6  xor     r8d, r8d; bInitialState
0x180028bf9  mov     edx, r12d; bManualReset
0x180028bfc  xor     ecx, ecx; lpEventAttributes
0x180028bfe  call    cs:__imp_CreateEventW
0x180028c04  mov     [rdi+10h], rax
0x180028c08  test    rax, rax
0x180028c0b  jnz     short loc_180028C24
0x180028c0d  call    cs:__imp_GetLastError
0x180028c13  mov     ebx, eax
0x180028c15  lea     r9, aFailedToCreate_37; "Failed to create event [%d]"
0x180028c1c  mov     r8d, 85h
0x180028c22  jmp     short loc_180028BD5
0x180028c24  lea     rsi, aUtcthrottleIni; "UtcThrottle::Initialize"
0x180028c2b  cmp     [rdi], r15
0x180028c2e  jnz     short loc_180028CAC
0x180028c30  lea     r9, [rbp+3E0h+Name]; lpName
0x180028c37  mov     ebx, 14h
0x180028c3c  mov     r8d, ebx; lMaximumCount
0x180028c3f  mov     edx, ebx; lInitialCount
0x180028c41  lea     rcx, [rsp+4E0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x180028c46  call    cs:__imp_CreateSemaphoreW
0x180028c4c  mov     [rdi], rax
0x180028c4f  test    rax, rax
0x180028c52  jnz     short loc_180028CAC
0x180028c54  call    cs:__imp_GetLastError
0x180028c5a  mov     dword ptr [rsp+4E0h+lpArgToCompletionRoutine], eax
0x180028c5e  lea     r9, aFailedToCreate_51; "Failed to create named semaphore [%d]"
0x180028c65  lea     r8d, [rbx+7Ch]
0x180028c69  mov     rdx, rsi
0x180028c6c  lea     ecx, [rbx-11h]
0x180028c6f  call    AslLogCallPrintf
0x180028c74  xor     r9d, r9d; lpName
0x180028c77  mov     r8d, ebx; lMaximumCount
0x180028c7a  mov     edx, ebx; lInitialCount
0x180028c7c  lea     rcx, [rsp+4E0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x180028c81  call    cs:__imp_CreateSemaphoreW
0x180028c87  mov     [rdi], rax
0x180028c8a  test    rax, rax
0x180028c8d  jnz     short loc_180028CAC
0x180028c8f  call    cs:__imp_GetLastError
0x180028c95  lea     r9, aFailedToCreate_47; "Failed to create semaphore [%d]"
0x180028c9c  mov     r8d, 96h
0x180028ca2  mov     ebx, eax
0x180028ca4  mov     rdx, rsi
0x180028ca7  jmp     loc_180028BDC
0x180028cac  cmp     [rdi+8], r15
0x180028cb0  jnz     loc_180028D9F
0x180028cb6  lea     r8, [rbp+3E0h+TimerName]; lpTimerName
0x180028cba  xor     edx, edx; bManualReset
0x180028cbc  lea     rcx, [rsp+4E0h+SemaphoreAttributes]; lpTimerAttributes
0x180028cc1  call    cs:__imp_CreateWaitableTimerW
0x180028cc7  mov     [rdi+8], rax
0x180028ccb  test    rax, rax
0x180028cce  jnz     loc_180028D66
0x180028cd4  call    cs:__imp_GetLastError
0x180028cda  mov     r8d, 0B7h
0x180028ce0  cmp     eax, r8d
0x180028ce3  jnz     short loc_180028D17
0x180028ce5  lea     r8, [rbp+3E0h+TimerName]; lpTimerName
0x180028ce9  xor     edx, edx; bInheritHandle
0x180028ceb  mov     ecx, 100000h; dwDesiredAccess
0x180028cf0  call    cs:__imp_OpenWaitableTimerW
0x180028cf6  mov     [rdi+8], rax
0x180028cfa  test    rax, rax
0x180028cfd  jnz     short loc_180028D2F
0x180028cff  call    cs:__imp_GetLastError
0x180028d05  lea     r9, aFailedToOpenNa; "Failed to open named timer [%d]"
0x180028d0c  mov     r8d, 0B2h
0x180028d12  mov     ecx, r12d
0x180028d15  jmp     short loc_180028D23
0x180028d17  lea     r9, aFailedToCreate_60; "Failed to create named timer [%d]"
0x180028d1e  mov     ecx, 3
0x180028d23  mov     dword ptr [rsp+4E0h+lpArgToCompletionRoutine], eax
0x180028d27  mov     rdx, rsi
0x180028d2a  call    AslLogCallPrintf
0x180028d2f  cmp     [rdi+8], r15
0x180028d33  jnz     short loc_180028D9F
0x180028d35  xor     r8d, r8d; lpTimerName
0x180028d38  xor     edx, edx; bManualReset
0x180028d3a  lea     rcx, [rsp+4E0h+SemaphoreAttributes]; lpTimerAttributes
0x180028d3f  call    cs:__imp_CreateWaitableTimerW
0x180028d45  mov     [rdi+8], rax
0x180028d49  test    rax, rax
0x180028d4c  jnz     short loc_180028D66
0x180028d4e  call    cs:__imp_GetLastError
0x180028d54  lea     r9, aFailedToCreate_23; "Failed to create timer [%d]"
0x180028d5b  mov     r8d, 0C5h
0x180028d61  jmp     loc_180028CA2
0x180028d66  mov     qword ptr [rsp+4E0h+DueTime], 0FFFFFFFFFF676980h
0x180028d6f  mov     [rsp+4E0h+fResume], r15d; fResume
0x180028d74  mov     [rsp+4E0h+lpArgToCompletionRoutine], r15; lpArgToCompletionRoutine
0x180028d79  xor     r9d, r9d; pfnCompletionRoutine
0x180028d7c  xor     r8d, r8d; lPeriod
0x180028d7f  lea     rdx, [rsp+4E0h+DueTime]; lpDueTime
0x180028d84  mov     rcx, rax; hTimer
0x180028d87  call    cs:__imp_SetWaitableTimer
0x180028d8d  test    eax, eax
0x180028d8f  jnz     short loc_180028D9F
0x180028d91  mov     rcx, [rdi+8]; hObject
0x180028d95  call    cs:__imp_CloseHandle
0x180028d9b  mov     [rdi+8], r15
0x180028d9f  mov     [rdi+40h], r12b
0x180028da3  mov     ebx, r15d
0x180028da6  mov     rcx, [rsp+4E0h+hMem]; hMem
0x180028dab  test    rcx, rcx
0x180028dae  jz      short loc_180028DBB
0x180028db0  call    cs:__imp_LocalFree
0x180028db6  mov     [rsp+4E0h+hMem], r15
0x180028dbb  test    r14, r14
0x180028dbe  jz      short loc_180028DC9
0x180028dc0  mov     rcx, r14; lpCriticalSection
0x180028dc3  call    cs:__imp_LeaveCriticalSection
0x180028dc9  mov     eax, ebx
0x180028dcb  mov     rcx, [rbp+3E0h+var_30]
0x180028dd2  xor     rcx, rsp; StackCookie
0x180028dd5  call    __security_check_cookie
0x180028dda  lea     r11, [rsp+4E0h+var_20]
0x180028de2  mov     rbx, [r11+40h]
0x180028de6  mov     rsi, [r11+48h]
0x180028dea  mov     rsp, r11
0x180028ded  pop     r15
0x180028def  pop     r14
0x180028df1  pop     r12
0x180028df3  pop     rdi
0x180028df4  pop     rbp
0x180028df5  retn
```
