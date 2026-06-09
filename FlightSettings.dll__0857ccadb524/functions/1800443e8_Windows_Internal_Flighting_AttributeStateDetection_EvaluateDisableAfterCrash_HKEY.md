# Windows::Internal::Flighting::AttributeStateDetection::EvaluateDisableAfterCrash(HKEY__ *)

- ea: `0x1800443e8`
- end: `0x18004474d`
- name: `?EvaluateDisableAfterCrash@AttributeStateDetection@Flighting@Internal@Windows@@QEAAJPEAUHKEY__@@@Z`
- size: `869`
- prototype: `int(Windows::Internal::Flighting::AttributeStateDetection *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004565c`

## callees

- `0x18000cc8c`
- `0x1800443e8`
- `0x18004588c`
- `0x180045914`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004444f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800444bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044509`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004466b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004444f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800444bb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180044509`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004466b`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800445a4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800446bb`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800446ff`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800445a4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800446bb`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800446ff`

## string_xrefs

- `0x180044474`: `onecore\base\flighting\flightsettings\broker\libs\ctac\attributestatedetection.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Flighting::AttributeStateDetection::EvaluateDisableAfterCrash(
        Windows::Internal::Flighting::AttributeStateDetection *this,
        HKEY a2)
{
  unsigned int v2; // r14d
  LSTATUS ValueW; // eax
  signed int v6; // ebx
  __int64 v7; // rdx
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  LSTATUS v11; // eax
  LSTATUS v12; // eax
  bool v13; // sf
  DWORD v14; // ecx
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  int pdwType; // [rsp+20h] [rbp-30h]
  LPDWORD pdwTypea; // [rsp+20h] [rbp-30h]
  LPDWORD pdwTypeb; // [rsp+20h] [rbp-30h]
  LPDWORD pdwTypec; // [rsp+20h] [rbp-30h]
  unsigned int pvData; // [rsp+28h] [rbp-28h]
  int pvDataa; // [rsp+28h] [rbp-28h]
  int pcbData; // [rsp+30h] [rbp-20h]
  unsigned int v24; // [rsp+40h] [rbp-10h] BYREF
  DWORD Data; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  unsigned int v27; // [rsp+98h] [rbp+48h] BYREF
  int v28; // [rsp+A0h] [rbp+50h] BYREF
  int v29; // [rsp+A8h] [rbp+58h] BYREF

  v2 = 5;
  v27 = 0;
  v24 = 5;
  v28 = 5;
  v29 = 0;
  Data = 4;
  ValueW = RegGetValueW(a2, 0, L"CrashCount", 0x10u, 0, &v27, &Data);
  v6 = ValueW;
  if ( ValueW > 0 )
    v6 = (unsigned __int16)ValueW | 0x80070000;
  if ( v6 < 0 )
  {
    v7 = 515;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\attributestatedetection.cpp",
      (const char *)(unsigned int)v6,
      pdwType);
    return (unsigned int)v6;
  }
  Data = 4;
  v9 = RegGetValueW(a2, 0, L"CrashThreshold", 0x10u, 0, &v24, &Data);
  v6 = v9;
  if ( v9 > 0 )
    v6 = (unsigned __int16)v9 | 0x80070000;
  if ( v6 < 0 )
  {
    v7 = 520;
    goto LABEL_5;
  }
  Data = 4;
  v10 = RegGetValueW(a2, 0, L"Disabled", 0x10u, 0, &v29, &Data);
  v6 = v10;
  if ( v10 > 0 )
    v6 = (unsigned __int16)v10 | 0x80070000;
  if ( v6 < 0 )
  {
    v7 = 525;
    goto LABEL_5;
  }
  if ( v27 )
  {
    pvData = v27;
    pdwTypea = (LPDWORD)*((_QWORD *)this + 36);
    Windows::Internal::Flighting::AttributeStateDetection::RecordAttributeCollectionEvent(
      this,
      *((_QWORD *)this + 21),
      3,
      *((_QWORD *)this + 18));
    if ( v29 || v27 < v24 )
    {
      LODWORD(pdwTypea) = v27;
      Windows::Internal::Flighting::AttributeStateDetection::RecordAttributeStateEvent(
        this,
        *((_QWORD *)this + 21),
        3,
        *((_QWORD *)this + 18),
        pdwTypea,
        pvData,
        0);
    }
    else
    {
      Data = 1;
      v11 = RegSetKeyValueW(a2, 0, L"Disabled", 4u, &Data, 4u);
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      if ( v6 < 0 )
      {
        v7 = 542;
        goto LABEL_5;
      }
      pdwTypeb = (LPDWORD)*((_QWORD *)this + 36);
      Windows::Internal::Flighting::AttributeStateDetection::RecordAttributeCollectionEvent(
        this,
        *((_QWORD *)this + 21),
        1,
        *((_QWORD *)this + 18));
      LODWORD(pdwTypeb) = v27;
      Windows::Internal::Flighting::AttributeStateDetection::RecordAttributeStateEvent(
        this,
        *((_QWORD *)this + 21),
        3,
        *((_QWORD *)this + 18),
        pdwTypeb,
        1,
        0);
      LODWORD(pdwTypec) = 0;
      Windows::Internal::Flighting::AttributeStateDetection::RecordAttributeStateEvent(
        this,
        *((_QWORD *)this + 21),
        1,
        *((_QWORD *)this + 18),
        pdwTypec,
        pvDataa,
        pcbData);
      Data = 4;
      v12 = RegGetValueW(a2, 0, L"SkipThreshold", 0x10u, 0, &v28, &Data);
      v13 = v12 < 0;
      if ( v12 > 0 )
        v13 = 1;
      if ( v13 )
        v28 = 5;
      else
        v2 = v28;
      v14 = 100;
      if ( 2 * (unsigned __int64)v2 <= 0x64 )
        v14 = 2 * v2;
      Data = v14;
      v15 = RegSetKeyValueW(a2, 0, L"SkipThreshold", 4u, &Data, 4u);
      v6 = v15;
      if ( v15 > 0 )
        v6 = (unsigned __int16)v15 | 0x80070000;
      if ( v6 < 0 )
      {
        v7 = 582;
        goto LABEL_5;
      }
      Data = 0;
      v16 = RegSetKeyValueW(a2, 0, L"SkipCount", 4u, &Data, 4u);
      v6 = v16;
      if ( v16 > 0 )
        v6 = (unsigned __int16)v16 | 0x80070000;
      if ( v6 < 0 )
      {
        v7 = 587;
        goto LABEL_5;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800443e8  push    rbp
0x1800443ea  push    rbx
0x1800443eb  push    rsi
0x1800443ec  push    rdi
0x1800443ed  push    r12
0x1800443ef  push    r13
0x1800443f1  push    r14
0x1800443f3  mov     rbp, rsp
0x1800443f6  sub     rsp, 50h
0x1800443fa  mov     r14d, 5
0x180044400  mov     [rbp+arg_8], 0
0x180044407  mov     rsi, rdx
0x18004440a  mov     [rbp+var_10], r14d
0x18004440e  lea     rax, [rbp+Data]
0x180044412  mov     [rbp+arg_10], r14d
0x180044416  mov     qword ptr [rsp+50h+pcbData], rax; pcbData
0x18004441b  lea     r8, Value; "CrashCount"
0x180044422  lea     rax, [rbp+arg_8]
0x180044426  mov     [rbp+arg_18], 0
0x18004442d  mov     rdi, rcx
0x180044430  mov     [rsp+50h+pvData], rax; pvData
0x180044435  lea     r12d, [r14-1]
0x180044439  mov     [rsp+50h+pdwType], 0; int
0x180044442  lea     r9d, [r14+0Bh]; dwFlags
0x180044446  mov     [rbp+Data], r12d
0x18004444a  xor     edx, edx; lpSubKey
0x18004444c  mov     rcx, rsi; hkey
0x18004444f  call    cs:__imp_RegGetValueW
0x180044455  mov     ebx, eax
0x180044457  mov     r13d, 80070000h
0x18004445d  test    eax, eax
0x18004445f  jle     short loc_180044467
0x180044461  movzx   ebx, ax
0x180044464  or      ebx, r13d
0x180044467  test    ebx, ebx
0x180044469  jns     short loc_18004448A
0x18004446b  mov     edx, 203h; void *
0x180044470  mov     rcx, [rbp+38h]; this
0x180044474  lea     r8, aOnecoreBaseFli_60; "onecore\\base\\flighting\\flightsetting"...
0x18004447b  mov     r9d, ebx; char *
0x18004447e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044483  mov     eax, ebx
0x180044485  jmp     loc_18004473E
0x18004448a  lea     rax, [rbp+Data]
0x18004448e  mov     [rbp+Data], r12d
0x180044492  mov     qword ptr [rsp+50h+pcbData], rax; pcbData
0x180044497  lea     r8, aCrashthreshold; "CrashThreshold"
0x18004449e  lea     rax, [rbp+var_10]
0x1800444a2  mov     r9d, 10h; dwFlags
0x1800444a8  mov     [rsp+50h+pvData], rax; pvData
0x1800444ad  xor     edx, edx; lpSubKey
0x1800444af  mov     rcx, rsi; hkey
0x1800444b2  mov     [rsp+50h+pdwType], 0; pdwType
0x1800444bb  call    cs:__imp_RegGetValueW
0x1800444c1  mov     ebx, eax
0x1800444c3  test    eax, eax
0x1800444c5  jle     short loc_1800444CD
0x1800444c7  movzx   ebx, ax
0x1800444ca  or      ebx, r13d
0x1800444cd  test    ebx, ebx
0x1800444cf  jns     short loc_1800444D8
0x1800444d1  mov     edx, 208h
0x1800444d6  jmp     short loc_180044470
0x1800444d8  lea     rax, [rbp+Data]
0x1800444dc  mov     [rbp+Data], r12d
0x1800444e0  mov     qword ptr [rsp+50h+pcbData], rax; pcbData
0x1800444e5  lea     r8, aDisabled; "Disabled"
0x1800444ec  lea     rax, [rbp+arg_18]
0x1800444f0  mov     r9d, 10h; dwFlags
0x1800444f6  mov     [rsp+50h+pvData], rax; pvData
0x1800444fb  xor     edx, edx; lpSubKey
0x1800444fd  mov     rcx, rsi; hkey
0x180044500  mov     [rsp+50h+pdwType], 0; pdwType
0x180044509  call    cs:__imp_RegGetValueW
0x18004450f  mov     ebx, eax
0x180044511  test    eax, eax
0x180044513  jle     short loc_18004451B
0x180044515  movzx   ebx, ax
0x180044518  or      ebx, r13d
0x18004451b  test    ebx, ebx
0x18004451d  jns     short loc_180044529
0x18004451f  mov     edx, 20Dh
0x180044524  jmp     loc_180044470
0x180044529  mov     eax, [rbp+arg_8]
0x18004452c  test    eax, eax
0x18004452e  jz      loc_18004473C
0x180044534  mov     r9, [rdi+90h]
0x18004453b  mov     ebx, 3
0x180044540  mov     rdx, [rdi+0A8h]
0x180044547  mov     r8d, ebx
0x18004454a  mov     [rsp+50h+pcbData], 0
0x180044552  mov     rcx, rdi
0x180044555  mov     dword ptr [rsp+50h+pvData], eax
0x180044559  mov     rax, [rdi+120h]
0x180044560  mov     [rsp+50h+pdwType], rax
0x180044565  call    ?RecordAttributeCollectionEvent@AttributeStateDetection@Flighting@Internal@Windows@@AEAAXPEBGW4AttributeEventType@Telemetry@CTAC@@0_KKJ@Z; Windows::Internal::Flighting::AttributeStateDetection::RecordAttributeCollectionEvent(ushort const *,CTAC::Telemetry::AttributeEventType,ushort const *,unsigned __int64,ulong,long)
0x18004456a  cmp     [rbp+arg_18], 0
0x18004456e  mov     eax, [rbp+arg_8]
0x180044571  jnz     loc_18004471F
0x180044577  cmp     eax, [rbp+var_10]
0x18004457a  jb      loc_18004471F
0x180044580  lea     rax, [rbp+Data]
0x180044584  mov     dword ptr [rsp+50h+pvData], r12d; cbData
0x180044589  mov     r9d, r12d; dwType
0x18004458c  mov     [rsp+50h+pdwType], rax; lpData
0x180044591  lea     r8, aDisabled; "Disabled"
0x180044598  mov     [rbp+Data], 1
0x18004459f  xor     edx, edx; lpSubKey
0x1800445a1  mov     rcx, rsi; hKey
0x1800445a4  call    cs:__imp_RegSetKeyValueW
0x1800445aa  mov     ebx, eax
0x1800445ac  test    eax, eax
0x1800445ae  jle     short loc_1800445B6
0x1800445b0  movzx   ebx, ax
0x1800445b3  or      ebx, r13d
0x1800445b6  test    ebx, ebx
0x1800445b8  jns     short loc_1800445C4
0x1800445ba  mov     edx, 21Eh
0x1800445bf  jmp     loc_180044470
0x1800445c4  mov     rax, [rdi+120h]
0x1800445cb  mov     ebx, 1
0x1800445d0  mov     r9, [rdi+90h]
0x1800445d7  mov     r8d, ebx
0x1800445da  mov     rdx, [rdi+0A8h]
0x1800445e1  mov     rcx, rdi
0x1800445e4  mov     [rsp+50h+pcbData], 0
0x1800445ec  mov     dword ptr [rsp+50h+pvData], ebx
0x1800445f0  mov     [rsp+50h+pdwType], rax
0x1800445f5  call    ?RecordAttributeCollectionEvent@AttributeStateDetection@Flighting@Internal@Windows@@AEAAXPEBGW4AttributeEventType@Telemetry@CTAC@@0_KKJ@Z; Windows::Internal::Flighting::AttributeStateDetection::RecordAttributeCollectionEvent(ushort const *,CTAC::Telemetry::AttributeEventType,ushort const *,unsigned __int64,ulong,long)
0x1800445fa  mov     eax, [rbp+arg_8]
0x1800445fd  lea     r8d, [rbx+2]
0x180044601  mov     r9, [rdi+90h]
0x180044608  mov     rcx, rdi
0x18004460b  mov     rdx, [rdi+0A8h]
0x180044612  mov     dword ptr [rsp+50h+pdwType], eax
0x180044616  call    ?RecordAttributeStateEvent@AttributeStateDetection@Flighting@Internal@Windows@@AEAAXPEBGW4AttributeEventType@Telemetry@CTAC@@0K@Z; Windows::Internal::Flighting::AttributeStateDetection::RecordAttributeStateEvent(ushort const *,CTAC::Telemetry::AttributeEventType,ushort const *,ulong)
0x18004461b  mov     r9, [rdi+90h]
0x180044622  mov     r8d, ebx
0x180044625  mov     rdx, [rdi+0A8h]
0x18004462c  mov     rcx, rdi
0x18004462f  mov     dword ptr [rsp+50h+pdwType], 0
0x180044637  call    ?RecordAttributeStateEvent@AttributeStateDetection@Flighting@Internal@Windows@@AEAAXPEBGW4AttributeEventType@Telemetry@CTAC@@0K@Z; Windows::Internal::Flighting::AttributeStateDetection::RecordAttributeStateEvent(ushort const *,CTAC::Telemetry::AttributeEventType,ushort const *,ulong)
0x18004463c  lea     rax, [rbp+Data]
0x180044640  mov     [rbp+Data], r12d
0x180044644  mov     qword ptr [rsp+50h+pcbData], rax; pcbData
0x180044649  lea     r9d, [rbx+0Fh]; dwFlags
0x18004464d  lea     rax, [rbp+arg_10]
0x180044651  xor     edx, edx; lpSubKey
0x180044653  mov     [rsp+50h+pvData], rax; pvData
0x180044658  lea     r8, aSkipthreshold; "SkipThreshold"
0x18004465f  mov     rcx, rsi; hkey
0x180044662  mov     [rsp+50h+pdwType], 0; pdwType
0x18004466b  call    cs:__imp_RegGetValueW
0x180044671  test    eax, eax
0x180044673  jle     short loc_18004467D
0x180044675  movzx   eax, ax
0x180044678  or      eax, r13d
0x18004467b  test    eax, eax
0x18004467d  jns     short loc_180044685
0x18004467f  mov     [rbp+arg_10], r14d
0x180044683  jmp     short loc_180044689
0x180044685  mov     r14d, [rbp+arg_10]
0x180044689  mov     eax, r14d
0x18004468c  mov     ecx, 64h ; 'd'
0x180044691  add     rax, rax
0x180044694  cmp     rax, rcx
0x180044697  ja      short loc_18004469B
0x180044699  mov     ecx, eax
0x18004469b  mov     [rbp+Data], ecx
0x18004469e  lea     rax, [rbp+Data]
0x1800446a2  mov     rcx, rsi; hKey
0x1800446a5  mov     dword ptr [rsp+50h+pvData], r12d; cbData
0x1800446aa  mov     r9d, r12d; dwType
0x1800446ad  mov     [rsp+50h+pdwType], rax; lpData
0x1800446b2  lea     r8, aSkipthreshold; "SkipThreshold"
0x1800446b9  xor     edx, edx; lpSubKey
0x1800446bb  call    cs:__imp_RegSetKeyValueW
0x1800446c1  mov     ebx, eax
0x1800446c3  test    eax, eax
0x1800446c5  jle     short loc_1800446CD
0x1800446c7  movzx   ebx, ax
0x1800446ca  or      ebx, r13d
0x1800446cd  test    ebx, ebx
0x1800446cf  jns     short loc_1800446DB
0x1800446d1  mov     edx, 246h
0x1800446d6  jmp     loc_180044470
0x1800446db  lea     rax, [rbp+Data]
0x1800446df  mov     dword ptr [rsp+50h+pvData], r12d; cbData
0x1800446e4  mov     r9d, r12d; dwType
0x1800446e7  mov     [rsp+50h+pdwType], rax; lpData
0x1800446ec  lea     r8, aSkipcount; "SkipCount"
0x1800446f3  mov     [rbp+Data], 0
0x1800446fa  xor     edx, edx; lpSubKey
0x1800446fc  mov     rcx, rsi; hKey
0x1800446ff  call    cs:__imp_RegSetKeyValueW
0x180044705  mov     ebx, eax
0x180044707  test    eax, eax
0x180044709  jle     short loc_180044711
0x18004470b  movzx   ebx, ax
0x18004470e  or      ebx, r13d
0x180044711  test    ebx, ebx
0x180044713  jns     short loc_18004473C
0x180044715  mov     edx, 24Bh
0x18004471a  jmp     loc_180044470
0x18004471f  mov     r9, [rdi+90h]
0x180044726  mov     r8d, ebx
0x180044729  mov     rdx, [rdi+0A8h]
0x180044730  mov     rcx, rdi
0x180044733  mov     dword ptr [rsp+50h+pdwType], eax
0x180044737  call    ?RecordAttributeStateEvent@AttributeStateDetection@Flighting@Internal@Windows@@AEAAXPEBGW4AttributeEventType@Telemetry@CTAC@@0K@Z; Windows::Internal::Flighting::AttributeStateDetection::RecordAttributeStateEvent(ushort const *,CTAC::Telemetry::AttributeEventType,ushort const *,ulong)
0x18004473c  xor     eax, eax
0x18004473e  add     rsp, 50h
0x180044742  pop     r14
0x180044744  pop     r13
0x180044746  pop     r12
0x180044748  pop     rdi
0x180044749  pop     rsi
0x18004474a  pop     rbx
0x18004474b  pop     rbp
0x18004474c  retn
```
