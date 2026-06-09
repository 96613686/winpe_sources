# Apx::ApfDevice::CreateApxDevice(void)

- ea: `0x18000ef00`
- end: `0x18000f2a5`
- name: `?CreateApxDevice@ApfDevice@Apx@@AEAAJXZ`
- size: `933`
- prototype: `__int64 __fastcall(unsigned __int64 this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f2ac`

## callees

- `0x180001d30`
- `0x1800027c8`
- `0x18000a12c`
- `0x18000d2f0`
- `0x18000d3c0`
- `0x18000ef00`

## import_xrefs

- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18000f20a`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18000f20a`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18000f23d`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18000f23d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f142`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f142`

## pseudocode

```c
__int64 __fastcall Apx::ApfDevice::CreateApxDevice(unsigned __int64 this)
{
  DEVPROPGUID fmtid; // xmm0
  DEVPROPID pid; // eax
  int v4; // eax
  int v5; // ecx
  __int64 v6; // rax
  bool v7; // zf
  unsigned int v8; // edi
  int v9; // edi
  _QWORD *v10; // rsi
  int v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v14[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v15; // [rsp+78h] [rbp-88h]
  const wchar_t *v16; // [rsp+80h] [rbp-80h]
  const wchar_t *v17; // [rsp+88h] [rbp-78h]
  __int64 v18; // [rsp+90h] [rbp-70h]
  __int128 v19; // [rsp+A0h] [rbp-60h] BYREF
  int v20; // [rsp+B0h] [rbp-50h]
  int v21; // [rsp+B4h] [rbp-4Ch]
  __int64 v22; // [rsp+B8h] [rbp-48h]
  int v23; // [rsp+C0h] [rbp-40h]
  int v24; // [rsp+C4h] [rbp-3Ch]
  char *v25; // [rsp+C8h] [rbp-38h]
  __int128 v26; // [rsp+D0h] [rbp-30h]
  int v27; // [rsp+E0h] [rbp-20h]
  int v28; // [rsp+E4h] [rbp-1Ch]
  __int64 v29; // [rsp+E8h] [rbp-18h]
  int v30; // [rsp+F0h] [rbp-10h]
  int v31; // [rsp+F4h] [rbp-Ch]
  char *v32; // [rsp+F8h] [rbp-8h]
  DEVPROPGUID v33; // [rsp+100h] [rbp+0h]
  DEVPROPID v34; // [rsp+110h] [rbp+10h]
  int v35; // [rsp+114h] [rbp+14h]
  __int64 v36; // [rsp+118h] [rbp+18h]
  int v37; // [rsp+120h] [rbp+20h]
  int v38; // [rsp+124h] [rbp+24h]
  char *v39; // [rsp+128h] [rbp+28h]
  DEVPROPGUID v40; // [rsp+130h] [rbp+30h]
  DEVPROPID v41; // [rsp+140h] [rbp+40h]
  int v42; // [rsp+144h] [rbp+44h]
  __int64 v43; // [rsp+148h] [rbp+48h]
  int v44; // [rsp+150h] [rbp+50h]
  int v45; // [rsp+154h] [rbp+54h]
  int *v46; // [rsp+158h] [rbp+58h]
  DEVPROPGUID v47; // [rsp+160h] [rbp+60h]
  DEVPROPID v48; // [rsp+170h] [rbp+70h]
  int v49; // [rsp+174h] [rbp+74h]
  __int64 v50; // [rsp+178h] [rbp+78h]
  int v51; // [rsp+180h] [rbp+80h]
  int v52; // [rsp+184h] [rbp+84h]
  char *v53; // [rsp+188h] [rbp+88h]
  __int128 v54; // [rsp+190h] [rbp+90h] BYREF
  OLECHAR sz[8]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v56; // [rsp+1B0h] [rbp+B0h]
  __int128 v57; // [rsp+1C0h] [rbp+C0h]
  _OWORD v58[2]; // [rsp+1D0h] [rbp+D0h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  v13 = 72;
  memset_0(v14, 0, 0x40u);
  v54 = *(_OWORD *)L"APXENUM#{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}";
  v56 = *(_OWORD *)L"x-xxxx-xxxx-xxxx-xxxxxxxxxxxx}";
  v58[0] = *(_OWORD *)L"-xxxxxxxxxxxx}";
  v20 = 1;
  *(_OWORD *)sz = *(_OWORD *)L"{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}";
  v25 = (char *)(this + 120);
  v19 = DEVPKEY_ApfDevice_IoLinkInterfaceId;
  v27 = 1;
  v57 = *(_OWORD *)L"xxx-xxxx-xxxxxxxxxxxx}";
  LOBYTE(v12) = 0;
  v26 = DEVPKEY_ApfDevice_OwnerProcessId;
  *(_OWORD *)((char *)v58 + 14) = *(_OWORD *)L"xxxxxx}";
  v21 = 0;
  v22 = 0;
  v23 = 13;
  v24 = 16;
  v28 = 0;
  v29 = 0;
  v30 = 7;
  v31 = 4;
  v32 = (char *)(this + 180);
  if ( *(_DWORD *)(this + 184) )
  {
    fmtid = DEVPKEY_Device_SessionId.fmtid;
    pid = DEVPKEY_Device_SessionId.pid;
  }
  else
  {
    fmtid = (DEVPROPGUID)DEVPKEY_ApfDevice_SessionId;
    pid = 1;
  }
  v34 = pid;
  v41 = DEVPKEY_Device_PresenceNotForDevice.pid;
  v46 = &v12;
  v48 = DEVPKEY_Device_FriendlyName.pid;
  v4 = 25;
  v33 = fmtid;
  v37 = 7;
  v39 = (char *)(this + 184);
  v5 = *(_DWORD *)(this + 1896);
  v40 = DEVPKEY_Device_PresenceNotForDevice.fmtid;
  if ( v5 == 1 )
    v4 = 18;
  v35 = 0;
  v51 = v4;
  v6 = -1;
  v36 = 0;
  v38 = 4;
  v42 = 0;
  v43 = 0;
  v44 = 17;
  v45 = 1;
  v47 = DEVPKEY_Device_FriendlyName.fmtid;
  v49 = 0;
  v50 = 0;
  do
    ++v6;
  while ( *(_WORD *)(this + 1900 + 2 * v6) );
  v7 = *(_BYTE *)(this + 32) >= 0;
  v52 = 2 * v6 + 2;
  v53 = (char *)(this + 1900);
  if ( !v7 )
    LOBYTE(v12) = -1;
  v8 = (v5 != 0) + 4;
  if ( StringFromGUID2((const GUID *const)(this + 152), sz, 39) )
  {
    v15 = 10;
    v14[0] = this + 328;
    v14[1] = *(_QWORD *)(this + 192);
    v18 = 0;
    v14[2] = L"APXENUM\\APXUNIT";
    v14[3] = this + 136;
    v16 = L"<description>";
    v17 = L"<location>";
    imp_ApxObjectReferenceActual(0, (Apx::ApfVerify *)~this);
    v10 = (_QWORD *)(this + 24);
    v9 = SwDeviceCreate(
           &v54,
           this + 1372,
           &v13,
           v8,
           &v19,
           Apx::ApfDevice::SwCreateApxDeviceCallback,
           this,
           this + 24,
           v12);
    if ( v9 >= 0 )
    {
      v9 = 0;
      goto LABEL_21;
    }
    imp_ApxObjectDereferenceActual(0, (Apx::ApfVerify *)~this);
  }
  else
  {
    v9 = -2147467259;
    v10 = (_QWORD *)(this + 24);
  }
  if ( *v10 )
  {
    SwDeviceClose(*v10);
    *v10 = 0;
  }
LABEL_21:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000ef00  mov     [rsp-8+arg_8], rbx
0x18000ef05  mov     [rsp-8+arg_10], rsi
0x18000ef0a  push    rbp
0x18000ef0b  push    rdi
0x18000ef0c  push    r13
0x18000ef0e  push    r14
0x18000ef10  push    r15
0x18000ef12  lea     rbp, [rsp-100h]
0x18000ef1a  sub     rsp, 200h
0x18000ef21  mov     rax, cs:__security_cookie
0x18000ef28  xor     rax, rsp
0x18000ef2b  mov     [rbp+120h+var_30], rax
0x18000ef32  mov     rbx, rcx
0x18000ef35  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef3c  lea     r13, WPP_GLOBAL_Control
0x18000ef43  cmp     rcx, r13
0x18000ef46  jz      short loc_18000EF69
0x18000ef48  test    byte ptr [rcx+1Ch], 1
0x18000ef4c  jz      short loc_18000EF69
0x18000ef4e  cmp     byte ptr [rcx+19h], 5
0x18000ef52  jb      short loc_18000EF69
0x18000ef54  mov     rcx, [rcx+10h]
0x18000ef58  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000ef5f  mov     edx, 2Ch ; ','
0x18000ef64  call    WPP_SF_
0x18000ef69  xor     edx, edx; Val
0x18000ef6b  mov     [rsp+220h+var_1D0], 48h ; 'H'
0x18000ef74  lea     rcx, [rsp+220h+var_1C8]; void *
0x18000ef79  lea     r8d, [rdx+40h]; Size
0x18000ef7d  call    memset_0
0x18000ef82  movaps  xmm0, xmmword ptr cs:aApxenumXxxxxxx; "APXENUM#{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxx"...
0x18000ef89  lea     rcx, [rbx+0B8h]
0x18000ef90  movaps  xmm1, xmmword ptr cs:aApxenumXxxxxxx+10h; "{xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}"
0x18000ef97  xor     r15d, r15d
0x18000ef9a  mov     eax, cs:dword_18002C870
0x18000efa0  movaps  [rbp+120h+var_90], xmm0
0x18000efa7  movaps  xmm0, xmmword ptr cs:aApxenumXxxxxxx+20h; "x-xxxx-xxxx-xxxx-xxxxxxxxxxxx}"
0x18000efae  lea     edx, [r15+7]
0x18000efb2  movaps  [rbp+120h+var_70], xmm0
0x18000efb9  lea     r8d, [r15+4]
0x18000efbd  movaps  xmm0, xmmword ptr cs:aApxenumXxxxxxx+40h; "-xxxxxxxxxxxx}"
0x18000efc4  movaps  xmmword ptr [rbp+120h+var_50], xmm0
0x18000efcb  movups  xmm0, cs:DEVPKEY_ApfDevice_IoLinkInterfaceId
0x18000efd2  mov     [rbp+120h+var_170], eax
0x18000efd5  lea     rax, [rbx+78h]
0x18000efd9  movaps  xmmword ptr [rbp+120h+sz], xmm1
0x18000efe0  movaps  xmm1, xmmword ptr cs:aApxenumXxxxxxx+30h; "xxx-xxxx-xxxxxxxxxxxx}"
0x18000efe7  mov     [rbp+120h+var_158], rax
0x18000efeb  mov     eax, cs:dword_18002C8A0
0x18000eff1  movaps  [rbp+120h+var_180], xmm0
0x18000eff5  movups  xmm0, cs:DEVPKEY_ApfDevice_OwnerProcessId
0x18000effc  mov     [rbp+120h+var_140], eax
0x18000efff  lea     rax, [rbx+0B4h]
0x18000f006  movaps  [rbp+120h+var_60], xmm1
0x18000f00d  movups  xmm1, xmmword ptr cs:aApxenumXxxxxxx+4Eh; "xxxxxx}"
0x18000f014  mov     byte ptr [rsp+220h+var_1E0], r15b
0x18000f019  movaps  [rbp+120h+var_150], xmm0
0x18000f01d  movups  xmmword ptr [rbp+120h+var_50+0Eh], xmm1
0x18000f024  mov     [rbp+120h+var_16C], r15d
0x18000f028  mov     [rbp+120h+var_168], r15
0x18000f02c  mov     [rbp+120h+var_160], 0Dh
0x18000f033  mov     [rbp+120h+var_15C], 10h
0x18000f03a  mov     [rbp+120h+var_13C], r15d
0x18000f03e  mov     [rbp+120h+var_138], r15
0x18000f042  mov     [rbp+120h+var_130], edx
0x18000f045  mov     [rbp+120h+var_12C], r8d
0x18000f049  mov     [rbp+120h+var_128], rax
0x18000f04d  cmp     [rcx], r15d
0x18000f050  jz      short loc_18000F061
0x18000f052  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_SessionId.fmtid.Data1
0x18000f059  mov     eax, cs:DEVPKEY_Device_SessionId.pid
0x18000f05f  jmp     short loc_18000F06E
0x18000f061  movups  xmm0, cs:DEVPKEY_ApfDevice_SessionId
0x18000f068  mov     eax, cs:dword_18002C7F8
0x18000f06e  mov     [rbp+120h+var_110], eax
0x18000f071  mov     eax, cs:DEVPKEY_Device_PresenceNotForDevice.pid
0x18000f077  mov     [rbp+120h+var_E0], eax
0x18000f07a  lea     rax, [rsp+220h+var_1E0]
0x18000f07f  mov     [rbp+120h+var_C8], rax
0x18000f083  mov     eax, cs:DEVPKEY_Device_FriendlyName.pid
0x18000f089  mov     [rbp+120h+var_B0], eax
0x18000f08c  mov     eax, 19h
0x18000f091  movaps  [rbp+120h+var_120], xmm0
0x18000f095  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_PresenceNotForDevice.fmtid.Data1
0x18000f09c  mov     [rbp+120h+var_100], edx
0x18000f09f  lea     edx, [rax-7]
0x18000f0a2  mov     [rbp+120h+var_F8], rcx
0x18000f0a6  mov     ecx, [rbx+768h]
0x18000f0ac  cmp     ecx, 1
0x18000f0af  movaps  [rbp+120h+var_F0], xmm0
0x18000f0b3  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_FriendlyName.fmtid.Data1
0x18000f0ba  cmovz   eax, edx
0x18000f0bd  mov     [rbp+120h+var_10C], r15d
0x18000f0c1  mov     [rbp+120h+var_A0], eax
0x18000f0c7  lea     rdx, [rbx+76Ch]
0x18000f0ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f0d2  mov     [rbp+120h+var_108], r15
0x18000f0d6  mov     [rbp+120h+var_FC], r8d
0x18000f0da  mov     [rbp+120h+var_DC], r15d
0x18000f0de  mov     [rbp+120h+var_D8], r15
0x18000f0e2  mov     [rbp+120h+var_D0], 11h
0x18000f0e9  mov     [rbp+120h+var_CC], 1
0x18000f0f0  movaps  [rbp+120h+var_C0], xmm0
0x18000f0f4  mov     [rbp+120h+var_AC], r15d
0x18000f0f8  mov     [rbp+120h+var_A8], r15
0x18000f0fc  inc     rax
0x18000f0ff  cmp     [rdx+rax*2], r15w
0x18000f104  jnz     short loc_18000F0FC
0x18000f106  test    byte ptr [rbx+20h], 80h
0x18000f10a  lea     eax, ds:2[rax*2]
0x18000f111  mov     [rbp+120h+var_9C], eax
0x18000f117  mov     [rbp+120h+var_98], rdx
0x18000f11e  jz      short loc_18000F125
0x18000f120  mov     byte ptr [rsp+220h+var_1E0], 0FFh
0x18000f125  neg     ecx
0x18000f127  lea     rdx, [rbp+120h+sz]; lpsz
0x18000f12e  lea     rcx, [rbx+98h]; rguid
0x18000f135  sbb     edi, edi
0x18000f137  neg     edi
0x18000f139  add     edi, r8d
0x18000f13c  mov     r8d, 27h ; '''; cchMax
0x18000f142  call    cs:__imp_StringFromGUID2
0x18000f148  test    eax, eax
0x18000f14a  jnz     short loc_18000F15A
0x18000f14c  mov     edi, 80004005h
0x18000f151  lea     rsi, [rbx+18h]
0x18000f155  jmp     loc_18000F235
0x18000f15a  lea     rax, [rbx+148h]
0x18000f161  mov     [rsp+220h+var_1A8], 0Ah
0x18000f169  mov     [rsp+220h+var_1C8], rax
0x18000f16e  mov     r14, rbx
0x18000f171  mov     rax, [rbx+0C0h]
0x18000f178  not     r14
0x18000f17b  mov     [rsp+220h+var_1C0], rax
0x18000f180  mov     r9d, 358h
0x18000f186  lea     rax, aApxenumApxunit; "APXENUM\\APXUNIT"
0x18000f18d  mov     [rbp+120h+var_190], r15
0x18000f191  mov     [rsp+220h+var_1B8], rax
0x18000f196  xor     r8d, r8d
0x18000f199  lea     rax, [rbx+88h]
0x18000f1a0  mov     rdx, r14; Apx::ApfVerify *
0x18000f1a3  mov     [rsp+220h+var_1B0], rax
0x18000f1a8  xor     ecx, ecx; this
0x18000f1aa  lea     rax, aDescription; "<description>"
0x18000f1b1  mov     [rbp+120h+var_1A0], rax
0x18000f1b5  lea     rax, aLocation; "<location>"
0x18000f1bc  mov     [rbp+120h+var_198], rax
0x18000f1c0  lea     rax, aOnecoreuapDriv_7; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x18000f1c7  mov     [rsp+220h+var_200], rax
0x18000f1cc  call    imp_ApxObjectReferenceActual
0x18000f1d1  lea     rax, ?SwCreateApxDeviceCallback@ApfDevice@Apx@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; Apx::ApfDevice::SwCreateApxDeviceCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x18000f1d8  mov     r9d, edi
0x18000f1db  lea     rsi, [rbx+18h]
0x18000f1df  mov     [rsp+220h+var_1E8], rsi
0x18000f1e4  lea     rdx, [rbx+55Ch]
0x18000f1eb  mov     [rsp+220h+var_1F0], rbx
0x18000f1f0  lea     r8, [rsp+220h+var_1D0]
0x18000f1f5  mov     [rsp+220h+var_1F8], rax
0x18000f1fa  lea     rcx, [rbp+120h+var_90]
0x18000f201  lea     rax, [rbp+120h+var_180]
0x18000f205  mov     [rsp+220h+var_200], rax
0x18000f20a  call    cs:__imp_SwDeviceCreate
0x18000f210  mov     edi, eax
0x18000f212  test    eax, eax
0x18000f214  jns     short loc_18000F248
0x18000f216  lea     rax, aOnecoreuapDriv_7; "onecoreuap\\drivers\\wdm\\audio\\backpl"...
0x18000f21d  mov     r9d, 365h
0x18000f223  xor     r8d, r8d
0x18000f226  mov     [rsp+220h+var_200], rax
0x18000f22b  mov     rdx, r14; Apx::ApfVerify *
0x18000f22e  xor     ecx, ecx; this
0x18000f230  call    imp_ApxObjectDereferenceActual
0x18000f235  mov     rcx, [rsi]
0x18000f238  test    rcx, rcx
0x18000f23b  jz      short loc_18000F24B
0x18000f23d  call    cs:__imp_SwDeviceClose
0x18000f243  mov     [rsi], r15
0x18000f246  jmp     short loc_18000F24B
0x18000f248  mov     edi, r15d
0x18000f24b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f252  cmp     rcx, r13
0x18000f255  jz      short loc_18000F278
0x18000f257  test    byte ptr [rcx+1Ch], 1
0x18000f25b  jz      short loc_18000F278
0x18000f25d  cmp     byte ptr [rcx+19h], 5
0x18000f261  jb      short loc_18000F278
0x18000f263  mov     rcx, [rcx+10h]
0x18000f267  lea     r8, WPP_3ec10e2928423f5854ad66ad2a4451e6_Traceguids
0x18000f26e  mov     edx, 2Dh ; '-'
0x18000f273  call    WPP_SF_
0x18000f278  mov     eax, edi
0x18000f27a  mov     rcx, [rbp+120h+var_30]
0x18000f281  xor     rcx, rsp; StackCookie
0x18000f284  call    __security_check_cookie
0x18000f289  lea     r11, [rsp+220h+var_20]
0x18000f291  mov     rbx, [r11+38h]
0x18000f295  mov     rsi, [r11+40h]
0x18000f299  mov     rsp, r11
0x18000f29c  pop     r15
0x18000f29e  pop     r14
0x18000f2a0  pop     r13
0x18000f2a2  pop     rdi
0x18000f2a3  pop     rbp
0x18000f2a4  retn
```
