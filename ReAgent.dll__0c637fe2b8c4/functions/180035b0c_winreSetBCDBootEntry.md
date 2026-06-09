# winreSetBCDBootEntry

- ea: `0x180035b0c`
- end: `0x180035c87`
- name: `winreSetBCDBootEntry`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180024df0`

## callees

- `0x1800059fc`
- `0x180033864`
- `0x180035b0c`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180035c5f`
- `ntdll!RtlNtStatusToDosError` at `0x180035c5f`
- `bcd!BcdSetElementData` at `0x180035bec`
- `bcd!BcdSetElementData` at `0x180035bec`
- `bcd!BcdCloseStore` at `0x180035c2c`
- `bcd!BcdCloseStore` at `0x180035c2c`
- `bcd!BcdCloseObject` at `0x180035c15`
- `bcd!BcdCloseObject` at `0x180035c15`
- `bcd!BcdOpenObject` at `0x180035bc4`
- `bcd!BcdOpenObject` at `0x180035bc4`
- `bcd!BcdOpenStore` at `0x180035b4e`
- `bcd!BcdOpenStore` at `0x180035b4e`

## string_xrefs

- `0x180035bd0`: `BcdOpenObject failed: 0x%x`
- `0x180035b7e`: `base\diagnosis\srt\reagent2\reagent\bcdutil.cpp`
- `0x180035b5a`: `Open store failed: 0x%x`

## pseudocode

```c
ULONG __fastcall winreSetBCDBootEntry(struct _GUID *a1)
{
  int v2; // eax
  NTSTATUS IdForCurrentOS; // ebx
  int v4; // eax
  int v5; // eax
  __int64 v7; // [rsp+30h] [rbp-30h] BYREF
  void *v8; // [rsp+38h] [rbp-28h] BYREF
  struct _GUID v9; // [rsp+40h] [rbp-20h] BYREF

  v8 = 0;
  v7 = 0;
  v9 = 0;
  v2 = BcdOpenStore(0, 0, &v8);
  IdForCurrentOS = v2;
  if ( v2 < 0 )
  {
    UnattendLogW(1, L"Open store failed: 0x%x", (unsigned int)v2);
    goto LABEL_11;
  }
  if ( a1 )
  {
    v9 = *a1;
  }
  else
  {
    IdForCurrentOS = winreGetIdForCurrentOS(v8, &v9);
    if ( IdForCurrentOS < 0 )
    {
      UnattendLogW(
        2,
        L"winreSetBCDBootEntry %s (0x%x) in file %S line %d",
        L"failed to get id for current os",
        (unsigned int)IdForCurrentOS,
        "base\\diagnosis\\srt\\reagent2\\reagent\\bcdutil.cpp",
        434);
      goto LABEL_11;
    }
  }
  v4 = BcdOpenObject(v8, &GUID_WINDOWS_BOOTMGR, &v7);
  IdForCurrentOS = v4;
  if ( v4 >= 0 )
  {
    v5 = BcdSetElementData(v7, 603979778, &v9, 16);
    IdForCurrentOS = v5;
    if ( v5 < 0 )
      UnattendLogW(1, L"BcdSetElementData failed: 0x%x", (unsigned int)v5);
  }
  else
  {
    UnattendLogW(1, L"BcdOpenObject failed: 0x%x", (unsigned int)v4);
  }
LABEL_11:
  if ( v7 )
  {
    BcdCloseObject();
    v7 = 0;
  }
  if ( v8 )
    BcdCloseStore(v8);
  if ( IdForCurrentOS >= 0 )
    return 0;
  if ( !ReAgentError )
    ReAgentError = 7;
  UnattendLogW(1, L"winreSetBCDBootEntry failed: 0x%x", (unsigned int)IdForCurrentOS);
  return RtlNtStatusToDosError(IdForCurrentOS);
}

```

## disassembly

