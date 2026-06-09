# FwRule::put_RemoteAddresses(ushort *)

- ea: `0x18003f620`
- end: `0x18003f83c`
- name: `?put_RemoteAddresses@FwRule@@UEAAJPEAG@Z`
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
- `0x18003f620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f6cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f6cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f7f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f7f2`
- `fwbase!FwReportReturnError` at `0x18003f7e8`
- `fwbase!FwReportReturnError` at `0x18003f810`
- `fwbase!FwReportReturnError` at `0x18003f7e8`
- `fwbase!FwReportReturnError` at `0x18003f810`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x18003f6da`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x18003f6da`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18003f7fd`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18003f7fd`

## pseudocode

```c
__int64 __fastcall FwRule::put_RemoteAddresses(FwRule *this, unsigned __int16 *a2)
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
  _BYTE v16[176]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v17; // [rsp+120h] [rbp+20h]
  __int128 v18; // [rsp+130h] [rbp+30h]
  __int128 v19; // [rsp+140h] [rbp+40h]
  __int128 v20; // [rsp+150h] [rbp+50h]
  __int64 v21; // [rsp+160h] [rbp+60h]

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)v4 + 2), 36, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids, a2);
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
    FwReportReturnError("FwRule::put_RemoteAddresses", (unsigned int)Rule);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  FwPolioEmptyWFAddresses(v14);
  if ( v6 < 0 )
    return (unsigned int)FwReportReturnError("FwRule::put_RemoteAddresses", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003f620  mov     [rsp-8+arg_10], rbx
0x18003f625  push    rbp
0x18003f626  push    rsi
0x18003f627  push    rdi
0x18003f628  lea     rbp, [rsp-180h]
0x18003f630  sub     rsp, 280h
0x18003f637  mov     rax, cs:__security_cookie
0x18003f63e  xor     rax, rsp
0x18003f641  mov     [rbp+190h+var_20], rax
0x18003f648  mov     rbx, rdx
0x18003f64b  mov     rdi, rcx
0x18003f64e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f655  lea     rsi, WPP_GLOBAL_Control
0x18003f65c  cmp     rcx, rsi
0x18003f65f  jz      short loc_18003F6A6
0x18003f661  test    byte ptr [rcx+1Ch], 8
0x18003f665  jz      short loc_18003F683
0x18003f667  mov     rcx, [rcx+10h]
0x18003f66b  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x18003f672  mov     edx, 23h ; '#'
0x18003f677  call    WPP_SF_
0x18003f67c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f683  cmp     rcx, rsi
0x18003f686  jz      short loc_18003F6A6
0x18003f688  test    byte ptr [rcx+1Ch], 4
0x18003f68c  jz      short loc_18003F6A6
0x18003f68e  mov     rcx, [rcx+10h]
0x18003f692  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x18003f699  mov     edx, 24h ; '$'
0x18003f69e  mov     r9, rbx
0x18003f6a1  call    WPP_SF_S
0x18003f6a6  xor     edx, edx; Val
0x18003f6a8  lea     rcx, [rsp+290h+var_270]; void *
0x18003f6ad  lea     r8d, [rdx+48h]; Size
0x18003f6b1  call    memset_0
0x18003f6b6  xor     edx, edx; Val
0x18003f6b8  lea     rcx, [rsp+290h+var_220]; void *
0x18003f6bd  mov     r8d, 1F8h; Size
0x18003f6c3  call    memset_0
0x18003f6c8  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003f6cc  call    cs:__imp_EnterCriticalSection
0x18003f6d2  lea     rdx, [rsp+290h+var_270]
0x18003f6d7  mov     rcx, rbx
0x18003f6da  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x18003f6e0  mov     ebx, eax
0x18003f6e2  test    eax, eax
0x18003f6e4  js      loc_18003F7DF
0x18003f6ea  cmp     qword ptr [rdi+50h], 0
0x18003f6ef  jnz     short loc_18003F703
0x18003f6f1  mov     rcx, rdi; this
0x18003f6f4  call    ?CreateRule@FwRule@@AEAAJXZ; FwRule::CreateRule(void)
0x18003f6f9  mov     ebx, eax
0x18003f6fb  test    eax, eax
0x18003f6fd  js      loc_18003F7DF
0x18003f703  mov     rax, [rdi+50h]
0x18003f707  lea     rdx, [rsp+290h+var_220]
0x18003f70c  mov     ecx, 3
0x18003f711  lea     r8d, [rcx+7Dh]
0x18003f715  movups  xmm0, xmmword ptr [rax]
0x18003f718  movups  xmmword ptr [rdx], xmm0
0x18003f71b  movups  xmm1, xmmword ptr [rax+10h]
0x18003f71f  movups  xmmword ptr [rdx+10h], xmm1
0x18003f723  movups  xmm0, xmmword ptr [rax+20h]
0x18003f727  movups  xmmword ptr [rdx+20h], xmm0
0x18003f72b  movups  xmm1, xmmword ptr [rax+30h]
0x18003f72f  movups  xmmword ptr [rdx+30h], xmm1
0x18003f733  movups  xmm0, xmmword ptr [rax+40h]
0x18003f737  movups  xmmword ptr [rdx+40h], xmm0
0x18003f73b  movups  xmm1, xmmword ptr [rax+50h]
0x18003f73f  movups  xmmword ptr [rdx+50h], xmm1
0x18003f743  movups  xmm0, xmmword ptr [rax+60h]
0x18003f747  movups  xmmword ptr [rdx+60h], xmm0
0x18003f74b  movups  xmm1, xmmword ptr [rax+70h]
0x18003f74f  add     rax, r8
0x18003f752  movups  xmmword ptr [rdx+70h], xmm1
0x18003f756  add     rdx, r8
0x18003f759  sub     rcx, 1
0x18003f75d  jnz     short loc_18003F715
0x18003f75f  movups  xmm0, xmmword ptr [rax]
0x18003f762  mov     rcx, rdi; this
0x18003f765  movups  xmmword ptr [rdx], xmm0
0x18003f768  movups  xmm1, xmmword ptr [rax+10h]
0x18003f76c  movups  xmmword ptr [rdx+10h], xmm1
0x18003f770  movups  xmm0, xmmword ptr [rax+20h]
0x18003f774  movups  xmmword ptr [rdx+20h], xmm0
0x18003f778  movups  xmm1, xmmword ptr [rax+30h]
0x18003f77c  movups  xmmword ptr [rdx+30h], xmm1
0x18003f780  movups  xmm0, xmmword ptr [rax+40h]
0x18003f784  movups  xmmword ptr [rdx+40h], xmm0
0x18003f788  movups  xmm1, xmmword ptr [rax+50h]
0x18003f78c  movups  xmmword ptr [rdx+50h], xmm1
0x18003f790  movups  xmm0, xmmword ptr [rax+60h]
0x18003f794  movaps  xmm1, [rsp+290h+var_260]
0x18003f799  movups  xmmword ptr [rdx+60h], xmm0
0x18003f79d  mov     rax, [rax+70h]
0x18003f7a1  movaps  xmm0, [rsp+290h+var_270]
0x18003f7a6  mov     [rdx+70h], rax
0x18003f7aa  lea     rdx, [rsp+290h+var_220]; struct _tag_FW_RULE *
0x18003f7af  movaps  [rbp+190h+var_170], xmm0
0x18003f7b3  movaps  xmm0, [rsp+290h+var_250]
0x18003f7b8  movaps  [rbp+190h+var_150], xmm0
0x18003f7bc  movsd   xmm0, [rsp+290h+var_230]
0x18003f7c2  movaps  [rbp+190h+var_160], xmm1
0x18003f7c6  movaps  xmm1, [rsp+290h+var_240]
0x18003f7cb  movsd   [rbp+190h+var_130], xmm0
0x18003f7d0  movaps  [rbp+190h+var_140], xmm1
0x18003f7d4  call    ?SetRule@FwRule@@AEAAJPEBU_tag_FW_RULE@@@Z; FwRule::SetRule(_tag_FW_RULE const *)
0x18003f7d9  mov     ebx, eax
0x18003f7db  test    eax, eax
0x18003f7dd  jns     short loc_18003F7EE
0x18003f7df  mov     edx, eax
0x18003f7e1  lea     rcx, aFwrulePutRemot_1; "FwRule::put_RemoteAddresses"
0x18003f7e8  call    cs:__imp_FwReportReturnError
0x18003f7ee  lea     rcx, [rdi+10h]; lpCriticalSection
0x18003f7f2  call    cs:__imp_LeaveCriticalSection
0x18003f7f8  lea     rcx, [rsp+290h+var_270]
0x18003f7fd  call    cs:__imp_FwPolioEmptyWFAddresses
0x18003f803  test    ebx, ebx
0x18003f805  jns     short loc_18003F818
0x18003f807  mov     edx, ebx
0x18003f809  lea     rcx, aFwrulePutRemot_1; "FwRule::put_RemoteAddresses"
0x18003f810  call    cs:__imp_FwReportReturnError
0x18003f816  mov     ebx, eax
0x18003f818  mov     eax, ebx
0x18003f81a  mov     rcx, [rbp+190h+var_20]
0x18003f821  xor     rcx, rsp; StackCookie
0x18003f824  call    __security_check_cookie
0x18003f829  mov     rbx, [rsp+290h+arg_10]
0x18003f831  add     rsp, 280h
0x18003f838  pop     rdi
0x18003f839  pop     rsi
0x18003f83a  pop     rbp
0x18003f83b  retn
```
