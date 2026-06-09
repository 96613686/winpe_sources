# CP2PSendActionFrameRequestJob::ConstructCompletionIndication(void)

- ea: `0x1400bf894`
- end: `0x1400bfce0`
- name: `?ConstructCompletionIndication@CP2PSendActionFrameRequestJob@@IEAAHXZ`
- size: `1100`
- prototype: `__int64 __fastcall(CP2PSendActionFrameRequestJob *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400c25f0`

## callees

- `0x1400032f0`
- `0x140009420`
- `0x140014b30`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002073c`
- `0x140020860`
- `0x14002bd34`
- `0x1400415cc`
- `0x1400bf894`
- `0x1400c371c`
- `0x1400dfd00`
- `0x1400dfe00`

## pseudocode

```c
__int64 __fastcall CP2PSendActionFrameRequestJob::ConstructCompletionIndication(
        CP2PSendActionFrameRequestJob *this,
        __int64 a2,
        int a3)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  unsigned int v6; // esi
  unsigned int StatusFromTaskOutput; // eax
  unsigned int v8; // edi
  int v9; // r9d
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r9
  __int16 v16; // ax
  int *v17; // rsi
  __int64 v18; // r9
  __int16 v19; // ax
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  size_t v23; // rsi
  int v24; // eax
  unsigned int v25; // r12d
  char *v26; // rax
  char *v27; // r14
  int v29; // [rsp+20h] [rbp-59h]
  int v30; // [rsp+30h] [rbp-49h]
  __int64 v31; // [rsp+38h] [rbp-41h]
  int v32; // [rsp+38h] [rbp-41h]
  unsigned int v33; // [rsp+50h] [rbp-29h] BYREF
  int v34; // [rsp+54h] [rbp-25h] BYREF
  unsigned __int8 *v35; // [rsp+58h] [rbp-21h] BYREF
  int v36; // [rsp+60h] [rbp-19h] BYREF
  __int16 v37; // [rsp+64h] [rbp-15h]
  char v38; // [rsp+66h] [rbp-13h]
  size_t Size; // [rsp+68h] [rbp-11h] BYREF
  void *Src; // [rsp+70h] [rbp-9h]
  char v41; // [rsp+78h] [rbp-1h]

  v36 = 0;
  LODWORD(Size) = 0;
  Src = 0;
  v41 = 0;
  v35 = 0;
  v33 = 0;
  v34 = 0;
  v37 = 0;
  v38 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      a3,
      172,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
  }
  if ( (unsigned int)Task::get_OutputBuffer((CP2PSendActionFrameRequestJob *)((char *)this + 1544), &v33, &v35)
    || (v6 = v33, v33 < 0x30) )
  {
    v8 = -1073676267;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_60;
    v9 = 173;
    v32 = -1073676267;
LABEL_54:
    v30 = *((_DWORD *)this + 4);
LABEL_55:
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      v5,
      v9,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      v30,
      v32);
    goto LABEL_56;
  }
  StatusFromTaskOutput = CMessageHelper::GetStatusFromTaskOutput(
                           (CP2PSendActionFrameRequestJob *)((char *)this + 1544),
                           &v34);
  v8 = StatusFromTaskOutput;
  if ( StatusFromTaskOutput )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_60;
    v9 = 174;
    v32 = StatusFromTaskOutput;
    v30 = *((_DWORD *)this + 4);
    goto LABEL_55;
  }
  v8 = v34;
  if ( v34 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_60;
    LOBYTE(v4) = 2;
    WPP_RECORDER_SF_qDdd(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      v5,
      175,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v34,
      v34);
    goto LABEL_56;
  }
  v10 = ParseWdiIndicationP2pSendRequestActionFrameCompleteFromIhv(
          v6 - 48,
          v35 + 48,
          *((_QWORD *)this + 67) + 5384LL,
          &v36);
  v8 = v10;
  if ( v10 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_60;
    v9 = 176;
    v32 = v10;
    goto LABEL_54;
  }
  if ( (unsigned int)Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline(v11, v4, v5) )
  {
    v13 = *((unsigned int *)this + 249);
    if ( *((_DWORD *)this + 249) == 1 )
    {
      v15 = *((unsigned __int16 *)this + 511);
      v16 = *((_WORD *)this + 512);
    }
    else
    {
      v14 = (unsigned int)(*((_DWORD *)this + 249) - 4);
      if ( *((_DWORD *)this + 249) == 4 )
      {
        v15 = *((unsigned __int16 *)this + 526);
        v16 = *((_WORD *)this + 527);
      }
      else
      {
        if ( *((_DWORD *)this + 249) != 6 || (*((_DWORD *)this + 276) & 2) == 0 )
          goto LABEL_25;
        v15 = *((unsigned __int16 *)this + 589);
        v16 = *((_WORD *)this + 590);
      }
    }
    LOWORD(v29) = v16;
    CP2PActionFrameHelpers::ValidateConfigurationTimeoutInternal(
      *((_QWORD *)this + 67),
      Src,
      (unsigned int)Size,
      v15,
      v29,
      v13);
LABEL_25:
    v17 = (int *)((char *)this + 580);
    goto LABEL_34;
  }
  v17 = (int *)((char *)this + 580);
  v13 = *((unsigned int *)this + 145);
  if ( *((_DWORD *)this + 145) == 1 )
  {
    v18 = *((unsigned __int16 *)this + 303);
    v19 = *((_WORD *)this + 304);
  }
  else
  {
    v14 = (unsigned int)(*((_DWORD *)this + 145) - 4);
    if ( *((_DWORD *)this + 145) == 4 )
    {
      v18 = *((unsigned __int16 *)this + 318);
      v19 = *((_WORD *)this + 319);
    }
    else
    {
      if ( *((_DWORD *)this + 145) != 6 || (*((_DWORD *)this + 172) & 2) == 0 )
        goto LABEL_34;
      v18 = *((unsigned __int16 *)this + 381);
      v19 = *((_WORD *)this + 382);
    }
  }
  LOWORD(v29) = v19;
  CP2PActionFrameHelpers::ValidateConfigurationTimeoutInternal(
    *((_QWORD *)this + 67),
    Src,
    (unsigned int)Size,
    v18,
    v29,
    v13);
