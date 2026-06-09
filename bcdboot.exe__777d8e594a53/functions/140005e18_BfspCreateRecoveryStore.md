# BfspCreateRecoveryStore

- ea: `0x140005e18`
- end: `0x140005fbd`
- name: `BfspCreateRecoveryStore`
- size: `421`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004080`

## callees

- `0x1400052bc`
- `0x14000583c`
- `0x140005e18`
- `0x14000e628`
- `0x14001a8c4`
- `0x14001a964`
- `0x14001bb00`
- `0x140026650`

## import_xrefs

- `msvcrt!swprintf_s` at `0x140005e94`
- `msvcrt!swprintf_s` at `0x140005e94`
- `ntdll!RtlInitUnicodeString` at `0x140005ea4`
- `ntdll!RtlInitUnicodeString` at `0x140005ea4`

## string_xrefs

- `0x140005eb6`: `Opening recovery store from %ws`
- `0x140005f5f`: `Failed to create create {bootmgr} object. Status = [%x]`
- `0x140005f20`: `Failed to create a new recovery store. Status = [%x]`
- `0x140005ee7`: `Failed to open recovery store. Status = [%x]`
- `0x140005f3f`: `Failed to create create general objects. Status = [%x]`

## pseudocode

```c
__int64 __fastcall BfspCreateRecoveryStore(__int64 a1, int a2)
{
  __int64 v4; // r8
  int v5; // eax
  int GeneralObjects; // ebx
  const wchar_t *v7; // rdx
  __int64 v8; // rdi
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  DestinationString = 0;
  v11 = 0;
  if ( !byte_14003F8F8 )
    return 0;
  dword_14003F8FC = a2 | 0x110;
  swprintf_s(Buffer, 0x104u, L"%s%s", Src, L"\\EFI\\Microsoft\\Recovery\\BCD");
  RtlInitUnicodeString(&DestinationString, Buffer);
  BfspLogMessage(2, L"Opening recovery store from %ws", Buffer);
  v5 = BiOpenStoreWithHash(&DestinationString, 0, v4, &v11);
  GeneralObjects = v5;
  if ( v5 == -1073741275 || v5 == -1073741809 )
  {
    BfspLogMessage(2, L"Creating new recovery store %ws", Buffer);
    GeneralObjects = BcdCreateStoreEx(&DestinationString, v9, &v11);
    if ( GeneralObjects < 0 )
    {
      v7 = L"Failed to create a new recovery store. Status = [%x]";
      goto LABEL_7;
    }
  }
  else if ( v5 < 0 )
  {
    v7 = L"Failed to open recovery store. Status = [%x]";
LABEL_7:
    v8 = v11;
LABEL_16:
    BfspLogMessage(4, v7, (unsigned int)GeneralObjects);
LABEL_17:
    if ( v8 )
      BcdCloseStore(v8);
    return (unsigned int)GeneralObjects;
  }
  v8 = v11;
  GeneralObjects = BfspCreateGeneralObjects(a1, v11);
  if ( GeneralObjects < 0 )
  {
    BfspLogMessage(4, L"Failed to create create general objects. Status = [%x]", (unsigned int)GeneralObjects);
    goto LABEL_17;
  }
  GeneralObjects = BfspCreateBootmgrObject(a1, v8, 0, 0);
  if ( GeneralObjects < 0 )
  {
    BfspLogMessage(4, L"Failed to create create {bootmgr} object. Status = [%x]", (unsigned int)GeneralObjects);
    goto LABEL_17;
  }
  v10 = BcdCloseStore(v8);
  v8 = 0;
  GeneralObjects = v10;
  if ( v10 < 0 )
  {
    v7 = L"Failed to close recovery store. Status = [%x]";
    goto LABEL_16;
  }
  return (unsigned int)GeneralObjects;
}

