# ProvHostManager::Initialize(CRequestContext *,CSoapProcessor *)

- ea: `0x1800eff94`
- end: `0x1800f03b7`
- name: `?Initialize@ProvHostManager@@QEAAHPEAVCRequestContext@@PEAVCSoapProcessor@@@Z`
- size: `1059`
- prototype: `__int64 __fastcall(ProvHostManager *__hidden this, struct CRequestContext *, struct CSoapProcessor *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180173484`

## callees

- `0x180019950`
- `0x18002dd80`
- `0x180064250`
- `0x180076d18`
- `0x1800973c0`
- `0x1800eff94`
- `0x180111270`
- `0x180112380`
- `0x1801123a8`
- `0x1801653d0`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f02f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0103`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f0176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f02f5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800f00ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800f00ae`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f0300`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f0300`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f00e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f0158`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f00e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800f0158`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800f02e6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800f02e6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f004a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f004a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProvHostManager::Initialize(
        ProvHostManager *this,
        struct CRequestContext *a2,
        struct CSoapProcessor *a3)
{
  unsigned int v6; // r14d
  __int64 v7; // rbx
  PSECURITY_DESCRIPTOR v8; // rcx
  HANDLE v10; // rax
  __int64 LastError; // rbx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  HANDLE EventW; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  HANDLE Thread; // rax
  DWORD v18; // ebx
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+30h] [rbp-20h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+80h] [rbp+30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+98h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
  *(_DWORD *)this = 0;
  *(_QWORD *)((char *)this + 164) = *(_QWORD *)L"Global\\";
  *((_DWORD *)this + 43) = *(_DWORD *)L"al\\";
  *((_WORD *)this + 88) = aGlobal[6];
  WSManCreateUuidString((unsigned __int16 *const)this + 89);
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  v6 = 1;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:P(A;;GA;;;S-1-5-80-569256582-2953403351-2909559716-1301513147-412116970)(A;;GX;;;AU)",
         1u,
         &SecurityDescriptor,
         &SecurityDescriptorSize) )
  {
    *(&EventAttributes.nLength + 1) = 0;
    *(_QWORD *)&EventAttributes.bInheritHandle = 0;
    EventAttributes.nLength = SecurityDescriptorSize;
    EventAttributes.lpSecurityDescriptor = SecurityDescriptor;
    v10 = CreateEventW(&EventAttributes, 1, 0, (LPCWSTR)this + 82);
    AutoHandle::operator=((char *)this + 256, v10);
    if ( !*((_QWORD *)this + 32) )
    {
      LastError = GetLastError();
      (*(void (__fastcall **)(struct CRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, LastError);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_33;
      v13 = 16;
      goto LABEL_32;
    }
    EventW = CreateEventW(0, 1, 0, 0);
    AutoHandle::operator=((char *)this + 264, EventW);
    if ( !*((_QWORD *)this + 33) )
    {
      LastError = GetLastError();
      (*(void (__fastcall **)(struct CRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, LastError);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_33;
      v13 = 17;
      goto LABEL_32;
    }
    if ( (unsigned int)HostMappingTable::Initialize((ProvHostManager *)((char *)this + 32), a2, this) )
    {
      if ( (unsigned int)CWSManCriticalSection::IsValid((ProvHostManager *)((char *)this + 112)) )
      {
        LODWORD(LastError) = (*(__int64 (__fastcall **)(void *))(ComLifetime_Thread::s_lifetimeThread + 8LL))(&ComLifetime_Thread::s_lifetimeThread);
        if ( !(_DWORD)LastError )
        {
          *((_QWORD *)this + 2) = (char *)a3 + 32;
          *((_QWORD *)this + 3) = a3;
          Thread = CreateThread(0, 0, ProvHostManager::AutoRestartPluginsOnStartup, this, 0, 0);
          *((_QWORD *)this + 1) = Thread;
          if ( !Thread )
          {
            v18 = GetLastError();
            SetEvent(*((HANDLE *)this + 33));
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids, v18);
            if ( WSMan::EventHandler::IsEventEnabled(&LOG_WSMAN_OP_AUTORESTART_FAILED) )
              WSMan::LogEvent<long>((struct _EVENT_DESCRIPTOR *)&LOG_WSMAN_OP_AUTORESTART_FAILED);
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
          *((_DWORD *)this + 68) = 1;
          goto LABEL_44;
        }
        (*(void (__fastcall **)(struct CRequestContext *, _QWORD))(*(_QWORD *)a2 + 72LL))(a2, (unsigned int)LastError);
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
        {
          v13 = 20;
LABEL_32:
          WPP_SF_d(v12[2], v13, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids, (unsigned int)LastError);
        }
LABEL_33:
        v6 = 0;
LABEL_44:
        AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(&SecurityDescriptor);
        return v6;
      }
      (*(void (__fastcall **)(struct CRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, 14);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_33;
      v16 = 19;
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 )
        goto LABEL_33;
      v16 = 18;
    }
    WPP_SF_(v15[2], v16, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids);
    goto LABEL_33;
  }
  v7 = GetLastError();
  (*(void (__fastcall **)(struct CRequestContext *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v7);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids, (unsigned int)v7);
  v8 = SecurityDescriptor;
  SecurityDescriptor = 0;
  if ( v8 )
    LocalFree(v8);
  return 0;
}

```

## disassembly

```asm
0x1800eff94  mov     [rsp-28h+arg_8], rbx
0x1800eff99  mov     [rsp-28h+arg_10], rsi
0x1800eff9e  push    rbp
0x1800eff9f  push    rdi
0x1800effa0  push    r13
0x1800effa2  push    r14
0x1800effa4  push    r15
0x1800effa6  mov     rbp, rsp
0x1800effa9  sub     rsp, 50h
0x1800effad  mov     r13, r8
0x1800effb0  mov     rdi, rdx
0x1800effb3  mov     rsi, rcx
0x1800effb6  lea     rax, WPP_GLOBAL_Control
0x1800effbd  lea     r15, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x1800effc4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800effcb  cmp     rcx, rax
0x1800effce  jz      short loc_1800EFFEA
0x1800effd0  test    dword ptr [rcx+1Ch], 400h
0x1800effd7  jz      short loc_1800EFFEA
0x1800effd9  mov     edx, 0Eh
0x1800effde  mov     r8, r15
0x1800effe1  mov     rcx, [rcx+10h]
0x1800effe5  call    WPP_SF_
0x1800effea  mov     dword ptr [rsi], 0
0x1800efff0  lea     rbx, [rsi+0A4h]
0x1800efff7  movsd   xmm0, qword ptr cs:aGlobal; "Global\\"
0x1800effff  movsd   qword ptr [rbx], xmm0
0x1800f0003  mov     eax, dword ptr cs:aGlobal+8; "al\\"
0x1800f0009  mov     [rbx+8], eax
0x1800f000c  movzx   eax, word ptr cs:aGlobal+0Ch; "\\"
0x1800f0013  mov     [rbx+0Ch], ax
0x1800f0017  lea     rcx, [rsi+0B2h]; unsigned __int16 *
0x1800f001e  call    ?WSManCreateUuidString@@YAXQEAG@Z; WSManCreateUuidString(ushort * const)
0x1800f0023  mov     [rbp+SecurityDescriptor], 0
0x1800f002b  mov     [rbp+SecurityDescriptorSize], 0
0x1800f0032  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800f0036  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800f003a  mov     r14d, 1
0x1800f0040  mov     edx, r14d; StringSDRevision
0x1800f0043  lea     rcx, StringSecurityDescriptor; "D:P(A;;GA;;;S-1-5-80-569256582-29534033"...
0x1800f004a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800f0050  test    eax, eax
0x1800f0052  jnz     short loc_1800F00BB
0x1800f0054  call    cs:__imp_GetLastError
0x1800f005a  mov     ebx, eax
0x1800f005c  mov     rcx, [rdi]
0x1800f005f  mov     rax, [rcx+48h]
0x1800f0063  mov     edx, ebx
0x1800f0065  mov     rcx, rdi
0x1800f0068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f006d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0074  lea     rdi, WPP_GLOBAL_Control
0x1800f007b  cmp     rcx, rdi
0x1800f007e  jz      short loc_1800F009D
0x1800f0080  test    dword ptr [rcx+1Ch], 200h
0x1800f0087  jz      short loc_1800F009D
0x1800f0089  lea     edx, [r14+0Eh]
0x1800f008d  mov     r9d, ebx
0x1800f0090  mov     r8, r15
0x1800f0093  mov     rcx, [rcx+10h]
0x1800f0097  call    WPP_SF_d
0x1800f009c  nop
0x1800f009d  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800f00a1  mov     [rbp+SecurityDescriptor], 0
0x1800f00a9  test    rcx, rcx
0x1800f00ac  jz      short loc_1800F00B4
0x1800f00ae  call    cs:__imp_LocalFree
0x1800f00b4  xor     eax, eax
0x1800f00b6  jmp     loc_1800F039E
0x1800f00bb  mov     dword ptr [rbp+EventAttributes+4], 0
0x1800f00c2  mov     qword ptr [rbp+EventAttributes.bInheritHandle], 0
0x1800f00ca  mov     eax, [rbp+SecurityDescriptorSize]
0x1800f00cd  mov     [rbp+EventAttributes.nLength], eax
0x1800f00d0  mov     rax, [rbp+SecurityDescriptor]
0x1800f00d4  mov     [rbp+EventAttributes.lpSecurityDescriptor], rax
0x1800f00d8  mov     r9, rbx; lpName
0x1800f00db  xor     r8d, r8d; bInitialState
0x1800f00de  mov     edx, r14d; bManualReset
0x1800f00e1  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x1800f00e5  call    cs:__imp_CreateEventW
0x1800f00eb  lea     rbx, [rsi+100h]
0x1800f00f2  mov     rdx, rax
0x1800f00f5  mov     rcx, rbx
0x1800f00f8  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x1800f00fd  cmp     qword ptr [rbx], 0
0x1800f0101  jnz     short loc_1800F014D
0x1800f0103  call    cs:__imp_GetLastError
0x1800f0109  mov     ebx, eax
0x1800f010b  mov     rcx, [rdi]
0x1800f010e  mov     rax, [rcx+48h]
0x1800f0112  mov     edx, ebx
0x1800f0114  mov     rcx, rdi
0x1800f0117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f011c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0123  lea     rdi, WPP_GLOBAL_Control
0x1800f012a  cmp     rcx, rdi
0x1800f012d  jz      loc_1800F02B3
0x1800f0133  test    dword ptr [rcx+1Ch], 200h
0x1800f013a  jz      loc_1800F02B3
0x1800f0140  mov     edx, 10h
0x1800f0145  mov     r8, r15
0x1800f0148  jmp     loc_1800F02A7
0x1800f014d  xor     r9d, r9d; lpName
0x1800f0150  xor     r8d, r8d; bInitialState
0x1800f0153  mov     edx, r14d; bManualReset
0x1800f0156  xor     ecx, ecx; lpEventAttributes
0x1800f0158  call    cs:__imp_CreateEventW
0x1800f015e  lea     r15, [rsi+108h]
0x1800f0165  mov     rdx, rax
0x1800f0168  mov     rcx, r15
0x1800f016b  call    ??4AutoHandle@@QEAAAEAV0@PEAX@Z; AutoHandle::operator=(void *)
0x1800f0170  cmp     qword ptr [r15], 0
0x1800f0174  jnz     short loc_1800F01BD
0x1800f0176  call    cs:__imp_GetLastError
0x1800f017c  mov     ebx, eax
0x1800f017e  mov     rcx, [rdi]
0x1800f0181  mov     rax, [rcx+48h]
0x1800f0185  mov     edx, ebx
0x1800f0187  mov     rcx, rdi
0x1800f018a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f018f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0196  lea     rdi, WPP_GLOBAL_Control
0x1800f019d  cmp     rcx, rdi
0x1800f01a0  jz      loc_1800F02B3
0x1800f01a6  test    dword ptr [rcx+1Ch], 200h
0x1800f01ad  jz      loc_1800F02B3
0x1800f01b3  mov     edx, 11h
0x1800f01b8  jmp     loc_1800F02A0
0x1800f01bd  lea     rcx, [rsi+20h]; this
0x1800f01c1  mov     r8, rsi; struct ProvHostManager *
0x1800f01c4  mov     rdx, rdi; struct CRequestContext *
0x1800f01c7  call    ?Initialize@HostMappingTable@@QEAAHPEAVCRequestContext@@PEAVProvHostManager@@@Z; HostMappingTable::Initialize(CRequestContext *,ProvHostManager *)
0x1800f01cc  test    eax, eax
0x1800f01ce  jnz     short loc_1800F01F9
0x1800f01d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f01d7  lea     rdi, WPP_GLOBAL_Control
0x1800f01de  cmp     rcx, rdi
0x1800f01e1  jz      loc_1800F02B3
0x1800f01e7  test    dword ptr [rcx+1Ch], 200h
0x1800f01ee  jz      loc_1800F02B3
0x1800f01f4  lea     edx, [rax+12h]
0x1800f01f7  jmp     short loc_1800F023F
0x1800f01f9  lea     rcx, [rsi+70h]; this
0x1800f01fd  call    ?IsValid@CWSManCriticalSection@@QEBAHXZ; CWSManCriticalSection::IsValid(void)
0x1800f0202  test    eax, eax
0x1800f0204  jnz     short loc_1800F0251
0x1800f0206  mov     rax, [rdi]
0x1800f0209  mov     edx, 0Eh
0x1800f020e  mov     rcx, rdi
0x1800f0211  mov     rax, [rax+48h]
0x1800f0215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f021a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0221  lea     rdi, WPP_GLOBAL_Control
0x1800f0228  cmp     rcx, rdi
0x1800f022b  jz      loc_1800F02B3
0x1800f0231  test    dword ptr [rcx+1Ch], 200h
0x1800f0238  jz      short loc_1800F02B3
0x1800f023a  mov     edx, 13h
0x1800f023f  lea     r8, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x1800f0246  mov     rcx, [rcx+10h]
0x1800f024a  call    WPP_SF_
0x1800f024f  jmp     short loc_1800F02B3
0x1800f0251  mov     rax, cs:?s_lifetimeThread@ComLifetime_Thread@@0V1@A; ComLifetime_Thread ComLifetime_Thread::s_lifetimeThread
0x1800f0258  lea     rcx, ?s_lifetimeThread@ComLifetime_Thread@@0V1@A; ComLifetime_Thread ComLifetime_Thread::s_lifetimeThread
0x1800f025f  mov     rax, [rax+8]
0x1800f0263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0268  mov     ebx, eax
0x1800f026a  test    eax, eax
0x1800f026c  jz      short loc_1800F02BB
0x1800f026e  mov     rcx, [rdi]
0x1800f0271  mov     rax, [rcx+48h]
0x1800f0275  mov     edx, ebx
0x1800f0277  mov     rcx, rdi
0x1800f027a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f027f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0286  lea     rdi, WPP_GLOBAL_Control
0x1800f028d  cmp     rcx, rdi
0x1800f0290  jz      short loc_1800F02B3
0x1800f0292  test    dword ptr [rcx+1Ch], 200h
0x1800f0299  jz      short loc_1800F02B3
0x1800f029b  mov     edx, 14h
0x1800f02a0  lea     r8, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x1800f02a7  mov     r9d, ebx
0x1800f02aa  mov     rcx, [rcx+10h]
0x1800f02ae  call    WPP_SF_d
0x1800f02b3  xor     r14d, r14d
0x1800f02b6  jmp     loc_1800F0392
0x1800f02bb  lea     rax, [r13+20h]
0x1800f02bf  mov     [rsi+10h], rax
0x1800f02c3  mov     [rsi+18h], r13
0x1800f02c7  mov     [rsp+50h+lpThreadId], 0; lpThreadId
0x1800f02d0  mov     [rsp+50h+dwCreationFlags], 0; dwCreationFlags
0x1800f02d8  mov     r9, rsi; lpParameter
0x1800f02db  lea     r8, ?AutoRestartPluginsOnStartup@ProvHostManager@@SAKPEAX@Z; lpStartAddress
0x1800f02e2  xor     edx, edx; dwStackSize
0x1800f02e4  xor     ecx, ecx; lpThreadAttributes
0x1800f02e6  call    cs:__imp_CreateThread
0x1800f02ec  mov     [rsi+8], rax
0x1800f02f0  test    rax, rax
0x1800f02f3  jnz     short loc_1800F035A
0x1800f02f5  call    cs:__imp_GetLastError
0x1800f02fb  mov     ebx, eax
0x1800f02fd  mov     rcx, [r15]; hEvent
0x1800f0300  call    cs:__imp_SetEvent
0x1800f0306  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f030d  lea     rdi, WPP_GLOBAL_Control
0x1800f0314  cmp     rcx, rdi
0x1800f0317  jz      short loc_1800F033A
0x1800f0319  test    dword ptr [rcx+1Ch], 200h
0x1800f0320  jz      short loc_1800F033A
0x1800f0322  mov     edx, 15h
0x1800f0327  mov     r9d, ebx
0x1800f032a  lea     r8, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x1800f0331  mov     rcx, [rcx+10h]
0x1800f0335  call    WPP_SF_d
0x1800f033a  lea     rcx, LOG_WSMAN_OP_AUTORESTART_FAILED; struct _EVENT_DESCRIPTOR *
0x1800f0341  call    ?IsEventEnabled@EventHandler@WSMan@@SA_NAEBU_EVENT_DESCRIPTOR@@@Z; WSMan::EventHandler::IsEventEnabled(_EVENT_DESCRIPTOR const &)
0x1800f0346  test    al, al
0x1800f0348  jz      short loc_1800F0361
0x1800f034a  mov     edx, ebx
0x1800f034c  lea     rcx, LOG_WSMAN_OP_AUTORESTART_FAILED; struct _EVENT_DESCRIPTOR *
0x1800f0353  call    ??$LogEvent@J@WSMan@@YAXAEBU_EVENT_DESCRIPTOR@@J@Z; WSMan::LogEvent<long>(_EVENT_DESCRIPTOR const &,long)
0x1800f0358  jmp     short loc_1800F0361
0x1800f035a  lea     rdi, WPP_GLOBAL_Control
0x1800f0361  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f0368  cmp     rcx, rdi
0x1800f036b  jz      short loc_1800F038B
0x1800f036d  test    dword ptr [rcx+1Ch], 400h
0x1800f0374  jz      short loc_1800F038B
0x1800f0376  mov     edx, 17h
0x1800f037b  lea     r8, WPP_c78bf4a69e83383d7167ee7fc69e79e1_Traceguids
0x1800f0382  mov     rcx, [rcx+10h]
0x1800f0386  call    WPP_SF_
0x1800f038b  mov     [rsi+110h], r14d
0x1800f0392  lea     rcx, [rbp+SecurityDescriptor]; void *
0x1800f0396  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x1800f039b  mov     eax, r14d
0x1800f039e  lea     r11, [rsp+50h+var_s0]
0x1800f03a3  mov     rbx, [r11+38h]
0x1800f03a7  mov     rsi, [r11+40h]
0x1800f03ab  mov     rsp, r11
0x1800f03ae  pop     r15
0x1800f03b0  pop     r14
0x1800f03b2  pop     r13
0x1800f03b4  pop     rdi
0x1800f03b5  pop     rbp
0x1800f03b6  retn
```
