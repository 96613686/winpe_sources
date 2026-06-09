# CFlightingAdmin::SetFlightSigningBcdSettings(int)

- ea: `0x180092e84`
- end: `0x1800930e9`
- name: `?SetFlightSigningBcdSettings@CFlightingAdmin@@SAHH@Z`
- size: `613`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800930f0`
- `0x1800abd20`

## callees

- `0x180004b80`
- `0x180013da0`
- `0x1800177bc`
- `0x18001c6f4`
- `0x18001ec78`
- `0x180086644`
- `0x180092c24`
- `0x180092dc8`
- `0x180092e84`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180092fb4`
- `ntdll!NtQuerySystemInformation` at `0x180092fb4`
- `bcd!BcdDeleteElement` at `0x180092f90`
- `bcd!BcdDeleteElement` at `0x18009301f`
- `bcd!BcdDeleteElement` at `0x180092f90`
- `bcd!BcdDeleteElement` at `0x18009301f`
- `bcd!BcdCloseStore` at `0x18009307e`
- `bcd!BcdCloseStore` at `0x18009307e`
- `bcd!BcdCloseObject` at `0x180093060`
- `bcd!BcdCloseObject` at `0x18009306f`
- `bcd!BcdCloseObject` at `0x180093060`
- `bcd!BcdCloseObject` at `0x18009306f`
- `bcd!BcdOpenStore` at `0x180092f19`
- `bcd!BcdOpenStore` at `0x180092f19`
- `bcd!BcdSetElementData` at `0x180092f7b`
- `bcd!BcdSetElementData` at `0x18009300a`
- `bcd!BcdSetElementData` at `0x180092f7b`
- `bcd!BcdSetElementData` at `0x18009300a`
- `bcd!BcdOpenObject` at `0x180092f4d`
- `bcd!BcdOpenObject` at `0x180092fdc`
- `bcd!BcdOpenObject` at `0x180092f4d`
- `bcd!BcdOpenObject` at `0x180092fdc`

## string_xrefs

- `0x180092f25`: `BcdOpenStore`
- `0x180092f9c`: `BcdDeleteElement`
- `0x18009302b`: `BcdDeleteElement`
- `0x180092f59`: `BcdOpenObject`
- `0x180092fe8`: `BcdOpenObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall CFlightingAdmin::SetFlightSigningBcdSettings(unsigned int a1)
{
  NTSTATUS v2; // ebx
  const wchar_t *v3; // rdx
  unsigned __int16 **v4; // rcx
  unsigned __int64 v5; // rdx
  unsigned __int8 v6; // cl
  __int64 v7; // rcx
  FlightSettingsAPITelemetryClass *v8; // rax
  _BYTE v10[8]; // [rsp+20h] [rbp-49h] BYREF
  __int64 v11; // [rsp+28h] [rbp-41h] BYREF
  __int64 v12; // [rsp+30h] [rbp-39h] BYREF
  __int64 v13; // [rsp+38h] [rbp-31h] BYREF
  unsigned __int16 *v14[3]; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int16 *v15[3]; // [rsp+58h] [rbp-11h] BYREF
  __int64 v16; // [rsp+70h] [rbp+7h] BYREF
  _OWORD SystemInformation[2]; // [rsp+78h] [rbp+Fh] BYREF

  v13 = 0;
  v11 = 0;
  v12 = 0;
  v10[1] = 0;
  v10[0] = a1 != 0;
  memset(SystemInformation, 0, sizeof(SystemInformation));
  memset(v15, 0, sizeof(v15));
  memset(v14, 0, sizeof(v14));
  v2 = BcdOpenStore(0, 0, &v13);
  if ( v2 < 0 )
  {
    v3 = L"BcdOpenStore";
LABEL_3:
    v4 = v15;
LABEL_4:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(v4, v3, -1);
    goto LABEL_23;
  }
  v2 = BcdOpenObject(v13, &GUID_WINDOWS_BOOTMGR, &v11);
  if ( v2 < 0 )
  {
    v3 = L"BcdOpenObject";
    goto LABEL_3;
  }
  if ( v10[0] )
  {
    v2 = BcdSetElementData(v11, 369098878, v10, 2);
    if ( v2 < 0 )
    {
      v3 = L"BcdSetElementData";
      goto LABEL_3;
    }
  }
  else
  {
    v2 = BcdDeleteElement(v11, 369098878);
    if ( v2 < 0 )
    {
      v3 = L"BcdDeleteElement";
      goto LABEL_3;
    }
  }
  v2 = NtQuerySystemInformation(SystemBootEnvironmentInformation, SystemInformation, 0x20u, 0);
  if ( v2 < 0 )
  {
    v3 = L"NtQuerySystemInformation";
LABEL_14:
    v4 = v14;
    goto LABEL_4;
  }
  v2 = BcdOpenObject(v13, SystemInformation, &v12);
  if ( v2 < 0 )
  {
    v3 = L"BcdOpenObject";
    goto LABEL_14;
  }
  if ( v10[0] )
  {
    v2 = BcdSetElementData(v12, 369098878, v10, 2);
    if ( v2 < 0 )
    {
      v3 = L"BcdSetElementData";
      goto LABEL_14;
    }
  }
  else
  {
    v2 = BcdDeleteElement(v12, 369098878);
    if ( v2 < 0 )
    {
      v3 = L"BcdDeleteElement";
      goto LABEL_14;
    }
  }
  v16 = -2147483646;
  FSRegUtils::SetFlightingRegDWORD(&v16, 1, L"BootMgrBcd", a1);
LABEL_23:
  CFlightingAdmin::ResealBitlockerAsNeeded();
  if ( v11 )
    BcdCloseObject();
  if ( v12 )
    BcdCloseObject();
  v6 = v13;
  if ( v13 )
    BcdCloseStore();
  if ( v2 < 0 && FlightSettingsAPITelemetryClass::IsEnabled(v6, v5) )
  {
    v8 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                              v7,
                                              _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    FlightSettingsAPITelemetryClass::SetBcdFailed_(v8, v15[0], v14[0], v2 | 0x10000000);
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v14);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v15);
  return v2 >= 0;
}

```

