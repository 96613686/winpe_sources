# BiAddStoreFromFile

- ea: `0x14001af00`
- end: `0x14001b1ec`
- name: `BiAddStoreFromFile`
- size: `748`
- prototype: `__int64 __fastcall(__int64, char, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14001a964`
- `0x14001b764`
- `0x14001bb00`

## callees

- `0x1400133e4`
- `0x14001af00`
- `0x14001e5e4`
- `0x14001e730`
- `0x14001ed70`
- `0x14001f570`
- `0x14001f980`
- `0x14001fc5c`
- `0x14001fe24`
- `0x140026650`

## import_xrefs

- `msvcrt!swprintf_s` at `0x14001af5b`
- `msvcrt!swprintf_s` at `0x14001af5b`

## string_xrefs

- `0x14001b163`: `Failed to open description key for store. Store: %s StoreKey: %ws Status: %x`
- `0x14001afb9`: `Failed to find a key to load store %s. Last attempted key: %ws`

## pseudocode

```c
__int64 __fastcall BiAddStoreFromFile(__int64 a1, char a2, __int64 a3, _QWORD *a4)
{
  unsigned int v7; // r14d
  unsigned int v8; // edi
  int Hive; // eax
  unsigned int v10; // ebx
  __int64 v12; // rcx
  int v13; // eax
  const wchar_t *v14; // rdx
  int v15; // eax
  HANDLE v16; // r14
  int v17; // eax
  __int64 v18; // [rsp+20h] [rbp-50h]
  __int64 v19; // [rsp+20h] [rbp-50h]
  HANDLE v20; // [rsp+38h] [rbp-38h] BYREF
  HANDLE v21; // [rsp+40h] [rbp-30h] BYREF
  wchar_t Buffer[12]; // [rsp+48h] [rbp-28h] BYREF

  v21 = 0;
  v20 = 0;
  if ( (a2 & 0x20) != 0 )
  {
LABEL_9:
    BiLogMessage(4, L"Failed to find a key to load store %s. Last attempted key: %ws", a1 + 12, Buffer);
    return (unsigned int)-1073741823;
  }
  v7 = 0;
  v8 = 0;
  while ( 1 )
  {
    swprintf_s(Buffer, 0xCu, L"BCD%08d", v8);
    Hive = BiLoadHive(Buffer);
    v10 = Hive;
    if ( Hive >= 0 )
      break;
    if ( Hive != -1073741790 )
    {
      v12 = 2;
      if ( Hive != -1073741809 )
        v12 = 4;
      BiLogMessage(v12, L"Failed to load hive into key %ws from %s. Status: %x", Buffer, a1 + 12, Hive);
      return v10;
    }
    ++v7;
    if ( (unsigned __int8)BiDoesHiveKeyExist(Buffer) )
      v7 = 0;
    if ( v7 >= 0xA )
    {
      BiLogMessage(4, L"Too many unexplained failures. File: %s Last status: %x", a1 + 12, 3221225506LL);
      return v10;
    }
    if ( ++v8 > 0x5F5E0FF )
      goto LABEL_9;
  }
  BiLogMessage(2, L"Loaded hive at BCD%08d", v8);
  if ( (a2 & 1) == 0 )
    goto LABEL_21;
  v13 = BiCreateKey(0, L"Objects", 131097, 0, &v20, 0);
  v10 = v13;
  if ( v13 >= 0 )
  {
    BiCloseKey(v20);
    v20 = 0;
    v13 = BiCreateKey(0, L"Description", 131097, 0, &v20, 0);
    v10 = v13;
    if ( v13 < 0 )
    {
      v14 = L"Failed to initialize description key for store. Store: %s StoreKey: %ws Status: %x";
      goto LABEL_18;
    }
LABEL_21:
    v15 = BiOpenKey(0, L"Description", 131103, &v21);
    v16 = v21;
    v10 = v15;
    if ( v15 >= 0 )
    {
      v17 = BiSetRegistryValue(v21, L"KeyName", 0, 1, Buffer, 24);
      v10 = v17;
      if ( v17 >= 0 )
      {
        *a4 = 0;
      }
      else
      {
        LODWORD(v19) = v17;
        BiLogMessage(
          4,
          L"Failed to set description key value. Store: %s StoreKey: %ws Status: %x",
          a1 + 12,
          Buffer,
          v19);
      }
    }
    else
    {
      if ( v15 == -1073741772 )
      {
        BiLogMessage(4, L"A valid store must have a description key.");
        v10 = -1073741476;
      }
      LODWORD(v18) = v10;
      BiLogMessage(
        4,
        L"Failed to open description key for store. Store: %s StoreKey: %ws Status: %x",
        a1 + 12,
        Buffer,
        v18);
    }
    if ( v16 )
      BiCloseKey(v16);
    goto LABEL_30;
  }
  v14 = L"Failed to initialize objects key for store. Store: %s StoreKey: %ws Status: %x";
LABEL_18:
  LODWORD(v18) = v13;
  BiLogMessage(4, v14, a1 + 12, Buffer, v18);
LABEL_30:
  if ( v20 )
    BiCloseKey(v20);
  return v10;
}

```

