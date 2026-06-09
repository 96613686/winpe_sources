# DdcCommandHandlerDesktop::LockDevice(ushort const *,ushort const *,ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180002c50`
- end: `0x180002f08`
- name: `?LockDevice@DdcCommandHandlerDesktop@@UEAAJPEBG00AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `696`
- prototype: `__int64 __fastcall(wchar_t *, const wchar_t *, __int64, const unsigned __int16 *, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800026ac`
- `0x1800027e4`
- `0x180002c50`
- `0x180002f10`
- `0x1800033f4`
- `0x18000450c`
- `0x180004684`

## import_xrefs

- `MdmCommon!MdmEnumerateUsers` at `0x180002d15`
- `MdmCommon!MdmEnumerateUsers` at `0x180002d15`
- `MdmCommon!MdmGetSidsByConnectedCids` at `0x180002d52`
- `MdmCommon!MdmGetSidsByConnectedCids` at `0x180002d88`
- `MdmCommon!MdmGetSidsByConnectedCids` at `0x180002d52`
- `MdmCommon!MdmGetSidsByConnectedCids` at `0x180002d88`

## string_xrefs

- `0x180002cb8`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\ddccomimplementationsdesktop\ddccommandhandlerdesktop.cpp`
- `0x180002d6b`: `CHR(MdmGetSidsByConnectedCids(vConnectedAdminsCids, vConnectedAdminsSids))`
- `0x180002da1`: `CHR(MdmGetSidsByConnectedCids(vCids, vCallerSid))`
- `0x180002dde`: `CBR(vCallerSid.size() == 1)`
- `0x180002e62`: `CBR(std::find(vConnectedAdminsSids.begin(), vConnectedAdminsSids.end(), vCallerSid.front()) != vConnectedAdminsSids.end())`
- `0x180002ea0`: `CHR(LockDeviceCritical(vCallerSid.front().c_str(), vConnectedAdminsSids))`

## pseudocode

```c
__int64 __fastcall DdcCommandHandlerDesktop::LockDevice(
        wchar_t *a1,
        const wchar_t *a2,
        __int64 a3,
        const unsigned __int16 *a4,
        _QWORD *a5)
{
  int v6; // r8d
  int SidsByConnectedCids; // ebx
  wchar_t *v8; // rbx
  wchar_t *v9; // rsi
  wchar_t *v10; // rdi
  size_t v11; // r8
  wchar_t *v12; // rbx
  const unsigned __int16 *v13; // r8
  int v14; // r9d
  const unsigned __int16 *v15; // rdx
  HKEY v16; // rcx
  const unsigned __int16 *v17; // r8
  __int64 v18; // rax
  unsigned int v20; // [rsp+20h] [rbp-41h]
  char v21; // [rsp+20h] [rbp-41h]
  unsigned int v22; // [rsp+28h] [rbp-39h]
  const char *v23; // [rsp+28h] [rbp-39h]
  wchar_t *S1[2]; // [rsp+30h] [rbp-31h] BYREF
  __int64 v25; // [rsp+40h] [rbp-21h]
  wchar_t *S2[2]; // [rsp+48h] [rbp-19h] BYREF
  __int64 v27; // [rsp+58h] [rbp-9h]
  __int128 v28; // [rsp+60h] [rbp-1h] BYREF
  __int64 v29; // [rsp+70h] [rbp+Fh]

  *(_OWORD *)S2 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  *(_OWORD *)S1 = 0;
  v25 = 0;
  if ( a4 )
  {
    if ( a5[1] - *a5 != 32 )
    {
      SidsByConnectedCids = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)a1,
          (_DWORD)a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccomm"
                        "andhandlerdesktop.cpp",
          243,
          (__int64)"CBR(vCids.size() == 1)");
      goto LABEL_44;
    }
    SidsByConnectedCids = MdmEnumerateUsers(&v28, 0, 0, 1);
    if ( SidsByConnectedCids >= 0 )
    {
      SidsByConnectedCids = MdmGetSidsByConnectedCids(&v28, S1);
      if ( SidsByConnectedCids >= 0 )
      {
        SidsByConnectedCids = MdmGetSidsByConnectedCids(a5, S2);
        if ( SidsByConnectedCids >= 0 )
        {
          v8 = S2[0];
          if ( (wchar_t *)((char *)S2[1] - (char *)S2[0]) != (wchar_t *)32 )
          {
            SidsByConnectedCids = -2147418113;
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                (_DWORD)a1,
                (_DWORD)a2,
                -2147418113,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\d"
                              "dccommandhandlerdesktop.cpp",
                2,
                (__int64)"CBR(vCallerSid.size() == 1)");
            goto LABEL_44;
          }
          v9 = S1[1];
          v10 = S1[0];
          if ( S1[0] == S1[1] )
            goto LABEL_34;
          do
          {
            if ( *((_QWORD *)v8 + 3) <= 7u )
              a2 = v8;
            else
              a2 = *(const wchar_t **)v8;
            v11 = *((_QWORD *)v10 + 2);
            if ( *((_QWORD *)v10 + 3) <= 7u )
              a1 = v10;
            else
              a1 = *(wchar_t **)v10;
            if ( v11 == *((_QWORD *)v8 + 2) && (!v11 || !wmemcmp(a1, a2, v11)) )
              break;
            v10 += 16;
          }
          while ( v10 != v9 );
          v12 = S2[0];
          if ( v10 == S1[1] )
          {
LABEL_34:
            SidsByConnectedCids = -2147418113;
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                (_DWORD)a1,
                (_DWORD)a2,
                -2147418113,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\d"
                              "dccommandhandlerdesktop.cpp",
                3,
                (__int64)"CBR(std::find(vConnectedAdminsSids.begin(), vConnectedAdminsSids.end(), vCallerSid.front()) != "
                         "vConnectedAdminsSids.end())");
            goto LABEL_44;
          }
          if ( *((_QWORD *)S2[0] + 3) > 7u )
            v12 = *(wchar_t **)S2[0];
          SidsByConnectedCids = LockDeviceCritical(v12, S1);
          if ( SidsByConnectedCids >= 0 )
          {
            DdcRegistry::SetBOOLValue((HKEY)a1, a2, v13, v14, v20);
            v18 = -1;
            do
              ++v18;
            while ( a4[v18] );
            DdcRegistry::SetStringValue(v16, v15, v17, a4, v18, v22);
            goto LABEL_44;
          }
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_44;
          v23 = "CHR(LockDeviceCritical(vCallerSid.front().c_str(), vConnectedAdminsSids))";
          v21 = 6;
        }
        else
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_44;
          v23 = "CHR(MdmGetSidsByConnectedCids(vCids, vCallerSid))";
          v21 = -3;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_44;
        v23 = "CHR(MdmGetSidsByConnectedCids(vConnectedAdminsCids, vConnectedAdminsSids))";
        v21 = -6;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_44;
      v23 = "CHR(MdmEnumerateUsers(&vConnectedAdminsCids, nullptr, nullptr, 1))";
      v21 = -10;
    }
    v6 = SidsByConnectedCids;
    goto LABEL_4;
  }
  v6 = -2147024809;
  SidsByConnectedCids = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    v23 = "CPR(pwszMessage)";
    v21 = -14;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)a1,
      (_DWORD)a2,
      v6,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccommandh"
                    "andlerdesktop.cpp",
      v21,
      (__int64)v23);
  }
LABEL_44:
  std::vector<std::wstring>::~vector<std::wstring>(S1);
  std::vector<std::wstring>::~vector<std::wstring>(&v28);
  std::vector<std::wstring>::~vector<std::wstring>(S2);
  return (unsigned int)SidsByConnectedCids;
}

```

## disassembly

```asm
0x180002c50  push    rbp
0x180002c52  push    rbx
0x180002c53  push    rsi
0x180002c54  push    rdi
0x180002c55  push    r14
0x180002c57  push    r15
0x180002c59  lea     rbp, [rsp-27h]
0x180002c5e  sub     rsp, 88h
0x180002c65  mov     r14, r9
0x180002c68  xorps   xmm0, xmm0
0x180002c6b  movdqu  xmmword ptr [rbp+4Fh+S2], xmm0
0x180002c70  xor     r15d, r15d
0x180002c73  mov     [rbp+4Fh+var_58], r15
0x180002c77  movdqu  [rbp+4Fh+var_50], xmm0
0x180002c7c  mov     [rbp+4Fh+var_40], r15
0x180002c80  movdqu  xmmword ptr [rbp+4Fh+S1], xmm0
0x180002c85  mov     [rbp+4Fh+var_70], r15
0x180002c89  test    r9, r9
0x180002c8c  jnz     short loc_180002CC9
0x180002c8e  mov     r8d, 80070057h
0x180002c94  mov     ebx, r8d
0x180002c97  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002c9e  jz      loc_180002ED9
0x180002ca4  lea     rax, aCprPwszmessage; "CPR(pwszMessage)"
0x180002cab  mov     [rsp+0B0h+var_88], rax
0x180002cb0  mov     [rsp+0B0h+var_90], 0F2h
0x180002cb8  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180002cbf  call    McTemplateU0dsqs_EventWriteTransfer
0x180002cc4  jmp     loc_180002ED9
0x180002cc9  mov     rdi, [rbp+4Fh+arg_20]
0x180002ccd  mov     rax, [rdi+8]
0x180002cd1  sub     rax, [rdi]
0x180002cd4  cmp     rax, 20h ; ' '
0x180002cd8  jz      short loc_180002D06
0x180002cda  mov     r8d, 80070057h
0x180002ce0  mov     ebx, r8d
0x180002ce3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002cea  jz      loc_180002ED9
0x180002cf0  lea     rax, aCbrVcidsSize1; "CBR(vCids.size() == 1)"
0x180002cf7  mov     [rsp+0B0h+var_88], rax
0x180002cfc  mov     [rsp+0B0h+var_90], 0F3h
0x180002d04  jmp     short loc_180002CB8
0x180002d06  mov     r9d, 1
0x180002d0c  xor     r8d, r8d
0x180002d0f  xor     edx, edx
0x180002d11  lea     rcx, [rbp+4Fh+var_50]
0x180002d15  call    cs:__imp_?MdmEnumerateUsers@@YAJPEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@00H@Z; MdmEnumerateUsers(std::vector<std::wstring> *,std::vector<std::wstring> *,std::vector<std::wstring> *,int)
0x180002d1b  mov     ebx, eax
0x180002d1d  test    eax, eax
0x180002d1f  jns     short loc_180002D4A
0x180002d21  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002d28  jz      loc_180002ED9
0x180002d2e  lea     rax, aChrMdmenumerat_0; "CHR(MdmEnumerateUsers(&vConnectedAdmins"...
0x180002d35  mov     [rsp+0B0h+var_88], rax
0x180002d3a  mov     [rsp+0B0h+var_90], 0F6h
0x180002d42  mov     r8d, ebx
0x180002d45  jmp     loc_180002CB8
0x180002d4a  lea     rdx, [rbp+4Fh+S1]
0x180002d4e  lea     rcx, [rbp+4Fh+var_50]
0x180002d52  call    cs:__imp_?MdmGetSidsByConnectedCids@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0@Z; MdmGetSidsByConnectedCids(std::vector<std::wstring> &,std::vector<std::wstring> &)
0x180002d58  mov     ebx, eax
0x180002d5a  test    eax, eax
0x180002d5c  jns     short loc_180002D81
0x180002d5e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002d65  jz      loc_180002ED9
0x180002d6b  lea     rax, aChrMdmgetsidsb; "CHR(MdmGetSidsByConnectedCids(vConnecte"...
0x180002d72  mov     [rsp+0B0h+var_88], rax
0x180002d77  mov     [rsp+0B0h+var_90], 0FAh
0x180002d7f  jmp     short loc_180002D42
0x180002d81  lea     rdx, [rbp+4Fh+S2]
0x180002d85  mov     rcx, rdi
0x180002d88  call    cs:__imp_?MdmGetSidsByConnectedCids@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0@Z; MdmGetSidsByConnectedCids(std::vector<std::wstring> &,std::vector<std::wstring> &)
0x180002d8e  mov     ebx, eax
0x180002d90  test    eax, eax
0x180002d92  jns     short loc_180002DB7
0x180002d94  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002d9b  jz      loc_180002ED9
0x180002da1  lea     rax, aChrMdmgetsidsb_0; "CHR(MdmGetSidsByConnectedCids(vCids, vC"...
0x180002da8  mov     [rsp+0B0h+var_88], rax
0x180002dad  mov     [rsp+0B0h+var_90], 0FDh
0x180002db5  jmp     short loc_180002D42
0x180002db7  mov     rbx, [rbp+4Fh+S2]
0x180002dbb  mov     rax, [rbp+4Fh+S2+8]
0x180002dbf  sub     rax, rbx
0x180002dc2  cmp     rax, 20h ; ' '
0x180002dc6  jz      short loc_180002DF7
0x180002dc8  mov     r8d, 8000FFFFh
0x180002dce  mov     ebx, r8d
0x180002dd1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002dd8  jz      loc_180002ED9
0x180002dde  lea     rax, aCbrVcallersidS; "CBR(vCallerSid.size() == 1)"
0x180002de5  mov     [rsp+0B0h+var_88], rax
0x180002dea  mov     [rsp+0B0h+var_90], 102h
0x180002df2  jmp     loc_180002CB8
0x180002df7  mov     rsi, [rbp+4Fh+S1+8]
0x180002dfb  mov     rdi, [rbp+4Fh+S1]
0x180002dff  cmp     rdi, rsi
0x180002e02  jz      short loc_180002E50
0x180002e04  cmp     qword ptr [rbx+18h], 7
0x180002e09  jbe     short loc_180002E10
0x180002e0b  mov     rdx, [rbx]
0x180002e0e  jmp     short loc_180002E13
0x180002e10  mov     rdx, rbx; S2
0x180002e13  mov     r8, [rdi+10h]; N
0x180002e17  cmp     qword ptr [rdi+18h], 7
0x180002e1c  jbe     short loc_180002E23
0x180002e1e  mov     rcx, [rdi]
0x180002e21  jmp     short loc_180002E26
0x180002e23  mov     rcx, rdi; S1
0x180002e26  cmp     r8, [rbx+10h]
0x180002e2a  jnz     short loc_180002E3A
0x180002e2c  test    r8, r8
0x180002e2f  jz      short loc_180002E43
0x180002e31  call    wmemcmp
0x180002e36  test    eax, eax
0x180002e38  jz      short loc_180002E43
0x180002e3a  add     rdi, 20h ; ' '
0x180002e3e  cmp     rdi, rsi
0x180002e41  jnz     short loc_180002E04
0x180002e43  mov     rbx, [rbp+4Fh+S2]
0x180002e47  mov     rsi, [rbp+4Fh+S1+8]
0x180002e4b  cmp     rdi, rsi
0x180002e4e  jnz     short loc_180002E7B
0x180002e50  mov     r8d, 8000FFFFh
0x180002e56  mov     ebx, r8d
0x180002e59  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002e60  jz      short loc_180002ED9
0x180002e62  lea     rax, aCbrStdFindVcon_0; "CBR(std::find(vConnectedAdminsSids.begi"...
0x180002e69  mov     [rsp+0B0h+var_88], rax
0x180002e6e  mov     [rsp+0B0h+var_90], 103h
0x180002e76  jmp     loc_180002CB8
0x180002e7b  cmp     qword ptr [rbx+18h], 7
0x180002e80  jbe     short loc_180002E85
0x180002e82  mov     rbx, [rbx]
0x180002e85  lea     rdx, [rbp+4Fh+S1]
0x180002e89  mov     rcx, rbx
0x180002e8c  call    ?LockDeviceCritical@@YAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; LockDeviceCritical(ushort const *,std::vector<std::wstring> &)
0x180002e91  mov     ebx, eax
0x180002e93  test    eax, eax
0x180002e95  jns     short loc_180002EB9
0x180002e97  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180002e9e  jz      short loc_180002ED9
0x180002ea0  lea     rax, aChrLockdevicec; "CHR(LockDeviceCritical(vCallerSid.front"...
0x180002ea7  mov     [rsp+0B0h+var_88], rax
0x180002eac  mov     [rsp+0B0h+var_90], 106h
0x180002eb4  jmp     loc_180002D42
0x180002eb9  call    ?SetBOOLValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1HK@Z; DdcRegistry::SetBOOLValue(HKEY__ *,ushort const *,ushort const *,int,ulong)
0x180002ebe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002ec2  inc     rax
0x180002ec5  cmp     [r14+rax*2], r15w
0x180002eca  jnz     short loc_180002EC2
0x180002ecc  mov     [rsp+0B0h+var_90], eax; unsigned int
0x180002ed0  mov     r9, r14; unsigned __int16 *
0x180002ed3  call    ?SetStringValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG11KK@Z; DdcRegistry::SetStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180002ed8  nop
0x180002ed9  lea     rcx, [rbp+4Fh+S1]
0x180002edd  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180002ee2  nop
0x180002ee3  lea     rcx, [rbp+4Fh+var_50]
0x180002ee7  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180002eec  nop
0x180002eed  lea     rcx, [rbp+4Fh+S2]
0x180002ef1  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180002ef6  mov     eax, ebx
0x180002ef8  add     rsp, 88h
0x180002eff  pop     r15
0x180002f01  pop     r14
0x180002f03  pop     rdi
0x180002f04  pop     rsi
0x180002f05  pop     rbx
0x180002f06  pop     rbp
0x180002f07  retn
```
