# Telemetryp_EventDataSaveToFile(_PCA_TELEMETRY_EVENT_DATA *)

- ea: `0x1800b01c8`
- end: `0x1800b09c4`
- name: `?Telemetryp_EventDataSaveToFile@@YAXPEAU_PCA_TELEMETRY_EVENT_DATA@@@Z`
- size: `2044`
- prototype: `void __fastcall(struct _PCA_TELEMETRY_EVENT_DATA *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001ecf0`

## callees

- `0x18000b6f0`
- `0x18000b730`
- `0x18000cb00`
- `0x18000d530`
- `0x18000dc08`
- `0x180012920`
- `0x18001e688`
- `0x1800b01c8`
- `0x1800ee5d0`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800b0298`
- `msvcrt!swprintf_s` at `0x1800b0310`
- `msvcrt!swprintf_s` at `0x1800b0374`
- `msvcrt!swprintf_s` at `0x1800b03d4`
- `msvcrt!swprintf_s` at `0x1800b0434`
- `msvcrt!swprintf_s` at `0x1800b0494`
- `msvcrt!swprintf_s` at `0x1800b04f4`
- `msvcrt!swprintf_s` at `0x1800b0554`
- `msvcrt!swprintf_s` at `0x1800b05b1`
- `msvcrt!swprintf_s` at `0x1800b06b3`
- `msvcrt!swprintf_s` at `0x1800b07ef`
- `msvcrt!swprintf_s` at `0x1800b0298`
- `msvcrt!swprintf_s` at `0x1800b0310`
- `msvcrt!swprintf_s` at `0x1800b0374`
- `msvcrt!swprintf_s` at `0x1800b03d4`
- `msvcrt!swprintf_s` at `0x1800b0434`
- `msvcrt!swprintf_s` at `0x1800b0494`
- `msvcrt!swprintf_s` at `0x1800b04f4`
- `msvcrt!swprintf_s` at `0x1800b0554`
- `msvcrt!swprintf_s` at `0x1800b05b1`
- `msvcrt!swprintf_s` at `0x1800b06b3`
- `msvcrt!swprintf_s` at `0x1800b07ef`
- `ntdll!RtlGetNtSystemRoot` at `0x1800b083e`
- `ntdll!RtlGetNtSystemRoot` at `0x1800b083e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0889`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0889`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800b087f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800b087f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800b08ac`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800b08ac`

## string_xrefs

