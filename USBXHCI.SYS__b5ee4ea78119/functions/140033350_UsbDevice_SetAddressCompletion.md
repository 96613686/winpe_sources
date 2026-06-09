# UsbDevice_SetAddressCompletion

- ea: `0x140033350`
- end: `0x140033734`
- name: `UsbDevice_SetAddressCompletion`
- size: `996`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x14000c264`
- `0x1400216b8`
- `0x14002499c`
- `0x140024f24`
- `0x1400296ac`
- `0x14002b2c0`
- `0x140033350`
- `0x14003373c`
- `0x1400392d4`
- `0x14004fe34`
- `0x140059970`
- `0x1400599b0`
- `0x140059d80`

## string_xrefs

- `0x14003368a`: `Set Address Command with BSR=1 failed`

## pseudocode

```c
__int64 __fastcall UsbDevice_SetAddressCompletion(__int64 a1, int a2, __int64 a3, int a4)
{
  __int64 v4; // rsi
  __int16 v7; // ax
  __int64 v8; // rdi
  __int64 v9; // r10
  __int64 v10; // rcx
  int v11; // r8d
  __int64 v12; // r8
  __int64 v13; // rdx
  int v15; // edx
  int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 v19; // rdi
  int v20; // [rsp+50h] [rbp-58h] BYREF
  _OWORD v21[2]; // [rsp+58h] [rbp-50h] BYREF
  __int64 v22; // [rsp+78h] [rbp-30h]

  v4 = *(_QWORD *)(a1 + 48);
  v20 = 0;
  memset(v21, 0, sizeof(v21));
  v22 = 0;
  if ( a2 == 3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = *(unsigned __int8 *)(v4 + 143);
      LOBYTE(v16) = 4;
      WPP_RECORDER_SF_dq(
        *(_QWORD *)(*(_QWORD *)(v4 + 8) + 72LL),
        v16,
        12,
        24,
        (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
        *(_BYTE *)(v4 + 143),
        *(_QWORD *)v4);
    }
    if ( (*(_DWORD *)(v4 + 500) & 0x200) == 0 )
    {
      v12 = *(_BYTE *)(v4 + 440) == 0 ? 0xC0000001 : 0;
      goto LABEL_14;
    }
    return UsbDevice_SetDeviceDisabled(v4);
  }
  else
  {
    if ( *(_BYTE *)(a1 + 60) == 1 )
    {
      if ( (*(_DWORD *)(v4 + 500) & 0x200) != 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v15 = *(unsigned __int8 *)(a1 + 61);
          LOBYTE(v15) = 4;
          WPP_RECORDER_SF_dq(
            *(_QWORD *)(*(_QWORD *)(v4 + 8) + 72LL),
            v15,
            12,
            26,
            (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
            *(_BYTE *)(a1 + 61),
            *(_QWORD *)v4);
        }
        goto LABEL_13;
      }
      if ( WdfClientVersionHigherThanFramework )
      {
        if ( (unsigned int)WdfStructureCount > 0x33 )
        {
          LOWORD(v21[0]) = *(_WORD *)(WdfStructures + 408);
LABEL_7:
          (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _OWORD *))(WdfFunctions_01033 + 2128))(
            WdfDriverGlobals,
            *(_QWORD *)(v4 + 432),
            v21);
          v8 = *((_QWORD *)&v21[0] + 1);
          v9 = *(_QWORD *)(*(_QWORD *)(v4 + 8) + 136LL);
          if ( *(_BYTE *)(v9 + 80)
            && ((v17 = *(_QWORD *)(*(_QWORD *)(v9 + 88) + 8LL), *(_BYTE *)(v4 + 664)) && *(_DWORD *)(v17 + 1052) == 2
             || *(_DWORD *)(v17 + 1052) == 1) )
          {
            XilDeviceSlot_SendQuerySlotContextInfoRequest(v9 + 16, v4, &v20, 0);
            v11 = v20;
          }
          else
          {
            v10 = v4 + 624;
            if ( !*(_BYTE *)(v4 + 665) )
              v10 = v4 + 616;
            v11 = (unsigned __int8)*(_DWORD *)(XilCoreUsbDevice_GetDeviceContextBufferVA(v10) + 12);
          }
          *(_DWORD *)(v8 + 28) = v11;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_dqD(*(_QWORD *)(*(_QWORD *)(v4 + 8) + 72LL), *(unsigned __int8 *)(a1 + 61), v11, 25);
LABEL_13:
          v12 = 0;
LABEL_14:
          v13 = *(_QWORD *)(v4 + 432);
          *(_QWORD *)(v4 + 432) = 0;
          return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
                   WdfDriverGlobals,
                   v13,
                   v12);
        }
        v7 = -1;
      }
      else
      {
        v7 = 40;
      }
      LOWORD(v21[0]) = v7;
      goto LABEL_7;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dqdL(
        *(_QWORD *)(*(_QWORD *)(v4 + 8) + 72LL),
        *(unsigned __int8 *)(v4 + 143),
        (*(_DWORD *)(v4 + 500) >> 9) & 1,
        a4);
    if ( (*(_DWORD *)(v4 + 500) & 0x200) == 0 )
    {
      v12 = 3221225473LL;
      goto LABEL_14;
    }
    v18 = *(_QWORD *)(v4 + 8);
    if ( *(_BYTE *)(v4 + 440) )
    {
      Controller_HwVerifierBreakIfEnabled(
        v18,
        *(_QWORD *)v4,
        0,
        0x40000,
        (__int64)"Set Address Command with BSR=1 failed",
        a1 + 24,
        a3);
      return Controller_ReportFatalError(*(_QWORD *)(v4 + 8), 2, 4117, 0, 0, 0, 0);
    }
    else
    {
      v19 = *(_QWORD *)(v18 + 144);
      memset((void *)(v4 + 464), 0, 0x60u);
      *(_DWORD *)(v4 + 500) = 10240;
      *(_QWORD *)(v4 + 504) = UsbDevice_DisableCompletionReturnFailure;
      *(_BYTE *)(v4 + 503) = *(_BYTE *)(v4 + 143);
      *(_QWORD *)(v4 + 512) = v4;
      *(_QWORD *)(v4 + 536) = 0;
      *(_QWORD *)(v4 + 544) = 0;
      *(_QWORD *)(v4 + 552) = 0;
      return Command_SendCommand(v19, v4 + 464);
    }
  }
}

