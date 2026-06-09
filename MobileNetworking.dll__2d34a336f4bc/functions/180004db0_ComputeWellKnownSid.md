# ComputeWellKnownSid

- ea: `0x180004db0`
- end: `0x180004ef5`
- name: `ComputeWellKnownSid`
- size: `325`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002080`
- `0x180008b00`

## callees

- `0x180004390`
- `0x180004db0`
- `0x180004f00`
- `0x180008ff0`
- `0x180009130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e71`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180004e67`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180004e67`

## string_xrefs

- `0x180004e0e`: `ComputeWellKnownSid`

## pseudocode

```c
__int64 __fastcall ComputeWellKnownSid(WELL_KNOWN_SID_TYPE WellKnownSidType, _QWORD *a2)
{
  SIZE_T v3; // rcx
  DWORD v5; // eax
  DWORD v6; // ebx
  PSID v7; // rdi
  DWORD LastError; // eax
  DWORD cbSid; // [rsp+50h] [rbp+18h] BYREF
  PSID pSid; // [rsp+58h] [rbp+20h] BYREF

  pSid = 0;
  v3 = 68;
  cbSid = 68;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_fd6184a389643c6486807174a58ed414_Traceguids);
    v3 = cbSid;
  }
  v5 = AllocateMemory(v3, &pSid, (int)"ComputeWellKnownSid", 139);
  v6 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v5);
    v7 = pSid;
  }
  else
  {
    v7 = pSid;
    if ( CreateWellKnownSid(WellKnownSidType, 0, pSid, &cbSid) || (LastError = GetLastError(), (v6 = LastError) == 0) )
    {
      *a2 = v7;
      v7 = 0;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_fd6184a389643c6486807174a58ed414_Traceguids, LastError);
    }
  }
  FreeWellKnownSid(v7);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_fd6184a389643c6486807174a58ed414_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180004db0  mov     [rsp+arg_0], rbx
0x180004db5  mov     [rsp+arg_8], rbp
0x180004dba  push    rsi
0x180004dbb  push    rdi
0x180004dbc  push    r14
0x180004dbe  sub     rsp, 20h
0x180004dc2  mov     ebp, ecx
0x180004dc4  mov     [rsp+38h+pSid], 0
0x180004dcd  mov     ecx, 44h ; 'D'
0x180004dd2  mov     rsi, rdx
0x180004dd5  mov     [rsp+38h+cbSid], ecx
0x180004dd9  mov     rax, cs:WPP_GLOBAL_Control
0x180004de0  lea     r14, WPP_GLOBAL_Control
0x180004de7  cmp     rax, r14
0x180004dea  jz      short loc_180004E08
0x180004dec  test    byte ptr [rax+1Ch], 8
0x180004df0  jz      short loc_180004E08
0x180004df2  mov     edx, ecx
0x180004df4  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180004dfb  mov     rcx, [rax+10h]
0x180004dff  call    WPP_SF_
0x180004e04  mov     ecx, [rsp+38h+cbSid]; dwBytes
0x180004e08  mov     r9d, 28Bh
0x180004e0e  lea     r8, aComputewellkno; "ComputeWellKnownSid"
0x180004e15  lea     rdx, [rsp+38h+pSid]
0x180004e1a  call    AllocateMemory
0x180004e1f  mov     ebx, eax
0x180004e21  test    eax, eax
0x180004e23  jz      short loc_180004E56
0x180004e25  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e2c  cmp     rcx, r14
0x180004e2f  jz      short loc_180004E4F
0x180004e31  test    byte ptr [rcx+1Ch], 4
0x180004e35  jz      short loc_180004E4F
0x180004e37  mov     rcx, [rcx+10h]
0x180004e3b  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180004e42  mov     edx, 45h ; 'E'
0x180004e47  mov     r9d, eax
0x180004e4a  call    WPP_SF_L
0x180004e4f  mov     rdi, [rsp+38h+pSid]
0x180004e54  jmp     short loc_180004EAE
0x180004e56  mov     rdi, [rsp+38h+pSid]
0x180004e5b  lea     r9, [rsp+38h+cbSid]; cbSid
0x180004e60  mov     r8, rdi; pSid
0x180004e63  xor     edx, edx; DomainSid
0x180004e65  mov     ecx, ebp; WellKnownSidType
0x180004e67  call    cs:__imp_CreateWellKnownSid
0x180004e6d  test    eax, eax
0x180004e6f  jnz     short loc_180004EA9
0x180004e71  call    cs:__imp_GetLastError
0x180004e77  mov     ebx, eax
0x180004e79  test    eax, eax
0x180004e7b  jz      short loc_180004EA9
0x180004e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e84  cmp     rcx, r14
0x180004e87  jz      short loc_180004EAE
0x180004e89  test    byte ptr [rcx+1Ch], 4
0x180004e8d  jz      short loc_180004EAE
0x180004e8f  mov     rcx, [rcx+10h]
0x180004e93  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180004e9a  mov     edx, 46h ; 'F'
0x180004e9f  mov     r9d, eax
0x180004ea2  call    WPP_SF_L
0x180004ea7  jmp     short loc_180004EAE
0x180004ea9  mov     [rsi], rdi
0x180004eac  xor     edi, edi
0x180004eae  mov     rcx, rdi
0x180004eb1  call    FreeWellKnownSid
0x180004eb6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ebd  cmp     rcx, r14
0x180004ec0  jz      short loc_180004EE0
0x180004ec2  test    byte ptr [rcx+1Ch], 8
0x180004ec6  jz      short loc_180004EE0
0x180004ec8  mov     rcx, [rcx+10h]
0x180004ecc  lea     r8, WPP_fd6184a389643c6486807174a58ed414_Traceguids
0x180004ed3  mov     edx, 47h ; 'G'
0x180004ed8  mov     r9d, ebx
0x180004edb  call    WPP_SF_L
0x180004ee0  mov     rbp, [rsp+38h+arg_8]
0x180004ee5  mov     eax, ebx
0x180004ee7  mov     rbx, [rsp+38h+arg_0]
0x180004eec  add     rsp, 20h
0x180004ef0  pop     r14
0x180004ef2  pop     rdi
0x180004ef3  pop     rsi
0x180004ef4  retn
```
