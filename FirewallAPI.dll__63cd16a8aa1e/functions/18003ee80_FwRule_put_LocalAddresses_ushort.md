# FwRule::put_LocalAddresses(ushort *)

- ea: `0x18003ee80`
- end: `0x18003f09c`
- name: `?put_LocalAddresses@FwRule@@UEAAJPEAG@Z`
- size: `540`
- prototype: `__int64 __fastcall(FwRule *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180012e88`
- `0x180013e64`
- `0x1800277b0`
- `0x1800284c4`
- `0x18003104c`
- `0x180037c6c`
- `0x18003ee80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ef2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ef2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f052`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f052`
- `fwbase!FwReportReturnError` at `0x18003f048`
- `fwbase!FwReportReturnError` at `0x18003f070`
- `fwbase!FwReportReturnError` at `0x18003f048`
- `fwbase!FwReportReturnError` at `0x18003f070`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x18003ef3a`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x18003ef3a`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18003f05d`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18003f05d`

## pseudocode

```c
__int64 __fastcall FwRule::put_LocalAddresses(FwRule *this, unsigned __int16 *a2)
{
  FwPolicy2 *v4; // rcx
  int Rule; // eax
  int v6; // ebx
  _OWORD *v7; // rax
  _OWORD *v8; // rdx
  __int64 v9; // rcx
  __int128 v10; // xmm1
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  _OWORD v14[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v15; // [rsp+60h] [rbp-A0h]
  _BYTE v16[104]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v17; // [rsp+D8h] [rbp-28h]
  __int128 v18; // [rsp+E8h] [rbp-18h]
  __int128 v19; // [rsp+F8h] [rbp-8h]
  __int128 v20; // [rsp+108h] [rbp+8h]
  __int64 v21; // [rsp+118h] [rbp+18h]

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)v4 + 2), 33, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids, a2);
  }
  memset_0(v14, 0, 0x48u);
  memset_0(v16, 0, 0x1F8u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  Rule = StringToOpenPortOrAuthAppAddress(a2, v14);
  v6 = Rule;
  if ( Rule < 0 )
    goto LABEL_13;
  if ( !*((_QWORD *)this + 10) )
  {
    Rule = FwRule::CreateRule(this);
    v6 = Rule;
    if ( Rule < 0 )
      goto LABEL_13;
  }
  v7 = (_OWORD *)*((_QWORD *)this + 10);
  v8 = v16;
  v9 = 3;
  do
  {
    *v8 = *v7;
    v8[1] = v7[1];
    v8[2] = v7[2];
    v8[3] = v7[3];
    v8[4] = v7[4];
    v8[5] = v7[5];
    v8[6] = v7[6];
    v10 = v7[7];
    v7 += 8;
    v8[7] = v10;
    v8 += 8;
    --v9;
  }
  while ( v9 );
  *v8 = *v7;
  v8[1] = v7[1];
  v8[2] = v7[2];
  v8[3] = v7[3];
  v8[4] = v7[4];
  v8[5] = v7[5];
  v11 = v14[1];
  v8[6] = v7[6];
  v12 = v14[0];
  *((_QWORD *)v8 + 14) = *((_QWORD *)v7 + 14);
  v17 = v12;
  v19 = v14[2];
  v18 = v11;
  v21 = v15;
  v20 = v14[3];
  Rule = FwRule::SetRule(this, (const struct _tag_FW_RULE *)v16);
  v6 = Rule;
  if ( Rule < 0 )
LABEL_13:
    FwReportReturnError("FwRule::put_LocalAddresses", (unsigned int)Rule);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  FwPolioEmptyWFAddresses(v14);
  if ( v6 < 0 )
    return (unsigned int)FwReportReturnError("FwRule::put_LocalAddresses", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003ee80  mov     [rsp-8+arg_10], rbx
0x18003ee85  push    rbp
0x18003ee86  push    rsi
0x18003ee87  push    rdi
0x18003ee88  lea     rbp, [rsp-180h]
0x18003ee90  sub     rsp, 280h
0x18003ee97  mov     rax, cs:__security_cookie
0x18003ee9e  xor     rax, rsp
0x18003eea1  mov     [rbp+190h+var_20], rax
0x18003eea8  mov     rbx, rdx
0x18003eeab  mov     rdi, rcx
0x18003eeae  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eeb5  lea     rsi, WPP_GLOBAL_Control
0x18003eebc  cmp     rcx, rsi
0x18003eebf  jz      short loc_18003EF06
0x18003eec1  test    byte ptr [rcx+1Ch], 8
0x18003eec5  jz      short loc_18003EEE3
0x18003eec7  mov     rcx, [rcx+10h]
0x18003eecb  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x18003eed2  mov     edx, 20h ; ' '
0x18003eed7  call    WPP_SF_
0x18003eedc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eee3  cmp     rcx, rsi
0x18003eee6  jz      short loc_18003EF06
0x18003eee8  test    byte ptr [rcx+1Ch], 4
0x18003eeec  jz      short loc_18003EF06
0x18003eeee  mov     rcx, [rcx+10h]
0x18003eef2  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x18003eef9  mov     edx, 21h ; '!'
0x18003eefe  mov     r9, rbx
0x18003ef01  call    WPP_SF_S
0x18003ef06  xor     edx, edx; Val
0x18003ef08  lea     rcx, [rsp+290h+var_270]; void *
0x18003ef0d  lea     r8d, [rdx+48h]; Size
0x18003ef11  call    memset_0
0x18003ef16  xor     edx, edx; Val
0x18003ef18  lea     rcx, [rsp+290h+var_220]; void *
0x18003ef1d  mov     r8d, 1F8h; Size
0x18003ef23  call    memset_0
0x18003ef28  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003ef2c  call    cs:__imp_EnterCriticalSection
0x18003ef32  lea     rdx, [rsp+290h+var_270]
0x18003ef37  mov     rcx, rbx
0x18003ef3a  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x18003ef40  mov     ebx, eax
0x18003ef42  test    eax, eax
0x18003ef44  js      loc_18003F03F
0x18003ef4a  cmp     qword ptr [rdi+50h], 0
0x18003ef4f  jnz     short loc_18003EF63
0x18003ef51  mov     rcx, rdi; this
0x18003ef54  call    ?CreateRule@FwRule@@AEAAJXZ; FwRule::CreateRule(void)
0x18003ef59  mov     ebx, eax
0x18003ef5b  test    eax, eax
0x18003ef5d  js      loc_18003F03F
0x18003ef63  mov     rax, [rdi+50h]
0x18003ef67  lea     rdx, [rsp+290h+var_220]
0x18003ef6c  mov     ecx, 3
0x18003ef71  lea     r8d, [rcx+7Dh]
0x18003ef75  movups  xmm0, xmmword ptr [rax]
0x18003ef78  movups  xmmword ptr [rdx], xmm0
0x18003ef7b  movups  xmm1, xmmword ptr [rax+10h]
0x18003ef7f  movups  xmmword ptr [rdx+10h], xmm1
0x18003ef83  movups  xmm0, xmmword ptr [rax+20h]
0x18003ef87  movups  xmmword ptr [rdx+20h], xmm0
0x18003ef8b  movups  xmm1, xmmword ptr [rax+30h]
0x18003ef8f  movups  xmmword ptr [rdx+30h], xmm1
0x18003ef93  movups  xmm0, xmmword ptr [rax+40h]
0x18003ef97  movups  xmmword ptr [rdx+40h], xmm0
0x18003ef9b  movups  xmm1, xmmword ptr [rax+50h]
0x18003ef9f  movups  xmmword ptr [rdx+50h], xmm1
0x18003efa3  movups  xmm0, xmmword ptr [rax+60h]
0x18003efa7  movups  xmmword ptr [rdx+60h], xmm0
0x18003efab  movups  xmm1, xmmword ptr [rax+70h]
0x18003efaf  add     rax, r8
0x18003efb2  movups  xmmword ptr [rdx+70h], xmm1
0x18003efb6  add     rdx, r8
0x18003efb9  sub     rcx, 1
0x18003efbd  jnz     short loc_18003EF75
0x18003efbf  movups  xmm0, xmmword ptr [rax]
0x18003efc2  mov     rcx, rdi; this
0x18003efc5  movups  xmmword ptr [rdx], xmm0
0x18003efc8  movups  xmm1, xmmword ptr [rax+10h]
0x18003efcc  movups  xmmword ptr [rdx+10h], xmm1
0x18003efd0  movups  xmm0, xmmword ptr [rax+20h]
0x18003efd4  movups  xmmword ptr [rdx+20h], xmm0
0x18003efd8  movups  xmm1, xmmword ptr [rax+30h]
0x18003efdc  movups  xmmword ptr [rdx+30h], xmm1
0x18003efe0  movups  xmm0, xmmword ptr [rax+40h]
0x18003efe4  movups  xmmword ptr [rdx+40h], xmm0
0x18003efe8  movups  xmm1, xmmword ptr [rax+50h]
0x18003efec  movups  xmmword ptr [rdx+50h], xmm1
0x18003eff0  movups  xmm0, xmmword ptr [rax+60h]
0x18003eff4  movaps  xmm1, [rsp+290h+var_260]
0x18003eff9  movups  xmmword ptr [rdx+60h], xmm0
0x18003effd  mov     rax, [rax+70h]
0x18003f001  movaps  xmm0, [rsp+290h+var_270]
0x18003f006  mov     [rdx+70h], rax
0x18003f00a  lea     rdx, [rsp+290h+var_220]; struct _tag_FW_RULE *
0x18003f00f  movups  [rbp+190h+var_1B8], xmm0
0x18003f013  movaps  xmm0, [rsp+290h+var_250]
0x18003f018  movups  [rbp+190h+var_198], xmm0
0x18003f01c  movsd   xmm0, [rsp+290h+var_230]
0x18003f022  movups  [rbp+190h+var_1A8], xmm1
0x18003f026  movaps  xmm1, [rsp+290h+var_240]
0x18003f02b  movsd   [rbp+190h+var_178], xmm0
0x18003f030  movups  [rbp+190h+var_188], xmm1
0x18003f034  call    ?SetRule@FwRule@@AEAAJPEBU_tag_FW_RULE@@@Z; FwRule::SetRule(_tag_FW_RULE const *)
0x18003f039  mov     ebx, eax
0x18003f03b  test    eax, eax
0x18003f03d  jns     short loc_18003F04E
0x18003f03f  mov     edx, eax
0x18003f041  lea     rcx, aFwrulePutLocal_1; "FwRule::put_LocalAddresses"
0x18003f048  call    cs:__imp_FwReportReturnError
0x18003f04e  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003f052  call    cs:__imp_LeaveCriticalSection
0x18003f058  lea     rcx, [rsp+290h+var_270]
0x18003f05d  call    cs:__imp_FwPolioEmptyWFAddresses
0x18003f063  test    ebx, ebx
0x18003f065  jns     short loc_18003F078
0x18003f067  mov     edx, ebx
0x18003f069  lea     rcx, aFwrulePutLocal_1; "FwRule::put_LocalAddresses"
0x18003f070  call    cs:__imp_FwReportReturnError
0x18003f076  mov     ebx, eax
0x18003f078  mov     eax, ebx
0x18003f07a  mov     rcx, [rbp+190h+var_20]
0x18003f081  xor     rcx, rsp; StackCookie
0x18003f084  call    __security_check_cookie
0x18003f089  mov     rbx, [rsp+290h+arg_10]
0x18003f091  add     rsp, 280h
0x18003f098  pop     rdi
0x18003f099  pop     rsi
0x18003f09a  pop     rbp
0x18003f09b  retn
```
