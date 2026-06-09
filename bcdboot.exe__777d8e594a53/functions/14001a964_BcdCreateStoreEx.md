# BcdCreateStoreEx

- ea: `0x14001a964`
- end: `0x14001ac78`
- name: `BcdCreateStoreEx`
- size: `788`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *p_DestinationString, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x140004080`
- `0x140005e18`

## callees

- `0x1400133e4`
- `0x14001a8c4`
- `0x14001a964`
- `0x14001ae30`
- `0x14001ae94`
- `0x14001af00`
- `0x14001b1f4`
- `0x14001c014`
- `0x14001c14c`
- `0x14001e648`
- `0x14001e730`
- `0x14001ec14`
- `0x14001f980`
- `0x1400200a0`
- `0x1400265e2`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14001ab1b`
- `ntdll!RtlAllocateHeap` at `0x14001ab1b`
- `ntdll!RtlFreeHeap` at `0x14001abfe`
- `ntdll!RtlFreeHeap` at `0x14001ac1b`
- `ntdll!RtlFreeHeap` at `0x14001abfe`
- `ntdll!RtlFreeHeap` at `0x14001ac1b`
- `ntdll!RtlInitUnicodeString` at `0x14001aaca`
- `ntdll!RtlInitUnicodeString` at `0x14001aaca`

## string_xrefs

- `0x14001a9d1`: `\Registry\Machine\System\CurrentControlSet\BootConfigurationData`
- `0x14001aa04`: `\Registry\Machine\System\CurrentControlSet\BootConfigurationData`
- `0x14001aa1d`: `Unable to create tempory root key. Status: %x`
- `0x14001aaed`: `Failed to create hive. Store: %ws Status: %x`
- `0x14001aa62`: `Unable to create tempory new store key. Status: %x`
- `0x14001aa8d`: `Failed to create system store path. Status: %x`
- `0x14001aaa8`: `Failed to get system store path. Status: %x`
- `0x14001abd6`: `Failed to open new system store. Store: %ws Status: %x`
- `0x14001ac48`: `Failed to create store. Status: %x`

## pseudocode

