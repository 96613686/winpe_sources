# BiDeleteElement

- ea: `0x140019990`
- end: `0x140019bb1`
- name: `BiDeleteElement`
- size: `545`
- prototype: `__int64 __fastcall(__int64, unsigned int, char)`
- caller_count: `8`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x140004a60`
- `0x140004e20`
- `0x1400052bc`
- `0x14000619c`
- `0x14001474c`
- `0x140018b54`
- `0x1400244fc`
- `0x140024cf0`

## callees

- `0x1400133e4`
- `0x140019990`
- `0x14001ae94`
- `0x14001c014`
- `0x14001c088`
- `0x14001c6e4`
- `0x14001e5e4`
- `0x14001ec14`
- `0x14001f980`
- `0x1400214ec`
- `0x140026650`

## import_xrefs

- `msvcrt!_ultow_s` at `0x140019abe`
- `msvcrt!_ultow_s` at `0x140019abe`

## string_xrefs

- `0x1400199f5`: `BiDeleteElement: Failed to acquire BCD sync mutant. Status: %x`
- `0x140019a61`: `Failed to filter delete element %08x. Status: %x`
- `0x140019a98`: `Failed to open key for all object's elements. Status: %x`
- `0x140019afa`: `Failed to open element %ws key for delete. Status: %x`
- `0x140019b34`: `Failed to open element %ws key for delete. Status: %x`

## pseudocode

