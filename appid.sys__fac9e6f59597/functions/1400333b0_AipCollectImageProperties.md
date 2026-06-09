# AipCollectImageProperties

- ea: `0x1400333b0`
- end: `0x1400339b7`
- name: `AipCollectImageProperties`
- size: `1543`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x140002bd0`
- `0x140027784`
- `0x140034550`

## callees

- `0x140001550`
- `0x140001590`
- `0x140001ee0`
- `0x140002c88`
- `0x140002d10`
- `0x140002d84`
- `0x140006a20`
- `0x140025560`
- `0x140027820`
- `0x140027a0c`
- `0x140027ad4`
- `0x140028040`
- `0x14002a840`
- `0x14002ff50`
- `0x1400302b0`
- `0x1400333b0`
- `0x1400339c0`
- `0x140037ac0`

## import_xrefs

- `ntoskrnl!FsRtlGetFileSize` at `0x1400335da`
- `ntoskrnl!FsRtlGetFileSize` at `0x1400335da`

## pseudocode

```c
__int64 __fastcall AipCollectImageProperties(__int64 a1, _DWORD *a2, __int64 a3, _QWORD *a4)
{
  char v4; // si
  __int64 PerformanceCounter; // rbx
  int FullImagePath; // ebp
  __int64 v10; // rbx
  __int64 v11; // rbx
  unsigned int i; // ebx
  _DWORD *v13; // rsi
  __int64 v14; // rbx
  int v15; // eax
  __int64 j; // rbx
  __int64 v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rbx
  __int64 v21; // rbx
  __int64 v23[2]; // [rsp+50h] [rbp-A8h] BYREF
  char v24[80]; // [rsp+60h] [rbp-98h] BYREF

  v4 = 0;
  v23[0] = 0;
  if ( *(_QWORD *)(a1 + 8) )
  {
    PerformanceCounter = AiQueryPerformanceCounter(0, 0);
    FullImagePath = AiGetFullImagePath(
                      *(HANDLE *)(a1 + 8),
                      *(PFILE_OBJECT *)(a1 + 16),
                      a1 + 24,
                      (struct _UNICODE_STRING *)(a1 + 48),
                      (PUNICODE_STRING)(a1 + 80),
                      (_DWORD *)v23 + 1,
                      v23);
    AiUpdatePerfTime(qword_140019650, PerformanceCounter, 0);
    if ( FullImagePath < 0 )
      return (unsigned int)FullImagePath;
    v4 = v23[0];
    if ( (v23[0] & 4) != 0 || HIDWORD(v23[0]) == 2 || HIDWORD(v23[0]) == 51 )
      *(_DWORD *)(a1 + 104) = 1;
  }
  if ( *a2 )
  {
    v10 = AiQueryPerformanceCounter(0, 0);
    if ( (v4 & 0x10) == 0 )
    {
      if ( *(_QWORD *)(a1 + 88) )
      {
        FullImagePath = AiGetVolumeInfo(
                          (struct _UNICODE_STRING *)(a1 + 80),
                          *(void **)(*(_QWORD *)(a1 + 16) + 8LL),
                          (struct _UNICODE_STRING *)(a1 + 64),
                          (_DWORD *)(a1 + 108));
        if ( FullImagePath < 0 )
          return (unsigned int)FullImagePath;
      }
    }
    AiUpdatePerfTime(qword_140019660, v10, 0);
    v11 = AiQueryPerformanceCounter(0, 0);
    FullImagePath = AiInitializeSoftwarePathMacroList();
    if ( FullImagePath < 0 )
      return (unsigned int)FullImagePath;
    FullImagePath = AiConvertFullImagePathToMacroFormat(
                      a1,
                      (const UNICODE_STRING *)(a1 + 48),
                      *(const UNICODE_STRING **)a1,
                      (__int128 *)(a1 + 64),
                      (PCUNICODE_STRING)(a1 + 80),
                      *(_DWORD *)(a1 + 104),
                      *(_DWORD *)(a1 + 108));
    if ( FullImagePath < 0 )
      return (unsigned int)FullImagePath;
    if ( a4 )
    {
      FullImagePath = AipAddPathAttribute(a1);
      if ( FullImagePath < 0 )
        return (unsigned int)FullImagePath;
    }
    AiUpdatePerfTime(qword_140019670, v11, 0);
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 116); ++i )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_Z(
            WPP_GLOBAL_Control->AttachedDevice,
            10,
            WPP_613678cfb9bc3eb3d7e100c284ea9323_Traceguids,
            *(_QWORD *)(a1 + 128) + 16LL * i);
        }
      }
    }
  }
  if ( !*(_QWORD *)(a1 + 8) )
  {
    *(_DWORD *)(a1 + 200) = -2;
    v13 = a2 + 1;
    *(_DWORD *)(a1 + 360) = -2;
    FullImagePath = 0;
    *(_DWORD *)(a1 + 420) = -2;
LABEL_70:
    if ( a4 )
      *a4 = a1 + 664;
    *v13 = *(_DWORD *)(a1 + 420) >= 0;
    a2[3] &= *(_DWORD *)(a1 + 200) >= 0;
    a2[4] &= *(_DWORD *)(a1 + 200) >= 0;
    a2[5] &= *(_DWORD *)(a1 + 200) >= 0;
    return (unsigned int)FullImagePath;
  }
  FullImagePath = FsRtlGetFileSize(*(PFILE_OBJECT *)(a1 + 16), (PLARGE_INTEGER)(a1 + 96));
  if ( FullImagePath < 0 )
    return (unsigned int)FullImagePath;
  v14 = AiQueryPerformanceCounter(0, 0);
  AipQueryAttributeCache(a1, a2);
  AiUpdatePerfTime(qword_140019680, v14, 0);
  v15 = *(_DWORD *)(a1 + 200);
  if ( v15 < 0 )
    return (unsigned int)v15;
  if ( a4 )
  {
    for ( j = 0; (unsigned int)j < 3; j = (unsigned int)(j + 1) )
    {
      if ( a2[j + 3] )
      {
        FullImagePath = AipAddHashAttribute(a1, (unsigned int)j);
        if ( FullImagePath < 0 )
          return (unsigned int)FullImagePath;
      }
    }
  }
  if ( *(_DWORD *)(a1 + 304) == 20 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    v17 = 0;
    do
    {
      RtlStringCbPrintfA(
        &v24[(unsigned int)(2 * v17)],
        65LL - (unsigned int)(2 * v17),
        "%2.2x",
        *(unsigned __int8 *)(v17 + a1 + 236));
      v17 = (unsigned int)(v17 + 1);
    }
    while ( (unsigned int)v17 < *(_DWORD *)(a1 + 304) );
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, v18, v19, v24);
  }
  v13 = a2 + 1;
  if ( !a2[1] )
    goto LABEL_48;
  v20 = AiQueryPerformanceCounter(0, 0);
  if ( !*(_BYTE *)(a1 + 416) )
    *(_DWORD *)(a1 + 420) = AiGetTrustedPublisherName(*(HANDLE *)(a1 + 8), (PUNICODE_STRING)(a1 + 424));
  AiUpdatePerfTime(qword_1400196A0, v20, 0);
  v15 = *(_DWORD *)(a1 + 420);
  if ( v15 < 0 )
  {
    if ( v15 != -2 )
      return (unsigned int)v15;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_613678cfb9bc3eb3d7e100c284ea9323_Traceguids, a1 + 424);
  }
  if ( !*v13 || *(int *)(a1 + 420) < 0 )
  {
LABEL_48:
    if ( !a2[2] )
      goto LABEL_66;
  }
  v21 = AiQueryPerformanceCounter(0, 0);
  if ( *(int *)(a1 + 360) < 0 )
    *(_DWORD *)(a1 + 360) = AiGetImageVersionInfo(
                              *(_QWORD *)(a1 + 8),
                              *(_DWORD *)(a1 + 112),
                              *(_QWORD *)(a1 + 16),
                              (int)a1 + 364,
                              a1 + 368,
                              a1 + 372,
                              a1 + 376,
                              a1 + 384,
                              a1 + 400);
  AiUpdatePerfTime(qword_140019690, v21, 0);
  v15 = *(_DWORD *)(a1 + 360);
  if ( v15 < 0 )
  {
    if ( v15 == -2 )
      goto LABEL_66;
    return (unsigned int)v15;
  }
  if ( *(_QWORD *)(a1 + 392)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_613678cfb9bc3eb3d7e100c284ea9323_Traceguids, a1 + 384);
  }
  if ( *(_QWORD *)(a1 + 408) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_66;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_613678cfb9bc3eb3d7e100c284ea9323_Traceguids, a1 + 400);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_DDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        (unsigned __int16)*(_DWORD *)(a1 + 368),
        HIWORD(*(_DWORD *)(a1 + 364)),
        (unsigned __int16)*(_DWORD *)(a1 + 364),
        HIWORD(*(_DWORD *)(a1 + 368)),
        (unsigned __int16)*(_DWORD *)(a1 + 368));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_DDDD(
        WPP_GLOBAL_Control->AttachedDevice,
        16,
        (unsigned __int16)*(_DWORD *)(a1 + 376),
        HIWORD(*(_DWORD *)(a1 + 372)),
        (unsigned __int16)*(_DWORD *)(a1 + 372),
        HIWORD(*(_DWORD *)(a1 + 376)),
        (unsigned __int16)*(_DWORD *)(a1 + 376));
  }
