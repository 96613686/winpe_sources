# UbpmpPostTaskHostDeadCallback

- ea: `0x180011480`
- end: `0x18001161f`
- name: `UbpmpPostTaskHostDeadCallback`
- size: `415`
- prototype: `__int64 __fastcall(UUID *Uuid2)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task`

## callees

- `0x180006820`
- `0x180008430`
- `0x180008720`
- `0x180008920`
- `0x1800101a0`
- `0x1800103c0`
- `0x180011480`
- `0x1800119a0`
- `0x180012570`
- `0x1800351ec`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800114c6`
- `ntdll!RtlFreeHeap` at `0x1800114c6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011591`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800115bb`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180011591`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800115bb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011529`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180011529`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180011543`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180011543`

## pseudocode

```c
void __fastcall UbpmpPostTaskHostDeadCallback(UUID *Uuid2, char a2)
{
  unsigned int v3; // eax
  DWORD v4; // ebx
  unsigned int v5; // edi
  __int64 v6; // rsi
  unsigned int Data1; // ebx
  __int64 v8; // [rsp+20h] [rbp-D8h] BYREF
  _BYTE v9[144]; // [rsp+30h] [rbp-C8h] BYREF

  v8 = 0;
  if ( (a2 & 4) == 0 )
  {
    memset_0(v9, 0, 0x88u);
    UbpmUtilsStartLockTracking((struct _CEM_LOCK_TRACKER *)v9);
    v3 = UbpmpOpenTriggerConsumer(Uuid2, 0, &v8);
    v4 = UbpmpLockTrackerId;
    v5 = v3;
    if ( UbpmpLockTrackerId != -1 )
    {
      if ( *(_QWORD *)TlsGetValue(UbpmpLockTrackerId) )
        __int2c();
      TlsSetValue(v4, 0);
    }
    v6 = v8;
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, v5);
    }
    else if ( !(unsigned int)UbpmConsumerIncPendingActions(v8) )
    {
      Data1 = Uuid2[1].Data1;
      UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)(v6 + 208));
      UbpmpTriggerConsumerReportResult(v6, Data1, 0);
      *(_DWORD *)(v6 + 216) = 0;
      RtlReleaseSRWLockExclusive(v6 + 208);
      UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)(v6 + 208));
      UbpmpActionContextCleanup(v6);
      *(_DWORD *)(v6 + 216) = 0;
      RtlReleaseSRWLockExclusive(v6 + 208);
      UbpmConsumerDecPendingActions(v6);
    }
    if ( v6 )
      UbpmCloseTriggerConsumer(v6);
  }
  if ( Uuid2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Uuid2);
}

