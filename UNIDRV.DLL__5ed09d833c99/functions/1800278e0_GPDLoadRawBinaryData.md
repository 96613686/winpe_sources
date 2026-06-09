# GPDLoadRawBinaryData

- ea: `0x1800278e0`
- end: `0x1800279fd`
- name: `GPDLoadRawBinaryData`
- size: `285`
- prototype: `_QWORD *__fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18002431c`
- `0x180025dc0`

## callees

- `0x180007150`
- `0x180008c9c`
- `0x1800278e0`
- `0x180028ec0`
- `0x180029010`
- `0x18002ef80`
- `0x18003bbec`
- `0x18003c694`
- `0x1800720e0`
- `0x1800721d0`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800279bc`
- `KERNEL32!SetLastError` at `0x1800279bc`

## string_xrefs

- `0x1800279a4`: `Unable to locate or create Binary data.`

## pseudocode

```c
_QWORD *__fastcall GPDLoadRawBinaryData(STRSAFE_LPCWSTR pszSrc)
{
  __int64 v2; // rdx
  _QWORD *CachedBinaryData; // rbx
  unsigned int inited; // eax
  DWORD v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  if ( !pszSrc )
  {
    WriteDbgTraceErrorGpd((__int64)"GPDLoadRawBinaryData", "GPD filename is NULL.");
    return 0;
  }
  CachedBinaryData = GpdLoadCachedBinaryData(pszSrc);
  if ( !CachedBinaryData )
  {
    v7 = 0;
    v6 = 0;
    if ( !(unsigned int)BcreateGPDbinary(pszSrc, v2, &v7, &v6)
      || !v7
      || (CachedBinaryData = GpdCreateCachedBinaryDataFromMemory(v7, v6)) == 0 )
    {
      WriteDbgTraceErrorGpd((__int64)"GPDLoadRawBinaryData", "Unable to locate or create Binary data.");
      SetLastError(0x570u);
      return 0;
    }
  }
  CachedBinaryData[24] = 0;
  CachedBinaryData[23] = 0;
  CachedBinaryData[22] = 0;
  if ( !(unsigned int)BinitSizeOptionTables((__int64)CachedBinaryData)
    || (inited = DwInitSnapShotTable1((__int64)CachedBinaryData)) == 0
    || (unsigned int)DwInitSnapShotTable2((__int64)CachedBinaryData, inited) - 1 > 0xDF
    || !(unsigned int)BinitSnapShotIndexTable((__int64)CachedBinaryData) )
  {
    GPDUnloadRawBinaryData(CachedBinaryData);
    return 0;
  }
  return CachedBinaryData;
}

```

## disassembly

```asm
0x1800278e0  mov     [rsp+arg_10], rbx
0x1800278e5  push    rdi
0x1800278e6  sub     rsp, 20h
0x1800278ea  mov     rdi, rcx
0x1800278ed  test    rcx, rcx
0x1800278f0  jz      loc_18002797A
0x1800278f6  call    GpdLoadCachedBinaryData
0x1800278fb  mov     rbx, rax
0x1800278fe  test    rax, rax
0x180027901  jz      loc_1800279CA
0x180027907  mov     rcx, rbx
0x18002790a  mov     qword ptr [rbx+0C0h], 0
0x180027915  mov     qword ptr [rbx+0B8h], 0
0x180027920  mov     qword ptr [rbx+0B0h], 0
0x18002792b  call    BinitSizeOptionTables
0x180027930  test    eax, eax
0x180027932  jz      short loc_180027953
0x180027934  mov     rcx, rbx
0x180027937  call    DwInitSnapShotTable1
0x18002793c  test    eax, eax
0x18002793e  jz      short loc_180027953
0x180027940  mov     edx, eax
0x180027942  mov     rcx, rbx
0x180027945  call    DwInitSnapShotTable2
0x18002794a  dec     eax
0x18002794c  cmp     eax, 0DFh
0x180027951  jbe     short loc_180027969
0x180027953  mov     rcx, rbx
0x180027956  call    GPDUnloadRawBinaryData
0x18002795b  xor     eax, eax
0x18002795d  mov     rbx, [rsp+28h+arg_10]
0x180027962  add     rsp, 20h
0x180027966  pop     rdi
0x180027967  retn
0x180027969  mov     rcx, rbx
0x18002796c  call    BinitSnapShotIndexTable
0x180027971  test    eax, eax
0x180027973  jz      short loc_180027953
0x180027975  mov     rax, rbx
0x180027978  jmp     short loc_18002795D
0x18002797a  lea     rdx, aGpdFilenameIsN; "GPD filename is NULL."
0x180027981  lea     rcx, aGpdloadrawbina; "GPDLoadRawBinaryData"
0x180027988  call    WriteDbgTraceErrorGpd
0x18002798d  jmp     short loc_18002795B
0x18002798f  mov     edx, [rsp+28h+arg_0]
0x180027993  call    GpdCreateCachedBinaryDataFromMemory
0x180027998  mov     rbx, rax
0x18002799b  test    rax, rax
0x18002799e  jnz     loc_180027907
0x1800279a4  lea     rdx, aUnableToLocate; "Unable to locate or create Binary data."
0x1800279ab  lea     rcx, aGpdloadrawbina; "GPDLoadRawBinaryData"
0x1800279b2  call    WriteDbgTraceErrorGpd
0x1800279b7  mov     ecx, 570h; dwErrCode
0x1800279bc  call    cs:__imp_SetLastError
0x1800279c3  nop     dword ptr [rax+rax+00h]
0x1800279c8  jmp     short loc_18002795B
0x1800279ca  lea     r9, [rsp+28h+arg_0]
0x1800279cf  mov     [rsp+28h+arg_8], 0
0x1800279d8  lea     r8, [rsp+28h+arg_8]
0x1800279dd  mov     [rsp+28h+arg_0], 0
0x1800279e5  mov     rcx, rdi; pszSrc
0x1800279e8  call    BcreateGPDbinary
0x1800279ed  test    eax, eax
0x1800279ef  jz      short loc_1800279A4
0x1800279f1  mov     rcx, [rsp+28h+arg_8]
0x1800279f6  test    rcx, rcx
0x1800279f9  jz      short loc_1800279A4
0x1800279fb  jmp     short loc_18002798F
```
