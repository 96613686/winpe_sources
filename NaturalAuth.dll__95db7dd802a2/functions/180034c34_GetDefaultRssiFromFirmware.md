# GetDefaultRssiFromFirmware

- ea: `0x180034c34`
- end: `0x180034e97`
- name: `GetDefaultRssiFromFirmware`
- size: `611`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800349d4`

## callees

- `0x18000a7f8`
- `0x180019bbc`
- `0x180034c34`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180034c72`
- `ntdll!RtlAdjustPrivilege` at `0x180034e71`
- `ntdll!RtlAdjustPrivilege` at `0x180034c72`
- `ntdll!RtlAdjustPrivilege` at `0x180034e71`
- `ntdll!RtlNtStatusToDosError` at `0x180034cb3`
- `ntdll!RtlNtStatusToDosError` at `0x180034cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034d7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034e42`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x180034cea`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x180034dc8`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x180034cea`
- `api-ms-win-core-firmware-l1-1-0!GetFirmwareEnvironmentVariableW` at `0x180034dc8`

## pseudocode

```c
__int64 __fastcall GetDefaultRssiFromFirmware(char *a1, char *a2)
{
  char v2; // di
  char v5; // r15
  NTSTATUS v6; // eax
  NTSTATUS v7; // r14d
  ULONG v8; // r14d
  const WCHAR *v9; // rax
  LPCWSTR v10; // rdx
  char v11; // r9
  DWORD LastError; // eax
  const WCHAR *v13; // rax
  LPCWSTR v14; // rdx
  char v15; // r9
  DWORD v16; // eax
  __int64 result; // rax
  unsigned __int8 OldValue; // [rsp+60h] [rbp+40h] BYREF
  unsigned int pBuffer; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v20; // [rsp+70h] [rbp+50h] BYREF

  OldValue = 0;
  pBuffer = -1;
  v2 = 1;
  v20 = -1;
  v5 = 1;
  v6 = RtlAdjustPrivilege(0x16u, 1u, 0, &OldValue);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = 0;
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_18005FA80);
    v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_18005FA60);
    if ( GetFirmwareEnvironmentVariableW(v9, v10, &pBuffer, 4u) )
    {
      v11 = pBuffer;
      if ( pBuffer > 0x7F )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids, pBuffer);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids, pBuffer);
          v11 = pBuffer;
        }
        v5 = -v11;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids, LastError);
    }
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_18005FA80);
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_18005FA40);
    if ( GetFirmwareEnvironmentVariableW(v13, v14, &v20, 4u) )
    {
      v15 = v20;
      if ( v20 > 0x7F )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids, v20);
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids, v20);
          v15 = v20;
        }
        v2 = -v15;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v16 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids, v16);
    }
    RtlAdjustPrivilege(0x16u, OldValue, 0, &OldValue);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        &WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids,
        (unsigned int)v6);
    v8 = RtlNtStatusToDosError(v7);
  }
  result = v8;
  *a1 = v5;
  *a2 = v2;
  return result;
}

