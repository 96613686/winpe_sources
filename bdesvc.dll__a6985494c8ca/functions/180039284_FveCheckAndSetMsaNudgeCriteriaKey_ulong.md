# FveCheckAndSetMsaNudgeCriteriaKey(ulong)

- ea: `0x180039284`
- end: `0x180039707`
- name: `?FveCheckAndSetMsaNudgeCriteriaKey@@YAJK@Z`
- size: `1155`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800090d0`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000dc4c`
- `0x18001aad0`
- `0x180034070`
- `0x180034d28`
- `0x180039284`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039356`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039356`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180039616`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180039616`
- `FVEAPI!FveIsVolumeEncryptable` at `0x18003951f`
- `FVEAPI!FveIsVolumeEncryptable` at `0x18003951f`
- `FVEAPI!FveGetStatus` at `0x1800394c1`
- `FVEAPI!FveGetStatus` at `0x1800394c1`
- `FVEAPI!FveOpenVolumeByHandle` at `0x1800393fe`
- `FVEAPI!FveOpenVolumeByHandle` at `0x1800393fe`
- `FVEAPI!FveCloseVolume` at `0x1800393ce`
- `FVEAPI!FveCloseVolume` at `0x18003968f`
- `FVEAPI!FveCloseVolume` at `0x1800393ce`
- `FVEAPI!FveCloseVolume` at `0x18003968f`
- `FVEAPI!FveFindNextVolume` at `0x18003956f`
- `FVEAPI!FveFindNextVolume` at `0x18003956f`
- `FVEAPI!FveFindFirstVolume` at `0x1800393aa`
- `FVEAPI!FveFindFirstVolume` at `0x1800393aa`

## pseudocode

```c
__int64 __fastcall FveCheckAndSetMsaNudgeCriteriaKey(int a1)
{
  signed int Status; // ebx
  int v2; // esi
  int v3; // r13d
  int v4; // r12d
  int v5; // r14d
  int v6; // r15d
  int i; // eax
  signed int v8; // edi
  int v9; // edi
  PVOID *v10; // rcx
  LSTATUS v11; // eax
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  int v14; // [rsp+40h] [rbp-C0h]
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  int Data; // [rsp+50h] [rbp-B0h] BYREF
  int pvData; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+68h] [rbp-98h] BYREF
  DWORD v20; // [rsp+6Ch] [rbp-94h] BYREF
  void **v21; // [rsp+70h] [rbp-90h] BYREF
  __int64 v22; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v23[2]; // [rsp+80h] [rbp-80h] BYREF
  char v24[4]; // [rsp+88h] [rbp-78h] BYREF
  int v25; // [rsp+8Ch] [rbp-74h]
  int v26; // [rsp+98h] [rbp-68h]
  char v27; // [rsp+B8h] [rbp-48h]

  Data = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ef8dbe2ba40b3b6c07a9725bb2dd3169_Traceguids);
  v15 = -1;
  pvData = 0;
  v20 = 0;
  Status = 0;
  pcbData = 4;
  memset_0(v23, 0, 0x90u);
  v18 = 0;
  v21 = &Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::`vftable';
  v22 = 0;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\BitLocker\\MsaConnected",
         L"ShowMsaConnectPrompt",
         4u,
         &v20,
         &pvData,
         &pcbData) != 2
    && pvData == Data )
  {
    goto LABEL_56;
  }
  v2 = 1;
  v14 = 0;
  v18 = 0xFFFFFFFF00000001uLL;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v21);
  for ( i = FveFindFirstVolume(&v22, &v18); ; i = FveFindNextVolume(v22, &v18) )
  {
    v8 = i;
    if ( i < 0 )
      break;
    if ( v15 != -1 )
    {
      FveCloseVolume(v15);
      v15 = -1;
    }
    LODWORD(pdwType) = 0;
    v9 = FveOpenVolumeByHandle(v22, 0, 0, 0xFFFFFFFFLL, pdwType, &v15);
    if ( v9 == -2147024894 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ef8dbe2ba40b3b6c07a9725bb2dd3169_Traceguids, 2147942402LL);
    }
    else
    {
      if ( v9 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            WPP_ef8dbe2ba40b3b6c07a9725bb2dd3169_Traceguids,
            (unsigned int)v9);
          v10 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v9 < 0 )
          goto LABEL_57;
      }
      memset_0(v24, 0, 0x88u);
      v23[0] = 144;
      v23[1] = 10;
      Status = FveGetStatus(v15, v23);
      if ( Status < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_ef8dbe2ba40b3b6c07a9725bb2dd3169_Traceguids,
            (unsigned int)Status);
