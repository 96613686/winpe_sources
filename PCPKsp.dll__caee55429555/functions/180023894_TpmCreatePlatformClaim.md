# TpmCreatePlatformClaim

- ea: `0x180023894`
- end: `0x180023f8f`
- name: `TpmCreatePlatformClaim`
- size: `1787`
- prototype: `__int64 __fastcall(int, int, int, int, int, void *Destination, rsize_t DestinationSize, __int64, int)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x180050bb0`

## callees

- `0x180010c90`
- `0x1800113f0`
- `0x180015660`
- `0x1800157c0`
- `0x18001c308`
- `0x180022504`
- `0x180023894`
- `0x180023f98`
- `0x1800249d8`
- `0x180024ef0`
- `0x180025344`
- `0x180029260`
- `0x18002aba0`
- `0x180037b20`
- `0x18003bad0`
- `0x18006a9f8`
- `0x18006bc88`
- `0x1800764d0`
- `0x180094714`
- `0x1800947cc`
- `0x180097984`
- `0x1800b9edc`
- `0x1800ba060`

## import_xrefs

- `tbs!Tbsi_GetDeviceInfo` at `0x180023dbc`
- `tbs!Tbsi_GetDeviceInfo` at `0x180023dbc`

## string_xrefs

- `0x1800238ec`: `TpmCreatePlatformClaim`
- `0x1800239c9`: `Flags must be create boot claim, get boot claim, or 0. Flags were: %I32u`
- `0x180023a02`: `Cannot create & get boot claim at the same time`
- `0x180023d9f`: `To create or use the static quote, the PCR mask must be all 24 PCRs and nonce must be empty`
- `0x180023b6a`: `Failed to get native key handle when comparing platform claims. hr: 0x%X`
- `0x180023bc8`: `Failed to get name of key when comparing platform claims. hr: 0x%X`
- `0x180023d5c`: `This platform has been resumed from hibernate, and can no longer create a platform boot claim. A reboot is required to generate a new platform boot claim.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall TpmCreatePlatformClaim(
        unsigned __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        unsigned __int8 *a4,
        int a5,
        unsigned int *Destination,
        rsize_t DestinationSize,
        unsigned int *a8,
        int a9)
{
  unsigned int v13; // ebx
  unsigned int v15; // r13d
  char v16; // r14
  __int64 v17; // rdx
  __int64 v18; // r11
  const unsigned __int8 *v19; // r10
  unsigned int v20; // r11d
  const unsigned __int8 *v21; // r10
  unsigned int v22; // r11d
  int KeyProperty; // eax
  int v24; // eax
  int v25; // eax
  const unsigned __int8 *v26; // r10
  unsigned int v27; // r11d
  const unsigned __int8 *v28; // r10
  unsigned int v29; // r11d
  int active; // eax
  unsigned int v31; // eax
  size_t Size; // [rsp+28h] [rbp-4C0h]
  size_t Sizea; // [rsp+28h] [rbp-4C0h]
  int DeviceInfo; // [rsp+50h] [rbp-498h] BYREF
  unsigned int v35; // [rsp+54h] [rbp-494h] BYREF
  unsigned int v36; // [rsp+58h] [rbp-490h] BYREF
  unsigned int v37; // [rsp+5Ch] [rbp-48Ch] BYREF
  unsigned __int8 *v38; // [rsp+60h] [rbp-488h] BYREF
  unsigned int v39; // [rsp+68h] [rbp-480h] BYREF
  unsigned int *v40; // [rsp+70h] [rbp-478h] BYREF
  unsigned __int8 *Src; // [rsp+78h] [rbp-470h] BYREF
  __int64 v42; // [rsp+80h] [rbp-468h]
  void *Source[2]; // [rsp+90h] [rbp-458h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-448h]
  _BYTE v45[24]; // [rsp+A8h] [rbp-440h] BYREF
  _BYTE v46[192]; // [rsp+C0h] [rbp-428h] BYREF
  int v47; // [rsp+180h] [rbp-368h]
  int v48; // [rsp+1D0h] [rbp-318h]
  char v49[264]; // [rsp+1D8h] [rbp-310h] BYREF
  unsigned __int16 v50; // [rsp+2E0h] [rbp-208h]
  unsigned __int8 *v51; // [rsp+2E8h] [rbp-200h]
  __int128 v52; // [rsp+490h] [rbp-58h] BYREF

  v38 = a4;
  v40 = a8;
  DeviceInfo = 0;
  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v45, L"TpmCreatePlatformClaim", &DeviceInfo);
  v52 = 0;
  LOWORD(v36) = 0;
  *(_OWORD *)Source = 0;
  v44 = 0;
  if ( !a1 || !a2 || (a3 & 0xFF000000) != 0 )
    goto LABEL_6;
  if ( a4 )
  {
    if ( !a5 )
    {
LABEL_6:
      DeviceInfo = -2147024809;
      goto LABEL_7;
    }
  }
  else if ( a5 )
  {
    goto LABEL_6;
  }
  if ( Destination )
  {
    if ( !(_DWORD)DestinationSize )
      goto LABEL_6;
  }
  else if ( (_DWORD)DestinationSize )
  {
    goto LABEL_6;
  }
  if ( !a8 )
    goto LABEL_6;
  if ( (a9 & 0xFFFFFFFC) != 0 )
  {
    KspDebugProvider::TraceLoggingError("Flags must be create boot claim, get boot claim, or 0. Flags were: %I32u", a9);
    DeviceInfo = -2146893815;
    goto LABEL_7;
  }
  v15 = 0xFFFFFF;
  if ( a3 )
    v15 = a3;
  v16 = a9 & 1;
  if ( (a9 & 2) != 0 )
  {
    if ( v16 )
    {
      KspDebugProvider::TraceLoggingError("Cannot create & get boot claim at the same time");
LABEL_21:
      DeviceInfo = -2146893783;
      goto LABEL_7;
    }
  }
  else if ( !v16 )
  {
LABEL_48:
    v37 = 0;
    DeviceInfo = Tbsi_GetDeviceInfo(16, &v52);
    if ( DeviceInfo >= 0 )
    {
      if ( DWORD1(v52) != 2 )
      {
        KspDebugProvider::TraceLoggingError("Creating platform claim not supported with TpmVersion: %I32u", DWORD1(v52));
        DeviceInfo = -2144795619;
        goto LABEL_7;
      }
      active = DetectActivePCRBank((unsigned __int16 *)&v36);
      DeviceInfo = SecurityStatusFromHResult(active);
      if ( DeviceInfo >= 0 )
      {
        LODWORD(Size) = a5;
        DeviceInfo = Tpm20CreatePlatformClaim(a1, a2, v36, v15, v38, Size, 0, 0, &v37);
        if ( DeviceInfo >= 0 )
        {
          KspLoggingProvider::TraceLoggingInfo("Boot claim requested size: %I32u", v37);
          std::vector<unsigned char>::_Resize<std::_Value_init_tag>(Source, v37);
          LODWORD(Sizea) = a5;
          DeviceInfo = Tpm20CreatePlatformClaim(
                         a1,
                         a2,
                         v36,
                         v15,
                         v38,
                         Sizea,
                         (unsigned __int8 *)Source[0],
                         LODWORD(Source[1]) - LODWORD(Source[0]),
                         &v37);
          std::vector<unsigned char>::_Resize<std::_Value_init_tag>(Source, v37);
          if ( DeviceInfo >= 0 )
          {
            v31 = v37;
            *v40 = v37;
            if ( v16 )
            {
              KspDebugProvider::TraceLoggingInfo("Saving the platform claim to the key.");
              DeviceInfo = PCPKspSetKeyProperty(a1, a2, L"PCP_PLATFORM_CLAIM");
              if ( DeviceInfo < 0 )
                goto LABEL_7;
              v31 = v37;
            }
            if ( Destination )
            {
              if ( (unsigned int)DestinationSize >= v31 )
                memcpy_s(Destination, (unsigned int)DestinationSize, Source[0], (char *)Source[1] - (char *)Source[0]);
              else
                DeviceInfo = -2146893784;
            }
          }
        }
      }
    }
    goto LABEL_7;
  }
  if ( v15 != 0xFFFFFF || a5 )
  {
    KspDebugProvider::TraceLoggingError("To create or use the static quote, the PCR mask must be all 24 PCRs and nonce must be empty");
    goto LABEL_21;
  }
  if ( (a9 & 2) == 0 )
    goto LABEL_48;
  DeviceInfo = PCPKspGetKeyProperty(a1, a2, L"PCP_PLATFORM_CLAIM", Destination, DestinationSize, v40, 0);
  if ( DeviceInfo >= 0 && Destination )
  {
    if ( (unsigned int)DestinationSize < 0x18
      || (v17 = Destination[3],
          v18 = Destination[4],
          (unsigned int)DestinationSize < v18 + v17 + (unsigned __int64)Destination[5] + 24)
      || *Destination != 1414548545
      || Destination[1] )
    {
      KspDebugProvider::TraceLoggingError("The platform claim was found, but cannot be parsed correctly.");
      goto LABEL_46;
    }
    LOWORD(v36) = 0;
    v35 = 6;
    ReadBigEndian((const unsigned __int8 *)Destination + v17 + 24, v18, &v35, (unsigned __int16 *)&v36);
    v35 += (unsigned __int16)v36;
    ReadBigEndian(v19, v20, &v35, (unsigned __int16 *)&v36);
    v35 += 8 + (unsigned __int16)v36;
    LODWORD(v38) = 0;
    ReadBigEndian(v21, v22, &v35, (unsigned int *)&v38);
    v39 = 0;
    LODWORD(v40) = 0;
    KeyProperty = PCPKspGetKeyProperty(a1, a2, L"PCP_PLATFORMHANDLE", &v40, 4, &v39, 0);
    DeviceInfo = KeyProperty;
    if ( KeyProperty < 0 )
    {
      KspDebugProvider::TraceLoggingError(
        "Failed to get native key handle when comparing platform claims. hr: 0x%X",
        KeyProperty);
LABEL_46:
      DeviceInfo = 1076429860;
      goto LABEL_7;
    }
    std::vector<unsigned char>::vector<unsigned char>(&Src, 260);
    v24 = PCPKspGetKeyProperty(a1, a2, L"PCP_TPM2BNAME", Src, (int)v42 - (int)Src, &v39, 0);
    DeviceInfo = v24;
    if ( v24 >= 0 )
    {
      std::vector<unsigned char>::_Resize<std::_Value_init_tag>(&Src, v39);
      tpm12class::TPMW8_GetTime::TPMW8_GetTime((tpm12class::TPMW8_GetTime *)v46);
      v47 = 1073741835;
      v48 = (int)v40;
      tpm12class::TPMW82B_BUFFER::CopyFrom((tpm12class::TPMW82B_BUFFER *)v49, Src, v42 - (_QWORD)Src);
      v25 = tpm12class::TPMW8_COMMAND::Execute((tpm12class::TPMW8_COMMAND *)v46, 0);
      DeviceInfo = v25;
      if ( v25 >= 0 )
      {
        v35 = 6;
        ReadBigEndian(v51, v50, &v35, (unsigned __int16 *)&v36);
        v35 += (unsigned __int16)v36;
        ReadBigEndian(v26, v27, &v35, (unsigned __int16 *)&v36);
        v35 += 8 + (unsigned __int16)v36;
        v36 = 0;
        ReadBigEndian(v28, v29, &v35, &v36);
        if ( (_DWORD)v38 == v36 )
        {
          KspLoggingProvider::TraceLoggingInfo("PCPKSP_PlatformClaimValidated");
        }
        else
        {
          KspDebugProvider::TraceLoggingError("Reset counts differ, platform claim is for a previous boot.");
          KspLoggingProvider::TraceLoggingError("PCPKSP_PlatformClaimMismatch");
          v35 += 33;
          LODWORD(v38) = 0;
          ReadBigEndian(v51, v50, &v35, (unsigned int *)&v38);
          if ( (_DWORD)v38 )
          {
            KspDebugProvider::TraceLoggingInfo(
              "This platform has been resumed from hibernate, and can no longer create a platform boot claim. A reboot is"
              " required to generate a new platform boot claim.");
            DeviceInfo = 1076429862;
          }
          else
          {
            KspDebugProvider::TraceLoggingInfo("This machine is still capable of creating the platform boot claim.");
            DeviceInfo = 1076429861;
          }
        }
      }
      else
      {
        KspDebugProvider::TraceLoggingError("GetTime failed to execute. hr: 0x%X", v25);
        DeviceInfo = 1076429860;
      }
      tpm12class::TPMW8_GetTime::~TPMW8_GetTime((tpm12class::TPMW8_GetTime *)v46);
    }
    else
    {
      KspDebugProvider::TraceLoggingError("Failed to get name of key when comparing platform claims. hr: 0x%X", v24);
      DeviceInfo = 1076429860;
    }
    std::vector<unsigned char>::_Tidy(&Src);
  }
LABEL_7:
  v13 = DeviceInfo;
  std::vector<unsigned char>::_Tidy(Source);
  KspFunctionLogger::~KspFunctionLogger((KspFunctionLogger *)v45);
  return v13;
}

```

