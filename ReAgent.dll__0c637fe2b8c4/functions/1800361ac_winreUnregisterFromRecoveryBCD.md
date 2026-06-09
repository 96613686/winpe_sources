# winreUnregisterFromRecoveryBCD

- ea: `0x1800361ac`
- end: `0x180036484`
- name: `winreUnregisterFromRecoveryBCD`
- size: `728`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x18001fd7c`

## callees

- `0x1800059fc`
- `0x180033270`
- `0x1800338fc`
- `0x180033a90`
- `0x180033f54`
- `0x1800341a0`
- `0x1800361ac`
- `0x18004e19c`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005cff0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800363d8`
- `msvcrt!_wcsicmp` at `0x1800363f0`
- `msvcrt!_wcsicmp` at `0x1800363d8`
- `msvcrt!_wcsicmp` at `0x1800363f0`
- `ntdll!RtlNtStatusToDosError` at `0x18003633f`
- `ntdll!RtlNtStatusToDosError` at `0x18003633f`
- `bcd!BcdCloseStore` at `0x180036448`
- `bcd!BcdCloseStore` at `0x180036458`
- `bcd!BcdCloseStore` at `0x180036448`
- `bcd!BcdCloseStore` at `0x180036458`
- `bcd!BcdOpenObject` at `0x180036359`
- `bcd!BcdOpenObject` at `0x180036359`
- `bcd!BcdOpenStore` at `0x18003631d`
- `bcd!BcdOpenStore` at `0x18003631d`

## string_xrefs

- `0x18003629a`: `Failed to open recovery BCD: 0x%x`
- `0x1800362d8`: `Recovery BCD is empty, nothing to delete`
- `0x18003630b`: `Failed to retrieve recovery entry WIM path: 0x%x`
- `0x180036329`: `Failed to open system BCD: 0x%x`
- `0x180036365`: `Failed to open main OS entry in system BCD: 0x%x`
- `0x18003638a`: `Failed to get path to winre.wim being unregistered: 0x%x`
- `0x1800363fa`: `Paths are the same, clearing Recovery BCD`
- `0x18003642d`: `Paths are different, not touching Recovery BCD`

## pseudocode

