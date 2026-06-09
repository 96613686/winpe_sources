# winreVerifyWinReBcdState

- ea: `0x1800367b8`
- end: `0x180036b0c`
- name: `winreVerifyWinReBcdState`
- size: `852`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180024ff0`

## callees

- `0x1800059fc`
- `0x180034590`
- `0x1800367b8`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180036ac1`
- `ntdll!RtlNtStatusToDosError` at `0x180036ac1`
- `bcd!BcdCloseStore` at `0x180036a91`
- `bcd!BcdCloseStore` at `0x180036a91`
- `bcd!BcdCloseObject` at `0x180036a6b`
- `bcd!BcdCloseObject` at `0x180036a7e`
- `bcd!BcdCloseObject` at `0x180036a6b`
- `bcd!BcdCloseObject` at `0x180036a7e`
- `bcd!BcdGetElementData` at `0x1800368ec`
- `bcd!BcdGetElementData` at `0x180036943`
- `bcd!BcdGetElementData` at `0x180036988`
- `bcd!BcdGetElementData` at `0x1800369cc`
- `bcd!BcdGetElementData` at `0x180036a06`
- `bcd!BcdGetElementData` at `0x1800368ec`
- `bcd!BcdGetElementData` at `0x180036943`
- `bcd!BcdGetElementData` at `0x180036988`
- `bcd!BcdGetElementData` at `0x1800369cc`
- `bcd!BcdGetElementData` at `0x180036a06`
- `bcd!BcdOpenObject` at `0x18003686b`
- `bcd!BcdOpenObject` at `0x1800368b7`
- `bcd!BcdOpenObject` at `0x1800369a4`
- `bcd!BcdOpenObject` at `0x18003686b`
- `bcd!BcdOpenObject` at `0x1800368b7`
- `bcd!BcdOpenObject` at `0x1800369a4`
- `bcd!BcdOpenStore` at `0x18003683b`
- `bcd!BcdOpenStore` at `0x18003683b`

## string_xrefs

- `0x1800368c6`: `BcdOpenObject failed: 0x%x`
- `0x18003684a`: `Open store failed: %x`
- `0x180036878`: `BcdOpenObject (Recovery Os object) failed: 0x%x`
- `0x180036a2c`: `Recovery sequence on current OS (resume) does not match the XML`

## pseudocode

