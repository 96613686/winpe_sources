# DdcCommandController::HandleCommandData(ulong,ulong,ulong,uchar *,ulong,MdmCommandChannelType,_FILETIME)

- ea: `0x180006230`
- end: `0x1800063ed`
- name: `?HandleCommandData@DdcCommandController@@CAJKKKPEAEKW4MdmCommandChannelType@@U_FILETIME@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(int, unsigned int, unsigned int, const void *, unsigned int SourceSize, int, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006748`
- `0x1800071d0`

## callees

- `0x180003288`
- `0x1800050b8`
- `0x180006230`
- `0x180007350`
- `0x1800079c4`

## string_xrefs

- `0x1800063d4`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandcontroller.cpp`
- `0x18000629a`: `CBR(cbCommandDataWithPrefix <= 4096)`
- `0x1800062fe`: `CPR(pbCommandDataWithPrefix)`
- `0x180006347`: `CBR(memcpy_s(pbCommandDataWithPrefix, cbCommandDataWithPrefix, (BYTE *)&prefix, sizeof(CommandPrefix)) == 0)`
- `0x180006386`: `CBR(memcpy_s(pbCommandDataWithPrefix + sizeof(CommandPrefix), cbCommandDataWithPrefix - sizeof(CommandPrefix), pbCommandData, cbCommandData) == 0)`
- `0x1800063bd`: `CHR(NotifyClient(PARSED_COMMAND_WNF_STATE, pbCommandDataWithPrefix, cbCommandDataWithPrefix))`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DdcCommandController::HandleCommandData(
        int a1,
        unsigned int a2,
        unsigned int a3,
        const void *a4,
        unsigned int SourceSize,
        int a6,
        __int64 a7)
{
  unsigned int v8; // ebx
  __int64 v9; // rbx
  unsigned __int8 *v10; // rax
  int v11; // edx
  int v12; // ecx
  unsigned __int8 *v13; // rdi
  int v14; // edx
  int v15; // ecx
  int v16; // edx
  int v17; // ecx
  char v19; // [rsp+20h] [rbp-58h]
  const char *v20; // [rsp+28h] [rbp-50h]
  unsigned __int64 Source; // [rsp+30h] [rbp-48h] BYREF
  __int128 v22; // [rsp+38h] [rbp-40h]

  if ( a1 != 6 )
  {
    v8 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        a1,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        230,
        "CBR(dwProfileId == FMP_PROFILE_ID)",
        Source,
        v22);
    return v8;
  }
  v9 = SourceSize + 20;
  if ( (unsigned int)v9 > 0x1000 )
  {
    v8 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        6,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        234,
        "CBR(cbCommandDataWithPrefix <= 4096)",
        Source,
        v22);
    return v8;
  }
  LODWORD(v22) = a6;
  Source = __PAIR64__(a3, a2);
  *(_QWORD *)((char *)&v22 + 4) = a7;
  v10 = (unsigned __int8 *)operator new[]((unsigned int)v9, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v10;
  if ( !v10 )
  {
    v8 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      return v8;
    v20 = "CPR(pbCommandDataWithPrefix)";
    v19 = -13;
    goto LABEL_19;
  }
  if ( memcpy_s(v10, (unsigned int)v9, &Source, 0x14u) )
  {
    v8 = -2147467259;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v15,
        v14,
        -2147467259,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        249,
        "CBR(memcpy_s(pbCommandDataWithPrefix, cbCommandDataWithPrefix, (BYTE *)&prefix, sizeof(CommandPrefix)) == 0)",
        Source,
        v22);
  }
  else
  {
    if ( !memcpy_s(v13 + 20, v9 - 20, a4, SourceSize) )
    {
      v8 = DdcCommandController::NotifyClient(stru_180049258, v13, v9);
      if ( (v8 & 0x80000000) == 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        return v8;
      v20 = "CHR(NotifyClient(PARSED_COMMAND_WNF_STATE, pbCommandDataWithPrefix, cbCommandDataWithPrefix))";
      v19 = 4;
LABEL_19:
      McTemplateU0dsqs_EventWriteTransfer(
        v12,
        v11,
        v8,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        v19,
        v20,
        Source,
        v22);
      return v8;
    }
    v8 = -2147467259;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v17,
        v16,
        -2147467259,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandcontroller.cpp",
        255,
        "CBR(memcpy_s(pbCommandDataWithPrefix + sizeof(CommandPrefix), cbCommandDataWithPrefix - sizeof(CommandPrefix), p"
        "bCommandData, cbCommandData) == 0)",
        Source,
        v22);
  }
  return v8;
}

```

## disassembly

