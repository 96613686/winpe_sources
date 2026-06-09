# CTipGateway::DoCreateTimer(ulong)

- ea: `0x18008eb78`
- end: `0x18008ecdf`
- name: `?DoCreateTimer@CTipGateway@@AEAAXK@Z`
- size: `359`
- prototype: `void __fastcall(CTipGateway *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180090530`
- `0x180092d50`

## callees

- `0x1800063b0`
- `0x18001d724`
- `0x180080f00`
- `0x18008eb78`
- `0x180097028`
- `0x1800bd010`

## string_xrefs

- `0x18008eba2`: `failed CreateCITimerManagere`
- `0x18008ebde`: `com\complus\dtc\dtc\tipgw\sm\src\tipgwsm.cpp`
- `0x18008ec3c`: `com\complus\dtc\dtc\tipgw\sm\src\tipgwsm.cpp`
- `0x18008ecbb`: `com\complus\dtc\dtc\tipgw\sm\src\tipgwsm.cpp`
- `0x18008ebb3`: `com\complus\dtc\dtc\tipgw\sm\src\tipgwsm.cpp`
- `0x18008ec22`: `com\complus\dtc\dtc\tipgw\sm\src\tipgwsm.cpp`
- `0x18008ec90`: `com\complus\dtc\dtc\tipgw\sm\src\tipgwsm.cpp`
- `0x18008ebc4`: `CTipGateway::DoCreateTimer`
- `0x18008ec1b`: `CTipGateway::DoCreateTimer`
- `0x18008eca1`: `CTipGateway::DoCreateTimer`
- `0x18008ec7f`: `failed pITimerManager->CreateTimer`

## pseudocode

```c
void __fastcall CTipGateway::DoCreateTimer(const struct _GUID *this)
{
  int v2; // eax
  CTipGwTrace *v3; // rcx
  __int64 v4; // r8
  CTipGwTrace *v5; // rcx
  int v6; // eax
  CTipGwTrace *v7; // rcx
  __int64 v8; // [rsp+28h] [rbp-20h]
  __int64 v9; // [rsp+28h] [rbp-20h]
  int v10; // [rsp+58h] [rbp+10h] BYREF
  void *v11; // [rsp+60h] [rbp+18h] BYREF

  v10 = 0;
  v11 = 0;
  v2 = CreateCITimerManager(this, &v11);
  if ( v2 )
  {
    LODWORD(v8) = v2;
    TraceStringInline(
      10,
      1,
      L"com\\complus\\dtc\\dtc\\tipgw\\sm\\src\\tipgwsm.cpp",
      2393,
      L"CTipGateway::DoCreateTimer",
      v8,
      L"failed CreateCITimerManagere");
    CTipGwTrace::InternalError(v3, "com\\complus\\dtc\\dtc\\tipgw\\sm\\src\\tipgwsm.cpp", 2394);
  }
  v4 = ASCGetSafeReference(&GUID_7087ebd6_b9ce_11d1_8f62_00c04fb611c7);
  if ( !v4 )
  {
    TraceStringInline(
      10,
      1,
      L"com\\complus\\dtc\\dtc\\tipgw\\sm\\src\\tipgwsm.cpp",
      2400,
      L"CTipGateway::DoCreateTimer",
      0,
      L"failed ASCGetSafeReference(__uuidof(ITimerNotify)");
    CTipGwTrace::InternalError(v5, "com\\complus\\dtc\\dtc\\tipgw\\sm\\src\\tipgwsm.cpp", 2401);
  }
  v6 = (*(__int64 (__fastcall **)(void *, __int64, __int64, __int64, int *, unsigned __int8 *))(*(_QWORD *)v11 + 24LL))(
         v11,
         2000,
         v4,
         1,
         &v10,
         this[26].Data4);
  if ( v6 )
  {
    LODWORD(v9) = v6;
    TraceStringInline(
      10,
      1,
      L"com\\complus\\dtc\\dtc\\tipgw\\sm\\src\\tipgwsm.cpp",
      2412,
      L"CTipGateway::DoCreateTimer",
      v9,
      L"failed pITimerManager->CreateTimer");
    CTipGwTrace::InternalError(v7, "com\\complus\\dtc\\dtc\\tipgw\\sm\\src\\tipgwsm.cpp", 2413);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
}

```

## disassembly

