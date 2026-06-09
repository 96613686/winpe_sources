# MessagingGetMediaTempFolder(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)

- ea: `0x18005cdcc`
- end: `0x18005ce38`
- name: `?MessagingGetMediaTempFolder@@YAJPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `108`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800522b0`
- `0x180052320`
- `0x180052770`
- `0x18005cd60`
- `0x18005d08c`

## callees

- `0x18005cd08`
- `0x18005cdcc`

## import_xrefs

- `UserDataPlatformHelperUtil!CreateKnownFolderPath` at `0x18005cdec`
- `UserDataPlatformHelperUtil!CreateKnownFolderPath` at `0x18005ce10`
- `UserDataPlatformHelperUtil!CreateKnownFolderPath` at `0x18005cdec`
- `UserDataPlatformHelperUtil!CreateKnownFolderPath` at `0x18005ce10`

## string_xrefs

- `0x18005cdd5`: `\Messaging\Temp\MMS\`
- `0x18005cdfc`: `\Messaging\Temp\MMS\`

## pseudocode

```c
__int64 __fastcall MessagingGetMediaTempFolder(__int64 a1)
{
  int KnownFolderPath; // eax
  unsigned int v3; // ebx

  if ( (unsigned int)CreateKnownFolderPath(qword_1800DBA40, L"\\Messaging\\Temp\\MMS\\", 1, a1) != -2147024894 )
    return 0;
  KnownFolderPath = CreateKnownFolderPath(&FOLDERID_LocalAppData, L"\\Messaging\\Temp\\MMS\\", 1, a1);
  v3 = KnownFolderPath;
  if ( KnownFolderPath >= 0 )
    return 0;
  Log_HREvent_33(KnownFolderPath);
  return v3;
}

```

## disassembly

```asm
0x18005cdcc  push    rbx
0x18005cdce  sub     rsp, 30h
0x18005cdd2  mov     rbx, rcx
0x18005cdd5  lea     rdx, ?c_mmsTempSubFolderPath@@3QBGB; "\\Messaging\\Temp\\MMS\\"
0x18005cddc  mov     r9, rcx
0x18005cddf  mov     r8d, 1
0x18005cde5  lea     rcx, qword_1800DBA40
0x18005cdec  call    cs:__imp_?CreateKnownFolderPath@@YAJAEBU_GUID@@PEBGHAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; CreateKnownFolderPath(_GUID const &,ushort const *,int,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18005cdf2  cmp     eax, 80070002h
0x18005cdf7  jnz     short loc_18005CE30
0x18005cdf9  mov     r9, rbx
0x18005cdfc  lea     rdx, ?c_mmsTempSubFolderPath@@3QBGB; "\\Messaging\\Temp\\MMS\\"
0x18005ce03  mov     r8d, 1
0x18005ce09  lea     rcx, FOLDERID_LocalAppData
0x18005ce10  call    cs:__imp_?CreateKnownFolderPath@@YAJAEBU_GUID@@PEBGHAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; CreateKnownFolderPath(_GUID const &,ushort const *,int,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18005ce16  mov     ebx, eax
0x18005ce18  test    eax, eax
0x18005ce1a  jns     short loc_18005CE30
0x18005ce1c  mov     edx, 1
0x18005ce21  mov     ecx, eax; int
0x18005ce23  lea     r9d, [rdx+68h]
0x18005ce27  call    Log_HREvent_33
0x18005ce2c  mov     eax, ebx
0x18005ce2e  jmp     short loc_18005CE32
0x18005ce30  xor     eax, eax
0x18005ce32  add     rsp, 30h
0x18005ce36  pop     rbx
0x18005ce37  retn
```