```

## disassembly

```asm
0x180011480  push    rbx
0x180011482  push    rbp
0x180011483  push    rsi
0x180011484  push    rdi
0x180011485  sub     rsp, 0D8h
0x18001148c  mov     rax, cs:__security_cookie
0x180011493  xor     rax, rsp
0x180011496  mov     [rsp+0F8h+var_38], rax
0x18001149e  mov     [rsp+0F8h+var_D8], 0
0x1800114a7  mov     rbp, rcx
0x1800114aa  test    dl, 4
0x1800114ad  jz      short loc_1800114EF
0x1800114af  test    rbp, rbp
0x1800114b2  jz      short loc_1800114D2
0x1800114b4  mov     rcx, gs:60h
0x1800114bd  mov     r8, rbp; P
0x1800114c0  xor     edx, edx; Flags
0x1800114c2  mov     rcx, [rcx+30h]; HeapHandle
0x1800114c6  call    cs:__imp_RtlFreeHeap
0x1800114cd  nop     dword ptr [rax+rax+00h]
0x1800114d2  mov     rcx, [rsp+0F8h+var_38]
0x1800114da  xor     rcx, rsp; StackCookie
0x1800114dd  call    __security_check_cookie
0x1800114e2  add     rsp, 0D8h
0x1800114e9  pop     rdi
0x1800114ea  pop     rsi
0x1800114eb  pop     rbp
0x1800114ec  pop     rbx
0x1800114ed  retn
0x1800114ef  xor     edx, edx; Val
0x1800114f1  lea     rcx, [rsp+0F8h+var_C8]; void *
0x1800114f6  mov     r8d, 88h; Size
0x1800114fc  call    memset_0
0x180011501  lea     rcx, [rsp+0F8h+var_C8]; lpTlsValue
0x180011506  call    ?UbpmUtilsStartLockTracking@@YAXPEAU_CEM_LOCK_TRACKER@@@Z; UbpmUtilsStartLockTracking(_CEM_LOCK_TRACKER *)
0x18001150b  lea     r8, [rsp+0F8h+var_D8]
0x180011510  xor     edx, edx; String2
0x180011512  mov     rcx, rbp; Uuid2
0x180011515  call    UbpmpOpenTriggerConsumer
0x18001151a  mov     ebx, cs:UbpmpLockTrackerId
0x180011520  mov     edi, eax
0x180011522  cmp     ebx, 0FFFFFFFFh
0x180011525  jz      short loc_18001154F
0x180011527  mov     ecx, ebx; dwTlsIndex
0x180011529  call    cs:__imp_TlsGetValue
0x180011530  nop     dword ptr [rax+rax+00h]
0x180011535  cmp     qword ptr [rax], 0
0x180011539  jnz     loc_180011618
0x18001153f  xor     edx, edx; lpTlsValue
0x180011541  mov     ecx, ebx; dwTlsIndex
0x180011543  call    cs:__imp_TlsSetValue
0x18001154a  nop     dword ptr [rax+rax+00h]
0x18001154f  mov     rsi, [rsp+0F8h+var_D8]
0x180011554  test    edi, edi
0x180011556  jnz     loc_1800115E5
0x18001155c  mov     rcx, rsi
0x18001155f  call    UbpmConsumerIncPendingActions
0x180011564  test    eax, eax
0x180011566  jnz     short loc_1800115CF
0x180011568  mov     ebx, [rbp+10h]
0x18001156b  lea     rdi, [rsi+0D0h]
0x180011572  mov     rcx, rdi; struct _UBPM_SRWLOCK *
0x180011575  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18001157a  xor     r8d, r8d
0x18001157d  mov     edx, ebx
0x18001157f  mov     rcx, rsi
0x180011582  call    UbpmpTriggerConsumerReportResult
0x180011587  mov     rcx, rdi
0x18001158a  mov     dword ptr [rdi+8], 0
0x180011591  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180011598  nop     dword ptr [rax+rax+00h]
0x18001159d  mov     rcx, rdi; struct _UBPM_SRWLOCK *
0x1800115a0  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x1800115a5  mov     rcx, rsi
0x1800115a8  call    UbpmpActionContextCleanup
0x1800115ad  lea     rcx, [rsi+0D0h]
0x1800115b4  mov     dword ptr [rcx+8], 0
0x1800115bb  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800115c2  nop     dword ptr [rax+rax+00h]
0x1800115c7  mov     rcx, rsi
0x1800115ca  call    UbpmConsumerDecPendingActions
0x1800115cf  test    rsi, rsi
0x1800115d2  jz      loc_1800114AF
0x1800115d8  mov     rcx, rsi
0x1800115db  call    UbpmCloseTriggerConsumer
0x1800115e0  jmp     loc_1800114AF
0x1800115e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800115ec  lea     rax, WPP_GLOBAL_Control
0x1800115f3  cmp     rcx, rax
0x1800115f6  jz      short loc_1800115CF
0x1800115f8  test    byte ptr [rcx+1Ch], 1
0x1800115fc  jz      short loc_1800115CF
0x1800115fe  mov     rcx, [rcx+10h]
0x180011602  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180011609  mov     edx, 0D4h
0x18001160e  mov     r9d, edi
0x180011611  call    WPP_SF_d
0x180011616  jmp     short loc_1800115CF
0x180011618  int     2Ch; Windows NT - assertion failure
0x18001161a  jmp     loc_18001153F
```