```c
__int64 __fastcall BiDeleteElement(__int64 a1, unsigned int a2, char a3)
{
  unsigned int v6; // r15d
  NTSTATUS v7; // eax
  int v8; // ebx
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  HANDLE v12; // r14
  int v13; // eax
  HANDLE v14; // rdi
  int v15; // eax
  unsigned int v17; // [rsp+30h] [rbp-50h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-48h] BYREF
  HANDLE v19; // [rsp+40h] [rbp-40h] BYREF
  wchar_t Buffer[24]; // [rsp+48h] [rbp-38h] BYREF

  v17 = a2;
  v6 = 2;
  BiLogMessage(2, L"Deleting element %08x", a2);
  v7 = BiAcquireBcdSyncMutant(a1 & 1);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v19 = 0;
    Handle = 0;
    if ( a3 && (v9 = BiFilterDoOperation(2, a1, a2, 0, 0), v8 = v9, v9 < 0) )
    {
      if ( v9 == -1069350910 )
        BiLogMessage(4, L"Deleting element %08x blocked by secure boot policy.", a2);
      else
        BiLogMessage(4, L"Failed to filter delete element %08x. Status: %x", a2, (unsigned int)v9);
    }
    else
    {
      v11 = BiOpenKey(a1, L"Elements", 131097, &v19);
      v12 = v19;
      v8 = v11;
      if ( v11 >= 0 )
      {
        if ( _ultow_s(a2, Buffer, 0x16u, 16) )
        {
          v8 = -1073741823;
        }
        else
        {
          v13 = BiOpenKey(v12, Buffer, 0x10000, &Handle);
          if ( v13 >= 0 )
          {
            v14 = Handle;
            v15 = BiDeleteKey(Handle);
            v8 = v15;
            if ( v15 >= 0 )
              v14 = 0;
            else
              BiLogMessage(4, L"Failed to open element %ws key for delete. Status: %x", Buffer, (unsigned int)v15);
          }
          else
          {
            if ( v13 != -1073741772 )
              v6 = 4;
            BiLogMessage(v6, L"Failed to open element %ws key for delete. Status: %x", Buffer, (unsigned int)v13);
            v14 = Handle;
            v8 = -1073741275;
          }
          if ( v14 )
            BiCloseKey(v14);
        }
      }
      else
      {
        BiLogMessage(4, L"Failed to open key for all object's elements. Status: %x", (unsigned int)v11);
      }
      if ( v12 )
        BiCloseKey(v12);
      if ( v8 >= 0 && (unsigned __int8)BiIsLinkedToFirmwareVariable(a1, &v17) )
        BiSetFirmwareModifiedFromObject(a1);
    }
    LOBYTE(v10) = a1 & 1;
    BiReleaseBcdSyncMutant(v10);
  }
  else
  {
    BiLogMessage(4, L"BiDeleteElement: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140019990  mov     [rsp-28h+arg_10], rbx
0x140019995  mov     [rsp-28h+arg_18], rsi
0x14001999a  push    rbp
0x14001999b  push    rdi
0x14001999c  push    r12
0x14001999e  push    r14
0x1400199a0  push    r15
0x1400199a2  mov     rbp, rsp
0x1400199a5  sub     rsp, 80h
0x1400199ac  mov     rax, cs:__security_cookie
0x1400199b3  xor     rax, rsp
0x1400199b6  mov     [rbp+var_8], rax
0x1400199ba  mov     r14b, r8b
0x1400199bd  mov     [rbp+var_50], edx
0x1400199c0  mov     r8d, edx
0x1400199c3  mov     edi, edx
0x1400199c5  mov     rsi, rcx
0x1400199c8  lea     rdx, aDeletingElemen; "Deleting element %08x"
0x1400199cf  mov     r15d, 2
0x1400199d5  mov     ecx, r15d
0x1400199d8  call    BiLogMessage
0x1400199dd  mov     r12b, sil
0x1400199e0  and     r12b, 1
0x1400199e4  mov     cl, r12b
0x1400199e7  call    BiAcquireBcdSyncMutant
0x1400199ec  mov     ebx, eax
0x1400199ee  test    eax, eax
0x1400199f0  jns     short loc_140019A0A
0x1400199f2  mov     r8d, eax
0x1400199f5  lea     rdx, aBideleteelemen; "BiDeleteElement: Failed to acquire BCD "...
0x1400199fc  lea     ecx, [r15+2]
0x140019a00  call    BiLogMessage
0x140019a05  jmp     loc_140019B87
0x140019a0a  mov     [rbp+var_40], 0
0x140019a12  mov     [rbp+Handle], 0
0x140019a1a  test    r14b, r14b
0x140019a1d  jz      short loc_140019A72
0x140019a1f  xor     r9d, r9d
0x140019a22  mov     [rsp+80h+var_60], 0
0x140019a2a  mov     r8d, edi
0x140019a2d  mov     rdx, rsi
0x140019a30  mov     ecx, r15d
0x140019a33  call    BiFilterDoOperation
0x140019a38  mov     ebx, eax
0x140019a3a  test    eax, eax
0x140019a3c  jns     short loc_140019A72
0x140019a3e  mov     r8d, edi
0x140019a41  mov     ecx, 4
0x140019a46  cmp     eax, 0C0430002h
0x140019a4b  jnz     short loc_140019A5E
0x140019a4d  lea     rdx, aDeletingElemen_0; "Deleting element %08x blocked by secure"...
0x140019a54  call    BiLogMessage
0x140019a59  jmp     loc_140019B7F
0x140019a5e  mov     r9d, eax
0x140019a61  lea     rdx, aFailedToFilter; "Failed to filter delete element %08x. S"...
0x140019a68  call    BiLogMessage
0x140019a6d  jmp     loc_140019B7F
0x140019a72  lea     r9, [rbp+var_40]
0x140019a76  mov     r8d, 20019h
0x140019a7c  lea     rdx, aElements; "Elements"
0x140019a83  mov     rcx, rsi
0x140019a86  call    BiOpenKey
0x140019a8b  mov     r14, [rbp+var_40]
0x140019a8f  mov     ebx, eax
0x140019a91  test    eax, eax
0x140019a93  jns     short loc_140019AAE
0x140019a95  mov     r8d, eax
0x140019a98  lea     rdx, aFailedToOpenKe; "Failed to open key for all object's ele"...
0x140019a9f  mov     ecx, 4
0x140019aa4  call    BiLogMessage
0x140019aa9  jmp     loc_140019B56
0x140019aae  mov     r9d, 10h; Radix
0x140019ab4  lea     rdx, [rbp+Buffer]; Buffer
0x140019ab8  mov     ecx, edi; Value
0x140019aba  lea     r8d, [r9+6]; BufferCount
0x140019abe  call    cs:__imp__ultow_s
0x140019ac4  test    eax, eax
0x140019ac6  jz      short loc_140019AD2
0x140019ac8  mov     ebx, 0C0000001h
0x140019acd  jmp     loc_140019B56
0x140019ad2  lea     r9, [rbp+Handle]
0x140019ad6  mov     r8d, 10000h
0x140019adc  lea     rdx, [rbp+Buffer]
0x140019ae0  mov     rcx, r14
0x140019ae3  call    BiOpenKey
0x140019ae8  test    eax, eax
0x140019aea  jns     short loc_140019B1B
0x140019aec  mov     ecx, 4
0x140019af1  lea     r8, [rbp+Buffer]
0x140019af5  cmp     eax, 0C0000034h
0x140019afa  lea     rdx, aFailedToOpenEl; "Failed to open element %ws key for dele"...
0x140019b01  mov     r9d, eax
0x140019b04  cmovnz  r15d, ecx
0x140019b08  mov     ecx, r15d
0x140019b0b  call    BiLogMessage
0x140019b10  mov     rdi, [rbp+Handle]
0x140019b14  mov     ebx, 0C0000225h
0x140019b19  jmp     short loc_140019B49
0x140019b1b  mov     rdi, [rbp+Handle]
0x140019b1f  mov     rcx, rdi
0x140019b22  call    BiDeleteKey
0x140019b27  mov     ebx, eax
0x140019b29  test    eax, eax
0x140019b2b  jns     short loc_140019B47
0x140019b2d  mov     r9d, eax
0x140019b30  lea     r8, [rbp+Buffer]
0x140019b34  lea     rdx, aFailedToOpenEl; "Failed to open element %ws key for dele"...
0x140019b3b  mov     ecx, 4
0x140019b40  call    BiLogMessage
0x140019b45  jmp     short loc_140019B49
0x140019b47  xor     edi, edi
0x140019b49  test    rdi, rdi
0x140019b4c  jz      short loc_140019B56
0x140019b4e  mov     rcx, rdi; Handle
0x140019b51  call    BiCloseKey
0x140019b56  test    r14, r14
0x140019b59  jz      short loc_140019B63
0x140019b5b  mov     rcx, r14; Handle
0x140019b5e  call    BiCloseKey
0x140019b63  test    ebx, ebx
0x140019b65  js      short loc_140019B7F
0x140019b67  lea     rdx, [rbp+var_50]
0x140019b6b  mov     rcx, rsi
0x140019b6e  call    BiIsLinkedToFirmwareVariable
0x140019b73  test    al, al
0x140019b75  jz      short loc_140019B7F
0x140019b77  mov     rcx, rsi
0x140019b7a  call    BiSetFirmwareModifiedFromObject
0x140019b7f  mov     cl, r12b
0x140019b82  call    BiReleaseBcdSyncMutant
0x140019b87  mov     eax, ebx
0x140019b89  mov     rcx, [rbp+var_8]
0x140019b8d  xor     rcx, rsp; StackCookie
0x140019b90  call    __security_check_cookie
0x140019b95  lea     r11, [rsp+80h+var_s0]
0x140019b9d  mov     rbx, [r11+40h]
0x140019ba1  mov     rsi, [r11+48h]
0x140019ba5  mov     rsp, r11
0x140019ba8  pop     r15
0x140019baa  pop     r14
0x140019bac  pop     r12
0x140019bae  pop     rdi
0x140019baf  pop     rbp
0x140019bb0  retn
```
