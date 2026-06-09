# MbxDiagnostics::FlushSleepStudyData(bool)

- ea: `0x140025854`
- end: `0x140025d70`
- name: `?FlushSleepStudyData@MbxDiagnostics@@QEAAX_N@Z`
- size: `1308`
- prototype: `void __fastcall(MbxDiagnostics *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140025e40`

## callees

- `0x1400010b4`
- `0x140025854`
- `0x140026048`
- `0x1400263b0`
- `0x1400264b4`
- `0x140047e50`
- `0x140047e90`

## string_xrefs

- `0x140025a09`: `PacketServiceWakeCnt`
- `0x140025a4e`: `UnknownOrIncomingPacketWakeCnt`

## pseudocode

```c
void __fastcall MbxDiagnostics::FlushSleepStudyData(MbxDiagnostics *this, char a2)
{
  __int64 v4; // rsi
  int v5; // edx
  __int64 v6; // rdi
  int v7; // r8d
  int v8; // r9d
  ULONGLONG v9; // r12
  ULONGLONG v10; // r13
  __int64 v11; // r15
  __int64 v12; // rsi
  __int64 *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rcx
  int v17; // r14d
  int v18; // edx
  int v19; // r8d
  int v20; // r9d
  int *v21; // r8
  char v22; // bl
  int *v23; // rdx
  int v24; // r9d
  __int64 *v25; // rax
  __int64 v26; // r10
  __int64 v27; // r10
  __int64 v28; // rax
  __int64 v29; // rcx
  int v30; // ecx
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+80h] [rbp-80h] BYREF
  int v33; // [rsp+84h] [rbp-7Ch]
  int v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+8Ch] [rbp-74h]
  int v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+94h] [rbp-6Ch]
  int v38; // [rsp+98h] [rbp-68h]
  int v39; // [rsp+9Ch] [rbp-64h] BYREF
  int v40; // [rsp+A0h] [rbp-60h] BYREF
  int v41; // [rsp+A4h] [rbp-5Ch] BYREF
  int v42; // [rsp+A8h] [rbp-58h] BYREF
  int v43; // [rsp+ACh] [rbp-54h] BYREF
  int v44; // [rsp+B0h] [rbp-50h] BYREF
  int v45; // [rsp+B4h] [rbp-4Ch] BYREF
  int v46; // [rsp+B8h] [rbp-48h] BYREF
  int v47; // [rsp+BCh] [rbp-44h] BYREF
  __int64 v48; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-30h] BYREF
  struct _GUID v51; // [rsp+D8h] [rbp-28h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+F0h] [rbp-10h] BYREF
  __int64 *v53; // [rsp+110h] [rbp+10h]
  __int64 v54; // [rsp+118h] [rbp+18h]
  __int64 v55; // [rsp+120h] [rbp+20h]
  __int64 v56; // [rsp+128h] [rbp+28h]
  int *v57; // [rsp+130h] [rbp+30h]
  int v58; // [rsp+138h] [rbp+38h]
  int v59; // [rsp+13Ch] [rbp+3Ch]
  int *v60; // [rsp+140h] [rbp+40h]
  int v61; // [rsp+148h] [rbp+48h]
  int v62; // [rsp+14Ch] [rbp+4Ch]
  __int64 *v63; // [rsp+150h] [rbp+50h]
  __int64 v64; // [rsp+158h] [rbp+58h]
  __int64 *v65; // [rsp+160h] [rbp+60h]
  __int64 v66; // [rsp+168h] [rbp+68h]
  int *v67; // [rsp+170h] [rbp+70h]
  __int64 v68; // [rsp+178h] [rbp+78h]
  int *v69; // [rsp+180h] [rbp+80h]
  __int64 v70; // [rsp+188h] [rbp+88h]
  int *v71; // [rsp+190h] [rbp+90h]
  __int64 v72; // [rsp+198h] [rbp+98h]
  int *v73; // [rsp+1A0h] [rbp+A0h]
  __int64 v74; // [rsp+1A8h] [rbp+A8h]
  int *v75; // [rsp+1B0h] [rbp+B0h]
  __int64 v76; // [rsp+1B8h] [rbp+B8h]
  int *v77; // [rsp+1C0h] [rbp+C0h]
  __int64 v78; // [rsp+1C8h] [rbp+C8h]
  int *v79; // [rsp+1D0h] [rbp+D0h]
  __int64 v80; // [rsp+1D8h] [rbp+D8h]
  int *v81; // [rsp+1E0h] [rbp+E0h]
  __int64 v82; // [rsp+1E8h] [rbp+E8h]
  int *v83; // [rsp+1F0h] [rbp+F0h]
  __int64 v84; // [rsp+1F8h] [rbp+F8h]
  int *v85; // [rsp+200h] [rbp+100h]
  __int64 v86; // [rsp+208h] [rbp+108h]

  v4 = MEMORY[0xFFFFF78000000014];
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01031 + 1616))(
         WdfDriverGlobals,
         *((_QWORD *)this + 3),
         off_14005DF70);
  v9 = *(int *)(v6 + 1672);
  v10 = *(int *)(v6 + 1676);
  v11 = *(_QWORD *)(v6 + 1712);
  v39 = *(_DWORD *)(v6 + 1680);
  v32 = *(_DWORD *)(v6 + 1684);
  v38 = *(_DWORD *)(v6 + 1688);
  v37 = *(_DWORD *)(v6 + 1692);
  v36 = *(_DWORD *)(v6 + 1696);
  v35 = *(_DWORD *)(v6 + 1700);
  v34 = *(_DWORD *)(v6 + 1704);
  v33 = *(_DWORD *)(v6 + 1708);
  *(_OWORD *)(v6 + 1672) = 0;
  *(_OWORD *)(v6 + 1688) = 0;
  *(_OWORD *)(v6 + 1704) = 0;
  *(_QWORD *)(v6 + 1728) = MEMORY[0xFFFFF78000000014];
  if ( !a2 )
  {
    v12 = v4 - *((_QWORD *)this + 2);
    v13 = (__int64 *)((char *)this + 8);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF__guid_iii(WPP_GLOBAL_Control->DeviceExtension, v5, v7, v8);
    v14 = *((_QWORD *)this + 3);
    v51 = 0;
    v15 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01031 + 264))(WdfDriverGlobals, v14);
    v16 = *v13;
    *(_QWORD *)&v51.Data1 = v15;
    MbxDiagnostics::PublishSleepStudyCustomData(v16, &v51, L"RegisterStateWakeCnt", v9);
    MbxDiagnostics::PublishSleepStudyCustomData(*v13, &v51, L"SmsWakeCnt", v10);
    v17 = v39;
    MbxDiagnostics::PublishSleepStudyCustomData(*v13, &v51, L"UssdWakeCnt", v39);
    MbxDiagnostics::PublishSleepStudyCustomData(*v13, &v51, L"PacketServiceWakeCnt", v32);
    MbxDiagnostics::PublishSleepStudyCustomData(*v13, &v51, L"UiccWakeCnt", v38);
    MbxDiagnostics::PublishSleepStudyCustomData(*v13, &v51, L"ConnectStatusWakeCnt", v37);
    MbxDiagnostics::PublishSleepStudyCustomData(*v13, &v51, L"UnknownOrIncomingPacketWakeCnt", v36);
    MbxDiagnostics::PublishSleepStudyCustomData(*v13, &v51, L"IllegalWakeCnt", v35);
    MbxDiagnostics::PublishSleepStudyCustomData(*v13, &v51, L"PoweredRequestCntInDx", v34);
    MbxDiagnostics::PublishSleepStudyCustomData(*v13, &v51, L"PoweredRequestCntInD0", v33);
    if ( (unsigned int)dword_14005E0C8 > 5
      && (v18 = 0, (qword_14005E0D8 & 0x800000000000LL) != 0)
      && (qword_14005E0E0 & 0x800000000000LL) == qword_14005E0E0 )
    {
      v21 = (int *)(v6 + 410);
      v22 = v32;
      v23 = (int *)(v6 + 154);
      v39 = v33;
      v40 = v34;
      v41 = v35;
      v24 = 2;
      v42 = v36;
      v43 = v37;
      v44 = v38;
      v25 = *(__int64 **)(v6 + 1208);
      v45 = v17;
      v46 = v10;
      v47 = v9;
      v48 = v12;
      v49 = v11;
      v26 = *v25;
      v85 = &v39;
      v27 = v26 + 40;
      v50 = 0x1000000;
      v83 = &v40;
      v81 = &v41;
      v79 = &v42;
      v77 = &v43;
      v75 = &v44;
      v73 = &v32;
      v71 = &v45;
      v69 = &v46;
      v67 = &v47;
      v65 = &v48;
      v63 = &v49;
      v28 = -1;
      v86 = 4;
      v84 = 4;
      v82 = 4;
      v80 = 4;
      v78 = 4;
      v76 = 4;
      v74 = 4;
      v72 = 4;
      v70 = 4;
      v68 = 4;
      v66 = 8;
      v64 = 8;
      if ( v6 == -410 )
      {
        v21 = &dword_14004E69C;
        v30 = 2;
      }
      else
      {
        v29 = -1;
        do
          ++v29;
        while ( *((_WORD *)v21 + v29) );
        v30 = 2 * v29 + 2;
      }
      v60 = v21;
      v61 = v30;
      v62 = 0;
      if ( v6 == -154 )
      {
        v23 = &dword_14004E69C;
      }
      else
      {
        do
          ++v28;
        while ( *((_WORD *)v23 + v28) );
        v24 = 2 * v28 + 2;
      }
      v57 = v23;
      v53 = &v50;
      v58 = v24;
      v59 = 0;
      v55 = v27;
      v56 = 16;
      v54 = 8;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14005E0C8, (unsigned __int8 *)&unk_140058C68, 0, 0, 0x12u, &v52);
    }
    else
    {
      v22 = v32;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_llllllllll(
        WPP_GLOBAL_Control->DeviceExtension,
        v18,
        v19,
        v20,
        v31,
        v9,
        v10,
        v17,
        v22,
        v38,
        v37,
        v36,
        v35,
        v34,
        v33);
  }
}

```

