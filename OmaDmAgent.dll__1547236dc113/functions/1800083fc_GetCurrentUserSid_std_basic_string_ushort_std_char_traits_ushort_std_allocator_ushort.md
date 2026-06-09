# GetCurrentUserSid(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800083fc`
- end: `0x18000847c`
- name: `?GetCurrentUserSid@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180015298`

## callees

- `0x1800065f8`
- `0x1800083fc`
- `0x180008484`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x180008434`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180008434`
- `KERNEL32!GetLastError` at `0x180008453`
- `KERNEL32!GetLastError` at `0x180008453`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(__int64 a1)
{
  signed int CurrentUserSid; // ebx
  signed int LastError; // eax
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp+18h] BYREF

  Sid = 0;
  StringSid = 0;
  CurrentUserSid = GetCurrentUserSid(&Sid);
  if ( CurrentUserSid >= 0 )
  {
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      std::wstring::assign(a1, StringSid);
    }
    else
    {
      LastError = GetLastError();
      CurrentUserSid = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return (unsigned int)CurrentUserSid;
}

```

## disassembly

```asm
0x1800083fc  mov     rax, rsp
0x1800083ff  mov     [rax+8], rbx
0x180008403  push    rdi
0x180008404  sub     rsp, 20h
0x180008408  mov     rdi, rcx
0x18000840b  mov     qword ptr [rax+10h], 0
0x180008413  lea     rcx, [rax+10h]; void **
0x180008417  mov     qword ptr [rax+18h], 0
0x18000841f  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x180008424  mov     ebx, eax
0x180008426  test    eax, eax
0x180008428  js      short loc_18000846E
0x18000842a  mov     rcx, [rsp+28h+Sid]; Sid
0x18000842f  lea     rdx, [rsp+28h+StringSid]; StringSid
0x180008434  call    cs:__imp_ConvertSidToStringSidW
0x18000843b  nop     dword ptr [rax+rax+00h]
0x180008440  test    eax, eax
0x180008442  jz      short loc_180008453
0x180008444  mov     rdx, [rsp+28h+StringSid]
0x180008449  mov     rcx, rdi
0x18000844c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180008451  jmp     short loc_18000846E
0x180008453  call    cs:__imp_GetLastError
0x18000845a  nop     dword ptr [rax+rax+00h]
0x18000845f  mov     ebx, eax
0x180008461  test    eax, eax
0x180008463  jle     short loc_18000846E
0x180008465  movzx   ebx, ax
0x180008468  or      ebx, 80070000h
0x18000846e  mov     eax, ebx
0x180008470  mov     rbx, [rsp+28h+arg_0]
0x180008475  add     rsp, 20h
0x180008479  pop     rdi
0x18000847a  retn
```
