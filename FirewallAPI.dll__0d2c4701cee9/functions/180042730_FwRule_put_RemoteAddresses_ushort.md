# FwRule::put_RemoteAddresses(ushort *)

- ea: `0x180042730`
- end: `0x180042971`
- name: `?put_RemoteAddresses@FwRule@@UEAAJPEAG@Z`
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
- `0x180042730`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800427dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800427dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042914`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042914`
- `fwbase!FwReportReturnError` at `0x180042904`
- `fwbase!FwReportReturnError` at `0x18004293e`
- `fwbase!FwReportReturnError` at `0x180042904`
- `fwbase!FwReportReturnError` at `0x18004293e`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x1800427f0`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x1800427f0`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180042925`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180042925`

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
0x180042730  mov     [rsp-8+arg_10], rbx
0x180042735  push    rbp
0x180042736  push    rsi
0x180042737  push    rdi
0x180042738  lea     rbp, [rsp-180h]
0x180042740  sub     rsp, 280h
0x180042747  mov     rax, cs:__security_cookie
0x18004274e  xor     rax, rsp
0x180042751  mov     [rbp+190h+var_20], rax
0x180042758  mov     rbx, rdx
0x18004275b  mov     rdi, rcx
0x18004275e  mov     rcx, cs:WPP_GLOBAL_Control
0x180042765  lea     rsi, WPP_GLOBAL_Control
0x18004276c  cmp     rcx, rsi
0x18004276f  jz      short loc_1800427B6
0x180042771  test    byte ptr [rcx+1Ch], 8
0x180042775  jz      short loc_180042793
0x180042777  mov     rcx, [rcx+10h]
0x18004277b  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180042782  mov     edx, 23h ; '#'
0x180042787  call    WPP_SF_
0x18004278c  mov     rcx, cs:WPP_GLOBAL_Control
0x180042793  cmp     rcx, rsi
0x180042796  jz      short loc_1800427B6
0x180042798  test    byte ptr [rcx+1Ch], 4
0x18004279c  jz      short loc_1800427B6
0x18004279e  mov     rcx, [rcx+10h]
0x1800427a2  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x1800427a9  mov     edx, 24h ; '$'
0x1800427ae  mov     r9, rbx
0x1800427b1  call    WPP_SF_S
0x1800427b6  xor     edx, edx; Val
0x1800427b8  lea     rcx, [rsp+290h+var_270]; void *
0x1800427bd  lea     r8d, [rdx+48h]; Size
0x1800427c1  call    memset_0
0x1800427c6  xor     edx, edx; Val
0x1800427c8  lea     rcx, [rsp+290h+var_220]; void *
0x1800427cd  mov     r8d, 1F8h; Size
0x1800427d3  call    memset_0
0x1800427d8  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800427dc  call    cs:__imp_EnterCriticalSection
0x1800427e3  nop     dword ptr [rax+rax+00h]
0x1800427e8  lea     rdx, [rsp+290h+var_270]
0x1800427ed  mov     rcx, rbx
0x1800427f0  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x1800427f7  nop     dword ptr [rax+rax+00h]
0x1800427fc  mov     ebx, eax
0x1800427fe  test    eax, eax
0x180042800  js      loc_1800428FB
0x180042806  cmp     qword ptr [rdi+50h], 0
0x18004280b  jnz     short loc_18004281F
0x18004280d  mov     rcx, rdi; this
0x180042810  call    ?CreateRule@FwRule@@AEAAJXZ; FwRule::CreateRule(void)
0x180042815  mov     ebx, eax
0x180042817  test    eax, eax
0x180042819  js      loc_1800428FB
0x18004281f  mov     rax, [rdi+50h]
0x180042823  lea     rdx, [rsp+290h+var_220]
0x180042828  mov     ecx, 3
0x18004282d  lea     r8d, [rcx+7Dh]
0x180042831  movups  xmm0, xmmword ptr [rax]
0x180042834  movups  xmmword ptr [rdx], xmm0
0x180042837  movups  xmm1, xmmword ptr [rax+10h]
0x18004283b  movups  xmmword ptr [rdx+10h], xmm1
0x18004283f  movups  xmm0, xmmword ptr [rax+20h]
0x180042843  movups  xmmword ptr [rdx+20h], xmm0
0x180042847  movups  xmm1, xmmword ptr [rax+30h]
0x18004284b  movups  xmmword ptr [rdx+30h], xmm1
0x18004284f  movups  xmm0, xmmword ptr [rax+40h]
0x180042853  movups  xmmword ptr [rdx+40h], xmm0
0x180042857  movups  xmm1, xmmword ptr [rax+50h]
0x18004285b  movups  xmmword ptr [rdx+50h], xmm1
0x18004285f  movups  xmm0, xmmword ptr [rax+60h]
0x180042863  movups  xmmword ptr [rdx+60h], xmm0
0x180042867  movups  xmm1, xmmword ptr [rax+70h]
0x18004286b  add     rax, r8
0x18004286e  movups  xmmword ptr [rdx+70h], xmm1
0x180042872  add     rdx, r8
0x180042875  sub     rcx, 1
0x180042879  jnz     short loc_180042831
0x18004287b  movups  xmm0, xmmword ptr [rax]
0x18004287e  mov     rcx, rdi; this
0x180042881  movups  xmmword ptr [rdx], xmm0
0x180042884  movups  xmm1, xmmword ptr [rax+10h]
0x180042888  movups  xmmword ptr [rdx+10h], xmm1
0x18004288c  movups  xmm0, xmmword ptr [rax+20h]
0x180042890  movups  xmmword ptr [rdx+20h], xmm0
0x180042894  movups  xmm1, xmmword ptr [rax+30h]
0x180042898  movups  xmmword ptr [rdx+30h], xmm1
0x18004289c  movups  xmm0, xmmword ptr [rax+40h]
0x1800428a0  movups  xmmword ptr [rdx+40h], xmm0
0x1800428a4  movups  xmm1, xmmword ptr [rax+50h]
0x1800428a8  movups  xmmword ptr [rdx+50h], xmm1
0x1800428ac  movups  xmm0, xmmword ptr [rax+60h]
0x1800428b0  movaps  xmm1, [rsp+290h+var_260]
0x1800428b5  movups  xmmword ptr [rdx+60h], xmm0
0x1800428b9  mov     rax, [rax+70h]
0x1800428bd  movaps  xmm0, [rsp+290h+var_270]
0x1800428c2  mov     [rdx+70h], rax
0x1800428c6  lea     rdx, [rsp+290h+var_220]; struct _tag_FW_RULE *
0x1800428cb  movaps  [rbp+190h+var_170], xmm0
0x1800428cf  movaps  xmm0, [rsp+290h+var_250]
0x1800428d4  movaps  [rbp+190h+var_150], xmm0
0x1800428d8  movsd   xmm0, [rsp+290h+var_230]
0x1800428de  movaps  [rbp+190h+var_160], xmm1
0x1800428e2  movaps  xmm1, [rsp+290h+var_240]
0x1800428e7  movsd   [rbp+190h+var_130], xmm0
0x1800428ec  movaps  [rbp+190h+var_140], xmm1
0x1800428f0  call    ?SetRule@FwRule@@AEAAJPEBU_tag_FW_RULE@@@Z; FwRule::SetRule(_tag_FW_RULE const *)
0x1800428f5  mov     ebx, eax
0x1800428f7  test    eax, eax
0x1800428f9  jns     short loc_180042910
0x1800428fb  mov     edx, eax
0x1800428fd  lea     rcx, aFwrulePutRemot_1; "FwRule::put_RemoteAddresses"
0x180042904  call    cs:__imp_FwReportReturnError
0x18004290b  nop     dword ptr [rax+rax+00h]
0x180042910  lea     rcx, [rdi+10h]; lpCriticalSection
0x180042914  call    cs:__imp_LeaveCriticalSection
0x18004291b  nop     dword ptr [rax+rax+00h]
0x180042920  lea     rcx, [rsp+290h+var_270]
0x180042925  call    cs:__imp_FwPolioEmptyWFAddresses
0x18004292c  nop     dword ptr [rax+rax+00h]
0x180042931  test    ebx, ebx
0x180042933  jns     short loc_18004294C
0x180042935  mov     edx, ebx
0x180042937  lea     rcx, aFwrulePutRemot_1; "FwRule::put_RemoteAddresses"
0x18004293e  call    cs:__imp_FwReportReturnError
0x180042945  nop     dword ptr [rax+rax+00h]
0x18004294a  mov     ebx, eax
0x18004294c  mov     eax, ebx
0x18004294e  mov     rcx, [rbp+190h+var_20]
0x180042955  xor     rcx, rsp; StackCookie
0x180042958  call    __security_check_cookie
0x18004295d  mov     rbx, [rsp+290h+arg_10]
0x180042965  add     rsp, 280h
0x18004296c  pop     rdi
0x18004296d  pop     rsi
0x18004296e  pop     rbp
0x18004296f  retn
```
