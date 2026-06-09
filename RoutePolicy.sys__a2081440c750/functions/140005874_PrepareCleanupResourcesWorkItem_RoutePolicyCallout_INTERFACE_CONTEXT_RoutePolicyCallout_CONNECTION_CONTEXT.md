# PrepareCleanupResourcesWorkItem(RoutePolicyCallout::INTERFACE_CONTEXT *,RoutePolicyCallout::CONNECTION_CONTEXT *)

- ea: `0x140005874`
- end: `0x140005b59`
- name: `?PrepareCleanupResourcesWorkItem@@YAJPEAUINTERFACE_CONTEXT@RoutePolicyCallout@@PEAUCONNECTION_CONTEXT@2@@Z`
- size: `741`
- prototype: `__int64 __fastcall(PVOID P, struct CONNECTION_CONTEXT *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140004330`
- `0x140004800`

## callees

- `0x140001008`
- `0x1400012f0`
- `0x14000294c`
- `0x140005874`
- `0x14000935c`
- `0x14000a680`
- `0x14000a6c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005970`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005ad9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005970`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005ad9`
- `ntoskrnl!ExAllocatePool2` at `0x1400059dc`
- `ntoskrnl!ExAllocatePool2` at `0x1400059dc`

## string_xrefs

- `0x140005aa5`: `WdfWorkItemCreate for RoutePolicyAsyncCleanupRoutine failed`

## pseudocode