```asm
0x180035b0c  mov     [rsp-8+arg_8], rbx
0x180035b11  mov     [rsp-8+arg_10], rdi
0x180035b16  push    rbp
0x180035b17  mov     rbp, rsp
0x180035b1a  sub     rsp, 60h
0x180035b1e  mov     rax, cs:__security_cookie
0x180035b25  xor     rax, rsp
0x180035b28  mov     [rbp+var_10], rax
0x180035b2c  mov     rdi, rcx
0x180035b2f  mov     [rbp+var_28], 0
0x180035b37  xorps   xmm0, xmm0
0x180035b3a  mov     [rbp+var_30], 0
0x180035b42  xor     ecx, ecx
0x180035b44  lea     r8, [rbp+var_28]
0x180035b48  xor     edx, edx
0x180035b4a  movups  xmmword ptr [rbp+var_20.Data1], xmm0
0x180035b4e  call    cs:__imp_BcdOpenStore
0x180035b54  mov     ebx, eax
0x180035b56  test    eax, eax
0x180035b58  jns     short loc_180035B66
0x180035b5a  lea     rdx, aOpenStoreFaile; "Open store failed: 0x%x"
0x180035b61  jmp     loc_180035BFF
0x180035b66  test    rdi, rdi
0x180035b69  jnz     short loc_180035BAD
0x180035b6b  mov     rcx, [rbp+var_28]; void *
0x180035b6f  lea     rdx, [rbp+var_20]; struct _GUID *
0x180035b73  call    ?winreGetIdForCurrentOS@@YAJPEAXPEAU_GUID@@@Z; winreGetIdForCurrentOS(void *,_GUID *)
0x180035b78  mov     ebx, eax
0x180035b7a  test    eax, eax
0x180035b7c  jns     short loc_180035BB5
0x180035b7e  lea     rax, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180035b85  mov     [rsp+60h+var_38], 1B2h
0x180035b8d  mov     r9d, ebx
0x180035b90  mov     [rsp+60h+var_40], rax
0x180035b95  lea     r8, aFailedToGetIdF; "failed to get id for current os"
0x180035b9c  lea     rdx, aWinresetbcdboo; "winreSetBCDBootEntry %s (0x%x) in file "...
0x180035ba3  lea     ecx, [rdi+2]
0x180035ba6  call    UnattendLogW
0x180035bab  jmp     short loc_180035C0C
0x180035bad  movups  xmm0, xmmword ptr [rdi]
0x180035bb0  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x180035bb5  mov     rcx, [rbp+var_28]
0x180035bb9  lea     r8, [rbp+var_30]
0x180035bbd  lea     rdx, GUID_WINDOWS_BOOTMGR
0x180035bc4  call    cs:__imp_BcdOpenObject
0x180035bca  mov     ebx, eax
0x180035bcc  test    eax, eax
0x180035bce  jns     short loc_180035BD9
0x180035bd0  lea     rdx, aBcdopenobjectF_0; "BcdOpenObject failed: 0x%x"
0x180035bd7  jmp     short loc_180035BFF
0x180035bd9  mov     rcx, [rbp+var_30]
0x180035bdd  lea     r8, [rbp+var_20]
0x180035be1  mov     r9d, 10h
0x180035be7  mov     edx, 24000002h
0x180035bec  call    cs:__imp_BcdSetElementData
0x180035bf2  mov     ebx, eax
0x180035bf4  test    eax, eax
0x180035bf6  jns     short loc_180035C0C
0x180035bf8  lea     rdx, aBcdsetelementd_1; "BcdSetElementData failed: 0x%x"
0x180035bff  mov     r8d, eax
0x180035c02  mov     ecx, 1
0x180035c07  call    UnattendLogW
0x180035c0c  mov     rcx, [rbp+var_30]
0x180035c10  test    rcx, rcx
0x180035c13  jz      short loc_180035C23
0x180035c15  call    cs:__imp_BcdCloseObject
0x180035c1b  mov     [rbp+var_30], 0
0x180035c23  mov     rcx, [rbp+var_28]
0x180035c27  test    rcx, rcx
0x180035c2a  jz      short loc_180035C32
0x180035c2c  call    cs:__imp_BcdCloseStore
0x180035c32  test    ebx, ebx
0x180035c34  jns     short loc_180035C67
0x180035c36  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x180035c3d  jnz     short loc_180035C49
0x180035c3f  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 7; _ReAgentErrorCodes ReAgentError
0x180035c49  mov     r8d, ebx
0x180035c4c  lea     rdx, aWinresetbcdboo_0; "winreSetBCDBootEntry failed: 0x%x"
0x180035c53  mov     ecx, 1
0x180035c58  call    UnattendLogW
0x180035c5d  mov     ecx, ebx; Status
0x180035c5f  call    cs:__imp_RtlNtStatusToDosError
0x180035c65  jmp     short loc_180035C69
0x180035c67  xor     eax, eax
0x180035c69  mov     rcx, [rbp+var_10]
0x180035c6d  xor     rcx, rsp; StackCookie
0x180035c70  call    __security_check_cookie
0x180035c75  lea     r11, [rsp+60h+var_s0]
0x180035c7a  mov     rbx, [r11+18h]
0x180035c7e  mov     rdi, [r11+20h]
0x180035c82  mov     rsp, r11
0x180035c85  pop     rbp
0x180035c86  retn
```
