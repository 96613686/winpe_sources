# SdbpQueryAppCompatFlagsByExeID

- ea: `0x14004634c`
- end: `0x140046435`
- name: `SdbpQueryAppCompatFlagsByExeID`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140046274`

## callees

- `0x140004469`
- `0x14003e364`
- `0x14004634c`
- `0x140046440`
- `0x140046660`

## string_xrefs

- `0x140046377`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x1400463f4`: `AslRegistryGetKey failed [%x]`
- `0x1400463fb`: `SdbpQueryAppCompatFlagsByExeID`
- `0x140046423`: `SdbpQueryAppCompatFlagsByExeID`
- `0x140046417`: `AslRegistryGetUInt32 failed for key: '%ws' [%x]`

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
    ZwClose_0(Handle);
  return v7;
}

```

## disassembly

```asm
0x14004634c  mov     rax, rsp
0x14004634f  mov     [rax+10h], rbx
0x140046353  mov     [rax+8], rcx
0x140046357  push    rbp
0x140046358  push    rsi
0x140046359  push    r14
0x14004635b  sub     rsp, 30h
0x14004635f  mov     r14, r9
0x140046362  mov     dword ptr [rax+8], 0
0x140046369  mov     r9d, r8d
0x14004636c  mov     qword ptr [rax+20h], 0
0x140046374  mov     rsi, rdx
0x140046377  lea     rbp, aSoftwareMicros_0; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x14004637e  mov     r8d, 80000100h
0x140046384  lea     rcx, [rax+20h]
0x140046388  mov     rdx, rbp
0x14004638b  call    AslRegistryGetKey
0x140046390  mov     ebx, eax
0x140046392  test    eax, eax
0x140046394  js      short loc_1400463E3
0x140046396  mov     rdx, [rsp+48h+Handle]
0x14004639b  lea     rcx, [rsp+48h+arg_0]
0x1400463a0  mov     r8, rsi
0x1400463a3  call    AslRegistryGetUInt32
0x1400463a8  mov     ebx, eax
0x1400463aa  test    eax, eax
0x1400463ac  jns     short loc_1400463DF
0x1400463ae  cmp     eax, 0C0000034h
0x1400463b3  jnz     short loc_14004640D
0x1400463b5  cmp     [rsp+48h+Handle], 0
0x1400463bb  mov     eax, [rsp+48h+arg_0]
0x1400463bf  mov     [r14], eax
0x1400463c2  jz      short loc_1400463CE
0x1400463c4  mov     rcx, [rsp+48h+Handle]; Handle
0x1400463c9  call    ZwClose_0
0x1400463ce  mov     eax, ebx
0x1400463d0  mov     rbx, [rsp+48h+arg_8]
0x1400463d5  add     rsp, 30h
0x1400463d9  pop     r14
0x1400463db  pop     rsi
0x1400463dc  pop     rbp
0x1400463dd  retn
0x1400463df  xor     ebx, ebx
0x1400463e1  jmp     short loc_1400463B5
0x1400463e3  cmp     eax, 0C0000034h
0x1400463e8  jz      short loc_1400463B5
0x1400463ea  mov     r8d, 40h ; '@'
0x1400463f0  mov     dword ptr [rsp+48h+var_28], eax
0x1400463f4  lea     r9, aAslregistryget_9; "AslRegistryGetKey failed [%x]"
0x1400463fb  lea     rdx, aSdbpqueryappco; "SdbpQueryAppCompatFlagsByExeID"
0x140046402  lea     ecx, [r8-3Fh]
0x140046406  call    AslLogCallPrintf
0x14004640b  jmp     short loc_1400463B5
0x14004640d  mov     r8d, 4Bh ; 'K'
0x140046413  mov     [rsp+48h+var_20], eax
0x140046417  lea     r9, aAslregistryget_7; "AslRegistryGetUInt32 failed for key: '%"...
0x14004641e  mov     [rsp+48h+var_28], rbp
0x140046423  lea     rdx, aSdbpqueryappco; "SdbpQueryAppCompatFlagsByExeID"
0x14004642a  lea     ecx, [r8-4Ah]
0x14004642e  call    AslLogCallPrintf
0x140046433  jmp     short loc_1400463B5
```
