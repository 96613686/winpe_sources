# FwppFreeWfpNblInfo

- ea: `0x180007530`
- end: `0x1800077d7`
- name: `FwppFreeWfpNblInfo`
- size: `679`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007080`
- `0x180007350`
- `0x18000aec0`
- `0x18000b290`

## callees

- `0x180007530`
- `0x18001f91c`
- `0x180020400`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1800075ad`
- `ntoskrnl!KeBugCheckEx` at `0x180007626`
- `ntoskrnl!KeBugCheckEx` at `0x180007659`
- `ntoskrnl!KeBugCheckEx` at `0x180007762`
- `ntoskrnl!KeBugCheckEx` at `0x1800077ca`
- `ntoskrnl!KeBugCheckEx` at `0x1800075ad`
- `ntoskrnl!KeBugCheckEx` at `0x180007626`
- `ntoskrnl!KeBugCheckEx` at `0x180007659`
- `ntoskrnl!KeBugCheckEx` at `0x180007762`
- `ntoskrnl!KeBugCheckEx` at `0x1800077ca`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180007674`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180007782`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180007674`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x180007782`
- `NETIO!WfpNblInfoGet` at `0x180007557`
- `NETIO!WfpNblInfoGet` at `0x1800076f0`
- `NETIO!WfpNblInfoGet` at `0x180007557`
- `NETIO!WfpNblInfoGet` at `0x1800076f0`

## pseudocode

```c
void __fastcall FwppFreeWfpNblInfo(char *Entry, __int64 a2, ULONG_PTR a3)
{
  unsigned int *v3; // rbx
  char v5; // bp
  unsigned int *v7; // rax
  __int64 v8; // rcx
  unsigned int *v9; // rsi
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rcx
  unsigned int **v13; // rsi
  __int64 v14; // rcx
  unsigned int *v15; // rbx
  int v16; // eax

  v3 = (unsigned int *)*((_QWORD *)Entry + 41);
  v5 = a2;
  if ( v3 )
  {
    v7 = (unsigned int *)WfpNblInfoGet(a3);
    v9 = v7;
    if ( gWFPFeature_Firewall_042024_IsEnabled )
    {
      v10 = *v3;
      if ( (_DWORD)v10 != 1768978246 )
        MicrosoftTelemetryAssertTriggeredArgsMsgKM(
          v8,
          v10,
          0,
          "FwppValidateInjectorInfo: the injectorInfo Signature is not FWPP_INJECTOR_INFO_POOLTAG");
      if ( *v3 != 1768978246 && gWfpVerifierEnabled )
LABEL_13:
        KeBugCheckEx(0xC4u, (ULONG_PTR)v3, a3, (ULONG_PTR)v9, 0);
    }
    else
    {
      if ( (gVerifierFlags & 0x2000000) == 0 )
      {
LABEL_15:
        ExFreeToNPagedLookasideList(&stru_180048500, *((PVOID *)Entry + 41));
        *((_QWORD *)Entry + 41) = 0xBADBADFABADBADFAuLL;
        goto LABEL_16;
      }
      if ( *v3 != 1768978246 )
      {
        MicrosoftTelemetryAssertTriggeredArgsMsgKM(
          v8,
          (unsigned int)v3,
          *v7,
          "The injectorInfo Signature is not FWPP_INJECTOR_INFO_POOLTAG");
        KeBugCheckEx(0xC4u, (ULONG_PTR)v3, *v9, 0, 0);
      }
    }
    if ( *((_QWORD *)v3 + 1) != *((_QWORD *)v9 + 1) )
    {
      if ( !gWFPFeature_Firewall_042024_IsEnabled )
      {
        MicrosoftTelemetryAssertTriggeredArgsMsgKM(
          v8,
          (unsigned int)v3,
          0,
          "The injectorInfo validator is not equal to wfpNblInfo->inejctionCtxt");
        KeBugCheckEx(0xC4u, (ULONG_PTR)v3, 0, 0, 0);
      }
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        v8,
        0,
        0,
        "FwppValidateInjectorInfo: the injectorInfo validator is not equal to wfpNblInfo->inejctionCtxt");
      if ( gWfpVerifierEnabled )
        goto LABEL_13;
    }
    goto LABEL_15;
  }
LABEL_16:
  if ( v5 )
  {
    if ( _InterlockedAdd(&gFwpTcpIp, 1u) < 0 )
      __fastfail(5u);
    LOBYTE(a2) = 1;
    (*((void (__fastcall **)(char *, __int64))qword_180048208 + 12))(Entry + 184, a2);
    v12 = *((_QWORD *)Entry + 40);
    if ( v12 )
    {
      LOBYTE(v11) = 1;
      (*((void (__fastcall **)(__int64, _QWORD, __int64))qword_180048208 + 13))(v12, *((_QWORD *)Entry + 38), v11);
    }
    _InterlockedDecrement(&gFwpTcpIp);
  }
  v13 = (unsigned int **)(Entry + 8);
  v15 = (unsigned int *)WfpNblInfoGet(a3);
  v16 = *(_DWORD *)Entry;
  if ( *(_DWORD *)Entry != 1852864326 || *v13 != v15 )
  {
    if ( !gWFPFeature_Firewall_042024_IsEnabled )
    {
      if ( v16 != 1852864326 || *v13 != v15 )
        MicrosoftTelemetryAssertTriggeredArgsMsgKM(
          v14,
          (unsigned int)v15,
          *v15,
          "nblInfo has the wrong Pool Tag for WFP Injection");
      KeBugCheckEx(0xC4u, (ULONG_PTR)v15, *v15, 0, 0);
    }
    if ( v16 != 1852864326 || *v13 != v15 )
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        v14,
        *(_DWORD *)Entry == 1852864326,
        *((_QWORD *)Entry + 1) == (_QWORD)v15,
        "FwppValidateInjectionContext: nblInfo has the wrong Pool Tag or incorrect an infoContainer value for WFP Injection");
    if ( gWfpVerifierEnabled )
      KeBugCheckEx(0xC4u, (ULONG_PTR)v15, (ULONG_PTR)Entry, 0, 0);
  }
  *(_DWORD *)Entry = -1;
  *v13 = 0;
  ExFreeToNPagedLookasideList(&gFwpNblInfo, Entry);
}

```

