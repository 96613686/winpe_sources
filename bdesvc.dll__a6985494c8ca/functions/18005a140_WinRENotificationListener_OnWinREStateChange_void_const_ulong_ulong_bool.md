# WinRENotificationListener::OnWinREStateChange(void const *,ulong,ulong &,bool *)

- ea: `0x18005a140`
- end: `0x18005a4ae`
- name: `?OnWinREStateChange@WinRENotificationListener@@KAJPEBXKAEAKPEA_N@Z`
- size: `878`
- prototype: `__int64 __fastcall(const void *, unsigned int, unsigned int *, bool *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000d408`
- `0x18000dc4c`
- `0x18001c6c8`
- `0x180024468`
- `0x180034070`
- `0x180055894`
- `0x18005a140`

## import_xrefs

- `FVEAPI!FveCommitChanges` at `0x18005a413`
- `FVEAPI!FveCommitChanges` at `0x18005a413`
- `FVEAPI!FveKeyManagement` at `0x18005a3cc`
- `FVEAPI!FveKeyManagement` at `0x18005a3cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinRENotificationListener::OnWinREStateChange(
        unsigned int *a1,
        __int64 a2,
        unsigned int *a3,
        bool *a4)
{
  int v5; // edi
  int v7; // ebx
  PVOID *v8; // rcx
  unsigned int v9; // edi
  unsigned int v10; // edi
  unsigned int v11; // edi
  int v12; // eax
  unsigned int OSVolumeHandle; // eax
  unsigned int StatusFlags; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v19; // [rsp+30h] [rbp-20h] BYREF
  void **v20; // [rsp+38h] [rbp-18h] BYREF
  void *v21; // [rsp+40h] [rbp-10h]

  v5 = a2;
  v19 = 0;
  v20 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  v21 = 0;
  v7 = 0;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_2b03041b5f7e35556d7d2b77e5887539_Traceguids);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *a3 )
  {
    if ( v5 != 4 )
    {
      if ( v8 == &WPP_GLOBAL_Control )
        goto LABEL_60;
      if ( (*((_BYTE *)v8 + 28) & 4) == 0 )
        goto LABEL_57;
      WPP_SF_DD(v8[2], 13, WPP_2b03041b5f7e35556d7d2b77e5887539_Traceguids, 4, v5);
      goto LABEL_56;
    }
    v9 = *a1;
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    {
      WPP_SF_d(v8[2], 14, WPP_2b03041b5f7e35556d7d2b77e5887539_Traceguids, v9);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    v10 = v9 - 1;
    if ( v10 && (v11 = v10 - 1) != 0 )
    {
      if ( v11 != 1 )
        goto LABEL_57;
    }
    else
    {
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
        WPP_SF_(v8[2], 15, WPP_2b03041b5f7e35556d7d2b77e5887539_Traceguids);
      v12 = CBdeSvcDE::NotifyWinREStatusChange();
      if ( v12 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_2b03041b5f7e35556d7d2b77e5887539_Traceguids,
          (unsigned int)v12);
    }
    LOBYTE(a2) = 1;
    OSVolumeHandle = FveEasUtil::I_GetOSVolumeHandle(&v20, a2);
    v7 = OSVolumeHandle;
    if ( OSVolumeHandle )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_2b03041b5f7e35556d7d2b77e5887539_Traceguids,
          OSVolumeHandle);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v7 < 0 )
        goto LABEL_57;
    }
    StatusFlags = CFveApiWrapper::GetStatusFlags(v21, &v19);
    v7 = StatusFlags;
    if ( StatusFlags )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_2b03041b5f7e35556d7d2b77e5887539_Traceguids, StatusFlags);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v7 < 0 )
        goto LABEL_57;
    }
    else
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (v19 & 0x601) == 0x201 )
    {
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
        WPP_SF_d(v8[2], 19, WPP_2b03041b5f7e35556d7d2b77e5887539_Traceguids, v19);
      v15 = FveEasUtil::I_GetOSVolumeHandle(&v20, 0);
      v7 = v15;
      if ( !v15 )
        goto LABEL_51;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_2b03041b5f7e35556d7d2b77e5887539_Traceguids, v15);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v7 >= 0 )
      {
LABEL_51:
        v16 = FveKeyManagement(v21, 256, 0);
        v7 = v16;
        if ( !v16 )
          goto LABEL_52;
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_2b03041b5f7e35556d7d2b77e5887539_Traceguids, v16);
          v8 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v7 >= 0 )
        {
LABEL_52:
          v17 = FveCommitChanges(v21);
          v7 = v17;
          if ( v17 )
          {
            v8 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              goto LABEL_60;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
              goto LABEL_57;
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_2b03041b5f7e35556d7d2b77e5887539_Traceguids, v17);
          }
          goto LABEL_56;
        }
      }
    }
  }
  else
  {
    if ( v8 == &WPP_GLOBAL_Control )
      goto LABEL_60;
    if ( (*((_BYTE *)v8 + 28) & 8) != 0 )
    {
      WPP_SF_(v8[2], 12, WPP_2b03041b5f7e35556d7d2b77e5887539_Traceguids);
LABEL_56:
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
LABEL_57:
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x20) != 0 )
    WPP_SF_d(v8[2], 23, WPP_2b03041b5f7e35556d7d2b77e5887539_Traceguids, (unsigned int)v7);
LABEL_60:
  v20 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v20);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005a140  mov     [rsp-28h+arg_8], rbx
0x18005a145  mov     [rsp-28h+arg_10], rsi
0x18005a14a  push    rbp
0x18005a14b  push    rdi
0x18005a14c  push    r12
0x18005a14e  push    r13
0x18005a150  push    r14
0x18005a152  mov     rbp, rsp
0x18005a155  sub     rsp, 50h
0x18005a159  mov     rax, cs:__security_cookie
0x18005a160  xor     rax, rsp
0x18005a163  mov     [rbp+var_8], rax
0x18005a167  mov     rsi, r8
0x18005a16a  mov     edi, edx
0x18005a16c  mov     r14, rcx
0x18005a16f  mov     [rbp+var_20], 0
0x18005a176  lea     rax, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x18005a17d  mov     [rbp+var_18], rax
0x18005a181  mov     [rbp+var_10], 0
0x18005a189  xor     ebx, ebx
0x18005a18b  lea     r12, WPP_GLOBAL_Control
0x18005a192  lea     r13, WPP_2b03041b5f7e35556d7d2b77e5887539_Traceguids
0x18005a199  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a1a0  cmp     rcx, r12
0x18005a1a3  jz      short loc_18005A1C1
0x18005a1a5  test    byte ptr [rcx+1Ch], 20h
0x18005a1a9  jz      short loc_18005A1C1
0x18005a1ab  lea     edx, [rbx+0Bh]
0x18005a1ae  mov     r8, r13
0x18005a1b1  mov     rcx, [rcx+10h]
0x18005a1b5  call    WPP_SF_
0x18005a1ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a1c1  cmp     [rsi], ebx
0x18005a1c3  jnz     short loc_18005A1EE
0x18005a1c5  cmp     rcx, r12
0x18005a1c8  jz      loc_18005A472
0x18005a1ce  test    byte ptr [rcx+1Ch], 8
0x18005a1d2  jz      loc_18005A452
0x18005a1d8  mov     edx, 0Ch
0x18005a1dd  mov     r8, r13
0x18005a1e0  mov     rcx, [rcx+10h]
0x18005a1e4  call    WPP_SF_
0x18005a1e9  jmp     loc_18005A44B
0x18005a1ee  mov     r9d, 4
0x18005a1f4  cmp     edi, r9d
0x18005a1f7  jz      short loc_18005A225
0x18005a1f9  cmp     rcx, r12
0x18005a1fc  jz      loc_18005A472
0x18005a202  test    [rcx+1Ch], r9b
0x18005a206  jz      loc_18005A452
0x18005a20c  lea     edx, [r9+9]
0x18005a210  mov     [rsp+50h+var_30], edi
0x18005a214  mov     r8, r13
0x18005a217  mov     rcx, [rcx+10h]
0x18005a21b  call    WPP_SF_DD
0x18005a220  jmp     loc_18005A44B
0x18005a225  mov     edi, [r14]
0x18005a228  cmp     rcx, r12
0x18005a22b  jz      short loc_18005A24E
0x18005a22d  test    byte ptr [rcx+1Ch], 8
0x18005a231  jz      short loc_18005A24E
0x18005a233  mov     edx, 0Eh
0x18005a238  mov     r9d, edi
0x18005a23b  mov     r8, r13
0x18005a23e  mov     rcx, [rcx+10h]
0x18005a242  call    WPP_SF_d
0x18005a247  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a24e  sub     edi, 1
0x18005a251  jz      short loc_18005A262
0x18005a253  sub     edi, 1
0x18005a256  jz      short loc_18005A262
0x18005a258  cmp     edi, 1
0x18005a25b  jz      short loc_18005A2AD
0x18005a25d  jmp     loc_18005A452
0x18005a262  cmp     rcx, r12
0x18005a265  jz      short loc_18005A27E
0x18005a267  test    byte ptr [rcx+1Ch], 8
0x18005a26b  jz      short loc_18005A27E
0x18005a26d  mov     edx, 0Fh
0x18005a272  mov     r8, r13
0x18005a275  mov     rcx, [rcx+10h]
0x18005a279  call    WPP_SF_
0x18005a27e  call    ?NotifyWinREStatusChange@CBdeSvcDE@@SAJXZ; CBdeSvcDE::NotifyWinREStatusChange(void)
0x18005a283  test    eax, eax
0x18005a285  jns     short loc_18005A2AD
0x18005a287  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a28e  cmp     rcx, r12
0x18005a291  jz      short loc_18005A2AD
0x18005a293  test    byte ptr [rcx+1Ch], 2
0x18005a297  jz      short loc_18005A2AD
0x18005a299  mov     edx, 10h
0x18005a29e  mov     r9d, eax
0x18005a2a1  mov     r8, r13
0x18005a2a4  mov     rcx, [rcx+10h]
0x18005a2a8  call    WPP_SF_d
0x18005a2ad  mov     dl, 1
0x18005a2af  lea     rcx, [rbp+var_18]
0x18005a2b3  call    ?I_GetOSVolumeHandle@FveEasUtil@@CAJAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z; FveEasUtil::I_GetOSVolumeHandle(Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)
0x18005a2b8  mov     ebx, eax
0x18005a2ba  mov     dil, 40h ; '@'
0x18005a2bd  test    eax, eax
0x18005a2bf  jz      short loc_18005A2F6
0x18005a2c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a2c8  cmp     rcx, r12
0x18005a2cb  jz      short loc_18005A2EE
0x18005a2cd  test    [rcx+1Ch], dil
0x18005a2d1  jz      short loc_18005A2EE
0x18005a2d3  mov     edx, 11h
0x18005a2d8  mov     r9d, eax
0x18005a2db  mov     r8, r13
0x18005a2de  mov     rcx, [rcx+10h]
0x18005a2e2  call    WPP_SF_d
0x18005a2e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a2ee  test    ebx, ebx
0x18005a2f0  js      loc_18005A452
0x18005a2f6  lea     rdx, [rbp+var_20]; unsigned int *
0x18005a2fa  mov     rcx, [rbp+var_10]; void *
0x18005a2fe  call    ?GetStatusFlags@CFveApiWrapper@@SAJPEAXPEAK@Z; CFveApiWrapper::GetStatusFlags(void *,ulong *)
0x18005a303  mov     ebx, eax
0x18005a305  test    eax, eax
0x18005a307  jz      short loc_18005A340
0x18005a309  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a310  cmp     rcx, r12
0x18005a313  jz      short loc_18005A336
0x18005a315  test    [rcx+1Ch], dil
0x18005a319  jz      short loc_18005A336
0x18005a31b  mov     edx, 12h
0x18005a320  mov     r9d, eax
0x18005a323  mov     r8, r13
0x18005a326  mov     rcx, [rcx+10h]
0x18005a32a  call    WPP_SF_d
0x18005a32f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a336  test    ebx, ebx
0x18005a338  js      loc_18005A452
0x18005a33e  jmp     short loc_18005A347
0x18005a340  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a347  mov     r9d, [rbp+var_20]
0x18005a34b  mov     eax, r9d
0x18005a34e  and     eax, 601h
0x18005a353  cmp     eax, 201h
0x18005a358  jnz     loc_18005A452
0x18005a35e  cmp     rcx, r12
0x18005a361  jz      short loc_18005A37A
0x18005a363  test    byte ptr [rcx+1Ch], 8
0x18005a367  jz      short loc_18005A37A
0x18005a369  mov     edx, 13h
0x18005a36e  mov     r8, r13
0x18005a371  mov     rcx, [rcx+10h]
0x18005a375  call    WPP_SF_d
0x18005a37a  xor     edx, edx
0x18005a37c  lea     rcx, [rbp+var_18]
0x18005a380  call    ?I_GetOSVolumeHandle@FveEasUtil@@CAJAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z; FveEasUtil::I_GetOSVolumeHandle(Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)
0x18005a385  mov     ebx, eax
0x18005a387  test    eax, eax
0x18005a389  jz      short loc_18005A3C0
0x18005a38b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a392  cmp     rcx, r12
0x18005a395  jz      short loc_18005A3B8
0x18005a397  test    [rcx+1Ch], dil
0x18005a39b  jz      short loc_18005A3B8
0x18005a39d  mov     edx, 14h
0x18005a3a2  mov     r9d, eax
0x18005a3a5  mov     r8, r13
0x18005a3a8  mov     rcx, [rcx+10h]
0x18005a3ac  call    WPP_SF_d
0x18005a3b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a3b8  test    ebx, ebx
0x18005a3ba  js      loc_18005A452
0x18005a3c0  xor     r8d, r8d
0x18005a3c3  mov     edx, 100h
0x18005a3c8  mov     rcx, [rbp+var_10]
0x18005a3cc  call    cs:__imp_FveKeyManagement
0x18005a3d3  nop     dword ptr [rax+rax+00h]
0x18005a3d8  mov     ebx, eax
0x18005a3da  test    eax, eax
0x18005a3dc  jz      short loc_18005A40F
0x18005a3de  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a3e5  cmp     rcx, r12
0x18005a3e8  jz      short loc_18005A40B
0x18005a3ea  test    [rcx+1Ch], dil
0x18005a3ee  jz      short loc_18005A40B
0x18005a3f0  mov     edx, 15h
0x18005a3f5  mov     r9d, eax
0x18005a3f8  mov     r8, r13
0x18005a3fb  mov     rcx, [rcx+10h]
0x18005a3ff  call    WPP_SF_d
0x18005a404  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a40b  test    ebx, ebx
0x18005a40d  js      short loc_18005A452
0x18005a40f  mov     rcx, [rbp+var_10]
0x18005a413  call    cs:__imp_FveCommitChanges
0x18005a41a  nop     dword ptr [rax+rax+00h]
0x18005a41f  mov     ebx, eax
0x18005a421  test    eax, eax
0x18005a423  jz      short loc_18005A44B
0x18005a425  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a42c  cmp     rcx, r12
0x18005a42f  jz      short loc_18005A472
0x18005a431  test    [rcx+1Ch], dil
0x18005a435  jz      short loc_18005A452
0x18005a437  mov     edx, 16h
0x18005a43c  mov     r9d, eax
0x18005a43f  mov     r8, r13
0x18005a442  mov     rcx, [rcx+10h]
0x18005a446  call    WPP_SF_d
0x18005a44b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a452  cmp     rcx, r12
0x18005a455  jz      short loc_18005A472
0x18005a457  test    byte ptr [rcx+1Ch], 20h
0x18005a45b  jz      short loc_18005A472
0x18005a45d  mov     edx, 17h
0x18005a462  mov     r9d, ebx
0x18005a465  mov     r8, r13
0x18005a468  mov     rcx, [rcx+10h]
0x18005a46c  call    WPP_SF_d
0x18005a471  nop
0x18005a472  lea     rax, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x18005a479  mov     [rbp+var_18], rax
0x18005a47d  lea     rcx, [rbp+var_18]
0x18005a481  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x18005a486  mov     eax, ebx
0x18005a488  mov     rcx, [rbp+var_8]
0x18005a48c  xor     rcx, rsp; StackCookie
0x18005a48f  call    __security_check_cookie
0x18005a494  lea     r11, [rsp+50h+var_s0]
0x18005a499  mov     rbx, [r11+38h]
0x18005a49d  mov     rsi, [r11+40h]
0x18005a4a1  mov     rsp, r11
0x18005a4a4  pop     r14
0x18005a4a6  pop     r13
0x18005a4a8  pop     r12
0x18005a4aa  pop     rdi
0x18005a4ab  pop     rbp
0x18005a4ac  retn
```