- `0x1800b045d`: `CompatStateAfter`
- `0x1800b043e`: `Failed to swprintf compatstateafter`
- `0x1800b0411`: `Failed to add compatestatebefore [%d]`
- `0x1800b03fd`: `CompatStateBefore`
- `0x1800b03de`: `Failed to swprintf compatstatebefore`
- `0x1800b0471`: `Failed to add compatstateafter [%d]`
- `0x1800b0726`: `Failed to add pinneddllname [%d]`
- `0x1800b0712`: `PinnedDllName`
- `0x1800b0847`: `%s\AppCompat\Programs\Install`
- `0x1800b08b9`: `Failed to create guid [%d]`
- `0x1800b0896`: `Failed to create directory [%d]`
- `0x1800b0867`: `Failed to create trace file name [%d]`
- `0x1800b094d`: `Failed to create trace file name [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Telemetryp_EventDataSaveToFile(struct _PCA_TELEMETRY_EVENT_DATA *a1)
{
  void *v2; // rdx
  int LastError; // eax
  const unsigned __int16 *v4; // rdx
  const char *v5; // r9
  int v6; // r8d
  const unsigned __int16 *v7; // rdx
  const unsigned __int16 *v8; // rdx
  const unsigned __int16 *v9; // rdx
  const unsigned __int16 *v10; // rdx
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // rdx
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // rdx
  const unsigned __int16 *v15; // rdx
  const unsigned __int16 *v16; // rdx
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // rdx
  const unsigned __int16 *v19; // rdx
  const unsigned __int16 *v20; // rdx
  const unsigned __int16 *v21; // rdx
  const unsigned __int16 *v22; // rdx
  const unsigned __int16 *v23; // rdx
  const unsigned __int16 *v24; // rdx
  __int64 NtSystemRoot; // rax
  unsigned __int64 v26; // [rsp+20h] [rbp-E0h]
  int Data2; // [rsp+28h] [rbp-D8h]
  int Data3; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+38h] [rbp-C8h]
  int v30; // [rsp+40h] [rbp-C0h]
  int v31; // [rsp+48h] [rbp-B8h]
  int v32; // [rsp+50h] [rbp-B0h]
  int v33; // [rsp+58h] [rbp-A8h]
  int v34; // [rsp+60h] [rbp-A0h]
  int v35; // [rsp+68h] [rbp-98h]
  int v36; // [rsp+70h] [rbp-90h]
  __int128 v37; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v38[2]; // [rsp+90h] [rbp-70h]
  __int128 v39; // [rsp+A0h] [rbp-60h]
  GUID pguid; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Buffer[32]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR PathName[264]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR FileName[264]; // [rsp+310h] [rbp+210h] BYREF

  RtlNameValueArray::RtlNameValueArray((RtlNameValueArray *)&v37);
  v37 = 0;
  *(_OWORD *)v38 = 0;
  v39 = 0;
  Buffer[0] = 0;
  FileName[0] = 0;
  pguid = 0;
  PathName[0] = 0;
  LastError = RtlNameValueArray::Initialize((RtlNameValueArray *)&v37, v2, 0x10u, 4u);
  if ( LastError )
  {
    v5 = "Failed to initialize event attribute list [%d]";
    v6 = 2063;
LABEL_75:
    LODWORD(v26) = LastError;
    AslLogCallPrintf(1, (unsigned int)"Telemetryp_EventDataSaveToFile", v6, (_DWORD)v5, v26);
    goto LABEL_76;
  }
  LastError = RtlNameValueArray::Insert(
                (RtlNameValueArray *)&v37,
                v4,
                L"ExeName",
                (const unsigned __int16 *)a1 + 32,
                v38[0]);
  if ( LastError )
  {
    v5 = "Failed to add exename [%d]";
    v6 = 2069;
    goto LABEL_75;
  }
  if ( swprintf_s(Buffer, 0x20u, L"%I32d", *((unsigned int *)a1 + 276)) == -1 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"Telemetryp_EventDataSaveToFile",
      2074,
      (unsigned int)"Failed to swprintf exe size");
    goto LABEL_76;
  }
  LastError = RtlNameValueArray::Insert((RtlNameValueArray *)&v37, v7, L"ExeSize", Buffer, v38[0]);
  if ( LastError )
  {
    v5 = "Failed to add exe size [%d]";
    v6 = 2079;
    goto LABEL_75;
  }
  if ( swprintf_s(Buffer, 0x20u, L"0x%I32X", *((unsigned int *)a1 + 277)) == -1 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"Telemetryp_EventDataSaveToFile",
      2084,
      (unsigned int)"Failed to swprintf exe checksum");
  }
  else
  {
    LastError = RtlNameValueArray::Insert((RtlNameValueArray *)&v37, v8, L"ExeCheckSum", Buffer, v38[0]);
    if ( LastError )
    {
      v5 = "Failed to add exe checksum [%d]";
      v6 = 2089;
      goto LABEL_75;
    }
    if ( swprintf_s(Buffer, 0x20u, L"0x%I64X", *((_QWORD *)a1 + 207)) == -1 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"Telemetryp_EventDataSaveToFile",
        2094,
        (unsigned int)"Failed to swprintf environment");
    }
    else
    {
      LastError = RtlNameValueArray::Insert((RtlNameValueArray *)&v37, v9, L"Environment", Buffer, v38[0]);
      if ( LastError )
      {
        v5 = "Failed to add environment [%d]";
        v6 = 2099;
        goto LABEL_75;
      }
      if ( swprintf_s(Buffer, 0x20u, L"0x%I64X", *((_QWORD *)a1 + 209)) == -1 )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"Telemetryp_EventDataSaveToFile",
          2104,
          (unsigned int)"Failed to swprintf compatstatebefore");
      }
      else
      {
        LastError = RtlNameValueArray::Insert((RtlNameValueArray *)&v37, v10, L"CompatStateBefore", Buffer, v38[0]);
        if ( LastError )
        {
          v5 = "Failed to add compatestatebefore [%d]";
          v6 = 2109;
          goto LABEL_75;
        }
        if ( swprintf_s(Buffer, 0x20u, L"0x%I64X", *((_QWORD *)a1 + 211)) == -1 )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"Telemetryp_EventDataSaveToFile",
            2114,
            (unsigned int)"Failed to swprintf compatstateafter");
        }
        else
        {
          LastError = RtlNameValueArray::Insert((RtlNameValueArray *)&v37, v11, L"CompatStateAfter", Buffer, v38[0]);
          if ( LastError )
          {
            v5 = "Failed to add compatstateafter [%d]";
            v6 = 2119;
            goto LABEL_75;
          }
          if ( swprintf_s(Buffer, 0x20u, L"%I32d", *((unsigned int *)a1 + 416)) == -1 )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"Telemetryp_EventDataSaveToFile",
              2124,
              (unsigned int)"Failed to swprintf runtimebefore");
          }
          else
          {
            LastError = RtlNameValueArray::Insert((RtlNameValueArray *)&v37, v12, L"RuntimeBefore", Buffer, v38[0]);
            if ( LastError )
            {
              v5 = "Failed to add runtimebefore [%d]";
              v6 = 2129;
              goto LABEL_75;
            }
            if ( swprintf_s(Buffer, 0x20u, L"%I32d", *((unsigned int *)a1 + 420)) == -1 )
            {
              AslLogCallPrintf(
                1,
                (unsigned int)"Telemetryp_EventDataSaveToFile",
                2134,
                (unsigned int)"Failed to swprintf runtimeafter");
            }
            else
            {
              LastError = RtlNameValueArray::Insert((RtlNameValueArray *)&v37, v13, L"RuntimeAfter", Buffer, v38[0]);
              if ( LastError )
              {
                v5 = "Failed to add runtimeafter [%d]";
                v6 = 2139;
                goto LABEL_75;
              }
              if ( swprintf_s(Buffer, 0x20u, L"0x%I64X", *((_QWORD *)a1 + 499)) == -1 )
              {
                AslLogCallPrintf(
                  1,
                  (unsigned int)"Telemetryp_EventDataSaveToFile",
                  2144,
                  (unsigned int)"Failed to swprintf flags");
              }
              else
              {
                LastError = RtlNameValueArray::Insert((RtlNameValueArray *)&v37, v14, L"Flags", Buffer, v38[0]);
                if ( LastError )
                {
                  v5 = "Failed to add flags [%d]";
                  v6 = 2149;
                  goto LABEL_75;
                }
                if ( swprintf_s(Buffer, 0x20u, L"0x%I64X", *((_QWORD *)a1 + 6)) == -1 )
                {
                  AslLogCallPrintf(
                    1,
                    (unsigned int)"Telemetryp_EventDataSaveToFile",
                    2154,
                    (unsigned int)"Failed to swprintf genome");
                }
                else
                {
                  LastError = RtlNameValueArray::Insert((RtlNameValueArray *)&v37, v15, L"Genome", Buffer, v38[0]);
                  if ( LastError )
                  {
                    v5 = "Failed to add genome [%d]";
                    v6 = 2159;
                    goto LABEL_75;
                  }
                  LastError = RtlNameValueArray::Insert(
                                (RtlNameValueArray *)&v37,
                                v16,
                                L"AppName",
                                (const unsigned __int16 *)a1 + 1200,
                                v38[0]);
                  if ( LastError )
                  {
                    v5 = "Failed to add appname [%d]";
                    v6 = 2164;
                    goto LABEL_75;
                  }
                  LastError = RtlNameValueArray::Insert(
                                (RtlNameValueArray *)&v37,
                                v17,
                                L"AppVersion",
                                (const unsigned __int16 *)a1 + 1460,
                                v38[0]);
                  if ( LastError )
                  {
                    v5 = "Failed to add appversion [%d]";
                    v6 = 2169;
                    goto LABEL_75;
                  }
                  LastError = RtlNameValueArray::Insert(
                                (RtlNameValueArray *)&v37,
                                v18,
                                L"AppPublisher",
                                (const unsigned __int16 *)a1 + 1720,
                                v38[0]);
                  if ( LastError )
                  {
                    v5 = "Failed to add apppublisher [%d]";
                    v6 = 2174;
                    goto LABEL_75;
                  }
                  if ( swprintf_s(Buffer, 0x20u, L"%I32d", *((unsigned int *)a1 + 990)) == -1 )
                  {
                    AslLogCallPrintf(
                      1,
                      (unsigned int)"Telemetryp_EventDataSaveToFile",
                      2179,
                      (unsigned int)"Failed to swprintf applanguage");
                  }
                  else
                  {
                    LastError = RtlNameValueArray::Insert(
                                  (RtlNameValueArray *)&v37,
                                  v19,
                                  L"AppLanguage",
                                  Buffer,
                                  v38[0]);
                    if ( LastError )
                    {
                      v5 = "Failed to add applanguage [%d]";
                      v6 = 2184;
                      goto LABEL_75;
                    }
                    LastError = RtlNameValueArray::Insert(
                                  (RtlNameValueArray *)&v37,
                                  v20,
                                  L"PinnedDllName",
                                  (const unsigned __int16 *)a1 + 848,
                                  v38[0]);
                    if ( LastError )
                    {
                      v5 = "Failed to add pinneddllname [%d]";
                      v6 = 2189;
                      goto LABEL_75;
                    }
                    LastError = RtlNameValueArray::Insert(
                                  (RtlNameValueArray *)&v37,
                                  v21,
                                  L"ProgramId",
                                  (const unsigned __int16 *)a1 + 1110,
                                  v38[0]);
                    if ( LastError )
                    {
                      v5 = "Failed to add programid [%d]";
                      v6 = 2194;
                      goto LABEL_75;
                    }
                    LastError = RtlNameValueArray::Insert(
                                  (RtlNameValueArray *)&v37,
                                  v22,
                                  L"FileId",
                                  (const unsigned __int16 *)a1 + 1155,
                                  v38[0]);
                    if ( LastError )
                    {
                      v5 = "Failed to add fileid [%d]";
                      v6 = 2199;
                      goto LABEL_75;
                    }
                    LastError = RtlNameValueArray::Insert(
                                  (RtlNameValueArray *)&v37,
                                  v23,
                                  L"AltName",
                                  (const unsigned __int16 *)a1 + 292,
                                  v38[0]);
                    if ( LastError )
                    {
                      v5 = "Failed to add altname [%d]";
                      v6 = 2204;
                      goto LABEL_75;
                    }
                    if ( swprintf_s(Buffer, 0x20u, L"%I64X", *((_QWORD *)a1 + 139)) == -1 )
                    {
                      AslLogCallPrintf(
                        1,
                        (unsigned int)"Telemetryp_EventDataSaveToFile",
                        2209,
                        (unsigned int)"Failed to swprintf exeversion");
                    }
                    else
                    {
                      LastError = RtlNameValueArray::Insert(
                                    (RtlNameValueArray *)&v37,
                                    v24,
                                    L"ExeBinFileVersion",
                                    Buffer,
                                    v38[0]);
                      if ( LastError )
                      {
                        v5 = "Failed to add exeversion [%d]";
                        v6 = 2214;
                        goto LABEL_75;
                      }
                      NtSystemRoot = RtlGetNtSystemRoot();
                      LastError = StringCchPrintfW(PathName, 0x104u, L"%s\\AppCompat\\Programs\\Install", NtSystemRoot);
                      if ( LastError < 0 )
                      {
                        LastError = (unsigned __int16)LastError;
                        v5 = "Failed to create trace file name [%d]";
                        v6 = 2228;
                        goto LABEL_75;
                      }
                      if ( !CreateDirectoryW(PathName, 0) )
                      {
                        LastError = GetLastError();
                        if ( LastError != 183 )
                        {
                          v5 = "Failed to create directory [%d]";
                          v6 = 2235;
                          goto LABEL_75;
                        }
                      }
                      LastError = CoCreateGuid(&pguid);
                      if ( LastError < 0 )
                      {
                        LastError = (unsigned __int16)LastError;
                        v5 = "Failed to create guid [%d]";
                        v6 = 2243;
                        goto LABEL_75;
                      }
                      v36 = pguid.Data4[7];
                      v35 = pguid.Data4[6];
                      v34 = pguid.Data4[5];
                      v33 = pguid.Data4[4];
                      v32 = pguid.Data4[3];
                      v31 = pguid.Data4[2];
                      v30 = pguid.Data4[1];
                      v29 = pguid.Data4[0];
                      Data3 = pguid.Data3;
                      Data2 = pguid.Data2;
                      LODWORD(v26) = pguid.Data1;
                      LastError = StringCchPrintfW(
                                    FileName,
                                    0x104u,
                                    L"%s\\TELEMETRY_EVENT_0000_%08lx-%04hx-%04hx-%02hx%02hx-%02hx%02hx%02hx%02hx%02hx%02hx.tel",
                                    PathName,
                                    v26,
                                    Data2,
                                    Data3,
                                    v29,
                                    v30,
                                    v31,
                                    v32,
                                    v33,
                                    v34,
                                    v35,
                                    v36);
                      if ( LastError < 0 )
                      {
                        LastError = (unsigned __int16)LastError;
                        v5 = "Failed to create trace file name [%d]";
                        v6 = 2264;
                        goto LABEL_75;
                      }
                      LastError = PcaUtilityNameValueArraySaveToFile((struct RtlNameValueArray *)&v37, FileName);
                      if ( LastError )
                      {
                        v5 = "Failed to save trace file [%d]";
                        v6 = 2274;
                        goto LABEL_75;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_76:
  RtlNameValueArray::Free((RtlNameValueArray *)&v37);
  RtlStringArray::~RtlStringArray((RtlStringArray *)&v37);
}

```

