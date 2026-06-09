# NcbRegistrarAuthorizeOrCleanupContexts

- ea: `0x18000d6dc`
- end: `0x18000d96a`
- name: `NcbRegistrarAuthorizeOrCleanupContexts`
- size: `654`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d650`

## callees

- `0x18000a0a0`
- `0x18000be70`
- `0x18000c820`
- `0x18000d6dc`
- `0x18000d970`
- `0x18001c500`
- `0x18001d09c`
- `0x18001fbe8`
- `0x180021c94`

## import_xrefs

- `ntdll!RtlRemoveEntryHashTable` at `0x18000d811`
- `ntdll!RtlRemoveEntryHashTable` at `0x18000d811`
- `ntdll!RtlInitEnumerationHashTable` at `0x18000d740`
- `ntdll!RtlInitEnumerationHashTable` at `0x18000d740`
- `ntdll!RtlEndEnumerationHashTable` at `0x18000d858`
- `ntdll!RtlEndEnumerationHashTable` at `0x18000d858`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18000d7d8`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18000d7d8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d72e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d74f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d72e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d74f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d7b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d865`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d7b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d865`

## string_xrefs

- `0x18000d92e`: `NcbRegpCreateOrUpdateWPMContext ended with`

## pseudocode

```c
void __fastcall NcbRegistrarAuthorizeOrCleanupContexts(char a1, unsigned int a2)
{
  bool v3; // cl
  bool v4; // cf
  BOOL v5; // edi
  bool v6; // zf
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rbx
  unsigned int IsContextAllowed; // esi
  unsigned int updated; // eax
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  _OWORD v16[2]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v17; // [rsp+50h] [rbp-48h]
  char v18; // [rsp+A0h] [rbp+8h] BYREF

  v18 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_cd(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
  memset(v16, 0, sizeof(v16));
  v17 = 0;
  v18 = 0;
  EnterCriticalSection(&g_ControlChannelTriggerContextTableLock);
  RtlInitEnumerationHashTable(g_ControlChannelTriggerContextTable, v16);
  while ( 1 )
  {
    v9 = RtlEnumerateEntryHashTable(g_ControlChannelTriggerContextTable, v16);
    v10 = v9;
    if ( !v9 )
      break;
    IsContextAllowed = NcbRegistrarPolicyIsContextAllowed(v9, a2, &v18);
    if ( IsContextAllowed == 5 )
    {
      RtlRemoveEntryHashTable(g_ControlChannelTriggerContextTable, v10, 0);
      CleanupContext((LPVOID)v10);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= (unsigned __int8)IsContextAllowed )
      {
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          IsContextAllowed + 43,
          &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
      }
    }
    else
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 24));
      v3 = v18 != 0;
      v4 = v18 != 0;
      *(_BYTE *)(v10 + 297) = v18 != 0;
      *(_DWORD *)(v10 + 304) = v4 ? 0 : 6;
      v5 = *(_BYTE *)(v10 + 298) && v3;
      v6 = *(_BYTE *)(v10 + 232) == 0;
      *(_DWORD *)(v10 + 364) = v5;
      if ( !v6 || *(_DWORD *)(v10 + 408) )
      {
        updated = NcbRegpCreateOrUpdateWPMContext(v10);
        IsContextAllowed = updated;
        if ( updated )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, updated);
          }
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v10 + 24));
      if ( IsContextAllowed )
      {
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
          McTemplateU0zq_EventWriteTransfer(v8, v7, L"NcbRegpCreateOrUpdateWPMContext ended with", IsContextAllowed);
      }
      else if ( !v5 )
      {
        v13 = KamSupressKeepaliveTimer(v10);
        if ( v13 )
        {
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
            McTemplateU0zq_EventWriteTransfer(v15, v14, L"KamSupressKeepaliveTimer ended with", v13);
        }
      }
    }
  }
  RtlEndEnumerationHashTable(g_ControlChannelTriggerContextTable, v16);
  LeaveCriticalSection(&g_ControlChannelTriggerContextTableLock);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
  }
}

```

## disassembly