LABEL_34:
  if ( (unsigned int)Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline(v14, v13, v12) )
    v20 = *((_DWORD *)this + 249);
  else
    v20 = *v17;
  v21 = v20 - 1;
  if ( !v21 )
  {
    *((_DWORD *)this + 1134) = 0;
    v23 = 24;
    *((_DWORD *)this + 1135) = 24;
    v24 = Size;
    *((_DWORD *)this + 1136) = Size;
LABEL_43:
    v25 = v24 + v23;
    if ( v24 + (int)v23 >= (unsigned int)v23 )
    {
      v26 = (char *)operator new(v25);
      v27 = v26;
      if ( v26 )
      {
        memmove(v26, (char *)this + 4524, v23);
        if ( (_DWORD)Size )
          memmove(&v27[v23], Src, (unsigned int)Size);
        *((_QWORD *)this + 564) = v27;
        *((_DWORD *)this + 1126) = v25;
        goto LABEL_56;
      }
      v8 = -1073741670;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_60;
      v9 = 178;
      v32 = -1073741670;
    }
    else
    {
      v8 = -2147483643;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_60;
      v9 = 177;
      v32 = -2147483643;
    }
    goto LABEL_54;
  }
  v22 = v21 - 3;
  if ( !v22 || v22 == 2 )
  {
    *((_DWORD *)this + 1136) = 0;
    v23 = 32;
    *((_DWORD *)this + 1137) = 32;
    v24 = Size;
    *((_DWORD *)this + 1138) = Size;
    goto LABEL_43;
  }
  v8 = -1073741637;
LABEL_56:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v4) = 5;
    LODWORD(v31) = v8;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v4,
      v5,
      179,
      (__int64)WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v31);
  }
LABEL_60:
  ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(&Size);
  return v8;
}

