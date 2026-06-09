# FwAppCParserSid(ushort const *,_SID * *)

- ea: `0x180010c60`
- end: `0x180010db8`
- name: `?FwAppCParserSid@@YAJPEBGPEAPEAU_SID@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _SID **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180010a10`
- `0x180010c40`
- `0x180010c50`

## callees

- `0x1800042c4`
- `0x180010c60`
- `0x18001f650`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180010ca7`
- `ntdll!RtlLengthSid` at `0x180010ca7`
- `ntdll!RtlCopySid` at `0x180010ccb`
- `ntdll!RtlCopySid` at `0x180010ccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010d02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010cd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010cd9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180010c8b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180010c8b`
- `fwbase!FwAlloc` at `0x180010cb1`
- `fwbase!FwAlloc` at `0x180010cb1`

## pseudocode

```c
__int64 __fastcall FwAppCParserSid(const unsigned __int16 *a1, struct _SID **a2)
{
  PSID v3; // rsi
  ULONG v4; // ebp
  struct _SID *v5; // rax
  struct _SID *v6; // rdi
  PSID v7; // rcx
  signed int LastError; // eax
  unsigned int v10; // ebx
  LPCOLESTR v11; // rcx
  PSID Sid; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
  {
    v3 = Sid;
    v4 = RtlLengthSid(Sid);
    v5 = (struct _SID *)FwAlloc(v4);
    v6 = v5;
    if ( v5 )
    {
      RtlCopySid(v4, v5, v3);
      v7 = Sid;
      *a2 = v6;
      LocalFree(v7);
      return 0;
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control )
      {
        if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids, 14);
          v11 = WPP_GLOBAL_Control;
        }
        if ( v11 != (LPCOLESTR)&WPP_GLOBAL_Control && (v11[14] & 1) != 0 )
          WPP_SF_d(*((_QWORD *)v11 + 2), 51, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids, 2147942414LL);
      }
      return 2147942414LL;
    }
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids, v10);
    return v10;
  }
}

```

## disassembly

```asm
0x180010c60  push    rbx
0x180010c62  push    rdi
0x180010c63  push    r14
0x180010c65  sub     rsp, 30h
0x180010c69  mov     rax, cs:__security_cookie
0x180010c70  xor     rax, rsp
0x180010c73  mov     [rsp+48h+var_20], rax
0x180010c78  xor     r14d, r14d
0x180010c7b  mov     rbx, rdx
0x180010c7e  mov     [rdx], r14
0x180010c81  lea     rdx, [rsp+48h+Sid]; Sid
0x180010c86  mov     [rsp+48h+Sid], r14
0x180010c8b  call    cs:__imp_ConvertStringSidToSidW
0x180010c91  test    eax, eax
0x180010c93  jz      short loc_180010D02
0x180010c95  mov     [rsp+48h+arg_10], rbp
0x180010c9a  mov     [rsp+48h+arg_18], rsi
0x180010c9f  mov     rsi, [rsp+48h+Sid]
0x180010ca4  mov     rcx, rsi; Sid
0x180010ca7  call    cs:__imp_RtlLengthSid
0x180010cad  mov     ecx, eax
0x180010caf  mov     ebp, eax
0x180010cb1  call    cs:__imp_FwAlloc
0x180010cb7  mov     rdi, rax
0x180010cba  test    rax, rax
0x180010cbd  jz      loc_180010D50
0x180010cc3  mov     r8, rsi; SourceSid
0x180010cc6  mov     rdx, rax; DestinationSid
0x180010cc9  mov     ecx, ebp; DestinationSidLength
0x180010ccb  call    cs:__imp_RtlCopySid
0x180010cd1  mov     rcx, [rsp+48h+Sid]; hMem
0x180010cd6  mov     [rbx], rdi
0x180010cd9  call    cs:__imp_LocalFree
0x180010cdf  mov     eax, r14d
0x180010ce2  mov     rbp, [rsp+48h+arg_10]
0x180010ce7  mov     rsi, [rsp+48h+arg_18]
0x180010cec  mov     rcx, [rsp+48h+var_20]
0x180010cf1  xor     rcx, rsp; StackCookie
0x180010cf4  call    __security_check_cookie
0x180010cf9  add     rsp, 30h
0x180010cfd  pop     r14
0x180010cff  pop     rdi
0x180010d00  pop     rbx
0x180010d01  retn
0x180010d02  call    cs:__imp_GetLastError
0x180010d08  mov     ebx, eax
0x180010d0a  test    eax, eax
0x180010d0c  jg      short loc_180010D25
0x180010d0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d15  lea     rdi, WPP_GLOBAL_Control
0x180010d1c  cmp     rcx, rdi
0x180010d1f  jnz     short loc_180010D30
0x180010d21  mov     eax, ebx
0x180010d23  jmp     short loc_180010CEC
0x180010d25  movzx   ebx, ax
0x180010d28  or      ebx, 80070000h
0x180010d2e  jmp     short loc_180010D0E
0x180010d30  test    byte ptr [rcx+1Ch], 1
0x180010d34  jz      short loc_180010D21
0x180010d36  mov     rcx, [rcx+10h]
0x180010d3a  lea     r8, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids
0x180010d41  mov     edx, 32h ; '2'
0x180010d46  mov     r9d, ebx
0x180010d49  call    WPP_SF_d
0x180010d4e  jmp     short loc_180010D21
0x180010d50  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d57  lea     rdi, WPP_GLOBAL_Control
0x180010d5e  cmp     rcx, rdi
0x180010d61  jz      short loc_180010DAE
0x180010d63  test    byte ptr [rcx+1Ch], 1
0x180010d67  jz      short loc_180010D88
0x180010d69  mov     rcx, [rcx+10h]
0x180010d6d  lea     r8, WPP_fffe468632e1369343f769dcfdbda4a1_Traceguids
0x180010d74  mov     edx, 0Eh
0x180010d79  mov     r9d, edx
0x180010d7c  call    WPP_SF_d
0x180010d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d88  cmp     rcx, rdi
0x180010d8b  jz      short loc_180010DAE
0x180010d8d  test    byte ptr [rcx+1Ch], 1
0x180010d91  jz      short loc_180010DAE
0x180010d93  mov     rcx, [rcx+10h]
0x180010d97  lea     r8, WPP_8aa7cdc55e8b3bac71a43653bf0f119d_Traceguids
0x180010d9e  mov     edx, 33h ; '3'
0x180010da3  mov     r9d, 8007000Eh
0x180010da9  call    WPP_SF_d
0x180010dae  mov     eax, 8007000Eh
0x180010db3  jmp     loc_180010CE2
```
