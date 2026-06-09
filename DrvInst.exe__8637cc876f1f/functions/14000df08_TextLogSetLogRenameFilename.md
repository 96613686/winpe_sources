# TextLogSetLogRenameFilename

- ea: `0x14000df08`
- end: `0x14000dfce`
- name: `TextLogSetLogRenameFilename`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x14000dc64`

## callees

- `0x14000aedc`
- `0x14000b28c`
- `0x14000bcbc`
- `0x14000df08`

## import_xrefs

- `ntdll!NtDeleteValueKey` at `0x14000df86`
- `ntdll!NtDeleteValueKey` at `0x14000df86`
- `ntdll!RtlInitUnicodeString` at `0x14000df77`
- `ntdll!RtlInitUnicodeString` at `0x14000df77`
- `ntdll!RtlNtStatusToDosError` at `0x14000df92`
- `ntdll!RtlNtStatusToDosError` at `0x14000df92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dfb6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000dfb6`

## string_xrefs

- `0x14000df43`: `SYSTEM\Setup\SetupapiLogRename`

## pseudocode

```c
_BOOL8 __fastcall TextLogSetLogRenameFilename(__int64 a1, void *a2)
{
  const WCHAR *FileTitle; // rdi
  ULONG v3; // eax
  ULONG v4; // ebx
  int v5; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp+10h] BYREF

  KeyHandle = a2;
  FileTitle = *(const WCHAR **)(a1 + 16);
  KeyHandle = 0;
  if ( !TextLogOffline )
    FileTitle = (const WCHAR *)pSetupGetFileTitle(FileTitle);
  v3 = pSetupOpenKeyEx(-2147483646, L"SYSTEM\\Setup\\SetupapiLogRename", 2, &KeyHandle);
  v4 = v3;
  if ( v3 )
  {
    if ( v3 == 2 )
      v4 = 0;
  }
  else
  {
    v4 = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, FileTitle);
    v5 = NtDeleteValueKey((HANDLE)(unsigned int)KeyHandle, &DestinationString);
    if ( v5 < 0 )
      v4 = RtlNtStatusToDosError(v5);
    if ( v4 == 2 )
      v4 = 0;
  }
  if ( KeyHandle )
    pSetupCloseKey(KeyHandle);
  SetLastError(v4);
  return v4 == 0;
}

```

## disassembly

```asm
0x14000df08  mov     [rsp+arg_0], rbx
0x14000df0d  mov     [rsp+KeyHandle], rdx
0x14000df12  push    rdi
0x14000df13  sub     rsp, 30h
0x14000df17  cmp     cs:TextLogOffline, 0
0x14000df1e  mov     rdi, [rcx+10h]
0x14000df22  mov     [rsp+38h+KeyHandle], 0
0x14000df2b  jnz     short loc_14000DF38
0x14000df2d  mov     rcx, rdi
0x14000df30  call    pSetupGetFileTitle
0x14000df35  mov     rdi, rax
0x14000df38  lea     r9, [rsp+38h+KeyHandle]
0x14000df3d  mov     r8d, 2
0x14000df43  lea     rdx, aSystemSetupSet; "SYSTEM\\Setup\\SetupapiLogRename"
0x14000df4a  mov     rcx, 0FFFFFFFF80000002h
0x14000df51  call    pSetupOpenKeyEx
0x14000df56  mov     ebx, eax
0x14000df58  test    eax, eax
0x14000df5a  jz      short loc_14000DF65
0x14000df5c  cmp     eax, 2
0x14000df5f  jnz     short loc_14000DFA2
0x14000df61  xor     ebx, ebx
0x14000df63  jmp     short loc_14000DFA2
0x14000df65  xorps   xmm0, xmm0
0x14000df68  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14000df6d  mov     rdx, rdi; SourceString
0x14000df70  xor     ebx, ebx
0x14000df72  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x14000df77  call    cs:__imp_RtlInitUnicodeString
0x14000df7d  mov     ecx, dword ptr [rsp+38h+KeyHandle]; KeyHandle
0x14000df81  lea     rdx, [rsp+38h+DestinationString]; ValueName
0x14000df86  call    cs:__imp_NtDeleteValueKey
0x14000df8c  test    eax, eax
0x14000df8e  jns     short loc_14000DF9A
0x14000df90  mov     ecx, eax; Status
0x14000df92  call    cs:__imp_RtlNtStatusToDosError
0x14000df98  mov     ebx, eax
0x14000df9a  xor     eax, eax
0x14000df9c  cmp     ebx, 2
0x14000df9f  cmovz   ebx, eax
0x14000dfa2  cmp     [rsp+38h+KeyHandle], 0
0x14000dfa8  jz      short loc_14000DFB4
0x14000dfaa  mov     rcx, [rsp+38h+KeyHandle]
0x14000dfaf  call    pSetupCloseKey
0x14000dfb4  mov     ecx, ebx; dwErrCode
0x14000dfb6  call    cs:__imp_SetLastError
0x14000dfbc  xor     eax, eax
0x14000dfbe  test    ebx, ebx
0x14000dfc0  mov     rbx, [rsp+38h+arg_0]
0x14000dfc5  setz    al
0x14000dfc8  add     rsp, 30h
0x14000dfcc  pop     rdi
0x14000dfcd  retn
```