```asm
0x180006230  push    rbx
0x180006232  push    rbp
0x180006233  push    rsi
0x180006234  push    rdi
0x180006235  push    r14
0x180006237  sub     rsp, 50h
0x18000623b  mov     r14, r9
0x18000623e  cmp     ecx, 6
0x180006241  jz      short loc_180006272
0x180006243  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000624a  mov     r8d, 80070057h
0x180006250  mov     ebx, r8d
0x180006253  jz      loc_1800063E0
0x180006259  lea     rax, aCbrDwprofileid; "CBR(dwProfileId == FMP_PROFILE_ID)"
0x180006260  mov     [rsp+78h+var_50], rax
0x180006265  mov     dword ptr [rsp+78h+var_58], 0E6h
0x18000626d  jmp     loc_1800063D4
0x180006272  mov     esi, dword ptr [rsp+78h+SourceSize]
0x180006279  lea     ebx, [rsi+14h]
0x18000627c  cmp     ebx, 1000h
0x180006282  jbe     short loc_1800062B3
0x180006284  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000628b  mov     r8d, 80070057h
0x180006291  mov     ebx, r8d
0x180006294  jz      loc_1800063E0
0x18000629a  lea     rax, aCbrCbcommandda; "CBR(cbCommandDataWithPrefix <= 4096)"
0x1800062a1  mov     [rsp+78h+var_50], rax
0x1800062a6  mov     dword ptr [rsp+78h+var_58], 0EAh
0x1800062ae  jmp     loc_1800063D4
0x1800062b3  mov     eax, [rsp+78h+arg_28]
0x1800062ba  mov     dword ptr [rsp+78h+var_40], eax
0x1800062be  mov     rax, [rsp+78h+arg_30]
0x1800062c6  mov     [rsp+78h+Source], edx
0x1800062ca  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800062d1  mov     ecx, ebx; unsigned __int64
0x1800062d3  mov     qword ptr [rsp+78h+var_40+4], rax
0x1800062d8  mov     [rsp+78h+var_44], r8d
0x1800062dd  mov     ebp, ebx
0x1800062df  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800062e4  mov     rdi, rax
0x1800062e7  test    rax, rax
0x1800062ea  jnz     short loc_180006317
0x1800062ec  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800062f3  mov     ebx, 8007000Eh
0x1800062f8  jz      loc_1800063E0
0x1800062fe  lea     rax, aCprPbcommandda; "CPR(pbCommandDataWithPrefix)"
0x180006305  mov     [rsp+78h+var_50], rax
0x18000630a  mov     dword ptr [rsp+78h+var_58], 0F3h
0x180006312  jmp     loc_1800063D1
0x180006317  mov     r9d, 14h; SourceSize
0x18000631d  lea     r8, [rsp+78h+Source]; Source
0x180006322  mov     rdx, rbp; DestinationSize
0x180006325  mov     rcx, rdi; Destination
0x180006328  call    memcpy_s
0x18000632d  test    eax, eax
0x18000632f  jz      short loc_18000635D
0x180006331  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180006338  mov     r8d, 80004005h
0x18000633e  mov     ebx, r8d
0x180006341  jz      loc_1800063E0
0x180006347  lea     rax, aCbrMemcpySPbco_0; "CBR(memcpy_s(pbCommandDataWithPrefix, c"...
0x18000634e  mov     [rsp+78h+var_50], rax
0x180006353  mov     dword ptr [rsp+78h+var_58], 0F9h
0x18000635b  jmp     short loc_1800063D4
0x18000635d  mov     r9, rsi; SourceSize
0x180006360  lea     rdx, [rbx-14h]; DestinationSize
0x180006364  lea     rcx, [rdi+14h]; Destination
0x180006368  mov     r8, r14; Source
0x18000636b  call    memcpy_s
0x180006370  test    eax, eax
0x180006372  jz      short loc_18000639C
0x180006374  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000637b  mov     r8d, 80004005h
0x180006381  mov     ebx, r8d
0x180006384  jz      short loc_1800063E0
0x180006386  lea     rax, aCbrMemcpySPbco; "CBR(memcpy_s(pbCommandDataWithPrefix + "...
0x18000638d  mov     [rsp+78h+var_50], rax
0x180006392  mov     dword ptr [rsp+78h+var_58], 0FFh
0x18000639a  jmp     short loc_1800063D4
0x18000639c  mov     rcx, qword ptr cs:stru_180049258.Data; struct _WNF_STATE_NAME
0x1800063a3  mov     r8d, ebx; unsigned int
0x1800063a6  mov     rdx, rdi; unsigned __int8 *
0x1800063a9  call    ?NotifyClient@DdcCommandController@@SAJU_WNF_STATE_NAME@@PEAEK@Z; DdcCommandController::NotifyClient(_WNF_STATE_NAME,uchar *,ulong)
0x1800063ae  mov     ebx, eax
0x1800063b0  test    eax, eax
0x1800063b2  jns     short loc_1800063E0
0x1800063b4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800063bb  jz      short loc_1800063E0
0x1800063bd  lea     rax, aChrNotifyclien; "CHR(NotifyClient(PARSED_COMMAND_WNF_STA"...
0x1800063c4  mov     [rsp+78h+var_50], rax
0x1800063c9  mov     dword ptr [rsp+78h+var_58], 104h
0x1800063d1  mov     r8d, ebx
0x1800063d4  lea     r9, aOnecoreuapShel_13; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800063db  call    McTemplateU0dsqs_EventWriteTransfer
0x1800063e0  mov     eax, ebx
0x1800063e2  add     rsp, 50h
0x1800063e6  pop     r14
0x1800063e8  pop     rdi
0x1800063e9  pop     rsi
0x1800063ea  pop     rbp
0x1800063eb  pop     rbx
0x1800063ec  retn
```
