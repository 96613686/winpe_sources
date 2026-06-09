# FwProfile::GetBool(_tag_FW_PROFILE_CONFIG,short,short *)

- ea: `0x180003194`
- end: `0x1800033ca`
- name: `?GetBool@FwProfile@@AEAAJW4_tag_FW_PROFILE_CONFIG@@FPEAF@Z`
- size: `566`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1800029f0`
- `0x1800437b0`
- `0x180043830`
- `0x180043960`

## callees

- `0x180003194`
- `0x180003520`
- `0x180005954`
- `0x180008b30`
- `0x18000c560`
- `0x1800277b0`
- `0x18003104c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180003242`
- `ntdll!EtwEventWrite` at `0x1800032c7`
- `ntdll!EtwEventWrite` at `0x180003242`
- `ntdll!EtwEventWrite` at `0x1800032c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003265`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180003265`
- `fwbase!FwReportReturnError` at `0x180003388`
- `fwbase!FwReportReturnError` at `0x1800033bd`
- `fwbase!FwReportReturnError` at `0x180003388`
- `fwbase!FwReportReturnError` at `0x1800033bd`

## pseudocode

```c
__int64 __fastcall FwProfile::GetBool(__int64 a1, unsigned int a2, __int16 a3, __int16 *a4)
{
  int v8; // eax
  signed int v9; // ebx
  unsigned int v10; // edi
  void *v11; // r14
  unsigned int v12; // edi
  __int16 v13; // ax
  void *v15; // [rsp+40h] [rbp-48h] BYREF
  _DWORD v16[2]; // [rsp+48h] [rbp-40h] BYREF
  int v17; // [rsp+50h] [rbp-38h] BYREF

  v16[0] = 0;
  v17 = 4;
  v15 = 0;
  if ( a4 )
  {
    v8 = FWOpenPolicyStore(0x221u, 0, 2u, 1u, 0, &v15);
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v9 >= 0 )
    {
      v10 = *(_DWORD *)(a1 + 24);
      v11 = v15;
      v16[1] = 0;
      if ( g_Provider )
        EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_GetConfig, 0, 0);
      if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
      GetTickCount64();
      v12 = Int_FWGetOrSetConfig(1u, (__int64)v11, a2, v10, 0, (__int64)v16, &v17);
      if ( v12
        && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v12);
      }
      if ( g_Provider )
        EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_GetConfig, 0, 0);
      if ( v12 == 2 )
      {
        v13 = -(a3 != 0);
LABEL_17:
        *a4 = v13;
        goto LABEL_18;
      }
      if ( !v12 )
      {
        if ( v16[0] )
          v13 = -1;
        else
          v13 = 0;
        goto LABEL_17;
      }
      v9 = -2147418113;
    }
  }
  else
  {
    v9 = -2147467261;
  }
  FwReportReturnError("FwProfile::GetBool", (unsigned int)v9);
LABEL_18:
  CloseLocalPolicyStore(v15);
  if ( v9 < 0 )
    return (unsigned int)FwReportReturnError("FwProfile::GetBool", (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180003194  mov     r11, rsp
0x180003197  mov     [r11+18h], rbx
0x18000319b  push    rbp
0x18000319c  push    rsi
0x18000319d  push    rdi
0x18000319e  push    r14
0x1800031a0  push    r15
0x1800031a2  sub     rsp, 60h
0x1800031a6  mov     rax, cs:__security_cookie
0x1800031ad  xor     rax, rsp
0x1800031b0  mov     [rsp+88h+var_30], rax
0x1800031b5  mov     [rsp+88h+var_40], 0
0x1800031bd  mov     rsi, r9
0x1800031c0  mov     [rsp+88h+var_38], 4
0x1800031c8  movzx   ebp, r8w
0x1800031cc  mov     qword ptr [r11-48h], 0
0x1800031d4  mov     r15d, edx
0x1800031d7  mov     rdi, rcx
0x1800031da  test    r9, r9
0x1800031dd  jz      loc_180003373
0x1800031e3  xor     edx, edx
0x1800031e5  lea     rax, [r11-48h]
0x1800031e9  mov     [r11-60h], rax
0x1800031ed  mov     ecx, 221h
0x1800031f2  mov     [rsp+88h+var_68], 0
0x1800031fa  lea     r9d, [rdx+1]
0x1800031fe  lea     r8d, [rdx+2]
0x180003202  call    FWOpenPolicyStore
0x180003207  mov     ebx, eax
0x180003209  test    eax, eax
0x18000320b  jg      loc_180003327
0x180003211  test    ebx, ebx
0x180003213  js      loc_18000337F
0x180003219  mov     rcx, cs:g_Provider
0x180003220  mov     edi, [rdi+18h]
0x180003223  mov     r14, [rsp+88h+var_48]
0x180003228  mov     [rsp+88h+var_3C], 0
0x180003230  test    rcx, rcx
0x180003233  jz      short loc_180003248
0x180003235  xor     r9d, r9d
0x180003238  lea     rdx, MPS_CLNT_API_Enter_GetConfig
0x18000323f  xor     r8d, r8d
0x180003242  call    cs:__imp_EtwEventWrite
0x180003248  mov     rcx, cs:WPP_GLOBAL_Control
0x18000324f  lea     rax, WPP_GLOBAL_Control
0x180003256  cmp     rcx, rax
0x180003259  jz      short loc_180003265
0x18000325b  test    byte ptr [rcx+1Ch], 8
0x18000325f  jnz     loc_180003393
0x180003265  call    cs:__imp_GetTickCount64
0x18000326b  lea     rax, [rsp+88h+var_3C]
0x180003270  mov     r9d, edi
0x180003273  mov     [rsp+88h+var_50], rax
0x180003278  mov     r8d, r15d
0x18000327b  lea     rax, [rsp+88h+var_38]
0x180003280  mov     rdx, r14
0x180003283  mov     [rsp+88h+var_58], rax
0x180003288  mov     ecx, 1
0x18000328d  lea     rax, [rsp+88h+var_40]
0x180003292  mov     [rsp+88h+var_60], rax
0x180003297  mov     [rsp+88h+var_68], 0
0x18000329f  call    Int_FWGetOrSetConfig
0x1800032a4  mov     edi, eax
0x1800032a6  test    eax, eax
0x1800032a8  jnz     loc_180003335
0x1800032ae  mov     rcx, cs:g_Provider
0x1800032b5  test    rcx, rcx
0x1800032b8  jz      short loc_1800032CD
0x1800032ba  xor     r9d, r9d
0x1800032bd  lea     rdx, MPS_CLNT_API_Exit_GetConfig
0x1800032c4  xor     r8d, r8d
0x1800032c7  call    cs:__imp_EtwEventWrite
0x1800032cd  cmp     edi, 2
0x1800032d0  jz      short loc_18000331F
0x1800032d2  test    edi, edi
0x1800032d4  jnz     loc_18000337A
0x1800032da  cmp     [rsp+88h+var_40], edi
0x1800032de  jz      loc_1800033AD
0x1800032e4  or      eax, 0FFFFFFFFh
0x1800032e7  mov     [rsi], ax
0x1800032ea  mov     rcx, [rsp+88h+var_48]; void *
0x1800032ef  call    ?CloseLocalPolicyStore@@YAXPEAX@Z; CloseLocalPolicyStore(void *)
0x1800032f4  test    ebx, ebx
0x1800032f6  js      loc_1800033B4
0x1800032fc  mov     eax, ebx
0x1800032fe  mov     rcx, [rsp+88h+var_30]
0x180003303  xor     rcx, rsp; StackCookie
0x180003306  call    __security_check_cookie
0x18000330b  mov     rbx, [rsp+88h+arg_10]
0x180003313  add     rsp, 60h
0x180003317  pop     r15
0x180003319  pop     r14
0x18000331b  pop     rdi
0x18000331c  pop     rsi
0x18000331d  pop     rbp
0x18000331e  retn
0x18000331f  neg     bp
0x180003322  sbb     ax, ax
0x180003325  jmp     short loc_1800032E7
0x180003327  movzx   ebx, ax
0x18000332a  or      ebx, 80070000h
0x180003330  jmp     loc_180003211
0x180003335  mov     rcx, cs:WPP_GLOBAL_Control
0x18000333c  lea     rax, WPP_GLOBAL_Control
0x180003343  cmp     rcx, rax
0x180003346  jz      loc_1800032AE
0x18000334c  test    byte ptr [rcx+1Ch], 1
0x180003350  jz      loc_1800032AE
0x180003356  mov     rcx, [rcx+10h]
0x18000335a  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180003361  mov     edx, 6Bh ; 'k'
0x180003366  mov     r9d, edi
0x180003369  call    WPP_SF_d
0x18000336e  jmp     loc_1800032AE
0x180003373  mov     ebx, 80004003h
0x180003378  jmp     short loc_18000337F
0x18000337a  mov     ebx, 8000FFFFh
0x18000337f  mov     edx, ebx
0x180003381  lea     rcx, aFwprofileGetbo; "FwProfile::GetBool"
0x180003388  call    cs:__imp_FwReportReturnError
0x18000338e  jmp     loc_1800032EA
0x180003393  mov     rcx, [rcx+10h]
0x180003397  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000339e  mov     edx, 6Ah ; 'j'
0x1800033a3  call    WPP_SF_
0x1800033a8  jmp     loc_180003265
0x1800033ad  xor     eax, eax
0x1800033af  jmp     loc_1800032E7
0x1800033b4  mov     edx, ebx
0x1800033b6  lea     rcx, aFwprofileGetbo; "FwProfile::GetBool"
0x1800033bd  call    cs:__imp_FwReportReturnError
0x1800033c3  mov     ebx, eax
0x1800033c5  jmp     loc_1800032FC
```
