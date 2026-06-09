# FwRulesEnum::Initialize(FwPolicyViewFlags,_tag_FW_QUERY *,ulong)

- ea: `0x18000bb40`
- end: `0x18000be56`
- name: `?Initialize@FwRulesEnum@@AEAAJW4FwPolicyViewFlags@@PEAU_tag_FW_QUERY@@K@Z`
- size: `790`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001c680`
- `0x18001c834`

## callees

- `0x180005e0c`
- `0x18000a530`
- `0x18000bb40`
- `0x18000d0f0`
- `0x1800294b0`
- `0x18003336c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000bc70`
- `ntdll!EtwEventWrite` at `0x18000bd1d`
- `ntdll!EtwEventWrite` at `0x18000bc70`
- `ntdll!EtwEventWrite` at `0x18000bd1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000bc92`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000bc92`
- `fwbase!FwReportReturnError` at `0x18000bd79`
- `fwbase!FwReportReturnError` at `0x18000bd8e`
- `fwbase!FwReportReturnError` at `0x18000bd79`
- `fwbase!FwReportReturnError` at `0x18000bd8e`

## pseudocode

```c
__int64 __fastcall FwRulesEnum::Initialize(__int64 a1, int a2, int *a3, int a4)
{
  int v8; // eax
  signed int v9; // ebx
  __int64 v10; // rbx
  unsigned int v11; // eax
  bool v12; // sf
  __int64 result; // rax
  int v14; // eax
  _QWORD *v15; // [rsp+28h] [rbp-B0h]
  int v16; // [rsp+60h] [rbp-78h] BYREF
  int v17; // [rsp+64h] [rbp-74h]
  __int128 *v18; // [rsp+68h] [rbp-70h]
  __int64 v19; // [rsp+70h] [rbp-68h]
  __int128 v20; // [rsp+78h] [rbp-60h] BYREF
  __int64 v21; // [rsp+88h] [rbp-50h] BYREF
  int v22; // [rsp+90h] [rbp-48h]
  int v23; // [rsp+98h] [rbp-40h]

  v16 = 532;
  v17 = 1;
  v20 = 0;
  v18 = 0;
  v19 = 0x10000;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_098d31ae94223bbae5defc232583cd37_Traceguids);
  *(_QWORD *)(a1 + 80) = a3;
  if ( !a3 )
  {
    LODWORD(v20) = 1;
    *((_QWORD *)&v20 + 1) = &v21;
    a3 = &v16;
    v17 = 1;
    v18 = &v20;
    v21 = 1;
    v22 = 3;
    v23 = 196608;
  }
  *(_DWORD *)(a1 + 64) = a4;
  v15 = (_QWORD *)(a1 + 88);
  if ( (a2 & 1) != 0 )
  {
    v14 = FWOpenPolicyStore(0x221u, 0, 4u, 1u, 0, v15);
    v9 = v14;
    if ( v14 > 0 )
      v9 = (unsigned __int16)v14 | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_20;
  }
  else
  {
    v8 = FWOpenPolicyStore(0x221u, 0, 2u, 1u, 0, v15);
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_20;
  }
  v10 = *(_QWORD *)(a1 + 88);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_QueryFirewallRules, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  GetTickCount64();
  v11 = Int_FWQueryObject(
          0,
          (unsigned int)FWVerifyFirewallRuleQuery,
          (unsigned int)RPC_FWQueryFirewallRules,
          (unsigned int)RRPC_FWQueryFirewallRules,
          (__int64)Int_RPC_FWEnumFirewallRules2_0,
          (__int64)Int_RRPC_FWEnumFirewallRules2_0,
          v10,
          (__int64)a3,
          7,
          a1 + 104,
          a1 + 96,
          0);
  v9 = v11;
  if ( v11 && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v11);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_QueryFirewallRules, 0, 0);
  v12 = v9 < 0;
  if ( v9 > 0 )
  {
    v9 = (unsigned __int16)v9 | 0x80070000;
    v12 = v9 < 0;
  }
  if ( !v12 )
  {
    *(_QWORD *)(a1 + 112) = *(_QWORD *)(a1 + 96);
    result = (unsigned int)v9;
    *(_DWORD *)(a1 + 120) = 0;
    *(_DWORD *)(a1 + 72) = a2;
    return result;
  }
LABEL_20:
  FwReportReturnError("FwRulesEnum::Initialize", (unsigned int)v9);
  return FwReportReturnError("FwRulesEnum::Initialize", (unsigned int)v9);
}

```

## disassembly