## disassembly

```asm
0x140025854  push    rbp
0x140025856  push    rbx
0x140025857  push    rsi
0x140025858  push    rdi
0x140025859  push    r12
0x14002585b  push    r13
0x14002585d  push    r14
0x14002585f  push    r15
0x140025861  lea     rbp, [rsp-128h]
0x140025869  sub     rsp, 228h
0x140025870  mov     rax, cs:__security_cookie
0x140025877  xor     rax, rsp
0x14002587a  mov     [rbp+160h+var_50], rax
0x140025881  mov     bl, dl
0x140025883  mov     r14, rcx
0x140025886  mov     rsi, 0FFFFF78000000014h
0x140025890  mov     rsi, [rsi]
0x140025893  mov     rax, cs:WdfFunctions_01031
0x14002589a  mov     rdx, [rcx+18h]
0x14002589e  mov     r8, cs:off_14005DF70
0x1400258a5  mov     rcx, cs:WdfDriverGlobals
0x1400258ac  mov     rax, [rax+650h]
0x1400258b3  call    _guard_dispatch_icall
0x1400258b8  mov     rdi, rax
0x1400258bb  xorps   xmm0, xmm0
0x1400258be  movsxd  r12, dword ptr [rax+688h]
0x1400258c5  movsxd  r13, dword ptr [rax+68Ch]
0x1400258cc  mov     eax, [rax+690h]
0x1400258d2  mov     r15, [rdi+6B0h]
0x1400258d9  mov     [rbp+160h+var_1C4], eax
0x1400258dc  mov     eax, [rdi+694h]
0x1400258e2  mov     [rbp+160h+var_1E0], eax
0x1400258e5  mov     eax, [rdi+698h]
0x1400258eb  mov     [rbp+160h+var_1C8], eax
0x1400258ee  mov     eax, [rdi+69Ch]
0x1400258f4  mov     [rbp+160h+var_1CC], eax
0x1400258f7  mov     eax, [rdi+6A0h]
0x1400258fd  mov     [rbp+160h+var_1D0], eax
0x140025900  mov     eax, [rdi+6A4h]
0x140025906  mov     [rbp+160h+var_1D4], eax
0x140025909  mov     eax, [rdi+6A8h]
0x14002590f  mov     [rbp+160h+var_1D8], eax
0x140025912  mov     eax, [rdi+6ACh]
0x140025918  mov     [rbp+160h+var_1DC], eax
0x14002591b  movups  xmmword ptr [rdi+688h], xmm0
0x140025922  movups  xmmword ptr [rdi+698h], xmm0
0x140025929  movups  xmmword ptr [rdi+6A8h], xmm0
0x140025930  mov     rax, ds:0FFFFF78000000014h
0x14002593a  mov     [rdi+6C0h], rax
0x140025941  test    bl, bl
0x140025943  jnz     loc_140025D4C
0x140025949  sub     rsi, [r14+10h]
0x14002594d  lea     rax, WPP_RECORDER_INITIALIZED
0x140025954  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002595b  lea     rbx, [r14+8]
0x14002595f  jz      short loc_140025996
0x140025961  mov     rax, [rdi+4B8h]
0x140025968  mov     [rsp+260h+var_220], rsi
0x14002596d  mov     [rsp+260h+var_228], r15
0x140025972  mov     rcx, [rax]
0x140025975  mov     rax, [rbx]
0x140025978  add     rcx, 28h ; '('
0x14002597c  mov     [rsp+260h+var_230], rax
0x140025981  mov     [rsp+260h+var_238], rcx
0x140025986  mov     rcx, cs:WPP_GLOBAL_Control
0x14002598d  mov     rcx, [rcx+40h]
0x140025991  call    WPP_RECORDER_SF__guid_iii
0x140025996  mov     rax, cs:WdfFunctions_01031
0x14002599d  xorps   xmm0, xmm0
0x1400259a0  mov     rdx, [r14+18h]
0x1400259a4  mov     rcx, cs:WdfDriverGlobals
0x1400259ab  movups  xmmword ptr [rbp+160h+var_188.Data1], xmm0
0x1400259af  mov     rax, [rax+108h]
0x1400259b6  call    _guard_dispatch_icall
0x1400259bb  mov     rcx, [rbx]; unsigned __int64
0x1400259be  lea     r8, aRegisterstatew; "RegisterStateWakeCnt"
0x1400259c5  mov     r9, r12; unsigned __int64
0x1400259c8  mov     qword ptr [rbp+160h+var_188.Data1], rax
0x1400259cc  lea     rdx, [rbp+160h+var_188]; struct _GUID *
0x1400259d0  call    ?PublishSleepStudyCustomData@MbxDiagnostics@@CAJ_KPEBU_GUID@@PEBG0@Z; MbxDiagnostics::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)
0x1400259d5  mov     rcx, [rbx]; unsigned __int64
0x1400259d8  lea     r8, aSmswakecnt; "SmsWakeCnt"
0x1400259df  mov     r9, r13; unsigned __int64
0x1400259e2  lea     rdx, [rbp+160h+var_188]; struct _GUID *
0x1400259e6  call    ?PublishSleepStudyCustomData@MbxDiagnostics@@CAJ_KPEBU_GUID@@PEBG0@Z; MbxDiagnostics::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)
0x1400259eb  movsxd  r14, [rbp+160h+var_1C4]
0x1400259ef  lea     r8, aUssdwakecnt; "UssdWakeCnt"
0x1400259f6  mov     rcx, [rbx]; unsigned __int64
0x1400259f9  lea     rdx, [rbp+160h+var_188]; struct _GUID *
0x1400259fd  mov     r9, r14; unsigned __int64
0x140025a00  call    ?PublishSleepStudyCustomData@MbxDiagnostics@@CAJ_KPEBU_GUID@@PEBG0@Z; MbxDiagnostics::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)
0x140025a05  movsxd  r9, [rbp+160h+var_1E0]; unsigned __int64
0x140025a09  lea     r8, aPacketservicew; "PacketServiceWakeCnt"
0x140025a10  mov     rcx, [rbx]; unsigned __int64
0x140025a13  lea     rdx, [rbp+160h+var_188]; struct _GUID *
0x140025a17  call    ?PublishSleepStudyCustomData@MbxDiagnostics@@CAJ_KPEBU_GUID@@PEBG0@Z; MbxDiagnostics::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)
0x140025a1c  movsxd  r9, [rbp+160h+var_1C8]; unsigned __int64
0x140025a20  lea     r8, aUiccwakecnt; "UiccWakeCnt"
0x140025a27  mov     rcx, [rbx]; unsigned __int64
0x140025a2a  lea     rdx, [rbp+160h+var_188]; struct _GUID *
0x140025a2e  call    ?PublishSleepStudyCustomData@MbxDiagnostics@@CAJ_KPEBU_GUID@@PEBG0@Z; MbxDiagnostics::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)
0x140025a33  movsxd  r9, [rbp+160h+var_1CC]; unsigned __int64
0x140025a37  lea     r8, aConnectstatusw; "ConnectStatusWakeCnt"
0x140025a3e  mov     rcx, [rbx]; unsigned __int64
0x140025a41  lea     rdx, [rbp+160h+var_188]; struct _GUID *
0x140025a45  call    ?PublishSleepStudyCustomData@MbxDiagnostics@@CAJ_KPEBU_GUID@@PEBG0@Z; MbxDiagnostics::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)
0x140025a4a  movsxd  r9, [rbp+160h+var_1D0]; unsigned __int64
0x140025a4e  lea     r8, aUnknownorincom; "UnknownOrIncomingPacketWakeCnt"
0x140025a55  mov     rcx, [rbx]; unsigned __int64
0x140025a58  lea     rdx, [rbp+160h+var_188]; struct _GUID *
0x140025a5c  call    ?PublishSleepStudyCustomData@MbxDiagnostics@@CAJ_KPEBU_GUID@@PEBG0@Z; MbxDiagnostics::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)
0x140025a61  movsxd  r9, [rbp+160h+var_1D4]; unsigned __int64
0x140025a65  lea     r8, aIllegalwakecnt; "IllegalWakeCnt"
0x140025a6c  mov     rcx, [rbx]; unsigned __int64
0x140025a6f  lea     rdx, [rbp+160h+var_188]; struct _GUID *
0x140025a73  call    ?PublishSleepStudyCustomData@MbxDiagnostics@@CAJ_KPEBU_GUID@@PEBG0@Z; MbxDiagnostics::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)
0x140025a78  movsxd  r9, [rbp+160h+var_1D8]; unsigned __int64
0x140025a7c  lea     r8, aPoweredrequest; "PoweredRequestCntInDx"
0x140025a83  mov     rcx, [rbx]; unsigned __int64
0x140025a86  lea     rdx, [rbp+160h+var_188]; struct _GUID *
0x140025a8a  call    ?PublishSleepStudyCustomData@MbxDiagnostics@@CAJ_KPEBU_GUID@@PEBG0@Z; MbxDiagnostics::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)
0x140025a8f  movsxd  r9, [rbp+160h+var_1DC]; unsigned __int64
0x140025a93  lea     r8, aPoweredrequest_0; "PoweredRequestCntInD0"
0x140025a9a  mov     rcx, [rbx]; unsigned __int64
0x140025a9d  lea     rdx, [rbp+160h+var_188]; struct _GUID *
0x140025aa1  call    ?PublishSleepStudyCustomData@MbxDiagnostics@@CAJ_KPEBU_GUID@@PEBG0@Z; MbxDiagnostics::PublishSleepStudyCustomData(unsigned __int64,_GUID const *,ushort const *,unsigned __int64)
0x140025aa6  mov     eax, cs:dword_14005E0C8
0x140025aac  cmp     eax, 5
0x140025aaf  jbe     loc_140025CEC
0x140025ab5  mov     rcx, cs:qword_14005E0E0
0x140025abc  mov     rdx, 800000000000h
0x140025ac6  mov     rax, cs:qword_14005E0D8
0x140025acd  test    rdx, rax
0x140025ad0  jz      loc_140025CEC
0x140025ad6  mov     rax, rcx
0x140025ad9  and     rax, rdx
0x140025adc  cmp     rax, rcx
0x140025adf  jnz     loc_140025CEC
0x140025ae5  mov     eax, [rbp+160h+var_1DC]
0x140025ae8  lea     r8, [rdi+19Ah]
0x140025aef  mov     ebx, [rbp+160h+var_1E0]
0x140025af2  lea     rdx, [rdi+9Ah]
0x140025af9  mov     [rbp+160h+var_1C4], eax
0x140025afc  xor     r11d, r11d
0x140025aff  mov     eax, [rbp+160h+var_1D8]
0x140025b02  mov     [rbp+160h+var_1C0], eax
0x140025b05  mov     eax, [rbp+160h+var_1D4]
0x140025b08  mov     [rbp+160h+var_1BC], eax
0x140025b0b  lea     r9d, [r11+2]
0x140025b0f  mov     eax, [rbp+160h+var_1D0]
0x140025b12  mov     [rbp+160h+var_1B8], eax
0x140025b15  mov     eax, [rbp+160h+var_1CC]
0x140025b18  mov     [rbp+160h+var_1B4], eax
0x140025b1b  mov     eax, [rbp+160h+var_1C8]
0x140025b1e  mov     [rbp+160h+var_1B0], eax
0x140025b21  mov     rax, [rdi+4B8h]
0x140025b28  mov     [rbp+160h+var_1E0], ebx
0x140025b2b  mov     [rbp+160h+var_1AC], r14d
0x140025b2f  mov     [rbp+160h+var_1A8], r13d
0x140025b33  mov     [rbp+160h+var_1A4], r12d
0x140025b37  mov     [rbp+160h+var_1A0], rsi
0x140025b3b  mov     [rbp+160h+var_198], r15
0x140025b3f  mov     r10, [rax]
0x140025b42  lea     rax, [rbp+160h+var_1C4]
0x140025b46  mov     [rbp+160h+var_60], rax
0x140025b4d  add     r10, 28h ; '('
0x140025b51  lea     rax, [rbp+160h+var_1C0]
0x140025b55  mov     [rbp+160h+var_190], 1000000h
0x140025b5d  mov     [rbp+160h+var_70], rax
0x140025b64  lea     rax, [rbp+160h+var_1BC]
0x140025b68  mov     [rbp+160h+var_80], rax
0x140025b6f  lea     rax, [rbp+160h+var_1B8]
0x140025b73  mov     [rbp+160h+var_90], rax
0x140025b7a  lea     rax, [rbp+160h+var_1B4]
0x140025b7e  mov     [rbp+160h+var_A0], rax
0x140025b85  lea     rax, [rbp+160h+var_1B0]
0x140025b89  mov     [rbp+160h+var_B0], rax
0x140025b90  lea     rax, [rbp+160h+var_1E0]
0x140025b94  mov     [rbp+160h+var_C0], rax
0x140025b9b  lea     rax, [rbp+160h+var_1AC]
0x140025b9f  mov     [rbp+160h+var_D0], rax
0x140025ba6  lea     rax, [rbp+160h+var_1A8]
0x140025baa  mov     [rbp+160h+var_E0], rax
0x140025bb1  lea     rax, [rbp+160h+var_1A4]
0x140025bb5  mov     [rbp+160h+var_F0], rax
0x140025bb9  lea     rax, [rbp+160h+var_1A0]
0x140025bbd  mov     [rbp+160h+var_100], rax
0x140025bc1  lea     rax, [rbp+160h+var_198]
0x140025bc5  mov     [rbp+160h+var_110], rax
0x140025bc9  or      rax, 0FFFFFFFFFFFFFFFFh
0x140025bcd  mov     [rbp+160h+var_58], 4
0x140025bd8  mov     [rbp+160h+var_68], 4
0x140025be3  mov     [rbp+160h+var_78], 4
0x140025bee  mov     [rbp+160h+var_88], 4
0x140025bf9  mov     [rbp+160h+var_98], 4
0x140025c04  mov     [rbp+160h+var_A8], 4
0x140025c0f  mov     [rbp+160h+var_B8], 4
0x140025c1a  mov     [rbp+160h+var_C8], 4
0x140025c25  mov     [rbp+160h+var_D8], 4
0x140025c30  mov     [rbp+160h+var_E8], 4
0x140025c38  mov     [rbp+160h+var_F8], 8
0x140025c40  mov     [rbp+160h+var_108], 8
0x140025c48  test    r8, r8
0x140025c4b  jz      short loc_140025C63
0x140025c4d  mov     rcx, rax
0x140025c50  inc     rcx
0x140025c53  cmp     [r8+rcx*2], r11w
0x140025c58  jnz     short loc_140025C50
0x140025c5a  lea     ecx, ds:2[rcx*2]
0x140025c61  jmp     short loc_140025C6D
0x140025c63  lea     r8, dword_14004E69C
0x140025c6a  mov     ecx, r9d
0x140025c6d  mov     [rbp+160h+var_120], r8
0x140025c71  mov     [rbp+160h+var_118], ecx
0x140025c74  mov     [rbp+160h+var_114], r11d
0x140025c78  test    rdx, rdx
0x140025c7b  jz      short loc_140025C91
0x140025c7d  inc     rax
0x140025c80  cmp     [rdx+rax*2], r11w
0x140025c85  jnz     short loc_140025C7D
0x140025c87  lea     r9d, ds:2[rax*2]
0x140025c8f  jmp     short loc_140025C98
0x140025c91  lea     rdx, dword_14004E69C
0x140025c98  lea     rax, [rbp+160h+var_190]
0x140025c9c  mov     [rbp+160h+var_130], rdx
0x140025ca0  mov     [rbp+160h+var_150], rax
0x140025ca4  lea     rdx, unk_140058C68
0x140025cab  lea     rax, [rbp+160h+var_170]
0x140025caf  mov     [rbp+160h+var_128], r9d
0x140025cb3  mov     [rsp+260h+var_238], rax
0x140025cb8  lea     rcx, dword_14005E0C8
0x140025cbf  xor     r9d, r9d
0x140025cc2  mov     [rsp+260h+var_240], 12h
0x140025cca  xor     r8d, r8d
0x140025ccd  mov     [rbp+160h+var_124], r11d
0x140025cd1  mov     [rbp+160h+var_140], r10
0x140025cd5  mov     [rbp+160h+var_138], 10h
0x140025cdd  mov     [rbp+160h+var_148], 8
0x140025ce5  call    _tlgWriteTransfer_EtwWriteTransfer
0x140025cea  jmp     short loc_140025CEF
0x140025cec  mov     ebx, [rbp+160h+var_1E0]
0x140025cef  lea     rax, WPP_RECORDER_INITIALIZED
0x140025cf6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140025cfd  jz      short loc_140025D4C
0x140025cff  mov     eax, [rbp+160h+var_1DC]
0x140025d02  mov     rcx, cs:WPP_GLOBAL_Control
0x140025d09  mov     [rsp+260h+var_1F0], eax
0x140025d0d  mov     eax, [rbp+160h+var_1D8]
0x140025d10  mov     [rsp+260h+var_1F8], eax
0x140025d14  mov     eax, [rbp+160h+var_1D4]
0x140025d17  mov     rcx, [rcx+40h]
0x140025d1b  mov     [rsp+260h+var_200], eax
0x140025d1f  mov     eax, [rbp+160h+var_1D0]
0x140025d22  mov     [rsp+260h+var_208], eax
0x140025d26  mov     eax, [rbp+160h+var_1CC]
0x140025d29  mov     [rsp+260h+var_210], eax
0x140025d2d  mov     eax, [rbp+160h+var_1C8]
0x140025d30  mov     [rsp+260h+var_218], eax
0x140025d34  mov     dword ptr [rsp+260h+var_220], ebx
0x140025d38  mov     dword ptr [rsp+260h+var_228], r14d
0x140025d3d  mov     dword ptr [rsp+260h+var_230], r13d
0x140025d42  mov     dword ptr [rsp+260h+var_238], r12d
0x140025d47  call    WPP_RECORDER_SF_llllllllll
0x140025d4c  mov     rcx, [rbp+160h+var_50]
0x140025d53  xor     rcx, rsp; StackCookie
0x140025d56  call    __security_check_cookie
0x140025d5b  add     rsp, 228h
0x140025d62  pop     r15
0x140025d64  pop     r14
0x140025d66  pop     r13
0x140025d68  pop     r12
0x140025d6a  pop     rdi
0x140025d6b  pop     rsi
0x140025d6c  pop     rbx
0x140025d6d  pop     rbp
0x140025d6e  retn
```
