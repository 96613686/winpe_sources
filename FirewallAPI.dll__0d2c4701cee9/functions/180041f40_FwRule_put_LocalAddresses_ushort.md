# FwRule::put_LocalAddresses(ushort *)

- ea: `0x180041f40`
- end: `0x180042181`
- name: `?put_LocalAddresses@FwRule@@UEAAJPEAG@Z`
- size: `577`
- prototype: `__int64 __fastcall(FwRule *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180012dcc`
- `0x180013e8c`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003336c`
- `0x18003a5bc`
- `0x180041f40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041fec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041fec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042124`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042124`
- `fwbase!FwReportReturnError` at `0x180042114`
- `fwbase!FwReportReturnError` at `0x18004214e`
- `fwbase!FwReportReturnError` at `0x180042114`
- `fwbase!FwReportReturnError` at `0x18004214e`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x180042000`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x180042000`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180042135`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180042135`

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
0x180041f40  mov     [rsp-8+arg_10], rbx
0x180041f45  push    rbp
0x180041f46  push    rsi
0x180041f47  push    rdi
0x180041f48  lea     rbp, [rsp-180h]
0x180041f50  sub     rsp, 280h
0x180041f57  mov     rax, cs:__security_cookie
0x180041f5e  xor     rax, rsp
0x180041f61  mov     [rbp+190h+var_20], rax
0x180041f68  mov     rbx, rdx
0x180041f6b  mov     rdi, rcx
0x180041f6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f75  lea     rsi, WPP_GLOBAL_Control
0x180041f7c  cmp     rcx, rsi
0x180041f7f  jz      short loc_180041FC6
0x180041f81  test    byte ptr [rcx+1Ch], 8
0x180041f85  jz      short loc_180041FA3
0x180041f87  mov     rcx, [rcx+10h]
0x180041f8b  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180041f92  mov     edx, 20h ; ' '
0x180041f97  call    WPP_SF_
0x180041f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180041fa3  cmp     rcx, rsi
0x180041fa6  jz      short loc_180041FC6
0x180041fa8  test    byte ptr [rcx+1Ch], 4
0x180041fac  jz      short loc_180041FC6
0x180041fae  mov     rcx, [rcx+10h]
0x180041fb2  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180041fb9  mov     edx, 21h ; '!'
0x180041fbe  mov     r9, rbx
0x180041fc1  call    WPP_SF_S
0x180041fc6  xor     edx, edx; Val
0x180041fc8  lea     rcx, [rsp+290h+var_270]; void *
0x180041fcd  lea     r8d, [rdx+48h]; Size
0x180041fd1  call    memset_0
0x180041fd6  xor     edx, edx; Val
0x180041fd8  lea     rcx, [rsp+290h+var_220]; void *
0x180041fdd  mov     r8d, 1F8h; Size
0x180041fe3  call    memset_0
0x180041fe8  lea     rcx, [rdi+10h]; lpCriticalSection
0x180041fec  call    cs:__imp_EnterCriticalSection
0x180041ff3  nop     dword ptr [rax+rax+00h]
0x180041ff8  lea     rdx, [rsp+290h+var_270]
0x180041ffd  mov     rcx, rbx
0x180042000  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x180042007  nop     dword ptr [rax+rax+00h]
0x18004200c  mov     ebx, eax
0x18004200e  test    eax, eax
0x180042010  js      loc_18004210B
0x180042016  cmp     qword ptr [rdi+50h], 0
0x18004201b  jnz     short loc_18004202F
0x18004201d  mov     rcx, rdi; this
0x180042020  call    ?CreateRule@FwRule@@AEAAJXZ; FwRule::CreateRule(void)
0x180042025  mov     ebx, eax
0x180042027  test    eax, eax
0x180042029  js      loc_18004210B
0x18004202f  mov     rax, [rdi+50h]
0x180042033  lea     rdx, [rsp+290h+var_220]
0x180042038  mov     ecx, 3
0x18004203d  lea     r8d, [rcx+7Dh]
0x180042041  movups  xmm0, xmmword ptr [rax]
0x180042044  movups  xmmword ptr [rdx], xmm0
0x180042047  movups  xmm1, xmmword ptr [rax+10h]
0x18004204b  movups  xmmword ptr [rdx+10h], xmm1
0x18004204f  movups  xmm0, xmmword ptr [rax+20h]
0x180042053  movups  xmmword ptr [rdx+20h], xmm0
0x180042057  movups  xmm1, xmmword ptr [rax+30h]
0x18004205b  movups  xmmword ptr [rdx+30h], xmm1
0x18004205f  movups  xmm0, xmmword ptr [rax+40h]
0x180042063  movups  xmmword ptr [rdx+40h], xmm0
0x180042067  movups  xmm1, xmmword ptr [rax+50h]
0x18004206b  movups  xmmword ptr [rdx+50h], xmm1
0x18004206f  movups  xmm0, xmmword ptr [rax+60h]
0x180042073  movups  xmmword ptr [rdx+60h], xmm0
0x180042077  movups  xmm1, xmmword ptr [rax+70h]
0x18004207b  add     rax, r8
0x18004207e  movups  xmmword ptr [rdx+70h], xmm1
0x180042082  add     rdx, r8
0x180042085  sub     rcx, 1
0x180042089  jnz     short loc_180042041
0x18004208b  movups  xmm0, xmmword ptr [rax]
0x18004208e  mov     rcx, rdi; this
0x180042091  movups  xmmword ptr [rdx], xmm0
0x180042094  movups  xmm1, xmmword ptr [rax+10h]
0x180042098  movups  xmmword ptr [rdx+10h], xmm1
0x18004209c  movups  xmm0, xmmword ptr [rax+20h]
0x1800420a0  movups  xmmword ptr [rdx+20h], xmm0
0x1800420a4  movups  xmm1, xmmword ptr [rax+30h]
0x1800420a8  movups  xmmword ptr [rdx+30h], xmm1
0x1800420ac  movups  xmm0, xmmword ptr [rax+40h]
0x1800420b0  movups  xmmword ptr [rdx+40h], xmm0
0x1800420b4  movups  xmm1, xmmword ptr [rax+50h]
0x1800420b8  movups  xmmword ptr [rdx+50h], xmm1
0x1800420bc  movups  xmm0, xmmword ptr [rax+60h]
0x1800420c0  movaps  xmm1, [rsp+290h+var_260]
0x1800420c5  movups  xmmword ptr [rdx+60h], xmm0
0x1800420c9  mov     rax, [rax+70h]
0x1800420cd  movaps  xmm0, [rsp+290h+var_270]
0x1800420d2  mov     [rdx+70h], rax
0x1800420d6  lea     rdx, [rsp+290h+var_220]; struct _tag_FW_RULE *
0x1800420db  movups  [rbp+190h+var_1B8], xmm0
0x1800420df  movaps  xmm0, [rsp+290h+var_250]
0x1800420e4  movups  [rbp+190h+var_198], xmm0
0x1800420e8  movsd   xmm0, [rsp+290h+var_230]
0x1800420ee  movups  [rbp+190h+var_1A8], xmm1
0x1800420f2  movaps  xmm1, [rsp+290h+var_240]
0x1800420f7  movsd   [rbp+190h+var_178], xmm0
0x1800420fc  movups  [rbp+190h+var_188], xmm1
0x180042100  call    ?SetRule@FwRule@@AEAAJPEBU_tag_FW_RULE@@@Z; FwRule::SetRule(_tag_FW_RULE const *)
0x180042105  mov     ebx, eax
0x180042107  test    eax, eax
0x180042109  jns     short loc_180042120
0x18004210b  mov     edx, eax
0x18004210d  lea     rcx, aFwrulePutLocal_1; "FwRule::put_LocalAddresses"
0x180042114  call    cs:__imp_FwReportReturnError
0x18004211b  nop     dword ptr [rax+rax+00h]
0x180042120  lea     rcx, [rdi+10h]; lpCriticalSection
0x180042124  call    cs:__imp_LeaveCriticalSection
0x18004212b  nop     dword ptr [rax+rax+00h]
0x180042130  lea     rcx, [rsp+290h+var_270]
0x180042135  call    cs:__imp_FwPolioEmptyWFAddresses
0x18004213c  nop     dword ptr [rax+rax+00h]
0x180042141  test    ebx, ebx
0x180042143  jns     short loc_18004215C
0x180042145  mov     edx, ebx
0x180042147  lea     rcx, aFwrulePutLocal_1; "FwRule::put_LocalAddresses"
0x18004214e  call    cs:__imp_FwReportReturnError
0x180042155  nop     dword ptr [rax+rax+00h]
0x18004215a  mov     ebx, eax
0x18004215c  mov     eax, ebx
0x18004215e  mov     rcx, [rbp+190h+var_20]
0x180042165  xor     rcx, rsp; StackCookie
0x180042168  call    __security_check_cookie
0x18004216d  mov     rbx, [rsp+290h+arg_10]
0x180042175  add     rsp, 280h
0x18004217c  pop     rdi
0x18004217d  pop     rsi
0x18004217e  pop     rbp
0x18004217f  retn
```
