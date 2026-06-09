# BfeFwTriggerEntryFireEvent

- ea: `0x180036170`
- end: `0x1800362e5`
- name: `BfeFwTriggerEntryFireEvent`
- size: `373`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c720`
- `0x18004ade0`

## callees

- `0x18000f1a8`
- `0x180010ad0`
- `0x18001236c`
- `0x180036170`
- `0x180058b30`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800361c9`
- `ntdll!EtwEventWrite` at `0x180036214`
- `ntdll!EtwEventWrite` at `0x1800361c9`
- `ntdll!EtwEventWrite` at `0x180036214`

## string_xrefs

- `0x180036221`: `EtwEventWrite`

## pseudocode

```c
__int64 __fastcall BfeFwTriggerEntryFireEvent(__int64 a1, int a2)
{
  __int64 v2; // rbx
  int v3; // eax
  unsigned int v4; // eax
  __int64 v5; // rcx
  int v7; // r8d
  int v8; // [rsp+30h] [rbp-58h] BYREF
  __int64 v9; // [rsp+38h] [rbp-50h] BYREF
  int v10; // [rsp+40h] [rbp-48h]
  int v11; // [rsp+44h] [rbp-44h]
  _BYTE v12[16]; // [rsp+48h] [rbp-40h] BYREF
  const char *v13; // [rsp+58h] [rbp-30h]
  __int64 v14; // [rsp+60h] [rbp-28h]
  int *v15; // [rsp+68h] [rbp-20h]
  __int64 v16; // [rsp+70h] [rbp-18h]

  v9 = *(_QWORD *)(a1 + 32);
  v2 = 0;
  v3 = *(_DWORD *)(a1 + 48) + 74;
  v11 = 0;
  v10 = v3;
  if ( a2 )
  {
    if ( a2 != 1 )
      return v2;
    if ( *(_DWORD *)(a1 + 28) != 1 )
      return v2;
    v4 = EtwEventWrite(gBfeFwPortEvent, Symbol_FirewallPortCloseEvent, 1, &v9);
    if ( !v4 )
      return v2;
  }
  else
  {
    if ( *(_DWORD *)(a1 + 28) )
      return v2;
    v4 = EtwEventWrite(gBfeFwPortEvent, Symbol_FirewallPortOpenEvent, 1, &v9);
    if ( !v4 )
      return v2;
  }
  v2 = WfpReportSysErrorAsWinError(v5, "EtwEventWrite", v4);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v7, 0, (__int64)"BfeFwTriggerEntryFireEvent", v2);
    }
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
    {
      v8 = v2;
      v15 = &v8;
      v13 = "BfeFwTriggerEntryFireEvent";
      v14 = 27;
      v16 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v7,
        3,
        (__int64)v12);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180036170  mov     [rsp+arg_8], rbx
0x180036175  push    rsi
0x180036176  sub     rsp, 80h
0x18003617d  mov     rax, cs:__security_cookie
0x180036184  xor     rax, rsp
0x180036187  mov     [rsp+88h+var_10], rax
0x18003618c  mov     rax, [rcx+20h]
0x180036190  xor     esi, esi
0x180036192  mov     [rsp+88h+var_50], rax
0x180036197  mov     ebx, esi
0x180036199  mov     eax, [rcx+30h]
0x18003619c  add     eax, 4Ah ; 'J'
0x18003619f  mov     [rsp+88h+var_44], esi
0x1800361a3  mov     [rsp+88h+var_48], eax
0x1800361a7  test    edx, edx
0x1800361a9  jnz     short loc_1800361F4
0x1800361ab  cmp     [rcx+1Ch], ebx
0x1800361ae  jnz     short loc_1800361D3
0x1800361b0  mov     rcx, cs:gBfeFwPortEvent
0x1800361b7  lea     r9, [rsp+88h+var_50]
0x1800361bc  mov     r8d, 1
0x1800361c2  lea     rdx, Symbol_FirewallPortOpenEvent
0x1800361c9  call    cs:__imp_EtwEventWrite
0x1800361cf  test    eax, eax
0x1800361d1  jnz     short loc_18003621E
0x1800361d3  mov     rax, rbx
0x1800361d6  mov     rcx, [rsp+88h+var_10]
0x1800361db  xor     rcx, rsp; StackCookie
0x1800361de  call    __security_check_cookie
0x1800361e3  mov     rbx, [rsp+88h+arg_8]
0x1800361eb  add     rsp, 80h
0x1800361f2  pop     rsi
0x1800361f3  retn
0x1800361f4  cmp     edx, 1
0x1800361f7  jnz     short loc_1800361D3
0x1800361f9  cmp     [rcx+1Ch], edx
0x1800361fc  jnz     short loc_1800361D3
0x1800361fe  mov     rcx, cs:gBfeFwPortEvent
0x180036205  lea     r9, [rsp+88h+var_50]
0x18003620a  mov     r8d, edx
0x18003620d  lea     rdx, Symbol_FirewallPortCloseEvent
0x180036214  call    cs:__imp_EtwEventWrite
0x18003621a  test    eax, eax
0x18003621c  jz      short loc_1800361D3
0x18003621e  mov     r8d, eax
0x180036221  lea     rdx, aEtweventwrite; "EtwEventWrite"
0x180036228  call    WfpReportSysErrorAsWinError
0x18003622d  mov     rbx, rax
0x180036230  test    rax, rax
0x180036233  jz      short loc_1800361D3
0x180036235  mov     [rsp+88h+arg_0], rdi
0x18003623d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036244  lea     rax, WPP_GLOBAL_Control
0x18003624b  lea     rdi, aBfefwtriggeren; "BfeFwTriggerEntryFireEvent"
0x180036252  cmp     rcx, rax
0x180036255  jz      short loc_18003627D
0x180036257  cmp     byte ptr [rcx+19h], 2
0x18003625b  jb      short loc_18003627D
0x18003625d  test    byte ptr [rcx+1Ch], 1
0x180036261  jz      short loc_18003627D
0x180036263  mov     rcx, [rcx+10h]
0x180036267  mov     edx, 1Ah
0x18003626c  mov     [rsp+88h+var_60], ebx
0x180036270  xor     r9d, r9d
0x180036273  mov     [rsp+88h+var_68], rdi
0x180036278  call    WPP_SF_Ssd
0x18003627d  cmp     cs:gWfpLogUserModeErrors, esi
0x180036283  jnz     short loc_180036292
0x180036285  mov     rdi, [rsp+88h+arg_0]
0x18003628d  jmp     loc_1800361D3
0x180036292  test    cs:byte_1800F30F5, 1
0x180036299  jz      short loc_180036285
0x18003629b  lea     rax, [rsp+88h+var_58]
0x1800362a0  mov     [rsp+88h+var_58], ebx
0x1800362a4  mov     [rsp+88h+var_20], rax
0x1800362a9  lea     rdx, WFP_USERMODE_ERROR
0x1800362b0  lea     rax, [rsp+88h+var_40]
0x1800362b5  mov     [rsp+88h+var_30], rdi
0x1800362ba  mov     r9d, 3
0x1800362c0  mov     [rsp+88h+var_68], rax
0x1800362c5  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800362cc  mov     [rsp+88h+var_28], 1Bh
0x1800362d5  mov     [rsp+88h+var_18], 4
0x1800362de  call    McGenEventWrite_EtwEventWriteTransfer
0x1800362e3  jmp     short loc_180036285
```