```

## disassembly

```asm
0x140033350  mov     r11, rsp
0x140033353  mov     [r11+10h], rbx
0x140033357  mov     [r11+20h], rbp
0x14003335b  push    rsi
0x14003335c  push    rdi
0x14003335d  push    r14
0x14003335f  sub     rsp, 90h
0x140033366  mov     rax, cs:__security_cookie
0x14003336d  xor     rax, rsp
0x140033370  mov     [rsp+0A8h+var_28], rax
0x140033378  mov     rsi, [rcx+30h]
0x14003337c  xorps   xmm0, xmm0
0x14003337f  xor     eax, eax
0x140033381  xor     r14d, r14d
0x140033384  mov     [r11-58h], r14d
0x140033388  mov     rbp, r8
0x14003338b  mov     rbx, rcx
0x14003338e  movups  [rsp+0A8h+var_50], xmm0
0x140033393  movups  [rsp+0A8h+var_40], xmm0
0x140033398  mov     [r11-30h], rax
0x14003339c  cmp     edx, 3
0x14003339f  jz      loc_140033515
0x1400333a5  movzx   ecx, byte ptr [rcx+3Ch]
0x1400333a9  cmp     cl, 1
0x1400333ac  jnz     loc_140033602
0x1400333b2  test    dword ptr [rsi+1F4h], 200h
0x1400333bc  jnz     loc_1400334CB
0x1400333c2  cmp     cs:WdfClientVersionHigherThanFramework, r14b
0x1400333c9  jnz     loc_140033592
0x1400333cf  lea     eax, [r14+28h]
0x1400333d3  mov     word ptr [rsp+0A8h+var_50], ax
0x1400333d8  mov     rax, cs:WdfFunctions_01033
0x1400333df  lea     r8, [rsp+0A8h+var_50]
0x1400333e4  mov     rdx, [rsi+1B0h]
0x1400333eb  mov     rcx, cs:WdfDriverGlobals
0x1400333f2  mov     rax, [rax+850h]
0x1400333f9  call    _guard_dispatch_icall
0x1400333fe  mov     rax, [rsi+8]
0x140033402  mov     rdi, qword ptr [rsp+0A8h+var_50+8]
0x140033407  mov     r10, [rax+88h]
0x14003340e  cmp     [r10+50h], r14b
0x140033412  jnz     loc_1400335BD
0x140033418  lea     rcx, [rsi+270h]
0x14003341f  cmp     [rsi+299h], r14b
0x140033426  jnz     short loc_14003342F
0x140033428  lea     rcx, [rsi+268h]
0x14003342f  call    XilCoreUsbDevice_GetDeviceContextBufferVA
0x140033434  mov     ecx, [rax+0Ch]
0x140033437  movzx   r8d, cl
0x14003343b  mov     [rdi+1Ch], r8d
0x14003343f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140033446  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003344d  jz      short loc_140033477
0x14003344f  mov     rcx, [rsi+8]
0x140033453  mov     r9d, 19h
0x140033459  mov     rax, [rsi]
0x14003345c  movzx   edx, byte ptr [rbx+3Dh]
0x140033460  mov     [rsp+0A8h+var_70], r8d
0x140033465  mov     rcx, [rcx+48h]
0x140033469  mov     [rsp+0A8h+var_78], rax
0x14003346e  mov     dword ptr [rsp+0A8h+var_80], edx
0x140033472  call    WPP_RECORDER_SF_dqD
0x140033477  mov     r8d, r14d
0x14003347a  mov     rdx, [rsi+1B0h]
0x140033481  mov     [rsi+1B0h], r14
0x140033488  mov     rax, cs:WdfFunctions_01033
0x14003348f  mov     rcx, cs:WdfDriverGlobals
0x140033496  mov     rax, [rax+838h]
0x14003349d  call    _guard_dispatch_icall
0x1400334a2  mov     rcx, [rsp+0A8h+var_28]
0x1400334aa  xor     rcx, rsp; StackCookie
0x1400334ad  call    __security_check_cookie
0x1400334b2  lea     r11, [rsp+0A8h+var_18]
0x1400334ba  mov     rbx, [r11+28h]
0x1400334be  mov     rbp, [r11+38h]
0x1400334c2  mov     rsp, r11
0x1400334c5  pop     r14
0x1400334c7  pop     rdi
0x1400334c8  pop     rsi
0x1400334c9  retn
0x1400334cb  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400334d2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400334d9  jz      short loc_140033477
0x1400334db  mov     rax, [rsi]
0x1400334de  mov     r9d, 1Ah
0x1400334e4  movzx   edx, byte ptr [rbx+3Dh]
0x1400334e8  mov     rcx, [rsi+8]
0x1400334ec  mov     [rsp+0A8h+var_78], rax
0x1400334f1  lea     rax, WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids
0x1400334f8  mov     dword ptr [rsp+0A8h+var_80], edx
0x1400334fc  lea     r8d, [r9-0Eh]
0x140033500  mov     dl, 4
0x140033502  mov     [rsp+0A8h+var_88], rax
0x140033507  mov     rcx, [rcx+48h]
0x14003350b  call    WPP_RECORDER_SF_dq
0x140033510  jmp     loc_140033477
0x140033515  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003351c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140033523  jnz     short loc_14003354B
0x140033525  test    dword ptr [rsi+1F4h], 200h
0x14003352f  jnz     short loc_140033585
0x140033531  mov     al, [rsi+1B8h]
0x140033537  neg     al
0x140033539  sbb     r8d, r8d
0x14003353c  not     r8d
0x14003353f  and     r8d, 0C0000001h
0x140033546  jmp     loc_14003347A
0x14003354b  mov     rax, [rsi]
0x14003354e  mov     r9d, 18h
0x140033554  movzx   edx, byte ptr [rsi+8Fh]
0x14003355b  mov     rcx, [rsi+8]
0x14003355f  mov     [rsp+0A8h+var_78], rax
0x140033564  lea     rax, WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids
0x14003356b  mov     dword ptr [rsp+0A8h+var_80], edx
0x14003356f  lea     r8d, [r9-0Ch]
0x140033573  mov     dl, 4
0x140033575  mov     [rsp+0A8h+var_88], rax
0x14003357a  mov     rcx, [rcx+48h]
0x14003357e  call    WPP_RECORDER_SF_dq
0x140033583  jmp     short loc_140033525
0x140033585  mov     rcx, rsi
0x140033588  call    UsbDevice_SetDeviceDisabled
0x14003358d  jmp     loc_1400334A2
0x140033592  cmp     cs:WdfStructureCount, 33h ; '3'
0x140033599  jbe     short loc_1400335B3
0x14003359b  mov     rax, cs:WdfStructures
0x1400335a2  movzx   ecx, word ptr [rax+198h]
0x1400335a9  mov     word ptr [rsp+0A8h+var_50], cx
0x1400335ae  jmp     loc_1400333D8
0x1400335b3  mov     eax, 0FFFFh
0x1400335b8  jmp     loc_1400333D3
0x1400335bd  mov     rax, [r10+58h]
0x1400335c1  mov     rcx, [rax+8]
0x1400335c5  cmp     [rsi+298h], r14b
0x1400335cc  jz      short loc_1400335D7
0x1400335ce  cmp     dword ptr [rcx+41Ch], 2
0x1400335d5  jz      short loc_1400335E4
0x1400335d7  cmp     dword ptr [rcx+41Ch], 1
0x1400335de  jnz     loc_140033418
0x1400335e4  xor     r9d, r9d
0x1400335e7  lea     r8, [rsp+0A8h+var_58]
0x1400335ec  mov     rdx, rsi
0x1400335ef  lea     rcx, [r10+10h]
0x1400335f3  call    XilDeviceSlot_SendQuerySlotContextInfoRequest
0x1400335f8  mov     r8d, [rsp+0A8h+var_58]
0x1400335fd  jmp     loc_14003343B
0x140033602  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140033609  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140033610  jz      short loc_14003364C
0x140033612  mov     r8d, [rsi+1F4h]
0x140033619  mov     eax, ecx
0x14003361b  mov     rcx, [rsi+8]
0x14003361f  movzx   edx, byte ptr [rsi+8Fh]
0x140033626  mov     [rsp+0A8h+var_68], eax
0x14003362a  mov     rax, [rsi]
0x14003362d  mov     rcx, [rcx+48h]
0x140033631  shr     r8d, 9
0x140033635  and     r8d, 1
0x140033639  mov     [rsp+0A8h+var_70], r8d
0x14003363e  mov     [rsp+0A8h+var_78], rax
0x140033643  mov     dword ptr [rsp+0A8h+var_80], edx
0x140033647  call    WPP_RECORDER_SF_dqdL
0x14003364c  test    dword ptr [rsi+1F4h], 200h
0x140033656  jnz     short loc_140033663
0x140033658  mov     r8d, 0C0000001h
0x14003365e  jmp     loc_14003347A
0x140033663  mov     rdi, [rsi+8]
0x140033667  cmp     [rsi+1B8h], r14b
0x14003366e  jz      short loc_1400336C8
0x140033670  mov     rdx, [rsi]
0x140033673  lea     rax, [rbx+18h]
0x140033677  mov     [rsp+0A8h+var_78], rbp
0x14003367c  mov     r9d, 40000h
0x140033682  mov     [rsp+0A8h+var_80], rax
0x140033687  xor     r8d, r8d
0x14003368a  lea     rax, aSetAddressComm; "Set Address Command with BSR=1 failed"
0x140033691  mov     rcx, rdi
0x140033694  mov     [rsp+0A8h+var_88], rax
0x140033699  call    Controller_HwVerifierBreakIfEnabled
0x14003369e  mov     rcx, [rsi+8]
0x1400336a2  xor     r9d, r9d
0x1400336a5  mov     [rsp+0A8h+var_78], r14
0x1400336aa  mov     r8d, 1015h
0x1400336b0  mov     [rsp+0A8h+var_80], r14
0x1400336b5  mov     [rsp+0A8h+var_88], r14
0x1400336ba  lea     edx, [r9+2]
0x1400336be  call    Controller_ReportFatalError
0x1400336c3  jmp     loc_1400334A2
0x1400336c8  mov     rdi, [rdi+90h]
0x1400336cf  lea     rbx, [rsi+1D0h]
0x1400336d6  xor     edx, edx; Val
0x1400336d8  mov     rcx, rbx; void *
0x1400336db  lea     r8d, [rdx+60h]; Size
0x1400336df  call    memset
0x1400336e4  lea     rax, UsbDevice_DisableCompletionReturnFailure
0x1400336eb  mov     dword ptr [rsi+1F4h], 2800h
0x1400336f5  mov     [rsi+1F8h], rax
0x1400336fc  mov     rdx, rbx
0x1400336ff  mov     al, [rsi+8Fh]
0x140033705  mov     rcx, rdi
0x140033708  mov     [rsi+1F7h], al
0x14003370e  mov     [rsi+200h], rsi
0x140033715  mov     [rsi+218h], r14
0x14003371c  mov     [rsi+220h], r14
0x140033723  mov     [rsi+228h], r14
0x14003372a  call    Command_SendCommand
0x14003372f  jmp     loc_1400334A2
```
