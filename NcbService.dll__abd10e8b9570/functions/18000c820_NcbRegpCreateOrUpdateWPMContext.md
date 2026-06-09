# NcbRegpCreateOrUpdateWPMContext

- ea: `0x18000c820`
- end: `0x18000cacf`
- name: `NcbRegpCreateOrUpdateWPMContext`
- size: `687`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cae0`
- `0x18000d6dc`
- `0x18001cb50`

## callees

- `0x18000a160`
- `0x18000ad30`
- `0x18000c820`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`
- `0x18001e368`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000c938`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000c938`
- `NSI!NsiSetAllParameters` at `0x18000c9d0`
- `NSI!NsiSetAllParameters` at `0x18000c9d0`

## string_xrefs

- `0x18000ca30`: `NcbReg: NcbRegpCreateOrUpdateWPMContext finished with`

## pseudocode

```c
__int64 __fastcall NcbRegpCreateOrUpdateWPMContext(__int64 a1)
{
  __int128 v2; // xmm0
  bool v3; // zf
  __int64 v4; // rcx
  char v5; // al
  __int128 v6; // xmm0
  __int64 v7; // r8
  __int128 v8; // xmm0
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  unsigned int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  unsigned int v19; // ebx
  unsigned int v21; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v22[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h]
  _OWORD v24[8]; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+E0h] [rbp-20h]
  _BYTE v26[524]; // [rsp+E4h] [rbp-1Ch] BYREF
  __int64 v27; // [rsp+2F0h] [rbp+1F0h]
  int v28; // [rsp+2F8h] [rbp+1F8h]
  int v29; // [rsp+2FCh] [rbp+1FCh]
  __int128 v30; // [rsp+300h] [rbp+200h]
  __int128 v31; // [rsp+310h] [rbp+210h]
  char v32; // [rsp+320h] [rbp+220h]
  bool v33; // [rsp+321h] [rbp+221h]
  char v34; // [rsp+322h] [rbp+222h]
  bool v35; // [rsp+323h] [rbp+223h]
  int v36; // [rsp+324h] [rbp+224h]
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+330h] [rbp+230h] BYREF
  const wchar_t *v38; // [rsp+340h] [rbp+240h]
  __int64 v39; // [rsp+348h] [rbp+248h]
  int *v40; // [rsp+350h] [rbp+250h]
  __int64 v41; // [rsp+358h] [rbp+258h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
  }
  memset_0(v24, 0, 0x2C8u);
  v2 = *(_OWORD *)(a1 + 324);
  v3 = *(_BYTE *)(a1 + 296) == 0;
  v28 = *(_DWORD *)(a1 + 288);
  LOBYTE(v4) = !v3;
  v32 = *(_BYTE *)(a1 + 360);
  v22[0] = *(_DWORD *)(a1 + 196);
  v23 = *(_QWORD *)(a1 + 416);
  v29 = *(_DWORD *)(a1 + 292);
  v22[1] = 0;
  v30 = v2;
  v5 = NcbRegistrarEffectiveSlotTypeRequiresHardware(v4);
  v6 = *(_OWORD *)(a1 + 344);
  v7 = *(_QWORD *)(a1 + 240);
  v35 = *(_BYTE *)(a1 + 297) == 0;
  v34 = v5;
  v3 = *(_BYTE *)(a1 + 340) == 0;
  v36 = *(_DWORD *)(a1 + 304);
  v33 = v3;
  v27 = *(_QWORD *)(a1 + 400);
  v31 = v6;
  if ( v7 || !*(_BYTE *)(a1 + 232) )
    _o_wcscpy_s(v26, 260);
  v8 = *(_OWORD *)(a1 + 68);
  v9 = *(_OWORD *)(a1 + 84);
  v25 = *(_DWORD *)(a1 + 208);
  v24[0] = v8;
  v10 = *(_OWORD *)(a1 + 100);
  v24[1] = v9;
  v11 = *(_OWORD *)(a1 + 116);
  v24[2] = v10;
  v12 = *(_OWORD *)(a1 + 132);
  v24[3] = v11;
  v13 = *(_OWORD *)(a1 + 148);
  v24[4] = v12;
  v14 = *(_OWORD *)(a1 + 164);
  v24[5] = v13;
  v15 = *(_OWORD *)(a1 + 180);
  v24[6] = v14;
  v24[7] = v15;
  v16 = NsiSetAllParameters(1, 2, NPI_MS_TCP_MODULEID, 31, v22, 16, v24, 712);
  v19 = v16;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    v21 = v16;
    v38 = L"NcbReg: NcbRegpCreateOrUpdateWPMContext finished with";
    v39 = 108;
    v40 = (int *)&v21;
    v41 = 4;
    McGenEventWrite_EventWriteTransfer(v17, (const EVENT_DESCRIPTOR *)NcbApiStatus, v18, 3u, &v37);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v19);
  }
  return v19;
}

```

