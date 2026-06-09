# SdbpOpenDatabaseInMemory

- ea: `0x18011a8b8`
- end: `0x18011aa1c`
- name: `SdbpOpenDatabaseInMemory`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801234f4`

## callees

- `0x1800197d4`
- `0x18001cce4`
- `0x180059920`
- `0x1801189c8`
- `0x18011a8b8`
- `0x18011aa24`
- `0x18011aaac`
- `0x18011abbc`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18011a8f9`
- `ntdll!RtlAllocateHeap` at `0x18011a8f9`

## string_xrefs

- `0x18011a959`: `Can't read database header`
- `0x18011aa05`: `SdbpValidateAndApplyCompatFlags failed [%x]`
- `0x18011a914`: `SdbpOpenDatabaseInMemory`
- `0x18011a966`: `SdbpOpenDatabaseInMemory`
- `0x18011a9c8`: `SdbpOpenDatabaseInMemory`

## pseudocode

```c
_DWORD *__fastcall SdbpOpenDatabaseInMemory(__int64 a1, int a2, unsigned int a3)
{
  _DWORD *Heap; // rax
  _DWORD *v7; // rbx
  const char *v9; // r9
  int v10; // r8d
  __int64 v11; // [rsp+30h] [rbp-48h] BYREF
  int v12; // [rsp+38h] [rbp-40h]

  v11 = 0;
  v12 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v7 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, (unsigned int)"SdbpOpenDatabaseInMemory", 2891, (unsigned int)"Failed to allocate DB structure");
    return 0;
  }
  Heap[5] = a2;
  Heap[4] = 0;
  Heap[6] |= 1u;
  *((_QWORD *)Heap + 1) = a1;
  *(_QWORD *)Heap = 0;
  if ( !(unsigned int)SdbpReadMappedData((__int64)Heap, 0, &v11, 0xCu) )
  {
    AslLogCallPrintf(1, (unsigned int)"SdbpOpenDatabaseInMemory", 2902, (unsigned int)"Can't read database header");
LABEL_5:
    AslFree(NtCurrentPeb()->ProcessHeap, v7);
    return 0;
  }
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
    && v12 != 1717724275
    && (a3 & 2) == 0 )
  {
    v9 = "Magic does not match a valid value: [0x%lx]";
    v10 = 2908;
LABEL_11:
    AslLogCallPrintf(1, (unsigned int)"SdbpOpenDatabaseInMemory", v10, (_DWORD)v9);
    goto LABEL_5;
  }
  if ( !(unsigned int)SdbpValidateAndApplyCompatFlags(v7, &v11, a3) )
    goto LABEL_5;
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
    && (int)SdbpValidateRootTagSizes(v7) < 0 )
  {
    v9 = "SdbpValidateAndApplyCompatFlags failed [%x]";
    v10 = 2920;
    goto LABEL_11;
  }
  return v7;
}

```

## disassembly

