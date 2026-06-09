# SdbpQueryAppCompatFlagsByExeID

- ea: `0x14003a6e8`
- end: `0x14003a7cf`
- name: `SdbpQueryAppCompatFlagsByExeID`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003a614`

## callees

- `0x14003a6e8`
- `0x14003bf18`
- `0x14003c618`
- `0x14003c910`

## import_xrefs

- `ntdll!ZwClose` at `0x14003a7b9`
- `ntdll!ZwClose` at `0x14003a7b9`

## string_xrefs

- `0x14003a713`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x14003a74a`: `SdbpQueryAppCompatFlagsByExeID`
- `0x14003a791`: `SdbpQueryAppCompatFlagsByExeID`
- `0x14003a743`: `AslRegistryGetKey failed [%x]`
- `0x14003a785`: `AslRegistryGetUInt32 failed for key: '%ws' [%x]`

## pseudocode

```c
__int64 __fastcall SdbpQueryAppCompatFlagsByExeID(__int64 a1, const WCHAR *a2, int a3, _DWORD *a4)
{
  int Key; // eax
  unsigned int v7; // ebx
  int UInt32; // eax
  bool v9; // zf
  int v11; // [rsp+28h] [rbp-20h]
  int v12; // [rsp+50h] [rbp+8h] BYREF
  int v13; // [rsp+54h] [rbp+Ch]
  HANDLE Handle; // [rsp+68h] [rbp+20h] BYREF

  v13 = HIDWORD(a1);
  v12 = 0;
  Handle = 0;
  Key = AslRegistryGetKey(&Handle, L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags", 0x80000100, a3);
  v7 = Key;
  if ( Key >= 0 )
  {
    UInt32 = AslRegistryGetUInt32((__int64)&v12, (__int64)Handle, a2);
    v7 = UInt32;
    if ( UInt32 >= 0 )
    {
      v7 = 0;
    }
    else if ( UInt32 != -1073741772 )
    {
      v11 = UInt32;
      AslLogCallPrintf(
        1,
        "SdbpQueryAppCompatFlagsByExeID",
        75,
        "AslRegistryGetUInt32 failed for key: '%ws' [%x]",
        L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
        v11);
    }
  }
  else if ( Key != -1073741772 )
  {
    AslLogCallPrintf(1, "SdbpQueryAppCompatFlagsByExeID", 64, "AslRegistryGetKey failed [%x]", Key);
  }
  v9 = Handle == 0;
  *a4 = v12;
  if ( !v9 )
    ZwClose(Handle);
  return v7;
}

```

## disassembly

```asm
0x14003a6e8  mov     rax, rsp
0x14003a6eb  mov     [rax+10h], rbx
0x14003a6ef  mov     [rax+8], rcx
0x14003a6f3  push    rbp
0x14003a6f4  push    rsi
0x14003a6f5  push    r14
0x14003a6f7  sub     rsp, 30h
0x14003a6fb  mov     r14, r9
0x14003a6fe  mov     dword ptr [rax+8], 0
0x14003a705  mov     r9d, r8d
0x14003a708  mov     qword ptr [rax+20h], 0
0x14003a710  mov     rsi, rdx
0x14003a713  lea     rbp, aSoftwareMicros; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x14003a71a  mov     r8d, 80000100h
0x14003a720  lea     rcx, [rax+20h]
0x14003a724  mov     rdx, rbp
0x14003a727  call    AslRegistryGetKey
0x14003a72c  mov     ebx, eax
0x14003a72e  test    eax, eax
0x14003a730  jns     short loc_14003A75C
0x14003a732  cmp     eax, 0C0000034h
0x14003a737  jz      short loc_14003A7A5
0x14003a739  mov     r8d, 40h ; '@'
0x14003a73f  mov     dword ptr [rsp+48h+var_28], eax
0x14003a743  lea     r9, aAslregistryget_6; "AslRegistryGetKey failed [%x]"
0x14003a74a  lea     rdx, aSdbpqueryappco; "SdbpQueryAppCompatFlagsByExeID"
0x14003a751  lea     ecx, [r8-3Fh]
0x14003a755  call    AslLogCallPrintf
0x14003a75a  jmp     short loc_14003A7A5
0x14003a75c  mov     rdx, [rsp+48h+Handle]
0x14003a761  lea     rcx, [rsp+48h+arg_0]
0x14003a766  mov     r8, rsi
0x14003a769  call    AslRegistryGetUInt32
0x14003a76e  mov     ebx, eax
0x14003a770  test    eax, eax
0x14003a772  jns     short loc_14003A7A3
0x14003a774  cmp     eax, 0C0000034h
0x14003a779  jz      short loc_14003A7A5
0x14003a77b  mov     r8d, 4Bh ; 'K'
0x14003a781  mov     [rsp+48h+var_20], eax
0x14003a785  lea     r9, aAslregistryget_5; "AslRegistryGetUInt32 failed for key: '%"...
0x14003a78c  mov     [rsp+48h+var_28], rbp
0x14003a791  lea     rdx, aSdbpqueryappco; "SdbpQueryAppCompatFlagsByExeID"
0x14003a798  lea     ecx, [r8-4Ah]
0x14003a79c  call    AslLogCallPrintf
0x14003a7a1  jmp     short loc_14003A7A5
0x14003a7a3  xor     ebx, ebx
0x14003a7a5  cmp     [rsp+48h+Handle], 0
0x14003a7ab  mov     eax, [rsp+48h+arg_0]
0x14003a7af  mov     [r14], eax
0x14003a7b2  jz      short loc_14003A7BF
0x14003a7b4  mov     rcx, [rsp+48h+Handle]; Handle
0x14003a7b9  call    cs:__imp_ZwClose
0x14003a7bf  mov     eax, ebx
0x14003a7c1  mov     rbx, [rsp+48h+arg_8]
0x14003a7c6  add     rsp, 30h
0x14003a7ca  pop     r14
0x14003a7cc  pop     rsi
0x14003a7cd  pop     rbp
0x14003a7ce  retn
```
