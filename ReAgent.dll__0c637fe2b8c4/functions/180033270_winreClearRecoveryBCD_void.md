# winreClearRecoveryBCD(void *)

- ea: `0x180033270`
- end: `0x1800333ab`
- name: `?winreClearRecoveryBCD@@YAKPEAX@Z`
- size: `315`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1800356d4`
- `0x1800361ac`

## callees

- `0x1800059fc`
- `0x180033270`
- `0x1800357cc`
- `0x18005cf30`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800332d6`
- `ntdll!RtlNtStatusToDosError` at `0x1800332d6`
- `bcd!BcdCloseObject` at `0x180033387`
- `bcd!BcdCloseObject` at `0x180033387`
- `bcd!BcdGetElementData` at `0x1800332fc`
- `bcd!BcdGetElementData` at `0x18003332b`
- `bcd!BcdGetElementData` at `0x1800332fc`
- `bcd!BcdGetElementData` at `0x18003332b`
- `bcd!BcdOpenObject` at `0x1800332b4`
- `bcd!BcdOpenObject` at `0x1800332b4`

## string_xrefs

- `0x1800332c3`: `Failed to open bootmgr object: 0x%x`
- `0x18003336d`: `Failed to remove recovery entry from BCD: 0x%x`

## pseudocode

```c
__int64 __fastcall winreClearRecoveryBCD(void *a1)
{
  int v2; // eax
  NTSTATUS v3; // ebx
  ULONG v4; // ebx
  int ElementData; // eax
  int v6; // eax
  ULONG v7; // eax
  __int64 v9; // [rsp+20h] [rbp-30h] BYREF
  int v10; // [rsp+28h] [rbp-28h] BYREF
  __int128 v11; // [rsp+30h] [rbp-20h] BYREF

  v9 = 0;
  v10 = 0;
  v11 = 0;
  v2 = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v9);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v10 = 16;
    ElementData = BcdGetElementData(v9, 587202563, &v11, &v10);
    if ( ElementData >= 0
      || (UnattendLogW(
            0,
            L"Bootmgr has no default object set (0x%x), will use first display order entry instead",
            (unsigned int)ElementData),
          v10 = 16,
          v6 = BcdGetElementData(v9, 603979777, &v11, &v10),
          v6 >= 0) )
    {
      v7 = winreRemoveRecoveryEntryFromBCD(a1, (__int64)&v11);
      v4 = v7;
      if ( v7 )
        UnattendLogW(1, L"Failed to remove recovery entry from BCD: 0x%x", v7);
    }
    else
    {
      UnattendLogW(0, L"Couldn't get top of display order: 0x%x", (unsigned int)v6);
      UnattendLogW(0, L"We will report success and exit because recovery BCD is not used at all.");
      v4 = 0;
    }
  }
  else
  {
    UnattendLogW(1, L"Failed to open bootmgr object: 0x%x", (unsigned int)v2);
    v4 = RtlNtStatusToDosError(v3);
  }
  if ( v9 )
    BcdCloseObject();
  return v4;
}

```

## disassembly

```asm
0x180033270  mov     [rsp-8+arg_8], rbx
0x180033275  mov     [rsp-8+arg_10], rdi
0x18003327a  push    rbp
0x18003327b  mov     rbp, rsp
0x18003327e  sub     rsp, 50h
0x180033282  mov     rax, cs:__security_cookie
0x180033289  xor     rax, rsp
0x18003328c  mov     [rbp+var_10], rax
0x180033290  xorps   xmm0, xmm0
0x180033293  mov     [rbp+var_30], 0
0x18003329b  lea     r8, [rbp+var_30]
0x18003329f  mov     [rbp+var_28], 0
0x1800332a6  lea     rdx, GUID_WINDOWS_BOOTMGR
0x1800332ad  mov     rdi, rcx
0x1800332b0  movups  [rbp+var_20], xmm0
0x1800332b4  call    cs:__imp_BcdOpenObject
0x1800332ba  mov     ebx, eax
0x1800332bc  test    eax, eax
0x1800332be  jns     short loc_1800332E3
0x1800332c0  mov     r8d, eax
0x1800332c3  lea     rdx, aFailedToOpenBo_0; "Failed to open bootmgr object: 0x%x"
0x1800332ca  mov     ecx, 1
0x1800332cf  call    UnattendLogW
0x1800332d4  mov     ecx, ebx; Status
0x1800332d6  call    cs:__imp_RtlNtStatusToDosError
0x1800332dc  mov     ebx, eax
0x1800332de  jmp     loc_18003337E
0x1800332e3  mov     rcx, [rbp+var_30]
0x1800332e7  lea     r9, [rbp+var_28]
0x1800332eb  mov     ebx, 10h
0x1800332f0  lea     r8, [rbp+var_20]
0x1800332f4  mov     edx, 23000003h
0x1800332f9  mov     [rbp+var_28], ebx
0x1800332fc  call    cs:__imp_BcdGetElementData
0x180033302  test    eax, eax
0x180033304  jns     short loc_180033358
0x180033306  mov     r8d, eax
0x180033309  lea     rdx, aBootmgrHasNoDe; "Bootmgr has no default object set (0x%x"...
0x180033310  xor     ecx, ecx
0x180033312  call    UnattendLogW
0x180033317  mov     rcx, [rbp+var_30]
0x18003331b  lea     r9, [rbp+var_28]
0x18003331f  lea     r8, [rbp+var_20]
0x180033323  mov     [rbp+var_28], ebx
0x180033326  mov     edx, 24000001h
0x18003332b  call    cs:__imp_BcdGetElementData
0x180033331  test    eax, eax
0x180033333  jns     short loc_180033358
0x180033335  mov     r8d, eax
0x180033338  lea     rdx, aCouldnTGetTopO; "Couldn't get top of display order: 0x%x"
0x18003333f  xor     ecx, ecx
0x180033341  call    UnattendLogW
0x180033346  lea     rdx, aWeWillReportSu; "We will report success and exit because"...
0x18003334d  xor     ecx, ecx
0x18003334f  call    UnattendLogW
0x180033354  xor     ebx, ebx
0x180033356  jmp     short loc_18003337E
0x180033358  lea     rdx, [rbp+var_20]
0x18003335c  mov     rcx, rdi; void *
0x18003335f  call    winreRemoveRecoveryEntryFromBCD
0x180033364  mov     ebx, eax
0x180033366  test    eax, eax
0x180033368  jz      short loc_18003337E
0x18003336a  mov     r8d, eax
0x18003336d  lea     rdx, aFailedToRemove_0; "Failed to remove recovery entry from BC"...
0x180033374  mov     ecx, 1
0x180033379  call    UnattendLogW
0x18003337e  mov     rcx, [rbp+var_30]
0x180033382  test    rcx, rcx
0x180033385  jz      short loc_18003338D
0x180033387  call    cs:__imp_BcdCloseObject
0x18003338d  mov     eax, ebx
0x18003338f  mov     rcx, [rbp+var_10]
0x180033393  xor     rcx, rsp; StackCookie
0x180033396  call    __security_check_cookie
0x18003339b  mov     rbx, [rsp+50h+arg_8]
0x1800333a0  mov     rdi, [rsp+50h+arg_10]
0x1800333a5  add     rsp, 50h
0x1800333a9  pop     rbp
0x1800333aa  retn
```
