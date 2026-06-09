# Interrupter_PrepareInterrupter

- ea: `0x14007d110`
- end: `0x14007d5c4`
- name: `Interrupter_PrepareInterrupter`
- size: `1204`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x14007cbe0`

## callees

- `0x1400054dc`
- `0x140006074`
- `0x14001ac48`
- `0x14001bb78`
- `0x14001d02c`
- `0x14001d118`
- `0x1400290e0`
- `0x14002cb28`
- `0x140040704`
- `0x140057db0`
- `0x140059970`
- `0x1400599b0`
- `0x14007c58c`
- `0x14007d110`

## import_xrefs

- `ntoskrnl!IoAllocateWorkItem` at `0x14007d48b`
- `ntoskrnl!IoAllocateWorkItem` at `0x14007d48b`
- `ntoskrnl!KeInitializeEvent` at `0x14007d4aa`
- `ntoskrnl!KeInitializeEvent` at `0x14007d4aa`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14007d530`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14007d530`

## string_xrefs

- `0x14007d30d`: `Common buffer allocation failure for large buffer (only asserting at the smallest allocation size failure)`

## pseudocode

```c
__int64 __fastcall Interrupter_PrepareInterrupter(__int64 a1, __int64 a2, unsigned __int8 a3)
{
  _QWORD *v3; // rdi
  __int64 v4; // r15
  __int64 v5; // rsi
  int v7; // ecx
  unsigned int v8; // esi
  int v9; // r12d
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // r15
  int v13; // r11d
  __int64 v14; // rax
  unsigned int v15; // edx
  int v16; // r9d
  unsigned int v17; // r13d
  _QWORD *v18; // rsi
  unsigned int v19; // r13d
  unsigned int v20; // edx
  _QWORD *v21; // rax
  _QWORD *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // r9
  __int64 v25; // rcx
  _DWORD *v26; // rdx
  __int64 v27; // r8
  _QWORD *v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rcx
  struct _DEVICE_OBJECT *v31; // rax
  __int64 v32; // r9
  int v33; // eax
  int v34; // edx
  signed __int32 v36[8]; // [rsp+0h] [rbp-79h] BYREF
  unsigned int v37; // [rsp+40h] [rbp-39h]
  __int64 v38; // [rsp+48h] [rbp-31h]
  __int64 v39; // [rsp+50h] [rbp-29h]
  __int128 v40; // [rsp+58h] [rbp-21h] BYREF
  __int128 v41; // [rsp+68h] [rbp-11h]
  char pszDest[16]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v43; // [rsp+88h] [rbp+Fh]

  v3 = (_QWORD *)(a2 + 176);
  v38 = a1;
  *(_QWORD *)(a2 + 184) = a2 + 176;
  *(_QWORD *)(a2 + 176) = a2 + 176;
  v4 = *(_QWORD *)(a2 + 8);
  v5 = a1;
  v40 = 0;
  v43 = 0;
  v41 = 0;
  *(_OWORD *)pszDest = 0;
  v7 = *(_DWORD *)(v4 + 1052);
  if ( v7 )
  {
    if ( (unsigned int)(v7 - 1) >= 2 )
    {
      Debug_FreAssertMsg("Unexpected DMA Mode", 0, "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\interrupter.c", 816);
      return (unsigned int)-1073741630;
    }
    v9 = 3;
  }
  else
  {
    v10 = *(_DWORD *)(v5 + 64);
    if ( !v10 || !*(_QWORD *)(v5 + 80) || (v9 = 4, *(_DWORD *)(a2 + 32) != v10) )
      v9 = 1;
  }
  v11 = *(_QWORD *)(v4 + 88);
  v12 = *(_QWORD *)(v4 + 120);
  v39 = v11;
  *(_DWORD *)(a2 + 112) ^= (*(_DWORD *)(a2 + 112) ^ a3) & 1;
  Interrupter_DetermineSegmentSizeAndCount(a2);
  v14 = XilCommonBuffer_AcquireBufferEx(v12, 16 * *(_DWORD *)(a2 + 124), a2, 829713993, v13);
  *(_QWORD *)(a2 + 168) = v14;
  if ( !v14 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = 28;
      goto LABEL_29;
    }
    goto LABEL_30;
  }
  v17 = 0;
  while ( 1 )
  {
    v37 = v17;
    if ( v17 >= *(_DWORD *)(a2 + 124) )
    {
      v24 = v39;
      v25 = *(_QWORD *)(v39 + 40) + 32 * (*(unsigned int *)(a2 + 32) + 1LL);
      *(_QWORD *)(a2 + 24) = v25;
      v26 = (_DWORD *)(v25 + 8);
      if ( *(_BYTE *)(v24 + 137) )
      {
        *v26 = 0;
        _InterlockedOr(v36, 0);
      }
      else
      {
        XilRegister_WriteUlong(v24, v26, 0);
      }
      v27 = 0;
      v28 = (_QWORD *)*v3;
      v29 = *(_QWORD *)(*(_QWORD *)(a2 + 168) + 16LL);
      while ( v3 != v28 )
      {
        v30 = 2LL * (unsigned int)v27;
        v27 = (unsigned int)(v27 + 1);
        *(_QWORD *)(v29 + 8 * v30) = v28[3];
        *(_WORD *)(v29 + 8 * v30 + 8) = *(_WORD *)(a2 + 132);
        v28 = (_QWORD *)*v28;
      }
      if ( WPP_MAIN_CB.Queue.Wcb.DeviceObject )
      {
        v31 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64))(WdfFunctions_01033 + 248))(
                                         WdfDriverGlobals,
                                         **(_QWORD **)(a2 + 8),
                                         v27,
                                         v29);
        *(_QWORD *)(a2 + 216) = IoAllocateWorkItem(v31);
        KeInitializeEvent((PRKEVENT)(a2 + 192), NotificationEvent, 1u);
      }
      else
      {
        *(_QWORD *)(a2 + 216) = 0;
      }
      v32 = *(_QWORD *)(a2 + 8);
      v33 = *(_DWORD *)(a2 + 32);
      *(_QWORD *)&v40 = 56;
      pszDest[0] = 0;
      HIDWORD(v41) = 16;
      *(_QWORD *)&v41 = 0;
      BYTE8(v41) = 0;
      v43 = 0x200000002LL;
      *((_QWORD *)&v40 + 1) = 0xC800000400LL;
      RtlStringCchPrintfA(pszDest, 0x10u, "%02d INT%02d", *(_DWORD *)(v32 + 176), v33);
      if ( (int)imp_WppRecorderLogCreate(WPP_GLOBAL_Control, &v40, a2 + 16) < 0 )
        *(_QWORD *)(a2 + 16) = *(_QWORD *)(*(_QWORD *)(a2 + 8) + 72LL);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v34) = 4;
        WPP_RECORDER_SF_qDD(
          *(_QWORD *)(*(_QWORD *)(a2 + 8) + 72LL),
          v34,
          9,
          31,
          (__int64)WPP_443b39bb81083aedb7bb6af0320847b8_Traceguids,
          *(_QWORD *)(a2 + 24),
          *(_DWORD *)(a2 + 120),
          *(_DWORD *)(a2 + 124));
      }
      *(_DWORD *)(a2 + 116) = 1;
      return 0;
    }
    if ( v9 == 4 )
    {
      v18 = (_QWORD *)XilCommonBuffer_AcquireBufferFromPhysicalAddress(
                        v12,
                        *(_QWORD *)(v5 + 80),
                        *(_DWORD *)(a2 + 120),
                        a2,
                        829713993);
    }
    else
    {
      v18 = (_QWORD *)XilCommonBuffer_AcquireBufferEx(v12, *(_DWORD *)(a2 + 120), a2, 829713993, v9);
      if ( v18 )
        goto LABEL_25;
      do
      {
        v19 = *(_DWORD *)(a2 + 120);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v15) = 2;
          WPP_RECORDER_SF_D(
            *(_QWORD *)(*(_QWORD *)(a2 + 8) + 72LL),
            v15,
            9,
            29,
            (__int64)WPP_443b39bb81083aedb7bb6af0320847b8_Traceguids,
            *(_DWORD *)(a2 + 120));
        }
        v15 = *(_DWORD *)(a2 + 120);
        if ( v15 <= 0x1000 )
          break;
        v20 = v15 >> 1;
        *(_DWORD *)(a2 + 120) = v20;
        v18 = (_QWORD *)XilCommonBuffer_AcquireBufferEx(v12, v20, a2, 829713993, v9);
      }
      while ( !v18 );
      v3 = (_QWORD *)(a2 + 176);
      if ( v19 )
        MicrosoftTelemetryAssertTriggeredArgsMsgKM(
          "usbxhci.sys",
          829713993,
          v19,
          "Common buffer allocation failure for large buffer (only asserting at the smallest allocation size failure)");
      v17 = v37;
    }
    if ( !v18 )
      break;
