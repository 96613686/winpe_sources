# winreRemoveRecoverySequenceEx

- ea: `0x18003591c`
- end: `0x180035b05`
- name: `winreRemoveRecoverySequenceEx`
- size: `489`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x18001fd7c`
- `0x180024a10`
- `0x18002cab4`

## callees

- `0x1800059fc`
- `0x1800357cc`
- `0x18003591c`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800359a6`
- `ntdll!RtlNtStatusToDosError` at `0x180035acb`
- `ntdll!RtlNtStatusToDosError` at `0x1800359a6`
- `ntdll!RtlNtStatusToDosError` at `0x180035acb`
- `bcd!BcdSetElementData` at `0x180035a03`
- `bcd!BcdSetElementData` at `0x180035a54`
- `bcd!BcdSetElementData` at `0x180035a03`
- `bcd!BcdSetElementData` at `0x180035a54`
- `bcd!BcdCloseStore` at `0x180035adc`
- `bcd!BcdCloseStore` at `0x180035adc`
- `bcd!BcdCloseObject` at `0x180035a7b`
- `bcd!BcdCloseObject` at `0x180035a92`
- `bcd!BcdCloseObject` at `0x180035a7b`
- `bcd!BcdCloseObject` at `0x180035a92`
- `bcd!BcdGetElementData` at `0x180035a20`
- `bcd!BcdGetElementData` at `0x180035a20`
- `bcd!BcdOpenObject` at `0x1800359d9`
- `bcd!BcdOpenObject` at `0x180035a38`
- `bcd!BcdOpenObject` at `0x1800359d9`
- `bcd!BcdOpenObject` at `0x180035a38`
- `bcd!BcdOpenStore` at `0x180035980`
- `bcd!BcdOpenStore` at `0x180035980`

## string_xrefs

- `0x1800359e5`: `BcdOpenObject failed: 0x%x`
- `0x180035992`: ` Failed to open system BCD: 0x%x`
- `0x1800359c5`: ` Failed to remove recovery entry from BCD: 0x%x`
- `0x180035aba`: `winreRemoveRecoverySequenceEx failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreRemoveRecoverySequenceEx(GUID *a1, __int64 a2)
{
  GUID *v3; // rsi
  NTSTATUS ElementData; // ebx
  unsigned int v5; // edi
  int v6; // eax
  int v7; // eax
  __int64 v9; // [rsp+20h] [rbp-40h] BYREF
  void *v10; // [rsp+28h] [rbp-38h] BYREF
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  _WORD v12[2]; // [rsp+38h] [rbp-28h] BYREF
  int v13; // [rsp+3Ch] [rbp-24h] BYREF
  __int128 v14; // [rsp+40h] [rbp-20h] BYREF

  v10 = 0;
  v9 = 0;
  v12[0] = 0;
  v13 = 16;
  v3 = &GUID_CURRENT_BOOT_ENTRY;
  v11 = 0;
  if ( a1 )
    v3 = a1;
  v14 = 0;
  ElementData = BcdOpenStore(0, 0, &v10);
  if ( ElementData < 0 )
  {
    UnattendLogW(1, L" Failed to open system BCD: 0x%x", (unsigned int)ElementData);
LABEL_5:
    v5 = RtlNtStatusToDosError(ElementData);
    goto LABEL_15;
  }
  v5 = winreRemoveRecoveryEntryFromBCD(v10, a2);
  if ( v5 )
  {
    UnattendLogW(1, L" Failed to remove recovery entry from BCD: 0x%x", (unsigned int)ElementData);
    goto LABEL_5;
  }
  v6 = BcdOpenObject(v10, v3, &v9);
  ElementData = v6;
  if ( v6 >= 0 )
  {
    v7 = BcdSetElementData(v9, 369098761, v12, 2);
    ElementData = v7;
    if ( v7 < 0
      || (ElementData = BcdGetElementData(v9, 587202563, &v14, &v13), ElementData >= 0)
      && (ElementData = BcdOpenObject(v10, &v14, &v11), ElementData >= 0)
      && (v7 = BcdSetElementData(v11, 369098761, v12, 2), ElementData = v7, v7 < 0) )
    {
      UnattendLogW(1, L"BcdSetElementData(recoveryenabled) failed: 0x%x", (unsigned int)v7);
    }
  }
  else
  {
    UnattendLogW(1, L"BcdOpenObject failed: 0x%x", (unsigned int)v6);
  }
LABEL_15:
  if ( v11 )
  {
    BcdCloseObject();
    v11 = 0;
  }
  if ( v9 )
  {
    BcdCloseObject();
    v9 = 0;
  }
  if ( ElementData < 0 )
  {
    if ( !ReAgentError )
      ReAgentError = 7;
    UnattendLogW(1, L"winreRemoveRecoverySequenceEx failed: 0x%x", (unsigned int)ElementData);
    v5 = RtlNtStatusToDosError(ElementData);
  }
  if ( v10 )
    BcdCloseStore();
  return v5;
}

```