```asm
0x18000bb40  mov     [rsp+arg_8], rbx
0x18000bb45  mov     [rsp+arg_18], rbp
0x18000bb4a  push    rsi
0x18000bb4b  push    rdi
0x18000bb4c  push    r12
0x18000bb4e  push    r14
0x18000bb50  push    r15
0x18000bb52  sub     rsp, 0B0h
0x18000bb59  mov     rax, cs:__security_cookie
0x18000bb60  xor     rax, rsp
0x18000bb63  mov     [rsp+0D8h+var_38], rax
0x18000bb6b  xorps   xmm0, xmm0
0x18000bb6e  mov     [rsp+0D8h+var_78], 214h
0x18000bb76  xor     r15d, r15d
0x18000bb79  mov     [rsp+0D8h+var_74], 1
0x18000bb81  movups  [rsp+0D8h+var_60], xmm0
0x18000bb86  mov     [rsp+0D8h+var_70], r15
0x18000bb8b  mov     ebx, r9d
0x18000bb8e  mov     rsi, r8
0x18000bb91  mov     [rsp+0D8h+var_68], 10000h
0x18000bb9a  mov     ebp, edx
0x18000bb9c  mov     rdi, rcx
0x18000bb9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bba6  lea     r12, WPP_GLOBAL_Control
0x18000bbad  cmp     rcx, r12
0x18000bbb0  jnz     loc_18000BD9C
0x18000bbb6  mov     [rdi+50h], rsi
0x18000bbba  test    rsi, rsi
0x18000bbbd  jnz     short loc_18000BC10
0x18000bbbf  lea     rax, [rsp+0D8h+var_50]
0x18000bbc7  mov     dword ptr [rsp+0D8h+var_60], 1
0x18000bbcf  mov     qword ptr [rsp+0D8h+var_60+8], rax
0x18000bbd7  lea     rsi, [rsp+0D8h+var_78]
0x18000bbdc  lea     rax, [rsp+0D8h+var_60]
0x18000bbe1  mov     [rsp+0D8h+var_74], 1
0x18000bbe9  mov     [rsp+0D8h+var_70], rax
0x18000bbee  mov     [rsp+0D8h+var_50], 1
0x18000bbfa  mov     [rsp+0D8h+var_48], 3
0x18000bc05  mov     [rsp+0D8h+var_40], 30000h
0x18000bc10  lea     r14, [rdi+58h]
0x18000bc14  mov     [rdi+40h], ebx
0x18000bc17  xor     edx, edx
0x18000bc19  mov     [rsp+0D8h+var_B0], r14
0x18000bc1e  mov     r9d, 1
0x18000bc24  mov     dword ptr [rsp+0D8h+var_B8], r15d
0x18000bc29  mov     ecx, 221h
0x18000bc2e  test    r9b, bpl
0x18000bc31  jnz     loc_18000BDDE
0x18000bc37  mov     r8d, 2
0x18000bc3d  call    FWOpenPolicyStore
0x18000bc42  mov     ebx, eax
0x18000bc44  test    eax, eax
0x18000bc46  jg      loc_18000BDC0
0x18000bc4c  test    ebx, ebx
0x18000bc4e  js      loc_18000BD70
0x18000bc54  mov     rcx, cs:g_Provider
0x18000bc5b  mov     rbx, [r14]
0x18000bc5e  test    rcx, rcx
0x18000bc61  jz      short loc_18000BC7C
0x18000bc63  xor     r9d, r9d
0x18000bc66  lea     rdx, MPS_CLNT_API_Enter_QueryFirewallRules
0x18000bc6d  xor     r8d, r8d
0x18000bc70  call    cs:__imp_EtwEventWrite
0x18000bc77  nop     dword ptr [rax+rax+00h]
0x18000bc7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc83  cmp     rcx, r12
0x18000bc86  jz      short loc_18000BC92
0x18000bc88  test    byte ptr [rcx+1Ch], 8
0x18000bc8c  jnz     loc_18000BE05
0x18000bc92  call    cs:__imp_GetTickCount64
0x18000bc99  nop     dword ptr [rax+rax+00h]
0x18000bc9e  mov     [rsp+0D8h+var_80], r15d
0x18000bca3  lea     rax, [rdi+68h]
0x18000bca7  lea     r14, [rdi+60h]
0x18000bcab  xor     ecx, ecx
0x18000bcad  mov     [rsp+0D8h+var_88], r14
0x18000bcb2  lea     r9, RRPC_FWQueryFirewallRules
0x18000bcb9  mov     [rsp+0D8h+var_90], rax
0x18000bcbe  lea     r8, RPC_FWQueryFirewallRules
0x18000bcc5  mov     [rsp+0D8h+var_98], 7
0x18000bccc  lea     rax, ?Int_RRPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RRPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000bcd3  mov     [rsp+0D8h+var_A0], rsi
0x18000bcd8  lea     rdx, FWVerifyFirewallRuleQuery
0x18000bcdf  mov     [rsp+0D8h+var_A8], rbx
0x18000bce4  mov     [rsp+0D8h+var_B0], rax
0x18000bce9  lea     rax, ?Int_RPC_FWEnumFirewallRules2_0@@YAKPEAX0KKGPEAKPEAPEAX@Z; Int_RPC_FWEnumFirewallRules2_0(void *,void *,ulong,ulong,ushort,ulong *,void * *)
0x18000bcf0  mov     [rsp+0D8h+var_B8], rax
0x18000bcf5  call    Int_FWQueryObject
0x18000bcfa  mov     ebx, eax
0x18000bcfc  test    eax, eax
0x18000bcfe  jnz     loc_18000BE1F
0x18000bd04  mov     rcx, cs:g_Provider
0x18000bd0b  test    rcx, rcx
0x18000bd0e  jz      short loc_18000BD29
0x18000bd10  xor     r9d, r9d
0x18000bd13  lea     rdx, MPS_CLNT_API_Exit_QueryFirewallRules
0x18000bd1a  xor     r8d, r8d
0x18000bd1d  call    cs:__imp_EtwEventWrite
0x18000bd24  nop     dword ptr [rax+rax+00h]
0x18000bd29  test    ebx, ebx
0x18000bd2b  jg      loc_18000BDCE
0x18000bd31  js      short loc_18000BD70
0x18000bd33  mov     rax, [r14]
0x18000bd36  mov     [rdi+70h], rax
0x18000bd3a  mov     eax, ebx
0x18000bd3c  mov     [rdi+78h], r15d
0x18000bd40  mov     [rdi+48h], ebp
0x18000bd43  mov     rcx, [rsp+0D8h+var_38]
0x18000bd4b  xor     rcx, rsp; StackCookie
0x18000bd4e  call    __security_check_cookie
0x18000bd53  lea     r11, [rsp+0D8h+var_28]
0x18000bd5b  mov     rbx, [r11+38h]
0x18000bd5f  mov     rbp, [r11+48h]
0x18000bd63  mov     rsp, r11
0x18000bd66  pop     r15
0x18000bd68  pop     r14
0x18000bd6a  pop     r12
0x18000bd6c  pop     rdi
0x18000bd6d  pop     rsi
0x18000bd6e  retn
0x18000bd70  mov     edx, ebx
0x18000bd72  lea     rcx, aFwrulesenumIni; "FwRulesEnum::Initialize"
0x18000bd79  call    cs:__imp_FwReportReturnError
0x18000bd80  nop     dword ptr [rax+rax+00h]
0x18000bd85  mov     edx, ebx
0x18000bd87  lea     rcx, aFwrulesenumIni; "FwRulesEnum::Initialize"
0x18000bd8e  call    cs:__imp_FwReportReturnError
0x18000bd95  nop     dword ptr [rax+rax+00h]
0x18000bd9a  jmp     short loc_18000BD43
0x18000bd9c  test    byte ptr [rcx+1Ch], 8
0x18000bda0  jz      loc_18000BBB6
0x18000bda6  mov     rcx, [rcx+10h]
0x18000bdaa  lea     r8, WPP_098d31ae94223bbae5defc232583cd37_Traceguids
0x18000bdb1  mov     edx, 0Ch
0x18000bdb6  call    WPP_SF_
0x18000bdbb  jmp     loc_18000BBB6
0x18000bdc0  movzx   ebx, ax
0x18000bdc3  or      ebx, 80070000h
0x18000bdc9  jmp     loc_18000BC4C
0x18000bdce  movzx   ebx, bx
0x18000bdd1  or      ebx, 80070000h
0x18000bdd7  test    ebx, ebx
0x18000bdd9  jmp     loc_18000BD31
0x18000bdde  mov     r8d, 4
0x18000bde4  call    FWOpenPolicyStore
0x18000bde9  mov     ebx, eax
0x18000bdeb  test    eax, eax
0x18000bded  jle     short loc_18000BDF8
0x18000bdef  movzx   ebx, ax
0x18000bdf2  or      ebx, 80070000h
0x18000bdf8  test    ebx, ebx
0x18000bdfa  js      loc_18000BD70
0x18000be00  jmp     loc_18000BC54
0x18000be05  mov     rcx, [rcx+10h]
0x18000be09  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000be10  mov     edx, 0B6h
0x18000be15  call    WPP_SF_
0x18000be1a  jmp     loc_18000BC92
0x18000be1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be26  cmp     rcx, r12
0x18000be29  jz      loc_18000BD04
0x18000be2f  test    byte ptr [rcx+1Ch], 1
0x18000be33  jz      loc_18000BD04
0x18000be39  mov     rcx, [rcx+10h]
0x18000be3d  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18000be44  mov     edx, 0B7h
0x18000be49  mov     r9d, ebx
0x18000be4c  call    WPP_SF_d
0x18000be51  jmp     loc_18000BD04
```
