# CopyConfigToProfile(void *,_tag_FW_PROFILE_TYPE,_tag_FW_STORE_TYPE,ICF_PROFILE_ *)

- ea: `0x180031770`
- end: `0x180031b69`
- name: `?CopyConfigToProfile@@YAKPEAXW4_tag_FW_PROFILE_TYPE@@W4_tag_FW_STORE_TYPE@@PEAUICF_PROFILE_@@@Z`
- size: `1017`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180032f90`

## callees

- `0x180008a10`
- `0x1800277b0`
- `0x1800284c4`
- `0x18003104c`
- `0x180031080`
- `0x180031770`

## import_xrefs

- `fwbase!FwHResultToWindowsError` at `0x180031b34`
- `fwbase!FwHResultToWindowsError` at `0x180031b34`
- `fwbase!FwReportErrorAsWinError` at `0x18003188b`
- `fwbase!FwReportErrorAsWinError` at `0x18003188b`
- `fwbase!FwReportReturnError` at `0x180031825`
- `fwbase!FwReportReturnError` at `0x180031825`
- `fwbase!FwStringCopy` at `0x180031b28`
- `fwbase!FwStringCopy` at `0x180031b28`

## string_xrefs

- `0x18003187d`: `FWGetConfig`
- `0x18003181c`: `CopyConfigToProfile`
- `0x180031884`: `CopyConfigToProfile`

## pseudocode

```c
__int64 __fastcall CopyConfigToProfile(__int64 a1, unsigned int a2, int a3, __int64 a4)
{
  unsigned int v5; // esi
  BOOL v8; // r14d
  int CurrentProfile; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // eax
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+4Ch] [rbp-B4h] BYREF
  _BYTE v23[1040]; // [rsp+50h] [rbp-B0h] BYREF

  v20 = a2;
  v5 = a2;
  v21 = 0;
  v22 = 4;
  memset_0(v23, 0, sizeof(v23));
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids);
  v8 = a3 == 5;
  if ( v5 == 0x80000000 )
  {
    CurrentProfile = FwGetCurrentProfile((enum _tag_FW_PROFILE_TYPE *)&v20);
    if ( CurrentProfile < 0 )
    {
      v10 = 0;
      FwReportReturnError("CopyConfigToProfile", (unsigned int)CurrentProfile);
      return v10;
    }
    v5 = v20;
  }
  v20 = 0;
  v11 = FWGetConfig2(a1, 1u, v5, a3 == 5, (__int64)&v21, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    v12 = 0;
  }
  else
  {
    if ( v11 )
    {
LABEL_10:
      FwReportErrorAsWinError("CopyConfigToProfile", "FWGetConfig", v11);
      return v10;
    }
    v12 = (v21 != 0) + 1;
  }
  *(_DWORD *)(a4 + 8) = v12;
  v20 = 0;
  v11 = FWGetConfig2(a1, 3u, v5, v8, (__int64)&v21, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    v13 = 0;
  }
  else
  {
    if ( v11 )
      goto LABEL_10;
    v13 = (v21 != 0) + 1;
  }
  *(_DWORD *)(a4 + 12) = v13;
  v20 = 0;
  v11 = FWGetConfig2(a1, 0xAu, v5, v8, (__int64)&v21, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    v14 = 0;
  }
  else
  {
    if ( v11 )
      goto LABEL_10;
    v14 = (v21 != 0) + 1;
  }
  *(_DWORD *)(a4 + 16) = v14;
  v20 = 0;
  v11 = FWGetConfig2(a1, 4u, v5, v8, (__int64)&v21, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    v15 = 0;
  }
  else
  {
    if ( v11 )
      goto LABEL_10;
    v15 = (v21 != 0) + 1;
  }
  *(_DWORD *)(a4 + 20) = v15;
  v20 = 0;
  v11 = FWGetConfig2(a1, 5u, v5, v8, (__int64)&v21, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    v16 = 0;
  }
  else
  {
    if ( v11 )
      goto LABEL_10;
    v16 = (v21 != 0) + 1;
  }
  *(_DWORD *)(a4 + 124) = v16;
  v20 = 0;
  v11 = FWGetConfig2(a1, 6u, v5, v8, (__int64)&v21, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    v17 = 0;
  }
  else
  {
    if ( v11 )
      goto LABEL_10;
    v17 = (v21 != 0) + 1;
  }
  *(_DWORD *)(a4 + 128) = v17;
  v20 = 0;
  v11 = FWGetConfig2(a1, 8u, v5, v8, (__int64)&v21, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    *(_DWORD *)(a4 + 120) = 0;
  }
  else
  {
    if ( v11 )
      goto LABEL_10;
    *(_DWORD *)(a4 + 120) = v21;
  }
  v22 = 1040;
  v20 = 0;
  v11 = FWGetConfig2(a1, 9u, v5, v8, (__int64)v23, &v22);
  v10 = v11;
  if ( v11 == 2 )
  {
    *(_QWORD *)(a4 + 112) = 0;
    return 0;
  }
  if ( v11 )
    goto LABEL_10;
  v18 = FwStringCopy(v23, a4 + 112);
  if ( v18 < 0 )
    return FwHResultToWindowsError((unsigned int)v18);
  return v10;
}

