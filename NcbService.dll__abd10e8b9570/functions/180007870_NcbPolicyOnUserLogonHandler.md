# NcbPolicyOnUserLogonHandler

- ea: `0x180007870`
- end: `0x180007a60`
- name: `NcbPolicyOnUserLogonHandler`
- size: `496`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180022c54`

## callees

- `0x18000723c`
- `0x180007260`
- `0x180007314`
- `0x1800075c4`
- `0x1800076e0`
- `0x180007870`
- `0x180007cf0`
- `0x18000a0a0`
- `0x18000a160`
- `0x18001d8e0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007898`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000795b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007898`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000795b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000799d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000799d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x180007961`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x180007961`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x1800079ea`
- `api-ms-win-core-bicltapi-l1-1-6!BiFreeMemory` at `0x1800079ea`

## string_xrefs

- `0x180007a52`: `Failed to get User Sid Status`

## pseudocode

```c
__int64 __fastcall NcbPolicyOnUserLogonHandler(PSID Sid, unsigned int a2)
{
  __int64 v4; // r8
  __int64 result; // rax
  __int64 active; // rbx
  int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // r8d
  __int64 v13; // rbx
  int v14; // [rsp+30h] [rbp-58h] BYREF
  int v15; // [rsp+38h] [rbp-50h] BYREF
  __int64 v16; // [rsp+40h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v17; // [rsp+48h] [rbp-40h] BYREF
  const wchar_t *v18; // [rsp+58h] [rbp-30h]
  __int64 v19; // [rsp+60h] [rbp-28h]
  int *v20; // [rsp+68h] [rbp-20h]
  __int64 v21; // [rsp+70h] [rbp-18h]

  EnterCriticalSection(&g_NcbPolicyLock);
  NcbPolicyCleanupPoliciesUnderLock(Sid);
  NcbPolicyAddUserLockscreenAppsUnderLock(Sid);
  LeaveCriticalSection(&g_NcbPolicyLock);
  NcbPolicyPolicyChangeCallback(0);
  v14 = 0;
  v16 = 0;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v15 = 0;
    v18 = L"NcbPolicy: NcbPolicyConsoleSessionChangeHandlerHelper called";
    v19 = 122;
    v20 = &v15;
    v21 = 4;
    McGenEventWrite_EventWriteTransfer(0, (const EVENT_DESCRIPTOR *)NcbApiStatus, v4, 3u, &v17);
  }
  while ( 1 )
  {
    result = (unsigned int)g_NcbPolicyReference;
    if ( (g_NcbPolicyReference & 1) != 0 )
      break;
    if ( (_DWORD)result == _InterlockedCompareExchange(
                             &g_NcbPolicyReference,
                             g_NcbPolicyReference + 2,
                             g_NcbPolicyReference) )
    {
      EnterCriticalSection(&g_NcbPolicyLock);
      active = WTSGetActiveConsoleSessionId();
      if ( (unsigned __int8)NcbPolicyIsInteractiveUserLogonSession(active, a2, &v14, &v16)
        || (LODWORD(active) = v14, v14 != -1) )
      {
        v7 = g_NcbPolicyCurrentConsoleSessionId;
        if ( (_DWORD)active != g_NcbPolicyCurrentConsoleSessionId )
        {
          v7 = active;
          g_NcbPolicyCurrentConsoleSessionId = active;
        }
      }
      else
      {
        v7 = g_NcbPolicyCurrentConsoleSessionId;
      }
      LeaveCriticalSection(&g_NcbPolicyLock);
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(
          v9,
          v8,
          L"NcbPolicy: NcbPolicyConsoleSessionChangeHandlerHelper invokes NCB registrar callback",
          0);
      ((void (__fastcall *)(__int64))g_NcbPolicyChangeCallback)(2);
      result = NcbPolicyDereference();
      v13 = v16;
      if ( v16 )
      {
        NcbCCResetSignal(v16, 0, v12, 0, a2 == v7, 1);
        return BiFreeMemory(v13);
      }
      else if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        return McTemplateU0zq_EventWriteTransfer(v11, v10, L"Failed to get User Sid Status", 1168);
      }
      return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007870  mov     [rsp+arg_10], rbx
0x180007875  push    rdi
0x180007876  sub     rsp, 80h
0x18000787d  mov     rax, cs:__security_cookie
0x180007884  xor     rax, rsp
0x180007887  mov     [rsp+88h+var_10], rax
0x18000788c  mov     rbx, rcx
0x18000788f  mov     edi, edx
0x180007891  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180007898  call    cs:__imp_EnterCriticalSection
0x18000789e  mov     rcx, rbx; Sid1
0x1800078a1  call    NcbPolicyCleanupPoliciesUnderLock
0x1800078a6  mov     rcx, rbx; Sid
0x1800078a9  call    NcbPolicyAddUserLockscreenAppsUnderLock
0x1800078ae  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x1800078b5  call    cs:__imp_LeaveCriticalSection
0x1800078bb  xor     ecx, ecx
0x1800078bd  call    NcbPolicyPolicyChangeCallback
0x1800078c2  xor     ecx, ecx
0x1800078c4  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800078cb  mov     [rsp+88h+var_58], ecx
0x1800078cf  mov     [rsp+88h+var_48], rcx
0x1800078d4  jnz     short loc_180007902
0x1800078d6  mov     eax, cs:g_NcbPolicyReference
0x1800078dc  test    al, 1
0x1800078de  jz      loc_180007A15
0x1800078e4  mov     rcx, [rsp+88h+var_10]
0x1800078e9  xor     rcx, rsp; StackCookie
0x1800078ec  call    __security_check_cookie
0x1800078f1  mov     rbx, [rsp+88h+arg_10]
0x1800078f9  add     rsp, 80h
0x180007900  pop     rdi
0x180007901  retn
0x180007902  lea     rax, aNcbpolicyNcbpo_7; "NcbPolicy: NcbPolicyConsoleSessionChang"...
0x180007909  mov     [rsp+88h+var_50], ecx
0x18000790d  mov     [rsp+88h+var_30], rax
0x180007912  lea     rdx, NcbApiStatus
0x180007919  lea     rax, [rsp+88h+var_50]
0x18000791e  mov     [rsp+88h+var_28], 7Ah ; 'z'
0x180007927  mov     [rsp+88h+var_20], rax
0x18000792c  mov     r9d, 3
0x180007932  lea     rax, [rsp+88h+var_40]
0x180007937  mov     [rsp+88h+var_18], 4
0x180007940  mov     [rsp+88h+var_68], rax
0x180007945  call    McGenEventWrite_EventWriteTransfer
0x18000794a  jmp     short loc_1800078D6
0x18000794c  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x180007953  mov     [rsp+88h+arg_8], rsi
0x18000795b  call    cs:__imp_EnterCriticalSection
0x180007961  call    cs:__imp_WTSGetActiveConsoleSessionId
0x180007967  lea     r9, [rsp+88h+var_48]
0x18000796c  mov     edx, edi
0x18000796e  mov     ecx, eax
0x180007970  lea     r8, [rsp+88h+var_58]
0x180007975  mov     ebx, eax
0x180007977  call    NcbPolicyIsInteractiveUserLogonSession
0x18000797c  test    al, al
0x18000797e  jz      loc_180007A2B
0x180007984  mov     esi, cs:g_NcbPolicyCurrentConsoleSessionId
0x18000798a  cmp     ebx, esi
0x18000798c  jz      short loc_180007996
0x18000798e  mov     esi, ebx
0x180007990  mov     cs:g_NcbPolicyCurrentConsoleSessionId, ebx
0x180007996  lea     rcx, g_NcbPolicyLock; lpCriticalSection
0x18000799d  call    cs:__imp_LeaveCriticalSection
0x1800079a3  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800079aa  jnz     short loc_180007A04
0x1800079ac  mov     rax, cs:g_NcbPolicyChangeCallback
0x1800079b3  mov     ecx, 2
0x1800079b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079bd  call    NcbPolicyDereference
0x1800079c2  mov     rbx, [rsp+88h+var_48]
0x1800079c7  test    rbx, rbx
0x1800079ca  jz      short loc_180007A43
0x1800079cc  xor     r9d, r9d
0x1800079cf  mov     [rsp+88h+var_60], 1
0x1800079d4  xor     edx, edx
0x1800079d6  mov     rcx, rbx
0x1800079d9  cmp     edi, esi
0x1800079db  jnz     short loc_1800079FD
0x1800079dd  mov     byte ptr [rsp+88h+var_68], 1
0x1800079e2  call    NcbCCResetSignal
0x1800079e7  mov     rcx, rbx
0x1800079ea  call    cs:__imp_BiFreeMemory
0x1800079f0  mov     rsi, [rsp+88h+arg_8]
0x1800079f8  jmp     loc_1800078E4
0x1800079fd  mov     byte ptr [rsp+88h+var_68], 0
0x180007a02  jmp     short loc_1800079E2
0x180007a04  xor     r9d, r9d
0x180007a07  lea     r8, aNcbpolicyNcbpo_5; "NcbPolicy: NcbPolicyConsoleSessionChang"...
0x180007a0e  call    McTemplateU0zq_EventWriteTransfer
0x180007a13  jmp     short loc_1800079AC
0x180007a15  lea     ecx, [rax+2]
0x180007a18  lock cmpxchg cs:g_NcbPolicyReference, ecx
0x180007a20  jnz     loc_1800078D6
0x180007a26  jmp     loc_18000794C
0x180007a2b  mov     ebx, [rsp+88h+var_58]
0x180007a2f  cmp     ebx, 0FFFFFFFFh
0x180007a32  jnz     loc_180007984
0x180007a38  mov     esi, cs:g_NcbPolicyCurrentConsoleSessionId
0x180007a3e  jmp     loc_180007996
0x180007a43  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180007a4a  jz      short loc_1800079F0
0x180007a4c  mov     r9d, 490h
0x180007a52  lea     r8, aFailedToGetUse; "Failed to get User Sid Status"
0x180007a59  call    McTemplateU0zq_EventWriteTransfer
0x180007a5e  jmp     short loc_1800079F0
```
