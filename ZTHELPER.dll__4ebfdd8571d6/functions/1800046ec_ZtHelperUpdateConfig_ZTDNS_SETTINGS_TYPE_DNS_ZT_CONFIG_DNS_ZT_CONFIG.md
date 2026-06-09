# ZtHelperUpdateConfig(_ZTDNS_SETTINGS_TYPE,_DNS_ZT_CONFIG *,_DNS_ZT_CONFIG *)

- ea: `0x1800046ec`
- end: `0x180004824`
- name: `?ZtHelperUpdateConfig@@YAJW4_ZTDNS_SETTINGS_TYPE@@PEAU_DNS_ZT_CONFIG@@1@Z`
- size: `312`
- prototype: `__int64 __fastcall(int, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800049b0`

## callees

- `0x180004218`
- `0x1800046ec`
- `0x18000fb40`
- `0x1800101e8`
- `0x180015008`
- `0x180015094`

## pseudocode

```c
__int64 __fastcall ZtHelperUpdateConfig(int a1, __int64 a2, _BYTE *a3)
{
  __int64 v4; // rbx
  unsigned int v6; // ebx
  __int64 v7; // rbp
  __int64 *v8; // r14
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  _OWORD v12[3]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v13; // [rsp+50h] [rbp-28h]
  __int64 v14; // [rsp+88h] [rbp+10h] BYREF

  v4 = a1;
  v14 = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_q(1026, 38, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, a2);
  WxZeroOut<_DNS_ZT_CONFIG>(a3);
  if ( a2 )
  {
    if ( (unsigned int)v4 > 1 )
    {
      v6 = 87;
      if ( (xmmword_18001F260 & 4) == 0 )
        return v6;
      WPP_SF_d(1026, 39, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, 87);
    }
    else
    {
      v7 = v4;
      v8 = &g_rgZtConfig[7 * v4];
      v6 = ZtComputeConfigChange(v8, a2, &v14);
      if ( !v6 )
      {
        v9 = *(_OWORD *)(a2 + 16);
        v12[0] = *(_OWORD *)a2;
        v10 = *(_OWORD *)(a2 + 32);
        v12[1] = v9;
        *(_QWORD *)&v9 = *(_QWORD *)(a2 + 48);
        v12[2] = v10;
        v13 = v9;
        ZtUpdateConfig(v12, &g_rgfZtConfigInitialized[v7], v8, a3);
      }
    }
  }
  else
  {
    v6 = 87;
  }
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 40, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1800046ec  mov     rax, rsp
0x1800046ef  mov     [rax+8], rbx
0x1800046f3  mov     [rax+18h], rbp
0x1800046f7  push    rsi
0x1800046f8  push    rdi
0x1800046f9  push    r14
0x1800046fb  sub     rsp, 60h
0x1800046ff  mov     rsi, r8
0x180004702  movsxd  rbx, ecx
0x180004705  mov     rdi, rdx
0x180004708  mov     qword ptr [rax+10h], 0
0x180004710  test    byte ptr cs:xmmword_18001F260, 4
0x180004717  jz      short loc_180004732
0x180004719  mov     edx, 26h ; '&'
0x18000471e  lea     r8, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x180004725  mov     ecx, 402h
0x18000472a  mov     r9, rdi
0x18000472d  call    WPP_SF_q
0x180004732  mov     rcx, rsi
0x180004735  call    ??$WxZeroOut@U_DNS_ZT_CONFIG@@@@YAXPEAU_DNS_ZT_CONFIG@@@Z; WxZeroOut<_DNS_ZT_CONFIG>(_DNS_ZT_CONFIG *)
0x18000473a  test    rdi, rdi
0x18000473d  jnz     short loc_180004747
0x18000473f  lea     ebx, [rdi+57h]
0x180004742  jmp     loc_1800047EB
0x180004747  cmp     ebx, 1
0x18000474a  ja      short loc_1800047C6
0x18000474c  imul    rax, rbx, 38h ; '8'
0x180004750  lea     rcx, cs:180000000h
0x180004757  mov     rdx, rdi
0x18000475a  lea     r14, rva g_rgZtConfig[rcx]
0x180004761  mov     rbp, rbx
0x180004764  add     r14, rax
0x180004767  lea     r8, [rsp+78h+arg_8]
0x18000476f  mov     rcx, r14
0x180004772  call    ZtComputeConfigChange
0x180004777  mov     ebx, eax
0x180004779  test    eax, eax
0x18000477b  jnz     short loc_1800047EB
0x18000477d  movups  xmm0, xmmword ptr [rdi]
0x180004780  lea     rax, cs:180000000h
0x180004787  mov     r9, rsi
0x18000478a  movups  xmm1, xmmword ptr [rdi+10h]
0x18000478e  lea     rdx, rva g_rgfZtConfigInitialized[rax]
0x180004795  mov     r8, r14
0x180004798  movaps  [rsp+78h+var_58], xmm0
0x18000479d  lea     rdx, [rdx+rbp*4]
0x1800047a1  movups  xmm0, xmmword ptr [rdi+20h]
0x1800047a5  lea     rcx, [rsp+78h+var_58]
0x1800047aa  movaps  [rsp+78h+var_48], xmm1
0x1800047af  movsd   xmm1, qword ptr [rdi+30h]
0x1800047b4  movaps  [rsp+78h+var_38], xmm0
0x1800047b9  movsd   [rsp+78h+var_28], xmm1
0x1800047bf  call    ZtUpdateConfig
0x1800047c4  jmp     short loc_1800047EB
0x1800047c6  mov     ebx, 57h ; 'W'
0x1800047cb  test    byte ptr cs:xmmword_18001F260, 4
0x1800047d2  jz      short loc_18000480D
0x1800047d4  lea     edx, [rbx-30h]
0x1800047d7  mov     ecx, 402h
0x1800047dc  mov     r9d, ebx
0x1800047df  lea     r8, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x1800047e6  call    WPP_SF_d
0x1800047eb  test    byte ptr cs:xmmword_18001F260, 4
0x1800047f2  jz      short loc_18000480D
0x1800047f4  mov     edx, 28h ; '('
0x1800047f9  lea     r8, WPP_7ce638d68950392782b9b287c2f9f93a_Traceguids
0x180004800  mov     ecx, 402h
0x180004805  mov     r9d, ebx
0x180004808  call    WPP_SF_d
0x18000480d  lea     r11, [rsp+78h+var_18]
0x180004812  mov     eax, ebx
0x180004814  mov     rbx, [r11+20h]
0x180004818  mov     rbp, [r11+30h]
0x18000481c  mov     rsp, r11
0x18000481f  pop     r14
0x180004821  pop     rdi
0x180004822  pop     rsi
0x180004823  retn
```