## disassembly

```asm
0x18000c820  push    rbp
0x18000c822  push    rbx
0x18000c823  push    rsi
0x18000c824  push    rdi
0x18000c825  lea     rbp, [rsp-278h]
0x18000c82d  sub     rsp, 378h
0x18000c834  mov     rax, cs:__security_cookie
0x18000c83b  xor     rax, rsp
0x18000c83e  mov     [rbp+290h+var_30], rax
0x18000c845  mov     rbx, rcx
0x18000c848  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c84f  lea     rdi, WPP_GLOBAL_Control
0x18000c856  cmp     rcx, rdi
0x18000c859  jz      short loc_18000C865
0x18000c85b  test    byte ptr [rcx+1Ch], 1
0x18000c85f  jnz     loc_18000CAAB
0x18000c865  xor     edx, edx; Val
0x18000c867  lea     rcx, [rsp+390h+var_330]; void *
0x18000c86c  mov     r8d, 2C8h; Size
0x18000c872  call    memset_0
0x18000c877  mov     eax, [rbx+120h]
0x18000c87d  xor     esi, esi
0x18000c87f  movups  xmm0, xmmword ptr [rbx+144h]
0x18000c886  cmp     [rbx+128h], sil
0x18000c88d  mov     [rbp+290h+var_98], eax
0x18000c893  movzx   eax, byte ptr [rbx+168h]
0x18000c89a  setnz   cl
0x18000c89d  mov     [rbp+290h+var_70], al
0x18000c8a3  mov     eax, [rbx+0C4h]
0x18000c8a9  mov     [rsp+390h+var_348], eax
0x18000c8ad  mov     rax, [rbx+1A0h]
0x18000c8b4  mov     [rsp+390h+var_340], rax
0x18000c8b9  mov     eax, [rbx+124h]
0x18000c8bf  mov     [rbp+290h+var_94], eax
0x18000c8c5  mov     [rsp+390h+var_344], esi
0x18000c8c9  movaps  [rbp+290h+var_90], xmm0
0x18000c8d0  call    NcbRegistrarEffectiveSlotTypeRequiresHardware
0x18000c8d5  cmp     [rbx+129h], sil
0x18000c8dc  movups  xmm0, xmmword ptr [rbx+158h]
0x18000c8e3  mov     r8, [rbx+0F0h]
0x18000c8ea  setz    [rbp+290h+var_6D]
0x18000c8f1  mov     [rbp+290h+var_6E], al
0x18000c8f7  cmp     [rbx+154h], sil
0x18000c8fe  mov     eax, [rbx+130h]
0x18000c904  mov     [rbp+290h+var_6C], eax
0x18000c90a  setz    [rbp+290h+var_6F]
0x18000c911  mov     rax, [rbx+190h]
0x18000c918  mov     [rbp+290h+var_A0], rax
0x18000c91f  movaps  [rbp+290h+var_80], xmm0
0x18000c926  test    r8, r8
0x18000c929  jz      loc_18000CA87
0x18000c92f  mov     edx, 104h
0x18000c934  lea     rcx, [rbp+290h+var_2AC]
0x18000c938  call    cs:__imp__o_wcscpy_s
0x18000c93e  movups  xmm0, xmmword ptr [rbx+44h]
0x18000c942  mov     eax, [rbx+0D0h]
0x18000c948  mov     r9d, 1Fh
0x18000c94e  movups  xmm1, xmmword ptr [rbx+54h]
0x18000c952  lea     r8, NPI_MS_TCP_MODULEID
0x18000c959  mov     [rbp+290h+var_2B0], eax
0x18000c95c  movaps  [rsp+390h+var_330], xmm0
0x18000c961  lea     rax, [rsp+390h+var_330]
0x18000c966  movups  xmm0, xmmword ptr [rbx+64h]
0x18000c96a  mov     edx, 2
0x18000c96f  mov     [rsp+390h+var_358], 2C8h
0x18000c977  movaps  [rsp+390h+var_320], xmm1
0x18000c97c  mov     ecx, 1
0x18000c981  movups  xmm1, xmmword ptr [rbx+74h]
0x18000c985  mov     [rsp+390h+var_360], rax
0x18000c98a  lea     rax, [rsp+390h+var_348]
0x18000c98f  movaps  [rbp+290h+var_310], xmm0
0x18000c993  movups  xmm0, xmmword ptr [rbx+84h]
0x18000c99a  mov     [rsp+390h+var_368], 10h
0x18000c9a2  movaps  [rbp+290h+var_300], xmm1
0x18000c9a6  movups  xmm1, xmmword ptr [rbx+94h]
0x18000c9ad  mov     [rsp+390h+var_370], rax
0x18000c9b2  movaps  [rbp+290h+var_2F0], xmm0
0x18000c9b6  movups  xmm0, xmmword ptr [rbx+0A4h]
0x18000c9bd  movaps  [rbp+290h+var_2E0], xmm1
0x18000c9c1  movups  xmm1, xmmword ptr [rbx+0B4h]
0x18000c9c8  movaps  [rbp+290h+var_2D0], xmm0
0x18000c9cc  movaps  [rbp+290h+var_2C0], xmm1
0x18000c9d0  call    cs:__imp_NsiSetAllParameters
0x18000c9d6  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000c9dd  mov     ebx, eax
0x18000c9df  jnz     short loc_18000CA30
0x18000c9e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9e8  cmp     rcx, rdi
0x18000c9eb  jnz     short loc_18000CA0A
0x18000c9ed  mov     eax, ebx
0x18000c9ef  mov     rcx, [rbp+290h+var_30]
0x18000c9f6  xor     rcx, rsp; StackCookie
0x18000c9f9  call    __security_check_cookie
0x18000c9fe  add     rsp, 378h
0x18000ca05  pop     rdi
0x18000ca06  pop     rsi
0x18000ca07  pop     rbx
0x18000ca08  pop     rbp
0x18000ca09  retn
0x18000ca0a  test    byte ptr [rcx+1Ch], 1
0x18000ca0e  jz      short loc_18000C9ED
0x18000ca10  cmp     byte ptr [rcx+19h], 6
0x18000ca14  jb      short loc_18000C9ED
0x18000ca16  mov     rcx, [rcx+10h]
0x18000ca1a  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000ca21  mov     edx, 9Ah
0x18000ca26  mov     r9d, ebx
0x18000ca29  call    WPP_SF_d
0x18000ca2e  jmp     short loc_18000C9ED
0x18000ca30  lea     rax, aNcbregNcbregpc; "NcbReg: NcbRegpCreateOrUpdateWPMContext"...
0x18000ca37  mov     [rsp+390h+var_350], ebx
0x18000ca3b  mov     [rbp+290h+var_50], rax
0x18000ca42  lea     rdx, NcbApiStatus
0x18000ca49  lea     rax, [rsp+390h+var_350]
0x18000ca4e  mov     [rbp+290h+var_48], 6Ch ; 'l'
0x18000ca59  mov     [rbp+290h+var_40], rax
0x18000ca60  mov     r9d, 3
0x18000ca66  lea     rax, [rbp+290h+var_60]
0x18000ca6d  mov     [rbp+290h+var_38], 4
0x18000ca78  mov     [rsp+390h+var_370], rax
0x18000ca7d  call    McGenEventWrite_EventWriteTransfer
0x18000ca82  jmp     loc_18000C9E1
0x18000ca87  cmp     [rbx+0E8h], sil
0x18000ca8e  jnz     loc_18000C93E
0x18000ca94  mov     r8d, [rbx+198h]
0x18000ca9b  lea     rax, g_cInboxClientAppNameTable
0x18000caa2  mov     r8, [rax+r8*8]
0x18000caa6  jmp     loc_18000C92F
0x18000caab  cmp     byte ptr [rcx+19h], 6
0x18000caaf  jb      loc_18000C865
0x18000cab5  mov     rcx, [rcx+10h]
0x18000cab9  lea     r8, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x18000cac0  mov     edx, 99h
0x18000cac5  call    WPP_SF_
0x18000caca  jmp     loc_18000C865
```
