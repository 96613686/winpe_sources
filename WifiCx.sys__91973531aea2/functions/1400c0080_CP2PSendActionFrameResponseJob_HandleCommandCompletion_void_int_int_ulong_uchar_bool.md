# CP2PSendActionFrameResponseJob::HandleCommandCompletion(void *,int,int,ulong,uchar *,bool *)

- ea: `0x1400c0080`
- end: `0x1400c0449`
- name: `?HandleCommandCompletion@CP2PSendActionFrameResponseJob@@UEAAHPEAXHHKPEAEPEA_N@Z`
- size: `969`
- prototype: `__int64 __fastcall(CP2PSendActionFrameResponseJob *__hidden this, void *, int, int, unsigned int, unsigned __int8 *, bool *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400032f0`
- `0x140009420`
- `0x140014b30`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14004162c`
- `0x1400c0080`
- `0x1400c371c`
- `0x1400dfd00`
- `0x1400dfe00`

## pseudocode

```c
__int64 __fastcall CP2PSendActionFrameResponseJob::HandleCommandCompletion(
        CP2PSendActionFrameResponseJob *this,
        void *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int8 *a6,
        bool *a7)
{
  unsigned int v8; // edi
  __int64 *v10; // rdx
  int v11; // r9d
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // eax
  __int64 v15; // rcx
  int v16; // r9d
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v18; // r10
  int v19; // ecx
  __int64 v20; // r9
  __int16 v21; // ax
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  __int64 v27; // r9
  __int16 v28; // ax
  unsigned int v29; // eax
  unsigned int v30; // r15d
  _QWORD *v31; // rax
  _QWORD *v32; // r14
  int v34; // [rsp+20h] [rbp-58h]
  int v35; // [rsp+30h] [rbp-48h]
  __int64 v36; // [rsp+38h] [rbp-40h]
  unsigned int v37; // [rsp+38h] [rbp-40h]
  int v38; // [rsp+38h] [rbp-40h]
  __int64 v39; // [rsp+40h] [rbp-38h] BYREF
  size_t Size; // [rsp+48h] [rbp-30h] BYREF
  void *Src; // [rsp+50h] [rbp-28h]
  char v42; // [rsp+58h] [rbp-20h]

  LODWORD(Size) = 0;
  Src = 0;
  v8 = a3;
  v42 = 0;
  LODWORD(v39) = 0;
  WORD2(v39) = 0;
  BYTE6(v39) = 0;
  v10 = WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v10,
      a3,
      227,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
    v10 = WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids;
  }
  *a7 = 0;
  if ( v8 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_54;
    v11 = 228;
    v37 = v8;
    goto LABEL_8;
  }
  if ( !a4 )
  {
    v14 = ParseWdiIndicationP2pSendResponseActionFrameCompleteFromIhv(
            a5 - 48,
            a6 + 48,
            *((_QWORD *)this + 67) + 5384LL,
            &v39);
    v8 = v14;
    if ( v14 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_54;
      v16 = 230;
      v38 = v14;
      v35 = *((_DWORD *)this + 4);
LABEL_15:
      LOBYTE(v12) = 2;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        v13,
        v16,
        (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
        (char)this,
        v35,
        v38,
        v39);
      goto LABEL_50;
    }
    IsEnabledDeviceUsageNoInline = Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline(v15, v12, v13);
    v18 = *((_QWORD *)this + 67);
    if ( IsEnabledDeviceUsageNoInline )
    {
      v19 = *((_DWORD *)this + 369);
      if ( v19 == 2 )
      {
        v20 = *((unsigned __int16 *)this + 752);
        v21 = *((_WORD *)this + 753);
      }
      else if ( v19 == 5 )
      {
        v20 = *((unsigned __int16 *)this + 803);
        v21 = *((_WORD *)this + 804);
      }
      else
      {
        if ( v19 != 7 || (*((_DWORD *)this + 406) & 1) == 0 )
          goto LABEL_25;
        v20 = *((unsigned __int16 *)this + 833);
        v21 = *((_WORD *)this + 834);
      }
      LOWORD(v34) = v21;
      CP2PActionFrameHelpers::ValidateConfigurationTimeoutInternal(v18, Src, (unsigned int)Size, v20, v34, v19);
LABEL_25:
      v22 = *((_DWORD *)this + 369);
      goto LABEL_26;
    }
    v26 = *((_DWORD *)this + 275);
    if ( v26 == 2 )
    {
      v27 = *((unsigned __int16 *)this + 564);
      v28 = *((_WORD *)this + 565);
    }
    else if ( v26 == 5 )
    {
      v27 = *((unsigned __int16 *)this + 615);
      v28 = *((_WORD *)this + 616);
    }
    else
    {
      if ( v26 != 7 || (*((_DWORD *)this + 312) & 1) == 0 )
        goto LABEL_39;
      v27 = *((unsigned __int16 *)this + 645);
      v28 = *((_WORD *)this + 646);
    }
    LOWORD(v34) = v28;
    CP2PActionFrameHelpers::ValidateConfigurationTimeoutInternal(v18, Src, (unsigned int)Size, v27, v34, v26);
LABEL_39:
    v22 = *((_DWORD *)this + 275);
LABEL_26:
    v23 = v22 - 2;
    if ( v23 )
    {
      v24 = v23 - 1;
      if ( v24 )
      {
        v25 = v24 - 2;
        if ( v25 )
        {
          if ( v25 != 2 )
          {
            v8 = -1073741637;
            goto LABEL_50;
          }
        }
      }
    }
    v29 = Size;
    *((_DWORD *)this + 499) = 0;
    *((_DWORD *)this + 500) = 24;
    *((_DWORD *)this + 501) = v29;
    v30 = v29 + 24;
    if ( v29 < 0xFFFFFFE8 )
    {
      v31 = operator new(v30);
      v32 = v31;
      if ( v31 )
      {
        *(_OWORD *)v31 = *((_OWORD *)this + 124);
        v31[2] = *((_QWORD *)this + 250);
        if ( (_DWORD)Size )
          memmove(v31 + 3, Src, (unsigned int)Size);
        *((_QWORD *)this + 247) = v32;
        *((_DWORD *)this + 492) = v30;
        goto LABEL_50;
      }
      v8 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_54;
      v16 = 232;
      v38 = -1073741670;
    }
    else
    {
      v8 = -2147483643;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_54;
      v16 = 231;
      v38 = -2147483643;
    }
    v35 = *((_DWORD *)this + 4);
    goto LABEL_15;
  }
  v8 = a4;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_54;
  v11 = 229;
  v37 = a4;
