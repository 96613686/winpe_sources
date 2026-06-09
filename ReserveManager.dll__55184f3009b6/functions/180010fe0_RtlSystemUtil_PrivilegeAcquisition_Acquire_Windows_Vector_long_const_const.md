# RtlSystemUtil::PrivilegeAcquisition::Acquire(Windows::Vector<long const> const &)

- ea: `0x180010fe0`
- end: `0x180011050`
- name: `?Acquire@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@@Z`
- size: `112`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `8`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b344`
- `0x1800177f8`
- `0x18001a120`
- `0x18001aff0`
- `0x18001b8f0`
- `0x18001bd30`
- `0x18001c520`
- `0x180020778`

## callees

- `0x18000fafc`
- `0x180010fe0`
- `0x180011058`

## string_xrefs

- `0x180010ffe`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18001101a`: `RtlSystemUtil::PrivilegeAcquisition::Acquire`

## pseudocode

```c
__int64 __fastcall RtlSystemUtil::PrivilegeAcquisition::Acquire(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  _BYTE v3[8]; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v4[6]; // [rsp+28h] [rbp-30h] BYREF

  v3[0] = 0;
  result = RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble(a1, a2, v3);
  if ( (int)result >= 0 )
  {
    if ( v3[0] )
    {
      return 0;
    }
    else
    {
      v4[2] = 747;
      v4[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v4[1] = "RtlSystemUtil::PrivilegeAcquisition::Acquire";
      v4[3] = "fAcquired";
      RtlReportErrorOrigination(v4, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225569LL);
      return 3221225569LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010fe0  sub     rsp, 58h
0x180010fe4  lea     r8, [rsp+58h+var_38]
0x180010fe9  mov     [rsp+58h+var_38], 0
0x180010fee  call    ?AcquireIfAble@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@PEA_N@Z; RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble(Windows::Vector<long const> const &,bool *)
0x180010ff3  test    eax, eax
0x180010ff5  js      short loc_18001104B
0x180010ff7  cmp     [rsp+58h+var_38], 0
0x180010ffc  jnz     short loc_180011049
0x180010ffe  lea     rax, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180011005  mov     [rsp+58h+var_20], 2EBh
0x18001100e  mov     [rsp+58h+var_30], rax
0x180011013  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001101a  lea     rax, aRtlsystemutilP_0; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x180011021  mov     r8d, 0C0000061h
0x180011027  mov     [rsp+58h+var_28], rax
0x18001102c  lea     rcx, [rsp+58h+var_30]
0x180011031  lea     rax, aFacquired; "fAcquired"
0x180011038  mov     [rsp+58h+var_18], rax
0x18001103d  call    RtlReportErrorOrigination
0x180011042  mov     eax, 0C0000061h
0x180011047  jmp     short loc_18001104B
0x180011049  xor     eax, eax
0x18001104b  add     rsp, 58h
0x18001104f  retn
```