## disassembly

```asm
0x14001af00  mov     [rsp-38h+arg_8], rbx
0x14001af05  push    rbp
0x14001af06  push    rsi
0x14001af07  push    rdi
0x14001af08  push    r12
0x14001af0a  push    r13
0x14001af0c  push    r14
0x14001af0e  push    r15
0x14001af10  mov     rbp, rsp
0x14001af13  sub     rsp, 70h
0x14001af17  mov     rax, cs:__security_cookie
0x14001af1e  xor     rax, rsp
0x14001af21  mov     [rbp+var_10], rax
0x14001af25  xor     r13d, r13d
0x14001af28  mov     r12, r9
0x14001af2b  mov     [rbp+var_30], r13
0x14001af2f  mov     r15d, edx
0x14001af32  mov     [rbp+Handle], r13
0x14001af36  mov     rsi, rcx
0x14001af39  mov     [rbp+var_38], r13
0x14001af3d  test    dl, 20h
0x14001af40  jnz     short loc_14001AFAC
0x14001af42  mov     r14d, r13d
0x14001af45  mov     edi, r13d
0x14001af48  mov     r9d, edi
0x14001af4b  lea     r8, aBcd08d; "BCD%08d"
0x14001af52  mov     edx, 0Ch; BufferCount
0x14001af57  lea     rcx, [rbp+Buffer]; Buffer
0x14001af5b  call    cs:__imp_swprintf_s
0x14001af61  lea     r8, [rbp+Handle]
0x14001af65  mov     rdx, rsi
0x14001af68  lea     rcx, [rbp+Buffer]; SourceString
0x14001af6c  call    BiLoadHive
0x14001af71  mov     ebx, eax
0x14001af73  test    eax, eax
0x14001af75  jns     loc_14001B06D
0x14001af7b  cmp     eax, 0C0000022h
0x14001af80  jnz     loc_14001B040
0x14001af86  lea     rcx, [rbp+Buffer]
0x14001af8a  call    BiDoesHiveKeyExist
0x14001af8f  inc     r14d
0x14001af92  test    al, al
0x14001af94  cmovnz  r14d, r13d
0x14001af98  cmp     r14d, 0Ah
0x14001af9c  jnb     loc_14001B023
0x14001afa2  inc     edi
0x14001afa4  cmp     edi, 5F5E0FFh
0x14001afaa  jbe     short loc_14001AF48
0x14001afac  lea     r8, [rsi+0Ch]
0x14001afb0  mov     ecx, 4
0x14001afb5  lea     r9, [rbp+Buffer]
0x14001afb9  lea     rdx, aFailedToFindAK; "Failed to find a key to load store %s. "...
0x14001afc0  call    BiLogMessage
0x14001afc5  mov     ebx, 0C0000001h
0x14001afca  mov     rcx, [rbp+Handle]; Handle
0x14001afce  test    rcx, rcx
0x14001afd1  jz      short loc_14001AFFD
0x14001afd3  call    BiCloseKey
0x14001afd8  lea     rax, [rbp+Buffer]
0x14001afdc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14001afe0  inc     rdx
0x14001afe3  cmp     [rax+rdx*2], r13w
0x14001afe8  jnz     short loc_14001AFE0
0x14001afea  lea     edx, ds:2[rdx*2]
0x14001aff1  xor     r8d, r8d
0x14001aff4  lea     rcx, [rbp+Buffer]
0x14001aff8  call    BiUnloadHiveByName
0x14001affd  mov     eax, ebx
0x14001afff  mov     rcx, [rbp+var_10]
0x14001b003  xor     rcx, rsp; StackCookie
0x14001b006  call    __security_check_cookie
0x14001b00b  mov     rbx, [rsp+70h+arg_8]
0x14001b013  add     rsp, 70h
0x14001b017  pop     r15
0x14001b019  pop     r14
0x14001b01b  pop     r13
0x14001b01d  pop     r12
0x14001b01f  pop     rdi
0x14001b020  pop     rsi
0x14001b021  pop     rbp
0x14001b022  retn
0x14001b023  lea     r8, [rsi+0Ch]
0x14001b027  mov     r9d, 0C0000022h
0x14001b02d  lea     rdx, aTooManyUnexpla; "Too many unexplained failures. File: %s"...
0x14001b034  mov     ecx, 4
0x14001b039  call    BiLogMessage
0x14001b03e  jmp     short loc_14001AFCA
0x14001b040  mov     ecx, 2
0x14001b045  mov     dword ptr [rsp+70h+var_50], eax
0x14001b049  cmp     eax, 0C000000Fh
0x14001b04e  lea     r9, [rsi+0Ch]
0x14001b052  lea     r8, [rbp+Buffer]
0x14001b056  lea     rdx, aFailedToLoadHi; "Failed to load hive into key %ws from %"...
0x14001b05d  lea     edi, [rcx+2]
0x14001b060  cmovnz  ecx, edi
0x14001b063  call    BiLogMessage
0x14001b068  jmp     loc_14001AFCA
0x14001b06d  mov     r8d, edi
0x14001b070  lea     rdx, aLoadedHiveAtBc; "Loaded hive at BCD%08d"
0x14001b077  mov     ecx, 2
0x14001b07c  call    BiLogMessage
0x14001b081  test    r15b, 1
0x14001b085  jz      loc_14001B11C
0x14001b08b  mov     rcx, [rbp+Handle]
0x14001b08f  lea     rax, [rbp+var_38]
0x14001b093  mov     edi, 20019h
0x14001b098  mov     [rsp+70h+var_48], r13
0x14001b09d  mov     r8d, edi
0x14001b0a0  mov     [rsp+70h+var_50], rax
0x14001b0a5  xor     r9d, r9d
0x14001b0a8  lea     rdx, aObjects; "Objects"
0x14001b0af  call    BiCreateKey
0x14001b0b4  mov     ebx, eax
0x14001b0b6  test    eax, eax
0x14001b0b8  jns     short loc_14001B0DC
0x14001b0ba  lea     rdx, aFailedToInitia_1; "Failed to initialize objects key for st"...
0x14001b0c1  lea     r9, [rbp+Buffer]
0x14001b0c5  mov     dword ptr [rsp+70h+var_50], eax
0x14001b0c9  lea     r8, [rsi+0Ch]
0x14001b0cd  mov     ecx, 4
0x14001b0d2  call    BiLogMessage
0x14001b0d7  jmp     loc_14001B1D1
0x14001b0dc  mov     rcx, [rbp+var_38]; Handle
0x14001b0e0  call    BiCloseKey
0x14001b0e5  mov     rcx, [rbp+Handle]
0x14001b0e9  lea     rax, [rbp+var_38]
0x14001b0ed  mov     [rsp+70h+var_48], r13
0x14001b0f2  lea     rdx, aDescription; "Description"
0x14001b0f9  xor     r9d, r9d
0x14001b0fc  mov     [rsp+70h+var_50], rax
0x14001b101  mov     r8d, edi
0x14001b104  mov     [rbp+var_38], r13
0x14001b108  call    BiCreateKey
0x14001b10d  mov     ebx, eax
0x14001b10f  test    eax, eax
0x14001b111  jns     short loc_14001B11C
0x14001b113  lea     rdx, aFailedToInitia_0; "Failed to initialize description key fo"...
0x14001b11a  jmp     short loc_14001B0C1
0x14001b11c  mov     rcx, [rbp+Handle]
0x14001b120  lea     r9, [rbp+var_30]
0x14001b124  mov     r8d, 2001Fh
0x14001b12a  lea     rdx, aDescription; "Description"
0x14001b131  call    BiOpenKey
0x14001b136  mov     r14, [rbp+var_30]
0x14001b13a  mov     ebx, eax
0x14001b13c  test    eax, eax
0x14001b13e  jns     short loc_14001B17B
0x14001b140  mov     edi, 4
0x14001b145  cmp     eax, 0C0000034h
0x14001b14a  jnz     short loc_14001B15F
0x14001b14c  lea     rdx, aAValidStoreMus; "A valid store must have a description k"...
0x14001b153  mov     ecx, edi
0x14001b155  call    BiLogMessage
0x14001b15a  mov     ebx, 0C000015Ch
0x14001b15f  mov     dword ptr [rsp+70h+var_50], ebx
0x14001b163  lea     rdx, aFailedToOpenDe; "Failed to open description key for stor"...
0x14001b16a  mov     ecx, edi
0x14001b16c  lea     r9, [rbp+Buffer]
0x14001b170  lea     r8, [rsi+0Ch]
0x14001b174  call    BiLogMessage
0x14001b179  jmp     short loc_14001B1C4
0x14001b17b  lea     rax, [rbp+Buffer]
0x14001b17f  mov     dword ptr [rsp+70h+var_48], 18h
0x14001b187  mov     r9d, 1
0x14001b18d  mov     [rsp+70h+var_50], rax
0x14001b192  xor     r8d, r8d
0x14001b195  lea     rdx, aKeyname; "KeyName"
0x14001b19c  mov     rcx, r14
0x14001b19f  call    BiSetRegistryValue
0x14001b1a4  mov     ebx, eax
0x14001b1a6  test    eax, eax
0x14001b1a8  jns     short loc_14001B1BC
0x14001b1aa  mov     dword ptr [rsp+70h+var_50], eax
0x14001b1ae  lea     rdx, aFailedToSetDes; "Failed to set description key value. St"...
0x14001b1b5  mov     ecx, 4
0x14001b1ba  jmp     short loc_14001B16C
0x14001b1bc  mov     rax, [rbp+Handle]
0x14001b1c0  mov     [r12], rax
0x14001b1c4  test    r14, r14
0x14001b1c7  jz      short loc_14001B1D1
0x14001b1c9  mov     rcx, r14; Handle
0x14001b1cc  call    BiCloseKey
0x14001b1d1  mov     rcx, [rbp+var_38]; Handle
0x14001b1d5  test    rcx, rcx
0x14001b1d8  jz      short loc_14001B1DF
0x14001b1da  call    BiCloseKey
0x14001b1df  test    ebx, ebx
0x14001b1e1  jns     loc_14001AFFD
0x14001b1e7  jmp     loc_14001AFCA
```
