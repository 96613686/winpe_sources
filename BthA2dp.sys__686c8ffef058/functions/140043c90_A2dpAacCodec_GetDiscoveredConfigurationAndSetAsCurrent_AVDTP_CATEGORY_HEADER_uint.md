# A2dpAacCodec::GetDiscoveredConfigurationAndSetAsCurrent(_AVDTP_CATEGORY_HEADER * *,uint &)

- ea: `0x140043c90`
- end: `0x14004420f`
- name: `?GetDiscoveredConfigurationAndSetAsCurrent@A2dpAacCodec@@UEAAJPEAPEAU_AVDTP_CATEGORY_HEADER@@AEAI@Z`
- size: `1407`
- prototype: `__int64 __fastcall(A2dpAacCodec *__hidden this, struct _AVDTP_CATEGORY_HEADER **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140003530`
- `0x140008810`
- `0x14000e690`
- `0x14000f570`
- `0x140010504`
- `0x14001f8bc`
- `0x1400396a4`
- `0x140043c90`
- `0x14005c870`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140043d59`
- `ntoskrnl!ExAllocatePool2` at `0x140043d59`

## pseudocode

```c
__int64 __fastcall A2dpAacCodec::GetDiscoveredConfigurationAndSetAsCurrent(
        A2dpAacCodec *this,
        struct _AVDTP_CATEGORY_HEADER **a2,
        unsigned int *a3)
{
  unsigned int *v3; // r13
  struct _AVDTP_CATEGORY_HEADER **v4; // r15
  PDEVICE_OBJECT v6; // rcx
  char v7; // si
  __int64 *v8; // r9
  __int64 v9; // r12
  __int64 Pool2; // rax
  __int64 v11; // r8
  char *v12; // rbx
  char v13; // dl
  char v14; // r8
  char v15; // r11
  int v16; // ebp
  int v17; // r14d
  char v18; // al
  char v19; // cl
  unsigned __int8 v20; // r8
  char v21; // r9
  unsigned __int8 v22; // r10
  char v23; // r8
  unsigned int v24; // edx
  unsigned int v25; // eax
  int v26; // edx
  __int64 v27; // r8
  char v28; // al
  _UNKNOWN **v29; // rdx
  unsigned int v30; // ebx
  __int64 v32; // [rsp+B0h] [rbp+8h] BYREF

  v3 = a3;
  v4 = a2;
  v6 = WPP_GLOBAL_Control;
  v7 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  v8 = WPP_241e11e0b94f348c3b57894f35631686_Traceguids;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      (_DWORD)a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      15,
      (__int64)WPP_241e11e0b94f348c3b57894f35631686_Traceguids,
      (char)this);
  if ( !v4 || *v4 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v6, a2, a3, v8);
  v9 = *(_BYTE *)(*((_QWORD *)this + 8) + 4LL) != 0 ? 12 : 10;
  Pool2 = ExAllocatePool2(64, v9, 1128354882);
  v32 = Pool2;
  v12 = (char *)Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = *(_QWORD *)((char *)this + 38);
    *(_WORD *)(Pool2 + 8) = *((_WORD *)this + 23);
    if ( *(_BYTE *)(*((_QWORD *)this + 8) + 4LL) )
    {
      *(_BYTE *)(Pool2 + 10) = 8;
      *((_BYTE *)this + 76) = 1;
    }
    v13 = *((_BYTE *)this + 53);
    v14 = *((_BYTE *)this + 54);
    v15 = *((_BYTE *)this + 55);
    v16 = *((unsigned __int8 *)this + 56);
    v17 = *((unsigned __int8 *)this + 57);
    *(_BYTE *)(Pool2 + 4) &= *((_BYTE *)this + 52);
    v18 = *(_BYTE *)(Pool2 + 4);
    v19 = *((_BYTE *)this + 32);
    if ( ((unsigned __int8)v19 & (unsigned __int8)v18) != 0 )
    {
      v12[4] = v19;
    }
    else if ( v18 >= 0 )
    {
      if ( (v18 & 0x40) != 0 )
        v12[4] = 64;
    }
    else
    {
      v12[4] = 0x80;
    }
    v12[5] &= v13;
    v12[6] &= v14 | 0xF;
    v20 = v12[6];
    v21 = *((_BYTE *)this + 33);
    v22 = *((_BYTE *)this + 34) >> 4;
    if ( ((v20 >> 4) & v22) == 0 && ((unsigned __int8)v21 & (unsigned __int8)v12[5]) == 0 )
    {
      if ( (v22 & 8) != 0 )
      {
        v12[5] = 0;
        v20 = v20 & 0xF | 0x80;
      }
      else
      {
        if ( (v21 & 1) == 0 )
          goto LABEL_28;
        v12[5] = 1;
        v20 &= 0xFu;
      }
    }
    else
    {
      v12[5] = v21;
      v20 = *((_BYTE *)this + 34) ^ (*((_BYTE *)this + 34) ^ v20) & 0xF;
    }
    v12[6] = v20;
