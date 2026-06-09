# mmDrvInstall

- ea: `0x180001f30`
- end: `0x180002334`
- name: `mmDrvInstall`
- size: `1028`
- prototype: `UINT __stdcall(HDRVR hDriver, LPCWSTR wszDrvEntry, DRIVERMSGPROC drvMessage, UINT wFlags)`
- caller_count: `4`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180001dc4`
- `0x18000233c`
- `0x180002628`
- `0x180004534`

## callees

- `0x180001cb0`
- `0x180001f30`
- `0x180002a20`
- `0x180003460`
- `0x1800041d0`
- `0x180004350`
- `0x1800106c0`
- `0x18001c870`
- `0x180021010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180002101`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180002101`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800022dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800022dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800020b6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800020b6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800021e3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800021e3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002176`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180002176`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000227c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000227c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002291`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002299`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002291`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002299`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800022c6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800022c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002078`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180002078`

## pseudocode

```c
UINT __stdcall mmDrvInstall(HDRVR hDriver, LPCWSTR wszDrvEntry, DRIVERMSGPROC drvMessage, UINT wFlags)
{
  int v4; // r14d
  __int64 **v5; // rbx
  __int16 v6; // di
  HDRVR v8; // rsi
  int v9; // r13d
  __int64 *v10; // rdi
  unsigned int v11; // r15d
  int *v12; // r12
  const CHAR *v13; // r14
  __int64 v14; // rcx
  __int64 **v15; // rax
  _WORD *v16; // rax
  __int64 v17; // r8
  _WORD *v18; // r9
  __int64 v19; // rdx
  _WORD *v20; // rcx
  int v21; // eax
  __int64 *v22; // rdx
  __int16 v24; // [rsp+30h] [rbp-158h]
  _WORD pvData[128]; // [rsp+40h] [rbp-148h] BYREF

  v4 = 0;
  v24 = wFlags;
  v5 = 0;
  v6 = wFlags;
  v8 = hDriver;
  if ( hDriver && (wFlags & 0x4000) != 0 )
    hDriver = (HDRVR)DrvGetModuleHandle(hDriver);
  else
    v8 = 0;
  v9 = v6 & 0xF;
  switch ( v6 & 0xF )
  {
    case 1:
      v10 = (__int64 *)&waveindrvZ;
      v11 = 50;
      v12 = (int *)&wTotalWaveInDevs;
      v13 = szWidMessage;
      goto LABEL_13;
    case 2:
      v10 = &waveoutdrvZ;
      v11 = 3;
      v12 = (int *)&wTotalWaveOutDevs;
      v13 = szWodMessage;
      goto LABEL_13;
    case 3:
      v10 = &midiindrvZ;
      v11 = 53;
      v12 = &wTotalMidiInDevs;
      v13 = szMidMessage;
      goto LABEL_13;
    case 4:
      v10 = &midioutdrvZ;
      v12 = &wTotalMidiOutDevs;
      v13 = szModMessage;
      goto LABEL_12;
    case 5:
      v10 = &auxdrvZ;
      v11 = 3;
      v12 = &wTotalAuxDevs;
      v13 = szAuxMessage;
      goto LABEL_13;
    case 7:
      v10 = (__int64 *)&mixerdrvZ;
      v12 = &guTotalMixerDevs;
      v13 = szMxdMessage;
LABEL_12:
      v11 = 1;
LABEL_13:
      if ( !drvMessage )
      {
        if ( !hDriver )
          goto LABEL_38;
        drvMessage = (DRIVERMSGPROC)GetProcAddress((HMODULE)hDriver, v13);
        if ( !drvMessage )
          goto LABEL_38;
      }
      v14 = *v10;
      if ( (__int64 *)*v10 == v10 )
        goto LABEL_19;
      break;
    default:
      goto LABEL_40;
  }
  do
  {
    if ( *(DRIVERMSGPROC *)(v14 + 80) == drvMessage )
    {
LABEL_38:
      v4 = 0;
      goto LABEL_39;
    }
    v14 = *(_QWORD *)v14;
  }
  while ( (__int64 *)v14 != v10 );
LABEL_19:
  v15 = (__int64 **)HeapAlloc(hHeap, 8u, 0x120u);
  v5 = v15;
  if ( v15 )
  {
    v15[4] = (__int64 *)v8;
    *((_DWORD *)v15 + 23) = 1;
    v15[10] = (__int64 *)drvMessage;
    v15[13] = 0;
    v15[12] = 0;
    *((_DWORD *)v15 + 28) = (v24 & 0x8000 | 0x10000u) >> 14;
    _o_mbstowcs(v15 + 5, v13, 20);
    winmmGetPrivateProfileString(wszDrivers, wszDrvEntry, pvData, 0x80u);
    v16 = v5 + 20;
    v17 = 2147483646;
    v18 = pvData;
    v19 = 64;
    do
    {
      if ( !v17 )
        break;
      if ( !*v18 )
        break;
      *v16++ = *v18++;
      --v17;
      --v19;
    }
    while ( v19 );
    v20 = v16 - 1;
    if ( v19 )
      v20 = v16;
    *v20 = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)v5 + 3);
    v4 = 1;
    if ( v9 == 7 )
      ((void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))drvMessage)(0, 100, 0, 0, 0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix>::GetImpl'::`2'::impl)
      && CompareStringW(0x7Fu, 1u, (PCNZWCH)v5 + 80, -1, L"wdmaud2.drv", -1) == 2 )
    {
      *((_DWORD *)v5 + 28) |= 1u;
      v21 = 0;
LABEL_34:
      *((_DWORD *)v5 + 22) = v21;
      if ( ((_BYTE)v5[14] & 2) == 0 )
        *v12 += v21;
      v22 = (__int64 *)v10[1];
      v5[1] = v22;
      *v5 = v10;
      *v22 = (__int64)v5;
      (*v5)[1] = (__int64)v5;
      StringIdDict_Insert((struct _MMDRV *)v5);
      return 1;
    }
    v21 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))drvMessage)(0, v11, 0, 0, 0);
    if ( !HIWORD(v21) && (_WORD)v21 )
    {
      v21 = (unsigned __int16)v21;
      goto LABEL_34;
    }
  }
  else
  {
    v4 = 0;
  }
