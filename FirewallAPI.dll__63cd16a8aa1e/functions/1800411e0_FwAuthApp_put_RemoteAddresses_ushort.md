# FwAuthApp::put_RemoteAddresses(ushort *)

- ea: `0x1800411e0`
- end: `0x18004147c`
- name: `?put_RemoteAddresses@FwAuthApp@@UEAAJPEAG@Z`
- size: `668`
- prototype: `__int64 __fastcall(FwAuthApp *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001dd0`
- `0x18000270c`
- `0x1800277b0`
- `0x1800284c4`
- `0x1800411e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004124c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004124c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004142d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004142d`
- `fwbase!FwReportReturnError` at `0x180041423`
- `fwbase!FwReportReturnError` at `0x18004144b`
- `fwbase!FwReportReturnError` at `0x180041423`
- `fwbase!FwReportReturnError` at `0x18004144b`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x18004125a`
- `FWPolicyIOMgr!StringToOpenPortOrAuthAppAddress` at `0x18004125a`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180041438`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180041438`

## pseudocode

```c
__int64 __fastcall FwAuthApp::put_RemoteAddresses(FwAuthApp *this, unsigned __int16 *a2)
{
  int DefaultAuthAppRules; // eax
  int v5; // ebx
  _OWORD *v6; // rax
  _OWORD *v7; // rcx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int128 v10; // xmm1
  _OWORD *v11; // rdx
  __int128 v12; // xmm2
  __int128 v13; // xmm3
  __int128 v14; // xmm4
  __int128 v15; // xmm5
  __int64 v16; // xmm6_8
  _OWORD *v17; // rax
  __int128 v18; // xmm1
  _OWORD v20[4]; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+68h] [rbp-A0h]
  _BYTE v22[176]; // [rsp+78h] [rbp-90h] BYREF
  __int128 v23; // [rsp+128h] [rbp+20h]
  __int128 v24; // [rsp+138h] [rbp+30h]
  __int128 v25; // [rsp+148h] [rbp+40h]
  __int128 v26; // [rsp+158h] [rbp+50h]
  __int64 v27; // [rsp+168h] [rbp+60h]
  _BYTE v28[176]; // [rsp+278h] [rbp+170h] BYREF
  __int128 v29; // [rsp+328h] [rbp+220h]
  __int128 v30; // [rsp+338h] [rbp+230h]
  __int128 v31; // [rsp+348h] [rbp+240h]
  __int128 v32; // [rsp+358h] [rbp+250h]
  __int64 v33; // [rsp+368h] [rbp+260h]

  memset_0(v20, 0, 0x48u);
  memset_0(v28, 0, 0x1F8u);
  memset_0(v22, 0, 0x1F8u);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  DefaultAuthAppRules = StringToOpenPortOrAuthAppAddress(a2, v20);
  v5 = DefaultAuthAppRules;
  if ( DefaultAuthAppRules < 0 )
    goto LABEL_8;
  DefaultAuthAppRules = FwAuthApp::CreateDefaultAuthAppRules(this);
  v5 = DefaultAuthAppRules;
  if ( DefaultAuthAppRules < 0 )
    goto LABEL_8;
  v6 = (_OWORD *)*((_QWORD *)this + 9);
  v7 = v28;
  v8 = 3;
  v9 = 3;
  do
  {
    *v7 = *v6;
    v7[1] = v6[1];
    v7[2] = v6[2];
    v7[3] = v6[3];
    v7[4] = v6[4];
    v7[5] = v6[5];
    v7[6] = v6[6];
    v10 = v6[7];
    v6 += 8;
    v7[7] = v10;
    v7 += 8;
    --v9;
  }
  while ( v9 );
  v11 = v22;
  v12 = v20[0];
  v13 = v20[1];
  v14 = v20[2];
  v15 = v20[3];
  v16 = v21;
  *v7 = *v6;
  v7[1] = v6[1];
  v7[2] = v6[2];
  v7[3] = v6[3];
  v7[4] = v6[4];
  v7[5] = v6[5];
  v7[6] = v6[6];
  *((_QWORD *)v7 + 14) = *((_QWORD *)v6 + 14);
  v17 = (_OWORD *)*((_QWORD *)this + 10);
  v29 = v12;
  v30 = v13;
  v31 = v14;
  v32 = v15;
  v33 = v16;
  do
  {
    *v11 = *v17;
    v11[1] = v17[1];
    v11[2] = v17[2];
    v11[3] = v17[3];
    v11[4] = v17[4];
    v11[5] = v17[5];
    v11[6] = v17[6];
    v18 = v17[7];
    v17 += 8;
    v11[7] = v18;
    v11 += 8;
    --v8;
  }
  while ( v8 );
  *v11 = *v17;
  v11[1] = v17[1];
  v11[2] = v17[2];
  v11[3] = v17[3];
  v11[4] = v17[4];
  v11[5] = v17[5];
  v11[6] = v17[6];
  *((_QWORD *)v11 + 14) = *((_QWORD *)v17 + 14);
  v23 = v12;
  v24 = v13;
  v25 = v14;
  v26 = v15;
  v27 = v16;
  DefaultAuthAppRules = FwAuthApp::SetRules(this, (const struct _tag_FW_RULE *)v28, (const struct _tag_FW_RULE *)v22);
  v5 = DefaultAuthAppRules;
  if ( DefaultAuthAppRules < 0 )
