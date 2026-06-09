# FwDiagResolveAddPortException

- ea: `0x1800090a0`
- end: `0x180009303`
- name: `FwDiagResolveAddPortException`
- size: `611`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180005dc0`
- `0x1800090a0`
- `0x18000c572`
- `0x18000c5b0`

## import_xrefs

- `FirewallAPI!FWGetGlobalConfig` at `0x180009123`
- `FirewallAPI!FWGetGlobalConfig` at `0x180009123`
- `FirewallAPI!FWOpenPolicyStore` at `0x18000919d`
- `FirewallAPI!FWOpenPolicyStore` at `0x18000919d`
- `FirewallAPI!FWClosePolicyStore` at `0x1800092b9`
- `FirewallAPI!FWClosePolicyStore` at `0x1800092b9`
- `FirewallAPI!FWAddFirewallRule` at `0x18000928f`
- `FirewallAPI!FWAddFirewallRule` at `0x18000928f`
- `RPCRT4!UuidCreate` at `0x1800091b4`
- `RPCRT4!UuidCreate` at `0x1800091b4`
- `RPCRT4!UuidToStringW` at `0x1800091d0`
- `RPCRT4!UuidToStringW` at `0x1800091d0`
- `RPCRT4!RpcStringFreeW` at `0x1800092cb`
- `RPCRT4!RpcStringFreeW` at `0x1800092cb`

## pseudocode

```c
__int64 __fastcall FwDiagResolveAddPortException(__int64 a1)
{
  __int64 result; // rax
  __int16 v3; // si
  int v4; // edi
  int v5; // r14d
  unsigned int v6; // ebx
  const wchar_t *v7; // r9
  __int64 v8; // [rsp+28h] [rbp-E0h]
  __int64 v9; // [rsp+48h] [rbp-C0h] BYREF
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v11; // [rsp+58h] [rbp-B0h] BYREF
  _WORD v12[8]; // [rsp+68h] [rbp-A0h] BYREF
  RPC_WSTR v13; // [rsp+78h] [rbp-90h]
  unsigned __int16 *v14; // [rsp+80h] [rbp-88h]
  int v15; // [rsp+90h] [rbp-78h]
  int v16; // [rsp+94h] [rbp-74h]
  __int16 v17; // [rsp+98h] [rbp-70h]
  int v18; // [rsp+A8h] [rbp-60h]
  __int64 *v19; // [rsp+B0h] [rbp-58h]
  int v20; // [rsp+C0h] [rbp-48h]
  __int64 *v21; // [rsp+C8h] [rbp-40h]
  int v22; // [rsp+188h] [rbp+80h]
  __int16 v23; // [rsp+18Ch] [rbp+84h]
  UUID Uuid; // [rsp+268h] [rbp+160h] BYREF
  unsigned __int16 v25[512]; // [rsp+278h] [rbp+170h] BYREF

  if ( !a1 || !*(_QWORD *)(a1 + 16) )
    return 87;
  v9 = 4;
  result = FWGetGlobalConfig(545, 0, 5, 2, 0, (char *)&v9 + 4, &v9);
  if ( !(_DWORD)result )
  {
    v3 = *(_WORD *)(a1 + 18);
    v4 = *(unsigned __int16 *)(a1 + 16);
    v5 = *(_DWORD *)(a1 + 8);
    v11 = 0;
    Uuid = 0;
    StringUuid = 0;
    LODWORD(v9) = 0;
    memset_0(v12, 0, 0x1F8u);
    v6 = FWOpenPolicyStore(545, 0, 2, 2, 0, &v11);
    if ( !v6 )
    {
      v6 = UuidCreate(&Uuid);
      if ( !v6 )
      {
        v6 = UuidToStringW(&Uuid, &StringUuid);
        if ( !v6 )
        {
          v23 |= 1u;
          v15 = HIDWORD(v9);
          v13 = StringUuid;
          v12[4] = 545;
          v17 = v3;
          v22 = 3;
          WORD1(v9) = v4;
          LOWORD(v9) = v4;
          if ( v5 )
          {
            v16 = 1;
            v18 = 1;
            v19 = &v9;
          }
          else
          {
            v16 = 2;
            v20 = 1;
            v21 = &v9;
          }
          LODWORD(v8) = v4;
          v7 = L"TCP";
          if ( v3 != 6 )
            v7 = L"UDP";
          StringCchPrintfW(v25, 0x200u, L"%s : %d", v7, v8);
          v14 = v25;
          v6 = FWAddFirewallRule(v11, v12);
        }
      }
    }
    if ( v11 )
      FWClosePolicyStore();
    if ( StringUuid )
      RpcStringFreeW(&StringUuid);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1800090a0  mov     r11, rsp
0x1800090a3  push    rbp
0x1800090a4  push    rbx
0x1800090a5  lea     rbp, [r11-5A8h]
0x1800090ac  sub     rsp, 698h
0x1800090b3  mov     rax, cs:__security_cookie
0x1800090ba  xor     rax, rsp
0x1800090bd  mov     [rbp+5A0h+var_30], rax
0x1800090c4  mov     rbx, rcx
0x1800090c7  test    rcx, rcx
0x1800090ca  jz      loc_1800092FC
0x1800090d0  cmp     qword ptr [rcx+10h], 0
0x1800090d5  jz      loc_1800092FC
0x1800090db  mov     [r11-18h], r12
0x1800090df  lea     rax, [rsp+6A0h+var_660]
0x1800090e4  mov     [rsp+30h], rax
0x1800090e9  mov     r12d, 221h
0x1800090ef  lea     rax, [rsp+6A0h+var_660+4]
0x1800090f4  mov     [r11-28h], r15
0x1800090f8  xor     r15d, r15d
0x1800090fb  mov     [rsp+6A0h+var_678], rax
0x180009100  mov     ecx, r12d
0x180009103  mov     dword ptr [rsp+6A0h+var_680], r15d
0x180009108  xor     edx, edx
0x18000910a  mov     dword ptr [rsp+6A0h+var_660], 4
0x180009112  mov     r9d, 2
0x180009118  mov     dword ptr [rsp+6A0h+var_660+4], r15d
0x18000911d  mov     r8d, 5
0x180009123  call    cs:__imp_FWGetGlobalConfig
0x180009129  test    eax, eax
0x18000912b  jnz     loc_1800092D3
0x180009131  mov     [rsp+6A0h+arg_8], rsi
0x180009139  lea     rcx, [rsp+6A0h+var_640]; void *
0x18000913e  movzx   esi, word ptr [rbx+12h]
0x180009142  xorps   xmm0, xmm0
0x180009145  mov     [rsp+6A0h+arg_10], rdi
0x18000914d  xor     edx, edx; Val
0x18000914f  movzx   edi, word ptr [rbx+10h]
0x180009153  mov     r8d, 1F8h; Size
0x180009159  mov     [rsp+6A0h+var_18], r14
0x180009161  mov     r14d, [rbx+8]
0x180009165  mov     [rsp+6A0h+var_650], r15
0x18000916a  movups  xmmword ptr [rbp+5A0h+Uuid.Data1], xmm0
0x180009171  mov     [rsp+6A0h+StringUuid], r15
0x180009176  mov     dword ptr [rsp+6A0h+var_660], r15d
0x18000917b  call    memset_0
0x180009180  lea     rax, [rsp+6A0h+var_650]
0x180009185  mov     r9d, 2
0x18000918b  mov     [rsp+6A0h+var_678], rax
0x180009190  mov     r8d, r9d
0x180009193  mov     ecx, r12d
0x180009196  mov     dword ptr [rsp+6A0h+var_680], r15d
0x18000919b  xor     edx, edx
0x18000919d  call    cs:__imp_FWOpenPolicyStore
0x1800091a3  mov     ebx, eax
0x1800091a5  test    eax, eax
0x1800091a7  jnz     loc_180009297
0x1800091ad  lea     rcx, [rbp+5A0h+Uuid]; Uuid
0x1800091b4  call    cs:__imp_UuidCreate
0x1800091ba  mov     ebx, eax
0x1800091bc  test    eax, eax
0x1800091be  jnz     loc_180009297
0x1800091c4  lea     rdx, [rsp+6A0h+StringUuid]; StringUuid
0x1800091c9  lea     rcx, [rbp+5A0h+Uuid]; Uuid
0x1800091d0  call    cs:__imp_UuidToStringW
0x1800091d6  mov     ebx, eax
0x1800091d8  test    eax, eax
0x1800091da  jnz     loc_180009297
0x1800091e0  mov     eax, dword ptr [rsp+6A0h+var_660+4]
0x1800091e4  or      [rbp+5A0h+var_51C], 1
0x1800091ec  mov     [rbp+5A0h+var_618], eax
0x1800091ef  mov     rax, [rsp+6A0h+StringUuid]
0x1800091f4  mov     [rsp+6A0h+var_630], rax
0x1800091f9  lea     rax, [rsp+6A0h+var_660]
0x1800091fe  mov     word ptr [rsp+6A0h+var_638], r12w
0x180009204  mov     [rbp+5A0h+var_610], si
0x180009208  mov     [rbp+5A0h+var_520], 3
0x180009212  mov     word ptr [rsp+6A0h+var_660+2], di
0x180009217  mov     word ptr [rsp+6A0h+var_660], di
0x18000921c  test    r14d, r14d
0x18000921f  jz      short loc_180009235
0x180009221  mov     [rbp+5A0h+var_614], 1
0x180009228  mov     [rbp+5A0h+var_600], 1
0x18000922f  mov     [rbp+5A0h+var_5F8], rax
0x180009233  jmp     short loc_180009247
0x180009235  mov     [rbp+5A0h+var_614], 2
0x18000923c  mov     [rbp+5A0h+var_5E8], 1
0x180009243  mov     [rbp+5A0h+var_5E0], rax
0x180009247  lea     rcx, aUdp; "UDP"
0x18000924e  mov     dword ptr [rsp+6A0h+var_680], edi
0x180009252  cmp     si, 6
0x180009256  lea     r9, aTcp; "TCP"
0x18000925d  lea     r8, aSD; "%s : %d"
0x180009264  mov     edx, 200h; unsigned __int64
0x180009269  cmovnz  r9, rcx
0x18000926d  lea     rcx, [rbp+5A0h+var_430]; unsigned __int16 *
0x180009274  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009279  mov     rcx, [rsp+6A0h+var_650]
0x18000927e  lea     rax, [rbp+5A0h+var_430]
0x180009285  lea     rdx, [rsp+6A0h+var_640]
0x18000928a  mov     [rsp+6A0h+var_628], rax
0x18000928f  call    cs:__imp_FWAddFirewallRule
0x180009295  mov     ebx, eax
0x180009297  mov     rcx, [rsp+6A0h+var_650]
0x18000929c  mov     r14, [rsp+6A0h+var_18]
0x1800092a4  mov     rdi, [rsp+6A0h+arg_10]
0x1800092ac  mov     rsi, [rsp+6A0h+arg_8]
0x1800092b4  test    rcx, rcx
0x1800092b7  jz      short loc_1800092BF
0x1800092b9  call    cs:__imp_FWClosePolicyStore
0x1800092bf  cmp     [rsp+6A0h+StringUuid], r15
0x1800092c4  jz      short loc_1800092D1
0x1800092c6  lea     rcx, [rsp+6A0h+StringUuid]; String
0x1800092cb  call    cs:__imp_RpcStringFreeW
0x1800092d1  mov     eax, ebx
0x1800092d3  mov     r12, [rsp+690h]
0x1800092db  mov     r15, [rsp+6A0h+var_20]
0x1800092e3  mov     rcx, [rbp+5A0h+var_30]
0x1800092ea  xor     rcx, rsp; StackCookie
0x1800092ed  call    __security_check_cookie
0x1800092f2  add     rsp, 698h
0x1800092f9  pop     rbx
0x1800092fa  pop     rbp
0x1800092fb  retn
0x1800092fc  mov     eax, 57h ; 'W'
0x180009301  jmp     short loc_1800092E3
```