LABEL_66:
  if ( a4 && a2[1] )
    FullImagePath = AipAddFQBNAttribute(a1);
  if ( FullImagePath >= 0 )
    goto LABEL_70;
  return (unsigned int)FullImagePath;
}

```

## disassembly

```asm
0x1400333b0  push    rbx
0x1400333b2  push    rbp
0x1400333b3  push    rsi
0x1400333b4  push    rdi
0x1400333b5  push    r14
0x1400333b7  push    r15
0x1400333b9  sub     rsp, 0C8h
0x1400333c0  mov     rax, cs:__security_cookie
0x1400333c7  xor     rax, rsp
0x1400333ca  mov     [rsp+0F8h+var_48], rax
0x1400333d2  xor     esi, esi
0x1400333d4  mov     dword ptr [rsp+0F8h+var_A8+4], 0
0x1400333dc  mov     r15, r9
0x1400333df  mov     r14, rdx
0x1400333e2  mov     rdi, rcx
0x1400333e5  mov     dword ptr [rsp+0F8h+var_A8], esi
0x1400333e9  cmp     [rcx+8], rsi
0x1400333ed  jz      short loc_140033468
0x1400333ef  xor     edx, edx
0x1400333f1  xor     ecx, ecx
0x1400333f3  call    AiQueryPerformanceCounter
0x1400333f8  mov     rdx, [rdi+10h]; FileObject
0x1400333fc  lea     rcx, [rsp+0F8h+var_A8]
0x140033401  mov     [rsp+0F8h+var_C8], rcx; __int64
0x140033406  lea     r9, [rdi+30h]
0x14003340a  lea     rcx, [rsp+0F8h+var_A8+4]
0x14003340f  mov     rbx, rax
0x140033412  mov     [rsp+0F8h+var_D0], rcx; __int64
0x140033417  lea     rax, [rdi+50h]
0x14003341b  mov     rcx, [rdi+8]; FileHandle
0x14003341f  lea     r8, [rdi+18h]
0x140033423  mov     [rsp+0F8h+DestinationString], rax; DestinationString
0x140033428  call    AiGetFullImagePath
0x14003342d  xor     r8d, r8d
0x140033430  lea     rcx, qword_140019650
0x140033437  mov     rdx, rbx
0x14003343a  mov     ebp, eax
0x14003343c  call    AiUpdatePerfTime
0x140033441  test    ebp, ebp
0x140033443  js      loc_140033987
0x140033449  mov     esi, dword ptr [rsp+0F8h+var_A8]
0x14003344d  test    sil, 4
0x140033451  jnz     short loc_140033461
0x140033453  mov     eax, dword ptr [rsp+0F8h+var_A8+4]
0x140033457  cmp     eax, 2
0x14003345a  jz      short loc_140033461
0x14003345c  cmp     eax, 33h ; '3'
0x14003345f  jnz     short loc_140033468
0x140033461  mov     dword ptr [rdi+68h], 1
0x140033468  cmp     dword ptr [r14], 0
0x14003346c  mov     [rsp+0F8h+var_38], r13
0x140033474  lea     r13, WPP_GLOBAL_Control
0x14003347b  jz      loc_14003359A
0x140033481  xor     edx, edx
0x140033483  xor     ecx, ecx
0x140033485  call    AiQueryPerformanceCounter
0x14003348a  mov     rbx, rax
0x14003348d  test    sil, 10h
0x140033491  jnz     short loc_1400334BD
0x140033493  cmp     qword ptr [rdi+58h], 0
0x140033498  jz      short loc_1400334BD
0x14003349a  mov     rdx, [rdi+10h]
0x14003349e  lea     r9, [rdi+6Ch]
0x1400334a2  lea     r8, [rdi+40h]
0x1400334a6  lea     rcx, [rdi+50h]
0x1400334aa  mov     rdx, [rdx+8]
0x1400334ae  call    AiGetVolumeInfo
0x1400334b3  mov     ebp, eax
0x1400334b5  test    eax, eax
0x1400334b7  js      loc_14003397F
0x1400334bd  xor     r8d, r8d
0x1400334c0  lea     rcx, qword_140019660
0x1400334c7  mov     rdx, rbx
0x1400334ca  call    AiUpdatePerfTime
0x1400334cf  xor     edx, edx
0x1400334d1  xor     ecx, ecx
0x1400334d3  call    AiQueryPerformanceCounter
0x1400334d8  mov     rbx, rax
0x1400334db  call    AiInitializeSoftwarePathMacroList
0x1400334e0  mov     ebp, eax
0x1400334e2  test    eax, eax
0x1400334e4  js      loc_14003397F
0x1400334ea  mov     eax, [rdi+6Ch]
0x1400334ed  lea     rcx, [rdi+50h]
0x1400334f1  mov     r8, [rdi]
0x1400334f4  lea     r9, [rdi+40h]
0x1400334f8  mov     dword ptr [rsp+0F8h+var_C8], eax
0x1400334fc  lea     rdx, [rdi+30h]
0x140033500  mov     eax, [rdi+68h]
0x140033503  mov     dword ptr [rsp+0F8h+var_D0], eax
0x140033507  mov     [rsp+0F8h+DestinationString], rcx
0x14003350c  mov     rcx, rdi
0x14003350f  call    AiConvertFullImagePathToMacroFormat
0x140033514  mov     ebp, eax
0x140033516  test    eax, eax
0x140033518  js      loc_14003397F
0x14003351e  test    r15, r15
0x140033521  jz      short loc_140033535
0x140033523  mov     rcx, rdi
0x140033526  call    AipAddPathAttribute
0x14003352b  mov     ebp, eax
0x14003352d  test    eax, eax
0x14003352f  js      loc_14003397F
0x140033535  xor     r8d, r8d
0x140033538  lea     rcx, qword_140019670
0x14003353f  mov     rdx, rbx
0x140033542  call    AiUpdatePerfTime
0x140033547  mov     rax, cs:WPP_GLOBAL_Control
0x14003354e  mov     ecx, [rax+2Ch]
0x140033551  test    cl, 10h
0x140033554  jz      short loc_14003359A
0x140033556  xor     ebx, ebx
0x140033558  cmp     [rdi+74h], ebx
0x14003355b  jbe     short loc_14003359A
0x14003355d  mov     rcx, cs:WPP_GLOBAL_Control
0x140033564  cmp     rcx, r13
0x140033567  jz      short loc_140033593
0x140033569  mov     eax, [rcx+2Ch]
0x14003356c  test    al, 10h
0x14003356e  jz      short loc_140033593
0x140033570  mov     rcx, [rcx+18h]
0x140033574  lea     r8, WPP_613678cfb9bc3eb3d7e100c284ea9323_Traceguids
0x14003357b  mov     r9d, ebx
0x14003357e  mov     edx, 0Ah
0x140033583  shl     r9, 4
0x140033587  add     r9, [rdi+80h]
0x14003358e  call    WPP_SF_Z
0x140033593  inc     ebx
0x140033595  cmp     ebx, [rdi+74h]
0x140033598  jb      short loc_14003355D
0x14003359a  cmp     qword ptr [rdi+8], 0
0x14003359f  mov     [rsp+0F8h+arg_10], r12
0x1400335a7  jnz     short loc_1400335D2
0x1400335a9  mov     dword ptr [rdi+0C8h], 0FFFFFFFEh
0x1400335b3  lea     rsi, [r14+4]
0x1400335b7  mov     dword ptr [rdi+168h], 0FFFFFFFEh
0x1400335c1  xor     ebp, ebp
0x1400335c3  mov     dword ptr [rdi+1A4h], 0FFFFFFFEh
0x1400335cd  jmp     loc_14003392E
0x1400335d2  mov     rcx, [rdi+10h]; FileObject
0x1400335d6  lea     rdx, [rdi+60h]; FileSize
0x1400335da  call    cs:__imp_FsRtlGetFileSize
0x1400335e1  nop     dword ptr [rax+rax+00h]
0x1400335e6  mov     ebp, eax
0x1400335e8  test    eax, eax
0x1400335ea  js      loc_140033977
0x1400335f0  xor     edx, edx
0x1400335f2  xor     ecx, ecx
0x1400335f4  call    AiQueryPerformanceCounter
0x1400335f9  mov     rdx, r14
0x1400335fc  mov     rcx, rdi
0x1400335ff  mov     rbx, rax
0x140033602  call    AipQueryAttributeCache
0x140033607  xor     r8d, r8d
0x14003360a  lea     rcx, qword_140019680
0x140033611  mov     rdx, rbx
0x140033614  call    AiUpdatePerfTime
0x140033619  mov     eax, [rdi+0C8h]
0x14003361f  test    eax, eax
0x140033621  js      loc_1400339B3
0x140033627  test    r15, r15
0x14003362a  jz      short loc_140033653
0x14003362c  xor     ebx, ebx
0x14003362e  cmp     ebx, 3
0x140033631  jnb     short loc_140033653
0x140033633  cmp     dword ptr [r14+rbx*4+0Ch], 0
0x140033639  jz      short loc_14003364F
0x14003363b  mov     edx, ebx
0x14003363d  mov     rcx, rdi
0x140033640  call    AipAddHashAttribute
0x140033645  mov     ebp, eax
0x140033647  test    eax, eax
0x140033649  js      loc_140033977
0x14003364f  inc     ebx
0x140033651  jmp     short loc_14003362E
0x140033653  cmp     dword ptr [rdi+130h], 14h
0x14003365a  jnz     short loc_1400336C0
0x14003365c  mov     rax, cs:WPP_GLOBAL_Control
0x140033663  mov     ecx, [rax+2Ch]
0x140033666  test    cl, 20h
0x140033669  jz      short loc_1400336C0
0x14003366b  xor     ebx, ebx
0x14003366d  movzx   r9d, byte ptr [rbx+rdi+0ECh]
0x140033676  lea     ecx, [rbx+rbx]
0x140033679  lea     rax, [rsp+0F8h+var_98]
0x14003367e  mov     edx, 41h ; 'A'
0x140033683  sub     rdx, rcx; cbDest
0x140033686  lea     r8, a22x; "%2.2x"
0x14003368d  add     rcx, rax; pszDest
0x140033690  call    RtlStringCbPrintfA
0x140033695  inc     ebx
0x140033697  cmp     ebx, [rdi+130h]
0x14003369d  jb      short loc_14003366D
0x14003369f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400336a6  cmp     rcx, r13
0x1400336a9  jz      short loc_1400336C0
0x1400336ab  mov     eax, [rcx+2Ch]
0x1400336ae  test    al, 20h
0x1400336b0  jz      short loc_1400336C0
0x1400336b2  mov     rcx, [rcx+18h]
0x1400336b6  lea     r9, [rsp+0F8h+var_98]
0x1400336bb  call    WPP_SF_s
0x1400336c0  cmp     dword ptr [r14+4], 0
0x1400336c5  lea     rsi, [r14+4]
0x1400336c9  jz      loc_140033767
0x1400336cf  xor     edx, edx
0x1400336d1  xor     ecx, ecx
0x1400336d3  call    AiQueryPerformanceCounter
0x1400336d8  cmp     byte ptr [rdi+1A0h], 0
0x1400336df  lea     r12, [rdi+1A8h]
0x1400336e6  mov     rbx, rax
0x1400336e9  jnz     short loc_140033707
0x1400336eb  mov     r9d, [rdi+70h]
0x1400336ef  mov     rdx, [rdi+10h]
0x1400336f3  mov     rcx, [rdi+8]; SourceHandle
0x1400336f7  mov     [rsp+0F8h+DestinationString], r12; DestinationString
0x1400336fc  call    AiGetTrustedPublisherName
0x140033701  mov     [rdi+1A4h], eax
0x140033707  xor     r8d, r8d
0x14003370a  lea     rcx, qword_1400196A0
0x140033711  mov     rdx, rbx
0x140033714  call    AiUpdatePerfTime
0x140033719  mov     eax, [rdi+1A4h]
0x14003371f  test    eax, eax
0x140033721  js      short loc_140033750
0x140033723  mov     rcx, cs:WPP_GLOBAL_Control
0x14003372a  cmp     rcx, r13
0x14003372d  jz      short loc_140033759
0x14003372f  mov     eax, [rcx+2Ch]
0x140033732  test    al, al
0x140033734  jns     short loc_140033759
0x140033736  mov     rcx, [rcx+18h]
0x14003373a  lea     r8, WPP_613678cfb9bc3eb3d7e100c284ea9323_Traceguids
0x140033741  mov     edx, 0Ch
0x140033746  mov     r9, r12
0x140033749  call    WPP_SF_Z
0x14003374e  jmp     short loc_140033759
0x140033750  cmp     eax, 0FFFFFFFEh
0x140033753  jnz     loc_1400339B3
0x140033759  cmp     dword ptr [rsi], 0
0x14003375c  jz      short loc_140033767
0x14003375e  cmp     dword ptr [rdi+1A4h], 0
0x140033765  jge     short loc_140033772
0x140033767  cmp     dword ptr [r14+8], 0
0x14003376c  jz      loc_140033914
0x140033772  xor     edx, edx
0x140033774  xor     ecx, ecx
0x140033776  call    AiQueryPerformanceCounter
0x14003377b  cmp     dword ptr [rdi+168h], 0
0x140033782  mov     rbx, rax
0x140033785  jge     short loc_1400337E0
0x140033787  lea     rdx, [rdi+178h]
0x14003378e  lea     rax, [rdi+190h]
0x140033795  mov     [rsp+0F8h+var_B8], rax
0x14003379a  lea     rcx, [rdi+180h]
0x1400337a1  mov     [rsp+0F8h+var_C0], rcx
0x1400337a6  lea     r8, [rdi+174h]
0x1400337ad  mov     rcx, [rdi+8]
0x1400337b1  lea     r10, [rdi+170h]
0x1400337b8  mov     [rsp+0F8h+var_C8], rdx
0x1400337bd  lea     r9, [rdi+16Ch]
0x1400337c4  mov     edx, [rdi+70h]
0x1400337c7  mov     [rsp+0F8h+var_D0], r8
0x1400337cc  mov     r8, [rdi+10h]
0x1400337d0  mov     [rsp+0F8h+DestinationString], r10
0x1400337d5  call    AiGetImageVersionInfo
0x1400337da  mov     [rdi+168h], eax
0x1400337e0  xor     r8d, r8d
0x1400337e3  lea     rcx, qword_140019690
0x1400337ea  mov     rdx, rbx
0x1400337ed  call    AiUpdatePerfTime
0x1400337f2  mov     eax, [rdi+168h]
0x1400337f8  test    eax, eax
0x1400337fa  js      loc_1400339AA
0x140033800  cmp     qword ptr [rdi+188h], 0
0x140033808  jz      short loc_140033839
0x14003380a  mov     rcx, cs:WPP_GLOBAL_Control
0x140033811  cmp     rcx, r13
0x140033814  jz      short loc_140033839
0x140033816  mov     eax, [rcx+2Ch]
0x140033819  test    al, 40h
0x14003381b  jz      short loc_140033839
0x14003381d  mov     rcx, [rcx+18h]
0x140033821  lea     r9, [rdi+180h]
0x140033828  mov     edx, 0Dh
0x14003382d  lea     r8, WPP_613678cfb9bc3eb3d7e100c284ea9323_Traceguids
0x140033834  call    WPP_SF_Z
0x140033839  cmp     qword ptr [rdi+198h], 0
0x140033841  jz      short loc_140033876
0x140033843  mov     rcx, cs:WPP_GLOBAL_Control
0x14003384a  cmp     rcx, r13
0x14003384d  jz      loc_140033914
0x140033853  mov     eax, [rcx+2Ch]
0x140033856  test    al, 40h
0x140033858  jz      short loc_140033876
0x14003385a  mov     rcx, [rcx+18h]
0x14003385e  lea     r9, [rdi+190h]
0x140033865  mov     edx, 0Eh
0x14003386a  lea     r8, WPP_613678cfb9bc3eb3d7e100c284ea9323_Traceguids
0x140033871  call    WPP_SF_Z
  ... truncated ...
```
