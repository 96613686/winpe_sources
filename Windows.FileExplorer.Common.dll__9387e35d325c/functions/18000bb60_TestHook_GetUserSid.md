# TestHook_GetUserSid

- ea: `0x18000bb60`
- end: `0x18000bc1e`
- name: `TestHook_GetUserSid`
- size: `190`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008130`
- `0x18000d188`
- `0x180034524`
- `0x180060fcc`
- `0x1800661e0`
- `0x18006898c`
- `0x180068e7c`
- `0x180069dac`

## callees

- `0x18000bb60`
- `0x18000bc30`
- `0x18000bd80`
- `0x18000c668`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bbcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bbd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bbcf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bbd8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000bbb1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000bbb1`

## pseudocode

```c
__int64 __fastcall TestHook_GetUserSid(void *a1, _QWORD *a2, DWORD a3)
{
  int Error; // ebx
  HLOCAL v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 *v9; // r8
  LPWSTR StringSid; // [rsp+40h] [rbp+18h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp+20h] BYREF

  if ( qword_1800ADF10 )
  {
    v9 = &g_testUserSid;
    if ( (unsigned __int64)qword_1800ADF18 > 7 )
      v9 = (__int64 *)g_testUserSid;
    return _AllocString<CTCoAllocPolicy>(a1, a2, v9, a2);
  }
  else
  {
    *a2 = 0;
    hMem = 0;
    Error = SHQueryToken<_TOKEN_USER>(a1, (__int64)a2, a3, &hMem);
    if ( Error >= 0 )
    {
      v5 = hMem;
      StringSid = 0;
      if ( ConvertSidToStringSidW(*(PSID *)hMem, &StringSid) || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        Error = _AllocString<CTCoAllocPolicy>(v7, v6, StringSid, a2);
        LocalFree(StringSid);
      }
      LocalFree(v5);
    }
    return (unsigned int)Error;
  }
}

```

## disassembly

```asm
0x18000bb60  mov     rax, rsp
0x18000bb63  mov     [rax+8], rbx
0x18000bb67  mov     [rax+10h], rsi
0x18000bb6b  push    rdi
0x18000bb6c  sub     rsp, 20h
0x18000bb70  cmp     cs:qword_1800ADF10, 0
0x18000bb78  mov     rdi, rdx
0x18000bb7b  jnz     short loc_18000BBF0
0x18000bb7d  lea     r9, [rax+20h]
0x18000bb81  mov     qword ptr [rdx], 0
0x18000bb88  mov     qword ptr [rax+20h], 0
0x18000bb90  call    ??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z; SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)
0x18000bb95  mov     ebx, eax
0x18000bb97  test    eax, eax
0x18000bb99  js      short loc_18000BBDE
0x18000bb9b  mov     rsi, [rsp+28h+hMem]
0x18000bba0  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18000bba5  mov     [rsp+28h+StringSid], 0
0x18000bbae  mov     rcx, [rsi]; Sid
0x18000bbb1  call    cs:__imp_ConvertSidToStringSidW
0x18000bbb7  test    eax, eax
0x18000bbb9  jz      short loc_18000BC11
0x18000bbbb  mov     r8, [rsp+28h+StringSid]
0x18000bbc0  mov     r9, rdi
0x18000bbc3  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000bbc8  mov     rcx, [rsp+28h+StringSid]; hMem
0x18000bbcd  mov     ebx, eax
0x18000bbcf  call    cs:__imp_LocalFree
0x18000bbd5  mov     rcx, rsi; hMem
0x18000bbd8  call    cs:__imp_LocalFree
0x18000bbde  mov     eax, ebx
0x18000bbe0  mov     rbx, [rsp+28h+arg_0]
0x18000bbe5  mov     rsi, [rsp+28h+arg_8]
0x18000bbea  add     rsp, 20h
0x18000bbee  pop     rdi
0x18000bbef  retn
0x18000bbf0  cmp     cs:qword_1800ADF18, 7
0x18000bbf8  lea     r8, ?g_testUserSid@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring g_testUserSid
0x18000bbff  mov     r9, rdi
0x18000bc02  cmova   r8, cs:?g_testUserSid@@3V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring g_testUserSid
0x18000bc0a  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000bc0f  jmp     short loc_18000BBE0
0x18000bc11  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000bc16  mov     ebx, eax
0x18000bc18  test    eax, eax
0x18000bc1a  js      short loc_18000BBD5
0x18000bc1c  jmp     short loc_18000BBBB
```
