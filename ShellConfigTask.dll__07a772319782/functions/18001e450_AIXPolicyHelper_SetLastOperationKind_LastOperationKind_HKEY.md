# AIXPolicyHelper::SetLastOperationKind(LastOperationKind,HKEY__ *)

- ea: `0x18001e450`
- end: `0x18001e511`
- name: `?SetLastOperationKind@AIXPolicyHelper@@YAXW4LastOperationKind@@PEAUHKEY__@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dac8`
- `0x18001fd50`
- `0x18002d050`

## callees

- `0x18001e450`
- `0x18002062c`
- `0x1800233ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e505`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e505`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e4cc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001e4cc`

## string_xrefs

- `0x18001e477`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsAI\LastConfiguration`
- `0x18001e48c`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`
- `0x18001e4e7`: `shellcommon\internal\shell\inc\AIXPolicyHelper.h`

## pseudocode

```c
void __fastcall AIXPolicyHelper::SetLastOperationKind(int a1, __int64 a2)
{
  int v3; // eax
  int v4; // eax
  bool v5; // sf
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  Data = a2;
  hKey = 0;
  v3 = wil::reg::open_unique_key_nothrow(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsAI\\LastConfiguration",
         &hKey);
  if ( v3 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x34E,
      (int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
      (const char *)(unsigned int)v3);
  if ( hKey )
  {
    LODWORD(Data) = a1;
    v4 = RegSetKeyValueW(hKey, 0, L"LastOperationKind", 4u, &Data, 4u);
    v5 = v4 < 0;
    if ( v4 > 0 )
    {
      v4 = (unsigned __int16)v4 | 0x80070000;
      v5 = v4 < 0;
    }
    if ( v5 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x351,
        (int)"shellcommon\\internal\\shell\\inc\\AIXPolicyHelper.h",
        (const char *)(unsigned int)v4);
    if ( hKey )
      RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x18001e450  mov     [rsp+Data], rdx
0x18001e455  push    rbx
0x18001e456  sub     rsp, 30h
0x18001e45a  mov     ebx, ecx
0x18001e45c  mov     [rsp+38h+hKey], 0
0x18001e465  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e46c  lea     r8, [rsp+38h+hKey]; phkResult
0x18001e471  mov     r9d, 1
0x18001e477  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001e47e  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18001e483  test    eax, eax
0x18001e485  jns     short loc_18001E4A0
0x18001e487  mov     rcx, [rsp+38h]; this
0x18001e48c  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x18001e493  mov     r9d, eax; char *
0x18001e496  mov     edx, 34Eh; void *
0x18001e49b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e4a0  mov     rcx, [rsp+38h+hKey]; hKey
0x18001e4a5  test    rcx, rcx
0x18001e4a8  jz      short loc_18001E50B
0x18001e4aa  mov     r9d, 4; dwType
0x18001e4b0  mov     dword ptr [rsp+38h+Data], ebx
0x18001e4b4  lea     rax, [rsp+38h+Data]
0x18001e4b9  mov     [rsp+38h+cbData], r9d; cbData
0x18001e4be  lea     r8, aLastoperationk; "LastOperationKind"
0x18001e4c5  mov     [rsp+38h+lpData], rax; int
0x18001e4ca  xor     edx, edx; lpSubKey
0x18001e4cc  call    cs:__imp_RegSetKeyValueW
0x18001e4d2  test    eax, eax
0x18001e4d4  jle     short loc_18001E4E0
0x18001e4d6  movzx   eax, ax
0x18001e4d9  or      eax, 80070000h
0x18001e4de  test    eax, eax
0x18001e4e0  jns     short loc_18001E4FB
0x18001e4e2  mov     rcx, [rsp+38h]; this
0x18001e4e7  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\AIXP"...
0x18001e4ee  mov     r9d, eax; char *
0x18001e4f1  mov     edx, 351h; void *
0x18001e4f6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e4fb  mov     rcx, [rsp+38h+hKey]; hKey
0x18001e500  test    rcx, rcx
0x18001e503  jz      short loc_18001E50B
0x18001e505  call    cs:__imp_RegCloseKey
0x18001e50b  add     rsp, 30h
0x18001e50f  pop     rbx
0x18001e510  retn
```