LABEL_23:
        Status = 0;
        continue;
      }
      if ( v25 >= 0 && (v25 & 0x400000) == 0 )
      {
        Status = FveIsVolumeEncryptable(v15);
        if ( Status < 0 )
          goto LABEL_23;
        if ( (v25 & 1) != 0 && (v27 & 8) != 0 )
        {
          v3 = 1;
          if ( (v25 & 0x10) != 0 )
          {
            if ( v26 >= 0 )
              v4 = 1;
            else
              v14 = 1;
          }
        }
        if ( (v25 & 0x2000000) != 0 )
          v6 = 1;
        if ( (v25 & 0x400) != 0 )
          v5 = 1;
      }
    }
  }
  if ( i != -2147024878 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_ef8dbe2ba40b3b6c07a9725bb2dd3169_Traceguids,
        (unsigned int)i);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    Status = v8;
    goto LABEL_57;
  }
  if ( v4 || !v3 || v14 || !v5 || !v6 )
    v2 = 0;
  Data = v2;
  v11 = RegSetKeyValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\BitLocker\\MsaConnected",
          L"ShowMsaConnectPrompt",
          4u,
          &Data,
          4u);
  if ( !v11 )
  {
LABEL_56:
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_57;
  }
  if ( v11 > 0 )
    Status = (unsigned __int16)v11 | 0x80070000;
  else
    Status = v11;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_dS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"ShowMsaConnectPrompt");
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_57:
  if ( v15 != -1 )
  {
    FveCloseVolume(v15);
    v10 = (PVOID *)WPP_GLOBAL_Control;
    v15 = -1;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 )
    WPP_SF_d(v10[2], 16, WPP_ef8dbe2ba40b3b6c07a9725bb2dd3169_Traceguids, (unsigned int)Status);
  v21 = &Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v21);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x180039284  push    rbp