```c
__int64 __fastcall PrepareCleanupResourcesWorkItem(_QWORD *P, struct CONNECTION_CONTEXT ***a2)
{
  struct CONNECTION_CONTEXT **v4; // rcx
  struct CONNECTION_CONTEXT **v5; // rax
  __int64 v6; // r15
  __int64 v7; // r12
  _QWORD *v8; // rcx
  PVOID *v9; // rax
  __int64 v10; // rcx
  __int64 Pool2; // rax
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  _QWORD *v15; // rbx
  _QWORD *v16; // r14
  __int64 v17; // rcx
  int v18; // edi
  __int64 v19; // r8
  __int64 v20; // r9
  _QWORD *v21; // rax
  char *v22; // rax
  PVOID *v23; // rcx
  __int64 v25; // [rsp+30h] [rbp-69h] BYREF
  const char *v26; // [rsp+38h] [rbp-61h] BYREF
  __int128 v27; // [rsp+40h] [rbp-59h] BYREF
  __int64 v28; // [rsp+50h] [rbp-49h]
  __int64 v29; // [rsp+58h] [rbp-41h]
  __int128 v30; // [rsp+60h] [rbp-39h]
  __int64 *v31; // [rsp+70h] [rbp-29h]
  _QWORD v32[3]; // [rsp+78h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v33; // [rsp+90h] [rbp-9h] BYREF
  __int64 *v34; // [rsp+B0h] [rbp+17h]
  __int64 v35; // [rsp+B8h] [rbp+1Fh]

  v4 = *a2;
  if ( (*a2)[1] != (struct CONNECTION_CONTEXT *)a2 )
    goto LABEL_21;
  v5 = a2[1];
  if ( *v5 != (struct CONNECTION_CONTEXT *)a2 )
    goto LABEL_21;
  *v5 = (struct CONNECTION_CONTEXT *)v4;
  v4[1] = (struct CONNECTION_CONTEXT *)v5;
  v6 = -1;
  v7 = P[2];
  if ( (_QWORD *)P[4] == P + 4 )
  {
    if ( !P[3] )
      MicrosoftTelemetryAssertTriggeredNoArgsKM();
    v6 = P[3];
    RoutePolicyCache::RemoveInterface((RoutePolicyCache *)(P + 2), (const union _NET_LUID_LH *)a2);
    if ( (unsigned int)dword_140012050 > 4 )
    {
      v25 = P[2];
      v35 = 8;
      v34 = &v25;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&byte_14000EF1D, 0, 0, 3u, &v33);
    }
    v8 = (_QWORD *)*P;
    if ( *(_QWORD **)(*P + 8LL) != P )
      goto LABEL_21;
    v9 = (PVOID *)P[1];
    if ( *v9 != P )
      goto LABEL_21;
    *v9 = v8;
    v8[1] = v9;
    ExFreePoolWithTag(P, 0x64667072u);
  }
  v28 = 0;
  v29 = 0x100000001LL;
  v31 = off_140012018;
  v27 = 0;
  LODWORD(v27) = 56;
  v30 = 0;
  v10 = *((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 3);
  v32[2] = 0;
  *(_QWORD *)&v30 = v10;
  v32[0] = 24;
  v32[1] = RoutePolicyAsyncCleanupRoutine;
  Pool2 = ExAllocatePool2(64, 24, 1684435058);
  v15 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    v16 = (_QWORD *)(Pool2 + 16);
    v18 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD *, __int128 *, __int64))(WdfFunctions_01015 + 3032))(
            WdfDriverGlobals,
            v32,
            &v27,
            Pool2 + 16);
    if ( v18 >= 0 )
    {
      v21 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01015 + 1616))(
                        WdfDriverGlobals,
                        *v16,
                        off_140012018);
      *v21 = v7;
      v21[1] = v6;
      v21[2] = a2;
      v22 = (char *)RoutePolicyCallout::g_pCalloutContext + 64;
      v23 = (PVOID *)*((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 9);
      if ( *v23 == (char *)RoutePolicyCallout::g_pCalloutContext + 64 )
      {
        *v15 = v22;
        v15[1] = v23;
        *v23 = v15;
        *((_QWORD *)v22 + 1) = v15;
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 3040))(WdfDriverGlobals, *v16);
        return (unsigned int)v18;
      }
LABEL_21:
      __fastfail(3u);
    }
    if ( (unsigned int)dword_140012050 > 2 )
    {
      LODWORD(v25) = v18;
      v26 = "WdfWorkItemCreate for RoutePolicyAsyncCleanupRoutine failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v17,
        (unsigned __int8 *)&unk_14000FED8,
        v19,
        v20,
        (int **)&v26,
        (__int64)&v25);
    }
    ExFreePoolWithTag(v15, 0x64667072u);
  }
  else
  {
    v18 = -1073741670;
    if ( (unsigned int)dword_140012050 > 2 )
    {
      LODWORD(v25) = -1073741670;
      v26 = "Failed to allocate work item list entry";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned __int8 *)word_14000FA7A,
        v13,
        v14,
        (int **)&v26,
        (__int64)&v25);
    }
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x140005874  mov     [rsp-8+arg_10], rbx
0x140005879  mov     [rsp-8+arg_18], rsi
0x14000587e  push    rbp
0x14000587f  push    rdi
0x140005880  push    r12
0x140005882  push    r14
0x140005884  push    r15
0x140005886  lea     rbp, [rsp-37h]
0x14000588b  sub     rsp, 0D0h
0x140005892  mov     rax, cs:__security_cookie
0x140005899  xor     rax, rsp
0x14000589c  mov     [rbp+57h+var_30], rax
0x1400058a0  mov     rbx, rcx
0x1400058a3  mov     rsi, rdx
0x1400058a6  mov     rcx, [rdx]
0x1400058a9  cmp     [rcx+8], rdx
0x1400058ad  jnz     loc_140005B52
0x1400058b3  mov     rax, [rdx+8]
0x1400058b7  cmp     [rax], rdx
0x1400058ba  jnz     loc_140005B52
0x1400058c0  mov     [rax], rcx
0x1400058c3  lea     rdi, [rbx+10h]
0x1400058c7  mov     [rcx+8], rax
0x1400058cb  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400058cf  mov     r12, [rdi]
0x1400058d2  lea     rax, [rbx+20h]
0x1400058d6  mov     r14d, 64667072h
0x1400058dc  cmp     [rax], rax
0x1400058df  jnz     loc_14000597C
0x1400058e5  cmp     qword ptr [rbx+18h], 0
0x1400058ea  jnz     short loc_1400058F1
0x1400058ec  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400058f1  mov     r15, [rbx+18h]
0x1400058f5  mov     rcx, rdi; this
0x1400058f8  call    ?RemoveInterface@RoutePolicyCache@@YAJAEBT_NET_LUID_LH@@@Z; RoutePolicyCache::RemoveInterface(_NET_LUID_LH const &)
0x1400058fd  mov     eax, cs:dword_140012050
0x140005903  cmp     eax, 4
0x140005906  jbe     short loc_140005949
0x140005908  mov     rax, [rdi]
0x14000590b  lea     rdx, byte_14000EF1D; int
0x140005912  mov     [rbp+57h+var_C0], rax
0x140005916  lea     rcx, dword_140012050; int
0x14000591d  lea     rax, [rbp+57h+var_C0]
0x140005921  mov     [rbp+57h+var_38], 8
0x140005929  mov     [rbp+57h+var_40], rax
0x14000592d  xor     r9d, r9d; int
0x140005930  lea     rax, [rbp+57h+var_60]
0x140005934  xor     r8d, r8d; int
0x140005937  mov     [rsp+0F0h+var_C8], rax; PEVENT_DATA_DESCRIPTOR
0x14000593c  mov     [rsp+0F0h+var_D0], 3; ULONG
0x140005944  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005949  mov     rcx, [rbx]
0x14000594c  cmp     [rcx+8], rbx
0x140005950  jnz     loc_140005B52
0x140005956  mov     rax, [rbx+8]
0x14000595a  cmp     [rax], rbx
0x14000595d  jnz     loc_140005B52
0x140005963  mov     [rax], rcx
0x140005966  mov     edx, r14d; Tag
0x140005969  mov     [rcx+8], rax
0x14000596d  mov     rcx, rbx; P
0x140005970  call    cs:__imp_ExFreePoolWithTag
0x140005977  nop     dword ptr [rax+rax+00h]
0x14000597c  xorps   xmm0, xmm0
0x14000597f  mov     eax, 1
0x140005984  movups  [rbp+57h+var_A0], xmm0
0x140005988  mov     dword ptr [rbp+57h+var_A0+8], eax
0x14000598b  mov     r8d, r14d
0x14000598e  mov     dword ptr [rbp+57h+var_A0+0Ch], eax
0x140005991  mov     rax, cs:off_140012018
0x140005998  mov     [rbp+57h+var_80], rax
0x14000599c  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x1400059a3  movups  [rbp+57h+var_B0], xmm0
0x1400059a7  mov     dword ptr [rbp+57h+var_B0], 38h ; '8'
0x1400059ae  movups  [rbp+57h+var_90], xmm0
0x1400059b2  mov     rcx, [rax+18h]
0x1400059b6  xor     eax, eax
0x1400059b8  mov     [rbp+57h+var_68], rax
0x1400059bc  movups  [rbp+57h+var_78], xmm0
0x1400059c0  mov     qword ptr [rbp+57h+var_90], rcx
0x1400059c4  lea     edx, [rax+18h]
0x1400059c7  mov     byte ptr [rbp+57h+var_68], 0
0x1400059cb  lea     rax, RoutePolicyAsyncCleanupRoutine
0x1400059d2  mov     dword ptr [rbp+57h+var_78], edx
0x1400059d5  lea     ecx, [rdx+28h]
0x1400059d8  mov     qword ptr [rbp+57h+var_78+8], rax
0x1400059dc  call    cs:__imp_ExAllocatePool2
0x1400059e3  nop     dword ptr [rax+rax+00h]
0x1400059e8  mov     rbx, rax
0x1400059eb  test    rax, rax
0x1400059ee  jz      loc_140005AE7
0x1400059f4  mov     rcx, cs:WdfFunctions_01015
0x1400059fb  lea     r14, [rax+10h]
0x1400059ff  mov     r9, r14
0x140005a02  lea     r8, [rbp+57h+var_B0]
0x140005a06  lea     rdx, [rbp+57h+var_78]
0x140005a0a  mov     rax, [rcx+0BD8h]
0x140005a11  mov     rcx, cs:WdfDriverGlobals
0x140005a18  call    _guard_dispatch_icall
0x140005a1d  mov     edi, eax
0x140005a1f  test    eax, eax
0x140005a21  js      short loc_140005A9A
0x140005a23  mov     rcx, cs:WdfFunctions_01015
0x140005a2a  mov     r8, cs:off_140012018
0x140005a31  mov     rdx, [r14]
0x140005a34  mov     rax, [rcx+650h]
0x140005a3b  mov     rcx, cs:WdfDriverGlobals
0x140005a42  call    _guard_dispatch_icall
0x140005a47  mov     [rax], r12
0x140005a4a  mov     [rax+8], r15
0x140005a4e  mov     [rax+10h], rsi
0x140005a52  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140005a59  add     rax, 40h ; '@'
0x140005a5d  mov     rcx, [rax+8]
0x140005a61  cmp     [rcx], rax
0x140005a64  jnz     loc_140005B52
0x140005a6a  mov     [rbx], rax
0x140005a6d  mov     [rbx+8], rcx
0x140005a71  mov     [rcx], rbx
0x140005a74  mov     [rax+8], rbx
0x140005a78  mov     rax, cs:WdfFunctions_01015
0x140005a7f  mov     rdx, [r14]
0x140005a82  mov     rcx, cs:WdfDriverGlobals
0x140005a89  mov     rax, [rax+0BE0h]
0x140005a90  call    _guard_dispatch_icall
0x140005a95  jmp     loc_140005B27
0x140005a9a  mov     eax, cs:dword_140012050
0x140005aa0  cmp     eax, 2
0x140005aa3  jbe     short loc_140005AD1
0x140005aa5  lea     rax, aWdfworkitemcre; "WdfWorkItemCreate for RoutePolicyAsyncC"...
0x140005aac  mov     dword ptr [rbp+57h+var_C0], edi
0x140005aaf  mov     [rbp+57h+var_B8], rax
0x140005ab3  lea     rdx, unk_14000FED8
0x140005aba  lea     rax, [rbp+57h+var_C0]
0x140005abe  mov     [rsp+0F0h+var_C8], rax
0x140005ac3  lea     rax, [rbp+57h+var_B8]
0x140005ac7  mov     qword ptr [rsp+0F0h+var_D0], rax
0x140005acc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140005ad1  mov     edx, 64667072h; Tag
0x140005ad6  mov     rcx, rbx; P
0x140005ad9  call    cs:__imp_ExFreePoolWithTag
0x140005ae0  nop     dword ptr [rax+rax+00h]
0x140005ae5  jmp     short loc_140005B27
0x140005ae7  mov     eax, cs:dword_140012050
0x140005aed  mov     edi, 0C000009Ah
0x140005af2  cmp     eax, 2
0x140005af5  jbe     short loc_140005B27
0x140005af7  lea     rax, aFailedToAlloca_5; "Failed to allocate work item list entry"
0x140005afe  mov     dword ptr [rbp+57h+var_C0], 0C000009Ah
0x140005b05  mov     [rbp+57h+var_B8], rax
0x140005b09  lea     rdx, word_14000FA7A
0x140005b10  lea     rax, [rbp+57h+var_C0]
0x140005b14  mov     [rsp+0F0h+var_C8], rax
0x140005b19  lea     rax, [rbp+57h+var_B8]
0x140005b1d  mov     qword ptr [rsp+0F0h+var_D0], rax
0x140005b22  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140005b27  mov     eax, edi
0x140005b29  mov     rcx, [rbp+57h+var_30]
0x140005b2d  xor     rcx, rsp; StackCookie
0x140005b30  call    __security_check_cookie
0x140005b35  lea     r11, [rsp+0F0h+var_20]
0x140005b3d  mov     rbx, [r11+40h]
0x140005b41  mov     rsi, [r11+48h]
0x140005b45  mov     rsp, r11
0x140005b48  pop     r15
0x140005b4a  pop     r14
0x140005b4c  pop     r12
0x140005b4e  pop     rdi
0x140005b4f  pop     rbp
0x140005b50  retn
0x140005b52  mov     ecx, 3
0x140005b57  int     29h; Win8: RtlFailFast(ecx)
```
