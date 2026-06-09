# Execution::BmWorkItem::StartActivity(void *,ushort const *,ulong,ulong)

- ea: `0x18006eda0`
- end: `0x18006f3e4`
- name: `?StartActivity@BmWorkItem@Execution@@QEAAJPEAXPEBGKK@Z`
- size: `1604`
- prototype: `__int64 __usercall@<rax>(Execution::BmWorkItem *__hidden this@<rcx>, void *@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023480`

## callees

- `0x1800207dc`
- `0x1800432e8`
- `0x180043f08`
- `0x18004de88`
- `0x1800682d4`
- `0x18006ad3c`
- `0x18006eda0`
- `0x18009467a`
- `0x1800946a0`
- `0x180095010`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x18006f0fa`
- `ntdll!NtOpenProcessToken` at `0x18006f0fa`
- `ntdll!NtOpenProcess` at `0x18006f0d6`
- `ntdll!NtOpenProcess` at `0x18006f0d6`
- `ntdll!NtClose` at `0x18006f128`
- `ntdll!NtClose` at `0x18006f394`
- `ntdll!NtClose` at `0x18006f3a3`
- `ntdll!NtClose` at `0x18006f128`
- `ntdll!NtClose` at `0x18006f394`
- `ntdll!NtClose` at `0x18006f3a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006ee3f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006ee3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006ef75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006f06a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006f3b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006ef75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006f06a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006f3b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006f32d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006f32d`
- `RMCLIENT!HamCloseActivity` at `0x18006f2ea`
- `RMCLIENT!HamCloseActivity` at `0x18006f2ea`
- `RMCLIENT!HamCreateActivityEx` at `0x18006f15c`
- `RMCLIENT!HamCreateActivityEx` at `0x18006f15c`
- `RMCLIENT!HamStartActivityAsync` at `0x18006f220`
- `RMCLIENT!HamStartActivityAsync` at `0x18006f220`

## string_xrefs

- `0x18006f047`: `Start Activity already pending for work item {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}`
- `0x18006f1ef`: `Unable to create HAM activity for {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}`

## pseudocode

```c
__int64 __fastcall Execution::BmWorkItem::StartActivity(
        Execution::BmWorkItem *this,
        void *a2,
        unsigned __int16 *a3,
        int a4,
        unsigned int a5)
{
  void *v7; // rsi
  __int64 v9; // rdx
  const char *v10; // rax
  int v12; // ebx
  int v13; // eax
  int v14; // r12d
  NTSTATUS Policy; // r12d
  __int64 v16; // rdx
  void *v17; // rax
  unsigned __int64 *v18; // rdi
  int Activity; // eax
  int started; // eax
  unsigned __int64 v21; // rdi
  unsigned int v22; // esi
  unsigned __int64 v23; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  char *v25; // [rsp+28h] [rbp-E8h]
  char *v26; // [rsp+28h] [rbp-E8h]
  int v27; // [rsp+30h] [rbp-E0h]
  int v28; // [rsp+38h] [rbp-D8h]
  int v29; // [rsp+40h] [rbp-D0h]
  int v30; // [rsp+48h] [rbp-C8h]
  int v31; // [rsp+50h] [rbp-C0h]
  int v32; // [rsp+58h] [rbp-B8h]
  int v33; // [rsp+60h] [rbp-B0h]
  int v34; // [rsp+68h] [rbp-A8h]
  int v35; // [rsp+70h] [rbp-A0h]
  int v36; // [rsp+78h] [rbp-98h]
  void *ProcessHandle; // [rsp+90h] [rbp-80h] BYREF
  int v38; // [rsp+98h] [rbp-78h] BYREF
  int v39; // [rsp+9Ch] [rbp-74h]
  int v40; // [rsp+A0h] [rbp-70h]
  void *TokenHandle; // [rsp+A8h] [rbp-68h] BYREF
  void *v42; // [rsp+B0h] [rbp-60h]
  unsigned __int16 *v43; // [rsp+B8h] [rbp-58h]
  _CLIENT_ID ClientId; // [rsp+C0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-40h] BYREF
  _BYTE v46[400]; // [rsp+100h] [rbp-10h] BYREF
  _BYTE v47[560]; // [rsp+290h] [rbp+180h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+3F8h]

  v43 = a3;
  v7 = a2;
  v42 = a2;
  v40 = a4;
  memset_0(v47, 0, 0x228u);
  memset_0(v46, 0, 0x188u);
  v38 = 0;
  ClientId = 0;
  ProcessHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  TokenHandle = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this + 14);
  if ( !*((_QWORD *)this + 20) )
  {
    v36 = *((unsigned __int8 *)this + 47);
    v35 = *((unsigned __int8 *)this + 46);
    v9 = 1547;
    v34 = *((unsigned __int8 *)this + 45);
    v33 = *((unsigned __int8 *)this + 44);
    v32 = *((unsigned __int8 *)this + 43);
    v31 = *((unsigned __int8 *)this + 42);
    v30 = *((unsigned __int8 *)this + 41);
    v29 = *((unsigned __int8 *)this + 40);
    v28 = *((unsigned __int16 *)this + 19);
    v27 = *((unsigned __int16 *)this + 18);
    LODWORD(v25) = *((_DWORD *)this + 8);
    v10 = "Host info object is not present for work item {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}";
LABEL_6:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\lib\\bmworkitem.cpp",
      (const char *)0x8000FFFFLL,
      (int)v10,
      v25,
      v27,
      v28,
      v29,
      v30,
      v31,
      v32,
      v33,
      v34,
      v35,
      v36);
    if ( this != (Execution::BmWorkItem *)-112LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 14);
    return 2147549183LL;
  }
  if ( a4 )
  {
    if ( *((_QWORD *)this + 24) != -1 )
    {
      v36 = *((unsigned __int8 *)this + 47);
      v35 = *((unsigned __int8 *)this + 46);
      v9 = 1559;
      v34 = *((unsigned __int8 *)this + 45);
      v33 = *((unsigned __int8 *)this + 44);
      v32 = *((unsigned __int8 *)this + 43);
      v31 = *((unsigned __int8 *)this + 42);
      v30 = *((unsigned __int8 *)this + 41);
      v29 = *((unsigned __int8 *)this + 40);
      v28 = *((unsigned __int16 *)this + 19);
      v27 = *((unsigned __int16 *)this + 18);
      LODWORD(v25) = *((_DWORD *)this + 8);
      v10 = "Another transition of HAM activity is being done for work item {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%"
            "02hhX%02hhX%02hhX%02hhX}";
      goto LABEL_6;
    }
    v12 = *((_DWORD *)this + 42);
    *((_QWORD *)this + 24) = *((_QWORD *)this + 23);
    v39 = v12;
    *((_DWORD *)this + 42) = 0;
    *((_QWORD *)this + 23) = -1;
    goto LABEL_17;
  }
  v13 = *((_DWORD *)this + 42);
  if ( v13 == 1 )
  {
    v14 = -2147483638;
    LODWORD(v25) = *((_DWORD *)this + 8);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x626,
      (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\lib\\bmworkitem.cpp",
      (const char *)0x8000000ALL,
      (int)"Start Activity already pending for work item {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
      v25,
      *((unsigned __int16 *)this + 18),
      *((unsigned __int16 *)this + 19),
      *((unsigned __int8 *)this + 40),
      *((unsigned __int8 *)this + 41),
      *((unsigned __int8 *)this + 42),
      *((unsigned __int8 *)this + 43),
      *((unsigned __int8 *)this + 44),
      *((unsigned __int8 *)this + 45),
      *((unsigned __int8 *)this + 46),
      *((unsigned __int8 *)this + 47));
LABEL_38:
    if ( this != (Execution::BmWorkItem *)-112LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 14);
    return (unsigned int)v14;
  }
  if ( v13 != 3 )
  {
    v39 = 0;
LABEL_17:
    Execution::BmWorkItem::GetHamHostInfo(this, (struct _RM_PSM_HOST_INFO *)v47);
    Execution::BmWorkItem::BmpHamActivityPropertiesInitialize(this, a3, (struct _HAM_ACTIVITY_PROPERTIES *)v46);
    if ( !a5 )
      goto LABEL_24;
    ClientId.UniqueThread = 0;
    ClientId.UniqueProcess = (HANDLE)a5;
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Policy = NtOpenProcess(&ProcessHandle, 0x1001u, &ObjectAttributes, &ClientId);
    if ( Policy < 0
      || (Policy = NtOpenProcessToken(ProcessHandle, 8u, &TokenHandle), Policy < 0)
      || (Policy = AppModelPolicy_GetPolicy(TokenHandle, v16, &v38), Policy < 0) )
    {
      v14 = Policy | 0x10000000;
      goto LABEL_30;
    }
    if ( v38 == 65537 )
    {
LABEL_24:
      v17 = ProcessHandle;
    }
    else
    {
      NtClose(ProcessHandle);
      v17 = 0;
      ProcessHandle = 0;
    }
    v18 = (unsigned __int64 *)((char *)this + 184);
    Activity = HamCreateActivityEx(v7, this, v47, v46, v17, (char *)this + 184);
    if ( Activity >= 0 )
    {
      (*(void (__fastcall **)(Execution::BmWorkItem *))(*(_QWORD *)this + 8LL))(this);
      started = HamStartActivityAsync(v7, *v18, 0, 0);
      if ( started >= 0 )
      {
        v21 = *v18;
        v22 = *((_DWORD *)this + 20);
        v23 = *(_QWORD *)(*((_QWORD *)this + 20) + 16LL);
        StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 7), 0);
        Execution::BmTraceProvider::BmTraceWorkItemActivityStarting(
          (const struct _GUID *)this + 2,
          *(void **)(*((_QWORD *)this + 6) + 16LL),
          *((_DWORD *)this + 24),
          StringRawBuffer,
          v22,
          v21,
          v43,
          a5 != 0,
          v40,
          v23);
        *((_DWORD *)this + 42) = 1;
        goto LABEL_33;
      }
      v14 = started | 0x10000000;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x687,
        (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\lib\\bmworkitem.cpp",
        (const char *)(started | 0x10000000u),
        (int)"Unable to start activity 0x%I64x work item resource set for {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02"
             "hhX%02hhX%02hhX%02hhX}",
        *((const char **)this + 23),
        *((_DWORD *)this + 8),
        *((unsigned __int16 *)this + 18),
        *((unsigned __int16 *)this + 19),
        *((unsigned __int8 *)this + 40),
        *((unsigned __int8 *)this + 41),
        *((unsigned __int8 *)this + 42),
        *((unsigned __int8 *)this + 43),
        *((unsigned __int8 *)this + 44),
        *((unsigned __int8 *)this + 45),
        *((unsigned __int8 *)this + 46),
        *((unsigned __int8 *)this + 47));
    }
    else
    {
      v14 = Activity | 0x10000000;
      LODWORD(v26) = *((_DWORD *)this + 8);
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x674,
        (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\lib\\bmworkitem.cpp",
        (const char *)(Activity | 0x10000000u),
        (int)"Unable to create HAM activity for {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
        v26,
        *((unsigned __int16 *)this + 18),
        *((unsigned __int16 *)this + 19),
        *((unsigned __int8 *)this + 40),
        *((unsigned __int8 *)this + 41),
        *((unsigned __int8 *)this + 42),
        *((unsigned __int8 *)this + 43),
        *((unsigned __int8 *)this + 44),
        *((unsigned __int8 *)this + 45),
        *((unsigned __int8 *)this + 46),
        *((unsigned __int8 *)this + 47));
    }
    v7 = v42;
