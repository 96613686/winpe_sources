# StringUtility::SidToString(void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x1800779bc`
- end: `0x180077aae`
- name: `?SidToString@StringUtility@@SAJPEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `10`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800116b8`
- `0x180023ca8`
- `0x180028088`
- `0x180035be4`
- `0x1800363a0`
- `0x180042960`
- `0x180047320`
- `0x180051e78`
- `0x18006b740`
- `0x1800788a4`

## callees

- `0x1800065e8`
- `0x18000685c`
- `0x180006908`
- `0x180071e14`
- `0x1800779bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077a41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077a9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077a9b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180077a37`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180077a37`

## pseudocode

```c
__int64 __fastcall StringUtility::SidToString(PSID Sid, __int64 a2)
{
  signed int v4; // ebx
  signed int LastError; // eax
  unsigned int v6; // eax
  __int64 v7; // rcx
  signed int v9; // [rsp+20h] [rbp-38h]
  int v10; // [rsp+30h] [rbp-28h]
  LPWSTR StringSid; // [rsp+60h] [rbp+8h] BYREF

  StringSid = 0;
  ATL::CSimpleStringT<unsigned short,0>::Empty(a2);
  if ( Sid )
  {
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      v4 = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 < 0 )
      {
        v10 = 396;
        goto LABEL_3;
      }
    }
    v6 = ATL::CSimpleStringT<unsigned short,0>::StringLength(StringSid);
    ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v7, v6);
    goto LABEL_11;
  }
  v4 = -2147024809;
  v10 = 391;
LABEL_3:
  v9 = v4;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v9, "aadstring.cpp", v10, "HRESULT", &base);
LABEL_11:
  LocalFree(StringSid);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800779bc  mov     [rsp+arg_8], rbx
0x1800779c1  push    rdi
0x1800779c2  sub     rsp, 50h
0x1800779c6  mov     rbx, rcx
0x1800779c9  mov     [rsp+58h+StringSid], 0
0x1800779d2  mov     rcx, rdx
0x1800779d5  mov     rdi, rdx
0x1800779d8  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x1800779dd  test    rbx, rbx
0x1800779e0  jnz     short loc_180077A2F
0x1800779e2  lea     rax, base
0x1800779e9  mov     ebx, 80070057h
0x1800779ee  mov     [rsp+58h+var_18], rax
0x1800779f3  lea     rax, aHresult; "HRESULT"
0x1800779fa  mov     [rsp+58h+var_20], rax
0x1800779ff  mov     [rsp+58h+var_28], 187h
0x180077a07  lea     rax, aOnecoreuapDsEx_10+20h; "aadstring.cpp"
0x180077a0e  mov     ecx, 2
0x180077a13  mov     [rsp+58h+var_30], rax
0x180077a18  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180077a1f  mov     r9d, ecx
0x180077a22  mov     [rsp+58h+var_38], ebx
0x180077a26  xor     edx, edx
0x180077a28  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180077a2d  jmp     short loc_180077A96
0x180077a2f  lea     rdx, [rsp+58h+StringSid]; StringSid
0x180077a34  mov     rcx, rbx; Sid
0x180077a37  call    cs:__imp_ConvertSidToStringSidW
0x180077a3d  test    eax, eax
0x180077a3f  jnz     short loc_180077A7C
0x180077a41  call    cs:__imp_GetLastError
0x180077a47  mov     ebx, eax
0x180077a49  test    eax, eax
0x180077a4b  jle     short loc_180077A56
0x180077a4d  movzx   ebx, ax
0x180077a50  or      ebx, 80070000h
0x180077a56  test    ebx, ebx
0x180077a58  jns     short loc_180077A7E
0x180077a5a  lea     rax, base
0x180077a61  mov     [rsp+58h+var_18], rax
0x180077a66  lea     rax, aHresult; "HRESULT"
0x180077a6d  mov     [rsp+58h+var_20], rax
0x180077a72  mov     [rsp+58h+var_28], 18Ch
0x180077a7a  jmp     short loc_180077A07
0x180077a7c  xor     ebx, ebx
0x180077a7e  mov     rcx, [rsp+58h+StringSid]
0x180077a83  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x180077a88  mov     rdx, rcx
0x180077a8b  mov     r8d, eax
0x180077a8e  mov     rcx, rdi
0x180077a91  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180077a96  mov     rcx, [rsp+58h+StringSid]; hMem
0x180077a9b  call    cs:__imp_LocalFree
0x180077aa1  mov     eax, ebx
0x180077aa3  mov     rbx, [rsp+58h+arg_8]
0x180077aa8  add     rsp, 50h
0x180077aac  pop     rdi
0x180077aad  retn
```