LABEL_8:
    FwReportReturnError("FwAuthApp::put_RemoteAddresses", (unsigned int)DefaultAuthAppRules);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  FwPolioEmptyWFAddresses(v20);
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthApp::put_RemoteAddresses", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800411e0  mov     rax, rsp
0x1800411e3  mov     [rax+18h], rbx
0x1800411e7  push    rbp
0x1800411e8  push    rsi
0x1800411e9  push    rdi
0x1800411ea  lea     rbp, [rax-3A8h]
0x1800411f1  sub     rsp, 490h
0x1800411f8  movaps  xmmword ptr [rax-28h], xmm6
0x1800411fc  mov     rax, cs:__security_cookie
0x180041203  xor     rax, rsp
0x180041206  mov     [rbp+3A0h+var_30], rax
0x18004120d  mov     rbx, rdx
0x180041210  mov     rdi, rcx
0x180041213  xor     edx, edx; Val
0x180041215  lea     rcx, [rsp+4A0h+var_488+8]; void *
0x18004121a  lea     r8d, [rdx+48h]; Size
0x18004121e  call    memset_0
0x180041223  mov     esi, 1F8h
0x180041228  lea     rcx, [rbp+3A0h+var_230]; void *
0x18004122f  mov     r8d, esi; Size
0x180041232  xor     edx, edx; Val
0x180041234  call    memset_0
0x180041239  mov     r8d, esi; Size
0x18004123c  lea     rcx, [rsp+4A0h+var_430]; void *
0x180041241  xor     edx, edx; Val
0x180041243  call    memset_0
0x180041248  lea     rcx, [rdi+10h]; lpCriticalSection
0x18004124c  call    cs:__imp_EnterCriticalSection
0x180041252  lea     rdx, [rsp+4A0h+var_488+8]
0x180041257  mov     rcx, rbx
0x18004125a  call    cs:__imp_StringToOpenPortOrAuthAppAddress
0x180041260  mov     ebx, eax
0x180041262  test    eax, eax
0x180041264  js      loc_18004141A
0x18004126a  mov     rcx, rdi; this
0x18004126d  call    ?CreateDefaultAuthAppRules@FwAuthApp@@AEAAJXZ; FwAuthApp::CreateDefaultAuthAppRules(void)
0x180041272  mov     ebx, eax
0x180041274  test    eax, eax
0x180041276  js      loc_18004141A
0x18004127c  mov     rax, [rdi+48h]
0x180041280  lea     rcx, [rbp+3A0h+var_230]
0x180041287  mov     r8d, 3
0x18004128d  mov     edx, r8d
0x180041290  lea     r9d, [r8+7Dh]
0x180041294  movups  xmm0, xmmword ptr [rax]
0x180041297  movups  xmmword ptr [rcx], xmm0
0x18004129a  movups  xmm1, xmmword ptr [rax+10h]
0x18004129e  movups  xmmword ptr [rcx+10h], xmm1
0x1800412a2  movups  xmm0, xmmword ptr [rax+20h]
0x1800412a6  movups  xmmword ptr [rcx+20h], xmm0
0x1800412aa  movups  xmm1, xmmword ptr [rax+30h]
0x1800412ae  movups  xmmword ptr [rcx+30h], xmm1
0x1800412b2  movups  xmm0, xmmword ptr [rax+40h]
0x1800412b6  movups  xmmword ptr [rcx+40h], xmm0
0x1800412ba  movups  xmm1, xmmword ptr [rax+50h]
0x1800412be  movups  xmmword ptr [rcx+50h], xmm1
0x1800412c2  movups  xmm0, xmmword ptr [rax+60h]
0x1800412c6  movups  xmmword ptr [rcx+60h], xmm0
0x1800412ca  movups  xmm1, xmmword ptr [rax+70h]
0x1800412ce  add     rax, r9
0x1800412d1  movups  xmmword ptr [rcx+70h], xmm1
0x1800412d5  add     rcx, r9
0x1800412d8  sub     rdx, 1
0x1800412dc  jnz     short loc_180041294
0x1800412de  movups  xmm0, xmmword ptr [rax]
0x1800412e1  lea     rdx, [rsp+4A0h+var_430]
0x1800412e6  movaps  xmm2, [rsp+4A0h+var_488+8]
0x1800412eb  movaps  xmm3, [rsp+4A0h+var_478+8]
0x1800412f0  movaps  xmm4, [rsp+4A0h+var_468+8]
0x1800412f5  movaps  xmm5, [rsp+4A0h+var_458+8]
0x1800412fa  movsd   xmm6, [rsp+4A0h+var_440]
0x180041300  movups  xmmword ptr [rcx], xmm0
0x180041303  movups  xmm1, xmmword ptr [rax+10h]
0x180041307  movups  xmmword ptr [rcx+10h], xmm1
0x18004130b  movups  xmm0, xmmword ptr [rax+20h]
0x18004130f  movups  xmmword ptr [rcx+20h], xmm0
0x180041313  movups  xmm1, xmmword ptr [rax+30h]
0x180041317  movups  xmmword ptr [rcx+30h], xmm1
0x18004131b  movups  xmm0, xmmword ptr [rax+40h]
0x18004131f  movups  xmmword ptr [rcx+40h], xmm0
0x180041323  movups  xmm1, xmmword ptr [rax+50h]
0x180041327  movups  xmmword ptr [rcx+50h], xmm1
0x18004132b  movups  xmm0, xmmword ptr [rax+60h]
0x18004132f  movups  xmmword ptr [rcx+60h], xmm0
0x180041333  mov     rax, [rax+70h]
0x180041337  mov     [rcx+70h], rax
0x18004133b  mov     rax, [rdi+50h]
0x18004133f  movaps  [rbp+3A0h+var_180], xmm2
0x180041346  movaps  [rbp+3A0h+var_170], xmm3
0x18004134d  movaps  [rbp+3A0h+var_160], xmm4
0x180041354  movaps  [rbp+3A0h+var_150], xmm5
0x18004135b  movsd   [rbp+3A0h+var_140], xmm6
0x180041363  movups  xmm0, xmmword ptr [rax]
0x180041366  movups  xmmword ptr [rdx], xmm0
0x180041369  movups  xmm1, xmmword ptr [rax+10h]
0x18004136d  movups  xmmword ptr [rdx+10h], xmm1
0x180041371  movups  xmm0, xmmword ptr [rax+20h]
0x180041375  movups  xmmword ptr [rdx+20h], xmm0
0x180041379  movups  xmm1, xmmword ptr [rax+30h]
0x18004137d  movups  xmmword ptr [rdx+30h], xmm1
0x180041381  movups  xmm0, xmmword ptr [rax+40h]
0x180041385  movups  xmmword ptr [rdx+40h], xmm0
0x180041389  movups  xmm1, xmmword ptr [rax+50h]
0x18004138d  movups  xmmword ptr [rdx+50h], xmm1
0x180041391  movups  xmm0, xmmword ptr [rax+60h]
0x180041395  movups  xmmword ptr [rdx+60h], xmm0
0x180041399  movups  xmm1, xmmword ptr [rax+70h]
0x18004139d  add     rax, r9
0x1800413a0  movups  xmmword ptr [rdx+70h], xmm1
0x1800413a4  add     rdx, r9
0x1800413a7  sub     r8, 1
0x1800413ab  jnz     short loc_180041363
0x1800413ad  movups  xmm0, xmmword ptr [rax]
0x1800413b0  lea     r8, [rsp+4A0h+var_430]; struct _tag_FW_RULE *
0x1800413b5  mov     rcx, rdi; this
0x1800413b8  movups  xmmword ptr [rdx], xmm0
0x1800413bb  movups  xmm1, xmmword ptr [rax+10h]
0x1800413bf  movups  xmmword ptr [rdx+10h], xmm1
0x1800413c3  movups  xmm0, xmmword ptr [rax+20h]
0x1800413c7  movups  xmmword ptr [rdx+20h], xmm0
0x1800413cb  movups  xmm1, xmmword ptr [rax+30h]
0x1800413cf  movups  xmmword ptr [rdx+30h], xmm1
0x1800413d3  movups  xmm0, xmmword ptr [rax+40h]
0x1800413d7  movups  xmmword ptr [rdx+40h], xmm0
0x1800413db  movups  xmm1, xmmword ptr [rax+50h]
0x1800413df  movups  xmmword ptr [rdx+50h], xmm1
0x1800413e3  movups  xmm0, xmmword ptr [rax+60h]
0x1800413e7  movups  xmmword ptr [rdx+60h], xmm0
0x1800413eb  mov     rax, [rax+70h]
0x1800413ef  mov     [rdx+70h], rax
0x1800413f3  lea     rdx, [rbp+3A0h+var_230]; struct _tag_FW_RULE *
0x1800413fa  movaps  [rbp+3A0h+var_380], xmm2
0x1800413fe  movaps  [rbp+3A0h+var_370], xmm3
0x180041402  movaps  [rbp+3A0h+var_360], xmm4
0x180041406  movaps  [rbp+3A0h+var_350], xmm5
0x18004140a  movsd   [rbp+3A0h+var_340], xmm6
0x18004140f  call    ?SetRules@FwAuthApp@@AEAAJPEBU_tag_FW_RULE@@0@Z; FwAuthApp::SetRules(_tag_FW_RULE const *,_tag_FW_RULE const *)
0x180041414  mov     ebx, eax
0x180041416  test    eax, eax
0x180041418  jns     short loc_180041429
0x18004141a  mov     edx, eax
0x18004141c  lea     rcx, aFwauthappPutRe; "FwAuthApp::put_RemoteAddresses"
0x180041423  call    cs:__imp_FwReportReturnError
0x180041429  lea     rcx, [rdi+10h]; lpCriticalSection
0x18004142d  call    cs:__imp_LeaveCriticalSection
0x180041433  lea     rcx, [rsp+4A0h+var_488+8]
0x180041438  call    cs:__imp_FwPolioEmptyWFAddresses
0x18004143e  test    ebx, ebx
0x180041440  jns     short loc_180041453
0x180041442  mov     edx, ebx
0x180041444  lea     rcx, aFwauthappPutRe; "FwAuthApp::put_RemoteAddresses"
0x18004144b  call    cs:__imp_FwReportReturnError
0x180041451  mov     ebx, eax
0x180041453  mov     eax, ebx
0x180041455  mov     rcx, [rbp+3A0h+var_30]
0x18004145c  xor     rcx, rsp; StackCookie
0x18004145f  call    __security_check_cookie
0x180041464  lea     r11, [rsp+4A0h+var_10]
0x18004146c  mov     rbx, [r11+30h]
0x180041470  movaps  xmm6, xmmword ptr [r11-10h]
0x180041475  mov     rsp, r11
0x180041478  pop     rdi
0x180041479  pop     rsi
0x18004147a  pop     rbp
0x18004147b  retn
```
