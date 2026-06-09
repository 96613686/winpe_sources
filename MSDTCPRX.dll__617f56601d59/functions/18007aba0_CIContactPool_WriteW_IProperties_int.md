# CIContactPool::WriteW(IProperties *,int)

- ea: `0x18007aba0`
- end: `0x18007afa4`
- name: `?WriteW@CIContactPool@@UEAAJPEAUIProperties@@H@Z`
- size: `1028`
- prototype: `__int64 __fastcall(CIContactPool *__hidden this, struct IProperties *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180079eac`
- `0x18007aba0`
- `0x18007afac`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `RPCRT4!RpcStringFreeA` at `0x18007add4`
- `RPCRT4!RpcStringFreeA` at `0x18007add4`
- `RPCRT4!UuidToStringA` at `0x18007adb5`
- `RPCRT4!UuidToStringA` at `0x18007adb5`

## string_xrefs

- `0x18007af44`: `com\complus\dtc\shared\util\cp_cicp.cpp`
- `0x18007af4b`: `CIContactPool::WriteW`
- `0x18007ac97`: `CreateConnectedContactRegistry failed.`
- `0x18007ad05`: `WriteProperty failed.`
- `0x18007ae2f`: `WriteProperty failed.`
- `0x18007ae9c`: `WriteProperty failed.`
- `0x18007af09`: `WriteProperty failed.`
- `0x18007ad75`: `WritePropertyW failed.`
- `0x18007ae60`: `GetProtocol failed.`

## pseudocode

