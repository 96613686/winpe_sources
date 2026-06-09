# AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)

- ea: `0x180001be0`
- end: `0x180001c5e`
- name: `?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z`
- size: `126`
- prototype: `unsigned int __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000198c`

## callees

- `0x180001be0`

## import_xrefs

- `ADVAPI32!CreateWellKnownSid` at `0x180001bff`
- `ADVAPI32!CreateWellKnownSid` at `0x180001c41`
- `ADVAPI32!CreateWellKnownSid` at `0x180001bff`
- `ADVAPI32!CreateWellKnownSid` at `0x180001c41`
- `KERNEL32!GlobalAlloc` at `0x180001c29`
- `KERNEL32!GlobalAlloc` at `0x180001c29`
- `KERNEL32!GlobalFree` at `0x180024b33`
- `KERNEL32!GlobalFree` at `0x180024b33`
- `KERNEL32!GetLastError` at `0x180001c0d`
- `KERNEL32!GetLastError` at `0x180024acd`
- `KERNEL32!GetLastError` at `0x180001c0d`
- `KERNEL32!GetLastError` at `0x180024acd`
- `iisutil!PuDbgPrintError` at `0x180024a9d`
- `iisutil!PuDbgPrintError` at `0x180024b19`
- `iisutil!PuDbgPrintError` at `0x180024a9d`
- `iisutil!PuDbgPrintError` at `0x180024b19`

## string_xrefs

- `0x180024a75`: `Creating a sid worked with no memory allocated for it. ( This is not good )\n`
- `0x180024a81`: `AllocateAndCreateWellKnownSid`
- `0x180024afb`: `AllocateAndCreateWellKnownSid`
- `0x180024abe`: `Getting the SID length failed, can't create the sid (Type = %d)\n`
- `0x180024aea`: `Creating SID failed ( SidType = %d )\n`

## pseudocode

```c
__int64 __fastcall AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE WellKnownSidType, void **a2)
{
  HGLOBAL v3; // rdi
  signed int LastError; // eax
  unsigned int v6; // ebx
  const char *v8; // rcx
  __int64 v9; // r8
  SIZE_T dwBytes; // [rsp+80h] [rbp+18h] BYREF

  v3 = 0;
  LODWORD(dwBytes) = 0;
  if ( CreateWellKnownSid(WellKnownSidType, 0, 0, (DWORD *)&dwBytes) )
  {
    v6 = 50;
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\util.cpp",
        2730,
        "AllocateAndCreateWellKnownSid",
        -2147024846,
        "Creating a sid worked with no memory allocated for it. ( This is not good )\n");
    goto LABEL_4;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError == 122 )
  {
    v6 = 0;
    v3 = GlobalAlloc(0, (unsigned int)dwBytes);
    if ( CreateWellKnownSid(WellKnownSidType, 0, v3, (DWORD *)&dwBytes) )
      goto LABEL_4;
    LastError = GetLastError();
    v6 = LastError;
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = "Creating SID failed ( SidType = %d )\n";
      v9 = 2777;
LABEL_16:
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\svcs\\cmp\\asp\\util.cpp",
        v9,
        "AllocateAndCreateWellKnownSid",
        LastError,
        v8);
    }
  }
  else if ( (g_dwDebugFlags & 0xF) != 0 )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v8 = "Getting the SID length failed, can't create the sid (Type = %d)\n";
    v9 = 2748;
    goto LABEL_16;
  }
  if ( v6 && v3 )
  {
    GlobalFree(v3);
    return v6;
  }
LABEL_4:
  *a2 = v3;
  return v6;
}

```

## disassembly