LABEL_28:
    if ( (v20 & *((_BYTE *)this + 34) & 0xC) != 0 )
    {
      v12[6] = v20 ^ (v20 ^ *((_BYTE *)this + 34)) & 0xC;
LABEL_35:
      v12[7] &= v15 | 0x7F;
      v24 = v17 + ((v16 + ((v15 & 0x7F) << 8)) << 8);
      if ( v24 )
      {
        v25 = *((_DWORD *)this + 18);
        if ( v25 >= v24 )
          v25 = v17 + ((v16 + ((v15 & 0x7F) << 8)) << 8);
        *((_DWORD *)this + 18) = v25;
      }
      (*(void (__fastcall **)(A2dpAacCodec *, char *, _QWORD))(*(_QWORD *)this + 216LL))(
        this,
        v12,
        *((unsigned int *)this + 18));
      LOBYTE(v26) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v26,
          v27,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          5,
          17,
          (__int64)WPP_241e11e0b94f348c3b57894f35631686_Traceguids);
      }
      LOBYTE(v26) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_DDD(
          WPP_GLOBAL_Control->AttachedDevice,
          v26,
          v27,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          5,
          18,
          (__int64)WPP_241e11e0b94f348c3b57894f35631686_Traceguids,
          v12[4],
          ((unsigned __int8)v12[6] >> 2) & 3,
          (unsigned __int8)v12[7] >> 7);
      }
      LOBYTE(v26) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      if ( (_BYTE)v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_DD(
          WPP_GLOBAL_Control->AttachedDevice,
          v26,
          v27,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          5,
          19,
          (__int64)WPP_241e11e0b94f348c3b57894f35631686_Traceguids,
          v12[5],
          (unsigned __int8)v12[6] >> 4);
      }
      LOBYTE(v26) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
      LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( (_BYTE)v26 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_DDD(
          WPP_GLOBAL_Control->AttachedDevice,
          v26,
          v27,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          5,
          20,
          (__int64)WPP_241e11e0b94f348c3b57894f35631686_Traceguids,
          v12[7] & 0x7F,
          v12[8],
          v12[9]);
      v28 = (*(__int64 (__fastcall **)(A2dpAacCodec *, char *, __int64))(*(_QWORD *)this + 208LL))(this, v12, v27);
      if ( v28 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          v7 = 0;
        }
        v29 = &WPP_RECORDER_INITIALIZED;
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v29) = v7;
          WPP_RECORDER_AND_TRACE_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)v29,
            v11,
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            5,
            21,
            (__int64)WPP_241e11e0b94f348c3b57894f35631686_Traceguids,
            v28);
        }
        v30 = -1073741823;
      }
      else
      {
        *v4 = (struct _AVDTP_CATEGORY_HEADER *)v12;
        v30 = 0;
        *v3 = v9;
        v32 = 0;
      }
      goto LABEL_89;
    }
    if ( (v20 & 4) != 0 )
    {
      v23 = v20 & 0xF3 | 4;
    }
    else
    {
      if ( ((v20 >> 2) & 2) == 0 )
        goto LABEL_35;
      v23 = v20 & 0xF3 | 8;
    }
    v12[6] = v23;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    v7 = 0;
  }
  v29 = &WPP_RECORDER_INITIALIZED;
  LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v29) = v7;
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v29,
      v11,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      20,
      16,
      (__int64)WPP_241e11e0b94f348c3b57894f35631686_Traceguids,
      (char)this);
  }
  v30 = -1073741670;