## disassembly

```asm
0x180023894  push    rbx
0x180023896  push    rsi
0x180023897  push    rdi
0x180023898  push    r12
0x18002389a  push    r13
0x18002389c  push    r14
0x18002389e  push    r15
0x1800238a0  sub     rsp, 4B0h
0x1800238a7  mov     rax, cs:__security_cookie
0x1800238ae  xor     rax, rsp
0x1800238b1  mov     [rsp+4E8h+var_48], rax
0x1800238b9  mov     rdi, r9
0x1800238bc  mov     [rsp+4E8h+var_488], r9
0x1800238c1  mov     r14d, r8d
0x1800238c4  mov     r15, rdx
0x1800238c7  mov     r12, rcx
0x1800238ca  mov     rbx, [rsp+4E8h+Destination]
0x1800238d2  mov     r13, [rsp+4E8h+arg_38]
0x1800238da  mov     [rsp+4E8h+var_478], r13
0x1800238df  mov     [rsp+4E8h+var_498], 0
0x1800238e7  lea     r8, [rsp+4E8h+var_498]; int *
0x1800238ec  lea     rdx, aTpmcreateplatf; "TpmCreatePlatformClaim"
0x1800238f3  lea     rcx, [rsp+4E8h+var_440]; this
0x1800238fb  call    ??0KspFunctionLogger@@QEAA@QEBGAEBJ@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,long const &)
0x180023900  nop
0x180023901  xorps   xmm0, xmm0
0x180023904  movups  [rsp+4E8h+var_58], xmm0
0x18002390c  xor     ecx, ecx
0x18002390e  mov     word ptr [rsp+4E8h+var_490], cx
0x180023913  movdqu  xmmword ptr [rsp+4E8h+Source], xmm0
0x18002391c  mov     [rsp+4E8h+var_448], rcx
0x180023924  test    r12, r12
0x180023927  jz      short loc_180023947
0x180023929  test    r15, r15
0x18002392c  jz      short loc_180023947
0x18002392e  test    r14d, 0FF000000h
0x180023935  jnz     short loc_180023947
0x180023937  mov     esi, dword ptr [rsp+4E8h+arg_20]
0x18002393e  test    rdi, rdi
0x180023941  jz      short loc_18002399A
0x180023943  test    esi, esi
0x180023945  jnz     short loc_18002399E
0x180023947  mov     [rsp+4E8h+var_498], 80070057h
0x18002394f  mov     ebx, [rsp+4E8h+var_498]
0x180023953  lea     rcx, [rsp+4E8h+Source]
0x18002395b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180023960  nop
0x180023961  lea     rcx, [rsp+4E8h+var_440]; this
0x180023969  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18002396e  mov     eax, ebx
0x180023970  jmp     short loc_180023976
0x180023972  mov     eax, dword ptr [rsp+4E8h+var_488]
0x180023976  mov     rcx, [rsp+4E8h+var_48]
0x18002397e  xor     rcx, rsp; StackCookie
0x180023981  call    __security_check_cookie
0x180023986  add     rsp, 4B0h
0x18002398d  pop     r15
0x18002398f  pop     r14
0x180023991  pop     r13
0x180023993  pop     r12
0x180023995  pop     rdi
0x180023996  pop     rsi
0x180023997  pop     rbx
0x180023998  retn
0x18002399a  test    esi, esi
0x18002399c  jnz     short loc_180023947
0x18002399e  mov     edi, dword ptr [rsp+4E8h+DestinationSize]
0x1800239a5  test    rbx, rbx
0x1800239a8  jz      short loc_1800239B0
0x1800239aa  test    edi, edi
0x1800239ac  jnz     short loc_1800239B4
0x1800239ae  jmp     short loc_180023947
0x1800239b0  test    edi, edi
0x1800239b2  jnz     short loc_180023947
0x1800239b4  test    r13, r13
0x1800239b7  jz      short loc_180023947
0x1800239b9  mov     eax, [rsp+4E8h+arg_40]
0x1800239c0  test    eax, 0FFFFFFFCh
0x1800239c5  jz      short loc_1800239E2
0x1800239c7  mov     edx, eax
0x1800239c9  lea     rcx, aFlagsMustBeCre; "Flags must be create boot claim, get bo"...
0x1800239d0  call    ?TraceLoggingError@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingError(char const *,...)
0x1800239d5  mov     [rsp+4E8h+var_498], 80090009h
0x1800239dd  jmp     loc_18002394F
0x1800239e2  mov     edx, 0FFFFFFh
0x1800239e7  mov     r13d, edx
0x1800239ea  test    r14d, r14d
0x1800239ed  cmovnz  r13d, r14d
0x1800239f1  mov     r14b, al
0x1800239f4  and     r14b, 1
0x1800239f8  and     eax, 2
0x1800239fb  jz      short loc_180023A1B
0x1800239fd  test    r14b, r14b
0x180023a00  jz      short loc_180023A24
0x180023a02  lea     rcx, aCannotCreateGe; "Cannot create & get boot claim at the s"...
0x180023a09  call    ?TraceLoggingError@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingError(char const *,...)
0x180023a0e  mov     [rsp+4E8h+var_498], 80090029h
0x180023a16  jmp     loc_18002394F
0x180023a1b  test    r14b, r14b
0x180023a1e  jz      loc_180023DAB
0x180023a24  cmp     r13d, edx
0x180023a27  jnz     loc_180023D9F
0x180023a2d  test    esi, esi
0x180023a2f  jnz     loc_180023D9F
0x180023a35  test    eax, eax
0x180023a37  jz      loc_180023DAB
0x180023a3d  mov     dword ptr [rsp+4E8h+var_4B8], ecx
0x180023a41  mov     rcx, [rsp+4E8h+var_478]
0x180023a46  mov     [rsp+4E8h+Size], rcx
0x180023a4b  mov     dword ptr [rsp+4E8h+var_4C8], edi
0x180023a4f  mov     r9, rbx
0x180023a52  lea     r8, aPcpPlatformCla; "PCP_PLATFORM_CLAIM"
0x180023a59  mov     rdx, r15
0x180023a5c  mov     rcx, r12
0x180023a5f  call    PCPKspGetKeyProperty
0x180023a64  mov     [rsp+4E8h+var_498], eax
0x180023a68  xor     esi, esi
0x180023a6a  test    eax, eax
0x180023a6c  js      loc_18002394F
0x180023a72  test    rbx, rbx
0x180023a75  jz      loc_18002394F
0x180023a7b  cmp     edi, 18h
0x180023a7e  jb      loc_180023D86
0x180023a84  mov     edx, [rbx+0Ch]
0x180023a87  mov     r11d, [rbx+10h]
0x180023a8b  mov     ecx, [rbx+14h]
0x180023a8e  add     rcx, 18h
0x180023a92  add     rcx, rdx
0x180023a95  add     rcx, r11
0x180023a98  mov     eax, edi
0x180023a9a  cmp     rax, rcx
0x180023a9d  jb      loc_180023D86
0x180023aa3  cmp     dword ptr [rbx], 54504C41h
0x180023aa9  jnz     loc_180023D86
0x180023aaf  cmp     [rbx+4], esi
0x180023ab2  jnz     loc_180023D86
0x180023ab8  lea     r10, [rbx+18h]
0x180023abc  add     r10, rdx
0x180023abf  mov     word ptr [rsp+4E8h+var_490], si
0x180023ac4  lea     ebx, [rsi+6]
0x180023ac7  mov     [rsp+4E8h+var_494], ebx
0x180023acb  lea     r9, [rsp+4E8h+var_490]; unsigned __int16 *
0x180023ad0  lea     r8, [rsp+4E8h+var_494]; unsigned int *
0x180023ad5  mov     edx, r11d; unsigned int
0x180023ad8  mov     rcx, r10; unsigned __int8 *
0x180023adb  call    ?ReadBigEndian@@YAJPEBEIPEAIPEAG@Z; ReadBigEndian(uchar const *,uint,uint *,ushort *)
0x180023ae0  movzx   r8d, word ptr [rsp+4E8h+var_490]
0x180023ae6  add     [rsp+4E8h+var_494], r8d
0x180023aeb  lea     r9, [rsp+4E8h+var_490]; unsigned __int16 *
0x180023af0  lea     r8, [rsp+4E8h+var_494]; unsigned int *
0x180023af5  mov     edx, r11d; unsigned int
0x180023af8  mov     rcx, r10; unsigned __int8 *
0x180023afb  call    ?ReadBigEndian@@YAJPEBEIPEAIPEAG@Z; ReadBigEndian(uchar const *,uint,uint *,ushort *)
0x180023b00  movzx   ecx, word ptr [rsp+4E8h+var_490]
0x180023b05  mov     eax, [rsp+4E8h+var_494]
0x180023b09  add     eax, 8
0x180023b0c  add     ecx, eax
0x180023b0e  mov     [rsp+4E8h+var_494], ecx
0x180023b12  mov     dword ptr [rsp+4E8h+var_488], esi
0x180023b16  lea     r9, [rsp+4E8h+var_488]; unsigned int *
0x180023b1b  lea     r8, [rsp+4E8h+var_494]; unsigned int *
0x180023b20  mov     edx, r11d; unsigned int
0x180023b23  mov     rcx, r10; unsigned __int8 *
0x180023b26  call    ?ReadBigEndian@@YAJPEBEIPEAI1@Z; ReadBigEndian(uchar const *,uint,uint *,uint *)
0x180023b2b  mov     [rsp+4E8h+var_480], esi
0x180023b2f  mov     dword ptr [rsp+4E8h+var_478], esi
0x180023b33  mov     dword ptr [rsp+4E8h+var_4B8], esi
0x180023b37  lea     rax, [rsp+4E8h+var_480]
0x180023b3c  mov     [rsp+4E8h+Size], rax
0x180023b41  mov     dword ptr [rsp+4E8h+var_4C8], 4
0x180023b49  lea     r9, [rsp+4E8h+var_478]
0x180023b4e  lea     r8, aPcpPlatformhan; "PCP_PLATFORMHANDLE"
0x180023b55  mov     rdx, r15
0x180023b58  mov     rcx, r12
0x180023b5b  call    PCPKspGetKeyProperty
0x180023b60  mov     [rsp+4E8h+var_498], eax
0x180023b64  test    eax, eax
0x180023b66  jns     short loc_180023B7B
0x180023b68  mov     edx, eax
0x180023b6a  lea     rcx, aFailedToGetNat; "Failed to get native key handle when co"...
0x180023b71  call    ?TraceLoggingError@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingError(char const *,...)
0x180023b76  jmp     loc_180023D92
0x180023b7b  mov     edx, 104h
0x180023b80  lea     rcx, [rsp+4E8h+Src]
0x180023b85  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180023b8a  nop
0x180023b8b  mov     r9, [rsp+4E8h+Src]
0x180023b90  mov     eax, dword ptr [rsp+4E8h+var_468]
0x180023b97  sub     eax, r9d
0x180023b9a  mov     dword ptr [rsp+4E8h+var_4B8], esi
0x180023b9e  lea     rcx, [rsp+4E8h+var_480]
0x180023ba3  mov     [rsp+4E8h+Size], rcx
0x180023ba8  mov     dword ptr [rsp+4E8h+var_4C8], eax
0x180023bac  lea     r8, aPcpTpm2bname; "PCP_TPM2BNAME"
0x180023bb3  mov     rdx, r15
0x180023bb6  mov     rcx, r12
0x180023bb9  call    PCPKspGetKeyProperty
0x180023bbe  mov     [rsp+4E8h+var_498], eax
0x180023bc2  test    eax, eax
0x180023bc4  jns     short loc_180023BEB
0x180023bc6  mov     edx, eax
0x180023bc8  lea     rcx, aFailedToGetNam; "Failed to get name of key when comparin"...
0x180023bcf  call    ?TraceLoggingError@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingError(char const *,...)
0x180023bd4  mov     [rsp+4E8h+var_498], 40290424h
0x180023bdc  lea     rcx, [rsp+4E8h+Src]
0x180023be1  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180023be6  jmp     loc_18002394F
0x180023beb  mov     edx, [rsp+4E8h+var_480]
0x180023bef  lea     rcx, [rsp+4E8h+Src]
0x180023bf4  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180023bf9  lea     rcx, [rsp+4E8h+var_428]; this
0x180023c01  call    ??0TPMW8_GetTime@tpm12class@@QEAA@XZ; tpm12class::TPMW8_GetTime::TPMW8_GetTime(void)
0x180023c06  nop
0x180023c07  mov     [rsp+4E8h+var_368], 4000000Bh
0x180023c12  mov     eax, dword ptr [rsp+4E8h+var_478]
0x180023c16  mov     [rsp+4E8h+var_318], eax
0x180023c1d  mov     r8, [rsp+4E8h+var_468]
0x180023c25  mov     rdx, [rsp+4E8h+Src]; Src
0x180023c2a  sub     r8, rdx; Size
0x180023c2d  lea     rcx, [rsp+4E8h+var_310]; this
0x180023c35  call    ?CopyFrom@TPMW82B_BUFFER@tpm12class@@QEAAJPEBE_K@Z; tpm12class::TPMW82B_BUFFER::CopyFrom(uchar const *,unsigned __int64)
0x180023c3a  xor     edx, edx; void *
0x180023c3c  lea     rcx, [rsp+4E8h+var_428]; this
0x180023c44  call    ?Execute@TPMW8_COMMAND@tpm12class@@QEAAJPEAX@Z; tpm12class::TPMW8_COMMAND::Execute(void *)
0x180023c49  mov     [rsp+4E8h+var_498], eax
0x180023c4d  test    eax, eax
0x180023c4f  jns     short loc_180023C79
0x180023c51  mov     edx, eax
0x180023c53  lea     rcx, aGettimeFailedT; "GetTime failed to execute. hr: 0x%X"
0x180023c5a  call    ?TraceLoggingError@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingError(char const *,...)
0x180023c5f  mov     [rsp+4E8h+var_498], 40290424h
0x180023c67  lea     rcx, [rsp+4E8h+var_428]; this
0x180023c6f  call    ??1TPMW8_GetTime@tpm12class@@UEAA@XZ; tpm12class::TPMW8_GetTime::~TPMW8_GetTime(void)
0x180023c74  jmp     loc_180023BDC
0x180023c79  mov     [rsp+4E8h+var_494], ebx
0x180023c7d  movzx   r11d, [rsp+4E8h+var_208]
0x180023c86  lea     r9, [rsp+4E8h+var_490]; unsigned __int16 *
0x180023c8b  lea     r8, [rsp+4E8h+var_494]; unsigned int *
0x180023c90  mov     edx, r11d; unsigned int
0x180023c93  mov     r10, [rsp+4E8h+var_200]
0x180023c9b  mov     rcx, r10; unsigned __int8 *
0x180023c9e  call    ?ReadBigEndian@@YAJPEBEIPEAIPEAG@Z; ReadBigEndian(uchar const *,uint,uint *,ushort *)
0x180023ca3  movzx   r8d, word ptr [rsp+4E8h+var_490]
0x180023ca9  add     [rsp+4E8h+var_494], r8d
0x180023cae  lea     r9, [rsp+4E8h+var_490]; unsigned __int16 *
0x180023cb3  lea     r8, [rsp+4E8h+var_494]; unsigned int *
0x180023cb8  mov     edx, r11d; unsigned int
0x180023cbb  mov     rcx, r10; unsigned __int8 *
0x180023cbe  call    ?ReadBigEndian@@YAJPEBEIPEAIPEAG@Z; ReadBigEndian(uchar const *,uint,uint *,ushort *)
0x180023cc3  movzx   r8d, word ptr [rsp+4E8h+var_490]
0x180023cc9  mov     eax, [rsp+4E8h+var_494]
0x180023ccd  add     eax, 8
0x180023cd0  add     r8d, eax
0x180023cd3  mov     [rsp+4E8h+var_494], r8d
0x180023cd8  mov     [rsp+4E8h+var_490], esi
0x180023cdc  lea     r9, [rsp+4E8h+var_490]; unsigned int *
0x180023ce1  lea     r8, [rsp+4E8h+var_494]; unsigned int *
0x180023ce6  mov     edx, r11d; unsigned int
0x180023ce9  mov     rcx, r10; unsigned __int8 *
0x180023cec  call    ?ReadBigEndian@@YAJPEBEIPEAI1@Z; ReadBigEndian(uchar const *,uint,uint *,uint *)
0x180023cf1  mov     r9d, [rsp+4E8h+var_490]
0x180023cf6  cmp     dword ptr [rsp+4E8h+var_488], r9d
0x180023cfb  jz      short loc_180023D75
0x180023cfd  lea     rcx, aResetCountsDif; "Reset counts differ, platform claim is "...
0x180023d04  call    ?TraceLoggingError@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingError(char const *,...)
0x180023d09  lea     rcx, aPcpkspPlatform_0; "PCPKSP_PlatformClaimMismatch"
0x180023d10  call    ?TraceLoggingError@KspLoggingProvider@@SAXPEBDZZ; KspLoggingProvider::TraceLoggingError(char const *,...)
0x180023d15  add     [rsp+4E8h+var_494], 21h ; '!'
0x180023d1a  mov     dword ptr [rsp+4E8h+var_488], esi
0x180023d1e  movzx   edx, [rsp+4E8h+var_208]; unsigned int
0x180023d26  lea     r9, [rsp+4E8h+var_488]; unsigned int *
0x180023d2b  lea     r8, [rsp+4E8h+var_494]; unsigned int *
0x180023d30  mov     rcx, [rsp+4E8h+var_200]; unsigned __int8 *
0x180023d38  call    ?ReadBigEndian@@YAJPEBEIPEAI1@Z; ReadBigEndian(uchar const *,uint,uint *,uint *)
0x180023d3d  cmp     dword ptr [rsp+4E8h+var_488], esi
0x180023d41  jnz     short loc_180023D5C
0x180023d43  lea     rcx, aThisMachineIsS; "This machine is still capable of creati"...
0x180023d4a  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x180023d4f  mov     [rsp+4E8h+var_498], 40290425h
0x180023d57  jmp     loc_180023C67
0x180023d5c  lea     rcx, aThisPlatformHa; "This platform has been resumed from hib"...
0x180023d63  call    ?TraceLoggingInfo@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingInfo(char const *,...)
0x180023d68  mov     [rsp+4E8h+var_498], 40290426h
0x180023d70  jmp     loc_180023C67
0x180023d75  lea     rcx, aPcpkspPlatform; "PCPKSP_PlatformClaimValidated"
0x180023d7c  call    ?TraceLoggingInfo@KspLoggingProvider@@SAXPEBDZZ; KspLoggingProvider::TraceLoggingInfo(char const *,...)
0x180023d81  jmp     loc_180023C67
0x180023d86  lea     rcx, aThePlatformCla; "The platform claim was found, but canno"...
0x180023d8d  call    ?TraceLoggingError@KspDebugProvider@@SAXPEBDZZ; KspDebugProvider::TraceLoggingError(char const *,...)
0x180023d92  mov     [rsp+4E8h+var_498], 40290424h
0x180023d9a  jmp     loc_18002394F
0x180023d9f  lea     rcx, aToCreateOrUseT; "To create or use the static quote, the "...
0x180023da6  jmp     loc_180023A09
0x180023dab  mov     [rsp+4E8h+var_48C], ecx
0x180023daf  lea     rdx, [rsp+4E8h+var_58]
0x180023db7  mov     ecx, 10h
0x180023dbc  call    cs:__imp_Tbsi_GetDeviceInfo
0x180023dc3  nop     dword ptr [rax+rax+00h]
0x180023dc8  mov     [rsp+4E8h+var_498], eax
0x180023dcc  test    eax, eax
  ... truncated ...
```
