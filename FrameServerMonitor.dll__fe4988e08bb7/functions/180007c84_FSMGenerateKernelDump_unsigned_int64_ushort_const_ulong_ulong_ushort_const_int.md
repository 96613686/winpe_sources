# FSMGenerateKernelDump(unsigned __int64,ushort const *,ulong,ulong,ushort const *,int *)

- ea: `0x180007c84`
- end: `0x180008048`
- name: `?FSMGenerateKernelDump@@YAJ_KPEBGKK1PEAH@Z`
- size: `964`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, unsigned int, unsigned int, LPCWSTR lpFileName, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800081a0`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180006a98`
- `0x180006ffc`
- `0x180007c84`
- `0x18000b388`
- `0x18000c684`
- `0x18000d208`
- `0x18000d3b0`
- `0x18000d3d8`
- `0x18000d418`
- `0x18000d498`
- `0x180025ea0`
- `0x1800265ac`

## import_xrefs

- `ntdll!NtSystemDebugControl` at `0x180007f4f`
- `ntdll!NtSystemDebugControl` at `0x180007f4f`
- `ntdll!RtlNtStatusToDosError` at `0x180007f66`
- `ntdll!RtlNtStatusToDosError` at `0x180007faf`
- `ntdll!RtlNtStatusToDosError` at `0x180007f66`
- `ntdll!RtlNtStatusToDosError` at `0x180007faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e80`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007e62`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007e62`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007f9a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007f9a`

## pseudocode

```c
__int64 __fastcall FSMGenerateKernelDump(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4,
        LPCWSTR lpFileName,
        int *a6)
{
  __int64 v6; // r14
  __int64 v7; // r12
  __int64 v8; // rcx
  signed int v9; // ebx
  __int64 v10; // rdx
  int GeneratedLiveKernelDumpTime; // eax
  int v12; // eax
  HANDLE v13; // rax
  signed int LastError; // eax
  unsigned int v15; // r14d
  int v16; // eax
  NTSTATUS v17; // ebx
  signed int v18; // eax
  signed int v19; // eax
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v23; // [rsp+50h] [rbp-B0h] BYREF
  void **v24; // [rsp+58h] [rbp-A8h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD InputBuffer[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v27; // [rsp+88h] [rbp-78h]
  const unsigned __int16 **v28; // [rsp+90h] [rbp-70h]
  __int64 v29; // [rsp+98h] [rbp-68h]
  __int64 v30; // [rsp+A0h] [rbp-60h]
  __int64 v31; // [rsp+A8h] [rbp-58h]
  int v32; // [rsp+B8h] [rbp-48h]
  __int128 *v33; // [rsp+C0h] [rbp-40h]
  __int128 v34; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v35; // [rsp+E0h] [rbp-20h]
  __int128 v36; // [rsp+F0h] [rbp-10h]

  v23 = a2;
  v6 = a3;
  v7 = a4;
  v22 = -1;
  memset_0(InputBuffer, 0, 0x48u);
  v24 = &AutoSecurityAttributes::`vftable';
  v21 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( lpFileName )
  {
    if ( a6 )
    {
      *a6 = 0;
      if ( (int)FSMCheckFreshNessGeneratedLiveKernelDumpTime(v8, &v21) >= 0 && v21 )
      {
        v9 = 0;
        if ( (unsigned __int8)byte_18005E5A5 >= 8u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 218, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids);
        *a6 = 1;
      }
      else
      {
        GeneratedLiveKernelDumpTime = FSMUpdateLastGeneratedLiveKernelDumpTime();
        if ( GeneratedLiveKernelDumpTime < 0 && byte_18005E5A5 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            219,
            &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
            (unsigned int)GeneratedLiveKernelDumpTime);
        if ( (unsigned __int8)byte_18005E5A5 >= 8u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 220, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids);
        v12 = AutoSecurityAttributes::Set(
                (AutoSecurityAttributes *)&v24,
                L"D:(A;;GASDWDWO;;;BA)(A;;GASDWDWO;;;SU)(A;;GASDWDWO;;;SY)");
        v9 = v12;
        if ( v12 >= 0 )
        {
          v13 = CreateFileW(lpFileName, 0x40040001u, 0, &SecurityAttributes, 2u, 0x80u, 0);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            &v22,
            v13);
          if ( v22 == -1 )
          {
            LastError = GetLastError();
            v9 = LastError;
            if ( LastError > 0 )
              v9 = (unsigned __int16)LastError | 0x80070000;
            if ( byte_18005E5A5 )
              WPP_SF_DS(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                222,
                (unsigned int)&WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
                v9,
                (__int64)lpFileName);
          }
          else
          {
            v32 |= 0x14u;
            v31 = v22;
            v29 = v6;
            v33 = &v34;
            InputBuffer[0] = 2;
            v15 = 0;
            InputBuffer[1] = 353;
            v27 = 0;
            v28 = &v23;
            v30 = v7;
            v35 = 0;
            *(_QWORD *)&v34 = 0x3000000001LL;
            v36 = 0;
            *((_QWORD *)&v34 + 1) = 1;
            do
            {
              v16 = NtSystemDebugControl(
                      SysDbgClearUmAttachPid|SysDbgQueryTraceInformation,
                      InputBuffer,
                      0x48u,
                      0,
                      0,
                      0);
              v17 = v16;
              if ( v16 >= 0 )
                break;
              if ( (unsigned __int8)byte_18005E5A5 >= 8u )
              {
                v18 = RtlNtStatusToDosError(v16);
                if ( v18 > 0 )
                  v18 = (unsigned __int16)v18 | 0x80070000;
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 27),
                  223,
                  &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
                  (unsigned int)v18);
              }
              DeleteFileW(lpFileName);
              v32 &= ~4u;
              ++v15;
            }
            while ( v15 < 2 );
            v19 = RtlNtStatusToDosError(v17);
            v9 = v19;
            if ( v19 > 0 )
              v9 = (unsigned __int16)v19 | 0x80070000;
            if ( v9 >= 0 )
            {
              if ( (unsigned __int8)byte_18005E5A5 >= 8u )
                WPP_SF_S(
                  *((_QWORD *)WPP_GLOBAL_Control + 27),
                  225,
                  &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
                  lpFileName);
            }
            else if ( g_wppLevels )
            {
              v10 = 224;
              goto LABEL_4;
            }
          }
        }
        else if ( g_wppLevels )
        {
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, 0, v12);
        }
      }
    }
    else
    {
      v9 = -2147467261;
      if ( g_wppLevels )
      {
        v10 = 217;
        goto LABEL_4;
      }
    }
  }
  else
  {
    v9 = -2147024809;
    if ( g_wppLevels )
    {
      v10 = 216;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, 0, v9);
    }
  }
  v24 = &AutoSecurityAttributes::`vftable';
  AutoSecurityAttributes::Reset((AutoSecurityAttributes *)&v24);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v22);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180007c84  mov     [rsp-8+arg_0], rbx
