# SdbpQueryAppCompatFlagsByExeID

- ea: `0x180016718`
- end: `0x18001680d`
- name: `SdbpQueryAppCompatFlagsByExeID`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016640`

## callees

- `0x18000f114`
- `0x180016718`
- `0x180016910`
- `0x180016b90`

## import_xrefs

- `ntdll!ZwClose` at `0x18001679d`
- `ntdll!ZwClose` at `0x18001679d`

## string_xrefs

- `0x18001674b`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x1800167d0`: `SdbpQueryAppCompatFlagsByExeID`
- `0x1800167f8`: `SdbpQueryAppCompatFlagsByExeID`
- `0x1800167c9`: `AslRegistryGetKey failed [%x]`
- `0x1800167ec`: `AslRegistryGetUInt32 failed for key: '%ws' [%x]`

## pseudocode

```c
__int64 __fastcall SdbpQueryAppCompatFlagsByExeID(__int64 a1, __int64 a2, int a3, _DWORD *a4)
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
  Key = AslRegistryGetKey(
          &Handle,
          L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
          0x80000100,
          a3,
          0);
  v7 = Key;
  if ( Key < 0 )
  {
    if ( Key != -1073741772 )
      AslLogCallPrintf(1, "SdbpQueryAppCompatFlagsByExeID", 64, "AslRegistryGetKey failed [%x]", Key);
  }
  else
  {
    UInt32 = AslRegistryGetUInt32(&v12, Handle, a2);
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
  v9 = Handle == 0;
  *a4 = v12;
  if ( !v9 )
    ZwClose(Handle);
  return v7;
}

```

## disassembly

```asm
0x180016718  mov     rax, rsp
0x18001671b  mov     [rax+10h], rbx
0x18001671f  mov     [rax+8], rcx
0x180016723  push    rsi
0x180016724  push    r14
0x180016726  push    r15
0x180016728  sub     rsp, 30h
0x18001672c  mov     r14, r9
0x18001672f  mov     dword ptr [rax+8], 0
0x180016736  mov     r9d, r8d
0x180016739  mov     qword ptr [rax+20h], 0
0x180016741  mov     rsi, rdx
0x180016744  mov     dword ptr [rax-28h], 0
0x18001674b  lea     r15, aSoftwareMicros; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x180016752  mov     r8d, 80000100h
0x180016758  mov     rdx, r15
0x18001675b  lea     rcx, [rax+20h]
0x18001675f  call    AslRegistryGetKey
0x180016764  mov     ebx, eax
0x180016766  test    eax, eax
0x180016768  js      short loc_1800167B8
0x18001676a  mov     rdx, [rsp+48h+Handle]
0x18001676f  lea     rcx, [rsp+48h+arg_0]
0x180016774  mov     r8, rsi
0x180016777  call    AslRegistryGetUInt32
0x18001677c  mov     ebx, eax
0x18001677e  test    eax, eax
0x180016780  jns     short loc_1800167B4
0x180016782  cmp     eax, 0C0000034h
0x180016787  jnz     short loc_1800167E2
0x180016789  cmp     [rsp+48h+Handle], 0
0x18001678f  mov     eax, [rsp+48h+arg_0]
0x180016793  mov     [r14], eax
0x180016796  jz      short loc_1800167A3
0x180016798  mov     rcx, [rsp+48h+Handle]; Handle
0x18001679d  call    cs:__imp_ZwClose
0x1800167a3  mov     eax, ebx
0x1800167a5  mov     rbx, [rsp+48h+arg_8]
0x1800167aa  add     rsp, 30h
0x1800167ae  pop     r15
0x1800167b0  pop     r14
0x1800167b2  pop     rsi
0x1800167b3  retn
0x1800167b4  xor     ebx, ebx
0x1800167b6  jmp     short loc_180016789
0x1800167b8  cmp     eax, 0C0000034h
0x1800167bd  jz      short loc_180016789
0x1800167bf  mov     r8d, 40h ; '@'
0x1800167c5  mov     dword ptr [rsp+48h+var_28], eax
0x1800167c9  lea     r9, aAslregistryget_7; "AslRegistryGetKey failed [%x]"
0x1800167d0  lea     rdx, aSdbpqueryappco; "SdbpQueryAppCompatFlagsByExeID"
0x1800167d7  lea     ecx, [r8-3Fh]
0x1800167db  call    AslLogCallPrintf
0x1800167e0  jmp     short loc_180016789
0x1800167e2  mov     r8d, 4Bh ; 'K'
0x1800167e8  mov     [rsp+48h+var_20], eax
0x1800167ec  lea     r9, aAslregistryget_5; "AslRegistryGetUInt32 failed for key: '%"...
0x1800167f3  mov     [rsp+48h+var_28], r15
0x1800167f8  lea     rdx, aSdbpqueryappco; "SdbpQueryAppCompatFlagsByExeID"
0x1800167ff  lea     ecx, [r8-4Ah]
0x180016803  call    AslLogCallPrintf
0x180016808  jmp     loc_180016789
```
