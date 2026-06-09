# Streaming::FileOperations::ChangeFileAttribute(_FLT_INSTANCE *,_FILE_OBJECT &,ulong,uchar)

- ea: `0x14000279c`
- end: `0x14000285e`
- name: `?ChangeFileAttribute@FileOperations@Streaming@@YAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@KE@Z`
- size: `194`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject, struct _FILE_OBJECT *, unsigned int, unsigned __int8)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140007fe4`
- `0x14000a1f0`
- `0x14000b32c`
- `0x14000b448`

## callees

- `0x14000279c`
- `0x140015af0`

## import_xrefs

- `FLTMGR!FltQueryInformationFile` at `0x1400027eb`
- `FLTMGR!FltQueryInformationFile` at `0x1400027eb`
- `FLTMGR!FltSetInformationFile` at `0x140002832`
- `FLTMGR!FltSetInformationFile` at `0x140002832`

## pseudocode

```c
int __fastcall Streaming::FileOperations::ChangeFileAttribute(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        struct _FILE_OBJECT *a3,
        char a4)
{
  int result; // eax
  int v8; // eax
  _OWORD FileInformation[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v10; // [rsp+50h] [rbp-18h]

  memset(FileInformation, 0, sizeof(FileInformation));
  v10 = 0;
  result = FltQueryInformationFile(Instance, FileObject, FileInformation, 0x28u, FileBasicInformation, 0);
  if ( result >= 0 )
  {
    if ( a4 )
      v8 = v10 | 0x1000;
    else
      v8 = v10 & 0xFFFFEFFF;
    if ( !v8 )
      v8 = 128;
    LODWORD(v10) = v8;
    return FltSetInformationFile(Instance, FileObject, FileInformation, 0x28u, FileBasicInformation);
  }
  return result;
}

```

## disassembly

```asm
0x14000279c  mov     r11, rsp
0x14000279f  mov     [r11+18h], rbx
0x1400027a3  mov     [r11+20h], rsi
0x1400027a7  push    rdi
0x1400027a8  sub     rsp, 60h
0x1400027ac  mov     rax, cs:__security_cookie
0x1400027b3  xor     rax, rsp
0x1400027b6  mov     [rsp+68h+var_10], rax
0x1400027bb  xor     eax, eax
0x1400027bd  lea     r8, [r11-38h]; FileInformation
0x1400027c1  xorps   xmm0, xmm0
0x1400027c4  mov     [r11-40h], rax
0x1400027c8  mov     bl, r9b
0x1400027cb  mov     [rsp+68h+FileInformationClass], 4; FileInformationClass
0x1400027d3  movups  [rsp+68h+FileInformation], xmm0
0x1400027d8  lea     r9d, [rax+28h]; Length
0x1400027dc  mov     rsi, rdx
0x1400027df  movups  [rsp+68h+var_28], xmm0
0x1400027e4  mov     rdi, rcx
0x1400027e7  mov     [r11-18h], rax
0x1400027eb  call    cs:__imp_FltQueryInformationFile
0x1400027f2  nop     dword ptr [rax+rax+00h]
0x1400027f7  test    eax, eax
0x1400027f9  js      short loc_14000283E
0x1400027fb  mov     eax, dword ptr [rsp+68h+var_18]
0x1400027ff  test    bl, bl
0x140002801  jz      short loc_140002809
0x140002803  bts     eax, 0Ch
0x140002807  jmp     short loc_14000280D
0x140002809  btr     eax, 0Ch
0x14000280d  mov     ecx, 80h
0x140002812  mov     [rsp+68h+FileInformationClass], 4; FileInformationClass
0x14000281a  test    eax, eax
0x14000281c  lea     r8, [rsp+68h+FileInformation]; FileInformation
0x140002821  mov     rdx, rsi; FileObject
0x140002824  cmovz   eax, ecx
0x140002827  lea     r9d, [rcx-58h]; Length
0x14000282b  mov     dword ptr [rsp+68h+var_18], eax
0x14000282f  mov     rcx, rdi; Instance
0x140002832  call    cs:__imp_FltSetInformationFile
0x140002839  nop     dword ptr [rax+rax+00h]
0x14000283e  mov     rcx, [rsp+68h+var_10]
0x140002843  xor     rcx, rsp; StackCookie
0x140002846  call    __security_check_cookie
0x14000284b  lea     r11, [rsp+68h+var_8]
0x140002850  mov     rbx, [r11+20h]
0x140002854  mov     rsi, [r11+28h]
0x140002858  mov     rsp, r11
0x14000285b  pop     rdi
0x14000285c  retn
```