```asm
0x180001be0  mov     rax, rsp
0x180001be3  push    rbx
0x180001be4  push    rsi
0x180001be5  push    rdi
0x180001be6  push    r14
0x180001be8  sub     rsp, 48h
0x180001bec  mov     r14, rdx
0x180001bef  lea     r9, [rax+18h]; cbSid
0x180001bf3  xor     edi, edi
0x180001bf5  xor     edx, edx; DomainSid
0x180001bf7  xor     r8d, r8d; pSid
0x180001bfa  mov     [rax+18h], edi
0x180001bfd  mov     esi, ecx
0x180001bff  call    cs:__imp_CreateWellKnownSid
0x180001c05  test    eax, eax
0x180001c07  jnz     loc_180024A5C
0x180001c0d  call    cs:__imp_GetLastError
0x180001c13  mov     ebx, eax
0x180001c15  cmp     eax, 7Ah ; 'z'
0x180001c18  jnz     loc_180024AA9
0x180001c1e  mov     edx, dword ptr [rsp+68h+dwBytes]; dwBytes
0x180001c25  xor     ecx, ecx; uFlags
0x180001c27  xor     ebx, ebx
0x180001c29  call    cs:__imp_GlobalAlloc
0x180001c2f  lea     r9, [rsp+68h+dwBytes]; cbSid
0x180001c37  xor     edx, edx; DomainSid
0x180001c39  mov     r8, rax; pSid
0x180001c3c  mov     ecx, esi; WellKnownSidType
0x180001c3e  mov     rdi, rax
0x180001c41  call    cs:__imp_CreateWellKnownSid
0x180001c47  test    eax, eax
0x180001c49  jz      loc_180024ACD
0x180001c4f  mov     [r14], rdi
0x180001c52  mov     eax, ebx
0x180001c54  add     rsp, 48h
0x180001c58  pop     r14
0x180001c5a  pop     rdi
0x180001c5b  pop     rsi
0x180001c5c  pop     rbx
0x180001c5d  retn
0x180024a5c  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024a63  mov     ebx, 32h ; '2'
0x180024a68  jz      loc_180001C4F
0x180024a6e  mov     rcx, cs:g_pDebug
0x180024a75  lea     rax, aCreatingASidWo; "Creating a sid worked with no memory al"...
0x180024a7c  mov     [rsp+68h+var_40], rax
0x180024a81  lea     r9, aAllocateandcre; "AllocateAndCreateWellKnownSid"
0x180024a88  mov     r8d, 0AAAh
0x180024a8e  mov     [rsp+68h+var_48], 80070032h
0x180024a96  lea     rdx, aInetsrvIisSvcs_3; "inetsrv\\iis\\svcs\\cmp\\asp\\util.cpp"
0x180024a9d  call    cs:__imp_PuDbgPrintError
0x180024aa3  nop
0x180024aa4  jmp     loc_180001C4F
0x180024aa9  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024ab0  jz      short loc_180024B1F
0x180024ab2  test    eax, eax
0x180024ab4  jle     short loc_180024ABE
0x180024ab6  movzx   eax, ax
0x180024ab9  or      eax, 80070000h
0x180024abe  lea     rcx, aGettingTheSidL; "Getting the SID length failed, can't cr"...
0x180024ac5  mov     r8d, 0ABCh
0x180024acb  jmp     short loc_180024AF7
0x180024acd  call    cs:__imp_GetLastError
0x180024ad3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180024ada  mov     ebx, eax
0x180024adc  jz      short loc_180024B1F
0x180024ade  test    eax, eax
0x180024ae0  jle     short loc_180024AEA
0x180024ae2  movzx   eax, ax
0x180024ae5  or      eax, 80070000h
0x180024aea  lea     rcx, aCreatingSidFai; "Creating SID failed ( SidType = %d )\n"
0x180024af1  mov     r8d, 0AD9h
0x180024af7  mov     [rsp+68h+var_38], esi
0x180024afb  lea     r9, aAllocateandcre; "AllocateAndCreateWellKnownSid"
0x180024b02  mov     [rsp+68h+var_40], rcx
0x180024b07  lea     rdx, aInetsrvIisSvcs_3; "inetsrv\\iis\\svcs\\cmp\\asp\\util.cpp"
0x180024b0e  mov     rcx, cs:g_pDebug
0x180024b15  mov     [rsp+68h+var_48], eax
0x180024b19  call    cs:__imp_PuDbgPrintError
0x180024b1f  test    ebx, ebx
0x180024b21  jz      loc_180001C4F
0x180024b27  test    rdi, rdi
0x180024b2a  jz      loc_180001C4F
0x180024b30  mov     rcx, rdi; hMem
0x180024b33  call    cs:__imp_GlobalFree
0x180024b39  nop
0x180024b3a  jmp     loc_180001C52
```