LABEL_39:
  v6 = v24;
LABEL_40:
  if ( v8 && (v6 & 0x2000) == 0 )
  {
    EnterCriticalSection(&DriverListCritSec);
    if ( (int)v8 <= cInstalledDrivers )
    {
      LeaveCriticalSection(&DriverListCritSec);
      if ( InternalBroadcastDriverMessage((unsigned int)v8, 4, 0, 0) )
        InternalFreeDriver((unsigned int)v8);
    }
    else
    {
      LeaveCriticalSection(&DriverListCritSec);
    }
  }
  if ( v4 )
    DeleteCriticalSection((LPCRITICAL_SECTION)v5 + 3);
  if ( v5 )
    HeapFree(hHeap, 0, v5);
  return 0;
}

```

## disassembly

```asm
0x180001f30  push    rbx
0x180001f32  push    rbp
0x180001f33  push    rsi
0x180001f34  push    rdi
0x180001f35  push    r13
0x180001f37  push    r14
0x180001f39  sub     rsp, 158h
0x180001f40  mov     rax, cs:__security_cookie
0x180001f47  xor     rax, rsp
0x180001f4a  mov     [rsp+188h+var_48], rax
0x180001f52  xor     r14d, r14d
0x180001f55  mov     [rsp+188h+var_158], r9d
0x180001f5a  xor     ebx, ebx
0x180001f5c  mov     [rsp+188h+lpValue], rdx
0x180001f61  mov     [rsp+188h+var_154], r14d
0x180001f66  mov     edi, r9d
0x180001f69  mov     rbp, r8
0x180001f6c  mov     rsi, rcx
0x180001f6f  test    rcx, rcx
0x180001f72  jz      short loc_180001F85
0x180001f74  bt      r9d, 0Eh
0x180001f79  jnb     short loc_180001F85
0x180001f7b  call    DrvGetModuleHandle
0x180001f80  mov     rcx, rax; hModule
0x180001f83  jmp     short loc_180001F87
0x180001f85  xor     esi, esi
0x180001f87  mov     r13d, edi
0x180001f8a  mov     [rsp+188h+arg_18], r12
0x180001f92  and     r13d, 0Fh
0x180001f96  mov     [rsp+188h+var_38], r15
0x180001f9e  lea     eax, [r13-1]; switch 7 cases
0x180001fa2  cmp     eax, 6
0x180001fa5  ja      def_180001FBC; jumptable 0000000180001FBC default case, case 6
0x180001fab  lea     rdx, __ImageBase
0x180001fb2  mov     eax, ds:(jpt_180001FBC - 180000000h)[rdx+rax*4]
0x180001fb9  add     rax, rdx
0x180001fbc  jmp     rax; switch jump
0x180001fbe  lea     rdi, waveoutdrvZ; jumptable 0000000180001FBC case 2
0x180001fc5  mov     r15d, 3
0x180001fcb  lea     r12, wTotalWaveOutDevs
0x180001fd2  lea     r14, szWodMessage; "wodMessage"
0x180001fd9  jmp     loc_180002067
0x180001fde  lea     rdi, waveindrvZ; jumptable 0000000180001FBC case 1
0x180001fe5  mov     r15d, 32h ; '2'
0x180001feb  lea     r12, wTotalWaveInDevs
0x180001ff2  lea     r14, szWidMessage; "widMessage"
0x180001ff9  jmp     short loc_180002067
0x180001ffb  lea     rdi, midioutdrvZ; jumptable 0000000180001FBC case 4
0x180002002  lea     r12, wTotalMidiOutDevs
0x180002009  lea     r14, szModMessage; "modMessage"
0x180002010  jmp     short loc_180002061
0x180002012  lea     rdi, midiindrvZ; jumptable 0000000180001FBC case 3
0x180002019  mov     r15d, 35h ; '5'
0x18000201f  lea     r12, wTotalMidiInDevs
0x180002026  lea     r14, szMidMessage; "midMessage"
0x18000202d  jmp     short loc_180002067
0x18000202f  lea     rdi, auxdrvZ; jumptable 0000000180001FBC case 5
0x180002036  mov     r15d, 3
0x18000203c  lea     r12, wTotalAuxDevs
0x180002043  lea     r14, szAuxMessage; "auxMessage"
0x18000204a  jmp     short loc_180002067
0x18000204c  lea     rdi, mixerdrvZ; jumptable 0000000180001FBC case 7
0x180002053  lea     r12, guTotalMixerDevs
0x18000205a  lea     r14, szMxdMessage; "mxdMessage"
0x180002061  mov     r15d, 1
0x180002067  test    rbp, rbp
0x18000206a  jnz     short loc_18000208A
0x18000206c  test    rcx, rcx
0x18000206f  jz      loc_180002263
0x180002075  mov     rdx, r14; lpProcName
0x180002078  call    cs:__imp_GetProcAddress
0x18000207e  mov     rbp, rax
0x180002081  test    rax, rax
0x180002084  jz      loc_180002263
0x18000208a  mov     rcx, [rdi]
0x18000208d  cmp     rcx, rdi
0x180002090  jz      short loc_1800020A4
0x180002092  cmp     [rcx+50h], rbp
0x180002096  jz      loc_180002263
0x18000209c  mov     rcx, [rcx]
0x18000209f  cmp     rcx, rdi
0x1800020a2  jnz     short loc_180002092
0x1800020a4  mov     rcx, cs:hHeap; hHeap
0x1800020ab  mov     edx, 8; dwFlags
0x1800020b0  mov     r8d, 120h; dwBytes
0x1800020b6  call    cs:__imp_HeapAlloc
0x1800020bc  mov     rbx, rax
0x1800020bf  test    rax, rax
0x1800020c2  jz      loc_18000225C
0x1800020c8  mov     [rax+20h], rsi
0x1800020cc  lea     rcx, [rbx+28h]
0x1800020d0  mov     dword ptr [rax+5Ch], 1
0x1800020d7  mov     r8d, 14h
0x1800020dd  xor     eax, eax
0x1800020df  mov     [rbx+50h], rbp
0x1800020e3  mov     [rbx+68h], rax
0x1800020e7  mov     rdx, r14
0x1800020ea  mov     [rbx+60h], rax
0x1800020ee  mov     eax, [rsp+188h+var_158]
0x1800020f2  and     eax, 8000h
0x1800020f7  bts     eax, 10h
0x1800020fb  shr     eax, 0Eh
0x1800020fe  mov     [rbx+70h], eax
0x180002101  call    cs:__imp__o_mbstowcs
0x180002107  mov     rdx, [rsp+188h+lpValue]; lpValue
0x18000210c  lea     r8, [rsp+188h+pvData]; pvData
0x180002111  mov     r9d, 80h
0x180002117  lea     rcx, wszDrivers; "DRIVERS32"
0x18000211e  call    winmmGetPrivateProfileString
0x180002123  lea     rax, [rbx+0A0h]
0x18000212a  mov     r8d, 7FFFFFFEh
0x180002130  lea     r9, [rsp+188h+pvData]
0x180002135  mov     edx, 40h ; '@'
0x18000213a  nop     word ptr [rax+rax+00h]
0x180002140  test    r8, r8
0x180002143  jz      short loc_180002162
0x180002145  movzx   ecx, word ptr [r9]
0x180002149  test    cx, cx
0x18000214c  jz      short loc_180002162
0x18000214e  mov     [rax], cx
0x180002151  add     r9, 2
0x180002155  add     rax, 2
0x180002159  dec     r8
0x18000215c  sub     rdx, 1
0x180002160  jnz     short loc_180002140
0x180002162  lea     rcx, [rax-2]
0x180002166  test    rdx, rdx
0x180002169  cmovnz  rcx, rax
0x18000216d  xor     eax, eax
0x18000216f  mov     [rcx], ax
0x180002172  lea     rcx, [rbx+78h]; lpCriticalSection
0x180002176  call    cs:__imp_InitializeCriticalSection
0x18000217c  mov     r14d, 1
0x180002182  cmp     r13d, 7
0x180002186  jnz     short loc_1800021A7
0x180002188  xor     r13d, r13d
0x18000218b  xor     r9d, r9d
0x18000218e  xor     r8d, r8d
0x180002191  mov     [rsp+188h+lpString2], r13
0x180002196  mov     edx, 64h ; 'd'
0x18000219b  xor     ecx, ecx
0x18000219d  mov     rax, rbp
0x1800021a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021a5  jmp     short loc_1800021AA
0x1800021a7  xor     r13d, r13d
0x1800021aa  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix>::GetImpl(void)'::`2'::impl
0x1800021b1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2WaveAPIFix>::__private_IsEnabled(void)
0x1800021b6  test    al, al
0x1800021b8  jz      short loc_1800021F7
0x1800021ba  lea     rax, String2; "wdmaud2.drv"
0x1800021c1  mov     [rsp+188h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800021c9  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800021cf  mov     [rsp+188h+lpString2], rax; lpString2
0x1800021d4  lea     r8, [rbx+0A0h]; lpString1
0x1800021db  mov     edx, r14d; dwCmpFlags
0x1800021de  mov     ecx, 7Fh; Locale
0x1800021e3  call    cs:__imp_CompareStringW
0x1800021e9  cmp     eax, 2
0x1800021ec  jnz     short loc_1800021F7
0x1800021ee  or      [rbx+70h], r14d
0x1800021f2  mov     eax, r13d
0x1800021f5  jmp     short loc_180002222
0x1800021f7  xor     r9d, r9d
0x1800021fa  mov     [rsp+188h+lpString2], r13
0x1800021ff  xor     r8d, r8d
0x180002202  mov     edx, r15d
0x180002205  xor     ecx, ecx
0x180002207  mov     rax, rbp
0x18000220a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000220f  mov     ecx, eax
0x180002211  shr     ecx, 10h
0x180002214  test    cx, cx
0x180002217  jnz     short loc_180002266
0x180002219  cmp     r13w, ax
0x18000221d  jz      short loc_180002266
0x18000221f  movzx   eax, ax
0x180002222  mov     ecx, 58h ; 'X'
0x180002227  mov     rdx, rbx
0x18000222a  mov     [rcx+rbx], eax
0x18000222d  test    byte ptr [rbx+70h], 2
0x180002231  jnz     short loc_180002237
0x180002233  add     [r12], eax
0x180002237  mov     rdx, [rdi+8]
0x18000223b  mov     rcx, rbx; struct _MMDRV *
0x18000223e  mov     [rbx+8], rdx
0x180002242  mov     [rbx], rdi
0x180002245  mov     [rdx], rbx
0x180002248  mov     rdx, [rbx]
0x18000224b  mov     [rdx+8], rbx
0x18000224f  call    ?StringIdDict_Insert@@YAXPEAU_MMDRV@@@Z; StringIdDict_Insert(_MMDRV *)
0x180002254  mov     eax, r14d
0x180002257  jmp     loc_1800022E5
0x18000225c  mov     r14d, [rsp+188h+var_154]
0x180002261  jmp     short loc_180002266
0x180002263  mov     r14d, ebx
0x180002266  mov     edi, [rsp+188h+var_158]
0x18000226a  test    rsi, rsi; jumptable 0000000180001FBC default case, case 6
0x18000226d  jz      short loc_1800022BD
0x18000226f  bt      edi, 0Dh
0x180002273  jb      short loc_1800022BD
0x180002275  lea     rcx, DriverListCritSec; lpCriticalSection
0x18000227c  call    cs:__imp_EnterCriticalSection
0x180002282  cmp     esi, cs:cInstalledDrivers
0x180002288  lea     rcx, DriverListCritSec; lpCriticalSection
0x18000228f  jle     short loc_180002299
0x180002291  call    cs:__imp_LeaveCriticalSection
0x180002297  jmp     short loc_1800022BD
0x180002299  call    cs:__imp_LeaveCriticalSection
0x18000229f  xor     r9d, r9d
0x1800022a2  xor     r8d, r8d
0x1800022a5  mov     edx, 4
0x1800022aa  mov     ecx, esi
0x1800022ac  call    InternalBroadcastDriverMessage
0x1800022b1  test    rax, rax
0x1800022b4  jz      short loc_1800022BD
0x1800022b6  mov     ecx, esi
0x1800022b8  call    InternalFreeDriver
0x1800022bd  test    r14d, r14d
0x1800022c0  jz      short loc_1800022CC
0x1800022c2  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800022c6  call    cs:__imp_DeleteCriticalSection
0x1800022cc  test    rbx, rbx
0x1800022cf  jz      short loc_1800022E3
0x1800022d1  mov     rcx, cs:hHeap; hHeap
0x1800022d8  mov     r8, rbx; lpMem
0x1800022db  xor     edx, edx; dwFlags
0x1800022dd  call    cs:__imp_HeapFree
0x1800022e3  xor     eax, eax
0x1800022e5  mov     r15, [rsp+188h+var_38]
0x1800022ed  mov     r12, [rsp+188h+arg_18]
0x1800022f5  mov     rcx, [rsp+188h+var_48]
0x1800022fd  xor     rcx, rsp; StackCookie
0x180002300  call    __security_check_cookie
0x180002305  add     rsp, 158h
0x18000230c  pop     r14
0x18000230e  pop     r13
0x180002310  pop     rdi
0x180002311  pop     rsi
0x180002312  pop     rbp
0x180002313  pop     rbx
0x180002314  retn
```