```asm
0x18000d6dc  mov     [rsp+arg_0], cl
0x18000d6e0  push    rbx
0x18000d6e1  push    rbp
0x18000d6e2  push    rsi
0x18000d6e3  push    rdi
0x18000d6e4  push    r13
0x18000d6e6  push    r14
0x18000d6e8  sub     rsp, 68h
0x18000d6ec  mov     r14d, edx
0x18000d6ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6f6  lea     r13, WPP_GLOBAL_Control
0x18000d6fd  cmp     rcx, r13
0x18000d700  jz      short loc_18000D70C
0x18000d702  test    byte ptr [rcx+1Ch], 1
0x18000d706  jnz     loc_18000D901
0x18000d70c  xorps   xmm0, xmm0
0x18000d70f  lea     rcx, g_ControlChannelTriggerContextTableLock; lpCriticalSection
0x18000d716  xor     eax, eax
0x18000d718  movups  [rsp+98h+var_68], xmm0
0x18000d71d  mov     [rsp+98h+var_48], rax
0x18000d722  movups  [rsp+98h+var_58], xmm0
0x18000d727  mov     [rsp+98h+arg_0], al
0x18000d72e  call    cs:__imp_EnterCriticalSection
0x18000d734  lea     rdx, [rsp+98h+var_68]
0x18000d739  lea     rcx, g_ControlChannelTriggerContextTable
0x18000d740  call    cs:__imp_RtlInitEnumerationHashTable
0x18000d746  jmp     loc_18000D7CC
0x18000d74b  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000d74f  call    cs:__imp_EnterCriticalSection
0x18000d755  mov     al, [rsp+98h+arg_0]
0x18000d75c  test    al, al
0x18000d75e  setnz   cl
0x18000d761  neg     al
0x18000d763  mov     [rbx+129h], cl
0x18000d769  sbb     eax, eax
0x18000d76b  not     eax
0x18000d76d  and     eax, 6
0x18000d770  mov     [rbx+130h], eax
0x18000d776  cmp     byte ptr [rbx+12Ah], 0
0x18000d77d  jz      loc_18000D8FA
0x18000d783  test    cl, cl
0x18000d785  jz      loc_18000D8FA
0x18000d78b  mov     edi, 1
0x18000d790  cmp     byte ptr [rbx+0E8h], 0
0x18000d797  mov     [rbx+16Ch], edi
0x18000d79d  jnz     loc_18000D8A7
0x18000d7a3  cmp     dword ptr [rbx+198h], 0
0x18000d7aa  jnz     loc_18000D8A7
0x18000d7b0  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000d7b4  call    cs:__imp_LeaveCriticalSection
0x18000d7ba  test    esi, esi
0x18000d7bc  jnz     loc_18000D91E
0x18000d7c2  xor     dil, 1
0x18000d7c6  jnz     loc_18000D94B
0x18000d7cc  lea     rdx, [rsp+98h+var_68]
0x18000d7d1  lea     rcx, g_ControlChannelTriggerContextTable
0x18000d7d8  call    cs:__imp_RtlEnumerateEntryHashTable
0x18000d7de  mov     rbx, rax
0x18000d7e1  test    rax, rax
0x18000d7e4  jz      short loc_18000D84C
0x18000d7e6  lea     r8, [rsp+98h+arg_0]
0x18000d7ee  mov     edx, r14d
0x18000d7f1  mov     rcx, rax
0x18000d7f4  call    NcbRegistrarPolicyIsContextAllowed
0x18000d7f9  mov     esi, eax
0x18000d7fb  cmp     eax, 5
0x18000d7fe  jnz     loc_18000D74B
0x18000d804  xor     r8d, r8d
0x18000d807  lea     rcx, g_ControlChannelTriggerContextTable
0x18000d80e  mov     rdx, rbx
0x18000d811  call    cs:__imp_RtlRemoveEntryHashTable
0x18000d817  mov     rcx, rbx; lpMem
0x18000d81a  call    CleanupContext
0x18000d81f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d826  cmp     rcx, r13
0x18000d829  jz      short loc_18000D7CC
0x18000d82b  test    byte ptr [rcx+1Ch], 1
0x18000d82f  jz      short loc_18000D7CC
0x18000d831  cmp     [rcx+19h], sil
0x18000d835  jb      short loc_18000D7CC
0x18000d837  mov     rcx, [rcx+10h]
0x18000d83b  lea     edx, [rsi+2Bh]
0x18000d83e  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000d845  call    WPP_SF_
0x18000d84a  jmp     short loc_18000D7CC
0x18000d84c  lea     rdx, [rsp+98h+var_68]
0x18000d851  lea     rcx, g_ControlChannelTriggerContextTable
0x18000d858  call    cs:__imp_RtlEndEnumerationHashTable
0x18000d85e  lea     rcx, g_ControlChannelTriggerContextTableLock; lpCriticalSection
0x18000d865  call    cs:__imp_LeaveCriticalSection
0x18000d86b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d872  cmp     rcx, r13
0x18000d875  jnz     short loc_18000D884
0x18000d877  add     rsp, 68h
0x18000d87b  pop     r14
0x18000d87d  pop     r13
0x18000d87f  pop     rdi
0x18000d880  pop     rsi
0x18000d881  pop     rbp
0x18000d882  pop     rbx
0x18000d883  retn
0x18000d884  test    byte ptr [rcx+1Ch], 1
0x18000d888  jz      short loc_18000D877
0x18000d88a  cmp     byte ptr [rcx+19h], 6
0x18000d88e  jb      short loc_18000D877
0x18000d890  mov     rcx, [rcx+10h]
0x18000d894  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000d89b  mov     edx, 32h ; '2'
0x18000d8a0  call    WPP_SF_
0x18000d8a5  jmp     short loc_18000D877
0x18000d8a7  mov     rcx, rbx
0x18000d8aa  call    NcbRegpCreateOrUpdateWPMContext
0x18000d8af  mov     esi, eax
0x18000d8b1  test    eax, eax
0x18000d8b3  jz      loc_18000D7B0
0x18000d8b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d8c0  cmp     rcx, r13
0x18000d8c3  jz      loc_18000D7B0
0x18000d8c9  test    byte ptr [rcx+1Ch], 1
0x18000d8cd  jz      loc_18000D7B0
0x18000d8d3  cmp     byte ptr [rcx+19h], 2
0x18000d8d7  jb      loc_18000D7B0
0x18000d8dd  mov     rcx, [rcx+10h]
0x18000d8e1  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000d8e8  mov     edx, 31h ; '1'
0x18000d8ed  mov     r9d, eax
0x18000d8f0  call    WPP_SF_d
0x18000d8f5  jmp     loc_18000D7B0
0x18000d8fa  xor     edi, edi
0x18000d8fc  jmp     loc_18000D790
0x18000d901  cmp     byte ptr [rcx+19h], 6
0x18000d905  jb      loc_18000D70C
0x18000d90b  mov     rcx, [rcx+10h]
0x18000d90f  mov     [rsp+98h+var_78], r14d
0x18000d914  call    WPP_SF_cd
0x18000d919  jmp     loc_18000D70C
0x18000d91e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000d925  jz      loc_18000D7CC
0x18000d92b  mov     r9d, esi
0x18000d92e  lea     r8, aNcbregpcreateo_0; "NcbRegpCreateOrUpdateWPMContext ended w"...
0x18000d935  jmp     short loc_18000D941
0x18000d937  mov     r9d, eax
0x18000d93a  lea     r8, aKamsupresskeep; "KamSupressKeepaliveTimer ended with"
0x18000d941  call    McTemplateU0zq_EventWriteTransfer
0x18000d946  jmp     loc_18000D7CC
0x18000d94b  mov     rcx, rbx
0x18000d94e  call    KamSupressKeepaliveTimer
0x18000d953  test    eax, eax
0x18000d955  jz      loc_18000D7CC
0x18000d95b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000d962  jz      loc_18000D7CC
0x18000d968  jmp     short loc_18000D937
```