0x180039286  push    rbx
0x180039287  push    rsi
0x180039288  push    rdi
0x180039289  push    r12
0x18003928b  push    r13
0x18003928d  push    r14
0x18003928f  push    r15
0x180039291  lea     rbp, [rsp-28h]
0x180039296  sub     rsp, 128h
0x18003929d  mov     rax, cs:__security_cookie
0x1800392a4  xor     rax, rsp
0x1800392a7  mov     [rbp+60h+var_50], rax
0x1800392ab  mov     [rsp+160h+Data], ecx
0x1800392af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800392b6  lea     rax, WPP_GLOBAL_Control
0x1800392bd  cmp     rcx, rax
0x1800392c0  jz      short loc_1800392DD
0x1800392c2  test    byte ptr [rcx+1Ch], 20h
0x1800392c6  jz      short loc_1800392DD
0x1800392c8  mov     rcx, [rcx+10h]
0x1800392cc  lea     r8, WPP_ef8dbe2ba40b3b6c07a9725bb2dd3169_Traceguids
0x1800392d3  mov     edx, 0Ah
0x1800392d8  call    WPP_SF_
0x1800392dd  xor     edi, edi
0x1800392df  mov     [rsp+160h+var_118], 0FFFFFFFFFFFFFFFFh
0x1800392e8  xor     edx, edx; Val
0x1800392ea  mov     [rsp+160h+var_108], edi
0x1800392ee  mov     r8d, 90h; Size
0x1800392f4  mov     [rsp+160h+var_F4], edi
0x1800392f8  lea     rcx, [rbp+60h+var_E0]; void *
0x1800392fc  mov     ebx, edi
0x1800392fe  lea     esi, [rdi+4]
0x180039301  mov     [rsp+160h+var_F8], esi
0x180039305  call    memset_0
0x18003930a  lea     rax, ??_7?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::`vftable'
0x180039311  mov     [rsp+160h+var_100], rdi
0x180039316  mov     [rsp+160h+var_F0], rax
0x18003931b  lea     r8, aShowmsaconnect; "ShowMsaConnectPrompt"
0x180039322  lea     rax, [rsp+160h+var_F8]
0x180039327  mov     [rsp+160h+var_E8], rdi
0x18003932c  mov     [rsp+160h+pcbData], rax; pcbData
0x180039331  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039338  lea     rax, [rsp+160h+var_108]
0x18003933d  mov     r9d, esi; dwFlags
0x180039340  mov     [rsp+160h+pvData], rax; pvData
0x180039345  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003934c  lea     rax, [rsp+160h+var_F4]
0x180039351  mov     [rsp+160h+pdwType], rax; pdwType
0x180039356  call    cs:__imp_RegGetValueW
0x18003935d  nop     dword ptr [rax+rax+00h]
0x180039362  cmp     eax, 2
0x180039365  jz      short loc_180039375
0x180039367  mov     eax, [rsp+160h+Data]
0x18003936b  cmp     [rsp+160h+var_108], eax
0x18003936f  jz      loc_180039674
0x180039375  mov     esi, 1
0x18003937a  mov     [rsp+160h+var_120], edi
0x18003937e  lea     rcx, [rsp+160h+var_F0]
0x180039383  mov     dword ptr [rsp+160h+var_100], esi
0x180039387  mov     r13d, edi
0x18003938a  mov     dword ptr [rsp+160h+var_100+4], 0FFFFFFFFh
0x180039392  mov     r12d, edi
0x180039395  mov     r14d, edi
0x180039398  mov     r15d, edi
0x18003939b  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x1800393a0  lea     rdx, [rsp+160h+var_100]
0x1800393a5  lea     rcx, [rsp+160h+var_E8]
0x1800393aa  call    cs:__imp_FveFindFirstVolume
0x1800393b1  nop     dword ptr [rax+rax+00h]
0x1800393b6  mov     edi, eax
0x1800393b8  test    eax, eax
0x1800393ba  js      loc_180039580
0x1800393c0  mov     rcx, [rsp+160h+var_118]
0x1800393c5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800393c9  cmp     rcx, rdi
0x1800393cc  jz      short loc_1800393DF
0x1800393ce  call    cs:__imp_FveCloseVolume
0x1800393d5  nop     dword ptr [rax+rax+00h]
0x1800393da  mov     [rsp+160h+var_118], rdi
0x1800393df  mov     rcx, [rsp+160h+var_E8]
0x1800393e4  lea     rax, [rsp+160h+var_118]
0x1800393e9  mov     [rsp+160h+pvData], rax
0x1800393ee  mov     r9d, edi
0x1800393f1  xor     r8d, r8d
0x1800393f4  mov     dword ptr [rsp+160h+pdwType], 0
0x1800393fc  xor     edx, edx
0x1800393fe  call    cs:__imp_FveOpenVolumeByHandle
0x180039405  nop     dword ptr [rax+rax+00h]
0x18003940a  mov     r8d, 80070002h
0x180039410  mov     edi, eax
0x180039412  cmp     eax, r8d
0x180039415  jnz     short loc_180039455
0x180039417  mov     rcx, cs:WPP_GLOBAL_Control
0x18003941e  lea     rax, WPP_GLOBAL_Control
0x180039425  cmp     rcx, rax
0x180039428  jz      loc_180039565
0x18003942e  test    byte ptr [rcx+1Ch], 4
0x180039432  jz      loc_180039565
0x180039438  mov     rcx, [rcx+10h]
0x18003943c  mov     r9d, r8d
0x18003943f  lea     r8, WPP_ef8dbe2ba40b3b6c07a9725bb2dd3169_Traceguids
0x180039446  mov     edx, 0Bh
0x18003944b  call    WPP_SF_d
0x180039450  jmp     loc_180039565
0x180039455  test    edi, edi
0x180039457  jz      short loc_180039499
0x180039459  mov     rcx, cs:WPP_GLOBAL_Control
0x180039460  lea     rax, WPP_GLOBAL_Control
0x180039467  cmp     rcx, rax
0x18003946a  jz      short loc_180039491
0x18003946c  test    byte ptr [rcx+1Ch], 40h
0x180039470  jz      short loc_180039491
0x180039472  mov     rcx, [rcx+10h]
0x180039476  lea     r8, WPP_ef8dbe2ba40b3b6c07a9725bb2dd3169_Traceguids
0x18003947d  mov     edx, 0Ch
0x180039482  mov     r9d, edi
0x180039485  call    WPP_SF_d
0x18003948a  mov     rcx, cs:WPP_GLOBAL_Control
0x180039491  test    edi, edi
0x180039493  js      loc_18003967B
0x180039499  xor     edx, edx; Val
0x18003949b  lea     rcx, [rbp+60h+var_D8]; void *
0x18003949f  mov     r8d, 88h; Size
0x1800394a5  call    memset_0
0x1800394aa  mov     rcx, [rsp+160h+var_118]
0x1800394af  lea     rdx, [rbp+60h+var_E0]
0x1800394b3  mov     [rbp+60h+var_E0], 90h
0x1800394ba  mov     [rbp+60h+var_DC], 0Ah
0x1800394c1  call    cs:__imp_FveGetStatus
0x1800394c8  nop     dword ptr [rax+rax+00h]
0x1800394cd  mov     ebx, eax
0x1800394cf  test    eax, eax
0x1800394d1  jns     short loc_180039508
0x1800394d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800394da  lea     rax, WPP_GLOBAL_Control
0x1800394e1  cmp     rcx, rax
0x1800394e4  jz      short loc_180039504
0x1800394e6  test    byte ptr [rcx+1Ch], 2
0x1800394ea  jz      short loc_180039504
0x1800394ec  mov     rcx, [rcx+10h]
0x1800394f0  lea     r8, WPP_ef8dbe2ba40b3b6c07a9725bb2dd3169_Traceguids
0x1800394f7  mov     edx, 0Dh
0x1800394fc  mov     r9d, ebx
0x1800394ff  call    WPP_SF_d
0x180039504  xor     ebx, ebx
0x180039506  jmp     short loc_180039565
0x180039508  test    [rbp+60h+var_D4], 80000000h
0x18003950f  jnz     short loc_180039565
0x180039511  test    [rbp+60h+var_D4], 400000h
0x180039518  jnz     short loc_180039565
0x18003951a  mov     rcx, [rsp+160h+var_118]
0x18003951f  call    cs:__imp_FveIsVolumeEncryptable
0x180039526  nop     dword ptr [rax+rax+00h]
0x18003952b  mov     ebx, eax
0x18003952d  test    eax, eax
0x18003952f  js      short loc_180039504
0x180039531  mov     eax, [rbp+60h+var_D4]
0x180039534  test    sil, al
0x180039537  jz      short loc_180039555
0x180039539  test    [rbp+60h+var_A8], 8
0x18003953d  jz      short loc_180039555
0x18003953f  mov     r13d, esi
0x180039542  test    al, 10h
0x180039544  jz      short loc_180039555
0x180039546  cmp     [rbp+60h+var_C8], 0
0x18003954a  jge     short loc_180039552
0x18003954c  mov     [rsp+160h+var_120], esi
0x180039550  jmp     short loc_180039555
0x180039552  mov     r12d, esi
0x180039555  bt      eax, 19h
0x180039559  cmovb   r15d, esi
0x18003955d  bt      eax, 0Ah
0x180039561  cmovb   r14d, esi
0x180039565  mov     rcx, [rsp+160h+var_E8]
0x18003956a  lea     rdx, [rsp+160h+var_100]
0x18003956f  call    cs:__imp_FveFindNextVolume
0x180039576  nop     dword ptr [rax+rax+00h]
0x18003957b  jmp     loc_1800393B6
0x180039580  cmp     edi, 80070012h
0x180039586  jz      short loc_1800395C7
0x180039588  mov     rcx, cs:WPP_GLOBAL_Control
0x18003958f  lea     rax, WPP_GLOBAL_Control
0x180039596  cmp     rcx, rax
0x180039599  jz      short loc_1800395C0
0x18003959b  test    byte ptr [rcx+1Ch], 2
0x18003959f  jz      short loc_1800395C0
0x1800395a1  mov     rcx, [rcx+10h]
0x1800395a5  lea     r8, WPP_ef8dbe2ba40b3b6c07a9725bb2dd3169_Traceguids
0x1800395ac  mov     edx, 0Eh
0x1800395b1  mov     r9d, edi
0x1800395b4  call    WPP_SF_d
0x1800395b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800395c0  mov     ebx, edi
0x1800395c2  jmp     loc_18003967B
0x1800395c7  test    r12d, r12d
0x1800395ca  jnz     short loc_1800395E2
0x1800395cc  test    r13d, r13d
0x1800395cf  jz      short loc_1800395E2
0x1800395d1  cmp     [rsp+160h+var_120], r12d
0x1800395d6  jnz     short loc_1800395E2
0x1800395d8  test    r14d, r14d
0x1800395db  jz      short loc_1800395E2
0x1800395dd  test    r15d, r15d
0x1800395e0  jnz     short loc_1800395E4
0x1800395e2  xor     esi, esi
0x1800395e4  mov     ecx, 4
0x1800395e9  mov     [rsp+160h+Data], esi
0x1800395ed  mov     dword ptr [rsp+160h+pvData], ecx; cbData
0x1800395f1  lea     rax, [rsp+160h+Data]
0x1800395f6  mov     r9d, ecx; dwType
0x1800395f9  mov     [rsp+160h+pdwType], rax; lpData
0x1800395fe  lea     rsi, aShowmsaconnect; "ShowMsaConnectPrompt"
0x180039605  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003960c  mov     r8, rsi; lpValueName
0x18003960f  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180039616  call    cs:__imp_RegSetKeyValueW
0x18003961d  nop     dword ptr [rax+rax+00h]
0x180039622  test    eax, eax
0x180039624  jz      short loc_180039674
0x180039626  jg      short loc_18003962C
0x180039628  mov     ebx, eax
0x18003962a  jmp     short loc_180039635
0x18003962c  movzx   ebx, ax
0x18003962f  or      ebx, 80070000h
0x180039635  mov     rcx, cs:WPP_GLOBAL_Control
0x18003963c  lea     rdi, WPP_GLOBAL_Control
0x180039643  cmp     rcx, rdi
0x180039646  jz      short loc_180039682
0x180039648  test    byte ptr [rcx+1Ch], 2
0x18003964c  jz      short loc_180039682
0x18003964e  mov     rcx, [rcx+10h]; LoggerHandle
0x180039652  lea     r8, WPP_ef8dbe2ba40b3b6c07a9725bb2dd3169_Traceguids
0x180039659  mov     edx, 0Fh
0x18003965e  mov     [rsp+160h+pdwType], rsi; __int64
0x180039663  mov     r9d, ebx
0x180039666  call    WPP_SF_dS
0x18003966b  mov     rcx, cs:WPP_GLOBAL_Control
0x180039672  jmp     short loc_180039682
0x180039674  mov     rcx, cs:WPP_GLOBAL_Control
0x18003967b  lea     rdi, WPP_GLOBAL_Control
0x180039682  cmp     [rsp+160h+var_118], 0FFFFFFFFFFFFFFFFh
0x180039688  jz      short loc_1800396AB
0x18003968a  mov     rcx, [rsp+160h+var_118]
0x18003968f  call    cs:__imp_FveCloseVolume
0x180039696  nop     dword ptr [rax+rax+00h]
0x18003969b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800396a2  mov     [rsp+160h+var_118], 0FFFFFFFFFFFFFFFFh
0x1800396ab  cmp     rcx, rdi
0x1800396ae  jz      short loc_1800396CE
0x1800396b0  test    byte ptr [rcx+1Ch], 20h
0x1800396b4  jz      short loc_1800396CE
0x1800396b6  mov     rcx, [rcx+10h]
0x1800396ba  lea     r8, WPP_ef8dbe2ba40b3b6c07a9725bb2dd3169_Traceguids
0x1800396c1  mov     edx, 10h
0x1800396c6  mov     r9d, ebx
0x1800396c9  call    WPP_SF_d
0x1800396ce  lea     rax, ??_7?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::`vftable'
0x1800396d5  lea     rcx, [rsp+160h+var_F0]
0x1800396da  mov     [rsp+160h+var_F0], rax
0x1800396df  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x1800396e4  mov     eax, ebx
0x1800396e6  mov     rcx, [rbp+60h+var_50]
0x1800396ea  xor     rcx, rsp; StackCookie
0x1800396ed  call    __security_check_cookie
0x1800396f2  add     rsp, 128h
0x1800396f9  pop     r15
0x1800396fb  pop     r14
0x1800396fd  pop     r13
0x1800396ff  pop     r12
0x180039701  pop     rdi
0x180039702  pop     rsi
0x180039703  pop     rbx
0x180039704  pop     rbp
0x180039705  retn
```
