# BfspCreateMemtestObject

- ea: `0x18004eb2c`
- end: `0x18004ed2b`
- name: `BfspCreateMemtestObject`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180050410`

## callees

- `0x1800078b0`
- `0x180008724`
- `0x18004cdd4`
- `0x18004eb2c`
- `0x18004f854`
- `0x1800507fc`
- `0x180050894`
- `0x180050c94`

## import_xrefs

- `bcd!BcdSetElementData` at `0x18004ecc7`
- `bcd!BcdSetElementData` at `0x18004ecc7`
- `bcd!BcdCloseObject` at `0x18004ebd6`
- `bcd!BcdCloseObject` at `0x18004ebd6`
- `bcd!BcdOpenObject` at `0x18004eb8d`
- `bcd!BcdOpenObject` at `0x18004ec5c`
- `bcd!BcdOpenObject` at `0x18004eb8d`
- `bcd!BcdOpenObject` at `0x18004ec5c`
- `bcd!BcdCopyObjects` at `0x18004ec14`
- `bcd!BcdCopyObjects` at `0x18004ec14`

## string_xrefs

- `0x18004ecd3`: `Failed to set element application path. Status = [%x]`
- `0x18004ebb8`: `Failed to open handle to Memtest object. Status = [%x]`
- `0x18004ec20`: `Failed to copy memtest object. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCreateMemtestObject(__int64 a1, __int64 a2)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rcx
  unsigned int BcdCopyFlags; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // r9
  int v11; // eax
  __int64 v13; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  v14 = 0;
  v13 = 0;
  BfspLogMessage(2, L"Creating MemTest object.");
  v4 = BcdOpenObject(a1, &GUID_WINDOWS_MEMORY_TESTER, &v13);
  v5 = v4;
  if ( v4 >= 0 )
  {
    BcdCloseObject(v13);
    v6 = (unsigned int)dword_1800A453C;
    v13 = 0;
    dword_1800A453C |= 0x800u;
    LODWORD(v6) = dword_1800A453C;
    v14 = 0x1020000500000001LL;
    BcdCopyFlags = BfspGetBcdCopyFlags(v6);
    v8 = BcdCopyObjects(a1, &v14, BcdCopyFlags, a2);
    v5 = v8;
    if ( v8 >= 0 )
    {
      v5 = BfspSetObjectDeviceAndPath(a1, a2, &GUID_WINDOWS_MEMORY_TESTER, &GUID_WINDOWS_MEMORY_TESTER);
      if ( v5 >= 0 )
      {
        if ( byte_1800A4538 )
        {
          v9 = BcdOpenObject(a2, &GUID_WINDOWS_MEMORY_TESTER, &v13);
          v5 = v9;
          if ( v9 < 0 )
          {
            BfspLogMessage(4, L"Failed to get a handle to the memtest object. Status = [%x]", (unsigned int)v9);
            return (unsigned int)v5;
          }
          swprintf_s(Buffer, 0x104u, L"%s%s", L"\\EFI\\Microsoft\\Boot\\", L"memtest.efi");
          v10 = -1;
          do
            ++v10;
          while ( Buffer[v10] );
          v11 = BcdSetElementData(v13, 301989890, Buffer, (unsigned int)(2 * v10 + 2));
          v5 = v11;
          if ( v11 < 0 )
          {
            BfspLogMessage(4, L"Failed to set element application path. Status = [%x]", (unsigned int)v11);
            return (unsigned int)v5;
          }
        }
        v5 = BfspSetLocale(a2, &GUID_WINDOWS_MEMORY_TESTER);
        if ( v5 >= 0 )
          return (unsigned int)BfspSetObjectStringElements(
                                 a1,
                                 a2,
                                 &GUID_WINDOWS_MEMORY_TESTER,
                                 &GUID_WINDOWS_MEMORY_TESTER);
      }
    }
    else
    {
      BfspLogMessage(4, L"Failed to copy memtest object. Status = [%x]", (unsigned int)v8);
    }
  }
  else if ( v4 == -1073741772 )
  {
    BfspLogMessage(2, L"Memory Tester application not found. Skipping add.");
    return 0;
  }
  else
  {
    BfspLogMessage(4, L"Failed to open handle to Memtest object. Status = [%x]", (unsigned int)v4);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004eb2c  mov     [rsp-8+arg_10], rbx
0x18004eb31  push    rbp
0x18004eb32  push    rsi
0x18004eb33  push    rdi
0x18004eb34  push    r14
0x18004eb36  push    r15
0x18004eb38  lea     rbp, [rsp-160h]
0x18004eb40  sub     rsp, 260h
0x18004eb47  mov     rax, cs:__security_cookie
0x18004eb4e  xor     rax, rsp
0x18004eb51  mov     [rbp+180h+var_30], rax
0x18004eb58  xor     r14d, r14d
0x18004eb5b  mov     rdi, rdx
0x18004eb5e  mov     rsi, rcx
0x18004eb61  mov     [rsp+280h+var_248], r14
0x18004eb66  lea     rdx, aCreatingMemtes; "Creating MemTest object."
0x18004eb6d  mov     [rsp+280h+var_250], r14
0x18004eb72  lea     ecx, [r14+2]
0x18004eb76  call    BfspLogMessage
0x18004eb7b  lea     r15, GUID_WINDOWS_MEMORY_TESTER
0x18004eb82  mov     rcx, rsi
0x18004eb85  mov     rdx, r15
0x18004eb88  lea     r8, [rsp+280h+var_250]
0x18004eb8d  call    cs:__imp_BcdOpenObject
0x18004eb93  mov     ebx, eax
0x18004eb95  test    eax, eax
0x18004eb97  jns     short loc_18004EBD1
0x18004eb99  cmp     eax, 0C0000034h
0x18004eb9e  jnz     short loc_18004EBB8
0x18004eba0  lea     rdx, aMemoryTesterAp; "Memory Tester application not found. Sk"...
0x18004eba7  lea     ecx, [r14+2]
0x18004ebab  call    BfspLogMessage
0x18004ebb0  mov     ebx, r14d
0x18004ebb3  jmp     loc_18004ED03
0x18004ebb8  lea     rdx, aFailedToOpenHa_0; "Failed to open handle to Memtest object"...
0x18004ebbf  mov     r8d, eax
0x18004ebc2  mov     ecx, 4
0x18004ebc7  call    BfspLogMessage
0x18004ebcc  jmp     loc_18004ED03
0x18004ebd1  mov     rcx, [rsp+280h+var_250]
0x18004ebd6  call    cs:__imp_BcdCloseObject
0x18004ebdc  mov     ecx, cs:dword_1800A453C
0x18004ebe2  bts     ecx, 0Bh
0x18004ebe6  mov     [rsp+280h+var_250], r14
0x18004ebeb  mov     cs:dword_1800A453C, ecx
0x18004ebf1  mov     dword ptr [rsp+280h+var_248], 1
0x18004ebf9  mov     dword ptr [rsp+280h+var_248+4], 10200005h
0x18004ec01  call    BfspGetBcdCopyFlags
0x18004ec06  mov     r8d, eax
0x18004ec09  lea     rdx, [rsp+280h+var_248]
0x18004ec0e  mov     r9, rdi
0x18004ec11  mov     rcx, rsi
0x18004ec14  call    cs:__imp_BcdCopyObjects
0x18004ec1a  mov     ebx, eax
0x18004ec1c  test    eax, eax
0x18004ec1e  jns     short loc_18004EC29
0x18004ec20  lea     rdx, aFailedToCopyMe; "Failed to copy memtest object. Status ="...
0x18004ec27  jmp     short loc_18004EBBF
0x18004ec29  mov     r9, r15
0x18004ec2c  mov     r8, r15
0x18004ec2f  mov     rdx, rdi
0x18004ec32  mov     rcx, rsi
0x18004ec35  call    BfspSetObjectDeviceAndPath
0x18004ec3a  mov     ebx, eax
0x18004ec3c  test    eax, eax
0x18004ec3e  js      loc_18004ED03
0x18004ec44  cmp     cs:byte_1800A4538, r14b
0x18004ec4b  jz      loc_18004ECDF
0x18004ec51  lea     r8, [rsp+280h+var_250]
0x18004ec56  mov     rdx, r15
0x18004ec59  mov     rcx, rdi
0x18004ec5c  call    cs:__imp_BcdOpenObject
0x18004ec62  mov     ebx, eax
0x18004ec64  test    eax, eax
0x18004ec66  jns     short loc_18004EC74
0x18004ec68  lea     rdx, aFailedToGetAHa; "Failed to get a handle to the memtest o"...
0x18004ec6f  jmp     loc_18004EBBF
0x18004ec74  lea     rax, aMemtestEfi; "memtest.efi"
0x18004ec7b  mov     edx, 104h; BufferCount
0x18004ec80  lea     r9, aEfiMicrosoftBo_1; "\\EFI\\Microsoft\\Boot\\"
0x18004ec87  mov     [rsp+280h+var_260], rax
0x18004ec8c  lea     r8, aSS_0; "%s%s"
0x18004ec93  lea     rcx, [rsp+280h+Buffer]; Buffer
0x18004ec98  call    swprintf_s
0x18004ec9d  lea     rax, [rsp+280h+Buffer]
0x18004eca2  or      r9, 0FFFFFFFFFFFFFFFFh
0x18004eca6  inc     r9
0x18004eca9  cmp     [rax+r9*2], r14w
0x18004ecae  jnz     short loc_18004ECA6
0x18004ecb0  mov     rcx, [rsp+280h+var_250]
0x18004ecb5  lea     r9d, ds:2[r9*2]
0x18004ecbd  lea     r8, [rsp+280h+Buffer]
0x18004ecc2  mov     edx, 12000002h
0x18004ecc7  call    cs:__imp_BcdSetElementData
0x18004eccd  mov     ebx, eax
0x18004eccf  test    eax, eax
0x18004ecd1  jns     short loc_18004ECDF
0x18004ecd3  lea     rdx, aFailedToSetEle_1; "Failed to set element application path."...
0x18004ecda  jmp     loc_18004EBBF
0x18004ecdf  mov     rdx, r15
0x18004ece2  mov     rcx, rdi
0x18004ece5  call    BfspSetLocale
0x18004ecea  mov     ebx, eax
0x18004ecec  test    eax, eax
0x18004ecee  js      short loc_18004ED03
0x18004ecf0  mov     r9, r15
0x18004ecf3  mov     r8, r15
0x18004ecf6  mov     rdx, rdi
0x18004ecf9  mov     rcx, rsi
0x18004ecfc  call    BfspSetObjectStringElements
0x18004ed01  mov     ebx, eax
0x18004ed03  mov     eax, ebx
0x18004ed05  mov     rcx, [rbp+180h+var_30]
0x18004ed0c  xor     rcx, rsp; StackCookie
0x18004ed0f  call    __security_check_cookie
0x18004ed14  mov     rbx, [rsp+280h+arg_10]
0x18004ed1c  add     rsp, 260h
0x18004ed23  pop     r15
0x18004ed25  pop     r14
0x18004ed27  pop     rdi
0x18004ed28  pop     rsi
0x18004ed29  pop     rbp
0x18004ed2a  retn
```