```c
__int64 __fastcall winreVerifyWinReBcdState(__int64 a1, _QWORD *a2, int *a3)
{
  NTSTATUS ElementData; // ebx
  ULONG v6; // r14d
  int v7; // eax
  __int64 v8; // r8
  const wchar_t *v9; // rdx
  void *v10; // rcx
  int v11; // eax
  const wchar_t *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rax
  const wchar_t *v15; // rdx
  void *v17; // [rsp+20h] [rbp-50h] BYREF
  void *v18; // [rsp+28h] [rbp-48h] BYREF
  __int64 v19; // [rsp+30h] [rbp-40h] BYREF
  _WORD v20[2]; // [rsp+38h] [rbp-38h] BYREF
  int v21; // [rsp+3Ch] [rbp-34h] BYREF
  int v22; // [rsp+40h] [rbp-30h] BYREF
  __int128 v23; // [rsp+48h] [rbp-28h] BYREF
  __int128 v24; // [rsp+58h] [rbp-18h] BYREF

  v22 = 16;
  v18 = 0;
  v17 = 0;
  v20[0] = 0;
  v19 = 0;
  v21 = 0;
  v24 = 0;
  v23 = 0;
  if ( !a3 )
  {
    ElementData = 0;
    UnattendLogW(1, L"NULL parameter");
    v6 = 87;
    goto LABEL_38;
  }
  *a3 = 0;
  v6 = 0;
  v7 = BcdOpenStore(0, 0, &v18);
  ElementData = v7;
  if ( v7 < 0 )
  {
    v8 = (unsigned int)v7;
    v9 = L"Open store failed: %x";
LABEL_5:
    UnattendLogW(2, v9, v8);
    goto LABEL_38;
  }
  if ( (int)BcdOpenObject(v18, a2, &v17) < 0 )
  {
    ElementData = 0;
    v9 = L"BcdOpenObject (Recovery Os object) failed: 0x%x";
    v8 = 0;
    goto LABEL_5;
  }
  if ( winreVerifyRamDiskObject(v18, v17, a3) || !*a3 )
  {
    ElementData = 0;
    UnattendLogW(0, L"Ram disk object was invalid");
    *a3 = 0;
    goto LABEL_38;
  }
  v10 = v18;
  *a3 = 0;
  v11 = BcdOpenObject(v10, &GUID_CURRENT_BOOT_ENTRY, &v17);
  ElementData = v11;
  if ( v11 < 0 )
  {
    UnattendLogW(1, L"BcdOpenObject failed: 0x%x", (unsigned int)v11);
    goto LABEL_38;
  }
  v21 = 2;
  if ( (int)BcdGetElementData(v17, 369098761, v20, &v21) < 0 )
    goto LABEL_14;
  if ( LOBYTE(v20[0]) )
  {
    v21 = 16;
    ElementData = BcdGetElementData(v17, 335544328, &v23, &v21);
    if ( ElementData < 0 )
      goto LABEL_20;
    v13 = v23 - *a2;
    if ( (_QWORD)v23 == *a2 )
      v13 = *((_QWORD *)&v23 + 1) - a2[1];
    if ( v13 )
    {
      UnattendLogW(0, L"Recovery sequence on current OS not matched with winre");
      goto LABEL_38;
    }
    ElementData = BcdGetElementData(v17, 587202563, &v24, &v22);
    if ( ElementData < 0 )
    {
      UnattendLogW(0, L"Resume object not found");
    }
    else
    {
      ElementData = BcdOpenObject(v18, &v24, &v19);
      if ( ElementData >= 0 )
      {
        v21 = 2;
        ElementData = BcdGetElementData(v19, 369098761, v20, &v21);
        if ( ElementData < 0 )
        {
LABEL_14:
          v12 = L"BcdGetElementData(recoveryenabled) failed: 0x%x";
LABEL_15:
          ElementData = 0;
          UnattendLogW(0, v12, 0);
          goto LABEL_38;
        }
        if ( !LOBYTE(v20[0]) )
        {
          UnattendLogW(0, L"Recovery not enabled on resume object of the current OS");
          goto LABEL_38;
        }
        v21 = 16;
        ElementData = BcdGetElementData(v19, 335544328, &v23, &v21);
        if ( ElementData < 0 )
        {
LABEL_20:
          v12 = L"BcdGetElementData(recoverysequence) failed: 0x%x";
          goto LABEL_15;
        }
        v14 = v23 - *a2;
        if ( (_QWORD)v23 == *a2 )
          v14 = *((_QWORD *)&v23 + 1) - a2[1];
        if ( v14 )
        {
          UnattendLogW(0, L"Recovery sequence on current OS (resume) does not match the XML");
          goto LABEL_38;
        }
      }
    }
    *a3 = 1;
    goto LABEL_38;
  }
  ElementData = 0;
  UnattendLogW(0, L"Recovery not enabled on current OS");
LABEL_38:
  if ( v19 )
  {
    BcdCloseObject();
    v19 = 0;
  }
  if ( v17 )
  {
    BcdCloseObject();
    v17 = 0;
  }
  if ( v18 )
    BcdCloseStore();
  if ( ElementData < 0 )
  {
    if ( !ReAgentError )
      ReAgentError = 7;
    UnattendLogW(0, L"winreVerifyWinReBcdState failed: 0x%x", (unsigned int)ElementData);
    v6 = RtlNtStatusToDosError(ElementData);
  }
  if ( a3 )
  {
    v15 = L"WinRE BCD entries are valid";
    if ( !*a3 )
      v15 = L" WinRE BCD entries are not valid";
    UnattendLogW(0, v15);
  }
  return v6;
}

```

## disassembly