LABEL_30:
    if ( v14 < 0 )
    {
      HamCloseActivity(v7);
      *((_QWORD *)this + 23) = *((_QWORD *)this + 24);
      *((_DWORD *)this + 42) = v39;
      *((_QWORD *)this + 24) = -1;
LABEL_34:
      if ( ProcessHandle )
        NtClose(ProcessHandle);
      if ( TokenHandle )
        NtClose(TokenHandle);
      goto LABEL_38;
    }
LABEL_33:
    v14 = -2147483638;
    goto LABEL_34;
  }
  if ( this != (Execution::BmWorkItem *)-112LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 14);
  return 0;
}

```

## disassembly

```asm
0x18006eda0  mov     [rsp-8+arg_18], rbx
0x18006eda5  push    rbp
0x18006eda6  push    rsi
0x18006eda7  push    rdi
0x18006eda8  push    r12
0x18006edaa  push    r13
0x18006edac  push    r14
0x18006edae  push    r15
0x18006edb0  lea     rbp, [rsp-3C0h]
0x18006edb8  sub     rsp, 4D0h
0x18006edbf  mov     rax, cs:__security_cookie
0x18006edc6  xor     rax, rsp
0x18006edc9  mov     [rbp+3F0h+var_40], rax
0x18006edd0  mov     r14d, [rbp+3F0h+arg_20]
0x18006edd7  mov     ebx, r9d
0x18006edda  mov     rdi, r8
0x18006eddd  mov     [rbp+3F0h+var_448], r8
0x18006ede1  mov     rsi, rdx
0x18006ede4  mov     [rbp+3F0h+var_450], rdx
0x18006ede8  mov     r15, rcx
0x18006edeb  mov     [rbp+3F0h+var_460], ebx
0x18006edee  xor     edx, edx; Val
0x18006edf0  lea     rcx, [rbp+3F0h+var_270]; void *
0x18006edf7  mov     r8d, 228h; Size
0x18006edfd  call    memset_0
0x18006ee02  xor     edx, edx; Val
0x18006ee04  lea     rcx, [rbp+3F0h+var_400]; void *
0x18006ee08  mov     r8d, 188h; Size
0x18006ee0e  call    memset_0
0x18006ee13  xorps   xmm1, xmm1
0x18006ee16  lea     r13, [r15+70h]
0x18006ee1a  xor     r12d, r12d
0x18006ee1d  xorps   xmm0, xmm0
0x18006ee20  mov     rcx, r13; SRWLock
0x18006ee23  mov     [rbp+3F0h+var_468], r12d
0x18006ee27  movups  xmmword ptr [rbp+3F0h+ClientId.UniqueProcess], xmm0
0x18006ee2b  mov     [rbp+3F0h+ProcessHandle], r12
0x18006ee2f  movups  xmmword ptr [rbp+3F0h+ObjectAttributes.Length], xmm1
0x18006ee33  mov     [rbp+3F0h+TokenHandle], r12
0x18006ee37  movups  xmmword ptr [rbp+3F0h+ObjectAttributes.ObjectName], xmm1
0x18006ee3b  movups  xmmword ptr [rbp+3F0h+ObjectAttributes.SecurityDescriptor], xmm1
0x18006ee3f  call    cs:__imp_AcquireSRWLockExclusive
0x18006ee45  cmp     [r15+0A0h], r12
0x18006ee4c  jnz     short loc_18006EEC6
0x18006ee4e  movzx   eax, byte ptr [r15+2Fh]
0x18006ee53  movzx   edx, byte ptr [r15+2Eh]
0x18006ee58  movzx   r8d, byte ptr [r15+2Dh]
0x18006ee5d  movzx   r9d, byte ptr [r15+2Ch]
0x18006ee62  movzx   r10d, byte ptr [r15+2Bh]
0x18006ee67  movzx   r11d, byte ptr [r15+2Ah]
0x18006ee6c  movzx   ebx, byte ptr [r15+29h]
0x18006ee71  movzx   edi, byte ptr [r15+28h]
0x18006ee76  movzx   esi, word ptr [r15+26h]
0x18006ee7b  movzx   r14d, word ptr [r15+24h]
0x18006ee80  mov     [rsp+500h+var_488], eax
0x18006ee84  mov     eax, [r15+20h]
0x18006ee88  mov     [rsp+500h+var_490], edx
0x18006ee8c  mov     edx, 60Bh
0x18006ee91  mov     [rsp+500h+var_498], r8d
0x18006ee96  mov     [rsp+500h+var_4A0], r9d
0x18006ee9b  mov     [rsp+500h+var_4A8], r10d
0x18006eea0  mov     [rsp+500h+var_4B0], r11d
0x18006eea5  mov     dword ptr [rsp+500h+var_4B8], ebx
0x18006eea9  mov     [rsp+500h+var_4C0], edi
0x18006eead  mov     [rsp+500h+var_4C8], esi
0x18006eeb1  mov     dword ptr [rsp+500h+var_4D0], r14d
0x18006eeb6  mov     dword ptr [rsp+500h+var_4D8], eax
0x18006eeba  lea     rax, aHostInfoObject; "Host info object is not present for wor"...
0x18006eec1  jmp     loc_18006EF4F
0x18006eec6  test    ebx, ebx
0x18006eec8  jz      loc_18006EFB4
0x18006eece  cmp     qword ptr [r15+0C0h], 0FFFFFFFFFFFFFFFFh
0x18006eed6  jz      loc_18006EF85
0x18006eedc  movzx   eax, byte ptr [r15+2Fh]
0x18006eee1  movzx   edx, byte ptr [r15+2Eh]
0x18006eee6  movzx   r8d, byte ptr [r15+2Dh]
0x18006eeeb  movzx   r9d, byte ptr [r15+2Ch]
0x18006eef0  movzx   r10d, byte ptr [r15+2Bh]
0x18006eef5  movzx   r11d, byte ptr [r15+2Ah]
0x18006eefa  movzx   ebx, byte ptr [r15+29h]
0x18006eeff  movzx   edi, byte ptr [r15+28h]
0x18006ef04  movzx   esi, word ptr [r15+26h]
0x18006ef09  movzx   r14d, word ptr [r15+24h]
0x18006ef0e  mov     [rsp+500h+var_488], eax
0x18006ef12  mov     eax, [r15+20h]
0x18006ef16  mov     [rsp+500h+var_490], edx
0x18006ef1a  mov     edx, 617h; void *
0x18006ef1f  mov     [rsp+500h+var_498], r8d
0x18006ef24  mov     [rsp+500h+var_4A0], r9d
0x18006ef29  mov     [rsp+500h+var_4A8], r10d
0x18006ef2e  mov     [rsp+500h+var_4B0], r11d
0x18006ef33  mov     dword ptr [rsp+500h+var_4B8], ebx
0x18006ef37  mov     [rsp+500h+var_4C0], edi
0x18006ef3b  mov     [rsp+500h+var_4C8], esi
0x18006ef3f  mov     dword ptr [rsp+500h+var_4D0], r14d
0x18006ef44  mov     dword ptr [rsp+500h+var_4D8], eax; char *
0x18006ef48  lea     rax, aAnotherTransit; "Another transition of HAM activity is b"...
0x18006ef4f  mov     rcx, [rbp+3F8h]; this
0x18006ef56  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\background\\bi\\backg"...
0x18006ef5d  mov     r9d, 8000FFFFh; char *
0x18006ef63  mov     qword ptr [rsp+500h+var_4E0], rax; int
0x18006ef68  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006ef6d  test    r13, r13
0x18006ef70  jz      short loc_18006EF7B
0x18006ef72  mov     rcx, r13; SRWLock
0x18006ef75  call    cs:__imp_ReleaseSRWLockExclusive
0x18006ef7b  mov     eax, 8000FFFFh
0x18006ef80  jmp     loc_18006F3BA
0x18006ef85  mov     rax, [r15+0B8h]
0x18006ef8c  mov     ebx, [r15+0A8h]
0x18006ef93  mov     [r15+0C0h], rax
0x18006ef9a  mov     [rbp+3F0h+var_464], ebx
0x18006ef9d  mov     [r15+0A8h], r12d
0x18006efa4  mov     qword ptr [r15+0B8h], 0FFFFFFFFFFFFFFFFh
0x18006efaf  jmp     loc_18006F07B
0x18006efb4  mov     eax, [r15+0A8h]
0x18006efbb  cmp     eax, 1
0x18006efbe  jnz     loc_18006F05D
0x18006efc4  movzx   eax, byte ptr [r15+2Fh]
0x18006efc9  mov     r12d, 8000000Ah
0x18006efcf  movzx   edx, byte ptr [r15+2Eh]
0x18006efd4  movzx   r8d, byte ptr [r15+2Dh]
0x18006efd9  movzx   r9d, byte ptr [r15+2Ch]
0x18006efde  movzx   r10d, byte ptr [r15+2Bh]
0x18006efe3  movzx   r11d, byte ptr [r15+2Ah]
0x18006efe8  movzx   ebx, byte ptr [r15+29h]
0x18006efed  movzx   edi, byte ptr [r15+28h]
0x18006eff2  movzx   esi, word ptr [r15+26h]
0x18006eff7  movzx   r14d, word ptr [r15+24h]
0x18006effc  mov     rcx, [rbp+3F8h]; this
0x18006f003  mov     [rsp+500h+var_488], eax
0x18006f007  mov     eax, [r15+20h]
0x18006f00b  mov     [rsp+500h+var_490], edx
0x18006f00f  mov     edx, 626h; void *
0x18006f014  mov     [rsp+500h+var_498], r8d
0x18006f019  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\background\\bi\\backg"...
0x18006f020  mov     [rsp+500h+var_4A0], r9d
0x18006f025  mov     r9d, r12d; char *
0x18006f028  mov     [rsp+500h+var_4A8], r10d
0x18006f02d  mov     [rsp+500h+var_4B0], r11d
0x18006f032  mov     dword ptr [rsp+500h+var_4B8], ebx
0x18006f036  mov     [rsp+500h+var_4C0], edi
0x18006f03a  mov     [rsp+500h+var_4C8], esi
0x18006f03e  mov     dword ptr [rsp+500h+var_4D0], r14d
0x18006f043  mov     dword ptr [rsp+500h+var_4D8], eax; char *
0x18006f047  lea     rax, aStartActivityA; "Start Activity already pending for work"...
0x18006f04e  mov     qword ptr [rsp+500h+var_4E0], rax; int
0x18006f053  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006f058  jmp     loc_18006F3A9
0x18006f05d  cmp     eax, 3
0x18006f060  jnz     short loc_18006F077
0x18006f062  test    r13, r13
0x18006f065  jz      short loc_18006F070
0x18006f067  mov     rcx, r13; SRWLock
0x18006f06a  call    cs:__imp_ReleaseSRWLockExclusive
0x18006f070  xor     eax, eax
0x18006f072  jmp     loc_18006F3BA
0x18006f077  mov     [rbp+3F0h+var_464], r12d
0x18006f07b  lea     rdx, [rbp+3F0h+var_270]; struct _RM_PSM_HOST_INFO *
0x18006f082  mov     rcx, r15; this
0x18006f085  call    ?GetHamHostInfo@BmWorkItem@Execution@@AEAAXPEAU_RM_PSM_HOST_INFO@@@Z; Execution::BmWorkItem::GetHamHostInfo(_RM_PSM_HOST_INFO *)
0x18006f08a  lea     r8, [rbp+3F0h+var_400]; struct _HAM_ACTIVITY_PROPERTIES *
0x18006f08e  mov     rdx, rdi; unsigned __int16 *
0x18006f091  mov     rcx, r15; this
0x18006f094  call    ?BmpHamActivityPropertiesInitialize@BmWorkItem@Execution@@AEAAXPEBGPEAU_HAM_ACTIVITY_PROPERTIES@@@Z; Execution::BmWorkItem::BmpHamActivityPropertiesInitialize(ushort const *,_HAM_ACTIVITY_PROPERTIES *)
0x18006f099  test    r14d, r14d
0x18006f09c  jz      loc_18006F136
0x18006f0a2  xorps   xmm0, xmm0
0x18006f0a5  mov     [rbp+3F0h+ClientId.UniqueThread], r12
0x18006f0a9  lea     r9, [rbp+3F0h+ClientId]; ClientId
0x18006f0ad  mov     [rbp+3F0h+ClientId.UniqueProcess], r14
0x18006f0b1  lea     r8, [rbp+3F0h+ObjectAttributes]; ObjectAttributes
0x18006f0b5  mov     [rbp+3F0h+ObjectAttributes.Length], 30h ; '0'
0x18006f0bc  mov     edx, 1001h; DesiredAccess
0x18006f0c1  mov     [rbp+3F0h+ObjectAttributes.RootDirectory], r12
0x18006f0c5  lea     rcx, [rbp+3F0h+ProcessHandle]; ProcessHandle
0x18006f0c9  mov     [rbp+3F0h+ObjectAttributes.Attributes], r12d
0x18006f0cd  movdqu  xmmword ptr [rbp+3F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006f0d2  mov     [rbp+3F0h+ObjectAttributes.ObjectName], r12
0x18006f0d6  call    cs:__imp_NtOpenProcess
0x18006f0dc  mov     r12d, eax
0x18006f0df  test    eax, eax
0x18006f0e1  jns     short loc_18006F0ED
0x18006f0e3  bts     r12d, 1Ch
0x18006f0e8  jmp     loc_18006F2D7
0x18006f0ed  mov     rcx, [rbp+3F0h+ProcessHandle]; ProcessHandle
0x18006f0f1  lea     r8, [rbp+3F0h+TokenHandle]; TokenHandle
0x18006f0f5  mov     edx, 8; DesiredAccess
0x18006f0fa  call    cs:__imp_NtOpenProcessToken
0x18006f100  mov     r12d, eax
0x18006f103  test    eax, eax
0x18006f105  js      short loc_18006F0E3
0x18006f107  mov     rcx, [rbp+3F0h+TokenHandle]
0x18006f10b  lea     r8, [rbp+3F0h+var_468]
0x18006f10f  call    ?AppModelPolicy_GetPolicy@@YAJPEAXW4AppModelPolicy_Type@@PEAW4AppModelPolicy_PolicyValue@@@Z; AppModelPolicy_GetPolicy(void *,AppModelPolicy_Type,AppModelPolicy_PolicyValue *)
0x18006f114  mov     r12d, eax
0x18006f117  test    eax, eax
0x18006f119  js      short loc_18006F0E3
0x18006f11b  cmp     [rbp+3F0h+var_468], 10001h
0x18006f122  jz      short loc_18006F136
0x18006f124  mov     rcx, [rbp+3F0h+ProcessHandle]; Handle
0x18006f128  call    cs:__imp_NtClose
0x18006f12e  xor     eax, eax
0x18006f130  mov     [rbp+3F0h+ProcessHandle], rax
0x18006f134  jmp     short loc_18006F13A
0x18006f136  mov     rax, [rbp+3F0h+ProcessHandle]
0x18006f13a  lea     rdi, [r15+0B8h]
0x18006f141  mov     rdx, r15
0x18006f144  mov     [rsp+500h+var_4D8], rdi
0x18006f149  lea     r9, [rbp+3F0h+var_400]
0x18006f14d  lea     r8, [rbp+3F0h+var_270]
0x18006f154  mov     qword ptr [rsp+500h+var_4E0], rax
0x18006f159  mov     rcx, rsi
0x18006f15c  call    cs:__imp_HamCreateActivityEx
0x18006f162  mov     r12d, eax
0x18006f165  test    eax, eax
0x18006f167  jns     loc_18006F205
0x18006f16d  movzx   eax, byte ptr [r15+2Fh]
0x18006f172  bts     r12d, 1Ch
0x18006f177  movzx   edx, byte ptr [r15+2Eh]
0x18006f17c  movzx   r8d, byte ptr [r15+2Dh]
0x18006f181  movzx   r9d, byte ptr [r15+2Ch]
0x18006f186  movzx   r10d, byte ptr [r15+2Bh]
0x18006f18b  movzx   r11d, byte ptr [r15+2Ah]
0x18006f190  movzx   ebx, byte ptr [r15+29h]
0x18006f195  movzx   edi, byte ptr [r15+28h]
0x18006f19a  movzx   esi, word ptr [r15+26h]
0x18006f19f  movzx   r14d, word ptr [r15+24h]
0x18006f1a4  mov     rcx, [rbp+3F8h]; this
0x18006f1ab  mov     [rsp+500h+var_488], eax
0x18006f1af  mov     eax, [r15+20h]
0x18006f1b3  mov     [rsp+500h+var_490], edx
0x18006f1b7  mov     edx, 674h; void *
0x18006f1bc  mov     [rsp+500h+var_498], r8d
0x18006f1c1  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\background\\bi\\backg"...
0x18006f1c8  mov     [rsp+500h+var_4A0], r9d
0x18006f1cd  mov     r9d, r12d; char *
0x18006f1d0  mov     [rsp+500h+var_4A8], r10d
0x18006f1d5  mov     [rsp+500h+var_4B0], r11d
0x18006f1da  mov     dword ptr [rsp+500h+var_4B8], ebx
0x18006f1de  mov     [rsp+500h+var_4C0], edi
0x18006f1e2  mov     [rsp+500h+var_4C8], esi
0x18006f1e6  mov     dword ptr [rsp+500h+var_4D0], r14d
0x18006f1eb  mov     dword ptr [rsp+500h+var_4D8], eax; char *
0x18006f1ef  lea     rax, aUnableToCreate; "Unable to create HAM activity for {%08l"...
0x18006f1f6  mov     qword ptr [rsp+500h+var_4E0], rax; int
0x18006f1fb  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006f200  jmp     loc_18006F2D3
0x18006f205  mov     rax, [r15]
0x18006f208  mov     rcx, r15
0x18006f20b  mov     rax, [rax+8]
0x18006f20f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f214  mov     rdx, [rdi]
0x18006f217  xor     r9d, r9d
0x18006f21a  xor     r8d, r8d
0x18006f21d  mov     rcx, rsi
0x18006f220  call    cs:__imp_HamStartActivityAsync
0x18006f226  mov     r12d, eax
0x18006f229  test    eax, eax
0x18006f22b  jns     loc_18006F315
0x18006f231  movzx   eax, byte ptr [r15+2Fh]
0x18006f236  bts     r12d, 1Ch
0x18006f23b  movzx   edx, byte ptr [r15+2Eh]
0x18006f240  movzx   r8d, byte ptr [r15+2Dh]
0x18006f245  movzx   r9d, byte ptr [r15+2Ch]
0x18006f24a  movzx   r10d, byte ptr [r15+2Bh]
0x18006f24f  movzx   r11d, byte ptr [r15+2Ah]
0x18006f254  movzx   ebx, byte ptr [r15+29h]
0x18006f259  movzx   edi, byte ptr [r15+28h]
0x18006f25e  movzx   esi, word ptr [r15+26h]
0x18006f263  movzx   r14d, word ptr [r15+24h]
0x18006f268  mov     rcx, [rbp+3F8h]; this
0x18006f26f  mov     [rsp+500h+var_480], eax
0x18006f276  mov     eax, [r15+20h]
0x18006f27a  mov     [rsp+500h+var_488], edx
0x18006f27e  mov     edx, 687h; void *
0x18006f283  mov     [rsp+500h+var_490], r8d
0x18006f288  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\background\\bi\\backg"...
0x18006f28f  mov     [rsp+500h+var_498], r9d
0x18006f294  mov     r9d, r12d; char *
0x18006f297  mov     [rsp+500h+var_4A0], r10d
0x18006f29c  mov     [rsp+500h+var_4A8], r11d
0x18006f2a1  mov     [rsp+500h+var_4B0], ebx
0x18006f2a5  mov     dword ptr [rsp+500h+var_4B8], edi
0x18006f2a9  mov     [rsp+500h+var_4C0], esi
0x18006f2ad  mov     [rsp+500h+var_4C8], r14d
0x18006f2b2  mov     dword ptr [rsp+500h+var_4D0], eax
0x18006f2b6  mov     rax, [r15+0B8h]
0x18006f2bd  mov     [rsp+500h+var_4D8], rax; char *
0x18006f2c2  lea     rax, aUnableToStartA; "Unable to start activity 0x%I64x work i"...
0x18006f2c9  mov     qword ptr [rsp+500h+var_4E0], rax; int
0x18006f2ce  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18006f2d3  mov     rsi, [rbp+3F0h+var_450]
0x18006f2d7  test    r12d, r12d
0x18006f2da  jns     loc_18006F385
0x18006f2e0  mov     rdx, [r15+0B8h]
0x18006f2e7  mov     rcx, rsi
0x18006f2ea  call    cs:__imp_HamCloseActivity
0x18006f2f0  mov     rax, [r15+0C0h]
0x18006f2f7  mov     [r15+0B8h], rax
  ... truncated ...
```
