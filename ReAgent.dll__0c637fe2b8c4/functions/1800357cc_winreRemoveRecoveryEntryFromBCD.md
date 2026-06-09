# winreRemoveRecoveryEntryFromBCD

- ea: `0x1800357cc`
- end: `0x180035915`
- name: `winreRemoveRecoveryEntryFromBCD`
- size: `329`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x180033270`
- `0x18003591c`

## callees

- `0x1800059fc`
- `0x180033684`
- `0x1800357cc`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800358ec`
- `ntdll!RtlNtStatusToDosError` at `0x1800358ec`
- `bcd!BcdDeleteObjectReferences` at `0x180035853`
- `bcd!BcdDeleteObjectReferences` at `0x180035853`
- `bcd!BcdDeleteObject` at `0x180035834`
- `bcd!BcdDeleteObject` at `0x180035834`
- `bcd!BcdDeleteElement` at `0x180035898`
- `bcd!BcdDeleteElement` at `0x1800358a7`
- `bcd!BcdDeleteElement` at `0x180035898`
- `bcd!BcdDeleteElement` at `0x1800358a7`
- `bcd!BcdCloseObject` at `0x180035862`
- `bcd!BcdCloseObject` at `0x1800358b6`
- `bcd!BcdCloseObject` at `0x180035862`
- `bcd!BcdCloseObject` at `0x1800358b6`
- `bcd!BcdOpenObject` at `0x1800357ff`
- `bcd!BcdOpenObject` at `0x18003587a`
- `bcd!BcdOpenObject` at `0x1800357ff`
- `bcd!BcdOpenObject` at `0x18003587a`

## string_xrefs

- `0x180035886`: `BcdOpenObject failed: 0x%x`
- `0x180035840`: `BcdDeleteObject filed: 0x%x`
- `0x18003580b`: `BcdOpenObject filed: 0x%x`
- `0x1800358d9`: `winreRemoveRecoveryEntryFromBCD failed: 0x%x`

## pseudocode

```c
__int64 __fastcall winreRemoveRecoveryEntryFromBCD(void *a1, __int64 a2)
{
  unsigned int v2; // esi
  int v5; // eax
  NTSTATUS v6; // ebx
  int v7; // eax
  int v8; // eax
  void *v10; // [rsp+20h] [rbp-10h] BYREF

  v2 = 0;
  v10 = 0;
  v5 = BcdOpenObject(a1, a2, &v10);
  v6 = v5;
  if ( v5 >= 0 )
  {
    winreDeleteRamDiskObject(a1, v10);
    v7 = BcdDeleteObject(v10);
    v6 = v7;
    if ( v7 >= 0 )
    {
      v10 = 0;
      BcdDeleteObjectReferences(a1, a2);
      if ( v10 )
      {
        BcdCloseObject();
        v10 = 0;
      }
      v8 = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v10);
      v6 = v8;
      if ( v8 >= 0 )
      {
        BcdDeleteElement(v10, 1409286159);
        BcdDeleteElement(v10, 654311472);
      }
      else
      {
        UnattendLogW(1, L"BcdOpenObject failed: 0x%x", (unsigned int)v8);
      }
    }
    else
    {
      UnattendLogW(1, L"BcdDeleteObject filed: 0x%x", (unsigned int)v7);
    }
  }
  else
  {
    UnattendLogW(1, L"BcdOpenObject filed: 0x%x", (unsigned int)v5);
  }
  if ( v10 )
  {
    BcdCloseObject();
    v10 = 0;
  }
  if ( v6 < 0 )
  {
    if ( !ReAgentError )
      ReAgentError = 7;
    UnattendLogW(1, L"winreRemoveRecoveryEntryFromBCD failed: 0x%x", (unsigned int)v6);
    return RtlNtStatusToDosError(v6);
  }
  return v2;
}

```

## disassembly

