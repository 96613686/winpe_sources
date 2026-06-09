# WaasMedic::AllocAdministratorsSid

- ea: `0x18002805c`
- end: `0x180028149`
- name: `WaasMedic::AllocAdministratorsSid`
- size: `237`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800288a0`

## callees

- `0x18002805c`
- `0x180028150`
- `0x18002a300`
- `0x18002e81c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800280fe`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028131`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180028131`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800280bd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800280bd`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800280f4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800280f4`

## string_xrefs

- `0x1800280d4`: `Failed to allocate memory for SID!`
- `0x180028073`: `Invalid pointer input for AllocAdministratorsSid!`
- `0x180028116`: `Failed to Copy SID! hr = 0x%08x`
- `0x1800280af`: `Failed to create SID! hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall WaasMedic::AllocAdministratorsSid(_QWORD *a1, void **a2, unsigned __int8 a3, unsigned int a4)
{
  int Sid; // eax
  unsigned int v7; // ebx
  WaasMedic *LengthSid; // rsi
  unsigned __int64 v9; // rdx
  bool v10; // r8
  void *v11; // rax
  signed int LastError; // eax
  unsigned int v13; // [rsp+20h] [rbp-8h]
  PSID pSid; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    *a1 = 0;
    pSid = 0;
    Sid = WaasMedic::CreateSid((WaasMedic *)&pSid, a2, a3, a4, v13);
    v7 = Sid;
    if ( Sid >= 0 )
    {
      LengthSid = (WaasMedic *)GetLengthSid(pSid);
      v11 = WaasMedic::SafeAlloc(LengthSid, v9, v10);
      *a1 = v11;
      if ( v11 )
      {
        if ( !CopySid((DWORD)LengthSid, v11, pSid) )
        {
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError > 0 )
            v7 = (unsigned __int16)LastError | 0x80070000;
          LogLevelW(2u, L"Failed to Copy SID! hr = 0x%08x", v7);
        }
      }
      else
      {
        v7 = -2147024882;
        LogLevelW(2u, L"Failed to allocate memory for SID!");
      }
    }
    else
    {
      LogLevelW(2u, L"Failed to create SID! hr = 0x%08x", (unsigned int)Sid);
    }
    if ( pSid )
      FreeSid(pSid);
    return v7;
  }
  else
  {
    LogLevelW(2u, L"Invalid pointer input for AllocAdministratorsSid!");
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18002805c  mov     [rsp+arg_8], rbx
0x180028061  mov     [rsp+arg_10], rsi
0x180028066  push    rdi; unsigned int
0x180028067  sub     rsp, 20h
0x18002806b  mov     rdi, rcx
0x18002806e  test    rcx, rcx
0x180028071  jnz     short loc_18002808C
0x180028073  lea     rdx, aInvalidPointer; "Invalid pointer input for AllocAdminist"...
0x18002807a  lea     ecx, [rdi+2]; unsigned __int8
0x18002807d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180028082  mov     eax, 80004003h
0x180028087  jmp     loc_180028139
0x18002808c  mov     qword ptr [rcx], 0
0x180028093  lea     rcx, [rsp+28h+pSid]; this
0x180028098  mov     [rsp+28h+pSid], 0
0x1800280a1  call    ?CreateSid@WaasMedic@@YAJPEAPEAXEKK@Z; WaasMedic::CreateSid(void * *,uchar,ulong,ulong)
0x1800280a6  mov     ebx, eax
0x1800280a8  test    eax, eax
0x1800280aa  jns     short loc_1800280B8
0x1800280ac  mov     r8d, eax
0x1800280af  lea     rdx, aFailedToCreate_9; "Failed to create SID! hr = 0x%08x"
0x1800280b6  jmp     short loc_18002811D
0x1800280b8  mov     rcx, [rsp+28h+pSid]; pSid
0x1800280bd  call    cs:__imp_GetLengthSid
0x1800280c3  mov     ecx, eax; this
0x1800280c5  mov     esi, eax
0x1800280c7  call    ?SafeAlloc@WaasMedic@@YAPEAX_K_N@Z; WaasMedic::SafeAlloc(unsigned __int64,bool)
0x1800280cc  mov     [rdi], rax
0x1800280cf  test    rax, rax
0x1800280d2  jnz     short loc_1800280EA
0x1800280d4  lea     rdx, aFailedToAlloca_6; "Failed to allocate memory for SID!"
0x1800280db  mov     ebx, 8007000Eh
0x1800280e0  lea     ecx, [rax+2]; unsigned __int8
0x1800280e3  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800280e8  jmp     short loc_180028127
0x1800280ea  mov     r8, [rsp+28h+pSid]; pSourceSid
0x1800280ef  mov     rdx, rax; pDestinationSid
0x1800280f2  mov     ecx, esi; nDestinationSidLength
0x1800280f4  call    cs:__imp_CopySid
0x1800280fa  test    eax, eax
0x1800280fc  jnz     short loc_180028127
0x1800280fe  call    cs:__imp_GetLastError
0x180028104  mov     ebx, eax
0x180028106  test    eax, eax
0x180028108  jle     short loc_180028113
0x18002810a  movzx   ebx, ax
0x18002810d  or      ebx, 80070000h
0x180028113  mov     r8d, ebx
0x180028116  lea     rdx, aFailedToCopySi; "Failed to Copy SID! hr = 0x%08x"
0x18002811d  mov     ecx, 2; unsigned __int8
0x180028122  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180028127  mov     rcx, [rsp+28h+pSid]; pSid
0x18002812c  test    rcx, rcx
0x18002812f  jz      short loc_180028137
0x180028131  call    cs:__imp_FreeSid
0x180028137  mov     eax, ebx
0x180028139  mov     rbx, [rsp+28h+arg_8]
0x18002813e  mov     rsi, [rsp+28h+arg_10]
0x180028143  add     rsp, 20h
0x180028147  pop     rdi
0x180028148  retn
```
