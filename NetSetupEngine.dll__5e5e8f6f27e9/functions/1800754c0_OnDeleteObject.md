# OnDeleteObject

- ea: `0x1800754c0`
- end: `0x180075599`
- name: `OnDeleteObject`
- size: `217`
- prototype: `LSTATUS __fastcall(__int64, __int64, __int64, const struct NetSetup2::ActiveObject *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callees

- `0x180017320`
- `0x180027b38`
- `0x18005a538`
- `0x1800754c0`
- `0x180075b08`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180075532`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180075532`

## pseudocode

```c
LSTATUS __fastcall OnDeleteObject(__int64 a1, __int64 a2, __int64 a3, const struct NetSetup2::ActiveObject *a4)
{
  HKEY CurrentControlSetRegistryHandle; // rbx
  LSTATUS result; // eax
  __int64 v7; // [rsp+30h] [rbp-258h] BYREF
  __int64 v8; // [rsp+38h] [rbp-250h] BYREF
  int v9; // [rsp+40h] [rbp-248h]
  __int128 v10; // [rsp+44h] [rbp-244h]
  __int64 v11; // [rsp+58h] [rbp-230h]
  WCHAR SubKey[264]; // [rsp+60h] [rbp-228h] BYREF

  v11 = -2;
  GetPathToDriverNetworkKey(a4, SubKey);
  v7 = a2;
  v8 = 0;
  v9 = 9;
  v10 = 0;
  CurrentControlSetRegistryHandle = NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle((NetSetup2::TransactionObject *)&v7);
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v8);
  result = RegDeleteTreeW(CurrentControlSetRegistryHandle, SubKey);
  if ( result && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    return WPP_SF_SDd(
             *((_QWORD *)WPP_GLOBAL_Control + 2),
             (_DWORD)WPP_GLOBAL_Control,
             (unsigned int)&WPP_GLOBAL_Control,
             (unsigned int)SubKey,
             result,
             result);
  return result;
}

```

## disassembly

```asm
0x1800754c0  push    rbx
0x1800754c2  sub     rsp, 280h
0x1800754c9  mov     [rsp+288h+var_230], 0FFFFFFFFFFFFFFFEh
0x1800754d2  mov     rax, cs:__security_cookie
0x1800754d9  xor     rax, rsp
0x1800754dc  mov     [rsp+288h+var_18], rax
0x1800754e4  mov     rbx, rdx
0x1800754e7  lea     rdx, [rsp+288h+SubKey]; wchar_t *
0x1800754ec  mov     rcx, r9; struct NetSetup2::ActiveObject *
0x1800754ef  call    ?GetPathToDriverNetworkKey@@YAXAEBVActiveObject@NetSetup2@@PEA_W@Z; GetPathToDriverNetworkKey(NetSetup2::ActiveObject const &,wchar_t *)
0x1800754f4  xorps   xmm0, xmm0
0x1800754f7  mov     [rsp+288h+var_258], rbx
0x1800754fc  mov     [rsp+288h+var_250], 0
0x180075505  mov     [rsp+288h+var_248], 9
0x18007550d  movdqu  [rsp+288h+var_244], xmm0
0x180075513  lea     rcx, [rsp+288h+var_258]; this
0x180075518  call    ?get_CurrentControlSetRegistryHandle@TransactionObject@NetSetup2@@QEBAPEAUHKEY__@@XZ; NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle(void)
0x18007551d  mov     rbx, rax
0x180075520  lea     rcx, [rsp+288h+var_250]
0x180075525  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18007552a  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x18007552f  mov     rcx, rbx; hKey
0x180075532  call    cs:__imp_RegDeleteTreeW
0x180075538  test    eax, eax
0x18007553a  jz      short loc_180075580
0x18007553c  jg      short loc_180075542
0x18007553e  mov     ecx, eax
0x180075540  jmp     short loc_18007554B
0x180075542  movzx   ecx, ax
0x180075545  or      ecx, 80070000h
0x18007554b  lea     r8, WPP_GLOBAL_Control
0x180075552  mov     rdx, cs:WPP_GLOBAL_Control
0x180075559  cmp     rdx, r8
0x18007555c  jz      short loc_180075580
0x18007555e  cmp     byte ptr [rdx+19h], 3
0x180075562  jb      short loc_180075580
0x180075564  or      ecx, 80000000h
0x18007556a  mov     [rsp+288h+var_260], ecx
0x18007556e  mov     [rsp+288h+var_268], eax
0x180075572  lea     r9, [rsp+288h+SubKey]
0x180075577  mov     rcx, [rdx+10h]
0x18007557b  call    WPP_SF_SDd
0x180075580  mov     rcx, [rsp+288h+var_18]
0x180075588  xor     rcx, rsp; StackCookie
0x18007558b  call    __security_check_cookie
0x180075590  add     rsp, 280h
0x180075597  pop     rbx
0x180075598  retn
```
