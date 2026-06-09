# SdbpQueryAppCompatFlagsByExeID

- ea: `0x18012517c`
- end: `0x180125263`
- name: `SdbpQueryAppCompatFlagsByExeID`
- size: `231`
- prototype: `__int64 __fastcall(__int64, __int64, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801250a8`

## callees

- `0x1800197d4`
- `0x180027118`
- `0x180027340`
- `0x18012517c`

## import_xrefs

- `ntdll!ZwClose` at `0x18012524d`
- `ntdll!ZwClose` at `0x18012524d`

## string_xrefs

- `0x1801251a7`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x1801251d7`: `AslRegistryGetKey failed [%x]`
- `0x1801251de`: `SdbpQueryAppCompatFlagsByExeID`
- `0x180125225`: `SdbpQueryAppCompatFlagsByExeID`
- `0x180125219`: `AslRegistryGetUInt32 failed for key: '%ws' [%x]`

## pseudocode

```c
__int64 __fastcall SdbpQueryAppCompatFlagsByExeID(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  int Key; // eax
  unsigned int v7; // ebx
  int UInt32; // eax
  bool v9; // zf
  int v11; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+54h] [rbp+Ch]
  HANDLE Handle; // [rsp+68h] [rbp+20h] BYREF

  v12 = HIDWORD(a1);
  v11 = 0;
  Handle = 0;
  Key = AslRegistryGetKey(&Handle, L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags", 0x80000100, a3);
  v7 = Key;
  if ( Key >= 0 )
  {
    UInt32 = AslRegistryGetUInt32(&v11, Handle, a2);
    v7 = UInt32;
    if ( UInt32 >= 0 )
    {
      v7 = 0;
    }
    else if ( UInt32 != -1073741772 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpQueryAppCompatFlagsByExeID",
        75,
        (unsigned int)"AslRegistryGetUInt32 failed for key: '%ws' [%x]");
    }
  }
  else if ( Key != -1073741772 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpQueryAppCompatFlagsByExeID",
      64,
      (unsigned int)"AslRegistryGetKey failed [%x]");
  }
  v9 = Handle == 0;
  *a4 = v11;
  if ( !v9 )
    ZwClose(Handle);
  return v7;
}

```

## disassembly

```asm
0x18012517c  mov     rax, rsp
0x18012517f  mov     [rax+10h], rbx
0x180125183  mov     [rax+8], rcx
0x180125187  push    rbp
0x180125188  push    rsi
0x180125189  push    r14
0x18012518b  sub     rsp, 30h
0x18012518f  mov     r14, r9
0x180125192  mov     dword ptr [rax+8], 0
0x180125199  mov     r9d, r8d
0x18012519c  mov     qword ptr [rax+20h], 0
0x1801251a4  mov     rsi, rdx
0x1801251a7  lea     rbp, aSoftwareMicros_2; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x1801251ae  mov     r8d, 80000100h
0x1801251b4  lea     rcx, [rax+20h]
0x1801251b8  mov     rdx, rbp
0x1801251bb  call    AslRegistryGetKey
0x1801251c0  mov     ebx, eax
0x1801251c2  test    eax, eax
0x1801251c4  jns     short loc_1801251F0
0x1801251c6  cmp     eax, 0C0000034h
0x1801251cb  jz      short loc_180125239
0x1801251cd  mov     r8d, 40h ; '@'
0x1801251d3  mov     dword ptr [rsp+48h+var_28], eax
0x1801251d7  lea     r9, aAslregistryget_7; "AslRegistryGetKey failed [%x]"
0x1801251de  lea     rdx, aSdbpqueryappco; "SdbpQueryAppCompatFlagsByExeID"
0x1801251e5  lea     ecx, [r8-3Fh]
0x1801251e9  call    AslLogCallPrintf
0x1801251ee  jmp     short loc_180125239
0x1801251f0  mov     rdx, [rsp+48h+Handle]
0x1801251f5  lea     rcx, [rsp+48h+arg_0]
0x1801251fa  mov     r8, rsi
0x1801251fd  call    AslRegistryGetUInt32
0x180125202  mov     ebx, eax
0x180125204  test    eax, eax
0x180125206  jns     short loc_180125237
0x180125208  cmp     eax, 0C0000034h
0x18012520d  jz      short loc_180125239
0x18012520f  mov     r8d, 4Bh ; 'K'
0x180125215  mov     [rsp+48h+var_20], eax
0x180125219  lea     r9, aAslregistryget_5; "AslRegistryGetUInt32 failed for key: '%"...
0x180125220  mov     [rsp+48h+var_28], rbp
0x180125225  lea     rdx, aSdbpqueryappco; "SdbpQueryAppCompatFlagsByExeID"
0x18012522c  lea     ecx, [r8-4Ah]
0x180125230  call    AslLogCallPrintf
0x180125235  jmp     short loc_180125239
0x180125237  xor     ebx, ebx
0x180125239  cmp     [rsp+48h+Handle], 0
0x18012523f  mov     eax, [rsp+48h+arg_0]
0x180125243  mov     [r14], eax
0x180125246  jz      short loc_180125253
0x180125248  mov     rcx, [rsp+48h+Handle]; Handle
0x18012524d  call    cs:__imp_ZwClose
0x180125253  mov     eax, ebx
0x180125255  mov     rbx, [rsp+48h+arg_8]
0x18012525a  add     rsp, 30h
0x18012525e  pop     r14
0x180125260  pop     rsi
0x180125261  pop     rbp
0x180125262  retn
```
