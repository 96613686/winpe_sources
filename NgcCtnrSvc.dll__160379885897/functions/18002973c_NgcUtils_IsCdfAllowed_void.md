# NgcUtils::IsCdfAllowed(void)

- ea: `0x18002973c`
- end: `0x180029897`
- name: `?IsCdfAllowed@NgcUtils@@YA_NXZ`
- size: `347`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180059e8c`

## callees

- `0x18002973c`
- `0x180029980`
- `0x18002daf4`
- `0x18003a404`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029789`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029858`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029789`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029858`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x1800297e6`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x1800297e6`

## string_xrefs

- `0x1800297b0`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x1800297fa`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`
- `0x18002987c`: `onecore\ds\security\ngc\utils\common\lib\velocityutils.cpp`

## pseudocode

```c
bool __fastcall NgcUtils::IsCdfAllowed(NgcUtils *this)
{
  unsigned int ValueW; // eax
  int PolicyInt; // eax
  unsigned int v4; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-20h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  int pvData; // [rsp+50h] [rbp+10h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+18h] BYREF
  int v10; // [rsp+60h] [rbp+20h] BYREF

  pvData = 1;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\Credential Providers\\{48B4E58D-2791-456C-9091-D524C6C706F2}",
             L"Disabled",
             0x10u,
             0,
             &pvData,
             &pcbData);
  if ( ValueW == 2 )
    return 1;
  if ( ValueW )
  {
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)ValueW,
      pdwType);
  }
  else if ( !pvData )
  {
    return 1;
  }
  if ( (unsigned __int8)IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent() )
  {
    v10 = 0;
    PolicyInt = PolicyManager_GetPolicyInt(L"Authentication", L"AllowSecondaryAuthenticationDevice", &v10);
    if ( PolicyInt < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
        (const char *)(unsigned int)PolicyInt,
        pdwType);
    if ( v10 )
      return 1;
  }
  pvData = 0;
  pcbData = 4;
  v4 = RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\SecondaryAuthenticationFactor",
         L"AllowSecondaryAuthenticationDevice",
         0x10u,
         0,
         &pvData,
         &pcbData);
  if ( !v4 )
    return pvData != 0;
  if ( v4 != 2 )
    wil::details::in1diag3::Log_Win32(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\velocityutils.cpp",
      (const char *)v4,
      pdwTypea);
  return 0;
}

```

## disassembly

```asm
0x18002973c  push    rbp
0x18002973e  mov     rbp, rsp
0x180029741  sub     rsp, 40h
0x180029745  lea     rax, [rbp+arg_8]
0x180029749  mov     [rbp+arg_0], 1
0x180029750  mov     [rsp+40h+pcbData], rax; pcbData
0x180029755  lea     r8, aDisabled; "Disabled"
0x18002975c  lea     rax, [rbp+arg_0]
0x180029760  mov     [rbp+arg_8], 4
0x180029767  mov     [rsp+40h+pvData], rax; pvData
0x18002976c  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180029773  mov     r9d, 10h; dwFlags
0x180029779  mov     [rsp+40h+pdwType], 0; int
0x180029782  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180029789  call    cs:__imp_RegGetValueW
0x180029790  nop     dword ptr [rax+rax+00h]
0x180029795  cmp     eax, 2
0x180029798  jz      short loc_1800297A3
0x18002979a  test    eax, eax
0x18002979c  jnz     short loc_1800297AC
0x18002979e  cmp     [rbp+arg_0], eax
0x1800297a1  jnz     short loc_1800297C4
0x1800297a3  mov     al, 1
0x1800297a5  add     rsp, 40h
0x1800297a9  pop     rbp
0x1800297aa  retn
0x1800297ac  mov     rcx, [rbp+8]; this
0x1800297b0  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800297b7  mov     r9d, eax; char *
0x1800297ba  mov     edx, 37h ; '7'; void *
0x1800297bf  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800297c4  call    IsPolicyManager_GetDeviceLockPolicy_AlphanumericDevicePasswordRequiredPresent
0x1800297c9  test    al, al
0x1800297cb  jz      short loc_180029814
0x1800297cd  lea     r8, [rbp+arg_10]
0x1800297d1  mov     [rbp+arg_10], 0
0x1800297d8  lea     rdx, aAllowsecondary; "AllowSecondaryAuthenticationDevice"
0x1800297df  lea     rcx, aAuthentication; "Authentication"
0x1800297e6  call    cs:__imp_PolicyManager_GetPolicyInt
0x1800297ed  nop     dword ptr [rax+rax+00h]
0x1800297f2  test    eax, eax
0x1800297f4  jns     short loc_18002980E
0x1800297f6  mov     rcx, [rbp+8]; this
0x1800297fa  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180029801  mov     r9d, eax; char *
0x180029804  mov     edx, 41h ; 'A'; void *
0x180029809  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002980e  cmp     [rbp+arg_10], 0
0x180029812  jnz     short loc_1800297A3
0x180029814  lea     rax, [rbp+arg_8]
0x180029818  mov     [rbp+arg_0], 0
0x18002981f  mov     [rsp+40h+pcbData], rax; pcbData
0x180029824  lea     r8, aAllowsecondary; "AllowSecondaryAuthenticationDevice"
0x18002982b  lea     rax, [rbp+arg_0]
0x18002982f  mov     [rbp+arg_8], 4
0x180029836  mov     [rsp+40h+pvData], rax; pvData
0x18002983b  lea     rdx, aSoftwarePolici_1; "SOFTWARE\\Policies\\Microsoft\\Secondar"...
0x180029842  mov     r9d, 10h; dwFlags
0x180029848  mov     [rsp+40h+pdwType], 0; unsigned int
0x180029851  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180029858  call    cs:__imp_RegGetValueW
0x18002985f  nop     dword ptr [rax+rax+00h]
0x180029864  test    eax, eax
0x180029866  jnz     short loc_180029873
0x180029868  cmp     [rbp+arg_0], eax
0x18002986b  setnz   al
0x18002986e  jmp     loc_1800297A5
0x180029873  cmp     eax, 2
0x180029876  jz      short loc_180029890
0x180029878  mov     rcx, [rbp+8]; this
0x18002987c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180029883  mov     r9d, eax; char *
0x180029886  mov     edx, 5Dh ; ']'; void *
0x18002988b  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180029890  xor     al, al
0x180029892  jmp     loc_1800297A5
```