## disassembly

```asm
0x18003591c  mov     [rsp-18h+arg_10], rbx
0x180035921  mov     [rsp-18h+arg_18], rsi
0x180035926  push    rbp
0x180035927  push    rdi
0x180035928  push    r15
0x18003592a  mov     rbp, rsp
0x18003592d  sub     rsp, 60h
0x180035931  mov     rax, cs:__security_cookie
0x180035938  xor     rax, rsp
0x18003593b  mov     [rbp+var_10], rax
0x18003593f  xor     eax, eax
0x180035941  mov     [rbp+var_38], 0
0x180035949  test    rcx, rcx
0x18003594c  mov     [rbp+var_40], 0
0x180035954  mov     rdi, rdx
0x180035957  mov     [rbp+var_28], ax
0x18003595b  xorps   xmm0, xmm0
0x18003595e  mov     [rbp+var_24], 10h
0x180035965  lea     rsi, GUID_CURRENT_BOOT_ENTRY
0x18003596c  mov     [rbp+var_30], rax
0x180035970  cmovnz  rsi, rcx
0x180035974  lea     r8, [rbp+var_38]
0x180035978  xor     edx, edx
0x18003597a  xor     ecx, ecx
0x18003597c  movups  [rbp+var_20], xmm0
0x180035980  call    cs:__imp_BcdOpenStore
0x180035986  mov     ebx, eax
0x180035988  mov     r15d, 1
0x18003598e  test    eax, eax
0x180035990  jns     short loc_1800359B3
0x180035992  lea     rdx, aFailedToOpenSy_1; " Failed to open system BCD: 0x%x"
0x180035999  mov     r8d, ebx
0x18003599c  mov     ecx, r15d
0x18003599f  call    UnattendLogW
0x1800359a4  mov     ecx, ebx; Status
0x1800359a6  call    cs:__imp_RtlNtStatusToDosError
0x1800359ac  mov     edi, eax
0x1800359ae  jmp     loc_180035A72
0x1800359b3  mov     rcx, [rbp+var_38]; void *
0x1800359b7  mov     rdx, rdi
0x1800359ba  call    winreRemoveRecoveryEntryFromBCD
0x1800359bf  mov     edi, eax
0x1800359c1  test    eax, eax
0x1800359c3  jz      short loc_1800359CE
0x1800359c5  lea     rdx, aFailedToRemove; " Failed to remove recovery entry from B"...
0x1800359cc  jmp     short loc_180035999
0x1800359ce  mov     rcx, [rbp+var_38]
0x1800359d2  lea     r8, [rbp+var_40]
0x1800359d6  mov     rdx, rsi
0x1800359d9  call    cs:__imp_BcdOpenObject
0x1800359df  mov     ebx, eax
0x1800359e1  test    eax, eax
0x1800359e3  jns     short loc_1800359EE
0x1800359e5  lea     rdx, aBcdopenobjectF_0; "BcdOpenObject failed: 0x%x"
0x1800359ec  jmp     short loc_180035A67
0x1800359ee  mov     rcx, [rbp+var_40]
0x1800359f2  lea     r8, [rbp+var_28]
0x1800359f6  mov     esi, 2
0x1800359fb  mov     edx, 16000009h
0x180035a00  mov     r9d, esi
0x180035a03  call    cs:__imp_BcdSetElementData
0x180035a09  mov     ebx, eax
0x180035a0b  test    eax, eax
0x180035a0d  js      short loc_180035A60
0x180035a0f  mov     rcx, [rbp+var_40]
0x180035a13  lea     r9, [rbp+var_24]
0x180035a17  lea     r8, [rbp+var_20]
0x180035a1b  mov     edx, 23000003h
0x180035a20  call    cs:__imp_BcdGetElementData
0x180035a26  mov     ebx, eax
0x180035a28  test    eax, eax
0x180035a2a  js      short loc_180035A72
0x180035a2c  mov     rcx, [rbp+var_38]
0x180035a30  lea     r8, [rbp+var_30]
0x180035a34  lea     rdx, [rbp+var_20]
0x180035a38  call    cs:__imp_BcdOpenObject
0x180035a3e  mov     ebx, eax
0x180035a40  test    eax, eax
0x180035a42  js      short loc_180035A72
0x180035a44  mov     rcx, [rbp+var_30]
0x180035a48  lea     r8, [rbp+var_28]
0x180035a4c  mov     r9d, esi
0x180035a4f  mov     edx, 16000009h
0x180035a54  call    cs:__imp_BcdSetElementData
0x180035a5a  mov     ebx, eax
0x180035a5c  test    eax, eax
0x180035a5e  jns     short loc_180035A72
0x180035a60  lea     rdx, aBcdsetelementd_3; "BcdSetElementData(recoveryenabled) fail"...
0x180035a67  mov     r8d, eax
0x180035a6a  mov     ecx, r15d
0x180035a6d  call    UnattendLogW
0x180035a72  mov     rcx, [rbp+var_30]
0x180035a76  test    rcx, rcx
0x180035a79  jz      short loc_180035A89
0x180035a7b  call    cs:__imp_BcdCloseObject
0x180035a81  mov     [rbp+var_30], 0
0x180035a89  mov     rcx, [rbp+var_40]
0x180035a8d  test    rcx, rcx
0x180035a90  jz      short loc_180035AA0
0x180035a92  call    cs:__imp_BcdCloseObject
0x180035a98  mov     [rbp+var_40], 0
0x180035aa0  test    ebx, ebx
0x180035aa2  jns     short loc_180035AD3
0x180035aa4  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180035aab  jnz     short loc_180035AB7
0x180035aad  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 7; _ReAgentErrorCodes ReAgentError
0x180035ab7  mov     r8d, ebx
0x180035aba  lea     rdx, aWinreremoverec_0; "winreRemoveRecoverySequenceEx failed: 0"...
0x180035ac1  mov     ecx, r15d
0x180035ac4  call    UnattendLogW
0x180035ac9  mov     ecx, ebx; Status
0x180035acb  call    cs:__imp_RtlNtStatusToDosError
0x180035ad1  mov     edi, eax
0x180035ad3  mov     rcx, [rbp+var_38]
0x180035ad7  test    rcx, rcx
0x180035ada  jz      short loc_180035AE2
0x180035adc  call    cs:__imp_BcdCloseStore
0x180035ae2  mov     eax, edi
0x180035ae4  mov     rcx, [rbp+var_10]
0x180035ae8  xor     rcx, rsp; StackCookie
0x180035aeb  call    __security_check_cookie
0x180035af0  lea     r11, [rsp+60h+var_s0]
0x180035af5  mov     rbx, [r11+30h]
0x180035af9  mov     rsi, [r11+38h]
0x180035afd  mov     rsp, r11
0x180035b00  pop     r15
0x180035b02  pop     rdi
0x180035b03  pop     rbp
0x180035b04  retn
```