```c
__int64 __fastcall winreUnregisterFromRecoveryBCD(__int64 a1)
{
  ULONG v2; // ebx
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned __int64 v5; // r9
  unsigned int RecoveryBCDEntry; // eax
  NTSTATUS v7; // ebx
  unsigned __int64 v8; // r9
  unsigned int WimPathFromBCDEntry; // eax
  unsigned int v10; // eax
  void *v12; // [rsp+20h] [rbp-E0h] BYREF
  int v13; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  void *v15; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t String2; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[1038]; // [rsp+42h] [rbp-BEh] BYREF
  wchar_t String1; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v19[1038]; // [rsp+452h] [rbp+352h] BYREF
  wchar_t v20; // [rsp+860h] [rbp+760h] BYREF
  _BYTE v21[1038]; // [rsp+862h] [rbp+762h] BYREF
  wchar_t v22; // [rsp+C70h] [rbp+B70h] BYREF
  _BYTE v23[1038]; // [rsp+C72h] [rbp+B72h] BYREF

  v12 = 0;
  v13 = 0;
  String1 = 0;
  memset_0(v19, 0, sizeof(v19));
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v14 = 0;
  String2 = 0;
  v15 = 0;
  memset_0(v17, 0, sizeof(v17));
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  if ( !(unsigned int)Utils::IsEfi() )
  {
    UnattendLogW(0, L"Machine firmware is not EFI, nothing to do");
    v2 = 0;
    goto LABEL_27;
  }
  v3 = winreOpenRecoveryBCD(&v12);
  v2 = v3;
  if ( v3 )
  {
    UnattendLogW(1, L"Failed to open recovery BCD: 0x%x", v3);
    goto LABEL_25;
  }
  v4 = winreRecoveryBCDHasEntry(v12, &v13);
  v2 = v4;
  if ( v4 )
  {
    UnattendLogW(1, L"Failed to check whether recovery BCD is empty: 0x%x", v4);
    goto LABEL_25;
  }
  if ( !v13 )
  {
    UnattendLogW(0, L"Recovery BCD is empty, nothing to delete");
    v2 = 0;
    goto LABEL_25;
  }
  RecoveryBCDEntry = winreGetRecoveryBCDEntry(v12, &String1, &v22, v5);
  v2 = RecoveryBCDEntry;
  if ( RecoveryBCDEntry )
  {
    UnattendLogW(1, L"Failed to retrieve recovery entry WIM path: 0x%x", RecoveryBCDEntry);
    goto LABEL_25;
  }
  v7 = BcdOpenStore(0, 0, &v14);
  if ( v7 < 0 )
  {
    UnattendLogW(1, L"Failed to open system BCD: 0x%x", (unsigned int)v7);
LABEL_14:
    v2 = RtlNtStatusToDosError(v7);
    goto LABEL_25;
  }
  v7 = BcdOpenObject(v14, a1, &v15);
  if ( v7 < 0 )
  {
    UnattendLogW(1, L"Failed to open main OS entry in system BCD: 0x%x", (unsigned int)v7);
    goto LABEL_14;
  }
  WimPathFromBCDEntry = winreGetWimPathFromBCDEntry(v15, &String2, &v20, v8);
  v2 = WimPathFromBCDEntry;
  if ( WimPathFromBCDEntry )
  {
    UnattendLogW(1, L"Failed to get path to winre.wim being unregistered: 0x%x", WimPathFromBCDEntry);
  }
  else
  {
    UnattendLogW(0, L"The current Recovery BCD entry points to %s[%s]", &String1, &v22);
    UnattendLogW(0, L"The WIM file being unregistered is %s[%s]", &String2, &v20);
    if ( _wcsicmp(&String1, &String2) || _wcsicmp(&v22, &v20) )
    {
      UnattendLogW(0, L"Paths are different, not touching Recovery BCD");
    }
    else
    {
      UnattendLogW(0, L"Paths are the same, clearing Recovery BCD");
      v10 = winreClearRecoveryBCD(v12);
      v2 = v10;
      if ( v10 )
        UnattendLogW(1, L"Failed to clear recovery BCD: 0x%x", v10);
      else
        UnattendLogW(0, L"Cleared recovery BCD successfully");
    }
  }
LABEL_25:
  if ( v12 )
    BcdCloseStore(v12);
LABEL_27:
  if ( v14 )
    BcdCloseStore(v14);
  return v2;
}

```

## disassembly