LABEL_89:
  wil::details::unique_storage<wil::details::resource_policy<_AVDTP_CATEGORY_HEADER *,void (*)(void *),&void ExFreePool(void *),wistd::integral_constant<unsigned __int64,0>,_AVDTP_CATEGORY_HEADER *,_AVDTP_CATEGORY_HEADER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_AVDTP_CATEGORY_HEADER *,void (*)(void *),&void ExFreePool(void *),wistd::integral_constant<unsigned __int64,0>,_AVDTP_CATEGORY_HEADER *,_AVDTP_CATEGORY_HEADER *,0,std::nullptr_t>>(
    &v32,
    v29,
    v11);
  return v30;
}

```

## disassembly

```asm
0x140043c90  push    rbx
0x140043c92  push    rbp
0x140043c93  push    rsi
0x140043c94  push    rdi
0x140043c95  push    r12
0x140043c97  push    r13
0x140043c99  push    r14
0x140043c9b  push    r15
0x140043c9d  sub     rsp, 68h
0x140043ca1  mov     r13, r8
0x140043ca4  mov     r15, rdx
0x140043ca7  mov     rdi, rcx
0x140043caa  mov     rcx, cs:WPP_GLOBAL_Control
0x140043cb1  lea     rbp, WPP_GLOBAL_Control
0x140043cb8  mov     sil, 1
0x140043cbb  mov     r14d, 10h
0x140043cc1  cmp     rcx, rbp
0x140043cc4  jz      short loc_140043CD9
0x140043cc6  mov     eax, [rcx+2Ch]
0x140043cc9  test    r14b, al
0x140043ccc  jz      short loc_140043CD9
0x140043cce  cmp     byte ptr [rcx+29h], 4
0x140043cd2  jb      short loc_140043CD9
0x140043cd4  mov     dl, sil
0x140043cd7  jmp     short loc_140043CDB
0x140043cd9  xor     dl, dl
0x140043cdb  lea     rax, WPP_RECORDER_INITIALIZED
0x140043ce2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140043ce9  lea     r9, WPP_241e11e0b94f348c3b57894f35631686_Traceguids
0x140043cf0  setnz   r8b
0x140043cf4  test    dl, dl
0x140043cf6  jnz     short loc_140043CFD
0x140043cf8  test    r8b, r8b
0x140043cfb  jz      short loc_140043D28
0x140043cfd  mov     [rsp+0A8h+var_68], rdi
0x140043d02  mov     [rsp+0A8h+var_70], r9
0x140043d07  mov     r9, [rcx+40h]
0x140043d0b  mov     rcx, [rcx+18h]
0x140043d0f  mov     [rsp+0A8h+var_78], 0Fh
0x140043d16  mov     [rsp+0A8h+var_80], 5
0x140043d1e  mov     [rsp+0A8h+var_88], 4
0x140043d23  call    WPP_RECORDER_AND_TRACE_SF_q
0x140043d28  test    r15, r15
0x140043d2b  jz      short loc_140043D33
0x140043d2d  cmp     qword ptr [r15], 0
0x140043d31  jz      short loc_140043D38
0x140043d33  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140043d38  mov     rax, [rdi+40h]
0x140043d3c  mov     r8d, 43415442h
0x140043d42  mov     cl, [rax+4]
0x140043d45  neg     cl
0x140043d47  mov     ecx, 40h ; '@'
0x140043d4c  sbb     eax, eax
0x140043d4e  and     eax, 2
0x140043d51  add     eax, 0Ah
0x140043d54  mov     edx, eax
0x140043d56  mov     r12d, eax
0x140043d59  call    cs:__imp_ExAllocatePool2
0x140043d60  nop     dword ptr [rax+rax+00h]
0x140043d65  mov     [rsp+0A8h+arg_0], rax
0x140043d6d  mov     rbx, rax
0x140043d70  test    rax, rax
0x140043d73  jz      loc_14004417B
0x140043d79  movsd   xmm0, qword ptr [rdi+26h]
0x140043d7e  movsd   qword ptr [rax], xmm0
0x140043d82  movzx   eax, word ptr [rdi+2Eh]
0x140043d86  mov     [rbx+8], ax
0x140043d8a  mov     rax, [rdi+40h]
0x140043d8e  cmp     byte ptr [rax+4], 0
0x140043d92  jz      short loc_140043D9C
0x140043d94  mov     byte ptr [rbx+0Ah], 8
0x140043d98  mov     [rdi+4Ch], sil
0x140043d9c  mov     al, [rdi+34h]
0x140043d9f  mov     dl, [rdi+35h]
0x140043da2  mov     r8b, [rdi+36h]
0x140043da6  movzx   r11d, byte ptr [rdi+37h]
0x140043dab  movzx   ebp, byte ptr [rdi+38h]
0x140043daf  movzx   r14d, byte ptr [rdi+39h]
0x140043db4  and     [rbx+4], al
0x140043db7  mov     al, [rbx+4]
0x140043dba  mov     cl, [rdi+20h]
0x140043dbd  test    al, cl
0x140043dbf  jz      short loc_140043DC6
0x140043dc1  mov     [rbx+4], cl
0x140043dc4  jmp     short loc_140043DD8
0x140043dc6  test    al, al
0x140043dc8  jns     short loc_140043DD0
0x140043dca  mov     byte ptr [rbx+4], 80h
0x140043dce  jmp     short loc_140043DD8
0x140043dd0  test    al, 40h
0x140043dd2  jz      short loc_140043DD8
0x140043dd4  mov     byte ptr [rbx+4], 40h ; '@'
0x140043dd8  and     [rbx+5], dl
0x140043ddb  or      r8b, 0Fh
0x140043ddf  and     [rbx+6], r8b
0x140043de3  mov     r8b, [rbx+6]
0x140043de7  mov     r10b, [rdi+22h]
0x140043deb  mov     al, r8b
0x140043dee  mov     r9b, [rdi+21h]
0x140043df2  shr     al, 4
0x140043df5  shr     r10b, 4
0x140043df9  test    r10b, al
0x140043dfc  setz    cl
0x140043dff  test    [rbx+5], r9b
0x140043e03  setz    al
0x140043e06  test    al, cl
0x140043e08  jz      short loc_140043E2D
0x140043e0a  test    r10b, 8
0x140043e0e  jz      short loc_140043E1E
0x140043e10  and     r8b, 0Fh
0x140043e14  mov     byte ptr [rbx+5], 0
0x140043e18  or      r8b, 80h
0x140043e1c  jmp     short loc_140043E3E
0x140043e1e  test    sil, r9b
0x140043e21  jz      short loc_140043E42
0x140043e23  mov     [rbx+5], sil
0x140043e27  and     r8b, 0Fh
0x140043e2b  jmp     short loc_140043E3E
0x140043e2d  mov     [rbx+5], r9b
0x140043e31  mov     cl, [rdi+22h]
0x140043e34  xor     r8b, cl
0x140043e37  and     r8b, 0Fh
0x140043e3b  xor     r8b, cl
0x140043e3e  mov     [rbx+6], r8b
0x140043e42  mov     cl, [rdi+22h]
0x140043e45  mov     al, cl
0x140043e47  and     al, r8b
0x140043e4a  test    al, 0Ch
0x140043e4c  jz      short loc_140043E5C
0x140043e4e  xor     cl, r8b
0x140043e51  and     cl, 0Ch
0x140043e54  xor     cl, r8b
0x140043e57  mov     [rbx+6], cl
0x140043e5a  jmp     short loc_140043E81
0x140043e5c  mov     al, r8b
0x140043e5f  shr     al, 2
0x140043e62  test    sil, al
0x140043e65  jz      short loc_140043E71
0x140043e67  and     r8b, 0F7h
0x140043e6b  or      r8b, 4
0x140043e6f  jmp     short loc_140043E7D
0x140043e71  test    al, 2
0x140043e73  jz      short loc_140043E81
0x140043e75  and     r8b, 0FBh
0x140043e79  or      r8b, 8
0x140043e7d  mov     [rbx+6], r8b
0x140043e81  mov     edx, r11d
0x140043e84  mov     al, r11b
0x140043e87  and     edx, 7Fh
0x140043e8a  or      al, 7Fh
0x140043e8c  and     [rbx+7], al
0x140043e8f  shl     edx, 8
0x140043e92  add     edx, ebp
0x140043e94  shl     edx, 8
0x140043e97  add     edx, r14d
0x140043e9a  jz      short loc_140043EA7
0x140043e9c  mov     eax, [rdi+48h]
0x140043e9f  cmp     eax, edx
0x140043ea1  cmovnb  eax, edx
0x140043ea4  mov     [rdi+48h], eax
0x140043ea7  mov     rax, [rdi]
0x140043eaa  mov     rdx, rbx
0x140043ead  mov     r8d, [rdi+48h]
0x140043eb1  mov     rcx, rdi
0x140043eb4  mov     rax, [rax+0D8h]
0x140043ebb  call    _guard_dispatch_icall
0x140043ec0  mov     rcx, cs:WPP_GLOBAL_Control
0x140043ec7  lea     rbp, WPP_GLOBAL_Control
0x140043ece  mov     r14d, 10h
0x140043ed4  cmp     rcx, rbp
0x140043ed7  jz      short loc_140043EEC
0x140043ed9  mov     eax, [rcx+2Ch]
0x140043edc  test    r14b, al
0x140043edf  jz      short loc_140043EEC
0x140043ee1  cmp     byte ptr [rcx+29h], 4
0x140043ee5  jb      short loc_140043EEC
0x140043ee7  mov     dl, sil
0x140043eea  jmp     short loc_140043EEE
0x140043eec  xor     dl, dl
0x140043eee  lea     r9, WPP_RECORDER_INITIALIZED
0x140043ef5  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140043efc  setnz   r8b
0x140043f00  test    dl, dl
0x140043f02  jnz     short loc_140043F09
0x140043f04  test    r8b, r8b
0x140043f07  jz      short loc_140043F3D
0x140043f09  lea     r9, WPP_241e11e0b94f348c3b57894f35631686_Traceguids
0x140043f10  mov     [rsp+0A8h+var_70], r9
0x140043f15  mov     r9, [rcx+40h]
0x140043f19  mov     rcx, [rcx+18h]
0x140043f1d  mov     [rsp+0A8h+var_78], 11h
0x140043f24  mov     [rsp+0A8h+var_80], 5
0x140043f2c  mov     [rsp+0A8h+var_88], 4
0x140043f31  call    WPP_RECORDER_AND_TRACE_SF_
0x140043f36  lea     r9, WPP_RECORDER_INITIALIZED
0x140043f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x140043f44  cmp     rcx, rbp
0x140043f47  jz      short loc_140043F5C
0x140043f49  mov     eax, [rcx+2Ch]
0x140043f4c  test    r14b, al
0x140043f4f  jz      short loc_140043F5C
0x140043f51  cmp     byte ptr [rcx+29h], 4
0x140043f55  jb      short loc_140043F5C
0x140043f57  mov     dl, sil
0x140043f5a  jmp     short loc_140043F5E
0x140043f5c  xor     dl, dl
0x140043f5e  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140043f65  setnz   r8b
0x140043f69  test    dl, dl
0x140043f6b  jnz     short loc_140043F72
0x140043f6d  test    r8b, r8b
0x140043f70  jz      short loc_140043FCE
0x140043f72  movzx   r9d, byte ptr [rbx+6]
0x140043f77  movzx   eax, byte ptr [rbx+4]
0x140043f7b  movzx   r10d, byte ptr [rbx+7]
0x140043f80  shr     r9d, 2
0x140043f84  and     r9d, 3
0x140043f88  shr     r10d, 7
0x140043f8c  mov     [rsp+0A8h+var_58], r10d
0x140043f91  mov     [rsp+0A8h+var_60], r9d
0x140043f96  mov     r9, [rcx+40h]
0x140043f9a  mov     rcx, [rcx+18h]
0x140043f9e  mov     dword ptr [rsp+0A8h+var_68], eax
0x140043fa2  lea     rax, WPP_241e11e0b94f348c3b57894f35631686_Traceguids
0x140043fa9  mov     [rsp+0A8h+var_70], rax
0x140043fae  mov     [rsp+0A8h+var_78], 12h
0x140043fb5  mov     [rsp+0A8h+var_80], 5
0x140043fbd  mov     [rsp+0A8h+var_88], 4
0x140043fc2  call    WPP_RECORDER_AND_TRACE_SF_DDD
0x140043fc7  lea     r9, WPP_RECORDER_INITIALIZED
0x140043fce  mov     rcx, cs:WPP_GLOBAL_Control
0x140043fd5  cmp     rcx, rbp
0x140043fd8  jz      short loc_140043FED
0x140043fda  mov     eax, [rcx+2Ch]
0x140043fdd  test    r14b, al
0x140043fe0  jz      short loc_140043FED
0x140043fe2  cmp     byte ptr [rcx+29h], 4
0x140043fe6  jb      short loc_140043FED
0x140043fe8  mov     dl, sil
0x140043feb  jmp     short loc_140043FEF
0x140043fed  xor     dl, dl
0x140043fef  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140043ff6  setnz   r8b
0x140043ffa  test    dl, dl
0x140043ffc  jnz     short loc_140044003
0x140043ffe  test    r8b, r8b
0x140044001  jz      short loc_14004404D
0x140044003  movzx   r9d, byte ptr [rbx+6]
0x140044008  movzx   eax, byte ptr [rbx+5]
0x14004400c  shr     r9d, 4
0x140044010  mov     [rsp+0A8h+var_60], r9d
0x140044015  mov     r9, [rcx+40h]
0x140044019  mov     rcx, [rcx+18h]
0x14004401d  mov     dword ptr [rsp+0A8h+var_68], eax
0x140044021  lea     rax, WPP_241e11e0b94f348c3b57894f35631686_Traceguids
0x140044028  mov     [rsp+0A8h+var_70], rax
0x14004402d  mov     [rsp+0A8h+var_78], 13h
0x140044034  mov     [rsp+0A8h+var_80], 5
0x14004403c  mov     [rsp+0A8h+var_88], 4
0x140044041  call    WPP_RECORDER_AND_TRACE_SF_DD
0x140044046  lea     r9, WPP_RECORDER_INITIALIZED
0x14004404d  mov     rcx, cs:WPP_GLOBAL_Control
0x140044054  cmp     rcx, rbp
0x140044057  jz      short loc_14004406C
0x140044059  mov     eax, [rcx+2Ch]
0x14004405c  test    r14b, al
0x14004405f  jz      short loc_14004406C
0x140044061  cmp     byte ptr [rcx+29h], 4
0x140044065  jb      short loc_14004406C
0x140044067  mov     dl, sil
0x14004406a  jmp     short loc_14004406E
0x14004406c  xor     dl, dl
0x14004406e  cmp     cs:WPP_RECORDER_INITIALIZED, r9
0x140044075  setnz   r8b
0x140044079  test    dl, dl
0x14004407b  jnz     short loc_140044082
0x14004407d  test    r8b, r8b
0x140044080  jz      short loc_1400440CF
0x140044082  movzx   eax, byte ptr [rbx+9]
0x140044086  movzx   r9d, byte ptr [rbx+8]
0x14004408b  movzx   r10d, byte ptr [rbx+7]
0x140044090  mov     [rsp+0A8h+var_58], eax
0x140044094  and     r10d, 7Fh
0x140044098  mov     [rsp+0A8h+var_60], r9d
0x14004409d  lea     rax, WPP_241e11e0b94f348c3b57894f35631686_Traceguids
0x1400440a4  mov     r9, [rcx+40h]
0x1400440a8  mov     rcx, [rcx+18h]
0x1400440ac  mov     dword ptr [rsp+0A8h+var_68], r10d
0x1400440b1  mov     [rsp+0A8h+var_70], rax
0x1400440b6  mov     [rsp+0A8h+var_78], 14h
0x1400440bd  mov     [rsp+0A8h+var_80], 5
0x1400440c5  mov     [rsp+0A8h+var_88], 4
0x1400440ca  call    WPP_RECORDER_AND_TRACE_SF_DDD
0x1400440cf  mov     rax, [rdi]
0x1400440d2  mov     rdx, rbx
0x1400440d5  mov     rcx, rdi
0x1400440d8  mov     rax, [rax+0D0h]
0x1400440df  call    _guard_dispatch_icall
0x1400440e4  test    al, al
0x1400440e6  jz      short loc_140044164
  ... truncated ...
```
