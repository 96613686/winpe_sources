# CSmsRpcUtils::DoesAppMeetCTA(ushort const *)

- ea: `0x180026a40`
- end: `0x180026bca`
- name: `?DoesAppMeetCTA@CSmsRpcUtils@@SAHPEBG@Z`
- size: `394`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800270b0`
- `0x180027468`

## callees

- `0x180003a60`
- `0x180004998`
- `0x180026a40`
- `0x180051420`
- `0x180051628`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026a89`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026b07`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026a89`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180026b07`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026af1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180026af1`

## string_xrefs

- `0x180026ad6`: `Software\Microsoft\Windows\CurrentVersion\DeviceAccess`
- `0x180026a93`: `Mobile Plans App comply with CTA`
- `0x180026b5b`: `RegGetValue:%S registry not found, not CTA device`

## pseudocode

```c
__int64 __fastcall CSmsRpcUtils::DoesAppMeetCTA(const unsigned __int16 *a1)
{
  unsigned int v3; // ebx
  int ValueW; // eax
  DWORD pcbData[4]; // [rsp+40h] [rbp-A8h] BYREF
  wchar_t pvData[64]; // [rsp+50h] [rbp-98h] BYREF

  memset_0(pvData, 0, sizeof(pvData));
  pcbData[0] = 128;
  if ( !(unsigned int)_o__wcsicmp(a1, L"Microsoft.OneConnect_8wekyb3d8bbwe") )
  {
    LogSmsRouterInfo("CSmsRpcUtils::DoesAppMeetCTA", 0x261u, "Mobile Plans App comply with CTA");
    return 1;
  }
  v3 = 1;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\DeviceAccess",
             L"ActivePolicyCode",
             2u,
             0,
             pvData,
             pcbData);
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      if ( ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0x80070000;
      LogSmsRouterError(
        "CSmsRpcUtils::DoesAppMeetCTA",
        0x279u,
        ValueW,
        "RegGetValue:%S failed, block App",
        L"ActivePolicyCode");
      return 0;
    }
    LogSmsRouterInfo(
      "CSmsRpcUtils::DoesAppMeetCTA",
      0x275u,
      "RegGetValue:%S registry not found, not CTA device",
      L"ActivePolicyCode");
  }
  else
  {
    if ( !(unsigned int)_o__wcsicmp(pvData, L"zh") )
    {
      LogSmsRouterInfo("CSmsRpcUtils::DoesAppMeetCTA", 0x26Au, "Block App [%S] on CTA device", a1);
      return 0;
    }
    LogSmsRouterInfo(
      "CSmsRpcUtils::DoesAppMeetCTA",
      0x270u,
      "RegGetValue: %S=%S, AppPackageFamilyName=%S",
      L"ActivePolicyCode",
      pvData,
      a1);
  }
  return v3;
}

```

## disassembly

