# BfspCreateMemtestObject

- ea: `0x1400058e4`
- end: `0x140005ae0`
- name: `BfspCreateMemtestObject`
- size: `508`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140007cdc`

## callees

- `0x1400058e4`
- `0x1400069e0`
- `0x1400087a8`
- `0x140008844`
- `0x140008c74`
- `0x14000e628`
- `0x140013b48`
- `0x140013ee8`
- `0x140014ec8`
- `0x140018b54`
- `0x140026650`

## import_xrefs

- `msvcrt!swprintf_s` at `0x140005a47`
- `msvcrt!swprintf_s` at `0x140005a47`

## string_xrefs

- `0x140005a88`: `Failed to set element application path. Status = [%x]`
- `0x14000596a`: `Failed to open handle to Memtest object. Status = [%x]`
- `0x1400059d0`: `Failed to copy memtest object. Status = [%x]`

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
  __int64 v10; // rax
  int v11; // eax
  HANDLE Handle; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v14[2]; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  Handle = 0;
  BfspLogMessage(2, L"Creating MemTest object.");
  v4 = BcdOpenObject(a1, &GUID_WINDOWS_MEMORY_TESTER, &Handle);
  v5 = v4;
  if ( v4 >= 0 )
  {
    BcdCloseObject(Handle);
    v6 = (unsigned int)dword_14003F8FC;
    Handle = 0;
    dword_14003F8FC |= 0x800u;
    LODWORD(v6) = dword_14003F8FC;
    v14[0] = 1;
    v14[1] = 270532613;
    BcdCopyFlags = BfspGetBcdCopyFlags(v6);
    v8 = BcdCopyObjects(a1, v14, BcdCopyFlags, a2);
    v5 = v8;
    if ( v8 >= 0 )
    {
      v5 = BfspSetObjectDeviceAndPath(a1, a2, &GUID_WINDOWS_MEMORY_TESTER, &GUID_WINDOWS_MEMORY_TESTER);
      if ( v5 >= 0 )
      {
        if ( byte_14003F8F8 )
        {
          v9 = BcdOpenObject(a2, &GUID_WINDOWS_MEMORY_TESTER, &Handle);
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
          v11 = BcdSetElementDataWithFlags((__int64)Handle, 301989890, 0, (__int64)Buffer, 2 * (int)v10 + 2);
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
0x1400058e4  mov     [rsp-8+arg_10], rbx
0x1400058e9  push    rbp
0x1400058ea  push    rsi
0x1400058eb  push    rdi
0x1400058ec  push    r14
0x1400058ee  push    r15
0x1400058f0  lea     rbp, [rsp-160h]
0x1400058f8  sub     rsp, 260h
0x1400058ff  mov     rax, cs:__security_cookie
0x140005906  xor     rax, rsp
0x140005909  mov     [rbp+180h+var_30], rax
0x140005910  xor     r14d, r14d
0x140005913  mov     rdi, rdx
0x140005916  mov     rsi, rcx
0x140005919  mov     [rsp+280h+Handle], r14
0x14000591e  lea     rdx, aCreatingMemtes; "Creating MemTest object."
0x140005925  lea     ecx, [r14+2]
0x140005929  call    BfspLogMessage
0x14000592e  lea     r15, GUID_WINDOWS_MEMORY_TESTER
0x140005935  mov     rcx, rsi
0x140005938  mov     rdx, r15
0x14000593b  lea     r8, [rsp+280h+Handle]
0x140005940  call    BcdOpenObject
0x140005945  mov     ebx, eax
0x140005947  test    eax, eax
0x140005949  jns     short loc_140005983
0x14000594b  cmp     eax, 0C0000034h
0x140005950  jnz     short loc_14000596A
0x140005952  lea     rdx, aMemoryTesterAp; "Memory Tester application not found. Sk"...
0x140005959  lea     ecx, [r14+2]
0x14000595d  call    BfspLogMessage
0x140005962  mov     ebx, r14d
0x140005965  jmp     loc_140005AB8
0x14000596a  lea     rdx, aFailedToOpenHa_0; "Failed to open handle to Memtest object"...
0x140005971  mov     r8d, eax
0x140005974  mov     ecx, 4
0x140005979  call    BfspLogMessage
0x14000597e  jmp     loc_140005AB8
0x140005983  mov     rcx, [rsp+280h+Handle]; Handle
0x140005988  call    BcdCloseObject
0x14000598d  mov     ecx, cs:dword_14003F8FC
0x140005993  bts     ecx, 0Bh
0x140005997  mov     [rsp+280h+Handle], r14
0x14000599c  mov     cs:dword_14003F8FC, ecx
0x1400059a2  mov     [rsp+280h+var_248], 1
0x1400059aa  mov     [rsp+280h+var_244], 10200005h
0x1400059b2  call    BfspGetBcdCopyFlags
0x1400059b7  mov     r8d, eax
0x1400059ba  lea     rdx, [rsp+280h+var_248]
0x1400059bf  mov     r9, rdi
0x1400059c2  mov     rcx, rsi
0x1400059c5  call    BcdCopyObjects
0x1400059ca  mov     ebx, eax
0x1400059cc  test    eax, eax
0x1400059ce  jns     short loc_1400059D9
0x1400059d0  lea     rdx, aFailedToCopyMe; "Failed to copy memtest object. Status ="...
0x1400059d7  jmp     short loc_140005971
0x1400059d9  mov     r9, r15
0x1400059dc  mov     r8, r15
0x1400059df  mov     rdx, rdi
0x1400059e2  mov     rcx, rsi
0x1400059e5  call    BfspSetObjectDeviceAndPath
0x1400059ea  mov     ebx, eax
0x1400059ec  test    eax, eax
0x1400059ee  js      loc_140005AB8
0x1400059f4  cmp     cs:byte_14003F8F8, r14b
0x1400059fb  jz      loc_140005A94
0x140005a01  lea     r8, [rsp+280h+Handle]
0x140005a06  mov     rdx, r15
0x140005a09  mov     rcx, rdi
0x140005a0c  call    BcdOpenObject
0x140005a11  mov     ebx, eax
0x140005a13  test    eax, eax
0x140005a15  jns     short loc_140005A23
0x140005a17  lea     rdx, aFailedToGetAHa; "Failed to get a handle to the memtest o"...
0x140005a1e  jmp     loc_140005971
0x140005a23  lea     rax, aMemtestEfi; "memtest.efi"
0x140005a2a  mov     edx, 104h; BufferCount
0x140005a2f  lea     r9, aEfiMicrosoftBo_1; "\\EFI\\Microsoft\\Boot\\"
0x140005a36  mov     [rsp+280h+var_260], rax
0x140005a3b  lea     r8, aSS_0; "%s%s"
0x140005a42  lea     rcx, [rsp+280h+Buffer]; Buffer
0x140005a47  call    cs:__imp_swprintf_s
0x140005a4d  lea     rcx, [rsp+280h+Buffer]
0x140005a52  or      rax, 0FFFFFFFFFFFFFFFFh
0x140005a56  inc     rax
0x140005a59  cmp     [rcx+rax*2], r14w
0x140005a5e  jnz     short loc_140005A56
0x140005a60  mov     rcx, [rsp+280h+Handle]
0x140005a65  lea     eax, ds:2[rax*2]
0x140005a6c  lea     r9, [rsp+280h+Buffer]
0x140005a71  mov     dword ptr [rsp+280h+var_260], eax
0x140005a75  xor     r8d, r8d
0x140005a78  mov     edx, 12000002h
0x140005a7d  call    BcdSetElementDataWithFlags
0x140005a82  mov     ebx, eax
0x140005a84  test    eax, eax
0x140005a86  jns     short loc_140005A94
0x140005a88  lea     rdx, aFailedToSetEle_1; "Failed to set element application path."...
0x140005a8f  jmp     loc_140005971
0x140005a94  mov     rdx, r15
0x140005a97  mov     rcx, rdi
0x140005a9a  call    BfspSetLocale
0x140005a9f  mov     ebx, eax
0x140005aa1  test    eax, eax
0x140005aa3  js      short loc_140005AB8
0x140005aa5  mov     r9, r15
0x140005aa8  mov     r8, r15
0x140005aab  mov     rdx, rdi
0x140005aae  mov     rcx, rsi
0x140005ab1  call    BfspSetObjectStringElements
0x140005ab6  mov     ebx, eax
0x140005ab8  mov     eax, ebx
0x140005aba  mov     rcx, [rbp+180h+var_30]
0x140005ac1  xor     rcx, rsp; StackCookie
0x140005ac4  call    __security_check_cookie
0x140005ac9  mov     rbx, [rsp+280h+arg_10]
0x140005ad1  add     rsp, 260h
0x140005ad8  pop     r15
0x140005ada  pop     r14
0x140005adc  pop     rdi
0x140005add  pop     rsi
0x140005ade  pop     rbp
0x140005adf  retn
```