0x180007c89  push    rbp
0x180007c8a  push    rsi
0x180007c8b  push    r12
0x180007c8d  push    r14
0x180007c8f  push    r15
0x180007c91  lea     rbp, [rsp-10h]
0x180007c96  sub     rsp, 110h
0x180007c9d  mov     rax, cs:__security_cookie
0x180007ca4  xor     rax, rsp
0x180007ca7  mov     [rbp+30h+var_30], rax
0x180007cab  mov     r15, [rbp+30h+lpFileName]
0x180007caf  lea     rcx, [rbp+30h+InputBuffer]; void *
0x180007cb3  mov     rsi, [rbp+30h+arg_28]
0x180007cb7  mov     [rsp+130h+var_E0], rdx
0x180007cbc  xor     edx, edx; Val
0x180007cbe  mov     r14d, r8d
0x180007cc1  mov     r12d, r9d
0x180007cc4  mov     [rsp+130h+var_E8], 0FFFFFFFFFFFFFFFFh
0x180007ccd  lea     r8d, [rdx+48h]; Size
0x180007cd1  call    memset_0
0x180007cd6  xorps   xmm0, xmm0
0x180007cd9  lea     rax, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x180007ce0  mov     [rsp+130h+var_D8], rax
0x180007ce5  xor     eax, eax
0x180007ce7  mov     qword ptr [rsp+130h+SecurityAttributes.bInheritHandle], rax
0x180007cec  mov     [rsp+130h+var_F0], eax
0x180007cf0  movups  [rbp+30h+var_60], xmm0
0x180007cf4  movups  [rbp+30h+var_50], xmm0
0x180007cf8  movups  [rbp+30h+var_40], xmm0
0x180007cfc  movups  xmmword ptr [rsp+130h+SecurityAttributes.nLength], xmm0
0x180007d01  test    r15, r15
0x180007d04  jnz     short loc_180007D40
0x180007d06  mov     ebx, 80070057h
0x180007d0b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007d12  jb      loc_180008002
0x180007d18  mov     edx, 0D8h
0x180007d1d  mov     [rsp+130h+dwCreationDisposition], ebx
0x180007d21  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d28  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007d2f  xor     r9d, r9d
0x180007d32  mov     rcx, [rcx+10h]
0x180007d36  call    WPP_SF_qD
0x180007d3b  jmp     loc_180008002
0x180007d40  test    rsi, rsi
0x180007d43  jnz     short loc_180007D5E
0x180007d45  mov     ebx, 80004003h
0x180007d4a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007d51  jb      loc_180008002
0x180007d57  mov     edx, 0D9h
0x180007d5c  jmp     short loc_180007D1D
0x180007d5e  lea     rdx, [rsp+130h+var_F0]
0x180007d63  mov     [rsi], eax
0x180007d65  call    ?FSMCheckFreshNessGeneratedLiveKernelDumpTime@@YAJW4_FSM_REGPATHLOOKUPKEY@@AEAH@Z; FSMCheckFreshNessGeneratedLiveKernelDumpTime(_FSM_REGPATHLOOKUPKEY,int &)
0x180007d6a  test    eax, eax
0x180007d6c  js      short loc_180007DAA
0x180007d6e  cmp     [rsp+130h+var_F0], 0
0x180007d73  jz      short loc_180007DAA
0x180007d75  xor     ebx, ebx
0x180007d77  cmp     cs:byte_18005E5A5, 8
0x180007d7e  jb      short loc_180007D9F
0x180007d80  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d87  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007d8e  mov     edx, 0DAh
0x180007d93  mov     rcx, [rcx+0D8h]
0x180007d9a  call    WPP_SF_
0x180007d9f  mov     dword ptr [rsi], 1
0x180007da5  jmp     loc_180008002
0x180007daa  call    ?FSMUpdateLastGeneratedLiveKernelDumpTime@@YAJW4_FSM_REGPATHLOOKUPKEY@@@Z; FSMUpdateLastGeneratedLiveKernelDumpTime(_FSM_REGPATHLOOKUPKEY)
0x180007daf  test    eax, eax
0x180007db1  jns     short loc_180007DDE
0x180007db3  cmp     cs:byte_18005E5A5, 1
0x180007dba  jb      short loc_180007DDE
0x180007dbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dc3  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007dca  mov     edx, 0DBh
0x180007dcf  mov     r9d, eax
0x180007dd2  mov     rcx, [rcx+0D8h]
0x180007dd9  call    WPP_SF_d
0x180007dde  cmp     cs:byte_18005E5A5, 8
0x180007de5  jb      short loc_180007E06
0x180007de7  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dee  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007df5  mov     edx, 0DCh
0x180007dfa  mov     rcx, [rcx+0D8h]
0x180007e01  call    WPP_SF_
0x180007e06  lea     rdx, StringSecurityDescriptor; "D:(A;;GASDWDWO;;;BA)(A;;GASDWDWO;;;SU)("...
0x180007e0d  lea     rcx, [rsp+130h+var_D8]; this
0x180007e12  call    ?Set@AutoSecurityAttributes@@QEAAJPEBG@Z; AutoSecurityAttributes::Set(ushort const *)
0x180007e17  mov     ebx, eax
0x180007e19  test    eax, eax
0x180007e1b  jns     short loc_180007E38
0x180007e1d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007e24  jb      loc_180008002
0x180007e2a  mov     edx, 0DDh
0x180007e2f  mov     [rsp+130h+dwCreationDisposition], eax
0x180007e33  jmp     loc_180007D21
0x180007e38  mov     [rsp+130h+hTemplateFile], 0; hTemplateFile
0x180007e41  lea     r9, [rsp+130h+SecurityAttributes]; lpSecurityAttributes
0x180007e46  mov     ebx, 2
0x180007e4b  mov     [rsp+130h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180007e53  xor     r8d, r8d; dwShareMode
0x180007e56  mov     [rsp+130h+dwCreationDisposition], ebx; dwCreationDisposition
0x180007e5a  mov     edx, 40040001h; dwDesiredAccess
0x180007e5f  mov     rcx, r15; lpFileName
0x180007e62  call    cs:__imp_CreateFileW
0x180007e68  mov     rdx, rax
0x180007e6b  lea     rcx, [rsp+130h+var_E8]
0x180007e70  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180007e75  mov     rax, [rsp+130h+var_E8]
0x180007e7a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007e7e  jnz     short loc_180007ECE
0x180007e80  call    cs:__imp_GetLastError
0x180007e86  mov     ebx, eax
0x180007e88  test    eax, eax
0x180007e8a  jle     short loc_180007E95
0x180007e8c  movzx   ebx, ax
0x180007e8f  or      ebx, 80070000h
0x180007e95  cmp     cs:byte_18005E5A5, 1
0x180007e9c  jb      loc_180008002
0x180007ea2  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ea9  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007eb0  mov     edx, 0DEh
0x180007eb5  mov     qword ptr [rsp+130h+dwCreationDisposition], r15
0x180007eba  mov     r9d, ebx
0x180007ebd  mov     rcx, [rcx+0D8h]
0x180007ec4  call    WPP_SF_DS
0x180007ec9  jmp     loc_180008002
0x180007ece  or      [rbp+30h+var_78], 14h
0x180007ed2  lea     rcx, [rsp+130h+var_E0]
0x180007ed7  mov     [rbp+30h+var_88], rax
0x180007edb  xorps   xmm0, xmm0
0x180007ede  lea     rax, [rbp+30h+var_60]
0x180007ee2  mov     [rbp+30h+var_98], r14
0x180007ee6  xorps   xmm1, xmm1
0x180007ee9  mov     [rbp+30h+var_70], rax
0x180007eed  mov     [rbp+30h+InputBuffer], ebx
0x180007ef0  xor     r14d, r14d
0x180007ef3  mov     [rbp+30h+var_AC], 161h
0x180007efa  mov     esi, 80070000h
0x180007eff  mov     [rbp+30h+var_A8], 0
0x180007f07  mov     [rbp+30h+var_A0], rcx
0x180007f0b  mov     [rbp+30h+var_90], r12
0x180007f0f  movdqu  [rbp+30h+var_50], xmm0
0x180007f14  mov     dword ptr [rbp+30h+var_60], 1
0x180007f1b  movdqu  [rbp+30h+var_40], xmm1
0x180007f20  mov     dword ptr [rbp+30h+var_60+4], 30h ; '0'
0x180007f27  mov     qword ptr [rbp+30h+var_60+8], 1
0x180007f2f  xor     r9d, r9d; OutputBuffer
0x180007f32  mov     qword ptr [rsp+130h+dwFlagsAndAttributes], 0; ReturnLength
0x180007f3b  lea     rdx, [rbp+30h+InputBuffer]; InputBuffer
0x180007f3f  mov     [rsp+130h+dwCreationDisposition], 0; OutputBufferLength
0x180007f47  lea     r8d, [r9+48h]; InputBufferLength
0x180007f4b  lea     ecx, [r9+25h]; ControlCode
0x180007f4f  call    cs:__imp_NtSystemDebugControl
0x180007f55  mov     ebx, eax
0x180007f57  test    eax, eax
0x180007f59  jns     short loc_180007FAD
0x180007f5b  cmp     cs:byte_18005E5A5, 8
0x180007f62  jb      short loc_180007F97
0x180007f64  mov     ecx, eax; Status
0x180007f66  call    cs:__imp_RtlNtStatusToDosError
0x180007f6c  test    eax, eax
0x180007f6e  jle     short loc_180007F75
0x180007f70  movzx   eax, ax
0x180007f73  or      eax, esi
0x180007f75  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f7c  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007f83  mov     edx, 0DFh
0x180007f88  mov     r9d, eax
0x180007f8b  mov     rcx, [rcx+0D8h]
0x180007f92  call    WPP_SF_d
0x180007f97  mov     rcx, r15; lpFileName
0x180007f9a  call    cs:__imp_DeleteFileW
0x180007fa0  and     [rbp+30h+var_78], 0FFFFFFFBh
0x180007fa4  inc     r14d
0x180007fa7  cmp     r14d, 2
0x180007fab  jb      short loc_180007F2F
0x180007fad  mov     ecx, ebx; Status
0x180007faf  call    cs:__imp_RtlNtStatusToDosError
0x180007fb5  mov     ebx, eax
0x180007fb7  test    eax, eax
0x180007fb9  jle     short loc_180007FC0
0x180007fbb  movzx   ebx, ax
0x180007fbe  or      ebx, esi
0x180007fc0  test    ebx, ebx
0x180007fc2  jns     short loc_180007FD7
0x180007fc4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007fcb  jb      short loc_180008002
0x180007fcd  mov     edx, 0E0h
0x180007fd2  jmp     loc_180007D1D
0x180007fd7  cmp     cs:byte_18005E5A5, 8
0x180007fde  jb      short loc_180008002
0x180007fe0  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fe7  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180007fee  mov     edx, 0E1h
0x180007ff3  mov     r9, r15
0x180007ff6  mov     rcx, [rcx+0D8h]
0x180007ffd  call    WPP_SF_S
0x180008002  lea     rax, ??_7AutoSecurityAttributes@@6B@; const AutoSecurityAttributes::`vftable'
0x180008009  lea     rcx, [rsp+130h+var_D8]; this
0x18000800e  mov     [rsp+130h+var_D8], rax
0x180008013  call    ?Reset@AutoSecurityAttributes@@QEAAXXZ; AutoSecurityAttributes::Reset(void)
0x180008018  lea     rcx, [rsp+130h+var_E8]
0x18000801d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180008022  mov     eax, ebx
0x180008024  mov     rcx, [rbp+30h+var_30]
0x180008028  xor     rcx, rsp; StackCookie
0x18000802b  call    __security_check_cookie
0x180008030  mov     rbx, [rsp+130h+arg_0]
0x180008038  add     rsp, 110h
0x18000803f  pop     r15
0x180008041  pop     r14
0x180008043  pop     r12
0x180008045  pop     rsi
0x180008046  pop     rbp
0x180008047  retn
```