```asm
0x1800357cc  mov     [rsp-18h+arg_10], rbx
0x1800357d1  mov     [rsp-18h+arg_18], rsi
0x1800357d6  push    rbp
0x1800357d7  push    rdi
0x1800357d8  push    r14
0x1800357da  mov     rbp, rsp
0x1800357dd  sub     rsp, 30h
0x1800357e1  mov     rax, cs:__security_cookie
0x1800357e8  xor     rax, rsp
0x1800357eb  mov     [rbp+var_8], rax
0x1800357ef  xor     esi, esi
0x1800357f1  lea     r8, [rbp+var_10]
0x1800357f5  mov     [rbp+var_10], rsi
0x1800357f9  mov     r14, rdx
0x1800357fc  mov     rdi, rcx
0x1800357ff  call    cs:__imp_BcdOpenObject
0x180035805  mov     ebx, eax
0x180035807  test    eax, eax
0x180035809  jns     short loc_180035824
0x18003580b  lea     rdx, aBcdopenobjectF; "BcdOpenObject filed: 0x%x"
0x180035812  mov     r8d, eax
0x180035815  mov     ecx, 1
0x18003581a  call    UnattendLogW
0x18003581f  jmp     loc_1800358AD
0x180035824  mov     rdx, [rbp+var_10]; void *
0x180035828  mov     rcx, rdi; void *
0x18003582b  call    ?winreDeleteRamDiskObject@@YAKPEAX0@Z; winreDeleteRamDiskObject(void *,void *)
0x180035830  mov     rcx, [rbp+var_10]
0x180035834  call    cs:__imp_BcdDeleteObject
0x18003583a  mov     ebx, eax
0x18003583c  test    eax, eax
0x18003583e  jns     short loc_180035849
0x180035840  lea     rdx, aBcddeleteobjec_1; "BcdDeleteObject filed: 0x%x"
0x180035847  jmp     short loc_180035812
0x180035849  mov     rdx, r14
0x18003584c  mov     [rbp+var_10], rsi
0x180035850  mov     rcx, rdi
0x180035853  call    cs:__imp_BcdDeleteObjectReferences
0x180035859  mov     rcx, [rbp+var_10]
0x18003585d  test    rcx, rcx
0x180035860  jz      short loc_18003586C
0x180035862  call    cs:__imp_BcdCloseObject
0x180035868  mov     [rbp+var_10], rsi
0x18003586c  lea     r8, [rbp+var_10]
0x180035870  mov     rcx, rdi
0x180035873  lea     rdx, GUID_WINDOWS_BOOTMGR
0x18003587a  call    cs:__imp_BcdOpenObject
0x180035880  mov     ebx, eax
0x180035882  test    eax, eax
0x180035884  jns     short loc_18003588F
0x180035886  lea     rdx, aBcdopenobjectF_0; "BcdOpenObject failed: 0x%x"
0x18003588d  jmp     short loc_180035812
0x18003588f  mov     rcx, [rbp+var_10]
0x180035893  mov     edx, 5400000Fh
0x180035898  call    cs:__imp_BcdDeleteElement
0x18003589e  mov     rcx, [rbp+var_10]
0x1800358a2  mov     edx, 27000030h
0x1800358a7  call    cs:__imp_BcdDeleteElement
0x1800358ad  mov     rcx, [rbp+var_10]
0x1800358b1  test    rcx, rcx
0x1800358b4  jz      short loc_1800358C0
0x1800358b6  call    cs:__imp_BcdCloseObject
0x1800358bc  mov     [rbp+var_10], rsi
0x1800358c0  test    ebx, ebx
0x1800358c2  jns     short loc_1800358F4
0x1800358c4  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, esi; _ReAgentErrorCodes ReAgentError
0x1800358ca  jnz     short loc_1800358D6
0x1800358cc  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 7; _ReAgentErrorCodes ReAgentError
0x1800358d6  mov     r8d, ebx
0x1800358d9  lea     rdx, aWinreremoverec; "winreRemoveRecoveryEntryFromBCD failed:"...
0x1800358e0  mov     ecx, 1
0x1800358e5  call    UnattendLogW
0x1800358ea  mov     ecx, ebx; Status
0x1800358ec  call    cs:__imp_RtlNtStatusToDosError
0x1800358f2  mov     esi, eax
0x1800358f4  mov     eax, esi
0x1800358f6  mov     rcx, [rbp+var_8]
0x1800358fa  xor     rcx, rsp; StackCookie
0x1800358fd  call    __security_check_cookie
0x180035902  mov     rbx, [rsp+30h+arg_10]
0x180035907  mov     rsi, [rsp+30h+arg_18]
0x18003590c  add     rsp, 30h
0x180035910  pop     r14
0x180035912  pop     rdi
0x180035913  pop     rbp
0x180035914  retn
```