```c
__int64 __fastcall BcdCreateStoreEx(struct _UNICODE_STRING *p_DestinationString, __int64 a2, _QWORD *a3)
{
  __int64 result; // rax
  WCHAR *v5; // r14
  int v6; // eax
  int v7; // ebx
  int v8; // eax
  char v9; // r12
  int SystemStorePath; // eax
  int v11; // eax
  int Hive; // eax
  unsigned int v13; // ebx
  _DWORD *Heap; // rax
  _WORD *v15; // r15
  __int64 v16; // r8
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // [rsp+30h] [rbp-30h] BYREF
  HANDLE KeyHandle; // [rsp+38h] [rbp-28h] BYREF
  PCWSTR SourceString; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+48h] BYREF

  v21 = 0;
  DestinationString = 0;
  result = BiAcquireBcdSyncMutant(0);
  if ( (int)result < 0 )
    return result;
  v5 = 0;
  SourceString = 0;
  v26 = 0;
  KeyHandle = 0;
  BiLogMessage(2, L"Creating store %08x.", 0);
  if ( (int)BiOpenKey(0, L"\\Registry\\Machine\\System\\CurrentControlSet\\BootConfigurationData", 983103, &v26) >= 0 )
  {
    BiDeleteKey(v26);
    v26 = 0;
  }
  v6 = BiCreateKey(0, L"\\Registry\\Machine\\System\\CurrentControlSet\\BootConfigurationData", 983103, 0, &v26, 0);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = BiCreateKey(v26, L"NewStoreRoot", 983103, 0, &KeyHandle, 0);
    v7 = v8;
    if ( v8 < 0 )
    {
      BiLogMessage(4, L"Unable to create tempory new store key. Status: %x", (unsigned int)v8);
LABEL_34:
      if ( KeyHandle )
        BiDeleteKey(KeyHandle);
      goto LABEL_36;
    }
    if ( p_DestinationString )
    {
      v9 = 0;
    }
    else
    {
      SystemStorePath = BiCreateSystemStorePath();
      v7 = SystemStorePath;
      if ( SystemStorePath < 0 )
      {
        BiLogMessage(4, L"Failed to create system store path. Status: %x", (unsigned int)SystemStorePath);
        goto LABEL_34;
      }
      v11 = BcdGetSystemStorePath(&SourceString);
      v7 = v11;
      if ( v11 < 0 )
      {
        BiLogMessage(4, L"Failed to get system store path. Status: %x", (unsigned int)v11);
        v5 = (WCHAR *)SourceString;
        goto LABEL_32;
      }
      v5 = (WCHAR *)SourceString;
      RtlInitUnicodeString(&DestinationString, SourceString);
      p_DestinationString = &DestinationString;
      v9 = 1;
    }
    Hive = BiCreateHive(KeyHandle);
    v7 = Hive;
    if ( Hive < 0 )
    {
      BiLogMessage(4, L"Failed to create hive. Store: %ws Status: %x", p_DestinationString->Buffer, (unsigned int)Hive);
      goto LABEL_32;
    }
    v13 = p_DestinationString->Length + 14;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
    v15 = Heap;
    if ( !Heap )
    {
      v7 = -1073741801;
      goto LABEL_32;
    }
    *Heap = 1;
    Heap[1] = v13;
    Heap[2] = 3;
    memcpy_0(Heap + 3, p_DestinationString->Buffer, p_DestinationString->Length);
    v15[((unsigned __int64)p_DestinationString->Length >> 1) + 6] = 0;
    v17 = BiAddStoreFromFile(v15, 1, v16, &v21);
    v7 = v17;
    if ( v17 < 0 )
    {
      BiLogMessage(
        4,
        L"Failed to add new store from file. File: %ws Status: %x",
        p_DestinationString->Buffer,
        (unsigned int)v17);
      goto LABEL_31;
    }
    if ( v9 )
    {
      v18 = BcdCloseStore(v21);
      v7 = v18;
      if ( v18 < 0 )
      {
        BiLogMessage(
          4,
          L"Failed to close new store. Store: %ws Status: %x",
          p_DestinationString->Buffer,
          (unsigned int)v18);
LABEL_31:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
LABEL_32:
        if ( v5 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
        goto LABEL_34;
      }
      v21 = 0;
      v19 = BiAdoptStore();
      v7 = v19;
      if ( v19 < 0 )
      {
        BiLogMessage(
          4,
          L"Failed to adopt new store. File: %ws Status: %x",
          p_DestinationString->Buffer,
          (unsigned int)v19);
        goto LABEL_31;
      }
      v20 = BcdOpenSystemStore(&v21);
      v7 = v20;
      if ( v20 < 0 )
      {
        BiLogMessage(
          4,
          L"Failed to open new system store. Store: %ws Status: %x",
          p_DestinationString->Buffer,
          (unsigned int)v20);
        goto LABEL_31;
      }
    }
    v7 = 0;
    *a3 = v21;
    goto LABEL_31;
  }
  BiLogMessage(4, L"Unable to create tempory root key. Status: %x", (unsigned int)v6);
LABEL_36:
  if ( v26 )
    BiDeleteKey(v26);
  if ( v7 < 0 )
    BiLogMessage(4, L"Failed to create store. Status: %x", (unsigned int)v7);
  BiReleaseBcdSyncMutant(0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001a964  mov     [rsp-28h+arg_0], rbx
0x14001a969  mov     [rsp-28h+arg_8], rsi
0x14001a96e  mov     [rsp-28h+arg_10], r8
0x14001a973  push    rbp
0x14001a974  push    rdi
0x14001a975  push    r12
0x14001a977  push    r14
0x14001a979  push    r15
0x14001a97b  mov     rbp, rsp
0x14001a97e  sub     rsp, 60h
0x14001a982  mov     rsi, rcx
0x14001a985  mov     [rbp+var_30], 0
0x14001a98d  xorps   xmm0, xmm0
0x14001a990  xor     ecx, ecx
0x14001a992  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001a996  call    BiAcquireBcdSyncMutant
0x14001a99b  test    eax, eax
0x14001a99d  js      loc_14001AC5F
0x14001a9a3  xor     r14d, r14d
0x14001a9a6  lea     rdx, aCreatingStore0; "Creating store %08x."
0x14001a9ad  xor     r8d, r8d
0x14001a9b0  mov     [rbp+SourceString], r14
0x14001a9b4  mov     [rbp+arg_18], r14
0x14001a9b8  mov     [rbp+KeyHandle], r14
0x14001a9bc  lea     ecx, [r14+2]
0x14001a9c0  call    BiLogMessage
0x14001a9c5  mov     edi, 0F003Fh
0x14001a9ca  lea     r9, [rbp+arg_18]
0x14001a9ce  mov     r8d, edi
0x14001a9d1  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x14001a9d8  xor     ecx, ecx
0x14001a9da  call    BiOpenKey
0x14001a9df  test    eax, eax
0x14001a9e1  js      short loc_14001A9F0
0x14001a9e3  mov     rcx, [rbp+arg_18]
0x14001a9e7  call    BiDeleteKey
0x14001a9ec  mov     [rbp+arg_18], r14
0x14001a9f0  lea     rax, [rbp+arg_18]
0x14001a9f4  mov     [rsp+60h+var_38], r14
0x14001a9f9  xor     r9d, r9d
0x14001a9fc  mov     [rsp+60h+var_40], rax
0x14001aa01  mov     r8d, edi
0x14001aa04  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x14001aa0b  xor     ecx, ecx
0x14001aa0d  call    BiCreateKey
0x14001aa12  mov     ebx, eax
0x14001aa14  test    eax, eax
0x14001aa16  jns     short loc_14001AA33
0x14001aa18  mov     edi, 4
0x14001aa1d  lea     rdx, aUnableToCreate; "Unable to create tempory root key. Stat"...
0x14001aa24  mov     ecx, edi
0x14001aa26  mov     r8d, eax
0x14001aa29  call    BiLogMessage
0x14001aa2e  jmp     loc_14001AC31
0x14001aa33  mov     rcx, [rbp+arg_18]
0x14001aa37  lea     rax, [rbp+KeyHandle]
0x14001aa3b  mov     [rsp+60h+var_38], r14
0x14001aa40  lea     rdx, aNewstoreroot; "NewStoreRoot"
0x14001aa47  xor     r9d, r9d
0x14001aa4a  mov     [rsp+60h+var_40], rax
0x14001aa4f  mov     r8d, edi
0x14001aa52  call    BiCreateKey
0x14001aa57  mov     ebx, eax
0x14001aa59  mov     edi, 4
0x14001aa5e  test    eax, eax
0x14001aa60  jns     short loc_14001AA78
0x14001aa62  lea     rdx, aUnableToCreate_0; "Unable to create tempory new store key."...
0x14001aa69  mov     r8d, eax
0x14001aa6c  mov     ecx, edi
0x14001aa6e  call    BiLogMessage
0x14001aa73  jmp     loc_14001AC21
0x14001aa78  test    rsi, rsi
0x14001aa7b  jz      short loc_14001AA82
0x14001aa7d  xor     r12b, r12b
0x14001aa80  jmp     short loc_14001AAD7
0x14001aa82  call    BiCreateSystemStorePath
0x14001aa87  mov     ebx, eax
0x14001aa89  test    eax, eax
0x14001aa8b  jns     short loc_14001AA96
0x14001aa8d  lea     rdx, aFailedToCreate_4; "Failed to create system store path. Sta"...
0x14001aa94  jmp     short loc_14001AA69
0x14001aa96  lea     rcx, [rbp+SourceString]
0x14001aa9a  call    BcdGetSystemStorePath
0x14001aa9f  mov     ebx, eax
0x14001aaa1  test    eax, eax
0x14001aaa3  jns     short loc_14001AABF
0x14001aaa5  mov     r8d, eax
0x14001aaa8  lea     rdx, aFailedToGetSys_1; "Failed to get system store path. Status"...
0x14001aaaf  mov     ecx, edi
0x14001aab1  call    BiLogMessage
0x14001aab6  mov     r14, [rbp+SourceString]
0x14001aaba  jmp     loc_14001AC04
0x14001aabf  mov     r14, [rbp+SourceString]
0x14001aac3  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001aac7  mov     rdx, r14; SourceString
0x14001aaca  call    cs:__imp_RtlInitUnicodeString
0x14001aad0  lea     rsi, [rbp+DestinationString]
0x14001aad4  mov     r12b, 1
0x14001aad7  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x14001aadb  mov     rdx, rsi
0x14001aade  call    BiCreateHive
0x14001aae3  mov     ebx, eax
0x14001aae5  test    eax, eax
0x14001aae7  jns     short loc_14001AB03
0x14001aae9  mov     r8, [rsi+8]
0x14001aaed  lea     rdx, aFailedToCreate; "Failed to create hive. Store: %ws Statu"...
0x14001aaf4  mov     r9d, eax
0x14001aaf7  mov     ecx, edi
0x14001aaf9  call    BiLogMessage
0x14001aafe  jmp     loc_14001AC04
0x14001ab03  mov     rcx, gs:60h
0x14001ab0c  xor     edx, edx; Flags
0x14001ab0e  movzx   ebx, word ptr [rsi]
0x14001ab11  add     ebx, 0Eh
0x14001ab14  mov     r8d, ebx; Size
0x14001ab17  mov     rcx, [rcx+30h]; HeapHandle
0x14001ab1b  call    cs:__imp_RtlAllocateHeap
0x14001ab21  mov     r15, rax
0x14001ab24  test    rax, rax
0x14001ab27  jnz     short loc_14001AB33
0x14001ab29  mov     ebx, 0C0000017h
0x14001ab2e  jmp     loc_14001AC04
0x14001ab33  mov     dword ptr [rax], 1
0x14001ab39  lea     rcx, [rax+0Ch]; void *
0x14001ab3d  mov     [rax+4], ebx
0x14001ab40  mov     dword ptr [rax+8], 3
0x14001ab47  movzx   r8d, word ptr [rsi]; Size
0x14001ab4b  mov     rdx, [rsi+8]; Src
0x14001ab4f  call    memcpy_0
0x14001ab54  movzx   ecx, word ptr [rsi]
0x14001ab57  lea     r9, [rbp+var_30]
0x14001ab5b  shr     rcx, 1
0x14001ab5e  xor     eax, eax
0x14001ab60  mov     [r15+rcx*2+0Ch], ax
0x14001ab66  lea     edx, [rax+1]
0x14001ab69  mov     rcx, r15
0x14001ab6c  call    BiAddStoreFromFile
0x14001ab71  mov     ebx, eax
0x14001ab73  test    eax, eax
0x14001ab75  jns     short loc_14001AB8E
0x14001ab77  lea     rdx, aFailedToAddNew; "Failed to add new store from file. File"...
0x14001ab7e  mov     r8, [rsi+8]
0x14001ab82  mov     r9d, eax
0x14001ab85  mov     ecx, edi
0x14001ab87  call    BiLogMessage
0x14001ab8c  jmp     short loc_14001ABEC
0x14001ab8e  test    r12b, r12b
0x14001ab91  jz      short loc_14001ABDF
0x14001ab93  mov     rcx, [rbp+var_30]
0x14001ab97  call    BcdCloseStore
0x14001ab9c  mov     ebx, eax
0x14001ab9e  test    eax, eax
0x14001aba0  jns     short loc_14001ABAB
0x14001aba2  lea     rdx, aFailedToCloseN; "Failed to close new store. Store: %ws S"...
0x14001aba9  jmp     short loc_14001AB7E
0x14001abab  mov     [rbp+var_30], 0
0x14001abb3  call    BiAdoptStore
0x14001abb8  mov     ebx, eax
0x14001abba  test    eax, eax
0x14001abbc  jns     short loc_14001ABC7
0x14001abbe  lea     rdx, aFailedToAdoptN; "Failed to adopt new store. File: %ws St"...
0x14001abc5  jmp     short loc_14001AB7E
0x14001abc7  lea     rcx, [rbp+var_30]
0x14001abcb  call    BcdOpenSystemStore
0x14001abd0  mov     ebx, eax
0x14001abd2  test    eax, eax
0x14001abd4  jns     short loc_14001ABDF
0x14001abd6  lea     rdx, aFailedToOpenNe; "Failed to open new system store. Store:"...
0x14001abdd  jmp     short loc_14001AB7E
0x14001abdf  mov     rcx, [rbp+arg_10]
0x14001abe3  xor     ebx, ebx
0x14001abe5  mov     rax, [rbp+var_30]
0x14001abe9  mov     [rcx], rax
0x14001abec  mov     rcx, gs:60h
0x14001abf5  mov     r8, r15; P
0x14001abf8  xor     edx, edx; Flags
0x14001abfa  mov     rcx, [rcx+30h]; HeapHandle
0x14001abfe  call    cs:__imp_RtlFreeHeap
0x14001ac04  test    r14, r14
0x14001ac07  jz      short loc_14001AC21
0x14001ac09  mov     rcx, gs:60h
0x14001ac12  mov     r8, r14; P
0x14001ac15  xor     edx, edx; Flags
0x14001ac17  mov     rcx, [rcx+30h]; HeapHandle
0x14001ac1b  call    cs:__imp_RtlFreeHeap
0x14001ac21  cmp     [rbp+KeyHandle], 0
0x14001ac26  jz      short loc_14001AC31
0x14001ac28  mov     rcx, [rbp+KeyHandle]
0x14001ac2c  call    BiDeleteKey
0x14001ac31  cmp     [rbp+arg_18], 0
0x14001ac36  jz      short loc_14001AC41
0x14001ac38  mov     rcx, [rbp+arg_18]
0x14001ac3c  call    BiDeleteKey
0x14001ac41  test    ebx, ebx
0x14001ac43  jns     short loc_14001AC56
0x14001ac45  mov     r8d, ebx
0x14001ac48  lea     rdx, aFailedToCreate_2; "Failed to create store. Status: %x"
0x14001ac4f  mov     ecx, edi
0x14001ac51  call    BiLogMessage
0x14001ac56  xor     ecx, ecx
0x14001ac58  call    BiReleaseBcdSyncMutant
0x14001ac5d  mov     eax, ebx
0x14001ac5f  lea     r11, [rsp+60h+var_s0]
0x14001ac64  mov     rbx, [r11+30h]
0x14001ac68  mov     rsi, [r11+38h]
0x14001ac6c  mov     rsp, r11
0x14001ac6f  pop     r15
0x14001ac71  pop     r14
0x14001ac73  pop     r12
0x14001ac75  pop     rdi
0x14001ac76  pop     rbp
0x14001ac77  retn
```