```

## disassembly

```asm
0x180031770  push    rbp
0x180031772  push    rbx
0x180031773  push    rsi
0x180031774  push    rdi
0x180031775  push    r12
0x180031777  push    r14
0x180031779  push    r15
0x18003177b  lea     rbp, [rsp-370h]
0x180031783  sub     rsp, 470h
0x18003178a  mov     rax, cs:__security_cookie
0x180031791  xor     rax, rsp
0x180031794  mov     [rbp+3A0h+var_40], rax
0x18003179b  mov     ebx, r8d
0x18003179e  mov     [rsp+4A0h+var_460], edx
0x1800317a2  mov     esi, edx
0x1800317a4  mov     [rsp+4A0h+var_458], 0
0x1800317ac  mov     r12, rcx
0x1800317af  mov     [rsp+4A0h+var_454], 4
0x1800317b7  xor     edx, edx; Val
0x1800317b9  lea     rcx, [rsp+4A0h+var_450]; void *
0x1800317be  mov     r8d, 410h; Size
0x1800317c4  mov     r15, r9
0x1800317c7  call    memset_0
0x1800317cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800317d3  lea     rax, WPP_GLOBAL_Control
0x1800317da  cmp     rcx, rax
0x1800317dd  jz      short loc_1800317FA
0x1800317df  test    byte ptr [rcx+1Ch], 8
0x1800317e3  jz      short loc_1800317FA
0x1800317e5  mov     rcx, [rcx+10h]
0x1800317e9  lea     r8, WPP_747c00bc9d9b32dc3faec2c7b2e79bbf_Traceguids
0x1800317f0  mov     edx, 24h ; '$'
0x1800317f5  call    WPP_SF_
0x1800317fa  xor     r14d, r14d
0x1800317fd  cmp     ebx, 5
0x180031800  setz    r14b
0x180031804  cmp     esi, 80000000h
0x18003180a  jnz     short loc_180031834
0x18003180c  lea     rcx, [rsp+4A0h+var_460]; enum _tag_FW_PROFILE_TYPE *
0x180031811  call    ?FwGetCurrentProfile@@YAJPEAW4_tag_FW_PROFILE_TYPE@@@Z; FwGetCurrentProfile(_tag_FW_PROFILE_TYPE *)
0x180031816  test    eax, eax
0x180031818  jns     short loc_180031830
0x18003181a  xor     ebx, ebx
0x18003181c  lea     rcx, aCopyconfigtopr; "CopyConfigToProfile"
0x180031823  mov     edx, eax
0x180031825  call    cs:__imp_FwReportReturnError
0x18003182b  jmp     loc_180031B46
0x180031830  mov     esi, [rsp+4A0h+var_460]
0x180031834  lea     rax, [rsp+4A0h+var_460]
0x180031839  mov     [rsp+4A0h+var_460], 0
0x180031841  mov     [rsp+4A0h+var_470], rax
0x180031846  mov     edi, 1
0x18003184b  lea     rax, [rsp+4A0h+var_454]
0x180031850  mov     r9d, r14d
0x180031853  mov     [rsp+4A0h+var_478], rax
0x180031858  mov     r8d, esi
0x18003185b  lea     rax, [rsp+4A0h+var_458]
0x180031860  mov     edx, edi
0x180031862  mov     rcx, r12
0x180031865  mov     [rsp+4A0h+var_480], rax
0x18003186a  call    FWGetConfig2
0x18003186f  mov     ebx, eax
0x180031871  cmp     eax, 2
0x180031874  jz      short loc_1800318A4
0x180031876  test    eax, eax
0x180031878  jz      short loc_180031896
0x18003187a  mov     r8d, eax
0x18003187d  lea     rdx, aFwgetconfig_1; "FWGetConfig"
0x180031884  lea     rcx, aCopyconfigtopr; "CopyConfigToProfile"
0x18003188b  call    cs:__imp_FwReportErrorAsWinError
0x180031891  jmp     loc_180031B46
0x180031896  mov     eax, [rsp+4A0h+var_458]
0x18003189a  neg     eax
0x18003189c  sbb     ecx, ecx
0x18003189e  neg     ecx
0x1800318a0  add     ecx, edi
0x1800318a2  jmp     short loc_1800318A6
0x1800318a4  xor     ecx, ecx
0x1800318a6  mov     [r15+8], ecx
0x1800318aa  lea     rax, [rsp+4A0h+var_460]
0x1800318af  mov     [rsp+4A0h+var_470], rax
0x1800318b4  mov     r9d, r14d
0x1800318b7  lea     rax, [rsp+4A0h+var_454]
0x1800318bc  mov     [rsp+4A0h+var_460], 0
0x1800318c4  mov     [rsp+4A0h+var_478], rax
0x1800318c9  mov     r8d, esi
0x1800318cc  lea     rax, [rsp+4A0h+var_458]
0x1800318d1  mov     edx, 3
0x1800318d6  mov     rcx, r12
0x1800318d9  mov     [rsp+4A0h+var_480], rax
0x1800318de  call    FWGetConfig2
0x1800318e3  mov     ebx, eax
0x1800318e5  cmp     eax, 2
0x1800318e8  jz      short loc_1800318FC
0x1800318ea  test    eax, eax
0x1800318ec  jnz     short loc_18003187A
0x1800318ee  mov     eax, [rsp+4A0h+var_458]
0x1800318f2  neg     eax
0x1800318f4  sbb     ecx, ecx
0x1800318f6  neg     ecx
0x1800318f8  add     ecx, edi
0x1800318fa  jmp     short loc_1800318FE
0x1800318fc  xor     ecx, ecx
0x1800318fe  mov     [r15+0Ch], ecx
0x180031902  lea     rax, [rsp+4A0h+var_460]
0x180031907  mov     [rsp+4A0h+var_470], rax
0x18003190c  mov     r9d, r14d
0x18003190f  lea     rax, [rsp+4A0h+var_454]
0x180031914  mov     [rsp+4A0h+var_460], 0
0x18003191c  mov     [rsp+4A0h+var_478], rax
0x180031921  mov     r8d, esi
0x180031924  lea     rax, [rsp+4A0h+var_458]
0x180031929  mov     edx, 0Ah
0x18003192e  mov     rcx, r12
0x180031931  mov     [rsp+4A0h+var_480], rax
0x180031936  call    FWGetConfig2
0x18003193b  mov     ebx, eax
0x18003193d  cmp     eax, 2
0x180031940  jz      short loc_180031958
0x180031942  test    eax, eax
0x180031944  jnz     loc_18003187A
0x18003194a  mov     eax, [rsp+4A0h+var_458]
0x18003194e  neg     eax
0x180031950  sbb     ecx, ecx
0x180031952  neg     ecx
0x180031954  add     ecx, edi
0x180031956  jmp     short loc_18003195A
0x180031958  xor     ecx, ecx
0x18003195a  mov     [r15+10h], ecx
0x18003195e  lea     rax, [rsp+4A0h+var_460]
0x180031963  mov     [rsp+4A0h+var_470], rax
0x180031968  mov     r9d, r14d
0x18003196b  lea     rax, [rsp+4A0h+var_454]
0x180031970  mov     [rsp+4A0h+var_460], 0
0x180031978  mov     [rsp+4A0h+var_478], rax
0x18003197d  mov     r8d, esi
0x180031980  lea     rax, [rsp+4A0h+var_458]
0x180031985  mov     edx, 4
0x18003198a  mov     rcx, r12
0x18003198d  mov     [rsp+4A0h+var_480], rax
0x180031992  call    FWGetConfig2
0x180031997  mov     ebx, eax
0x180031999  cmp     eax, 2
0x18003199c  jz      short loc_1800319B4
0x18003199e  test    eax, eax
0x1800319a0  jnz     loc_18003187A
0x1800319a6  mov     eax, [rsp+4A0h+var_458]
0x1800319aa  neg     eax
0x1800319ac  sbb     ecx, ecx
0x1800319ae  neg     ecx
0x1800319b0  add     ecx, edi
0x1800319b2  jmp     short loc_1800319B6
0x1800319b4  xor     ecx, ecx
0x1800319b6  mov     [r15+14h], ecx
0x1800319ba  lea     rax, [rsp+4A0h+var_460]
0x1800319bf  mov     [rsp+4A0h+var_470], rax
0x1800319c4  mov     r9d, r14d
0x1800319c7  lea     rax, [rsp+4A0h+var_454]
0x1800319cc  mov     [rsp+4A0h+var_460], 0
0x1800319d4  mov     [rsp+4A0h+var_478], rax
0x1800319d9  mov     r8d, esi
0x1800319dc  lea     rax, [rsp+4A0h+var_458]
0x1800319e1  mov     edx, 5
0x1800319e6  mov     rcx, r12
0x1800319e9  mov     [rsp+4A0h+var_480], rax
0x1800319ee  call    FWGetConfig2
0x1800319f3  mov     ebx, eax
0x1800319f5  cmp     eax, 2
0x1800319f8  jz      short loc_180031A10
0x1800319fa  test    eax, eax
0x1800319fc  jnz     loc_18003187A
0x180031a02  mov     eax, [rsp+4A0h+var_458]
0x180031a06  neg     eax
0x180031a08  sbb     ecx, ecx
0x180031a0a  neg     ecx
0x180031a0c  add     ecx, edi
0x180031a0e  jmp     short loc_180031A12
0x180031a10  xor     ecx, ecx
0x180031a12  mov     [r15+7Ch], ecx
0x180031a16  lea     rax, [rsp+4A0h+var_460]
0x180031a1b  mov     [rsp+4A0h+var_470], rax
0x180031a20  mov     r9d, r14d
0x180031a23  lea     rax, [rsp+4A0h+var_454]
0x180031a28  mov     [rsp+4A0h+var_460], 0
0x180031a30  mov     [rsp+4A0h+var_478], rax
0x180031a35  mov     r8d, esi
0x180031a38  lea     rax, [rsp+4A0h+var_458]
0x180031a3d  mov     edx, 6
0x180031a42  mov     rcx, r12
0x180031a45  mov     [rsp+4A0h+var_480], rax
0x180031a4a  call    FWGetConfig2
0x180031a4f  mov     ebx, eax
0x180031a51  cmp     eax, 2
0x180031a54  jz      short loc_180031A6C
0x180031a56  test    eax, eax
0x180031a58  jnz     loc_18003187A
0x180031a5e  mov     eax, [rsp+4A0h+var_458]
0x180031a62  neg     eax
0x180031a64  sbb     ecx, ecx
0x180031a66  neg     ecx
0x180031a68  inc     ecx
0x180031a6a  jmp     short loc_180031A6E
0x180031a6c  xor     ecx, ecx
0x180031a6e  mov     [r15+80h], ecx
0x180031a75  lea     rax, [rsp+4A0h+var_460]
0x180031a7a  mov     [rsp+4A0h+var_470], rax
0x180031a7f  mov     r9d, r14d
0x180031a82  lea     rax, [rsp+4A0h+var_454]
0x180031a87  mov     [rsp+4A0h+var_460], 0
0x180031a8f  mov     [rsp+4A0h+var_478], rax
0x180031a94  mov     r8d, esi
0x180031a97  lea     rax, [rsp+4A0h+var_458]
0x180031a9c  mov     edx, 8
0x180031aa1  mov     rcx, r12
0x180031aa4  mov     [rsp+4A0h+var_480], rax
0x180031aa9  call    FWGetConfig2
0x180031aae  mov     ebx, eax
0x180031ab0  cmp     eax, 2
0x180031ab3  jz      short loc_180031AC7
0x180031ab5  test    eax, eax
0x180031ab7  jnz     loc_18003187A
0x180031abd  mov     eax, [rsp+4A0h+var_458]
0x180031ac1  mov     [r15+78h], eax
0x180031ac5  jmp     short loc_180031ACF
0x180031ac7  mov     dword ptr [r15+78h], 0
0x180031acf  lea     rax, [rsp+4A0h+var_460]
0x180031ad4  mov     [rsp+4A0h+var_454], 410h
0x180031adc  mov     [rsp+4A0h+var_470], rax
0x180031ae1  mov     r9d, r14d
0x180031ae4  lea     rax, [rsp+4A0h+var_454]
0x180031ae9  mov     [rsp+4A0h+var_460], 0
0x180031af1  mov     [rsp+4A0h+var_478], rax
0x180031af6  mov     r8d, esi
0x180031af9  lea     rax, [rsp+4A0h+var_450]
0x180031afe  mov     edx, 9
0x180031b03  mov     rcx, r12
0x180031b06  mov     [rsp+4A0h+var_480], rax
0x180031b0b  call    FWGetConfig2
0x180031b10  mov     ebx, eax
0x180031b12  cmp     eax, 2
0x180031b15  jz      short loc_180031B3C
0x180031b17  test    eax, eax
0x180031b19  jnz     loc_18003187A
0x180031b1f  lea     rdx, [r15+70h]
0x180031b23  lea     rcx, [rsp+4A0h+var_450]
0x180031b28  call    cs:__imp_FwStringCopy
0x180031b2e  test    eax, eax
0x180031b30  jns     short loc_180031B46
0x180031b32  mov     ecx, eax
0x180031b34  call    cs:__imp_FwHResultToWindowsError
0x180031b3a  jmp     short loc_180031B48
0x180031b3c  mov     qword ptr [r15+70h], 0
0x180031b44  xor     ebx, ebx
0x180031b46  mov     eax, ebx
0x180031b48  mov     rcx, [rbp+3A0h+var_40]
0x180031b4f  xor     rcx, rsp; StackCookie
0x180031b52  call    __security_check_cookie
0x180031b57  add     rsp, 470h
0x180031b5e  pop     r15
0x180031b60  pop     r14
0x180031b62  pop     r12
0x180031b64  pop     rdi
0x180031b65  pop     rsi
0x180031b66  pop     rbx
0x180031b67  pop     rbp
0x180031b68  retn
```
