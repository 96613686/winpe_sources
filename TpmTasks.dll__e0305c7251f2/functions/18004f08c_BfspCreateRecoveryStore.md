# BfspCreateRecoveryStore

- ea: `0x18004f08c`
- end: `0x18004f23d`
- name: `BfspCreateRecoveryStore`
- size: `433`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004d7e4`

## callees

- `0x1800078b0`
- `0x180008724`
- `0x18004cdd4`
- `0x18004e544`
- `0x18004ea7c`
- `0x18004f08c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18004f11a`
- `ntdll!RtlInitUnicodeString` at `0x18004f11a`
- `bcd!BcdOpenStoreFromFile` at `0x18004f140`
- `bcd!BcdOpenStoreFromFile` at `0x18004f140`
- `bcd!BcdCloseStore` at `0x18004f1de`
- `bcd!BcdCloseStore` at `0x18004f211`
- `bcd!BcdCloseStore` at `0x18004f1de`
- `bcd!BcdCloseStore` at `0x18004f211`
- `bcd!BcdCreateStore` at `0x18004f186`
- `bcd!BcdCreateStore` at `0x18004f186`

## string_xrefs

- `0x18004f12a`: `Opening recovery store from %ws`
- `0x18004f1d0`: `Failed to create create {bootmgr} object. Status = [%x]`
- `0x18004f192`: `Failed to create a new recovery store. Status = [%x]`
- `0x18004f1ae`: `Failed to create create general objects. Status = [%x]`
- `0x18004f15a`: `Failed to open recovery store. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCreateRecoveryStore(__int64 a1, int a2)
{
  int v4; // eax
  int GeneralObjects; // ebx
  int v6; // eax
  __int64 v7; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  DestinationString = 0;
  v7 = 0;
  if ( !byte_1800A4538 )
    return 0;
  dword_1800A453C = a2 | 0x110;
  swprintf_s(Buffer, 0x104u, L"%s%s", Src, L"\\EFI\\Microsoft\\Recovery\\BCD");
  RtlInitUnicodeString(&DestinationString, Buffer);
  BfspLogMessage(2, L"Opening recovery store from %ws", Buffer);
  v4 = BcdOpenStoreFromFile(&DestinationString, &v7);
  GeneralObjects = v4;
  if ( v4 == -1073741275 || v4 == -1073741809 )
  {
    BfspLogMessage(2, L"Creating new recovery store %ws", Buffer);
    GeneralObjects = BcdCreateStore(&DestinationString, &v7);
    if ( GeneralObjects < 0 )
    {
      BfspLogMessage(4, L"Failed to create a new recovery store. Status = [%x]", (unsigned int)GeneralObjects);
      goto LABEL_15;
    }
  }
  else if ( v4 < 0 )
  {
    BfspLogMessage(4, L"Failed to open recovery store. Status = [%x]", (unsigned int)v4);
    goto LABEL_15;
  }
  GeneralObjects = BfspCreateGeneralObjects(a1, v7);
  if ( GeneralObjects < 0 )
  {
    BfspLogMessage(4, L"Failed to create create general objects. Status = [%x]", (unsigned int)GeneralObjects);
    goto LABEL_15;
  }
  GeneralObjects = BfspCreateBootmgrObject(a1, v7, 0, 0);
  if ( GeneralObjects < 0 )
  {
    BfspLogMessage(4, L"Failed to create create {bootmgr} object. Status = [%x]", (unsigned int)GeneralObjects);
    goto LABEL_15;
  }
  v6 = BcdCloseStore(v7);
  v7 = 0;
  GeneralObjects = v6;
  if ( v6 < 0 )
  {
    BfspLogMessage(4, L"Failed to close recovery store. Status = [%x]", (unsigned int)v6);
LABEL_15:
    if ( v7 )
      BcdCloseStore(v7);
  }
  return (unsigned int)GeneralObjects;
}