```asm
0x18008eb78  mov     rax, rsp
0x18008eb7b  mov     [rax+10h], edx
0x18008eb7e  push    rbx
0x18008eb7f  sub     rsp, 40h
0x18008eb83  lea     rdx, [rax+18h]; void **
0x18008eb87  mov     dword ptr [rax+10h], 0
0x18008eb8e  mov     rbx, rcx
0x18008eb91  mov     qword ptr [rax+18h], 0
0x18008eb99  call    ?CreateCITimerManager@@YAJAEBU_GUID@@PEAPEAX@Z; CreateCITimerManager(_GUID const &,void * *)
0x18008eb9e  test    eax, eax
0x18008eba0  jz      short loc_18008EBEB
0x18008eba2  lea     rcx, aFailedCreateci_0; "failed CreateCITimerManagere"
0x18008eba9  mov     edx, 1
0x18008ebae  mov     [rsp+48h+var_18], rcx
0x18008ebb3  lea     r8, aComComplusDtcD_99; "com\\complus\\dtc\\dtc\\tipgw\\sm\\src"...
0x18008ebba  mov     dword ptr [rsp+48h+var_20], eax
0x18008ebbe  mov     r9d, 959h
0x18008ebc4  lea     rax, aCtipgatewayDoc; "CTipGateway::DoCreateTimer"
0x18008ebcb  lea     ecx, [rdx+9]
0x18008ebce  mov     [rsp+48h+var_28], rax
0x18008ebd3  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18008ebd8  mov     r8d, 95Ah; int
0x18008ebde  lea     rdx, aComComplusDtcD_18; "com\\complus\\dtc\\dtc\\tipgw\\sm\\src"...
0x18008ebe5  call    ?InternalError@CTipGwTrace@@QEAAXPEBDH@Z; CTipGwTrace::InternalError(char const *,int)
0x18008ebeb  lea     rcx, _GUID_7087ebd6_b9ce_11d1_8f62_00c04fb611c7; struct _GUID *
0x18008ebf2  call    ?ASCGetSafeReference@@YAPEAXAEBU_GUID@@@Z; ASCGetSafeReference(_GUID const &)
0x18008ebf7  mov     r8, rax
0x18008ebfa  test    rax, rax
0x18008ebfd  jnz     short loc_18008EC49
0x18008ebff  mov     edx, 1
0x18008ec04  lea     rax, aFailedAscgetsa_1; "failed ASCGetSafeReference(__uuidof(ITi"...
0x18008ec0b  mov     [rsp+48h+var_18], rax
0x18008ec10  mov     r9d, 960h
0x18008ec16  mov     [rsp+48h+var_20], r8
0x18008ec1b  lea     rax, aCtipgatewayDoc; "CTipGateway::DoCreateTimer"
0x18008ec22  lea     r8, aComComplusDtcD_99; "com\\complus\\dtc\\dtc\\tipgw\\sm\\src"...
0x18008ec29  mov     [rsp+48h+var_28], rax
0x18008ec2e  lea     ecx, [rdx+9]
0x18008ec31  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18008ec36  mov     r8d, 961h; int
0x18008ec3c  lea     rdx, aComComplusDtcD_18; "com\\complus\\dtc\\dtc\\tipgw\\sm\\src"...
0x18008ec43  call    ?InternalError@CTipGwTrace@@QEAAXPEBDH@Z; CTipGwTrace::InternalError(char const *,int)
0x18008ec49  mov     rcx, [rsp+48h+arg_10]
0x18008ec4e  lea     rdx, [rbx+1A8h]
0x18008ec55  mov     [rsp+48h+var_20], rdx
0x18008ec5a  mov     r9d, 1
0x18008ec60  lea     rdx, [rsp+48h+arg_8]
0x18008ec65  mov     [rsp+48h+var_28], rdx
0x18008ec6a  mov     edx, 7D0h
0x18008ec6f  mov     rax, [rcx]
0x18008ec72  mov     rax, [rax+18h]
0x18008ec76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ec7b  test    eax, eax
0x18008ec7d  jz      short loc_18008ECC8
0x18008ec7f  lea     rcx, aFailedPitimerm; "failed pITimerManager->CreateTimer"
0x18008ec86  mov     edx, 1
0x18008ec8b  mov     [rsp+48h+var_18], rcx
0x18008ec90  lea     r8, aComComplusDtcD_99; "com\\complus\\dtc\\dtc\\tipgw\\sm\\src"...
0x18008ec97  mov     dword ptr [rsp+48h+var_20], eax
0x18008ec9b  mov     r9d, 96Ch
0x18008eca1  lea     rax, aCtipgatewayDoc; "CTipGateway::DoCreateTimer"
0x18008eca8  lea     ecx, [rdx+9]
0x18008ecab  mov     [rsp+48h+var_28], rax
0x18008ecb0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18008ecb5  mov     r8d, 96Dh; int
0x18008ecbb  lea     rdx, aComComplusDtcD_18; "com\\complus\\dtc\\dtc\\tipgw\\sm\\src"...
0x18008ecc2  call    ?InternalError@CTipGwTrace@@QEAAXPEBDH@Z; CTipGwTrace::InternalError(char const *,int)
0x18008ecc8  mov     rcx, [rsp+48h+arg_10]
0x18008eccd  mov     rax, [rcx]
0x18008ecd0  mov     rax, [rax+10h]
0x18008ecd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ecd9  add     rsp, 40h
0x18008ecdd  pop     rbx
0x18008ecde  retn
```