```asm
0x180026a40  mov     [rsp+arg_8], rbx
0x180026a45  mov     [rsp+arg_10], rsi
0x180026a4a  push    rdi
0x180026a4b  sub     rsp, 0E0h
0x180026a52  mov     rax, cs:__security_cookie
0x180026a59  xor     rax, rsp
0x180026a5c  mov     [rsp+0E8h+var_18], rax
0x180026a64  mov     rdi, rcx
0x180026a67  mov     ebx, 80h
0x180026a6c  mov     r8d, ebx; Size
0x180026a6f  lea     rcx, [rsp+0E8h+var_98]; void *
0x180026a74  xor     edx, edx; Val
0x180026a76  call    memset_0
0x180026a7b  lea     rdx, aMicrosoftOneco; "Microsoft.OneConnect_8wekyb3d8bbwe"
0x180026a82  mov     [rsp+0E8h+var_A8], ebx
0x180026a86  mov     rcx, rdi
0x180026a89  call    cs:__imp__o__wcsicmp
0x180026a8f  test    eax, eax
0x180026a91  jnz     short loc_180026AB3
0x180026a93  lea     r8, aMobilePlansApp; "Mobile Plans App comply with CTA"
0x180026a9a  mov     edx, 261h; unsigned int
0x180026a9f  lea     rcx, aCsmsrpcutilsDo; "CSmsRpcUtils::DoesAppMeetCTA"
0x180026aa6  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180026aab  lea     eax, [rbx-7Fh]
0x180026aae  jmp     loc_180026BA5
0x180026ab3  lea     rax, [rsp+0E8h+var_A8]
0x180026ab8  mov     ebx, 1
0x180026abd  mov     [rsp+0E8h+pcbData], rax; pcbData
0x180026ac2  lea     rsi, aActivepolicyco; "ActivePolicyCode"
0x180026ac9  lea     rax, [rsp+0E8h+var_98]
0x180026ace  mov     r8, rsi; lpValue
0x180026ad1  mov     [rsp+0E8h+pvData], rax; pvData
0x180026ad6  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180026add  lea     r9d, [rbx+1]; dwFlags
0x180026ae1  mov     [rsp+0E8h+pdwType], 0; pdwType
0x180026aea  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180026af1  call    cs:__imp_RegGetValueW
0x180026af7  test    eax, eax
0x180026af9  jnz     short loc_180026B53
0x180026afb  lea     rdx, aZh; "zh"
0x180026b02  lea     rcx, [rsp+0E8h+var_98]
0x180026b07  call    cs:__imp__o__wcsicmp
0x180026b0d  lea     rcx, aCsmsrpcutilsDo; "CSmsRpcUtils::DoesAppMeetCTA"
0x180026b14  test    eax, eax
0x180026b16  jnz     short loc_180026B2E
0x180026b18  mov     r9, rdi
0x180026b1b  lea     r8, aBlockAppSOnCta; "Block App [%S] on CTA device"
0x180026b22  mov     edx, 26Ah; unsigned int
0x180026b27  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180026b2c  jmp     short loc_180026BA1
0x180026b2e  lea     rax, [rsp+0E8h+var_98]
0x180026b33  mov     [rsp+0E8h+pvData], rdi
0x180026b38  mov     r9, rsi
0x180026b3b  mov     [rsp+0E8h+pdwType], rax
0x180026b40  lea     r8, aReggetvalueSSA; "RegGetValue: %S=%S, AppPackageFamilyNam"...
0x180026b47  mov     edx, 270h; unsigned int
0x180026b4c  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180026b51  jmp     short loc_180026BA3
0x180026b53  cmp     eax, 2
0x180026b56  jnz     short loc_180026B75
0x180026b58  mov     r9, rsi
0x180026b5b  lea     r8, aReggetvalueSRe; "RegGetValue:%S registry not found, not "...
0x180026b62  mov     edx, 275h; unsigned int
0x180026b67  lea     rcx, aCsmsrpcutilsDo; "CSmsRpcUtils::DoesAppMeetCTA"
0x180026b6e  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180026b73  jmp     short loc_180026BA3
0x180026b75  test    eax, eax
0x180026b77  jle     short loc_180026B81
0x180026b79  movzx   eax, ax
0x180026b7c  or      eax, 80070000h
0x180026b81  lea     r9, aReggetvalueSFa; "RegGetValue:%S failed, block App"
0x180026b88  mov     [rsp+0E8h+pdwType], rsi
0x180026b8d  mov     r8d, eax; int
0x180026b90  lea     rcx, aCsmsrpcutilsDo; "CSmsRpcUtils::DoesAppMeetCTA"
0x180026b97  mov     edx, 279h; unsigned int
0x180026b9c  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x180026ba1  xor     ebx, ebx
0x180026ba3  mov     eax, ebx
0x180026ba5  mov     rcx, [rsp+0E8h+var_18]
0x180026bad  xor     rcx, rsp; StackCookie
0x180026bb0  call    __security_check_cookie
0x180026bb5  lea     r11, [rsp+0E8h+var_8]
0x180026bbd  mov     rbx, [r11+18h]
0x180026bc1  mov     rsi, [r11+20h]
0x180026bc5  mov     rsp, r11
0x180026bc8  pop     rdi
0x180026bc9  retn
```