```

## disassembly

```asm
0x18004f08c  mov     [rsp-8+arg_10], rbx
0x18004f091  mov     [rsp-8+arg_18], rdi
0x18004f096  push    rbp
0x18004f097  lea     rbp, [rsp-170h]
0x18004f09f  sub     rsp, 270h
0x18004f0a6  mov     rax, cs:__security_cookie
0x18004f0ad  xor     rax, rsp
0x18004f0b0  mov     [rbp+170h+var_10], rax
0x18004f0b7  cmp     cs:byte_1800A4538, 0
0x18004f0be  xorps   xmm0, xmm0
0x18004f0c1  movups  xmmword ptr [rsp+270h+DestinationString.Length], xmm0
0x18004f0c6  mov     rdi, rcx
0x18004f0c9  mov     [rsp+270h+var_240], 0
0x18004f0d2  jnz     short loc_18004F0DB
0x18004f0d4  xor     eax, eax
0x18004f0d6  jmp     loc_18004F219
0x18004f0db  mov     r9, cs:Src
0x18004f0e2  lea     rax, aEfiMicrosoftRe_0; "\\EFI\\Microsoft\\Recovery\\BCD"
0x18004f0e9  or      edx, 110h
0x18004f0ef  mov     [rsp+270h+var_250], rax
0x18004f0f4  mov     cs:dword_1800A453C, edx
0x18004f0fa  lea     r8, aSS_0; "%s%s"
0x18004f101  mov     edx, 104h; BufferCount
0x18004f106  lea     rcx, [rsp+270h+Buffer]; Buffer
0x18004f10b  call    swprintf_s
0x18004f110  lea     rdx, [rsp+270h+Buffer]; SourceString
0x18004f115  lea     rcx, [rsp+270h+DestinationString]; DestinationString
0x18004f11a  call    cs:__imp_RtlInitUnicodeString
0x18004f120  lea     r8, [rsp+270h+Buffer]
0x18004f125  mov     ecx, 2
0x18004f12a  lea     rdx, aOpeningRecover; "Opening recovery store from %ws"
0x18004f131  call    BfspLogMessage
0x18004f136  lea     rdx, [rsp+270h+var_240]
0x18004f13b  lea     rcx, [rsp+270h+DestinationString]
0x18004f140  call    cs:__imp_BcdOpenStoreFromFile
0x18004f146  mov     ebx, eax
0x18004f148  cmp     eax, 0C0000225h
0x18004f14d  jz      short loc_18004F166
0x18004f14f  cmp     eax, 0C000000Fh
0x18004f154  jz      short loc_18004F166
0x18004f156  test    eax, eax
0x18004f158  jns     short loc_18004F19B
0x18004f15a  lea     rdx, aFailedToOpenRe_0; "Failed to open recovery store. Status ="...
0x18004f161  jmp     loc_18004F1FA
0x18004f166  lea     r8, [rsp+270h+Buffer]
0x18004f16b  mov     ecx, 2
0x18004f170  lea     rdx, aCreatingNewRec; "Creating new recovery store %ws"
0x18004f177  call    BfspLogMessage
0x18004f17c  lea     rdx, [rsp+270h+var_240]
0x18004f181  lea     rcx, [rsp+270h+DestinationString]
0x18004f186  call    cs:__imp_BcdCreateStore
0x18004f18c  mov     ebx, eax
0x18004f18e  test    eax, eax
0x18004f190  jns     short loc_18004F19B
0x18004f192  lea     rdx, aFailedToCreate_3; "Failed to create a new recovery store. "...
0x18004f199  jmp     short loc_18004F1FA
0x18004f19b  mov     rdx, [rsp+270h+var_240]
0x18004f1a0  mov     rcx, rdi
0x18004f1a3  call    BfspCreateGeneralObjects
0x18004f1a8  mov     ebx, eax
0x18004f1aa  test    eax, eax
0x18004f1ac  jns     short loc_18004F1B7
0x18004f1ae  lea     rdx, aFailedToCreate_5; "Failed to create create general objects"...
0x18004f1b5  jmp     short loc_18004F1FA
0x18004f1b7  mov     rdx, [rsp+270h+var_240]
0x18004f1bc  xor     r9d, r9d
0x18004f1bf  xor     r8d, r8d
0x18004f1c2  mov     rcx, rdi
0x18004f1c5  call    BfspCreateBootmgrObject
0x18004f1ca  mov     ebx, eax
0x18004f1cc  test    eax, eax
0x18004f1ce  jns     short loc_18004F1D9
0x18004f1d0  lea     rdx, aFailedToCreate_1; "Failed to create create {bootmgr} objec"...
0x18004f1d7  jmp     short loc_18004F1FA
0x18004f1d9  mov     rcx, [rsp+270h+var_240]
0x18004f1de  call    cs:__imp_BcdCloseStore
0x18004f1e4  mov     [rsp+270h+var_240], 0
0x18004f1ed  mov     ebx, eax
0x18004f1ef  test    eax, eax
0x18004f1f1  jns     short loc_18004F217
0x18004f1f3  lea     rdx, aFailedToCloseR; "Failed to close recovery store. Status "...
0x18004f1fa  mov     ecx, 4
0x18004f1ff  mov     r8d, ebx
0x18004f202  call    BfspLogMessage
0x18004f207  mov     rcx, [rsp+270h+var_240]
0x18004f20c  test    rcx, rcx
0x18004f20f  jz      short loc_18004F217
0x18004f211  call    cs:__imp_BcdCloseStore
0x18004f217  mov     eax, ebx
0x18004f219  mov     rcx, [rbp+170h+var_10]
0x18004f220  xor     rcx, rsp; StackCookie
0x18004f223  call    __security_check_cookie
0x18004f228  lea     r11, [rsp+270h+var_s0]
0x18004f230  mov     rbx, [r11+20h]
0x18004f234  mov     rdi, [r11+28h]
0x18004f238  mov     rsp, r11
0x18004f23b  pop     rbp
0x18004f23c  retn
```