```

## disassembly

```asm
0x140005e18  mov     [rsp-8+arg_10], rbx
0x140005e1d  push    rbp
0x140005e1e  push    rsi
0x140005e1f  push    rdi
0x140005e20  lea     rbp, [rsp-170h]
0x140005e28  sub     rsp, 270h
0x140005e2f  mov     rax, cs:__security_cookie
0x140005e36  xor     rax, rsp
0x140005e39  mov     [rbp+180h+var_20], rax
0x140005e40  cmp     cs:byte_14003F8F8, 0
0x140005e47  xorps   xmm0, xmm0
0x140005e4a  movups  xmmword ptr [rsp+280h+DestinationString.Length], xmm0
0x140005e4f  mov     rsi, rcx
0x140005e52  mov     [rsp+280h+var_250], 0
0x140005e5b  jnz     short loc_140005E64
0x140005e5d  xor     eax, eax
0x140005e5f  jmp     loc_140005F9B
0x140005e64  mov     r9, cs:Src
0x140005e6b  lea     rax, aEfiMicrosoftRe_0; "\\EFI\\Microsoft\\Recovery\\BCD"
0x140005e72  or      edx, 110h
0x140005e78  mov     [rsp+280h+var_260], rax
0x140005e7d  mov     cs:dword_14003F8FC, edx
0x140005e83  lea     r8, aSS_0; "%s%s"
0x140005e8a  mov     edx, 104h; BufferCount
0x140005e8f  lea     rcx, [rsp+280h+Buffer]; Buffer
0x140005e94  call    cs:__imp_swprintf_s
0x140005e9a  lea     rdx, [rsp+280h+Buffer]; SourceString
0x140005e9f  lea     rcx, [rsp+280h+DestinationString]; DestinationString
0x140005ea4  call    cs:__imp_RtlInitUnicodeString
0x140005eaa  mov     edi, 2
0x140005eaf  lea     r8, [rsp+280h+Buffer]
0x140005eb4  mov     ecx, edi
0x140005eb6  lea     rdx, aOpeningRecover; "Opening recovery store from %ws"
0x140005ebd  call    BfspLogMessage
0x140005ec2  lea     r9, [rsp+280h+var_250]
0x140005ec7  xor     edx, edx
0x140005ec9  lea     rcx, [rsp+280h+DestinationString]
0x140005ece  call    BiOpenStoreWithHash
0x140005ed3  mov     ebx, eax
0x140005ed5  cmp     eax, 0C0000225h
0x140005eda  jz      short loc_140005EF8
0x140005edc  cmp     eax, 0C000000Fh
0x140005ee1  jz      short loc_140005EF8
0x140005ee3  test    eax, eax
0x140005ee5  jns     short loc_140005F29
0x140005ee7  lea     rdx, aFailedToOpenRe; "Failed to open recovery store. Status ="...
0x140005eee  mov     rdi, [rsp+280h+var_250]
0x140005ef3  jmp     loc_140005F7F
0x140005ef8  lea     r8, [rsp+280h+Buffer]
0x140005efd  mov     ecx, edi
0x140005eff  lea     rdx, aCreatingNewRec; "Creating new recovery store %ws"
0x140005f06  call    BfspLogMessage
0x140005f0b  lea     r8, [rsp+280h+var_250]
0x140005f10  lea     rcx, [rsp+280h+DestinationString]
0x140005f15  call    BcdCreateStoreEx
0x140005f1a  mov     ebx, eax
0x140005f1c  test    eax, eax
0x140005f1e  jns     short loc_140005F29
0x140005f20  lea     rdx, aFailedToCreate_5; "Failed to create a new recovery store. "...
0x140005f27  jmp     short loc_140005EEE
0x140005f29  mov     rdi, [rsp+280h+var_250]
0x140005f2e  mov     rcx, rsi
0x140005f31  mov     rdx, rdi
0x140005f34  call    BfspCreateGeneralObjects
0x140005f39  mov     ebx, eax
0x140005f3b  test    eax, eax
0x140005f3d  jns     short loc_140005F48
0x140005f3f  lea     rdx, aFailedToCreate_7; "Failed to create create general objects"...
0x140005f46  jmp     short loc_140005F7F
0x140005f48  xor     r9d, r9d
0x140005f4b  xor     r8d, r8d
0x140005f4e  mov     rdx, rdi
0x140005f51  mov     rcx, rsi
0x140005f54  call    BfspCreateBootmgrObject
0x140005f59  mov     ebx, eax
0x140005f5b  test    eax, eax
0x140005f5d  jns     short loc_140005F68
0x140005f5f  lea     rdx, aFailedToCreate_1; "Failed to create create {bootmgr} objec"...
0x140005f66  jmp     short loc_140005F7F
0x140005f68  mov     rcx, rdi
0x140005f6b  call    BcdCloseStore
0x140005f70  xor     edi, edi
0x140005f72  mov     ebx, eax
0x140005f74  test    eax, eax
0x140005f76  jns     short loc_140005F99
0x140005f78  lea     rdx, aFailedToCloseR; "Failed to close recovery store. Status "...
0x140005f7f  mov     ecx, 4
0x140005f84  mov     r8d, ebx
0x140005f87  call    BfspLogMessage
0x140005f8c  test    rdi, rdi
0x140005f8f  jz      short loc_140005F99
0x140005f91  mov     rcx, rdi
0x140005f94  call    BcdCloseStore
0x140005f99  mov     eax, ebx
0x140005f9b  mov     rcx, [rbp+180h+var_20]
0x140005fa2  xor     rcx, rsp; StackCookie
0x140005fa5  call    __security_check_cookie
0x140005faa  mov     rbx, [rsp+280h+arg_10]
0x140005fb2  add     rsp, 270h
0x140005fb9  pop     rdi
0x140005fba  pop     rsi
0x140005fbb  pop     rbp
0x140005fbc  retn
```