LABEL_8:
  LOBYTE(v10) = 2;
  WPP_RECORDER_SF_qDD(
    WPP_GLOBAL_Control->DeviceExtension,
    (_DWORD)v10,
    a3,
    v11,
    (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
    (char)this,
    *((_DWORD *)this + 4),
    v37,
    v39);
LABEL_50:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v12) = 5;
    LODWORD(v36) = v8;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      v13,
      233,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v36);
  }
LABEL_54:
  ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(&Size);
  return v8;
}

```

## disassembly

```asm
0x1400c0080  push    rbp
0x1400c0082  push    rbx
0x1400c0083  push    rsi
0x1400c0084  push    rdi
0x1400c0085  push    r12
0x1400c0087  push    r13
0x1400c0089  push    r14
0x1400c008b  push    r15
0x1400c008d  mov     rbp, rsp
0x1400c0090  sub     rsp, 78h
0x1400c0094  mov     rax, cs:__security_cookie
0x1400c009b  xor     rax, rsp
0x1400c009e  mov     [rbp+var_18], rax
0x1400c00a2  mov     r15, [rbp+arg_28]
0x1400c00a6  xor     eax, eax
0x1400c00a8  mov     r14, [rbp+arg_30]
0x1400c00ac  xor     r12d, r12d
0x1400c00af  mov     dword ptr [rbp+Size], r12d
0x1400c00b3  mov     esi, r9d
0x1400c00b6  mov     [rbp+Src], r12
0x1400c00ba  mov     edi, r8d
0x1400c00bd  mov     [rbp+var_20], r12b
0x1400c00c1  mov     rbx, rcx
0x1400c00c4  mov     [rbp+var_38], eax
0x1400c00c7  mov     [rbp+var_34], ax
0x1400c00cb  mov     [rbp+var_32], al
0x1400c00ce  lea     r13, WPP_RECORDER_INITIALIZED
0x1400c00d5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400c00dc  lea     rdx, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400c00e3  jz      short loc_1400C0122
0x1400c00e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c00ec  cmp     byte ptr [rcx+29h], 5
0x1400c00f0  jnb     short loc_1400C00F9
0x1400c00f2  cmp     [rcx+48h], r12w
0x1400c00f7  jz      short loc_1400C0122
0x1400c00f9  mov     eax, [rbx+10h]
0x1400c00fc  mov     r9d, 0E3h
0x1400c0102  mov     rcx, [rcx+40h]
0x1400c0106  mov     [rsp+78h+var_48], eax
0x1400c010a  mov     [rsp+78h+var_50], rbx
0x1400c010f  mov     [rsp+78h+var_58], rdx
0x1400c0114  mov     dl, 5
0x1400c0116  call    WPP_RECORDER_SF_qD
0x1400c011b  lea     rdx, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400c0122  mov     [r14], r12b
0x1400c0125  test    edi, edi
0x1400c0127  jz      short loc_1400C0168
0x1400c0129  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400c0130  jz      loc_1400C0420
0x1400c0136  mov     r9d, 0E4h
0x1400c013c  mov     dword ptr [rsp+78h+var_40], edi
0x1400c0140  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c0147  mov     eax, [rbx+10h]
0x1400c014a  mov     [rsp+78h+var_48], eax
0x1400c014e  mov     [rsp+78h+var_50], rbx
0x1400c0153  mov     rcx, [rcx+40h]
0x1400c0157  mov     [rsp+78h+var_58], rdx
0x1400c015c  mov     dl, 2
0x1400c015e  call    WPP_RECORDER_SF_qDD
0x1400c0163  jmp     loc_1400C03D6
0x1400c0168  test    esi, esi
0x1400c016a  jz      short loc_1400C0187
0x1400c016c  mov     edi, esi
0x1400c016e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400c0175  jz      loc_1400C0420
0x1400c017b  mov     r9d, 0E5h
0x1400c0181  mov     dword ptr [rsp+78h+var_40], esi
0x1400c0185  jmp     short loc_1400C0140
0x1400c0187  mov     r8, [rbx+218h]
0x1400c018e  lea     rdx, [r15+30h]
0x1400c0192  mov     ecx, [rbp+arg_20]
0x1400c0195  lea     r9, [rbp+var_38]
0x1400c0199  add     r8, 1508h
0x1400c01a0  add     ecx, 0FFFFFFD0h
0x1400c01a3  call    ParseWdiIndicationP2pSendResponseActionFrameCompleteFromIhv
0x1400c01a8  mov     edi, eax
0x1400c01aa  test    eax, eax
0x1400c01ac  jz      short loc_1400C01F4
0x1400c01ae  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400c01b5  jz      loc_1400C0420
0x1400c01bb  mov     ecx, [rbx+10h]
0x1400c01be  mov     r9d, 0E6h
0x1400c01c4  mov     dword ptr [rsp+78h+var_40], eax
0x1400c01c8  mov     [rsp+78h+var_48], ecx
0x1400c01cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c01d3  lea     rsi, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400c01da  mov     [rsp+78h+var_50], rbx
0x1400c01df  mov     dl, 2
0x1400c01e1  mov     [rsp+78h+var_58], rsi
0x1400c01e6  mov     rcx, [rcx+40h]
0x1400c01ea  call    WPP_RECORDER_SF_qDD
0x1400c01ef  jmp     loc_1400C03DD
0x1400c01f4  call    Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline
0x1400c01f9  mov     r10, [rbx+218h]
0x1400c0200  test    eax, eax
0x1400c0202  jz      loc_1400C02A1
0x1400c0208  mov     ecx, [rbx+5C4h]
0x1400c020e  cmp     ecx, 2
0x1400c0211  jz      short loc_1400C0249
0x1400c0213  cmp     ecx, 5
0x1400c0216  jz      short loc_1400C0238
0x1400c0218  cmp     ecx, 7
0x1400c021b  jnz     short loc_1400C0271
0x1400c021d  mov     eax, [rbx+658h]
0x1400c0223  test    al, 1
0x1400c0225  jz      short loc_1400C0271
0x1400c0227  movzx   r9d, word ptr [rbx+682h]
0x1400c022f  movzx   eax, word ptr [rbx+684h]
0x1400c0236  jmp     short loc_1400C0258
0x1400c0238  movzx   r9d, word ptr [rbx+646h]
0x1400c0240  movzx   eax, word ptr [rbx+648h]
0x1400c0247  jmp     short loc_1400C0258
0x1400c0249  movzx   r9d, word ptr [rbx+5E0h]
0x1400c0251  movzx   eax, word ptr [rbx+5E2h]
0x1400c0258  mov     r8d, dword ptr [rbp+Size]
0x1400c025c  mov     rdx, [rbp+Src]
0x1400c0260  mov     dword ptr [rsp+78h+var_50], ecx
0x1400c0264  mov     rcx, r10
0x1400c0267  mov     word ptr [rsp+78h+var_58], ax
0x1400c026c  call    ?ValidateConfigurationTimeoutInternal@CP2PActionFrameHelpers@@CAXPEAVCAdapter@@PEBEKGGW4_WDI_P2P_ACTION_FRAME_TYPE@@@Z; CP2PActionFrameHelpers::ValidateConfigurationTimeoutInternal(CAdapter *,uchar const *,ulong,ushort,ushort,_WDI_P2P_ACTION_FRAME_TYPE)
0x1400c0271  mov     ecx, [rbx+5C4h]
0x1400c0277  sub     ecx, 2
0x1400c027a  jz      loc_1400C0315
0x1400c0280  sub     ecx, 1
0x1400c0283  jz      loc_1400C0315
0x1400c0289  sub     ecx, 2
0x1400c028c  jz      loc_1400C0315
0x1400c0292  cmp     ecx, 2
0x1400c0295  jz      short loc_1400C0315
0x1400c0297  mov     edi, 0C00000BBh
0x1400c029c  jmp     loc_1400C03D6
0x1400c02a1  mov     ecx, [rbx+44Ch]
0x1400c02a7  cmp     ecx, 2
0x1400c02aa  jz      short loc_1400C02E2
0x1400c02ac  cmp     ecx, 5
0x1400c02af  jz      short loc_1400C02D1
0x1400c02b1  cmp     ecx, 7
0x1400c02b4  jnz     short loc_1400C030A
0x1400c02b6  mov     eax, [rbx+4E0h]
0x1400c02bc  test    al, 1
0x1400c02be  jz      short loc_1400C030A
0x1400c02c0  movzx   r9d, word ptr [rbx+50Ah]
0x1400c02c8  movzx   eax, word ptr [rbx+50Ch]
0x1400c02cf  jmp     short loc_1400C02F1
0x1400c02d1  movzx   r9d, word ptr [rbx+4CEh]
0x1400c02d9  movzx   eax, word ptr [rbx+4D0h]
0x1400c02e0  jmp     short loc_1400C02F1
0x1400c02e2  movzx   r9d, word ptr [rbx+468h]
0x1400c02ea  movzx   eax, word ptr [rbx+46Ah]
0x1400c02f1  mov     r8d, dword ptr [rbp+Size]
0x1400c02f5  mov     rdx, [rbp+Src]
0x1400c02f9  mov     dword ptr [rsp+78h+var_50], ecx
0x1400c02fd  mov     rcx, r10
0x1400c0300  mov     word ptr [rsp+78h+var_58], ax
0x1400c0305  call    ?ValidateConfigurationTimeoutInternal@CP2PActionFrameHelpers@@CAXPEAVCAdapter@@PEBEKGGW4_WDI_P2P_ACTION_FRAME_TYPE@@@Z; CP2PActionFrameHelpers::ValidateConfigurationTimeoutInternal(CAdapter *,uchar const *,ulong,ushort,ushort,_WDI_P2P_ACTION_FRAME_TYPE)
0x1400c030a  mov     ecx, [rbx+44Ch]
0x1400c0310  jmp     loc_1400C0277
0x1400c0315  mov     eax, dword ptr [rbp+Size]
0x1400c0318  mov     rsi, rbx
0x1400c031b  mov     [rbx+7CCh], r12d
0x1400c0322  mov     dword ptr [rbx+7D0h], 18h
0x1400c032c  mov     [rbx+7D4h], eax
0x1400c0332  lea     r15d, [rax+18h]
0x1400c0336  cmp     r15d, 18h
0x1400c033a  jnb     short loc_1400C0368
0x1400c033c  mov     edi, 80000005h
0x1400c0341  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400c0348  jz      loc_1400C0420
0x1400c034e  mov     r9d, 0E7h
0x1400c0354  mov     dword ptr [rsp+78h+var_40], 80000005h
0x1400c035c  mov     eax, [rbx+10h]
0x1400c035f  mov     [rsp+78h+var_48], eax
0x1400c0363  jmp     loc_1400C01CC
0x1400c0368  mov     ecx, r15d; unsigned __int64
0x1400c036b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400c0370  mov     r14, rax
0x1400c0373  test    rax, rax
0x1400c0376  jnz     short loc_1400C039A
0x1400c0378  mov     edi, 0C000009Ah
0x1400c037d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400c0384  jz      loc_1400C0420
0x1400c038a  mov     r9d, 0E8h
0x1400c0390  mov     dword ptr [rsp+78h+var_40], 0C000009Ah
0x1400c0398  jmp     short loc_1400C035C
0x1400c039a  movups  xmm0, xmmword ptr [rsi+7C0h]
0x1400c03a1  movups  xmmword ptr [rax], xmm0
0x1400c03a4  movsd   xmm1, qword ptr [rsi+7D0h]
0x1400c03ac  movsd   qword ptr [rax+10h], xmm1
0x1400c03b1  mov     eax, dword ptr [rbp+Size]
0x1400c03b4  test    eax, eax
0x1400c03b6  jz      short loc_1400C03C8
0x1400c03b8  mov     rdx, [rbp+Src]; Src
0x1400c03bc  lea     rcx, [r14+18h]; void *
0x1400c03c0  mov     r8d, eax; Size
0x1400c03c3  call    memmove
0x1400c03c8  mov     [rbx+7B8h], r14
0x1400c03cf  mov     [rbx+7B0h], r15d
0x1400c03d6  lea     rsi, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400c03dd  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400c03e4  jz      short loc_1400C0420
0x1400c03e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c03ed  cmp     byte ptr [rcx+29h], 5
0x1400c03f1  jnb     short loc_1400C03FA
0x1400c03f3  cmp     [rcx+48h], r12w
0x1400c03f8  jz      short loc_1400C0420
0x1400c03fa  mov     eax, [rbx+10h]
0x1400c03fd  mov     r9d, 0E9h
0x1400c0403  mov     rcx, [rcx+40h]
0x1400c0407  mov     dl, 5
0x1400c0409  mov     dword ptr [rsp+78h+var_40], edi
0x1400c040d  mov     [rsp+78h+var_48], eax
0x1400c0411  mov     [rsp+78h+var_50], rbx
0x1400c0416  mov     [rsp+78h+var_58], rsi
0x1400c041b  call    WPP_RECORDER_SF_qDD
0x1400c0420  lea     rcx, [rbp+Size]; void *
0x1400c0424  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ; ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(void)
0x1400c0429  mov     eax, edi
0x1400c042b  mov     rcx, [rbp+var_18]
0x1400c042f  xor     rcx, rsp; StackCookie
0x1400c0432  call    __security_check_cookie
0x1400c0437  add     rsp, 78h
0x1400c043b  pop     r15
0x1400c043d  pop     r14
0x1400c043f  pop     r13
0x1400c0441  pop     r12
0x1400c0443  pop     rdi
0x1400c0444  pop     rsi
0x1400c0445  pop     rbx
0x1400c0446  pop     rbp
0x1400c0447  retn
```