## disassembly

```asm
0x1800b01c8  push    rbp
0x1800b01ca  push    rbx
0x1800b01cb  push    rsi
0x1800b01cc  push    rdi
0x1800b01cd  push    r14
0x1800b01cf  push    r15
0x1800b01d1  lea     rbp, [rsp-438h]
0x1800b01d9  sub     rsp, 538h
0x1800b01e0  mov     rax, cs:__security_cookie
0x1800b01e7  xor     rax, rsp
0x1800b01ea  mov     [rbp+460h+var_40], rax
0x1800b01f1  mov     rbx, rcx
0x1800b01f4  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b01f8  call    ??0RtlNameValueArray@@QEAA@XZ; RtlNameValueArray::RtlNameValueArray(void)
0x1800b01fd  nop
0x1800b01fe  xorps   xmm0, xmm0
0x1800b0201  movups  [rbp+460h+var_4E0], xmm0
0x1800b0205  movups  xmmword ptr [rbp+460h+var_4D0], xmm0
0x1800b0209  movups  [rbp+460h+var_4C0], xmm0
0x1800b020d  xor     eax, eax
0x1800b020f  mov     [rbp+460h+Buffer], ax
0x1800b0213  mov     [rbp+460h+FileName], ax
0x1800b021a  movups  xmmword ptr [rbp+460h+pguid.Data1], xmm0
0x1800b021e  mov     [rbp+460h+PathName], ax
0x1800b0222  lea     r9d, [rax+4]; unsigned __int64
0x1800b0226  lea     r8d, [rax+10h]; unsigned __int64
0x1800b022a  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b022e  call    ?Initialize@RtlNameValueArray@@QEAAJPEAX_K1@Z; RtlNameValueArray::Initialize(void *,unsigned __int64,unsigned __int64)
0x1800b0233  test    eax, eax
0x1800b0235  jz      short loc_1800B0249
0x1800b0237  lea     r9, aFailedToInitia_1; "Failed to initialize event attribute li"...
0x1800b023e  mov     r8d, 80Fh
0x1800b0244  jmp     loc_1800B097D
0x1800b0249  lea     r9, [rbx+40h]; unsigned __int16 *
0x1800b024d  mov     rax, [rbp+460h+var_4D0]
0x1800b0251  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b0256  lea     r8, aExename; "ExeName"
0x1800b025d  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b0261  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b0266  test    eax, eax
0x1800b0268  jz      short loc_1800B027C
0x1800b026a  lea     r9, aFailedToAddExe; "Failed to add exename [%d]"
0x1800b0271  mov     r8d, 815h
0x1800b0277  jmp     loc_1800B097D
0x1800b027c  mov     r9d, [rbx+450h]
0x1800b0283  lea     r15, aI32d; "%I32d"
0x1800b028a  mov     r8, r15; Format
0x1800b028d  mov     edi, 20h ; ' '
0x1800b0292  mov     edx, edi; BufferCount
0x1800b0294  lea     rcx, [rbp+460h+Buffer]; Buffer
0x1800b0298  call    cs:__imp_swprintf_s
0x1800b029e  or      esi, 0FFFFFFFFh
0x1800b02a1  cmp     eax, esi
0x1800b02a3  jnz     short loc_1800B02C8
0x1800b02a5  lea     r9, aFailedToSwprin_7; "Failed to swprintf exe size"
0x1800b02ac  mov     r8d, 81Ah
0x1800b02b2  lea     rdx, aTelemetrypEven_1; "Telemetryp_EventDataSaveToFile"
0x1800b02b9  mov     ecx, 1
0x1800b02be  call    AslLogCallPrintf
0x1800b02c3  jmp     loc_1800B0992
0x1800b02c8  mov     rax, [rbp+460h+var_4D0]
0x1800b02cc  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b02d1  lea     r9, [rbp+460h+Buffer]; unsigned __int16 *
0x1800b02d5  lea     r8, aExesize; "ExeSize"
0x1800b02dc  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b02e0  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b02e5  test    eax, eax
0x1800b02e7  jz      short loc_1800B02FB
0x1800b02e9  lea     r9, aFailedToAddExe_1; "Failed to add exe size [%d]"
0x1800b02f0  mov     r8d, 81Fh
0x1800b02f6  jmp     loc_1800B097D
0x1800b02fb  mov     r9d, [rbx+454h]
0x1800b0302  lea     r8, a0xI32x; "0x%I32X"
0x1800b0309  mov     rdx, rdi; BufferCount
0x1800b030c  lea     rcx, [rbp+460h+Buffer]; Buffer
0x1800b0310  call    cs:__imp_swprintf_s
0x1800b0316  cmp     eax, esi
0x1800b0318  jnz     short loc_1800B0329
0x1800b031a  lea     r9, aFailedToSwprin_2; "Failed to swprintf exe checksum"
0x1800b0321  mov     r8d, 824h
0x1800b0327  jmp     short loc_1800B02B2
0x1800b0329  mov     rax, [rbp+460h+var_4D0]
0x1800b032d  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b0332  lea     r9, [rbp+460h+Buffer]; unsigned __int16 *
0x1800b0336  lea     r8, aExechecksum; "ExeCheckSum"
0x1800b033d  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b0341  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b0346  test    eax, eax
0x1800b0348  jz      short loc_1800B035C
0x1800b034a  lea     r9, aFailedToAddExe_3; "Failed to add exe checksum [%d]"
0x1800b0351  mov     r8d, 829h
0x1800b0357  jmp     loc_1800B097D
0x1800b035c  mov     r9, [rbx+678h]
0x1800b0363  lea     r14, a0xI64x; "0x%I64X"
0x1800b036a  mov     r8, r14; Format
0x1800b036d  mov     rdx, rdi; BufferCount
0x1800b0370  lea     rcx, [rbp+460h+Buffer]; Buffer
0x1800b0374  call    cs:__imp_swprintf_s
0x1800b037a  cmp     eax, esi
0x1800b037c  jnz     short loc_1800B0390
0x1800b037e  lea     r9, aFailedToSwprin_8; "Failed to swprintf environment"
0x1800b0385  mov     r8d, 82Eh
0x1800b038b  jmp     loc_1800B02B2
0x1800b0390  mov     rax, [rbp+460h+var_4D0]
0x1800b0394  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b0399  lea     r9, [rbp+460h+Buffer]; unsigned __int16 *
0x1800b039d  lea     r8, aEnvironment; "Environment"
0x1800b03a4  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b03a8  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b03ad  test    eax, eax
0x1800b03af  jz      short loc_1800B03C3
0x1800b03b1  lea     r9, aFailedToAddEnv; "Failed to add environment [%d]"
0x1800b03b8  mov     r8d, 833h
0x1800b03be  jmp     loc_1800B097D
0x1800b03c3  mov     r9, [rbx+688h]
0x1800b03ca  mov     r8, r14; Format
0x1800b03cd  mov     rdx, rdi; BufferCount
0x1800b03d0  lea     rcx, [rbp+460h+Buffer]; Buffer
0x1800b03d4  call    cs:__imp_swprintf_s
0x1800b03da  cmp     eax, esi
0x1800b03dc  jnz     short loc_1800B03F0
0x1800b03de  lea     r9, aFailedToSwprin_9; "Failed to swprintf compatstatebefore"
0x1800b03e5  mov     r8d, 838h
0x1800b03eb  jmp     loc_1800B02B2
0x1800b03f0  mov     rax, [rbp+460h+var_4D0]
0x1800b03f4  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b03f9  lea     r9, [rbp+460h+Buffer]; unsigned __int16 *
0x1800b03fd  lea     r8, aCompatstatebef; "CompatStateBefore"
0x1800b0404  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b0408  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b040d  test    eax, eax
0x1800b040f  jz      short loc_1800B0423
0x1800b0411  lea     r9, aFailedToAddCom; "Failed to add compatestatebefore [%d]"
0x1800b0418  mov     r8d, 83Dh
0x1800b041e  jmp     loc_1800B097D
0x1800b0423  mov     r9, [rbx+698h]
0x1800b042a  mov     r8, r14; Format
0x1800b042d  mov     rdx, rdi; BufferCount
0x1800b0430  lea     rcx, [rbp+460h+Buffer]; Buffer
0x1800b0434  call    cs:__imp_swprintf_s
0x1800b043a  cmp     eax, esi
0x1800b043c  jnz     short loc_1800B0450
0x1800b043e  lea     r9, aFailedToSwprin_3; "Failed to swprintf compatstateafter"
0x1800b0445  mov     r8d, 842h
0x1800b044b  jmp     loc_1800B02B2
0x1800b0450  mov     rax, [rbp+460h+var_4D0]
0x1800b0454  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b0459  lea     r9, [rbp+460h+Buffer]; unsigned __int16 *
0x1800b045d  lea     r8, aCompatstateaft; "CompatStateAfter"
0x1800b0464  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b0468  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b046d  test    eax, eax
0x1800b046f  jz      short loc_1800B0483
0x1800b0471  lea     r9, aFailedToAddCom_0; "Failed to add compatstateafter [%d]"
0x1800b0478  mov     r8d, 847h
0x1800b047e  jmp     loc_1800B097D
0x1800b0483  mov     r9d, [rbx+680h]
0x1800b048a  mov     r8, r15; Format
0x1800b048d  mov     rdx, rdi; BufferCount
0x1800b0490  lea     rcx, [rbp+460h+Buffer]; Buffer
0x1800b0494  call    cs:__imp_swprintf_s
0x1800b049a  cmp     eax, esi
0x1800b049c  jnz     short loc_1800B04B0
0x1800b049e  lea     r9, aFailedToSwprin_0; "Failed to swprintf runtimebefore"
0x1800b04a5  mov     r8d, 84Ch
0x1800b04ab  jmp     loc_1800B02B2
0x1800b04b0  mov     rax, [rbp+460h+var_4D0]
0x1800b04b4  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b04b9  lea     r9, [rbp+460h+Buffer]; unsigned __int16 *
0x1800b04bd  lea     r8, aRuntimebefore; "RuntimeBefore"
0x1800b04c4  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b04c8  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b04cd  test    eax, eax
0x1800b04cf  jz      short loc_1800B04E3
0x1800b04d1  lea     r9, aFailedToAddRun; "Failed to add runtimebefore [%d]"
0x1800b04d8  mov     r8d, 851h
0x1800b04de  jmp     loc_1800B097D
0x1800b04e3  mov     r9d, [rbx+690h]
0x1800b04ea  mov     r8, r15; Format
0x1800b04ed  mov     rdx, rdi; BufferCount
0x1800b04f0  lea     rcx, [rbp+460h+Buffer]; Buffer
0x1800b04f4  call    cs:__imp_swprintf_s
0x1800b04fa  cmp     eax, esi
0x1800b04fc  jnz     short loc_1800B0510
0x1800b04fe  lea     r9, aFailedToSwprin_5; "Failed to swprintf runtimeafter"
0x1800b0505  mov     r8d, 856h
0x1800b050b  jmp     loc_1800B02B2
0x1800b0510  mov     rax, [rbp+460h+var_4D0]
0x1800b0514  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b0519  lea     r9, [rbp+460h+Buffer]; unsigned __int16 *
0x1800b051d  lea     r8, aRuntimeafter; "RuntimeAfter"
0x1800b0524  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b0528  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b052d  test    eax, eax
0x1800b052f  jz      short loc_1800B0543
0x1800b0531  lea     r9, aFailedToAddRun_0; "Failed to add runtimeafter [%d]"
0x1800b0538  mov     r8d, 85Bh
0x1800b053e  jmp     loc_1800B097D
0x1800b0543  mov     r9, [rbx+0F98h]
0x1800b054a  mov     r8, r14; Format
0x1800b054d  mov     rdx, rdi; BufferCount
0x1800b0550  lea     rcx, [rbp+460h+Buffer]; Buffer
0x1800b0554  call    cs:__imp_swprintf_s
0x1800b055a  cmp     eax, esi
0x1800b055c  jnz     short loc_1800B0570
0x1800b055e  lea     r9, aFailedToSwprin_6; "Failed to swprintf flags"
0x1800b0565  mov     r8d, 860h
0x1800b056b  jmp     loc_1800B02B2
0x1800b0570  mov     rax, [rbp+460h+var_4D0]
0x1800b0574  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b0579  lea     r9, [rbp+460h+Buffer]; unsigned __int16 *
0x1800b057d  lea     r8, aFlags; "Flags"
0x1800b0584  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b0588  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b058d  test    eax, eax
0x1800b058f  jz      short loc_1800B05A3
0x1800b0591  lea     r9, aFailedToAddFla; "Failed to add flags [%d]"
0x1800b0598  mov     r8d, 865h
0x1800b059e  jmp     loc_1800B097D
0x1800b05a3  mov     r9, [rbx+30h]
0x1800b05a7  mov     r8, r14; Format
0x1800b05aa  mov     rdx, rdi; BufferCount
0x1800b05ad  lea     rcx, [rbp+460h+Buffer]; Buffer
0x1800b05b1  call    cs:__imp_swprintf_s
0x1800b05b7  cmp     eax, esi
0x1800b05b9  jnz     short loc_1800B05CD
0x1800b05bb  lea     r9, aFailedToSwprin_1; "Failed to swprintf genome"
0x1800b05c2  mov     r8d, 86Ah
0x1800b05c8  jmp     loc_1800B02B2
0x1800b05cd  mov     rax, [rbp+460h+var_4D0]
0x1800b05d1  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b05d6  lea     r9, [rbp+460h+Buffer]; unsigned __int16 *
0x1800b05da  lea     r8, aGenome; "Genome"
0x1800b05e1  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b05e5  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b05ea  test    eax, eax
0x1800b05ec  jz      short loc_1800B0600
0x1800b05ee  lea     r9, aFailedToAddGen; "Failed to add genome [%d]"
0x1800b05f5  mov     r8d, 86Fh
0x1800b05fb  jmp     loc_1800B097D
0x1800b0600  lea     r9, [rbx+960h]; unsigned __int16 *
0x1800b0607  mov     rax, [rbp+460h+var_4D0]
0x1800b060b  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b0610  lea     r8, aAppname; "AppName"
0x1800b0617  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b061b  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b0620  test    eax, eax
0x1800b0622  jz      short loc_1800B0636
0x1800b0624  lea     r9, aFailedToAddApp_4; "Failed to add appname [%d]"
0x1800b062b  mov     r8d, 874h
0x1800b0631  jmp     loc_1800B097D
0x1800b0636  lea     r9, [rbx+0B68h]; unsigned __int16 *
0x1800b063d  mov     rax, [rbp+460h+var_4D0]
0x1800b0641  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b0646  lea     r8, aAppversion; "AppVersion"
0x1800b064d  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b0651  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b0656  test    eax, eax
0x1800b0658  jz      short loc_1800B066C
0x1800b065a  lea     r9, aFailedToAddApp_3; "Failed to add appversion [%d]"
0x1800b0661  mov     r8d, 879h
0x1800b0667  jmp     loc_1800B097D
0x1800b066c  lea     r9, [rbx+0D70h]; unsigned __int16 *
0x1800b0673  mov     rax, [rbp+460h+var_4D0]
0x1800b0677  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b067c  lea     r8, aApppublisher; "AppPublisher"
0x1800b0683  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b0687  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b068c  test    eax, eax
0x1800b068e  jz      short loc_1800B06A2
0x1800b0690  lea     r9, aFailedToAddApp_1; "Failed to add apppublisher [%d]"
0x1800b0697  mov     r8d, 87Eh
0x1800b069d  jmp     loc_1800B097D
0x1800b06a2  mov     r9d, [rbx+0F78h]
0x1800b06a9  mov     r8, r15; Format
0x1800b06ac  mov     rdx, rdi; BufferCount
0x1800b06af  lea     rcx, [rbp+460h+Buffer]; Buffer
0x1800b06b3  call    cs:__imp_swprintf_s
0x1800b06b9  cmp     eax, esi
0x1800b06bb  jnz     short loc_1800B06CF
0x1800b06bd  lea     r9, aFailedToSwprin; "Failed to swprintf applanguage"
0x1800b06c4  mov     r8d, 883h
0x1800b06ca  jmp     loc_1800B02B2
0x1800b06cf  mov     rax, [rbp+460h+var_4D0]
0x1800b06d3  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b06d8  lea     r9, [rbp+460h+Buffer]; unsigned __int16 *
0x1800b06dc  lea     r8, aApplanguage; "AppLanguage"
0x1800b06e3  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b06e7  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x1800b06ec  test    eax, eax
0x1800b06ee  jz      short loc_1800B0702
0x1800b06f0  lea     r9, aFailedToAddApp_0; "Failed to add applanguage [%d]"
0x1800b06f7  mov     r8d, 888h
0x1800b06fd  jmp     loc_1800B097D
0x1800b0702  lea     r9, [rbx+6A0h]; unsigned __int16 *
0x1800b0709  mov     rax, [rbp+460h+var_4D0]
0x1800b070d  mov     [rsp+560h+var_540], rax; unsigned __int64
0x1800b0712  lea     r8, aPinneddllname; "PinnedDllName"
0x1800b0719  lea     rcx, [rbp+460h+var_4E0]; this
0x1800b071d  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
  ... truncated ...
```
