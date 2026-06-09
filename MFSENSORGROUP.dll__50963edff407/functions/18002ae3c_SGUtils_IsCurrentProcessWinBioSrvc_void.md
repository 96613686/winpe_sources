# SGUtils_IsCurrentProcessWinBioSrvc(void)

- ea: `0x18002ae3c`
- end: `0x18002af7f`
- name: `?SGUtils_IsCurrentProcessWinBioSrvc@@YA_NXZ`
- size: `323`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012284`
- `0x18002eb64`
- `0x180057220`

## callees

- `0x18000c348`
- `0x18002ae3c`
- `0x18002af88`
- `0x180051a1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002af46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aed7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aef8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aed7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aef8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002ae62`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002ae62`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002ae7c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18002ae7c`

## pseudocode

```c
bool SGUtils_IsCurrentProcessWinBioSrvc(void)
{
  const char *v0; // r9
  bool v1; // bl
  signed int v3; // eax
  signed int LastError; // eax
  WINBOOL IsMember; // [rsp+40h] [rbp+8h] BYREF
  PSID Sid; // [rsp+48h] [rbp+10h] BYREF

  IsMember = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(L"S-1-5-80-1577343513-2244782562-3500840712-2807016722-4230555396", &Sid) )
  {
    if ( CheckTokenMembership(0, Sid, &IsMember) )
    {
      if ( byte_18008D62D )
      {
        v0 = "is";
        if ( !IsMember )
          v0 = "is_not";
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 27), 155, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, v0);
      }
      v1 = IsMember != 0;
      if ( Sid )
        LocalFree(Sid);
      return v1;
    }
    if ( byte_18008D62D )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        154,
        &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
        (unsigned int)LastError);
    }
  }
  else if ( byte_18008D62D )
  {
    v3 = GetLastError();
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      153,
      (unsigned int)&WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
      v3,
      (__int64)L"S-1-5-80-1577343513-2244782562-3500840712-2807016722-4230555396");
  }
  if ( Sid )
    LocalFree(Sid);
  return 0;
}

```

## disassembly

```asm
0x18002ae3c  push    rbx
0x18002ae3e  sub     rsp, 30h
0x18002ae42  lea     rbx, StringSid; "S-1-5-80-1577343513-2244782562-35008407"...
0x18002ae49  mov     [rsp+38h+IsMember], 0
0x18002ae51  mov     rcx, rbx; StringSid
0x18002ae54  mov     [rsp+38h+Sid], 0
0x18002ae5d  lea     rdx, [rsp+38h+Sid]; Sid
0x18002ae62  call    cs:__imp_ConvertStringSidToSidW
0x18002ae68  test    eax, eax
0x18002ae6a  jz      loc_18002AF02
0x18002ae70  mov     rdx, [rsp+38h+Sid]; SidToCheck
0x18002ae75  lea     r8, [rsp+38h+IsMember]; IsMember
0x18002ae7a  xor     ecx, ecx; TokenHandle
0x18002ae7c  call    cs:__imp_CheckTokenMembership
0x18002ae82  test    eax, eax
0x18002ae84  jz      short loc_18002AEE5
0x18002ae86  cmp     cs:byte_18008D62D, 1
0x18002ae8d  jb      short loc_18002AEC5
0x18002ae8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae96  lea     rax, aIsNot; "is_not"
0x18002ae9d  cmp     [rsp+38h+IsMember], 0
0x18002aea2  lea     r9, aIs; "is"
0x18002aea9  mov     edx, 9Bh
0x18002aeae  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18002aeb5  cmovz   r9, rax
0x18002aeb9  mov     rcx, [rcx+0D8h]
0x18002aec0  call    WPP_SF_s
0x18002aec5  cmp     [rsp+38h+IsMember], 0
0x18002aeca  mov     rcx, [rsp+38h+Sid]; hMem
0x18002aecf  setnz   bl
0x18002aed2  test    rcx, rcx
0x18002aed5  jz      short loc_18002AEDD
0x18002aed7  call    cs:__imp_LocalFree
0x18002aedd  mov     al, bl
0x18002aedf  add     rsp, 30h
0x18002aee3  pop     rbx
0x18002aee4  retn
0x18002aee5  cmp     cs:byte_18008D62D, 1
0x18002aeec  jnb     short loc_18002AF46
0x18002aeee  mov     rcx, [rsp+38h+Sid]; hMem
0x18002aef3  test    rcx, rcx
0x18002aef6  jz      short loc_18002AEFE
0x18002aef8  call    cs:__imp_LocalFree
0x18002aefe  xor     al, al
0x18002af00  jmp     short loc_18002AEDF
0x18002af02  cmp     cs:byte_18008D62D, 1
0x18002af09  jb      short loc_18002AEEE
0x18002af0b  call    cs:__imp_GetLastError
0x18002af11  test    eax, eax
0x18002af13  jle     short loc_18002AF1D
0x18002af15  movzx   eax, ax
0x18002af18  or      eax, 80070000h
0x18002af1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af24  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18002af2b  mov     edx, 99h
0x18002af30  mov     [rsp+38h+var_18], rbx
0x18002af35  mov     r9d, eax
0x18002af38  mov     rcx, [rcx+0D8h]
0x18002af3f  call    WPP_SF_dS
0x18002af44  jmp     short loc_18002AEEE
0x18002af46  call    cs:__imp_GetLastError
0x18002af4c  test    eax, eax
0x18002af4e  jle     short loc_18002AF58
0x18002af50  movzx   eax, ax
0x18002af53  or      eax, 80070000h
0x18002af58  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af5f  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18002af66  mov     edx, 9Ah
0x18002af6b  mov     r9d, eax
0x18002af6e  mov     rcx, [rcx+0D8h]
0x18002af75  call    WPP_SF_d
0x18002af7a  jmp     loc_18002AEEE
```