```c
__int64 __fastcall CIContactPool::WriteW(CIContactPool *this, struct IProperties *a2, int a3)
{
  int v6; // ebx
  const wchar_t *v7; // rax
  __int64 v8; // r9
  int v9; // eax
  struct _GUID *v10; // r9
  __int64 v11; // [rsp+28h] [rbp-D8h]
  struct IContactRegistry *v12; // [rsp+40h] [rbp-C0h] BYREF
  int v13; // [rsp+48h] [rbp-B8h] BYREF
  RPC_CSTR StringUuid; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v15; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID v16; // [rsp+68h] [rbp-98h] BYREF
  UUID Uuid; // [rsp+78h] [rbp-88h] BYREF
  char v18[256]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v19[512]; // [rsp+190h] [rbp+90h] BYREF

  v12 = 0;
  v13 = 0;
  v16 = 0;
  v15 = 0;
  Uuid = 0;
  if ( a3 == 1 )
    return 2147500033LL;
  v6 = (*(__int64 (__fastcall **)(struct IProperties *, struct _GUID *))(*(_QWORD *)a2 + 24LL))(a2, &v16);
  if ( v6 < 0 )
  {
    v7 = L"GetContactId failed.";
    v8 = 421;
LABEL_34:
    LODWORD(v11) = v6;
    TraceStringInline(7, 1, L"com\\complus\\dtc\\shared\\util\\cp_cicp.cpp", v8, L"CIContactPool::WriteW", v11, v7);
    goto LABEL_35;
  }
  v9 = (*(__int64 (__fastcall **)(struct IProperties *, __int128 *, int *))(*(_QWORD *)a2 + 112LL))(a2, &v15, &v13);
  v10 = (struct _GUID *)&v15;
  if ( v9 == -2146435003 )
    v10 = 0;
  v6 = CIContactPool::CreateConnectedContactRegistry(this, 2u, &v16, 0, v10, v13, &v12);
  if ( v6 < 0 )
  {
    v7 = L"CreateConnectedContactRegistry failed.";
    v8 = 429;
    goto LABEL_34;
  }
  v6 = (*(__int64 (__fastcall **)(struct IProperties *, char *, __int64))(*(_QWORD *)a2 + 32LL))(a2, v18, 256);
  if ( v6 < 0 )
  {
    v7 = L"GetDescription failed.";
    v8 = 437;
    goto LABEL_34;
  }
  v6 = (*(__int64 (__fastcall **)(struct IContactRegistry *, __int64, _QWORD, _QWORD, char *))(*(_QWORD *)v12 + 64LL))(
         v12,
         1,
         0,
         0,
         v18);
  if ( v6 < 0 )
  {
    v7 = L"WriteProperty failed.";
    v8 = 444;
    goto LABEL_34;
  }
  v6 = (*(__int64 (__fastcall **)(struct IProperties *, _BYTE *, __int64))(*(_QWORD *)a2 + 72LL))(a2, v19, 256);
  if ( v6 < 0 )
  {
    v7 = L"GetHostW failed.";
    v8 = 452;
    goto LABEL_34;
  }
  v6 = (*(__int64 (__fastcall **)(struct IContactRegistry *, __int64, _QWORD))(*(_QWORD *)v12 + 72LL))(v12, 2, 0);
  if ( v6 < 0 )
  {
    v7 = L"WritePropertyW failed.";
    v8 = 459;
    goto LABEL_34;
  }
  if ( (*(unsigned int (__fastcall **)(struct IProperties *, UUID *))(*(_QWORD *)a2 + 96LL))(a2, &Uuid) == -2146435003 )
  {
    vstrcpy(v18, 0x100u, Class);
  }
  else
  {
    StringUuid = 0;
    if ( UuidToStringA(&Uuid, &StringUuid) )
    {
      v6 = -2147024882;
      v7 = L"ConvertGuidToTString failed.";
      v8 = 470;
      goto LABEL_34;
    }
    vstrcpy(v18, 0x100u, (const char *)StringUuid);
    RpcStringFreeA(&StringUuid);
  }
  v6 = (*(__int64 (__fastcall **)(struct IContactRegistry *, __int64, _QWORD))(*(_QWORD *)v12 + 64LL))(v12, 3, 0);
  if ( v6 < 0 )
  {
    v7 = L"WriteProperty failed.";
    v8 = 482;
    goto LABEL_34;
  }
  v6 = (*(__int64 (__fastcall **)(struct IProperties *, char *, __int64))(*(_QWORD *)a2 + 128LL))(a2, v18, 256);
  if ( v6 < 0 )
  {
    v7 = L"GetProtocol failed.";
    v8 = 490;
    goto LABEL_34;
  }
  v6 = (*(__int64 (__fastcall **)(struct IContactRegistry *, __int64, _QWORD))(*(_QWORD *)v12 + 64LL))(v12, 5, 0);
  if ( v6 < 0 )
  {
    v7 = L"WriteProperty failed.";
    v8 = 497;
    goto LABEL_34;
  }
  v6 = (*(__int64 (__fastcall **)(struct IProperties *, char *, __int64))(*(_QWORD *)a2 + 152LL))(a2, v18, 256);
  if ( v6 < 0 )
  {
    v7 = L"GetEndpoint failed.";
    v8 = 505;
    goto LABEL_34;
  }
  v6 = (*(__int64 (__fastcall **)(struct IContactRegistry *, __int64, _QWORD))(*(_QWORD *)v12 + 64LL))(v12, 6, 0);
  if ( v6 < 0 )
  {
    v7 = L"WriteProperty failed.";
    v8 = 512;
    goto LABEL_34;
  }
  v6 = (*(__int64 (__fastcall **)(struct IContactRegistry *, __int64))(*(_QWORD *)v12 + 80LL))(v12, 1);
  if ( v6 < 0 )
  {
    v7 = L"Disconnect failed.";
    v8 = 521;
    goto LABEL_34;
  }
LABEL_35:
  if ( v12 )
    (*(void (__fastcall **)(struct IContactRegistry *))(*(_QWORD *)v12 + 16LL))(v12);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007aba0  mov     [rsp-8+arg_10], rbx
0x18007aba5  mov     [rsp-8+arg_18], rsi
0x18007abaa  push    rbp
0x18007abab  push    rdi
0x18007abac  push    r15
0x18007abae  lea     rbp, [rsp-2A0h]
0x18007abb6  sub     rsp, 3A0h
0x18007abbd  mov     rax, cs:__security_cookie
0x18007abc4  xor     rax, rsp
0x18007abc7  mov     [rbp+2B0h+var_20], rax
0x18007abce  xorps   xmm0, xmm0
0x18007abd1  mov     [rsp+3B0h+var_370], 0
0x18007abda  mov     r15d, 1
0x18007abe0  mov     [rsp+3B0h+var_368], 0
0x18007abe8  xorps   xmm1, xmm1
0x18007abeb  mov     rdi, rdx
0x18007abee  mov     rsi, rcx
0x18007abf1  movups  xmmword ptr [rsp+3B0h+var_348.Data1], xmm0
0x18007abf6  movups  [rsp+3B0h+var_358], xmm1
0x18007abfb  movups  xmmword ptr [rsp+3B0h+Uuid.Data1], xmm0
0x18007ac00  cmp     r8d, r15d
0x18007ac03  jnz     short loc_18007AC0F
0x18007ac05  mov     eax, 80004001h
0x18007ac0a  jmp     loc_18007AF7D
0x18007ac0f  mov     rax, [rdx]
0x18007ac12  mov     rcx, rdi
0x18007ac15  lea     rdx, [rsp+3B0h+var_348]
0x18007ac1a  mov     rax, [rax+18h]
0x18007ac1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ac23  mov     ebx, eax
0x18007ac25  test    eax, eax
0x18007ac27  jns     short loc_18007AC3B
0x18007ac29  lea     rax, aGetcontactidFa; "GetContactId failed."
0x18007ac30  mov     r9d, 1A5h
0x18007ac36  jmp     loc_18007AF3C
0x18007ac3b  mov     rax, [rdi]
0x18007ac3e  lea     r8, [rsp+3B0h+var_368]
0x18007ac43  lea     rdx, [rsp+3B0h+var_358]
0x18007ac48  mov     rcx, rdi
0x18007ac4b  mov     rax, [rax+70h]
0x18007ac4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ac54  mov     r8d, [rsp+3B0h+var_368]
0x18007ac59  lea     r9, [rsp+3B0h+var_358]
0x18007ac5e  xor     edx, edx
0x18007ac60  mov     rcx, rsi; this
0x18007ac63  cmp     eax, 80100045h
0x18007ac68  lea     rax, [rsp+3B0h+var_370]
0x18007ac6d  mov     [rsp+3B0h+var_380], rax; struct IContactRegistry **
0x18007ac72  cmovz   r9, rdx
0x18007ac76  mov     dword ptr [rsp+3B0h+var_388], r8d; int
0x18007ac7b  mov     [rsp+3B0h+var_390], r9; struct _GUID *
0x18007ac80  lea     r8, [rsp+3B0h+var_348]; struct _GUID *
0x18007ac85  xor     r9d, r9d; unsigned __int16 *
0x18007ac88  lea     edx, [r9+2]; unsigned int
0x18007ac8c  call    ?CreateConnectedContactRegistry@CIContactPool@@AEAAJKPEAU_GUID@@PEBG0HPEAPEAUIContactRegistry@@@Z; CIContactPool::CreateConnectedContactRegistry(ulong,_GUID *,ushort const *,_GUID *,int,IContactRegistry * *)
0x18007ac91  mov     ebx, eax
0x18007ac93  test    eax, eax
0x18007ac95  jns     short loc_18007ACA9
0x18007ac97  lea     rax, aCreateconnecte; "CreateConnectedContactRegistry failed."
0x18007ac9e  mov     r9d, 1ADh
0x18007aca4  jmp     loc_18007AF3C
0x18007aca9  mov     rax, [rdi]
0x18007acac  lea     rdx, [rbp+2B0h+var_320]
0x18007acb0  mov     esi, 100h
0x18007acb5  mov     rcx, rdi
0x18007acb8  mov     r8d, esi
0x18007acbb  mov     rax, [rax+20h]
0x18007acbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007acc4  mov     ebx, eax
0x18007acc6  test    eax, eax
0x18007acc8  jns     short loc_18007ACDC
0x18007acca  lea     rax, aGetdescription; "GetDescription failed."
0x18007acd1  mov     r9d, 1B5h
0x18007acd7  jmp     loc_18007AF3C
0x18007acdc  mov     rcx, [rsp+3B0h+var_370]
0x18007ace1  lea     rdx, [rbp+2B0h+var_320]
0x18007ace5  mov     [rsp+3B0h+var_390], rdx
0x18007acea  xor     r9d, r9d
0x18007aced  xor     r8d, r8d
0x18007acf0  mov     edx, r15d
0x18007acf3  mov     rax, [rcx]
0x18007acf6  mov     rax, [rax+40h]
0x18007acfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007acff  mov     ebx, eax
0x18007ad01  test    eax, eax
0x18007ad03  jns     short loc_18007AD17
0x18007ad05  lea     rax, aWritepropertyF; "WriteProperty failed."
0x18007ad0c  mov     r9d, 1BCh
0x18007ad12  jmp     loc_18007AF3C
0x18007ad17  mov     rax, [rdi]
0x18007ad1a  lea     rdx, [rbp+2B0h+var_220]
0x18007ad21  mov     r8d, esi
0x18007ad24  mov     rcx, rdi
0x18007ad27  mov     rax, [rax+48h]
0x18007ad2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ad30  mov     ebx, eax
0x18007ad32  test    eax, eax
0x18007ad34  jns     short loc_18007AD48
0x18007ad36  lea     rax, aGethostwFailed; "GetHostW failed."
0x18007ad3d  mov     r9d, 1C4h
0x18007ad43  jmp     loc_18007AF3C
0x18007ad48  mov     rcx, [rsp+3B0h+var_370]
0x18007ad4d  lea     r8, [rbp+2B0h+var_220]
0x18007ad54  xor     r9d, r9d
0x18007ad57  mov     [rsp+3B0h+var_390], r8
0x18007ad5c  xor     r8d, r8d
0x18007ad5f  mov     rax, [rcx]
0x18007ad62  lea     edx, [r9+2]
0x18007ad66  mov     rax, [rax+48h]
0x18007ad6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ad6f  mov     ebx, eax
0x18007ad71  test    eax, eax
0x18007ad73  jns     short loc_18007AD87
0x18007ad75  lea     rax, aWritepropertyw; "WritePropertyW failed."
0x18007ad7c  mov     r9d, 1CBh
0x18007ad82  jmp     loc_18007AF3C
0x18007ad87  mov     rax, [rdi]
0x18007ad8a  lea     rdx, [rsp+3B0h+Uuid]
0x18007ad8f  mov     rcx, rdi
0x18007ad92  mov     rax, [rax+60h]
0x18007ad96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ad9b  cmp     eax, 80100045h
0x18007ada0  jz      short loc_18007ADF3
0x18007ada2  lea     rdx, [rsp+3B0h+StringUuid]; StringUuid
0x18007ada7  mov     [rsp+3B0h+StringUuid], 0
0x18007adb0  lea     rcx, [rsp+3B0h+Uuid]; Uuid
0x18007adb5  call    cs:__imp_UuidToStringA
0x18007adbb  test    eax, eax
0x18007adbd  jnz     short loc_18007ADDC
0x18007adbf  mov     r8, [rsp+3B0h+StringUuid]; char *
0x18007adc4  lea     rcx, [rbp+2B0h+var_320]; char *
0x18007adc8  mov     edx, esi; unsigned int
0x18007adca  call    ?vstrcpy@@YAPEADPEADKPEBD@Z; vstrcpy(char *,ulong,char const *)
0x18007adcf  lea     rcx, [rsp+3B0h+StringUuid]; String
0x18007add4  call    cs:__imp_RpcStringFreeA
0x18007adda  jmp     short loc_18007AE05
0x18007addc  mov     ebx, 8007000Eh
0x18007ade1  lea     rax, aConvertguidtot; "ConvertGuidToTString failed."
0x18007ade8  mov     r9d, 1D6h
0x18007adee  jmp     loc_18007AF3C
0x18007adf3  lea     r8, Class; char *
0x18007adfa  mov     edx, esi; unsigned int
0x18007adfc  lea     rcx, [rbp+2B0h+var_320]; char *
0x18007ae00  call    ?vstrcpy@@YAPEADPEADKPEBD@Z; vstrcpy(char *,ulong,char const *)
0x18007ae05  mov     rcx, [rsp+3B0h+var_370]
0x18007ae0a  lea     rdx, [rbp+2B0h+var_320]
0x18007ae0e  xor     r9d, r9d
0x18007ae11  mov     [rsp+3B0h+var_390], rdx
0x18007ae16  xor     r8d, r8d
0x18007ae19  mov     rax, [rcx]
0x18007ae1c  lea     edx, [r9+3]
0x18007ae20  mov     rax, [rax+40h]
0x18007ae24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ae29  mov     ebx, eax
0x18007ae2b  test    eax, eax
0x18007ae2d  jns     short loc_18007AE41
0x18007ae2f  lea     rax, aWritepropertyF; "WriteProperty failed."
0x18007ae36  mov     r9d, 1E2h
0x18007ae3c  jmp     loc_18007AF3C
0x18007ae41  mov     rax, [rdi]
0x18007ae44  lea     rdx, [rbp+2B0h+var_320]
0x18007ae48  mov     r8d, esi
0x18007ae4b  mov     rcx, rdi
0x18007ae4e  mov     rax, [rax+80h]
0x18007ae55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ae5a  mov     ebx, eax
0x18007ae5c  test    eax, eax
0x18007ae5e  jns     short loc_18007AE72
0x18007ae60  lea     rax, aGetprotocolFai; "GetProtocol failed."
0x18007ae67  mov     r9d, 1EAh
0x18007ae6d  jmp     loc_18007AF3C
0x18007ae72  mov     rcx, [rsp+3B0h+var_370]
0x18007ae77  lea     rdx, [rbp+2B0h+var_320]
0x18007ae7b  xor     r9d, r9d
0x18007ae7e  mov     [rsp+3B0h+var_390], rdx
0x18007ae83  xor     r8d, r8d
0x18007ae86  mov     rax, [rcx]
0x18007ae89  lea     edx, [r9+5]
0x18007ae8d  mov     rax, [rax+40h]
0x18007ae91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ae96  mov     ebx, eax
0x18007ae98  test    eax, eax
0x18007ae9a  jns     short loc_18007AEAE
0x18007ae9c  lea     rax, aWritepropertyF; "WriteProperty failed."
0x18007aea3  mov     r9d, 1F1h
0x18007aea9  jmp     loc_18007AF3C
0x18007aeae  mov     rax, [rdi]
0x18007aeb1  lea     rdx, [rbp+2B0h+var_320]
0x18007aeb5  mov     r8d, esi
0x18007aeb8  mov     rcx, rdi
0x18007aebb  mov     rax, [rax+98h]
0x18007aec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aec7  mov     ebx, eax
0x18007aec9  test    eax, eax
0x18007aecb  jns     short loc_18007AEDC
0x18007aecd  lea     rax, aGetendpointFai; "GetEndpoint failed."
0x18007aed4  mov     r9d, 1F9h
0x18007aeda  jmp     short loc_18007AF3C
0x18007aedc  mov     rcx, [rsp+3B0h+var_370]
0x18007aee1  lea     rdx, [rbp+2B0h+var_320]
0x18007aee5  xor     r9d, r9d
0x18007aee8  mov     [rsp+3B0h+var_390], rdx
0x18007aeed  xor     r8d, r8d
0x18007aef0  mov     rax, [rcx]
0x18007aef3  lea     edx, [r9+6]
0x18007aef7  mov     rax, [rax+40h]
0x18007aefb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007af00  mov     ebx, eax
0x18007af02  mov     edx, r15d
0x18007af05  test    eax, eax
0x18007af07  jns     short loc_18007AF18
0x18007af09  lea     rax, aWritepropertyF; "WriteProperty failed."
0x18007af10  mov     r9d, 200h
0x18007af16  jmp     short loc_18007AF3F
0x18007af18  mov     rcx, [rsp+3B0h+var_370]
0x18007af1d  mov     rax, [rcx]
0x18007af20  mov     rax, [rax+50h]
0x18007af24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007af29  mov     ebx, eax
0x18007af2b  test    eax, eax
0x18007af2d  jns     short loc_18007AF65
0x18007af2f  lea     rax, aDisconnectFail; "Disconnect failed."
0x18007af36  mov     r9d, 209h
0x18007af3c  mov     edx, r15d
0x18007af3f  mov     [rsp+3B0h+var_380], rax
0x18007af44  lea     r8, aComComplusDtcS_2; "com\\complus\\dtc\\shared\\util\\cp_cic"...
0x18007af4b  lea     rax, aCicontactpoolW; "CIContactPool::WriteW"
0x18007af52  mov     dword ptr [rsp+3B0h+var_388], ebx
0x18007af56  mov     ecx, 7
0x18007af5b  mov     [rsp+3B0h+var_390], rax
0x18007af60  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18007af65  mov     rcx, [rsp+3B0h+var_370]
0x18007af6a  test    rcx, rcx
0x18007af6d  jz      short loc_18007AF7B
0x18007af6f  mov     rax, [rcx]
0x18007af72  mov     rax, [rax+10h]
0x18007af76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007af7b  mov     eax, ebx
0x18007af7d  mov     rcx, [rbp+2B0h+var_20]
0x18007af84  xor     rcx, rsp; StackCookie
0x18007af87  call    __security_check_cookie
0x18007af8c  lea     r11, [rsp+3B0h+var_10]
0x18007af94  mov     rbx, [r11+30h]
0x18007af98  mov     rsi, [r11+38h]
0x18007af9c  mov     rsp, r11
0x18007af9f  pop     r15
0x18007afa1  pop     rdi
0x18007afa2  pop     rbp
0x18007afa3  retn
```