## disassembly

```asm
0x180092e84  push    rbp
0x180092e86  push    rbx
0x180092e87  push    rsi
0x180092e88  push    r12
0x180092e8a  lea     rbp, [rsp-3Fh]
0x180092e8f  sub     rsp, 0A8h
0x180092e96  mov     rax, cs:__security_cookie
0x180092e9d  xor     rax, rsp
0x180092ea0  mov     [rbp+57h+var_28], rax
0x180092ea4  mov     esi, ecx
0x180092ea6  mov     [rbp+57h+var_88], 0
0x180092eae  mov     [rbp+57h+var_98], 0
0x180092eb6  mov     [rbp+57h+var_90], 0
0x180092ebe  xor     eax, eax
0x180092ec0  mov     word ptr [rbp+57h+var_A0], ax
0x180092ec4  movzx   eax, al
0x180092ec7  mov     r12d, 1
0x180092ecd  test    ecx, ecx
0x180092ecf  cmovnz  eax, r12d
0x180092ed3  mov     [rbp+57h+var_A0], al
0x180092ed6  xorps   xmm0, xmm0
0x180092ed9  movups  [rbp+57h+SystemInformation], xmm0
0x180092edd  movups  [rbp+57h+var_38], xmm0
0x180092ee1  mov     [rbp+57h+var_68], 0
0x180092ee9  mov     [rbp+57h+var_60], 0
0x180092ef1  mov     [rbp+57h+var_58], 0
0x180092ef9  mov     [rbp+57h+var_80], 0
0x180092f01  mov     [rbp+57h+var_78], 0
0x180092f09  mov     [rbp+57h+var_70], 0
0x180092f11  lea     r8, [rbp+57h+var_88]
0x180092f15  xor     edx, edx
0x180092f17  xor     ecx, ecx
0x180092f19  call    cs:__imp_BcdOpenStore
0x180092f1f  mov     ebx, eax
0x180092f21  test    eax, eax
0x180092f23  jns     short loc_180092F3E
0x180092f25  lea     rdx, aBcdopenstore_0; "BcdOpenStore"
0x180092f2c  lea     rcx, [rbp+57h+var_68]
0x180092f30  or      r8, 0FFFFFFFFFFFFFFFFh
0x180092f34  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180092f39  jmp     loc_180093052
0x180092f3e  lea     r8, [rbp+57h+var_98]
0x180092f42  lea     rdx, GUID_WINDOWS_BOOTMGR
0x180092f49  mov     rcx, [rbp+57h+var_88]
0x180092f4d  call    cs:__imp_BcdOpenObject
0x180092f53  mov     ebx, eax
0x180092f55  test    eax, eax
0x180092f57  jns     short loc_180092F62
0x180092f59  lea     rdx, aBcdopenobject_0; "BcdOpenObject"
0x180092f60  jmp     short loc_180092F2C
0x180092f62  mov     edx, 1600007Eh
0x180092f67  mov     rcx, [rbp+57h+var_98]
0x180092f6b  cmp     [rbp+57h+var_A0], 0
0x180092f6f  jz      short loc_180092F90
0x180092f71  mov     r9d, 2
0x180092f77  lea     r8, [rbp+57h+var_A0]
0x180092f7b  call    cs:__imp_BcdSetElementData
0x180092f81  mov     ebx, eax
0x180092f83  test    eax, eax
0x180092f85  jns     short loc_180092FA5
0x180092f87  lea     rdx, aBcdsetelementd_0; "BcdSetElementData"
0x180092f8e  jmp     short loc_180092F2C
0x180092f90  call    cs:__imp_BcdDeleteElement
0x180092f96  mov     ebx, eax
0x180092f98  test    eax, eax
0x180092f9a  jns     short loc_180092FA5
0x180092f9c  lea     rdx, aBcddeleteeleme_0; "BcdDeleteElement"
0x180092fa3  jmp     short loc_180092F2C
0x180092fa5  xor     r9d, r9d; ReturnLength
0x180092fa8  lea     r8d, [r9+20h]; SystemInformationLength
0x180092fac  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x180092fb0  lea     ecx, [r9+5Ah]; SystemInformationClass
0x180092fb4  call    cs:__imp_NtQuerySystemInformation
0x180092fba  mov     ebx, eax
0x180092fbc  test    eax, eax
0x180092fbe  jns     short loc_180092FD0
0x180092fc0  lea     rdx, aNtquerysystemi_0; "NtQuerySystemInformation"
0x180092fc7  lea     rcx, [rbp+57h+var_80]
0x180092fcb  jmp     loc_180092F30
0x180092fd0  lea     r8, [rbp+57h+var_90]
0x180092fd4  lea     rdx, [rbp+57h+SystemInformation]
0x180092fd8  mov     rcx, [rbp+57h+var_88]
0x180092fdc  call    cs:__imp_BcdOpenObject
0x180092fe2  mov     ebx, eax
0x180092fe4  test    eax, eax
0x180092fe6  jns     short loc_180092FF1
0x180092fe8  lea     rdx, aBcdopenobject_0; "BcdOpenObject"
0x180092fef  jmp     short loc_180092FC7
0x180092ff1  mov     edx, 1600007Eh
0x180092ff6  mov     rcx, [rbp+57h+var_90]
0x180092ffa  cmp     [rbp+57h+var_A0], 0
0x180092ffe  jz      short loc_18009301F
0x180093000  mov     r9d, 2
0x180093006  lea     r8, [rbp+57h+var_A0]
0x18009300a  call    cs:__imp_BcdSetElementData
0x180093010  mov     ebx, eax
0x180093012  test    eax, eax
0x180093014  jns     short loc_180093034
0x180093016  lea     rdx, aBcdsetelementd_0; "BcdSetElementData"
0x18009301d  jmp     short loc_180092FC7
0x18009301f  call    cs:__imp_BcdDeleteElement
0x180093025  mov     ebx, eax
0x180093027  test    eax, eax
0x180093029  jns     short loc_180093034
0x18009302b  lea     rdx, aBcddeleteeleme_0; "BcdDeleteElement"
0x180093032  jmp     short loc_180092FC7
0x180093034  mov     [rbp+57h+var_50], 0FFFFFFFF80000002h
0x18009303c  mov     r9d, esi
0x18009303f  lea     r8, aBootmgrbcd; "BootMgrBcd"
0x180093046  mov     edx, r12d
0x180093049  lea     rcx, [rbp+57h+var_50]
0x18009304d  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x180093052  call    ?ResealBitlockerAsNeeded@CFlightingAdmin@@CAJXZ; CFlightingAdmin::ResealBitlockerAsNeeded(void)
0x180093057  mov     rcx, [rbp+57h+var_98]
0x18009305b  test    rcx, rcx
0x18009305e  jz      short loc_180093066
0x180093060  call    cs:__imp_BcdCloseObject
0x180093066  mov     rcx, [rbp+57h+var_90]
0x18009306a  test    rcx, rcx
0x18009306d  jz      short loc_180093075
0x18009306f  call    cs:__imp_BcdCloseObject
0x180093075  mov     rcx, [rbp+57h+var_88]
0x180093079  test    rcx, rcx
0x18009307c  jz      short loc_180093084
0x18009307e  call    cs:__imp_BcdCloseStore
0x180093084  test    ebx, ebx
0x180093086  jns     short loc_1800930B6
0x180093088  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x18009308d  test    al, al
0x18009308f  jz      short loc_1800930B6
0x180093091  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x180093098  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x18009309d  mov     r9d, ebx
0x1800930a0  bts     r9d, 1Ch; int
0x1800930a5  mov     r8, [rbp+57h+var_80]; unsigned __int16 *
0x1800930a9  mov     rdx, [rbp+57h+var_68]; unsigned __int16 *
0x1800930ad  mov     rcx, rax; this
0x1800930b0  call    ?SetBcdFailed_@FlightSettingsAPITelemetryClass@@QEAAXPEBG0J@Z; FlightSettingsAPITelemetryClass::SetBcdFailed_(ushort const *,ushort const *,long)
0x1800930b5  nop
0x1800930b6  not     ebx
0x1800930b8  shr     ebx, 1Fh
0x1800930bb  lea     rcx, [rbp+57h+var_80]
0x1800930bf  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800930c4  nop
0x1800930c5  lea     rcx, [rbp+57h+var_68]
0x1800930c9  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800930ce  mov     eax, ebx
0x1800930d0  mov     rcx, [rbp+57h+var_28]
0x1800930d4  xor     rcx, rsp; StackCookie
0x1800930d7  call    __security_check_cookie
0x1800930dc  add     rsp, 0A8h
0x1800930e3  pop     r12
0x1800930e5  pop     rsi
0x1800930e6  pop     rbx
0x1800930e7  pop     rbp
0x1800930e8  retn
```
