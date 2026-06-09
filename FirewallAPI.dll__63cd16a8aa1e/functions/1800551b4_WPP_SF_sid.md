# WPP_SF__sid_

- ea: `0x1800551b4`
- end: `0x180055246`
- name: `WPP_SF__sid_`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180053b70`

## callees

- `0x1800551b4`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180055230`
- `ntdll!EtwTraceMessage` at `0x180055230`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800551de`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800551de`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800551d1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800551f5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800551d1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800551f5`

## pseudocode

```c
__int64 __fastcall WPP_SF__sid_(__int64 a1, __int64 a2, __int64 a3, char *a4)
{
  char *v4; // rbx
  DWORD LengthSid; // edi

  v4 = a4;
  if ( a4 && IsValidSid(a4) )
  {
    LengthSid = GetLengthSid(v4);
  }
  else
  {
    LengthSid = 5;
    if ( !v4 )
    {
LABEL_6:
      v4 = "NULL";
      return EtwTraceMessage(a1, 43, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, 463, v4, LengthSid, 0);
    }
  }
  if ( !IsValidSid(v4) )
    goto LABEL_6;
  return EtwTraceMessage(a1, 43, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, 463, v4, LengthSid, 0);
}

```

## disassembly

```asm
0x1800551b4  mov     [rsp+arg_0], rbx
0x1800551b9  mov     [rsp+arg_8], rsi
0x1800551be  push    rdi
0x1800551bf  sub     rsp, 40h
0x1800551c3  mov     rbx, r9
0x1800551c6  mov     rsi, rcx
0x1800551c9  test    r9, r9
0x1800551cc  jz      short loc_1800551E8
0x1800551ce  mov     rcx, rbx; pSid
0x1800551d1  call    cs:__imp_IsValidSid
0x1800551d7  test    eax, eax
0x1800551d9  jz      short loc_1800551E8
0x1800551db  mov     rcx, rbx; pSid
0x1800551de  call    cs:__imp_GetLengthSid
0x1800551e4  mov     edi, eax
0x1800551e6  jmp     short loc_1800551F2
0x1800551e8  mov     edi, 5
0x1800551ed  test    rbx, rbx
0x1800551f0  jz      short loc_1800551FF
0x1800551f2  mov     rcx, rbx; pSid
0x1800551f5  call    cs:__imp_IsValidSid
0x1800551fb  test    eax, eax
0x1800551fd  jnz     short loc_180055206
0x1800551ff  lea     rbx, aNull_0; "NULL"
0x180055206  mov     eax, edi
0x180055208  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18005520f  mov     [rsp+48h+var_18], 0
0x180055218  mov     r9d, 1CFh
0x18005521e  mov     [rsp+48h+var_20], rax
0x180055223  mov     edx, 2Bh ; '+'
0x180055228  mov     rcx, rsi
0x18005522b  mov     [rsp+48h+var_28], rbx
0x180055230  call    cs:__imp_EtwTraceMessage
0x180055236  mov     rbx, [rsp+48h+arg_0]
0x18005523b  mov     rsi, [rsp+48h+arg_8]
0x180055240  add     rsp, 40h
0x180055244  pop     rdi
0x180055245  retn
```
