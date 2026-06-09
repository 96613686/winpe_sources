# GPDLoadRawBinaryData

- ea: `0x1800271d4`
- end: `0x1800272ea`
- name: `GPDLoadRawBinaryData`
- size: `278`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180023e18`
- `0x180025780`

## callees

- `0x180007220`
- `0x180008d2c`
- `0x1800271d4`
- `0x1800286ac`
- `0x180028800`
- `0x18002e550`
- `0x18003aee0`
- `0x18003b934`
- `0x1800700cc`
- `0x1800701a8`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800272af`
- `KERNEL32!SetLastError` at `0x1800272af`

## string_xrefs

- `0x180027297`: `Unable to locate or create Binary data.`

## pseudocode

```c
_QWORD *__fastcall GPDLoadRawBinaryData(STRSAFE_LPCWSTR pszSrc)
{
  _QWORD *CachedBinaryData; // rbx
  unsigned int inited; // eax

  if ( !pszSrc )
  {
    WriteDbgTraceErrorGpd("GPDLoadRawBinaryData", "GPD filename is NULL.");
    return 0;
  }
  CachedBinaryData = GpdLoadCachedBinaryData(pszSrc);
  if ( !CachedBinaryData )
  {
    BcreateGPDbinary(pszSrc);
    WriteDbgTraceErrorGpd("GPDLoadRawBinaryData", "Unable to locate or create Binary data.");
    SetLastError(0x570u);
    return 0;
  }
  CachedBinaryData[24] = 0;
  CachedBinaryData[23] = 0;
  CachedBinaryData[22] = 0;
  if ( !(unsigned int)BinitSizeOptionTables(CachedBinaryData)
    || (inited = DwInitSnapShotTable1((__int64)CachedBinaryData)) == 0
    || (unsigned int)DwInitSnapShotTable2((__int64)CachedBinaryData, inited) - 1 > 0xDF
    || !(unsigned int)BinitSnapShotIndexTable(CachedBinaryData) )
  {
    GPDUnloadRawBinaryData(CachedBinaryData);
    return 0;
  }
  return CachedBinaryData;
}

```

## disassembly

```asm
0x1800271d4  mov     [rsp+arg_10], rbx
0x1800271d9  push    rdi
0x1800271da  sub     rsp, 20h
0x1800271de  mov     rdi, rcx
0x1800271e1  test    rcx, rcx
0x1800271e4  jz      loc_18002726D
0x1800271ea  call    GpdLoadCachedBinaryData
0x1800271ef  mov     rbx, rax
0x1800271f2  test    rax, rax
0x1800271f5  jz      loc_1800272B7
0x1800271fb  mov     rcx, rbx
0x1800271fe  mov     qword ptr [rbx+0C0h], 0
0x180027209  mov     qword ptr [rbx+0B8h], 0
0x180027214  mov     qword ptr [rbx+0B0h], 0
0x18002721f  call    BinitSizeOptionTables
0x180027224  test    eax, eax
0x180027226  jz      short loc_180027247
0x180027228  mov     rcx, rbx
0x18002722b  call    DwInitSnapShotTable1
0x180027230  test    eax, eax
0x180027232  jz      short loc_180027247
0x180027234  mov     edx, eax
0x180027236  mov     rcx, rbx
0x180027239  call    DwInitSnapShotTable2
0x18002723e  dec     eax
0x180027240  cmp     eax, 0DFh
0x180027245  jbe     short loc_18002725C
0x180027247  mov     rcx, rbx
0x18002724a  call    GPDUnloadRawBinaryData
0x18002724f  xor     eax, eax
0x180027251  mov     rbx, [rsp+28h+arg_10]
0x180027256  add     rsp, 20h
0x18002725a  pop     rdi
0x18002725b  retn
0x18002725c  mov     rcx, rbx
0x18002725f  call    BinitSnapShotIndexTable
0x180027264  test    eax, eax
0x180027266  jz      short loc_180027247
0x180027268  mov     rax, rbx
0x18002726b  jmp     short loc_180027251
0x18002726d  lea     rdx, aGpdFilenameIsN; "GPD filename is NULL."
0x180027274  lea     rcx, aGpdloadrawbina; "GPDLoadRawBinaryData"
0x18002727b  call    WriteDbgTraceErrorGpd
0x180027280  jmp     short loc_18002724F
0x180027282  mov     edx, [rsp+28h+arg_0]
0x180027286  call    GpdCreateCachedBinaryDataFromMemory
0x18002728b  mov     rbx, rax
0x18002728e  test    rax, rax
0x180027291  jnz     loc_1800271FB
0x180027297  lea     rdx, aUnableToLocate; "Unable to locate or create Binary data."
0x18002729e  lea     rcx, aGpdloadrawbina; "GPDLoadRawBinaryData"
0x1800272a5  call    WriteDbgTraceErrorGpd
0x1800272aa  mov     ecx, 570h; dwErrCode
0x1800272af  call    cs:__imp_SetLastError
0x1800272b5  jmp     short loc_18002724F
0x1800272b7  lea     r9, [rsp+28h+arg_0]
0x1800272bc  mov     [rsp+28h+arg_8], 0
0x1800272c5  lea     r8, [rsp+28h+arg_8]
0x1800272ca  mov     [rsp+28h+arg_0], 0
0x1800272d2  mov     rcx, rdi; pszSrc
0x1800272d5  call    BcreateGPDbinary
0x1800272da  test    eax, eax
0x1800272dc  jz      short loc_180027297
0x1800272de  mov     rcx, [rsp+28h+arg_8]
0x1800272e3  test    rcx, rcx
0x1800272e6  jz      short loc_180027297
0x1800272e8  jmp     short loc_180027282
```
