# DdcCommandHandlerDesktop::ValidateLockParameters(ushort const *,ushort const *,int,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180003210`
- end: `0x1800033ec`
- name: `?ValidateLockParameters@DdcCommandHandlerDesktop@@UEAAJPEBG0HAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `476`
- prototype: `__int64 __fastcall(int, __int64, __int64, int, __int64 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800026ac`
- `0x1800027e4`
- `0x180003210`
- `0x1800033f4`

## import_xrefs

- `MdmCommon!MdmEnumerateUsers` at `0x18000331b`
- `MdmCommon!MdmEnumerateUsers` at `0x18000331b`

## string_xrefs

- `0x1800033ca`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\ddccomimplementationsdesktop\ddccommandhandlerdesktop.cpp`

## pseudocode

```c
__int64 __fastcall DdcCommandHandlerDesktop::ValidateLockParameters(
        int a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 *a5)
{
  int v5; // ebx
  const wchar_t *v6; // rdx
  const wchar_t *v7; // rcx
  wchar_t *v8; // rbp
  wchar_t *v9; // rdi
  __int64 v10; // rsi
  size_t v11; // r8
  char v13; // [rsp+20h] [rbp-58h]
  const char *v14; // [rsp+28h] [rbp-50h]
  wchar_t *S1[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+40h] [rbp-38h]

  *(_OWORD *)S1 = 0;
  v16 = 0;
  if ( a2 )
  {
    v5 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomman"
                      "dhandlerdesktop.cpp",
        145,
        (__int64)"CBR(pwszPin == nullptr)");
    goto LABEL_32;
  }
  if ( a3 )
  {
    v5 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomman"
                      "dhandlerdesktop.cpp",
        148,
        (__int64)"CBR(pwszCpn == nullptr)");
    goto LABEL_32;
  }
  if ( a4 )
  {
    v5 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomman"
                      "dhandlerdesktop.cpp",
        151,
        (__int64)"CBR(fRingAfterLock == 0)");
    goto LABEL_32;
  }
  if ( a5[1] - *a5 == 32 )
  {
    v5 = MdmEnumerateUsers(S1, 0, 0, 1);
    if ( v5 >= 0 )
    {
      v8 = S1[1];
      v9 = S1[0];
      if ( S1[0] != S1[1] )
      {
        v10 = *a5;
        do
        {
          if ( *(_QWORD *)(v10 + 24) <= 7u )
            v6 = (const wchar_t *)v10;
          else
            v6 = *(const wchar_t **)v10;
          v11 = *((_QWORD *)v9 + 2);
          if ( *((_QWORD *)v9 + 3) <= 7u )
            v7 = v9;
          else
            v7 = *(const wchar_t **)v9;
          if ( v11 == *(_QWORD *)(v10 + 16) && (!v11 || !wmemcmp(v7, v6, v11)) )
            break;
          v9 += 16;
        }
        while ( v9 != v8 );
        if ( v9 != S1[1] )
          goto LABEL_32;
      }
      v5 = -2147024891;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_32;
      v14 = "CBR(std::find(vConnectedAdmins.begin(), vConnectedAdmins.end(), vCids.front()) != vConnectedAdmins.end())";
      v13 = -96;
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_32;
      v14 = "CHR(MdmEnumerateUsers(&vConnectedAdmins, nullptr, nullptr, 1))";
      v13 = -99;
    }
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)v7,
      (_DWORD)v6,
      v5,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccommandh"
                    "andlerdesktop.cpp",
      v13,
      (__int64)v14);
    goto LABEL_32;
  }
  v5 = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      a1,
      0,
      -2147024809,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccommandh"
                    "andlerdesktop.cpp",
      154,
      (__int64)"CBR(vCids.size() == 1)");
LABEL_32:
  std::vector<std::wstring>::~vector<std::wstring>(S1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180003210  push    rbx
0x180003212  push    rbp
0x180003213  push    rsi
0x180003214  push    rdi
0x180003215  sub     rsp, 58h
0x180003219  xorps   xmm0, xmm0
0x18000321c  movdqu  xmmword ptr [rsp+78h+S1], xmm0
0x180003222  mov     [rsp+78h+var_38], 0
0x18000322b  test    rdx, rdx
0x18000322e  jz      short loc_18000325F
0x180003230  mov     r8d, 80070057h
0x180003236  mov     ebx, r8d
0x180003239  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180003240  jz      loc_1800033D7
0x180003246  lea     rax, aCbrPwszpinNull; "CBR(pwszPin == nullptr)"
0x18000324d  mov     [rsp+78h+var_50], rax
0x180003252  mov     dword ptr [rsp+78h+var_58], 91h
0x18000325a  jmp     loc_1800033CA
0x18000325f  test    r8, r8
0x180003262  jz      short loc_180003293
0x180003264  mov     r8d, 80070057h
0x18000326a  mov     ebx, r8d
0x18000326d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180003274  jz      loc_1800033D7
0x18000327a  lea     rax, aCbrPwszcpnNull; "CBR(pwszCpn == nullptr)"
0x180003281  mov     [rsp+78h+var_50], rax
0x180003286  mov     dword ptr [rsp+78h+var_58], 94h
0x18000328e  jmp     loc_1800033CA
0x180003293  test    r9d, r9d
0x180003296  jz      short loc_1800032C7
0x180003298  mov     r8d, 80070057h
0x18000329e  mov     ebx, r8d
0x1800032a1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800032a8  jz      loc_1800033D7
0x1800032ae  lea     rax, aCbrFringafterl; "CBR(fRingAfterLock == 0)"
0x1800032b5  mov     [rsp+78h+var_50], rax
0x1800032ba  mov     dword ptr [rsp+78h+var_58], 97h
0x1800032c2  jmp     loc_1800033CA
0x1800032c7  mov     rsi, [rsp+78h+arg_20]
0x1800032cf  mov     rax, [rsi+8]
0x1800032d3  sub     rax, [rsi]
0x1800032d6  cmp     rax, 20h ; ' '
0x1800032da  jz      short loc_18000330B
0x1800032dc  mov     r8d, 80070057h
0x1800032e2  mov     ebx, r8d
0x1800032e5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800032ec  jz      loc_1800033D7
0x1800032f2  lea     rax, aCbrVcidsSize1; "CBR(vCids.size() == 1)"
0x1800032f9  mov     [rsp+78h+var_50], rax
0x1800032fe  mov     dword ptr [rsp+78h+var_58], 9Ah
0x180003306  jmp     loc_1800033CA
0x18000330b  mov     r9d, 1
0x180003311  xor     r8d, r8d
0x180003314  xor     edx, edx
0x180003316  lea     rcx, [rsp+78h+S1]
0x18000331b  call    cs:__imp_?MdmEnumerateUsers@@YAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00H@Z; MdmEnumerateUsers(std::vector<std::wstring> *,std::vector<std::wstring> *,std::vector<std::wstring> *,int)
0x180003321  mov     ebx, eax
0x180003323  test    eax, eax
0x180003325  jns     short loc_18000334A
0x180003327  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000332e  jz      loc_1800033D7
0x180003334  lea     rax, aChrMdmenumerat_1; "CHR(MdmEnumerateUsers(&vConnectedAdmins"...
0x18000333b  mov     [rsp+78h+var_50], rax
0x180003340  mov     dword ptr [rsp+78h+var_58], 9Dh
0x180003348  jmp     short loc_1800033C7
0x18000334a  mov     rbp, [rsp+78h+S1+8]
0x18000334f  mov     rdi, [rsp+78h+S1]
0x180003354  cmp     rdi, rbp
0x180003357  jz      short loc_1800033A5
0x180003359  mov     rsi, [rsi]
0x18000335c  cmp     qword ptr [rsi+18h], 7
0x180003361  jbe     short loc_180003368
0x180003363  mov     rdx, [rsi]
0x180003366  jmp     short loc_18000336B
0x180003368  mov     rdx, rsi; S2
0x18000336b  mov     r8, [rdi+10h]; N
0x18000336f  cmp     qword ptr [rdi+18h], 7
0x180003374  jbe     short loc_18000337B
0x180003376  mov     rcx, [rdi]
0x180003379  jmp     short loc_18000337E
0x18000337b  mov     rcx, rdi; S1
0x18000337e  cmp     r8, [rsi+10h]
0x180003382  jnz     short loc_180003392
0x180003384  test    r8, r8
0x180003387  jz      short loc_18000339B
0x180003389  call    wmemcmp
0x18000338e  test    eax, eax
0x180003390  jz      short loc_18000339B
0x180003392  add     rdi, 20h ; ' '
0x180003396  cmp     rdi, rbp
0x180003399  jnz     short loc_18000335C
0x18000339b  mov     rbp, [rsp+78h+S1+8]
0x1800033a0  cmp     rdi, rbp
0x1800033a3  jnz     short loc_1800033D7
0x1800033a5  mov     ebx, 80070005h
0x1800033aa  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800033b1  jz      short loc_1800033D7
0x1800033b3  lea     rax, aCbrStdFindVcon; "CBR(std::find(vConnectedAdmins.begin(),"...
0x1800033ba  mov     [rsp+78h+var_50], rax
0x1800033bf  mov     dword ptr [rsp+78h+var_58], 0A0h
0x1800033c7  mov     r8d, ebx
0x1800033ca  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800033d1  call    McTemplateU0dsqs_EventWriteTransfer
0x1800033d6  nop
0x1800033d7  lea     rcx, [rsp+78h+S1]
0x1800033dc  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x1800033e1  mov     eax, ebx
0x1800033e3  add     rsp, 58h
0x1800033e7  pop     rdi
0x1800033e8  pop     rsi
0x1800033e9  pop     rbp
0x1800033ea  pop     rbx
0x1800033eb  retn
```