LABEL_25:
    v21 = (_QWORD *)v3[1];
    if ( (_QWORD *)*v21 != v3 )
LABEL_37:
      __fastfail(3u);
    *v18 = v3;
    ++v17;
    v18[1] = v21;
    *v21 = v18;
    v3[1] = v18;
    v5 = v38;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_30;
  v16 = 30;
LABEL_29:
  LOBYTE(v15) = 2;
  WPP_RECORDER_SF_(
    *(_QWORD *)(*(_QWORD *)(a2 + 8) + 72LL),
    v15,
    9,
    v16,
    (__int64)WPP_443b39bb81083aedb7bb6af0320847b8_Traceguids);
LABEL_30:
  v8 = -1073741670;
  if ( v12 )
  {
    if ( *(_QWORD *)(a2 + 168) )
    {
      XilCommonBuffer_ReleaseBuffer(v12);
      *(_QWORD *)(a2 + 168) = 0;
    }
    while ( 1 )
    {
      v22 = (_QWORD *)*v3;
      if ( (_QWORD *)*v3 == v3 )
        break;
      if ( (_QWORD *)v22[1] != v3 )
        goto LABEL_37;
      v23 = *v22;
      if ( *(_QWORD **)(*v22 + 8LL) != v22 )
        goto LABEL_37;
      *v3 = v23;
      *(_QWORD *)(v23 + 8) = v3;
      XilCommonBuffer_ReleaseBuffer(v12);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x14007d110  mov     [rsp-8+arg_10], rbx
0x14007d115  push    rbp
0x14007d116  push    rsi
0x14007d117  push    rdi
0x14007d118  push    r12
0x14007d11a  push    r13
0x14007d11c  push    r14
0x14007d11e  push    r15
0x14007d120  lea     rbp, [rsp-27h]
0x14007d125  sub     rsp, 0A0h
0x14007d12c  mov     rax, cs:__security_cookie
0x14007d133  xor     rax, rsp
0x14007d136  mov     [rbp+57h+var_40], rax
0x14007d13a  lea     rdi, [rdx+0B0h]
0x14007d141  mov     [rbp+57h+var_88], rcx
0x14007d145  xorps   xmm0, xmm0
0x14007d148  mov     [rdi+8], rdi
0x14007d14c  xor     eax, eax
0x14007d14e  mov     [rdi], rdi
0x14007d151  mov     r15, [rdx+8]
0x14007d155  mov     rsi, rcx
0x14007d158  movups  [rbp+57h+var_78], xmm0
0x14007d15c  mov     [rbp+57h+var_48], rax
0x14007d160  mov     rbx, rdx
0x14007d163  movups  [rbp+57h+var_68], xmm0
0x14007d167  lea     edx, [rax+1]
0x14007d16a  movups  xmmword ptr [rbp+57h+pszDest], xmm0
0x14007d16e  mov     ecx, [r15+41Ch]
0x14007d175  test    ecx, ecx
0x14007d177  jz      short loc_14007D1B1
0x14007d179  sub     ecx, edx
0x14007d17b  jz      short loc_14007D1A6
0x14007d17d  cmp     ecx, edx
0x14007d17f  jz      short loc_14007D1A6
0x14007d181  mov     r9d, 330h
0x14007d187  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14007d18e  xor     edx, edx
0x14007d190  lea     rcx, aUnexpectedDmaM_0; "Unexpected DMA Mode"
0x14007d197  call    Debug_FreAssertMsg
0x14007d19c  mov     esi, 0C00000C2h
0x14007d1a1  jmp     loc_14007D59A
0x14007d1a6  mov     r11d, 3
0x14007d1ac  mov     r12d, r11d
0x14007d1af  jmp     short loc_14007D1D0
0x14007d1b1  mov     eax, [rsi+40h]
0x14007d1b4  test    eax, eax
0x14007d1b6  jz      short loc_14007D1CA
0x14007d1b8  cmp     qword ptr [rsi+50h], 0
0x14007d1bd  jz      short loc_14007D1CA
0x14007d1bf  mov     r12d, 4
0x14007d1c5  cmp     [rbx+20h], eax
0x14007d1c8  jz      short loc_14007D1CD
0x14007d1ca  mov     r12d, edx
0x14007d1cd  mov     r11d, edx
0x14007d1d0  mov     rax, [r15+58h]
0x14007d1d4  mov     r15, [r15+78h]
0x14007d1d8  movzx   ecx, r8b
0x14007d1dc  mov     [rbp+57h+var_80], rax
0x14007d1e0  mov     eax, [rbx+70h]
0x14007d1e3  xor     ecx, eax
0x14007d1e5  and     ecx, edx
0x14007d1e7  xor     ecx, eax
0x14007d1e9  mov     [rbx+70h], ecx
0x14007d1ec  mov     rcx, rbx
0x14007d1ef  call    Interrupter_DetermineSegmentSizeAndCount
0x14007d1f4  mov     edx, [rbx+7Ch]
0x14007d1f7  mov     r9d, 31746E49h
0x14007d1fd  shl     edx, 4
0x14007d200  mov     r8, rbx
0x14007d203  mov     rcx, r15
0x14007d206  mov     dword ptr [rsp+0D0h+var_B0], r11d
0x14007d20b  call    XilCommonBuffer_AcquireBufferEx
0x14007d210  mov     [rbx+0A8h], rax
0x14007d217  test    rax, rax
0x14007d21a  jnz     short loc_14007D239
0x14007d21c  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007d223  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14007d22a  jz      loc_14007D388
0x14007d230  lea     r9d, [rax+1Ch]
0x14007d234  jmp     loc_14007D367
0x14007d239  xor     r13d, r13d
0x14007d23c  lea     r14, WPP_RECORDER_INITIALIZED
0x14007d243  mov     [rbp+57h+var_90], r13d
0x14007d247  cmp     r13d, [rbx+7Ch]
0x14007d24b  jnb     loc_14007D3E8
0x14007d251  mov     rcx, r15
0x14007d254  cmp     r12d, 4
0x14007d258  jnz     short loc_14007D27A
0x14007d25a  mov     rdx, [rsi+50h]
0x14007d25e  mov     r9, rbx
0x14007d261  mov     r8d, [rbx+78h]
0x14007d265  mov     dword ptr [rsp+0D0h+var_B0], 31746E49h
0x14007d26d  call    XilCommonBuffer_AcquireBufferFromPhysicalAddress
0x14007d272  mov     rsi, rax
0x14007d275  jmp     loc_14007D32C
0x14007d27a  mov     edx, [rbx+78h]
0x14007d27d  mov     r9d, 31746E49h
0x14007d283  mov     r8, rbx
0x14007d286  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x14007d28b  call    XilCommonBuffer_AcquireBufferEx
0x14007d290  mov     rsi, rax
0x14007d293  test    rax, rax
0x14007d296  jnz     loc_14007D331
0x14007d29c  lea     rdi, WPP_443b39bb81083aedb7bb6af0320847b8_Traceguids
0x14007d2a3  mov     r13d, [rbx+78h]
0x14007d2a7  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d2ae  jz      short loc_14007D2D3
0x14007d2b0  mov     rcx, [rbx+8]
0x14007d2b4  mov     r9d, 1Dh
0x14007d2ba  mov     dword ptr [rsp+0D0h+var_A8], r13d
0x14007d2bf  mov     dl, 2
0x14007d2c1  mov     [rsp+0D0h+var_B0], rdi
0x14007d2c6  mov     rcx, [rcx+48h]
0x14007d2ca  lea     r8d, [r9-14h]
0x14007d2ce  call    WPP_RECORDER_SF_D
0x14007d2d3  mov     edx, [rbx+78h]
0x14007d2d6  cmp     edx, 1000h
0x14007d2dc  jbe     short loc_14007D301
0x14007d2de  shr     edx, 1
0x14007d2e0  mov     r9d, 31746E49h
0x14007d2e6  mov     r8, rbx
0x14007d2e9  mov     [rbx+78h], edx
0x14007d2ec  mov     rcx, r15
0x14007d2ef  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x14007d2f4  call    XilCommonBuffer_AcquireBufferEx
0x14007d2f9  mov     rsi, rax
0x14007d2fc  test    rax, rax
0x14007d2ff  jz      short loc_14007D2A3
0x14007d301  lea     rdi, [rbx+0B0h]
0x14007d308  test    r13d, r13d
0x14007d30b  jz      short loc_14007D328
0x14007d30d  lea     r9, aCommonBufferAl_0; __annotation("Debug", "TelemetryAssert", "FALSE", "Common buffer allocation failure for large buffer (only asserting at the smallest allocation size failure)")
0x14007d314  mov     r8d, r13d
0x14007d317  mov     edx, 31746E49h
0x14007d31c  lea     rcx, aUsbxhciSys; "usbxhci.sys"
0x14007d323  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x14007d328  mov     r13d, [rbp+57h+var_90]
0x14007d32c  test    rsi, rsi
0x14007d32f  jz      short loc_14007D358
0x14007d331  mov     rax, [rdi+8]
0x14007d335  cmp     [rax], rdi
0x14007d338  jnz     loc_14007D3E1
0x14007d33e  mov     [rsi], rdi
0x14007d341  inc     r13d
0x14007d344  mov     [rsi+8], rax
0x14007d348  mov     [rax], rsi
0x14007d34b  mov     [rdi+8], rsi
0x14007d34f  mov     rsi, [rbp+57h+var_88]
0x14007d353  jmp     loc_14007D243
0x14007d358  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d35f  jz      short loc_14007D388
0x14007d361  mov     r9d, 1Eh
0x14007d367  mov     rcx, [rbx+8]
0x14007d36b  lea     rax, WPP_443b39bb81083aedb7bb6af0320847b8_Traceguids
0x14007d372  mov     r8d, 9
0x14007d378  mov     [rsp+0D0h+var_B0], rax
0x14007d37d  mov     dl, 2
0x14007d37f  mov     rcx, [rcx+48h]
0x14007d383  call    WPP_RECORDER_SF_
0x14007d388  mov     esi, 0C000009Ah
0x14007d38d  test    r15, r15
0x14007d390  jz      loc_14007D59A
0x14007d396  mov     rdx, [rbx+0A8h]
0x14007d39d  test    rdx, rdx
0x14007d3a0  jz      short loc_14007D3B5
0x14007d3a2  mov     rcx, r15
0x14007d3a5  call    XilCommonBuffer_ReleaseBuffer
0x14007d3aa  mov     qword ptr [rbx+0A8h], 0
0x14007d3b5  mov     rdx, [rdi]
0x14007d3b8  cmp     rdx, rdi
0x14007d3bb  jz      loc_14007D59A
0x14007d3c1  cmp     [rdx+8], rdi
0x14007d3c5  jnz     short loc_14007D3E1
0x14007d3c7  mov     rax, [rdx]
0x14007d3ca  cmp     [rax+8], rdx
0x14007d3ce  jnz     short loc_14007D3E1
0x14007d3d0  mov     [rdi], rax
0x14007d3d3  mov     rcx, r15
0x14007d3d6  mov     [rax+8], rdi
0x14007d3da  call    XilCommonBuffer_ReleaseBuffer
0x14007d3df  jmp     short loc_14007D3B5
0x14007d3e1  mov     ecx, 3
0x14007d3e6  int     29h; Win8: RtlFailFast(ecx)
0x14007d3e8  mov     r9, [rbp+57h+var_80]
0x14007d3ec  mov     ecx, [rbx+20h]
0x14007d3ef  inc     rcx
0x14007d3f2  shl     rcx, 5
0x14007d3f6  add     rcx, [r9+28h]
0x14007d3fa  mov     [rbx+18h], rcx
0x14007d3fe  cmp     byte ptr [r9+89h], 0
0x14007d406  lea     rdx, [rcx+8]
0x14007d40a  jz      short loc_14007D419
0x14007d40c  mov     dword ptr [rdx], 0
0x14007d412  lock or [rsp+0D0h+var_D0], 0
0x14007d417  jmp     short loc_14007D424
0x14007d419  xor     r8d, r8d
0x14007d41c  mov     rcx, r9
0x14007d41f  call    XilRegister_WriteUlong
0x14007d424  mov     rax, [rbx+0A8h]
0x14007d42b  xor     r8d, r8d
0x14007d42e  mov     rdx, [rdi]
0x14007d431  mov     r9, [rax+10h]
0x14007d435  jmp     short loc_14007D458
0x14007d437  mov     rax, [rdx+18h]
0x14007d43b  mov     ecx, r8d
0x14007d43e  add     rcx, rcx
0x14007d441  inc     r8d
0x14007d444  mov     [r9+rcx*8], rax
0x14007d448  movzx   eax, word ptr [rbx+84h]
0x14007d44f  mov     [r9+rcx*8+8], ax
0x14007d455  mov     rdx, [rdx]
0x14007d458  cmp     rdi, rdx
0x14007d45b  jnz     short loc_14007D437
0x14007d45d  cmp     qword ptr cs:WPP_MAIN_CB.Queue+30h, 0
0x14007d465  jz      short loc_14007D4B8
0x14007d467  mov     rdx, [rbx+8]
0x14007d46b  mov     rax, cs:WdfFunctions_01033
0x14007d472  mov     rcx, cs:WdfDriverGlobals
0x14007d479  mov     rdx, [rdx]
0x14007d47c  mov     rax, [rax+0F8h]
0x14007d483  call    _guard_dispatch_icall
0x14007d488  mov     rcx, rax; DeviceObject
0x14007d48b  call    cs:__imp_IoAllocateWorkItem
0x14007d492  nop     dword ptr [rax+rax+00h]
0x14007d497  lea     rcx, [rbx+0C0h]; Event
0x14007d49e  mov     r8b, 1; State
0x14007d4a1  xor     edx, edx; Type
0x14007d4a3  mov     [rbx+0D8h], rax
0x14007d4aa  call    cs:__imp_KeInitializeEvent
0x14007d4b1  nop     dword ptr [rax+rax+00h]
0x14007d4b6  jmp     short loc_14007D4C3
0x14007d4b8  mov     qword ptr [rbx+0D8h], 0
0x14007d4c3  mov     r9, [rbx+8]
0x14007d4c7  lea     r8, a02dInt02d; "%02d INT%02d"
0x14007d4ce  mov     eax, [rbx+20h]
0x14007d4d1  lea     rcx, [rbp+57h+pszDest]; pszDest
0x14007d4d5  mov     edx, 10h; cchDest
0x14007d4da  mov     qword ptr [rbp+57h+var_78], 38h ; '8'
0x14007d4e2  mov     [rbp+57h+pszDest], 0
0x14007d4e6  mov     dword ptr [rbp+57h+var_68+0Ch], edx
0x14007d4e9  mov     qword ptr [rbp+57h+var_68], 0
0x14007d4f1  mov     byte ptr [rbp+57h+var_68+8], 0
0x14007d4f5  mov     dword ptr [rbp+57h+var_48], 2
0x14007d4fc  mov     dword ptr [rbp+57h+var_48+4], 2
0x14007d503  mov     dword ptr [rbp+57h+var_78+8], 400h
0x14007d50a  mov     dword ptr [rbp+57h+var_78+0Ch], 0C8h
0x14007d511  mov     r9d, [r9+0B0h]
0x14007d518  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14007d51c  call    RtlStringCchPrintfA
0x14007d521  mov     rcx, cs:WPP_GLOBAL_Control
0x14007d528  lea     r8, [rbx+10h]
0x14007d52c  lea     rdx, [rbp+57h+var_78]
0x14007d530  call    cs:__imp_imp_WppRecorderLogCreate
0x14007d537  nop     dword ptr [rax+rax+00h]
0x14007d53c  test    eax, eax
0x14007d53e  jns     short loc_14007D54C
0x14007d540  mov     rax, [rbx+8]
0x14007d544  mov     rcx, [rax+48h]
0x14007d548  mov     [rbx+10h], rcx
0x14007d54c  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x14007d553  jz      short loc_14007D591
0x14007d555  mov     eax, [rbx+7Ch]
0x14007d558  mov     r9d, 1Fh
0x14007d55e  mov     rcx, [rbx+8]
0x14007d562  mov     dl, 4
0x14007d564  mov     [rsp+0D0h+var_98], eax
0x14007d568  mov     eax, [rbx+78h]
0x14007d56b  mov     [rsp+0D0h+var_A0], eax
0x14007d56f  lea     r8d, [r9-16h]
0x14007d573  mov     rax, [rbx+18h]
0x14007d577  mov     rcx, [rcx+48h]
0x14007d57b  mov     [rsp+0D0h+var_A8], rax
0x14007d580  lea     rax, WPP_443b39bb81083aedb7bb6af0320847b8_Traceguids
0x14007d587  mov     [rsp+0D0h+var_B0], rax
0x14007d58c  call    WPP_RECORDER_SF_qDD
0x14007d591  mov     dword ptr [rbx+74h], 1
0x14007d598  xor     esi, esi
0x14007d59a  mov     eax, esi
0x14007d59c  mov     rcx, [rbp+57h+var_40]
0x14007d5a0  xor     rcx, rsp; StackCookie
0x14007d5a3  call    __security_check_cookie
0x14007d5a8  mov     rbx, [rsp+0D0h+arg_10]
0x14007d5b0  add     rsp, 0A0h
0x14007d5b7  pop     r15
0x14007d5b9  pop     r14
0x14007d5bb  pop     r13
0x14007d5bd  pop     r12
0x14007d5bf  pop     rdi
0x14007d5c0  pop     rsi
0x14007d5c1  pop     rbp
0x14007d5c2  retn
```
