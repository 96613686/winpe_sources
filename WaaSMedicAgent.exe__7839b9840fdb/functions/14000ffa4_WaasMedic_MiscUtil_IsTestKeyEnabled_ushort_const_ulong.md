# WaasMedic::MiscUtil::IsTestKeyEnabled(ushort const *,ulong)

- ea: `0x14000ffa4`
- end: `0x140010024`
- name: `?IsTestKeyEnabled@MiscUtil@WaasMedic@@SA_NPEBGK@Z`
- size: `128`
- prototype: `char __fastcall(WaasMedic *, unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x14000a8f0`

## callees

- `0x140002a30`
- `0x14000b470`
- `0x14000ffa4`
- `0x1400102f0`
- `0x1400103f0`
- `0x14001063c`

## string_xrefs

- `0x14000ffd2`: `Failed to retrieve test key path! hr = 0x%08x`

## pseudocode

```c
char __fastcall WaasMedic::MiscUtil::IsTestKeyEnabled(
        WaasMedic *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int *v8; // [rsp+20h] [rbp-238h]
  unsigned int v9[132]; // [rsp+30h] [rbp-228h] BYREF

  v4 = 0;
  if ( WaasMedic::RegGetPersistedSubkeyPath(a1, a2, (unsigned int)v9, a4, v8) >= 0 )
  {
    if ( (int)WaasMedic::RegKeyExists(v5, v9) >= 0 )
      return (int)WaasMedic::RegValueExists(v6, v9) >= 0;
  }
  else
  {
    LogLevelW(2u, L"Failed to retrieve test key path! hr = 0x%08x");
  }
  return v4;
}

```

## disassembly

```asm
0x14000ffa4  push    rbx
0x14000ffa6  sub     rsp, 250h
0x14000ffad  mov     rax, cs:__security_cookie
0x14000ffb4  xor     rax, rsp
0x14000ffb7  mov     [rsp+258h+var_18], rax
0x14000ffbf  xor     bl, bl
0x14000ffc1  lea     r8, [rsp+258h+var_228]; unsigned int
0x14000ffc6  call    ?RegGetPersistedSubkeyPath@WaasMedic@@YAJPEAGK0PEAK@Z; WaasMedic::RegGetPersistedSubkeyPath(ushort *,ulong,ushort *,ulong *)
0x14000ffcb  test    eax, eax
0x14000ffcd  jns     short loc_14000FFE4
0x14000ffcf  xor     r8d, r8d
0x14000ffd2  lea     rdx, aFailedToRetrie; "Failed to retrieve test key path! hr = "...
0x14000ffd9  lea     ecx, [r8+2]; unsigned __int8
0x14000ffdd  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x14000ffe2  jmp     short loc_140010009
0x14000ffe4  lea     rdx, [rsp+258h+var_228]
0x14000ffe9  call    ?RegKeyExists@WaasMedic@@YAJPEAUHKEY__@@PEBGW4RegistryHiveType@1@@Z; WaasMedic::RegKeyExists(HKEY__ *,ushort const *,WaasMedic::RegistryHiveType)
0x14000ffee  test    eax, eax
0x14000fff0  js      short loc_140010009
0x14000fff2  lea     rdx, [rsp+258h+var_228]
0x14000fff7  call    ?RegValueExists@WaasMedic@@YAJPEAUHKEY__@@PEBG1KW4RegistryHiveType@1@@Z; WaasMedic::RegValueExists(HKEY__ *,ushort const *,ushort const *,ulong,WaasMedic::RegistryHiveType)
0x14000fffc  test    eax, eax
0x14000fffe  movzx   ebx, bl
0x140010001  mov     ecx, 1
0x140010006  cmovns  ebx, ecx
0x140010009  mov     al, bl
0x14001000b  mov     rcx, [rsp+258h+var_18]
0x140010013  xor     rcx, rsp; StackCookie
0x140010016  call    __security_check_cookie
0x14001001b  add     rsp, 250h
0x140010022  pop     rbx
0x140010023  retn
```