```asm
0x18011a8b8  push    rbx
0x18011a8ba  push    rbp
0x18011a8bb  push    rsi
0x18011a8bc  push    rdi
0x18011a8bd  sub     rsp, 58h
0x18011a8c1  mov     rax, cs:__security_cookie
0x18011a8c8  xor     rax, rsp
0x18011a8cb  mov     [rsp+78h+var_38], rax
0x18011a8d0  xor     eax, eax
0x18011a8d2  mov     rbp, rcx
0x18011a8d5  mov     rcx, gs:60h
0x18011a8de  mov     esi, r8d
0x18011a8e1  mov     edi, edx
0x18011a8e3  mov     [rsp+78h+var_48], rax
0x18011a8e8  mov     r8d, 0A80h; Size
0x18011a8ee  mov     [rsp+78h+var_40], eax
0x18011a8f2  lea     edx, [rax+8]; Flags
0x18011a8f5  mov     rcx, [rcx+30h]; HeapHandle
0x18011a8f9  call    cs:__imp_RtlAllocateHeap
0x18011a8ff  mov     rbx, rax
0x18011a902  test    rax, rax
0x18011a905  jnz     short loc_18011A925
0x18011a907  lea     r9, aFailedToAlloca_10; "Failed to allocate DB structure"
0x18011a90e  mov     r8d, 0B4Bh
0x18011a914  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x18011a91b  lea     ecx, [rax+1]
0x18011a91e  call    AslLogCallPrintf
0x18011a923  jmp     short loc_18011A989
0x18011a925  mov     [rax+14h], edi
0x18011a928  lea     r8, [rsp+78h+var_48]
0x18011a92d  mov     edi, 1
0x18011a932  mov     dword ptr [rax+10h], 0
0x18011a939  or      [rax+18h], edi
0x18011a93c  xor     edx, edx
0x18011a93e  mov     rcx, rbx
0x18011a941  mov     [rax+8], rbp
0x18011a945  mov     qword ptr [rax], 0
0x18011a94c  lea     r9d, [rdi+0Bh]
0x18011a950  call    SdbpReadMappedData
0x18011a955  test    eax, eax
0x18011a957  jnz     short loc_18011A9A1
0x18011a959  lea     r9, aCanTReadDataba; "Can't read database header"
0x18011a960  mov     r8d, 0B56h
0x18011a966  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x18011a96d  mov     ecx, edi
0x18011a96f  call    AslLogCallPrintf
0x18011a974  mov     rcx, gs:60h
0x18011a97d  mov     rdx, rbx
0x18011a980  mov     rcx, [rcx+30h]
0x18011a984  call    AslFree
0x18011a989  xor     eax, eax
0x18011a98b  mov     rcx, [rsp+78h+var_38]
0x18011a990  xor     rcx, rsp; StackCookie
0x18011a993  call    __security_check_cookie
0x18011a998  add     rsp, 58h
0x18011a99c  pop     rdi
0x18011a99d  pop     rsi
0x18011a99e  pop     rbp
0x18011a99f  pop     rbx
0x18011a9a0  retn
0x18011a9a1  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18011a9a6  test    eax, eax
0x18011a9a8  jz      short loc_18011A9DC
0x18011a9aa  mov     eax, [rsp+78h+var_40]
0x18011a9ae  cmp     eax, 66626473h
0x18011a9b3  jz      short loc_18011A9DC
0x18011a9b5  test    sil, 2
0x18011a9b9  jnz     short loc_18011A9DC
0x18011a9bb  lea     r9, aMagicDoesNotMa; "Magic does not match a valid value: [0x"...
0x18011a9c2  mov     r8d, 0B5Ch
0x18011a9c8  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x18011a9cf  mov     [rsp+78h+var_58], eax
0x18011a9d3  mov     ecx, edi
0x18011a9d5  call    AslLogCallPrintf
0x18011a9da  jmp     short loc_18011A974
0x18011a9dc  mov     r8d, esi
0x18011a9df  lea     rdx, [rsp+78h+var_48]
0x18011a9e4  mov     rcx, rbx
0x18011a9e7  call    SdbpValidateAndApplyCompatFlags
0x18011a9ec  test    eax, eax
0x18011a9ee  jz      short loc_18011A974
0x18011a9f0  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x18011a9f5  test    eax, eax
0x18011a9f7  jz      short loc_18011AA14
0x18011a9f9  mov     rcx, rbx
0x18011a9fc  call    SdbpValidateRootTagSizes
0x18011aa01  test    eax, eax
0x18011aa03  jns     short loc_18011AA14
0x18011aa05  lea     r9, aSdbpvalidatean_0; "SdbpValidateAndApplyCompatFlags failed "...
0x18011aa0c  mov     r8d, 0B68h
0x18011aa12  jmp     short loc_18011A9C8
0x18011aa14  mov     rax, rbx
0x18011aa17  jmp     loc_18011A98B
```
