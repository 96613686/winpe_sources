# Bus_CreatePdo

- ea: `0x14002a548`
- end: `0x14002abbd`
- name: `Bus_CreatePdo`
- size: `1653`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400296f8`

## callees

- `0x140005af8`
- `0x14001adc0`
- `0x14001ae00`
- `0x14001b2c0`
- `0x14002a548`
- `0x14002add0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002a6c7`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002a6c7`

## pseudocode

```c
__int64 __fastcall Bus_CreatePdo(__int64 a1)
{
  __int64 v2; // rdx
  NTSTATUS v3; // ebx
  char v4; // bl
  _DWORD *v5; // rbx
  __int64 result; // rax
  __int64 v7; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v8; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING v9; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v10[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v12; // [rsp+70h] [rbp-90h] BYREF
  __int128 v13; // [rsp+80h] [rbp-80h]
  __int128 v14; // [rsp+90h] [rbp-70h]
  __int128 v15; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v16; // [rsp+B0h] [rbp-50h]
  __int128 v17; // [rsp+C0h] [rbp-40h]
  __int64 *v18; // [rsp+D0h] [rbp-30h]
  _QWORD v19[8]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v20[20]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v21; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v22; // [rsp+1D0h] [rbp+D0h]
  __int128 v23; // [rsp+1E0h] [rbp+E0h]
  _QWORD v24[10]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v25; // [rsp+240h] [rbp+140h] BYREF
  int v26; // [rsp+250h] [rbp+150h]
  char v27; // [rsp+260h] [rbp+160h] BYREF

  v7 = 0;
  v8 = 0;
  v18 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  memset(v19, 0, sizeof(v19));
  v21 = 0;
  v22 = 0;
  v23 = 0;
  memset(v24, 0, sizeof(v24));
  memset(v20, 0, 0x98u);
  v26 = *(_DWORD *)L"0";
  v10[1] = &v25;
  v9.Buffer = (PWSTR)&v27;
  v25 = *(_OWORD *)L"HFP Bus 0";
  v10[0] = 1310738;
  *(_QWORD *)&v9.Length = 10485760;
  DestinationString = 0;
  v7 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 1680))(WdfDriverGlobals, a1);
  v2 = v7;
  if ( v7 )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 528))(WdfDriverGlobals, v7, 42);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 3136))(WdfDriverGlobals, v7);
    RtlInitUnicodeString(&DestinationString, L"BTHHFENUM\\BthHFPAudio");
    v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015 + 1696))(
           WdfDriverGlobals,
           v7,
           &DestinationString);
    if ( v3 >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015 + 1712))(
             WdfDriverGlobals,
             v7,
             &DestinationString);
      if ( v3 >= 0 )
      {
        v3 = RtlUnicodeStringPrintf(&v9, L"%02d", 97);
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *))(WdfFunctions_01015
                                                                                                 + 1704))(
                 WdfDriverGlobals,
                 v7,
                 &v9);
          if ( v3 >= 0 )
          {
            v3 = RtlUnicodeStringPrintf(&v9, L"Microsoft_HFP_Audio_Device_%02d", 97);
            if ( v3 >= 0 )
            {
              v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, struct _UNICODE_STRING *, _QWORD *, int))(WdfFunctions_01015 + 1728))(
                     WdfDriverGlobals,
                     v7,
                     &v9,
                     v10,
                     2048);
              if ( v3 >= 0 )
              {
                (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 1736))(
                  WdfDriverGlobals,
                  v7,
                  2048);
                memset(v19, 0, sizeof(v19));
                v19[2] = Bus_EvtDeviceResourceRequirementsQuery;
                LODWORD(v19[0]) = 64;
                (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01015 + 1688))(
                  WdfDriverGlobals,
                  v7,
                  v19);
                v18 = off_1400220D8;
                *(_QWORD *)&v16 = 0;
                *((_QWORD *)&v16 + 1) = 0x100000001LL;
                v15 = 0;
                LODWORD(v15) = 56;
                v17 = 0;
                v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *, __int128 *, __int64 *))(WdfFunctions_01015 + 600))(
                       WdfDriverGlobals,
                       &v7,
                       &v15,
                       &v8);
                if ( v3 >= 0 )
                {
                  v4 = *(_BYTE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 248))(
                                    WdfDriverGlobals,
                                    a1)
                                + 76)
                     + 1;
                  *(_BYTE *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 248))(
                               WdfDriverGlobals,
                               v8)
                           + 76) = v4;
                  v5 = (_DWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                                   WdfDriverGlobals,
                                   v8,
                                   off_1400220D8);
                  memset(v5 + 2, 0, 0x68u);
                  *v5 = 97;
                  v5[1] = 1;
                  *((_QWORD *)v5 + 1) = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015
                                                                                                + 336))(
                                          WdfDriverGlobals,
                                          a1);
                  v3 = Bus_SetupAudioPDOQueues(v8);
                  if ( v3 >= 0 )
                  {
                    LODWORD(v21) = 48;
                    *(_QWORD *)((char *)&v21 + 4) = 2;
                    *(_QWORD *)&v22 = 0x200000002LL;
                    *((_QWORD *)&v22 + 1) = 0x100000002LL;
                    *(_QWORD *)&v23 = 0x200000002LL;
                    HIDWORD(v21) = 0;
                    *((_QWORD *)&v23 + 1) = 0x6100000061LL;
                    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 664))(
                      WdfDriverGlobals,
                      v8,
                      &v21);
                    v24[8] = -1;
                    v24[9] = 0x5FFFFFFFFLL;
                    LODWORD(v24[3]) = 2;
                    HIDWORD(v24[3]) = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
                    v24[0] = 0x100000050LL;
                    v24[1] = 0x200000002LL;
                    v24[2] = 0x200000001LL;
                    v24[7] = 0x700000002LL;
                    v24[4] = 0x200000001LL;
                    *(__m128i *)&v24[5] = _mm_load_si128((const __m128i *)&_xmm);
                    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01015 + 672))(
                      WdfDriverGlobals,
                      v8,
                      v24);
                    memset(v20, 0, 0x98u);
                    v20[2] = guard_check_icall_nop;
                    LODWORD(v20[0]) = 65688;
                    v20[3] = guard_check_icall_nop;
                    *((_QWORD *)&v12 + 1) = v20;
                    v20[1] = v8;
                    *((_QWORD *)&v13 + 1) = 0;
                    *(_QWORD *)&v13 = &GUID_HFP_INTERFACE_STANDARD;
                    *(_QWORD *)&v14 = BusPdo_EvtDeviceProcessQueryInterfaceRequest;
                    *(_QWORD *)&v12 = 48;
                    *((_QWORD *)&v14 + 1) = 1;
                    v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *))(WdfFunctions_01015 + 1824))(
                           WdfDriverGlobals,
                           v8,
                           &v12);
                    if ( v3 >= 0 )
                    {
                      result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015
                                                                                                + 1064))(
                                 WdfDriverGlobals,
                                 a1,
                                 v8);
                      v3 = result;
                      if ( (int)result >= 0 )
                        return result;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    v2 = v7;
  }
  else
  {
    v3 = -1073741670;
  }
  if ( v2 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 432))(WdfDriverGlobals);
  if ( v8 )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 1664))(WdfDriverGlobals);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14002a548  push    rbp
0x14002a54a  push    rbx
0x14002a54b  push    rdi
0x14002a54c  push    r12
0x14002a54e  push    r13
0x14002a550  push    r15
0x14002a552  lea     rbp, [rsp-218h]
0x14002a55a  sub     rsp, 318h
0x14002a561  mov     rax, cs:__security_cookie
0x14002a568  xor     rax, rsp
0x14002a56b  mov     [rbp+240h+var_40], rax
0x14002a572  xorps   xmm0, xmm0
0x14002a575  mov     [rsp+340h+var_310], 0
0x14002a57e  xorps   xmm1, xmm1
0x14002a581  mov     [rsp+340h+var_308], 0
0x14002a58a  xor     eax, eax
0x14002a58c  mov     rdi, rcx
0x14002a58f  xor     edx, edx; Val
0x14002a591  mov     [rbp+240h+var_270], rax
0x14002a595  lea     rcx, [rbp+240h+var_260]; void *
0x14002a599  movups  [rsp+340h+var_2D0], xmm0
0x14002a59e  lea     r12d, [rax+40h]
0x14002a5a2  mov     r8d, r12d; Size
0x14002a5a5  movups  [rbp+240h+var_2C0], xmm0
0x14002a5a9  movups  [rbp+240h+var_2B0], xmm0
0x14002a5ad  movups  [rbp+240h+var_2A0], xmm1
0x14002a5b1  movups  [rbp+240h+var_290], xmm1
0x14002a5b5  movups  [rbp+240h+var_280], xmm1
0x14002a5b9  call    memset
0x14002a5be  xorps   xmm0, xmm0
0x14002a5c1  lea     r8d, [r12+10h]; Size
0x14002a5c6  xor     edx, edx; Val
0x14002a5c8  lea     rcx, [rbp+240h+var_150]; void *
0x14002a5cf  movups  [rbp+240h+var_180], xmm0
0x14002a5d6  movups  [rbp+240h+var_170], xmm0
0x14002a5dd  movups  [rbp+240h+var_160], xmm0
0x14002a5e4  call    memset
0x14002a5e9  lea     r13d, [r12+58h]
0x14002a5ee  xor     edx, edx; Val
0x14002a5f0  mov     r8d, r13d; Size
0x14002a5f3  lea     rcx, [rbp+240h+var_220]; void *
0x14002a5f7  call    memset
0x14002a5fc  mov     eax, dword ptr cs:aHfpBus0+10h; "0"
0x14002a602  mov     rdx, rdi
0x14002a605  movups  xmm0, xmmword ptr cs:aHfpBus0; "HFP Bus 0"
0x14002a60c  mov     rcx, cs:WdfDriverGlobals
0x14002a613  mov     [rbp+240h+var_F0], eax
0x14002a619  lea     rax, [rbp+240h+var_100]
0x14002a620  mov     [rsp+340h+var_2E8], rax
0x14002a625  lea     rax, [rbp+240h+var_E0]
0x14002a62c  mov     [rsp+340h+var_300.Buffer], rax
0x14002a631  mov     rax, cs:WdfFunctions_01015
0x14002a638  movups  [rbp+240h+var_100], xmm0
0x14002a63f  mov     [rsp+340h+var_2F0], 140012h
0x14002a648  xorps   xmm0, xmm0
0x14002a64b  mov     qword ptr [rsp+340h+var_300.Length], 0A00000h
0x14002a654  movups  xmmword ptr [rsp+340h+DestinationString.Length], xmm0
0x14002a659  mov     rax, [rax+690h]
0x14002a660  call    _guard_dispatch_icall
0x14002a665  mov     [rsp+340h+var_310], rax
0x14002a66a  mov     rdx, rax
0x14002a66d  test    rax, rax
0x14002a670  jnz     short loc_14002A67C
0x14002a672  mov     ebx, 0C000009Ah
0x14002a677  jmp     loc_14002AB57
0x14002a67c  mov     rax, cs:WdfFunctions_01015
0x14002a683  mov     r8d, 2Ah ; '*'
0x14002a689  mov     rcx, cs:WdfDriverGlobals
0x14002a690  mov     rax, [rax+210h]
0x14002a697  call    _guard_dispatch_icall
0x14002a69c  mov     rax, cs:WdfFunctions_01015
0x14002a6a3  mov     rdx, [rsp+340h+var_310]
0x14002a6a8  mov     rcx, cs:WdfDriverGlobals
0x14002a6af  mov     rax, [rax+0C40h]
0x14002a6b6  call    _guard_dispatch_icall
0x14002a6bb  lea     rdx, aBthhfenumBthhf; "BTHHFENUM\\BthHFPAudio"
0x14002a6c2  lea     rcx, [rsp+340h+DestinationString]; DestinationString
0x14002a6c7  call    cs:__imp_RtlInitUnicodeString
0x14002a6ce  nop     dword ptr [rax+rax+00h]
0x14002a6d3  mov     rax, cs:WdfFunctions_01015
0x14002a6da  lea     r8, [rsp+340h+DestinationString]
0x14002a6df  mov     rdx, [rsp+340h+var_310]
0x14002a6e4  mov     rcx, cs:WdfDriverGlobals
0x14002a6eb  mov     rax, [rax+6A0h]
0x14002a6f2  call    _guard_dispatch_icall
0x14002a6f7  mov     ebx, eax
0x14002a6f9  test    eax, eax
0x14002a6fb  js      loc_14002AB52
0x14002a701  mov     rax, cs:WdfFunctions_01015
0x14002a708  lea     r8, [rsp+340h+DestinationString]
0x14002a70d  mov     rdx, [rsp+340h+var_310]
0x14002a712  mov     rcx, cs:WdfDriverGlobals
0x14002a719  mov     rax, [rax+6B0h]
0x14002a720  call    _guard_dispatch_icall
0x14002a725  mov     ebx, eax
0x14002a727  test    eax, eax
0x14002a729  js      loc_14002AB52
0x14002a72f  mov     r15d, 61h ; 'a'
0x14002a735  lea     rdx, a02d; "%02d"
0x14002a73c  mov     r8d, r15d
0x14002a73f  lea     rcx, [rsp+340h+var_300]; DestinationString
0x14002a744  call    RtlUnicodeStringPrintf
0x14002a749  mov     ebx, eax
0x14002a74b  test    eax, eax
0x14002a74d  js      loc_14002AB52
0x14002a753  mov     rax, cs:WdfFunctions_01015
0x14002a75a  lea     r8, [rsp+340h+var_300]
0x14002a75f  mov     rdx, [rsp+340h+var_310]
0x14002a764  mov     rcx, cs:WdfDriverGlobals
0x14002a76b  mov     rax, [rax+6A8h]
0x14002a772  call    _guard_dispatch_icall
0x14002a777  mov     ebx, eax
0x14002a779  test    eax, eax
0x14002a77b  js      loc_14002AB52
0x14002a781  mov     r8d, r15d
0x14002a784  lea     rdx, aMicrosoftHfpAu; "Microsoft_HFP_Audio_Device_%02d"
0x14002a78b  lea     rcx, [rsp+340h+var_300]; DestinationString
0x14002a790  call    RtlUnicodeStringPrintf
0x14002a795  mov     ebx, eax
0x14002a797  test    eax, eax
0x14002a799  js      loc_14002AB52
0x14002a79f  mov     rax, cs:WdfFunctions_01015
0x14002a7a6  lea     r9, [rsp+340h+var_2F0]
0x14002a7ab  mov     rdx, [rsp+340h+var_310]
0x14002a7b0  lea     r8, [rsp+340h+var_300]
0x14002a7b5  mov     rcx, cs:WdfDriverGlobals
0x14002a7bc  mov     [rsp+340h+var_320], 800h
0x14002a7c4  mov     rax, [rax+6C0h]
0x14002a7cb  call    _guard_dispatch_icall
0x14002a7d0  mov     ebx, eax
0x14002a7d2  test    eax, eax
0x14002a7d4  js      loc_14002AB52
0x14002a7da  mov     rax, cs:WdfFunctions_01015
0x14002a7e1  mov     r8d, 800h
0x14002a7e7  mov     rdx, [rsp+340h+var_310]
0x14002a7ec  mov     rcx, cs:WdfDriverGlobals
0x14002a7f3  mov     rax, [rax+6C8h]
0x14002a7fa  call    _guard_dispatch_icall
0x14002a7ff  mov     r8, r12; Size
0x14002a802  lea     rcx, [rbp+240h+var_260]; void *
0x14002a806  xor     edx, edx; Val
0x14002a808  call    memset
0x14002a80d  mov     rdx, [rsp+340h+var_310]
0x14002a812  lea     rax, Bus_EvtDeviceResourceRequirementsQuery
0x14002a819  mov     rcx, cs:WdfDriverGlobals
0x14002a820  lea     r8, [rbp+240h+var_260]
0x14002a824  mov     [rbp+240h+var_250], rax
0x14002a828  mov     rax, cs:WdfFunctions_01015
0x14002a82f  mov     [rbp+240h+var_260], r12d
0x14002a833  mov     rax, [rax+698h]
0x14002a83a  call    _guard_dispatch_icall
0x14002a83f  mov     rax, cs:off_1400220D8
0x14002a846  lea     r12d, [r15-60h]
0x14002a84a  mov     rcx, cs:WdfDriverGlobals
0x14002a851  lea     r9, [rsp+340h+var_308]
0x14002a856  xorps   xmm0, xmm0
0x14002a859  mov     [rbp+240h+var_270], rax
0x14002a85d  mov     rax, cs:WdfFunctions_01015
0x14002a864  lea     r8, [rbp+240h+var_2A0]
0x14002a868  movups  [rbp+240h+var_290], xmm0
0x14002a86c  mov     dword ptr [rbp+240h+var_290+8], r12d
0x14002a870  lea     rdx, [rsp+340h+var_310]
0x14002a875  movups  [rbp+240h+var_2A0], xmm0
0x14002a879  mov     dword ptr [rbp+240h+var_2A0], 38h ; '8'
0x14002a880  movups  [rbp+240h+var_280], xmm0
0x14002a884  mov     dword ptr [rbp+240h+var_290+0Ch], r12d
0x14002a888  mov     rax, [rax+258h]
0x14002a88f  call    _guard_dispatch_icall
0x14002a894  mov     ebx, eax
0x14002a896  test    eax, eax
0x14002a898  js      loc_14002AB52
0x14002a89e  mov     rax, cs:WdfFunctions_01015
0x14002a8a5  mov     rdx, rdi
0x14002a8a8  mov     rcx, cs:WdfDriverGlobals
0x14002a8af  mov     rax, [rax+0F8h]
0x14002a8b6  call    _guard_dispatch_icall
0x14002a8bb  mov     rdx, [rsp+340h+var_308]
0x14002a8c0  mov     rcx, cs:WdfDriverGlobals
0x14002a8c7  mov     bl, [rax+4Ch]
0x14002a8ca  mov     rax, cs:WdfFunctions_01015
0x14002a8d1  add     bl, r12b
0x14002a8d4  mov     rax, [rax+0F8h]
0x14002a8db  call    _guard_dispatch_icall
0x14002a8e0  mov     [rax+4Ch], bl
0x14002a8e3  mov     rax, cs:WdfFunctions_01015
0x14002a8ea  mov     r8, cs:off_1400220D8
0x14002a8f1  mov     rdx, [rsp+340h+var_308]
0x14002a8f6  mov     rcx, cs:WdfDriverGlobals
0x14002a8fd  mov     rax, [rax+650h]
0x14002a904  call    _guard_dispatch_icall
0x14002a909  xor     edx, edx; Val
0x14002a90b  lea     r8d, [r15+7]; Size
0x14002a90f  mov     rbx, rax
0x14002a912  lea     rcx, [rax+8]; void *
0x14002a916  call    memset
0x14002a91b  mov     [rbx], r15d
0x14002a91e  mov     rdx, rdi
0x14002a921  mov     [rbx+4], r12d
0x14002a925  mov     rcx, cs:WdfFunctions_01015
0x14002a92c  mov     rax, [rcx+150h]
0x14002a933  mov     rcx, cs:WdfDriverGlobals
0x14002a93a  call    _guard_dispatch_icall
0x14002a93f  mov     [rbx+8], rax
0x14002a943  mov     rcx, [rsp+340h+var_308]
0x14002a948  call    Bus_SetupAudioPDOQueues
0x14002a94d  mov     ebx, eax
0x14002a94f  test    eax, eax
0x14002a951  js      loc_14002AB52
0x14002a957  mov     rax, cs:WdfFunctions_01015
0x14002a95e  lea     ebx, [r15-5Fh]
0x14002a962  mov     rdx, [rsp+340h+var_308]
0x14002a967  lea     r8, [rbp+240h+var_180]
0x14002a96e  mov     rcx, cs:WdfDriverGlobals
0x14002a975  mov     dword ptr [rbp+240h+var_180], 30h ; '0'
0x14002a97f  mov     qword ptr [rbp+240h+var_180+4], rbx
0x14002a986  mov     dword ptr [rbp+240h+var_170], ebx
0x14002a98c  mov     dword ptr [rbp+240h+var_170+4], ebx
0x14002a992  mov     dword ptr [rbp+240h+var_170+8], ebx
0x14002a998  mov     dword ptr [rbp+240h+var_160], ebx
0x14002a99e  mov     dword ptr [rbp+240h+var_160+4], ebx
0x14002a9a4  mov     dword ptr [rbp+240h+var_180+0Ch], 0
0x14002a9ae  mov     dword ptr [rbp+240h+var_170+0Ch], r12d
0x14002a9b5  mov     dword ptr [rbp+240h+var_160+8], r15d
0x14002a9bc  mov     dword ptr [rbp+240h+var_160+0Ch], r15d
0x14002a9c3  mov     rax, [rax+298h]
0x14002a9ca  call    _guard_dispatch_icall
0x14002a9cf  movdqa  xmm0, cs:__xmm@00000005000000050000000500000005
0x14002a9d7  lea     r8, [rbp+240h+var_150]
0x14002a9de  mov     rdx, [rsp+340h+var_308]
0x14002a9e3  or      eax, 0FFFFFFFFh
0x14002a9e6  mov     rcx, cs:WdfDriverGlobals
0x14002a9ed  mov     qword ptr [rbp+240h+var_128], 0
0x14002a9f8  mov     [rbp+240h+var_110], eax
0x14002a9fe  mov     [rbp+240h+var_10C], eax
0x14002aa04  mov     [rbp+240h+var_108], eax
0x14002aa0a  mov     rax, cs:WdfFunctions_01015
0x14002aa11  mov     qword ptr [rbp+240h+var_138], rbx
0x14002aa18  movups  [rbp+240h+var_138+4], xmm0
0x14002aa1f  mov     qword ptr [rbp+240h+var_128+8], 0
0x14002aa2a  movdqa  xmm0, cs:__xmm@00000004000000040000000400000004
0x14002aa32  mov     [rbp+240h+var_150], 50h ; 'P'
0x14002aa3c  mov     [rbp+240h+var_148], ebx
0x14002aa42  mov     [rbp+240h+var_144], ebx
0x14002aa48  mov     [rbp+240h+var_13C], ebx
0x14002aa4e  mov     [rbp+240h+var_114], 7
0x14002aa58  mov     [rbp+240h+var_104], 5
0x14002aa62  mov     [rbp+240h+var_14C], r12d
0x14002aa69  mov     [rbp+240h+var_140], r12d
0x14002aa70  mov     [rbp+240h+var_118], ebx
0x14002aa76  mov     dword ptr [rbp+240h+var_138+8], r12d
0x14002aa7d  mov     dword ptr [rbp+240h+var_138+0Ch], ebx
0x14002aa83  movups  [rbp+240h+var_128], xmm0
0x14002aa8a  mov     rax, [rax+2A0h]
0x14002aa91  call    _guard_dispatch_icall
0x14002aa96  mov     r8, r13; Size
0x14002aa99  lea     rcx, [rbp+240h+var_220]; void *
0x14002aa9d  xor     edx, edx; Val
0x14002aa9f  call    memset
0x14002aaa4  mov     rdx, [rsp+340h+var_308]
0x14002aaa9  lea     rax, _guard_check_icall_nop
0x14002aab0  mov     rcx, cs:WdfDriverGlobals
0x14002aab7  lea     r8, [rsp+340h+var_2D0]
0x14002aabc  mov     [rbp+240h+var_210], rax
0x14002aac0  xorps   xmm0, xmm0
0x14002aac3  movups  [rsp+340h+var_2D0], xmm0
0x14002aac8  lea     rax, _guard_check_icall_nop
0x14002aacf  mov     [rbp+240h+var_220], 10098h
0x14002aad6  mov     [rbp+240h+var_208], rax
0x14002aada  lea     rax, [rbp+240h+var_220]
0x14002aade  mov     qword ptr [rsp+340h+var_2D0+8], rax
0x14002aae3  lea     rax, GUID_HFP_INTERFACE_STANDARD
0x14002aaea  movups  [rbp+240h+var_2B0], xmm0
0x14002aaee  mov     [rbp+240h+var_218], rdx
0x14002aaf2  movups  [rbp+240h+var_2C0], xmm0
0x14002aaf6  mov     qword ptr [rbp+240h+var_2C0], rax
0x14002aafa  lea     rax, BusPdo_EvtDeviceProcessQueryInterfaceRequest
0x14002ab01  mov     qword ptr [rbp+240h+var_2B0], rax
0x14002ab05  mov     rax, cs:WdfFunctions_01015
0x14002ab0c  mov     dword ptr [rsp+340h+var_2D0], 30h ; '0'
0x14002ab14  mov     byte ptr [rbp+240h+var_2B0+8], r12b
0x14002ab18  mov     rax, [rax+720h]
0x14002ab1f  call    _guard_dispatch_icall
0x14002ab24  mov     ebx, eax
0x14002ab26  test    eax, eax
0x14002ab28  js      short loc_14002AB52
0x14002ab2a  mov     rax, cs:WdfFunctions_01015
0x14002ab31  mov     rdx, rdi
0x14002ab34  mov     r8, [rsp+340h+var_308]
0x14002ab39  mov     rcx, cs:WdfDriverGlobals
0x14002ab40  mov     rax, [rax+428h]
0x14002ab47  call    _guard_dispatch_icall
0x14002ab4c  mov     ebx, eax
0x14002ab4e  test    eax, eax
0x14002ab50  jns     short loc_14002AB9C
0x14002ab52  mov     rdx, [rsp+340h+var_310]
0x14002ab57  test    rdx, rdx
0x14002ab5a  jz      short loc_14002AB76
0x14002ab5c  mov     rax, cs:WdfFunctions_01015
0x14002ab63  mov     rcx, cs:WdfDriverGlobals
0x14002ab6a  mov     rax, [rax+1B0h]
  ... truncated ...
```