```

## disassembly

```asm
0x180034c34  mov     [rsp-38h+arg_18], rbx
0x180034c39  push    rbp
0x180034c3a  push    rsi
0x180034c3b  push    rdi
0x180034c3c  push    r12
0x180034c3e  push    r13
0x180034c40  push    r14
0x180034c42  push    r15
0x180034c44  mov     rbp, rsp
0x180034c47  sub     rsp, 20h
0x180034c4b  or      eax, 0FFFFFFFFh
0x180034c4e  mov     [rbp+OldValue], 0
0x180034c52  xor     r8d, r8d; ForThread
0x180034c55  mov     [rbp+pBuffer], eax
0x180034c58  mov     dil, 1
0x180034c5b  mov     [rbp+arg_10], eax
0x180034c5e  mov     r12, rdx
0x180034c61  lea     r9, [rbp+OldValue]; OldValue
0x180034c65  mov     r13, rcx
0x180034c68  mov     dl, dil; NewValue
0x180034c6b  lea     ecx, [r8+16h]; Privilege
0x180034c6f  mov     r15b, dil
0x180034c72  call    cs:__imp_RtlAdjustPrivilege
0x180034c78  mov     r14d, eax
0x180034c7b  test    eax, eax
0x180034c7d  jns     short loc_180034CC1
0x180034c7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180034c86  lea     rbx, WPP_GLOBAL_Control
0x180034c8d  cmp     rcx, rbx
0x180034c90  jz      short loc_180034CB0
0x180034c92  test    [rcx+1Ch], dil
0x180034c96  jz      short loc_180034CB0
0x180034c98  mov     rcx, [rcx+10h]
0x180034c9c  lea     r8, WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids
0x180034ca3  mov     edx, 42h ; 'B'
0x180034ca8  mov     r9d, eax
0x180034cab  call    WPP_SF_d
0x180034cb0  mov     ecx, r14d; Status
0x180034cb3  call    cs:__imp_RtlNtStatusToDosError
0x180034cb9  mov     r14d, eax
0x180034cbc  jmp     loc_180034E77
0x180034cc1  lea     rcx, qword_18005FA80
0x180034cc8  xor     r14d, r14d
0x180034ccb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034cd0  lea     rcx, qword_18005FA60
0x180034cd7  mov     rdx, rax
0x180034cda  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034cdf  mov     rcx, rax; lpName
0x180034ce2  lea     r9d, [r14+4]; nSize
0x180034ce6  lea     r8, [rbp+pBuffer]; pBuffer
0x180034cea  call    cs:__imp_GetFirmwareEnvironmentVariableW
0x180034cf0  lea     rsi, WPP_2a4849df4c173e483f2416a1f7178d1a_Traceguids
0x180034cf7  test    eax, eax
0x180034cf9  jz      short loc_180034D66
0x180034cfb  mov     r9d, [rbp+pBuffer]
0x180034cff  cmp     r9d, 7Fh
0x180034d03  ja      short loc_180034D3A
0x180034d05  mov     rcx, cs:WPP_GLOBAL_Control
0x180034d0c  lea     rbx, WPP_GLOBAL_Control
0x180034d13  cmp     rcx, rbx
0x180034d16  jz      short loc_180034D32
0x180034d18  test    byte ptr [rcx+1Ch], 4
0x180034d1c  jz      short loc_180034D32
0x180034d1e  mov     rcx, [rcx+10h]
0x180034d22  lea     edx, [r14+43h]
0x180034d26  mov     r8, rsi
0x180034d29  call    WPP_SF_d
0x180034d2e  mov     r9d, [rbp+pBuffer]
0x180034d32  mov     r15b, r9b
0x180034d35  neg     r15b
0x180034d38  jmp     short loc_180034DA0
0x180034d3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180034d41  lea     rbx, WPP_GLOBAL_Control
0x180034d48  cmp     rcx, rbx
0x180034d4b  jz      short loc_180034DA0
0x180034d4d  test    [rcx+1Ch], dil
0x180034d51  jz      short loc_180034DA0
0x180034d53  mov     rcx, [rcx+10h]
0x180034d57  mov     edx, 44h ; 'D'
0x180034d5c  mov     r8, rsi
0x180034d5f  call    WPP_SF_d
0x180034d64  jmp     short loc_180034DA0
0x180034d66  mov     rax, cs:WPP_GLOBAL_Control
0x180034d6d  lea     rbx, WPP_GLOBAL_Control
0x180034d74  cmp     rax, rbx
0x180034d77  jz      short loc_180034DA0
0x180034d79  test    byte ptr [rax+1Ch], 4
0x180034d7d  jz      short loc_180034DA0
0x180034d7f  call    cs:__imp_GetLastError
0x180034d85  mov     rcx, cs:WPP_GLOBAL_Control
0x180034d8c  mov     edx, 45h ; 'E'
0x180034d91  mov     r9d, eax
0x180034d94  mov     r8, rsi
0x180034d97  mov     rcx, [rcx+10h]
0x180034d9b  call    WPP_SF_d
0x180034da0  lea     rcx, qword_18005FA80
0x180034da7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034dac  lea     rcx, qword_18005FA40
0x180034db3  mov     rdx, rax
0x180034db6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180034dbb  mov     rcx, rax; lpName
0x180034dbe  lea     r8, [rbp+arg_10]; pBuffer
0x180034dc2  mov     r9d, 4; nSize
0x180034dc8  call    cs:__imp_GetFirmwareEnvironmentVariableW
0x180034dce  test    eax, eax
0x180034dd0  jz      short loc_180034E30
0x180034dd2  mov     r9d, [rbp+arg_10]
0x180034dd6  cmp     r9d, 7Fh
0x180034dda  ja      short loc_180034E0B
0x180034ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x180034de3  cmp     rcx, rbx
0x180034de6  jz      short loc_180034E03
0x180034de8  test    byte ptr [rcx+1Ch], 4
0x180034dec  jz      short loc_180034E03
0x180034dee  mov     rcx, [rcx+10h]
0x180034df2  mov     edx, 46h ; 'F'
0x180034df7  mov     r8, rsi
0x180034dfa  call    WPP_SF_d
0x180034dff  mov     r9d, [rbp+arg_10]
0x180034e03  mov     dil, r9b
0x180034e06  neg     dil
0x180034e09  jmp     short loc_180034E63
0x180034e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e12  cmp     rcx, rbx
0x180034e15  jz      short loc_180034E63
0x180034e17  test    [rcx+1Ch], dil
0x180034e1b  jz      short loc_180034E63
0x180034e1d  mov     rcx, [rcx+10h]
0x180034e21  mov     edx, 47h ; 'G'
0x180034e26  mov     r8, rsi
0x180034e29  call    WPP_SF_d
0x180034e2e  jmp     short loc_180034E63
0x180034e30  mov     rax, cs:WPP_GLOBAL_Control
0x180034e37  cmp     rax, rbx
0x180034e3a  jz      short loc_180034E63
0x180034e3c  test    byte ptr [rax+1Ch], 4
0x180034e40  jz      short loc_180034E63
0x180034e42  call    cs:__imp_GetLastError
0x180034e48  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e4f  mov     edx, 48h ; 'H'
0x180034e54  mov     r9d, eax
0x180034e57  mov     r8, rsi
0x180034e5a  mov     rcx, [rcx+10h]
0x180034e5e  call    WPP_SF_d
0x180034e63  mov     dl, [rbp+OldValue]; NewValue
0x180034e66  lea     r9, [rbp+OldValue]; OldValue
0x180034e6a  xor     r8d, r8d; ForThread
0x180034e6d  lea     ecx, [r8+16h]; Privilege
0x180034e71  call    cs:__imp_RtlAdjustPrivilege
0x180034e77  mov     rbx, [rsp+20h+arg_18]
0x180034e7c  mov     eax, r14d
0x180034e7f  mov     [r13+0], r15b
0x180034e83  mov     [r12], dil
0x180034e87  add     rsp, 20h
0x180034e8b  pop     r15
0x180034e8d  pop     r14
0x180034e8f  pop     r13
0x180034e91  pop     r12
0x180034e93  pop     rdi
0x180034e94  pop     rsi
0x180034e95  pop     rbp
0x180034e96  retn
```