## disassembly

```asm
0x180007530  push    rbx
0x180007532  push    rbp
0x180007533  push    rsi
0x180007534  push    rdi
0x180007535  push    r14
0x180007537  sub     rsp, 30h
0x18000753b  mov     rbx, [rcx+148h]
0x180007542  mov     r14, r8
0x180007545  movzx   ebp, dl
0x180007548  mov     rdi, rcx
0x18000754b  test    rbx, rbx
0x18000754e  jz      loc_180007691
0x180007554  mov     rcx, r8
0x180007557  call    cs:__imp_WfpNblInfoGet
0x18000755e  nop     dword ptr [rax+rax+00h]
0x180007563  cmp     cs:gWFPFeature_Firewall_042024_IsEnabled, 0
0x18000756a  mov     rsi, rax
0x18000756d  jnz     short loc_1800075BA
0x18000756f  test    cs:gVerifierFlags, 2000000h
0x180007579  jz      loc_180007666
0x18000757f  cmp     dword ptr [rbx], 69707746h
0x180007585  jz      short loc_1800075E4
0x180007587  mov     r8d, [rax]
0x18000758a  lea     r9, aTheInjectorinf; "The injectorInfo Signature is not FWPP_"...
0x180007591  mov     edx, ebx
0x180007593  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x180007598  mov     r8d, [rsi]; BugCheckParameter2
0x18000759b  xor     ebp, ebp
0x18000759d  xor     r9d, r9d; BugCheckParameter3
0x1800075a0  mov     [rsp+58h+BugCheckParameter4], rbp; BugCheckParameter4
0x1800075a5  mov     rdx, rbx; BugCheckParameter1
0x1800075a8  mov     ecx, 0C4h; BugCheckCode
0x1800075ad  call    cs:__imp_KeBugCheckEx
0x1800075ba  mov     edx, [rbx]
0x1800075bc  cmp     edx, 69707746h
0x1800075c2  jz      short loc_1800075D3
0x1800075c4  lea     r9, aFwppvalidatein_1; "FwppValidateInjectorInfo: the injectorI"...
0x1800075cb  xor     r8d, r8d
0x1800075ce  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x1800075d3  cmp     dword ptr [rbx], 69707746h
0x1800075d9  jz      short loc_1800075E4
0x1800075db  cmp     cs:gWfpVerifierEnabled, 0
0x1800075e2  jnz     short loc_180007611
0x1800075e4  mov     rax, [rsi+8]
0x1800075e8  cmp     [rbx+8], rax
0x1800075ec  jz      short loc_180007666
0x1800075ee  cmp     cs:gWFPFeature_Firewall_042024_IsEnabled, 0
0x1800075f5  jz      short loc_180007633
0x1800075f7  lea     r9, aFwppvalidatein_0; "FwppValidateInjectorInfo: the injectorI"...
0x1800075fe  xor     r8d, r8d
0x180007601  xor     edx, edx
0x180007603  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x180007608  cmp     cs:gWfpVerifierEnabled, 0
0x18000760f  jz      short loc_180007666
0x180007611  xor     ebp, ebp
0x180007613  mov     r9, rsi; BugCheckParameter3
0x180007616  mov     r8, r14; BugCheckParameter2
0x180007619  mov     [rsp+58h+BugCheckParameter4], rbp; BugCheckParameter4
0x18000761e  mov     rdx, rbx; BugCheckParameter1
0x180007621  mov     ecx, 0C4h; BugCheckCode
0x180007626  call    cs:__imp_KeBugCheckEx
0x180007633  lea     r9, aTheInjectorinf_0; "The injectorInfo validator is not equal"...
0x18000763a  xor     r8d, r8d
0x18000763d  mov     edx, ebx
0x18000763f  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x180007644  xor     ebp, ebp
0x180007646  xor     r9d, r9d; BugCheckParameter3
0x180007649  xor     r8d, r8d; BugCheckParameter2
0x18000764c  mov     [rsp+58h+BugCheckParameter4], rbp; BugCheckParameter4
0x180007651  mov     rdx, rbx; BugCheckParameter1
0x180007654  mov     ecx, 0C4h; BugCheckCode
0x180007659  call    cs:__imp_KeBugCheckEx
0x180007666  mov     rdx, [rdi+148h]; Entry
0x18000766d  lea     rcx, stru_180048500; Lookaside
0x180007674  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000767b  nop     dword ptr [rax+rax+00h]
0x180007680  mov     rax, 0BADBADFABADBADFAh
0x18000768a  mov     [rdi+148h], rax
0x180007691  test    bpl, bpl
0x180007694  jz      short loc_1800076ED
0x180007696  lock add cs:gFwpTcpIp, 1
0x18000769e  jns     short loc_1800076A7
0x1800076a0  mov     ecx, 5
0x1800076a5  int     29h; Win8: RtlFailFast(ecx)
0x1800076a7  mov     rax, cs:qword_180048208
0x1800076ae  lea     rcx, [rdi+0B8h]
0x1800076b5  mov     dl, 1
0x1800076b7  mov     rax, [rax+60h]
0x1800076bb  call    _guard_dispatch_icall
0x1800076c0  mov     rcx, [rdi+140h]
0x1800076c7  test    rcx, rcx
0x1800076ca  jz      short loc_1800076E6
0x1800076cc  mov     rax, cs:qword_180048208
0x1800076d3  mov     r8b, 1
0x1800076d6  mov     rdx, [rdi+130h]
0x1800076dd  mov     rax, [rax+68h]
0x1800076e1  call    _guard_dispatch_icall
0x1800076e6  lock dec cs:gFwpTcpIp
0x1800076ed  mov     rcx, r14
0x1800076f0  call    cs:__imp_WfpNblInfoGet
0x1800076f7  nop     dword ptr [rax+rax+00h]
0x1800076fc  xor     ebp, ebp
0x1800076fe  lea     rsi, [rdi+8]
0x180007702  mov     rbx, rax
0x180007705  mov     eax, [rdi]
0x180007707  cmp     eax, 6E707746h
0x18000770c  jnz     short loc_180007713
0x18000770e  cmp     [rsi], rbx
0x180007711  jz      short loc_18000776F
0x180007713  cmp     cs:gWFPFeature_Firewall_042024_IsEnabled, ebp
0x180007719  jz      short loc_18000779A
0x18000771b  cmp     eax, 6E707746h
0x180007720  jnz     short loc_180007727
0x180007722  cmp     [rsi], rbx
0x180007725  jz      short loc_180007747
0x180007727  cmp     [rsi], rbx
0x18000772a  lea     r9, aFwppvalidatein; "FwppValidateInjectionContext: nblInfo h"...
0x180007731  mov     r8d, ebp
0x180007734  mov     edx, ebp
0x180007736  setz    r8b
0x18000773a  cmp     eax, 6E707746h
0x18000773f  setz    dl
0x180007742  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x180007747  cmp     cs:gWfpVerifierEnabled, ebp
0x18000774d  jz      short loc_18000776F
0x18000774f  xor     r9d, r9d; BugCheckParameter3
0x180007752  mov     [rsp+58h+BugCheckParameter4], rbp; BugCheckParameter4
0x180007757  mov     r8, rdi; BugCheckParameter2
0x18000775a  mov     rdx, rbx; BugCheckParameter1
0x18000775d  mov     ecx, 0C4h; BugCheckCode
0x180007762  call    cs:__imp_KeBugCheckEx
0x18000776f  mov     rdx, rdi; Entry
0x180007772  mov     dword ptr [rdi], 0FFFFFFFFh
0x180007778  lea     rcx, gFwpNblInfo; Lookaside
0x18000777f  mov     [rsi], rbp
0x180007782  call    cs:__imp_ExFreeToNPagedLookasideList
0x180007789  nop     dword ptr [rax+rax+00h]
0x18000778e  add     rsp, 30h
0x180007792  pop     r14
0x180007794  pop     rdi
0x180007795  pop     rsi
0x180007796  pop     rbp
0x180007797  pop     rbx
0x180007798  retn
0x18000779a  cmp     eax, 6E707746h
0x18000779f  jnz     short loc_1800077A6
0x1800077a1  cmp     [rsi], rbx
0x1800077a4  jz      short loc_1800077B7
0x1800077a6  mov     r8d, [rbx]
0x1800077a9  lea     r9, aNblinfoHasTheW; "nblInfo has the wrong Pool Tag for WFP "...
0x1800077b0  mov     edx, ebx
0x1800077b2  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x1800077b7  mov     r8d, [rbx]; BugCheckParameter2
0x1800077ba  xor     r9d, r9d; BugCheckParameter3
0x1800077bd  mov     rdx, rbx; BugCheckParameter1
0x1800077c0  mov     [rsp+58h+BugCheckParameter4], rbp; BugCheckParameter4
0x1800077c5  mov     ecx, 0C4h; BugCheckCode
0x1800077ca  call    cs:__imp_KeBugCheckEx
```
