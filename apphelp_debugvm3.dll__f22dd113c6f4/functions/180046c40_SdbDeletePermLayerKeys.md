# SdbDeletePermLayerKeys

- ea: `0x180046c40`
- end: `0x180046d8c`
- name: `SdbDeletePermLayerKeys`
- size: `332`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180046f10`
- `0x180047130`

## callees

- `0x18000f114`
- `0x180016910`
- `0x18003d070`
- `0x180046c40`
- `0x1800591b0`

## import_xrefs

- `ntdll!NtDeleteValueKey` at `0x180046d2c`
- `ntdll!NtDeleteValueKey` at `0x180046d2c`
- `ntdll!NtClose` at `0x180046d39`
- `ntdll!NtClose` at `0x180046d39`
- `ntdll!RtlInitUnicodeString` at `0x180046cc7`
- `ntdll!RtlInitUnicodeString` at `0x180046cc7`

## string_xrefs

- `0x180046ccd`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`
- `0x180046c9c`: `Failed to get perm layer path`
- `0x180046ca9`: `SdbDeletePermLayerKeys`
- `0x180046d0a`: `SdbDeletePermLayerKeys`
- `0x180046cfd`: `Failed to open Key for "%S" [%x]`
- `0x180046d4f`: `Failed to delete value from Key "%S" [%x]`

## pseudocode

```c
__int64 __fastcall SdbDeletePermLayerKeys(_WORD *a1, int a2)
{
  unsigned int v3; // ebx
  int Key; // eax
  NTSTATUS v5; // edi
  int v7; // [rsp+28h] [rbp-260h]
  NTSTATUS v8; // [rsp+28h] [rbp-260h]
  HANDLE KeyHandle; // [rsp+30h] [rbp-258h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-250h] BYREF
  WCHAR SourceString[264]; // [rsp+50h] [rbp-238h] BYREF

  KeyHandle = 0;
  DestinationString = 0;
  if ( a1 && *a1 )
  {
    v3 = 0;
    if ( (int)AslPathBuildSignature(SourceString, 260, a1) < 0 )
    {
      AslLogCallPrintf(1, "SdbDeletePermLayerKeys", 295, "Failed to get perm layer path");
      return v3;
    }
    RtlInitUnicodeString(&DestinationString, SourceString);
    Key = AslRegistryGetKey(
            &KeyHandle,
            L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
            0x20106u,
            a2,
            0);
    if ( Key >= 0 )
    {
      v5 = NtDeleteValueKey(KeyHandle, &DestinationString);
      NtClose(KeyHandle);
      if ( v5 < 0 && v5 != -1073741772 )
      {
        v8 = v5;
        AslLogCallPrintf(
          1,
          "SdbDeletePermLayerKeys",
          326,
          "Failed to delete value from Key \"%S\" [%x]",
          L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
          v8);
        return v3;
      }
    }
    else if ( Key != -1073741772 )
    {
      v7 = Key;
      AslLogCallPrintf(
        1,
        "SdbDeletePermLayerKeys",
        313,
        "Failed to open Key for \"%S\" [%x]",
        L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
        v7);
      return v3;
    }
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180046c40  mov     [rsp+arg_10], rbx
0x180046c45  push    rbp
0x180046c46  push    rsi
0x180046c47  push    rdi
0x180046c48  sub     rsp, 270h
0x180046c4f  mov     rax, cs:__security_cookie
0x180046c56  xor     rax, rsp
0x180046c59  mov     [rsp+288h+var_28], rax
0x180046c61  xor     esi, esi
0x180046c63  xorps   xmm0, xmm0
0x180046c66  mov     [rsp+288h+KeyHandle], rsi
0x180046c6b  mov     edi, edx
0x180046c6d  movups  xmmword ptr [rsp+288h+DestinationString.Length], xmm0
0x180046c72  test    rcx, rcx
0x180046c75  jz      loc_180046D67
0x180046c7b  cmp     [rcx], si
0x180046c7e  jz      loc_180046D67
0x180046c84  mov     r8, rcx
0x180046c87  mov     edx, 104h
0x180046c8c  lea     rcx, [rsp+288h+SourceString]
0x180046c91  mov     ebx, esi
0x180046c93  call    AslPathBuildSignature
0x180046c98  test    eax, eax
0x180046c9a  jns     short loc_180046CBD
0x180046c9c  lea     r9, aFailedToGetPer; "Failed to get perm layer path"
0x180046ca3  mov     r8d, 127h
0x180046ca9  lea     rdx, aSdbdeleteperml_0; "SdbDeletePermLayerKeys"
0x180046cb0  lea     ecx, [rsi+1]
0x180046cb3  call    AslLogCallPrintf
0x180046cb8  jmp     loc_180046D63
0x180046cbd  lea     rdx, [rsp+288h+SourceString]; SourceString
0x180046cc2  lea     rcx, [rsp+288h+DestinationString]; DestinationString
0x180046cc7  call    cs:__imp_RtlInitUnicodeString
0x180046ccd  lea     rbp, aSoftwareMicros_2; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x180046cd4  mov     dword ptr [rsp+288h+var_268], esi
0x180046cd8  mov     rdx, rbp
0x180046cdb  lea     rcx, [rsp+288h+KeyHandle]
0x180046ce0  mov     r9d, edi
0x180046ce3  mov     r8d, 20106h
0x180046ce9  call    AslRegistryGetKey
0x180046cee  test    eax, eax
0x180046cf0  jns     short loc_180046D22
0x180046cf2  cmp     eax, 0C0000034h
0x180046cf7  jz      short loc_180046D5E
0x180046cf9  mov     [rsp+288h+var_260], eax
0x180046cfd  lea     r9, aFailedToOpenKe_1; "Failed to open Key for \"%S\" [%x]"
0x180046d04  mov     r8d, 139h
0x180046d0a  lea     rdx, aSdbdeleteperml_0; "SdbDeletePermLayerKeys"
0x180046d11  mov     [rsp+288h+var_268], rbp
0x180046d16  mov     ecx, 1
0x180046d1b  call    AslLogCallPrintf
0x180046d20  jmp     short loc_180046D63
0x180046d22  mov     rcx, [rsp+288h+KeyHandle]; KeyHandle
0x180046d27  lea     rdx, [rsp+288h+DestinationString]; ValueName
0x180046d2c  call    cs:__imp_NtDeleteValueKey
0x180046d32  mov     rcx, [rsp+288h+KeyHandle]; Handle
0x180046d37  mov     edi, eax
0x180046d39  call    cs:__imp_NtClose
0x180046d3f  test    edi, edi
0x180046d41  jns     short loc_180046D5E
0x180046d43  cmp     edi, 0C0000034h
0x180046d49  jz      short loc_180046D5E
0x180046d4b  mov     [rsp+288h+var_260], edi
0x180046d4f  lea     r9, aFailedToDelete_0; "Failed to delete value from Key \"%S\" "...
0x180046d56  mov     r8d, 146h
0x180046d5c  jmp     short loc_180046D0A
0x180046d5e  mov     ebx, 1
0x180046d63  mov     eax, ebx
0x180046d65  jmp     short loc_180046D69
0x180046d67  xor     eax, eax
0x180046d69  mov     rcx, [rsp+288h+var_28]
0x180046d71  xor     rcx, rsp; StackCookie
0x180046d74  call    __security_check_cookie
0x180046d79  mov     rbx, [rsp+288h+arg_10]
0x180046d81  add     rsp, 270h
0x180046d88  pop     rdi
0x180046d89  pop     rsi
0x180046d8a  pop     rbp
0x180046d8b  retn
```