```asm
0x1800367b8  mov     [rsp-28h+arg_0], rbx
0x1800367bd  push    rbp
0x1800367be  push    rsi
0x1800367bf  push    rdi
0x1800367c0  push    r14
0x1800367c2  push    r15
0x1800367c4  mov     rbp, rsp
0x1800367c7  sub     rsp, 70h
0x1800367cb  mov     rax, cs:__security_cookie
0x1800367d2  xor     rax, rsp
0x1800367d5  mov     [rbp+var_8], rax
0x1800367d9  xor     r15d, r15d
0x1800367dc  mov     [rbp+var_30], 10h
0x1800367e3  mov     [rbp+var_48], r15
0x1800367e7  xorps   xmm0, xmm0
0x1800367ea  mov     [rbp+var_50], r15
0x1800367ee  xorps   xmm1, xmm1
0x1800367f1  mov     [rbp+var_38], r15w
0x1800367f6  mov     rdi, r8
0x1800367f9  mov     [rbp+var_40], r15
0x1800367fd  mov     rsi, rdx
0x180036800  mov     [rbp+var_34], r15d
0x180036804  movups  [rbp+var_18], xmm0
0x180036808  movups  [rbp+var_28], xmm1
0x18003680c  test    r8, r8
0x18003680f  jnz     short loc_18003682D
0x180036811  lea     rdx, aNullParameter; "NULL parameter"
0x180036818  mov     ebx, r15d
0x18003681b  lea     ecx, [r8+1]
0x18003681f  call    UnattendLogW
0x180036824  lea     r14d, [rdi+57h]
0x180036828  jmp     loc_180036A62
0x18003682d  mov     [r8], r15d
0x180036830  xor     edx, edx
0x180036832  lea     r8, [rbp+var_48]
0x180036836  xor     ecx, ecx
0x180036838  mov     r14d, r15d
0x18003683b  call    cs:__imp_BcdOpenStore
0x180036841  mov     ebx, eax
0x180036843  test    eax, eax
0x180036845  jns     short loc_180036860
0x180036847  mov     r8d, eax
0x18003684a  lea     rdx, aOpenStoreFaile_0; "Open store failed: %x"
0x180036851  mov     ecx, 2
0x180036856  call    UnattendLogW
0x18003685b  jmp     loc_180036A62
0x180036860  mov     rcx, [rbp+var_48]
0x180036864  lea     r8, [rbp+var_50]
0x180036868  mov     rdx, rsi
0x18003686b  call    cs:__imp_BcdOpenObject
0x180036871  test    eax, eax
0x180036873  jns     short loc_180036884
0x180036875  mov     ebx, r15d
0x180036878  lea     rdx, aBcdopenobjectR; "BcdOpenObject (Recovery Os object) fail"...
0x18003687f  xor     r8d, r8d
0x180036882  jmp     short loc_180036851
0x180036884  mov     rdx, [rbp+var_50]; void *
0x180036888  mov     r8, rdi; int *
0x18003688b  mov     rcx, [rbp+var_48]; void *
0x18003688f  call    ?winreVerifyRamDiskObject@@YAKPEAX0PEAH@Z; winreVerifyRamDiskObject(void *,void *,int *)
0x180036894  test    eax, eax
0x180036896  jnz     loc_180036A4E
0x18003689c  cmp     [rdi], r15d
0x18003689f  jz      loc_180036A4E
0x1800368a5  mov     rcx, [rbp+var_48]
0x1800368a9  lea     r8, [rbp+var_50]
0x1800368ad  lea     rdx, GUID_CURRENT_BOOT_ENTRY
0x1800368b4  mov     [rdi], r15d
0x1800368b7  call    cs:__imp_BcdOpenObject
0x1800368bd  mov     ebx, eax
0x1800368bf  test    eax, eax
0x1800368c1  jns     short loc_1800368D4
0x1800368c3  mov     r8d, eax
0x1800368c6  lea     rdx, aBcdopenobjectF_0; "BcdOpenObject failed: 0x%x"
0x1800368cd  mov     ecx, 1
0x1800368d2  jmp     short loc_180036856
0x1800368d4  mov     rcx, [rbp+var_50]
0x1800368d8  lea     r9, [rbp+var_34]
0x1800368dc  lea     r8, [rbp+var_38]
0x1800368e0  mov     [rbp+var_34], 2
0x1800368e7  mov     edx, 16000009h
0x1800368ec  call    cs:__imp_BcdGetElementData
0x1800368f2  test    eax, eax
0x1800368f4  jns     short loc_18003690F
0x1800368f6  lea     rdx, aBcdgetelementd_3; "BcdGetElementData(recoveryenabled) fail"...
0x1800368fd  xor     r8d, r8d
0x180036900  xor     ecx, ecx
0x180036902  mov     ebx, r15d
0x180036905  call    UnattendLogW
0x18003690a  jmp     loc_180036A62
0x18003690f  cmp     byte ptr [rbp+var_38], r15b
0x180036913  jnz     short loc_18003692B
0x180036915  mov     ebx, r15d
0x180036918  lea     rdx, aRecoveryNotEna_0; "Recovery not enabled on current OS"
0x18003691f  xor     ecx, ecx
0x180036921  call    UnattendLogW
0x180036926  jmp     loc_180036A62
0x18003692b  mov     rcx, [rbp+var_50]
0x18003692f  lea     r9, [rbp+var_34]
0x180036933  lea     r8, [rbp+var_28]
0x180036937  mov     [rbp+var_34], 10h
0x18003693e  mov     edx, 14000008h
0x180036943  call    cs:__imp_BcdGetElementData
0x180036949  mov     ebx, eax
0x18003694b  test    eax, eax
0x18003694d  jns     short loc_180036958
0x18003694f  lea     rdx, aBcdgetelementd_1; "BcdGetElementData(recoverysequence) fai"...
0x180036956  jmp     short loc_1800368FD
0x180036958  mov     rax, qword ptr [rbp+var_28]
0x18003695c  sub     rax, [rsi]
0x18003695f  jnz     short loc_180036969
0x180036961  mov     rax, qword ptr [rbp+var_28+8]
0x180036965  sub     rax, [rsi+8]
0x180036969  test    rax, rax
0x18003696c  jz      short loc_180036977
0x18003696e  lea     rdx, aRecoverySequen_0; "Recovery sequence on current OS not mat"...
0x180036975  jmp     short loc_18003691F
0x180036977  mov     rcx, [rbp+var_50]
0x18003697b  lea     r9, [rbp+var_30]
0x18003697f  lea     r8, [rbp+var_18]
0x180036983  mov     edx, 23000003h
0x180036988  call    cs:__imp_BcdGetElementData
0x18003698e  mov     ebx, eax
0x180036990  test    eax, eax
0x180036992  js      loc_180036A38
0x180036998  mov     rcx, [rbp+var_48]
0x18003699c  lea     r8, [rbp+var_40]
0x1800369a0  lea     rdx, [rbp+var_18]
0x1800369a4  call    cs:__imp_BcdOpenObject
0x1800369aa  mov     ebx, eax
0x1800369ac  test    eax, eax
0x1800369ae  js      loc_180036A46
0x1800369b4  mov     rcx, [rbp+var_40]
0x1800369b8  lea     r9, [rbp+var_34]
0x1800369bc  lea     r8, [rbp+var_38]
0x1800369c0  mov     [rbp+var_34], 2
0x1800369c7  mov     edx, 16000009h
0x1800369cc  call    cs:__imp_BcdGetElementData
0x1800369d2  mov     ebx, eax
0x1800369d4  test    eax, eax
0x1800369d6  js      loc_1800368F6
0x1800369dc  cmp     byte ptr [rbp+var_38], r15b
0x1800369e0  jnz     short loc_1800369EE
0x1800369e2  lea     rdx, aRecoveryNotEna; "Recovery not enabled on resume object o"...
0x1800369e9  jmp     loc_18003691F
0x1800369ee  mov     rcx, [rbp+var_40]
0x1800369f2  lea     r9, [rbp+var_34]
0x1800369f6  lea     r8, [rbp+var_28]
0x1800369fa  mov     [rbp+var_34], 10h
0x180036a01  mov     edx, 14000008h
0x180036a06  call    cs:__imp_BcdGetElementData
0x180036a0c  mov     ebx, eax
0x180036a0e  test    eax, eax
0x180036a10  js      loc_18003694F
0x180036a16  mov     rax, qword ptr [rbp+var_28]
0x180036a1a  sub     rax, [rsi]
0x180036a1d  jnz     short loc_180036A27
0x180036a1f  mov     rax, qword ptr [rbp+var_28+8]
0x180036a23  sub     rax, [rsi+8]
0x180036a27  test    rax, rax
0x180036a2a  jz      short loc_180036A46
0x180036a2c  lea     rdx, aRecoverySequen_1; "Recovery sequence on current OS (resume"...
0x180036a33  jmp     loc_18003691F
0x180036a38  lea     rdx, aResumeObjectNo; "Resume object not found"
0x180036a3f  xor     ecx, ecx
0x180036a41  call    UnattendLogW
0x180036a46  mov     dword ptr [rdi], 1
0x180036a4c  jmp     short loc_180036A62
0x180036a4e  lea     rdx, aRamDiskObjectW; "Ram disk object was invalid"
0x180036a55  xor     ecx, ecx
0x180036a57  mov     ebx, r15d
0x180036a5a  call    UnattendLogW
0x180036a5f  mov     [rdi], r15d
0x180036a62  mov     rcx, [rbp+var_40]
0x180036a66  test    rcx, rcx
0x180036a69  jz      short loc_180036A75
0x180036a6b  call    cs:__imp_BcdCloseObject
0x180036a71  mov     [rbp+var_40], r15
0x180036a75  mov     rcx, [rbp+var_50]
0x180036a79  test    rcx, rcx
0x180036a7c  jz      short loc_180036A88
0x180036a7e  call    cs:__imp_BcdCloseObject
0x180036a84  mov     [rbp+var_50], r15
0x180036a88  mov     rcx, [rbp+var_48]
0x180036a8c  test    rcx, rcx
0x180036a8f  jz      short loc_180036A97
0x180036a91  call    cs:__imp_BcdCloseStore
0x180036a97  test    ebx, ebx
0x180036a99  jns     short loc_180036ACA
0x180036a9b  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, r15d; _ReAgentErrorCodes ReAgentError
0x180036aa2  jnz     short loc_180036AAE
0x180036aa4  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 7; _ReAgentErrorCodes ReAgentError
0x180036aae  mov     r8d, ebx
0x180036ab1  lea     rdx, aWinreverifywin; "winreVerifyWinReBcdState failed: 0x%x"
0x180036ab8  xor     ecx, ecx
0x180036aba  call    UnattendLogW
0x180036abf  mov     ecx, ebx; Status
0x180036ac1  call    cs:__imp_RtlNtStatusToDosError
0x180036ac7  mov     r14d, eax
0x180036aca  test    rdi, rdi
0x180036acd  jz      short loc_180036AE9
0x180036acf  xor     ecx, ecx
0x180036ad1  lea     rdx, aWinreBcdEntrie_0; "WinRE BCD entries are valid"
0x180036ad8  cmp     [rdi], r15d
0x180036adb  jnz     short loc_180036AE4
0x180036add  lea     rdx, aWinreBcdEntrie; " WinRE BCD entries are not valid"
0x180036ae4  call    UnattendLogW
0x180036ae9  mov     eax, r14d
0x180036aec  mov     rcx, [rbp+var_8]
0x180036af0  xor     rcx, rsp; StackCookie
0x180036af3  call    __security_check_cookie
0x180036af8  mov     rbx, [rsp+70h+arg_0]
0x180036b00  add     rsp, 70h
0x180036b04  pop     r15
0x180036b06  pop     r14
0x180036b08  pop     rdi
0x180036b09  pop     rsi
0x180036b0a  pop     rbp
0x180036b0b  retn
```