```asm
0x1800361ac  mov     [rsp-8+arg_8], rbx
0x1800361b1  mov     [rsp-8+arg_10], rsi
0x1800361b6  push    rbp
0x1800361b7  lea     rbp, [rsp-0F90h]
0x1800361bf  mov     eax, 1090h
0x1800361c4  call    _alloca_probe
0x1800361c9  sub     rsp, rax
0x1800361cc  mov     rax, cs:__security_cookie
0x1800361d3  xor     rax, rsp
0x1800361d6  mov     [rbp+0F90h+var_10], rax
0x1800361dd  mov     rsi, rcx
0x1800361e0  mov     [rsp+1090h+var_1070], 0
0x1800361e9  xor     eax, eax
0x1800361eb  mov     [rsp+1090h+var_1068], 0
0x1800361f3  mov     ebx, 40Eh
0x1800361f8  mov     [rbp+0F90h+String1], ax
0x1800361ff  mov     r8d, ebx; Size
0x180036202  lea     rcx, [rbp+0F90h+var_C3E]; void *
0x180036209  xor     edx, edx; Val
0x18003620b  call    memset_0
0x180036210  xor     eax, eax
0x180036212  lea     rcx, [rbp+0F90h+var_41E]; void *
0x180036219  mov     r8d, ebx; Size
0x18003621c  mov     [rbp+0F90h+var_420], ax
0x180036223  xor     edx, edx; Val
0x180036225  call    memset_0
0x18003622a  xor     eax, eax
0x18003622c  mov     [rsp+1090h+var_1060], 0
0x180036235  mov     r8d, ebx; Size
0x180036238  mov     [rsp+1090h+String2], ax
0x18003623d  xor     edx, edx; Val
0x18003623f  mov     [rsp+1090h+var_1058], 0
0x180036248  lea     rcx, [rsp+1090h+var_104E]; void *
0x18003624d  call    memset_0
0x180036252  xor     eax, eax
0x180036254  lea     rcx, [rbp+0F90h+var_82E]; void *
0x18003625b  mov     r8d, ebx; Size
0x18003625e  mov     [rbp+0F90h+var_830], ax
0x180036265  xor     edx, edx; Val
0x180036267  call    memset_0
0x18003626c  call    ?IsEfi@Utils@@SAHXZ; Utils::IsEfi(void)
0x180036271  test    eax, eax
0x180036273  jnz     short loc_18003628A
0x180036275  lea     rdx, aMachineFirmwar; "Machine firmware is not EFI, nothing to"...
0x18003627c  xor     ecx, ecx
0x18003627e  call    UnattendLogW
0x180036283  xor     ebx, ebx
0x180036285  jmp     loc_18003644E
0x18003628a  lea     rcx, [rsp+1090h+var_1070]; void **
0x18003628f  call    ?winreOpenRecoveryBCD@@YAKPEAPEAX@Z; winreOpenRecoveryBCD(void * *)
0x180036294  mov     ebx, eax
0x180036296  test    eax, eax
0x180036298  jz      short loc_1800362B3
0x18003629a  lea     rdx, aFailedToOpenRe; "Failed to open recovery BCD: 0x%x"
0x1800362a1  mov     r8d, eax
0x1800362a4  mov     ecx, 1
0x1800362a9  call    UnattendLogW
0x1800362ae  jmp     loc_18003643B
0x1800362b3  mov     rcx, [rsp+1090h+var_1070]; void *
0x1800362b8  lea     rdx, [rsp+1090h+var_1068]; int *
0x1800362bd  call    ?winreRecoveryBCDHasEntry@@YAKPEAXPEAH@Z; winreRecoveryBCDHasEntry(void *,int *)
0x1800362c2  mov     ebx, eax
0x1800362c4  test    eax, eax
0x1800362c6  jz      short loc_1800362D1
0x1800362c8  lea     rdx, aFailedToCheckW_2; "Failed to check whether recovery BCD is"...
0x1800362cf  jmp     short loc_1800362A1
0x1800362d1  cmp     [rsp+1090h+var_1068], 0
0x1800362d6  jnz     short loc_1800362ED
0x1800362d8  lea     rdx, aRecoveryBcdIsE; "Recovery BCD is empty, nothing to delet"...
0x1800362df  xor     ecx, ecx
0x1800362e1  call    UnattendLogW
0x1800362e6  xor     ebx, ebx
0x1800362e8  jmp     loc_18003643B
0x1800362ed  mov     rcx, [rsp+1090h+var_1070]; void *
0x1800362f2  lea     r8, [rbp+0F90h+var_420]; unsigned __int16 *
0x1800362f9  lea     rdx, [rbp+0F90h+String1]; unsigned __int16 *
0x180036300  call    ?winreGetRecoveryBCDEntry@@YAKPEAXPEAG1_K@Z; winreGetRecoveryBCDEntry(void *,ushort *,ushort *,unsigned __int64)
0x180036305  mov     ebx, eax
0x180036307  test    eax, eax
0x180036309  jz      short loc_180036314
0x18003630b  lea     rdx, aFailedToRetrie; "Failed to retrieve recovery entry WIM p"...
0x180036312  jmp     short loc_1800362A1
0x180036314  lea     r8, [rsp+1090h+var_1060]
0x180036319  xor     edx, edx
0x18003631b  xor     ecx, ecx
0x18003631d  call    cs:__imp_BcdOpenStore
0x180036323  mov     ebx, eax
0x180036325  test    eax, eax
0x180036327  jns     short loc_18003634C
0x180036329  lea     rdx, aFailedToOpenSy_0; "Failed to open system BCD: 0x%x"
0x180036330  mov     r8d, ebx
0x180036333  mov     ecx, 1
0x180036338  call    UnattendLogW
0x18003633d  mov     ecx, ebx; Status
0x18003633f  call    cs:__imp_RtlNtStatusToDosError
0x180036345  mov     ebx, eax
0x180036347  jmp     loc_18003643B
0x18003634c  mov     rcx, [rsp+1090h+var_1060]
0x180036351  lea     r8, [rsp+1090h+var_1058]
0x180036356  mov     rdx, rsi
0x180036359  call    cs:__imp_BcdOpenObject
0x18003635f  mov     ebx, eax
0x180036361  test    eax, eax
0x180036363  jns     short loc_18003636E
0x180036365  lea     rdx, aFailedToOpenMa; "Failed to open main OS entry in system "...
0x18003636c  jmp     short loc_180036330
0x18003636e  mov     rcx, [rsp+1090h+var_1058]; void *
0x180036373  lea     r8, [rbp+0F90h+var_830]; unsigned __int16 *
0x18003637a  lea     rdx, [rsp+1090h+String2]; unsigned __int16 *
0x18003637f  call    ?winreGetWimPathFromBCDEntry@@YAKPEAXPEAG1_K@Z; winreGetWimPathFromBCDEntry(void *,ushort *,ushort *,unsigned __int64)
0x180036384  mov     ebx, eax
0x180036386  test    eax, eax
0x180036388  jz      short loc_180036396
0x18003638a  lea     rdx, aFailedToGetPat; "Failed to get path to winre.wim being u"...
0x180036391  jmp     loc_1800362A1
0x180036396  lea     r9, [rbp+0F90h+var_420]
0x18003639d  xor     ecx, ecx
0x18003639f  lea     r8, [rbp+0F90h+String1]
0x1800363a6  lea     rdx, aTheCurrentReco; "The current Recovery BCD entry points t"...
0x1800363ad  call    UnattendLogW
0x1800363b2  lea     r9, [rbp+0F90h+var_830]
0x1800363b9  xor     ecx, ecx
0x1800363bb  lea     r8, [rsp+1090h+String2]
0x1800363c0  lea     rdx, aTheWimFileBein; "The WIM file being unregistered is %s[%"...
0x1800363c7  call    UnattendLogW
0x1800363cc  lea     rdx, [rsp+1090h+String2]; String2
0x1800363d1  lea     rcx, [rbp+0F90h+String1]; String1
0x1800363d8  call    cs:__imp__wcsicmp
0x1800363de  test    eax, eax
0x1800363e0  jnz     short loc_18003642D
0x1800363e2  lea     rdx, [rbp+0F90h+var_830]; String2
0x1800363e9  lea     rcx, [rbp+0F90h+var_420]; String1
0x1800363f0  call    cs:__imp__wcsicmp
0x1800363f6  test    eax, eax
0x1800363f8  jnz     short loc_18003642D
0x1800363fa  lea     rdx, aPathsAreTheSam; "Paths are the same, clearing Recovery B"...
0x180036401  xor     ecx, ecx
0x180036403  call    UnattendLogW
0x180036408  mov     rcx, [rsp+1090h+var_1070]; void *
0x18003640d  call    ?winreClearRecoveryBCD@@YAKPEAX@Z; winreClearRecoveryBCD(void *)
0x180036412  mov     ebx, eax
0x180036414  test    eax, eax
0x180036416  jz      short loc_180036424
0x180036418  lea     rdx, aFailedToClearR; "Failed to clear recovery BCD: 0x%x"
0x18003641f  jmp     loc_1800362A1
0x180036424  lea     rdx, aClearedRecover; "Cleared recovery BCD successfully"
0x18003642b  jmp     short loc_180036434
0x18003642d  lea     rdx, aPathsAreDiffer; "Paths are different, not touching Recov"...
0x180036434  xor     ecx, ecx
0x180036436  call    UnattendLogW
0x18003643b  cmp     [rsp+1090h+var_1070], 0
0x180036441  jz      short loc_18003644E
0x180036443  mov     rcx, [rsp+1090h+var_1070]
0x180036448  call    cs:__imp_BcdCloseStore
0x18003644e  mov     rcx, [rsp+1090h+var_1060]
0x180036453  test    rcx, rcx
0x180036456  jz      short loc_18003645E
0x180036458  call    cs:__imp_BcdCloseStore
0x18003645e  mov     eax, ebx
0x180036460  mov     rcx, [rbp+0F90h+var_10]
0x180036467  xor     rcx, rsp; StackCookie
0x18003646a  call    __security_check_cookie
0x18003646f  lea     r11, [rsp+1090h+var_s0]
0x180036477  mov     rbx, [r11+18h]
0x18003647b  mov     rsi, [r11+20h]
0x18003647f  mov     rsp, r11
0x180036482  pop     rbp
0x180036483  retn
```