```

## disassembly

```asm
0x1400bf894  push    rbp
0x1400bf896  push    rbx
0x1400bf897  push    rsi
0x1400bf898  push    rdi
0x1400bf899  push    r12
0x1400bf89b  push    r13
0x1400bf89d  push    r14
0x1400bf89f  push    r15
0x1400bf8a1  lea     rbp, [rsp-1Fh]
0x1400bf8a6  sub     rsp, 98h
0x1400bf8ad  mov     rax, cs:__security_cookie
0x1400bf8b4  xor     rax, rsp
0x1400bf8b7  mov     [rbp+57h+var_50], rax
0x1400bf8bb  xor     eax, eax
0x1400bf8bd  mov     rbx, rcx
0x1400bf8c0  xor     r13d, r13d
0x1400bf8c3  mov     [rbp+57h+var_70], eax
0x1400bf8c6  mov     dword ptr [rbp+57h+Size], r13d
0x1400bf8ca  mov     [rbp+57h+Src], r13
0x1400bf8ce  mov     [rbp+57h+var_58], r13b
0x1400bf8d2  mov     [rbp+57h+var_78], r13
0x1400bf8d6  mov     [rbp+57h+var_80], r13d
0x1400bf8da  mov     [rbp+57h+var_7C], r13d
0x1400bf8de  mov     [rbp+57h+var_6C], ax
0x1400bf8e2  mov     [rbp+57h+var_6A], al
0x1400bf8e5  lea     r14, WPP_RECORDER_INITIALIZED
0x1400bf8ec  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400bf8f3  lea     r15, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400bf8fa  jz      short loc_1400BF932
0x1400bf8fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bf903  cmp     byte ptr [rcx+29h], 5
0x1400bf907  jnb     short loc_1400BF910
0x1400bf909  cmp     [rcx+48h], r13w
0x1400bf90e  jz      short loc_1400BF932
0x1400bf910  mov     eax, [rbx+10h]
0x1400bf913  mov     r9d, 0ACh
0x1400bf919  mov     rcx, [rcx+40h]
0x1400bf91d  mov     dl, 5
0x1400bf91f  mov     [rsp+0D0h+var_A0], eax
0x1400bf923  mov     [rsp+0D0h+var_A8], rbx
0x1400bf928  mov     [rsp+0D0h+var_B0], r15
0x1400bf92d  call    WPP_RECORDER_SF_qD
0x1400bf932  lea     rdi, [rbx+608h]
0x1400bf939  mov     rcx, rdi; this
0x1400bf93c  lea     r8, [rbp+57h+var_78]; unsigned __int8 **
0x1400bf940  lea     rdx, [rbp+57h+var_80]; unsigned int *
0x1400bf944  call    ?get_OutputBuffer@Task@@QEAAHPEAKPEAPEAE@Z; Task::get_OutputBuffer(ulong *,uchar * *)
0x1400bf949  test    eax, eax
0x1400bf94b  jnz     loc_1400BFC32
0x1400bf951  mov     esi, [rbp+57h+var_80]
0x1400bf954  cmp     esi, 30h ; '0'
0x1400bf957  jb      loc_1400BFC32
0x1400bf95d  lea     rdx, [rbp+57h+var_7C]; int *
0x1400bf961  mov     rcx, rdi; struct Task *
0x1400bf964  call    ?GetStatusFromTaskOutput@CMessageHelper@@SAHPEAVTask@@PEAH@Z; CMessageHelper::GetStatusFromTaskOutput(Task *,int *)
0x1400bf969  mov     edi, eax
0x1400bf96b  test    eax, eax
0x1400bf96d  jz      short loc_1400BF992
0x1400bf96f  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400bf976  jz      loc_1400BFCB4
0x1400bf97c  mov     ecx, [rbx+10h]
0x1400bf97f  mov     r9d, 0AEh
0x1400bf985  mov     dword ptr [rsp+0D0h+var_98], eax
0x1400bf989  mov     [rsp+0D0h+var_A0], ecx
0x1400bf98d  jmp     loc_1400BFC55
0x1400bf992  mov     edi, [rbp+57h+var_7C]
0x1400bf995  test    edi, edi
0x1400bf997  jz      short loc_1400BF9DC
0x1400bf999  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400bf9a0  jz      loc_1400BFCB4
0x1400bf9a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bf9ad  mov     r9d, 0AFh
0x1400bf9b3  mov     eax, [rbx+10h]
0x1400bf9b6  mov     dl, 2
0x1400bf9b8  mov     [rsp+0D0h+var_90], edi
0x1400bf9bc  mov     dword ptr [rsp+0D0h+var_98], edi
0x1400bf9c0  mov     rcx, [rcx+40h]
0x1400bf9c4  mov     [rsp+0D0h+var_A0], eax
0x1400bf9c8  mov     [rsp+0D0h+var_A8], rbx
0x1400bf9cd  mov     [rsp+0D0h+var_B0], r15
0x1400bf9d2  call    WPP_RECORDER_SF_qDdd
0x1400bf9d7  jmp     loc_1400BFC71
0x1400bf9dc  mov     r8, [rbx+218h]
0x1400bf9e3  lea     ecx, [rsi-30h]
0x1400bf9e6  mov     rdx, [rbp+57h+var_78]
0x1400bf9ea  lea     r9, [rbp+57h+var_70]
0x1400bf9ee  add     r8, 1508h
0x1400bf9f5  add     rdx, 30h ; '0'
0x1400bf9f9  call    ParseWdiIndicationP2pSendRequestActionFrameCompleteFromIhv
0x1400bf9fe  mov     edi, eax
0x1400bfa00  test    eax, eax
0x1400bfa02  jz      short loc_1400BFA20
0x1400bfa04  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400bfa0b  jz      loc_1400BFCB4
0x1400bfa11  mov     r9d, 0B0h
0x1400bfa17  mov     dword ptr [rsp+0D0h+var_98], eax
0x1400bfa1b  jmp     loc_1400BFC4E
0x1400bfa20  call    Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline
0x1400bfa25  mov     r10, [rbx+218h]
0x1400bfa2c  test    eax, eax
0x1400bfa2e  jz      short loc_1400BFAA4
0x1400bfa30  mov     edx, [rbx+3E4h]
0x1400bfa36  mov     ecx, edx
0x1400bfa38  sub     ecx, 1
0x1400bfa3b  jz      short loc_1400BFA73
0x1400bfa3d  sub     ecx, 3
0x1400bfa40  jz      short loc_1400BFA62
0x1400bfa42  cmp     ecx, 2
0x1400bfa45  jnz     short loc_1400BFA9B
0x1400bfa47  mov     eax, [rbx+450h]
0x1400bfa4d  test    cl, al
0x1400bfa4f  jz      short loc_1400BFA9B
0x1400bfa51  movzx   r9d, word ptr [rbx+49Ah]
0x1400bfa59  movzx   eax, word ptr [rbx+49Ch]
0x1400bfa60  jmp     short loc_1400BFA82
0x1400bfa62  movzx   r9d, word ptr [rbx+41Ch]
0x1400bfa6a  movzx   eax, word ptr [rbx+41Eh]
0x1400bfa71  jmp     short loc_1400BFA82
0x1400bfa73  movzx   r9d, word ptr [rbx+3FEh]
0x1400bfa7b  movzx   eax, word ptr [rbx+400h]
0x1400bfa82  mov     r8d, dword ptr [rbp+57h+Size]
0x1400bfa86  mov     rcx, r10
0x1400bfa89  mov     dword ptr [rsp+0D0h+var_A8], edx
0x1400bfa8d  mov     rdx, [rbp+57h+Src]
0x1400bfa91  mov     word ptr [rsp+0D0h+var_B0], ax
0x1400bfa96  call    ?ValidateConfigurationTimeoutInternal@CP2PActionFrameHelpers@@CAXPEAVCAdapter@@PEBEKGGW4_WDI_P2P_ACTION_FRAME_TYPE@@@Z; CP2PActionFrameHelpers::ValidateConfigurationTimeoutInternal(CAdapter *,uchar const *,ulong,ushort,ushort,_WDI_P2P_ACTION_FRAME_TYPE)
0x1400bfa9b  lea     rsi, [rbx+244h]
0x1400bfaa2  jmp     short loc_1400BFB12
0x1400bfaa4  lea     rsi, [rbx+244h]
0x1400bfaab  mov     edx, [rsi]
0x1400bfaad  mov     ecx, edx
0x1400bfaaf  sub     ecx, 1
0x1400bfab2  jz      short loc_1400BFAEA
0x1400bfab4  sub     ecx, 3
0x1400bfab7  jz      short loc_1400BFAD9
0x1400bfab9  cmp     ecx, 2
0x1400bfabc  jnz     short loc_1400BFB12
0x1400bfabe  mov     eax, [rbx+2B0h]
0x1400bfac4  test    cl, al
0x1400bfac6  jz      short loc_1400BFB12
0x1400bfac8  movzx   r9d, word ptr [rbx+2FAh]
0x1400bfad0  movzx   eax, word ptr [rbx+2FCh]
0x1400bfad7  jmp     short loc_1400BFAF9
0x1400bfad9  movzx   r9d, word ptr [rbx+27Ch]
0x1400bfae1  movzx   eax, word ptr [rbx+27Eh]
0x1400bfae8  jmp     short loc_1400BFAF9
0x1400bfaea  movzx   r9d, word ptr [rbx+25Eh]
0x1400bfaf2  movzx   eax, word ptr [rbx+260h]
0x1400bfaf9  mov     r8d, dword ptr [rbp+57h+Size]
0x1400bfafd  mov     rcx, r10
0x1400bfb00  mov     dword ptr [rsp+0D0h+var_A8], edx
0x1400bfb04  mov     rdx, [rbp+57h+Src]
0x1400bfb08  mov     word ptr [rsp+0D0h+var_B0], ax
0x1400bfb0d  call    ?ValidateConfigurationTimeoutInternal@CP2PActionFrameHelpers@@CAXPEAVCAdapter@@PEBEKGGW4_WDI_P2P_ACTION_FRAME_TYPE@@@Z; CP2PActionFrameHelpers::ValidateConfigurationTimeoutInternal(CAdapter *,uchar const *,ulong,ushort,ushort,_WDI_P2P_ACTION_FRAME_TYPE)
0x1400bfb12  call    Feature_WiFiCx_TlvParserStaging__private_IsEnabledDeviceUsageNoInline
0x1400bfb17  test    eax, eax
0x1400bfb19  jz      short loc_1400BFB59
0x1400bfb1b  mov     ecx, [rbx+3E4h]
0x1400bfb21  sub     ecx, 1
0x1400bfb24  jz      short loc_1400BFB5D
0x1400bfb26  sub     ecx, 3
0x1400bfb29  jz      short loc_1400BFB3A
0x1400bfb2b  cmp     ecx, 2
0x1400bfb2e  jz      short loc_1400BFB3A
0x1400bfb30  mov     edi, 0C00000BBh
0x1400bfb35  jmp     loc_1400BFC71
0x1400bfb3a  mov     eax, 20h ; ' '
0x1400bfb3f  mov     [rbx+11C0h], r13d
0x1400bfb46  mov     esi, eax
0x1400bfb48  mov     [rbx+11C4h], eax
0x1400bfb4e  mov     eax, dword ptr [rbp+57h+Size]
0x1400bfb51  mov     [rbx+11C8h], eax
0x1400bfb57  jmp     short loc_1400BFB7A
0x1400bfb59  mov     ecx, [rsi]
0x1400bfb5b  jmp     short loc_1400BFB21
0x1400bfb5d  mov     eax, 18h
0x1400bfb62  mov     [rbx+11B8h], r13d
0x1400bfb69  mov     esi, eax
0x1400bfb6b  mov     [rbx+11BCh], eax
0x1400bfb71  mov     eax, dword ptr [rbp+57h+Size]
0x1400bfb74  mov     [rbx+11C0h], eax
0x1400bfb7a  lea     r12d, [rax+rsi]
0x1400bfb7e  mov     r15, rbx
0x1400bfb81  cmp     r12d, esi
0x1400bfb84  jnb     short loc_1400BFBB2
0x1400bfb86  mov     edi, 80000005h
0x1400bfb8b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400bfb92  jz      loc_1400BFCB4
0x1400bfb98  mov     r9d, 0B1h
0x1400bfb9e  mov     dword ptr [rsp+0D0h+var_98], 80000005h
0x1400bfba6  lea     r15, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400bfbad  jmp     loc_1400BFC4E
0x1400bfbb2  mov     ecx, r12d; unsigned __int64
0x1400bfbb5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400bfbba  mov     r14, rax
0x1400bfbbd  test    rax, rax
0x1400bfbc0  jnz     short loc_1400BFBEB
0x1400bfbc2  mov     edi, 0C000009Ah
0x1400bfbc7  lea     r14, WPP_RECORDER_INITIALIZED
0x1400bfbce  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400bfbd5  jz      loc_1400BFCB4
0x1400bfbdb  mov     r9d, 0B2h
0x1400bfbe1  mov     dword ptr [rsp+0D0h+var_98], 0C000009Ah
0x1400bfbe9  jmp     short loc_1400BFBA6
0x1400bfbeb  lea     rdx, [r15+11ACh]; Src
0x1400bfbf2  mov     r8, rsi; Size
0x1400bfbf5  mov     rcx, r14; void *
0x1400bfbf8  call    memmove
0x1400bfbfd  mov     eax, dword ptr [rbp+57h+Size]
0x1400bfc00  test    eax, eax
0x1400bfc02  jz      short loc_1400BFC14
0x1400bfc04  mov     rdx, [rbp+57h+Src]; Src
0x1400bfc08  lea     rcx, [rsi+r14]; void *
0x1400bfc0c  mov     r8d, eax; Size
0x1400bfc0f  call    memmove
0x1400bfc14  mov     [rbx+11A0h], r14
0x1400bfc1b  lea     r15, WPP_c7878cb29ed934641b2057fd7c6cbdda_Traceguids
0x1400bfc22  lea     r14, WPP_RECORDER_INITIALIZED
0x1400bfc29  mov     [rbx+1198h], r12d
0x1400bfc30  jmp     short loc_1400BFC71
0x1400bfc32  mov     edi, 0C0010015h
0x1400bfc37  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400bfc3e  jz      short loc_1400BFCB4
0x1400bfc40  mov     r9d, 0ADh
0x1400bfc46  mov     dword ptr [rsp+0D0h+var_98], 0C0010015h
0x1400bfc4e  mov     eax, [rbx+10h]
0x1400bfc51  mov     [rsp+0D0h+var_A0], eax
0x1400bfc55  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bfc5c  mov     dl, 2
0x1400bfc5e  mov     [rsp+0D0h+var_A8], rbx
0x1400bfc63  mov     [rsp+0D0h+var_B0], r15
0x1400bfc68  mov     rcx, [rcx+40h]
0x1400bfc6c  call    WPP_RECORDER_SF_qDD
0x1400bfc71  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400bfc78  jz      short loc_1400BFCB4
0x1400bfc7a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bfc81  cmp     byte ptr [rcx+29h], 5
0x1400bfc85  jnb     short loc_1400BFC8E
0x1400bfc87  cmp     [rcx+48h], r13w
0x1400bfc8c  jz      short loc_1400BFCB4
0x1400bfc8e  mov     eax, [rbx+10h]
0x1400bfc91  mov     r9d, 0B3h
0x1400bfc97  mov     rcx, [rcx+40h]
0x1400bfc9b  mov     dl, 5
0x1400bfc9d  mov     dword ptr [rsp+0D0h+var_98], edi
0x1400bfca1  mov     [rsp+0D0h+var_A0], eax
0x1400bfca5  mov     [rsp+0D0h+var_A8], rbx
0x1400bfcaa  mov     [rsp+0D0h+var_B0], r15
0x1400bfcaf  call    WPP_RECORDER_SF_qDD
0x1400bfcb4  lea     rcx, [rbp+57h+Size]; void *
0x1400bfcb8  call    ?Cleanup@?$ArrayOfElements@U_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER@WiFiCxTLVStaging@@@@QEAAXXZ; ArrayOfElements<WiFiCxTLVStaging::_WDI_P2P_AP_INFO_LIST_ENTRY_CONTAINER>::Cleanup(void)
0x1400bfcbd  mov     eax, edi
0x1400bfcbf  mov     rcx, [rbp+57h+var_50]
0x1400bfcc3  xor     rcx, rsp; StackCookie
0x1400bfcc6  call    __security_check_cookie
0x1400bfccb  add     rsp, 98h
0x1400bfcd2  pop     r15
0x1400bfcd4  pop     r14
0x1400bfcd6  pop     r13
0x1400bfcd8  pop     r12
0x1400bfcda  pop     rdi
0x1400bfcdb  pop     rsi
0x1400bfcdc  pop     rbx
0x1400bfcdd  pop     rbp
0x1400bfcde  retn
```
