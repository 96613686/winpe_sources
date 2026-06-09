# AhcpCacheEntryAcquire

- ea: `0x140043bb0`
- end: `0x140043f0a`
- name: `AhcpCacheEntryAcquire`
- size: `858`
- prototype: `__int64 __fastcall(_QWORD *, volatile signed __int32 **, __int64, _OWORD *, HANDLE FileHandle, int)`
- caller_count: `4`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140027bc8`
- `0x140043fc4`
- `0x14004c3a0`
- `0x1400576e8`

## callees

- `0x1400043fd`
- `0x1400079f0`
- `0x14003e364`
- `0x140043bb0`
- `0x140043f10`
- `0x1400440d8`
- `0x14004b7e4`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140043c55`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140043d9e`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140043c55`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140043d9e`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140043c8c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140043d6c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140043dd1`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140043c8c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140043d6c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140043dd1`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140043d5d`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140043dbd`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140043df3`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140043efc`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140043d5d`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140043dbd`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140043df3`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140043efc`

## string_xrefs

- `0x140043ce9`: `AhcpCacheEntryAcquire`
- `0x140043e18`: `AhcpCacheEntryAcquire`
- `0x140043e63`: `AhcpCacheEntryAcquire`
- `0x140043e8a`: `AhcpCacheEntryAcquire`
- `0x140043ee3`: `AhcpCacheEntryAcquire`
- `0x140043e52`: `Failed to read file time [%x]`
- `0x140043e79`: `Failed to acquire store read lock [%x]`
- `0x140043e07`: `Failed to update entry when time changed [%x]`

## pseudocode

```c
__int64 __fastcall AhcpCacheEntryAcquire(
        _QWORD *a1,
        volatile signed __int32 **a2,
        __int64 a3,
        _OWORD *a4,
        HANDLE FileHandle,
        int a6)
{
  __int64 v7; // rbp
  volatile signed __int32 *v11; // rbx
  int v12; // r13d
  int v13; // eax
  int v14; // esi
  struct _RTL_AVL_TABLE *v15; // rcx
  volatile signed __int32 *v16; // rax
  __int64 v17; // rdi
  struct _ERESOURCE *v18; // rcx
  __int64 result; // rax
  int v20; // eax
  NTSTATUS v21; // eax
  unsigned int v22; // ebx
  struct _RTL_AVL_TABLE *v23; // rcx
  volatile signed __int32 *v24; // rax
  struct _RTL_AVL_TABLE *v25; // rcx
  int v26; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-E8h] BYREF
  __int128 v28; // [rsp+40h] [rbp-D8h]
  __int128 v29; // [rsp+50h] [rbp-C8h]
  _OWORD v30[3]; // [rsp+60h] [rbp-B8h] BYREF
  __int128 Buffer; // [rsp+90h] [rbp-88h] BYREF
  _OWORD v32[2]; // [rsp+A0h] [rbp-78h] BYREF

  v7 = 0;
  v28 = 0;
  v29 = 0;
  if ( FileHandle )
  {
    Buffer = 0;
    memset(v32, 0, 24);
    IoStatusBlock = 0;
    v21 = ZwQueryInformationFile_0(FileHandle, &IoStatusBlock, &Buffer, 0x28u, FileBasicInformation);
    v22 = v21;
    if ( v21 < 0 )
    {
      AslLogCallPrintf(1, "AslFileGetTime", 2064, "NtQueryInformationFile failed [%x]", v21);
      AslLogCallPrintf(1, "AhcpCacheEntryAcquire", 1148, "Failed to read file time [%x]", v22);
      return v22;
    }
    v7 = *(_QWORD *)&v32[0];
  }
  v11 = 0;
  v12 = 1;
  while ( 1 )
  {
    v13 = AhcLockAcquireSharedWait(*(PERESOURCE *)a3);
    v14 = v13;
    if ( v13 < 0 )
      break;
    v15 = *(struct _RTL_AVL_TABLE **)(a3 + 8);
    memset(v32, 0, sizeof(v32));
    Buffer = 0;
    *(_OWORD *)((char *)v32 + 8) = *a4;
    v16 = (volatile signed __int32 *)RtlLookupElementGenericTableAvl(v15, &Buffer);
    v11 = v16;
    if ( v16 )
    {
      _InterlockedIncrement(v16 + 4);
      v17 = *((_QWORD *)v16 + 5);
      if ( v7 == *(_QWORD *)(v17 + 8)
        || (ExEnterCriticalRegionAndAcquireResourceExclusive(*(PERESOURCE *)v17),
            *(_QWORD *)(v17 + 8) = v7,
            v14 = AhcpCacheEntryFilter(v17, 4294918463LL),
            ExReleaseResourceAndLeaveCriticalRegion(*(PERESOURCE *)v17),
            v14 >= 0) )
      {
        v18 = *(struct _ERESOURCE **)v17;
        if ( a6 )
        {
          ExEnterCriticalRegionAndAcquireResourceExclusive(v18);
        }
        else
        {
          v20 = AhcLockAcquireSharedWait(v18);
          v14 = v20;
          if ( v20 < 0 )
          {
            AslLogCallPrintf(1, "AhcpCacheEntryAcquire", 1226, "Failed to lock entry [%x]", v20);
            goto LABEL_12;
          }
        }
        *a1 = v17;
        result = 0;
        *a2 = v11;
        return result;
      }
      AslLogCallPrintf(1, "AhcpCacheEntryAcquire", 1212, "Failed to update entry when time changed [%x]", v14);
      goto LABEL_12;
    }
    ExReleaseResourceAndLeaveCriticalRegion(*(PERESOURCE *)a3);
    ExEnterCriticalRegionAndAcquireResourceExclusive(*(PERESOURCE *)a3);
    v23 = *(struct _RTL_AVL_TABLE **)(a3 + 8);
    memset(v30, 0, sizeof(v30));
    *(_OWORD *)((char *)&v30[1] + 8) = *a4;
    v24 = (volatile signed __int32 *)RtlLookupElementGenericTableAvl(v23, v30);
    v11 = v24;
    if ( v24 )
    {
      _InterlockedIncrement(v24 + 4);
    }
    else
    {
      v25 = *(struct _RTL_AVL_TABLE **)(a3 + 8);
      *((_QWORD *)&v28 + 1) = v7;
      v11 = 0;
      v26 = AhcStoreInsert(v25);
      v14 = v26;
      if ( v26 < 0 )
      {
        AslLogCallPrintf(1, "AhcpCacheEntryAcquire", 1191, "Failed to insert entry [%x]", v26);
        goto LABEL_27;
      }
    }
    ExReleaseResourceAndLeaveCriticalRegion(*(PERESOURCE *)a3);
  }
  AslLogCallPrintf(1, "AhcpCacheEntryAcquire", 1160, "Failed to acquire store read lock [%x]", v13);
  v12 = 0;
  if ( v11 )
LABEL_12:
    _InterlockedDecrement(v11 + 4);
  if ( v14 < 0 && v12 )
LABEL_27:
    ExReleaseResourceAndLeaveCriticalRegion(*(PERESOURCE *)a3);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140043bb0  push    rbx
0x140043bb2  push    rbp
0x140043bb3  push    rdi
0x140043bb4  push    r12
0x140043bb6  push    r13
0x140043bb8  push    r14
0x140043bba  push    r15
0x140043bbc  sub     rsp, 0E0h
0x140043bc3  mov     rax, cs:__security_cookie
0x140043bca  xor     rax, rsp
0x140043bcd  mov     [rsp+118h+var_58], rax
0x140043bd5  xorps   xmm0, xmm0
0x140043bd8  mov     r15, rcx
0x140043bdb  mov     rcx, [rsp+118h+FileHandle]; FileHandle
0x140043be3  xor     ebp, ebp
0x140043be5  mov     rdi, r9
0x140043be8  mov     r14, r8
0x140043beb  mov     r12, rdx
0x140043bee  movups  [rsp+118h+var_D8], xmm0
0x140043bf3  movups  [rsp+118h+var_C8], xmm0
0x140043bf8  test    rcx, rcx
0x140043bfb  jnz     loc_140043D01
0x140043c01  mov     [rsp+118h+var_40], rsi
0x140043c09  xor     ebx, ebx
0x140043c0b  mov     r13d, 1
0x140043c11  mov     rcx, [r14]; Resource
0x140043c14  call    AhcLockAcquireSharedWait
0x140043c19  mov     esi, eax
0x140043c1b  test    eax, eax
0x140043c1d  js      loc_140043E79
0x140043c23  mov     rcx, [r14+8]; Table
0x140043c27  lea     rdx, [rsp+118h+Buffer]; Buffer
0x140043c2f  xorps   xmm0, xmm0
0x140043c32  movups  [rsp+118h+var_78], xmm0
0x140043c3a  movups  [rsp+118h+var_68], xmm0
0x140043c42  movups  [rsp+118h+Buffer], xmm0
0x140043c4a  movups  xmm0, xmmword ptr [rdi]
0x140043c4d  movups  [rsp+118h+var_78+8], xmm0
0x140043c55  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140043c5c  nop     dword ptr [rax+rax+00h]
0x140043c61  mov     rbx, rax
0x140043c64  test    rax, rax
0x140043c67  jz      loc_140043D5A
0x140043c6d  lock inc dword ptr [rax+10h]
0x140043c71  mov     rdi, [rax+28h]
0x140043c75  cmp     rbp, [rdi+8]
0x140043c79  jnz     loc_140043DCE
0x140043c7f  cmp     [rsp+118h+arg_28], 0
0x140043c87  mov     rcx, [rdi]; Resource
0x140043c8a  jz      short loc_140043CCD
0x140043c8c  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140043c93  nop     dword ptr [rax+rax+00h]
0x140043c98  mov     [r15], rdi
0x140043c9b  xor     eax, eax
0x140043c9d  mov     [r12], rbx
0x140043ca1  mov     rsi, [rsp+118h+var_40]
0x140043ca9  mov     rcx, [rsp+118h+var_58]
0x140043cb1  xor     rcx, rsp; StackCookie
0x140043cb4  call    __security_check_cookie
0x140043cb9  add     rsp, 0E0h
0x140043cc0  pop     r15
0x140043cc2  pop     r14
0x140043cc4  pop     r13
0x140043cc6  pop     r12
0x140043cc8  pop     rdi
0x140043cc9  pop     rbp
0x140043cca  pop     rbx
0x140043ccb  retn
0x140043ccd  call    AhcLockAcquireSharedWait
0x140043cd2  mov     esi, eax
0x140043cd4  test    eax, eax
0x140043cd6  jns     short loc_140043C98
0x140043cd8  lea     r9, aFailedToLockEn; "Failed to lock entry [%x]"
0x140043cdf  mov     [rsp+118h+FileInformationClass], eax
0x140043ce3  mov     r8d, 4CAh
0x140043ce9  lea     rdx, aAhcpcacheentry_5; "AhcpCacheEntryAcquire"
0x140043cf0  mov     ecx, r13d
0x140043cf3  call    AslLogCallPrintf
0x140043cf8  lock dec dword ptr [rbx+10h]
0x140043cfc  jmp     loc_140043EA5
0x140043d01  xorps   xmm1, xmm1
0x140043d04  mov     [rsp+118h+FileInformationClass], 4; FileInformationClass
0x140043d0c  xor     eax, eax
0x140043d0e  lea     r8, [rsp+118h+Buffer]; FileInformation
0x140043d16  mov     r9d, 28h ; '('; Length
0x140043d1c  mov     qword ptr [rsp+118h+var_68], rax
0x140043d24  lea     rdx, [rsp+118h+IoStatusBlock]; IoStatusBlock
0x140043d29  movups  [rsp+118h+Buffer], xmm1
0x140043d31  movups  [rsp+118h+var_78], xmm1
0x140043d39  movups  xmmword ptr [rsp+118h+IoStatusBlock], xmm0
0x140043d3e  call    ZwQueryInformationFile_0
0x140043d43  mov     ebx, eax
0x140043d45  test    eax, eax
0x140043d47  js      loc_140043E2C
0x140043d4d  mov     rbp, qword ptr [rsp+118h+var_78]
0x140043d55  jmp     loc_140043C01
0x140043d5a  mov     rcx, [r14]; Resource
0x140043d5d  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140043d64  nop     dword ptr [rax+rax+00h]
0x140043d69  mov     rcx, [r14]; Resource
0x140043d6c  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140043d73  nop     dword ptr [rax+rax+00h]
0x140043d78  mov     rcx, [r14+8]; Table
0x140043d7c  lea     rdx, [rsp+118h+var_B8]; Buffer
0x140043d81  xorps   xmm0, xmm0
0x140043d84  movups  [rsp+118h+var_A8], xmm0
0x140043d89  movups  [rsp+118h+var_98], xmm0
0x140043d91  movups  [rsp+118h+var_B8], xmm0
0x140043d96  movups  xmm0, xmmword ptr [rdi]
0x140043d99  movups  [rsp+118h+var_A8+8], xmm0
0x140043d9e  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140043da5  nop     dword ptr [rax+rax+00h]
0x140043daa  mov     rbx, rax
0x140043dad  test    rax, rax
0x140043db0  jz      loc_140043EB0
0x140043db6  lock inc dword ptr [rax+10h]
0x140043dba  mov     rcx, [r14]; Resource
0x140043dbd  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140043dc4  nop     dword ptr [rax+rax+00h]
0x140043dc9  jmp     loc_140043C11
0x140043dce  mov     rcx, [rdi]; Resource
0x140043dd1  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140043dd8  nop     dword ptr [rax+rax+00h]
0x140043ddd  mov     edx, 0FFFF413Fh
0x140043de2  mov     [rdi+8], rbp
0x140043de6  mov     rcx, rdi
0x140043de9  call    AhcpCacheEntryFilter
0x140043dee  mov     rcx, [rdi]; Resource
0x140043df1  mov     esi, eax
0x140043df3  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140043dfa  nop     dword ptr [rax+rax+00h]
0x140043dff  test    esi, esi
0x140043e01  jns     loc_140043C7F
0x140043e07  lea     r9, aFailedToUpdate_3; "Failed to update entry when time change"...
0x140043e0e  mov     [rsp+118h+FileInformationClass], esi
0x140043e12  mov     r8d, 4BCh
0x140043e18  lea     rdx, aAhcpcacheentry_5; "AhcpCacheEntryAcquire"
0x140043e1f  mov     ecx, r13d
0x140043e22  call    AslLogCallPrintf
0x140043e27  jmp     loc_140043CF8
0x140043e2c  mov     r13d, 1
0x140043e32  mov     [rsp+118h+FileInformationClass], ebx
0x140043e36  mov     ecx, r13d
0x140043e39  lea     r9, aNtqueryinforma_0; "NtQueryInformationFile failed [%x]"
0x140043e40  mov     r8d, 810h
0x140043e46  lea     rdx, aAslfilegettime; "AslFileGetTime"
0x140043e4d  call    AslLogCallPrintf
0x140043e52  lea     r9, aFailedToReadFi_0; "Failed to read file time [%x]"
0x140043e59  mov     [rsp+118h+FileInformationClass], ebx
0x140043e5d  mov     r8d, 47Ch
0x140043e63  lea     rdx, aAhcpcacheentry_5; "AhcpCacheEntryAcquire"
0x140043e6a  mov     ecx, r13d
0x140043e6d  call    AslLogCallPrintf
0x140043e72  mov     eax, ebx
0x140043e74  jmp     loc_140043CA9
0x140043e79  lea     r9, aFailedToAcquir_1; "Failed to acquire store read lock [%x]"
0x140043e80  mov     [rsp+118h+FileInformationClass], eax
0x140043e84  mov     r8d, 488h
0x140043e8a  lea     rdx, aAhcpcacheentry_5; "AhcpCacheEntryAcquire"
0x140043e91  mov     ecx, r13d
0x140043e94  call    AslLogCallPrintf
0x140043e99  xor     r13d, r13d
0x140043e9c  test    rbx, rbx
0x140043e9f  jnz     loc_140043CF8
0x140043ea5  test    esi, esi
0x140043ea7  js      short loc_140043EF4
0x140043ea9  mov     eax, esi
0x140043eab  jmp     loc_140043CA1
0x140043eb0  mov     rcx, [r14+8]; Table
0x140043eb4  lea     r8, [rsp+118h+var_D8]
0x140043eb9  mov     rdx, rdi
0x140043ebc  mov     qword ptr [rsp+118h+var_D8+8], rbp
0x140043ec1  xor     ebx, ebx
0x140043ec3  call    AhcStoreInsert
0x140043ec8  mov     esi, eax
0x140043eca  test    eax, eax
0x140043ecc  jns     loc_140043DBA
0x140043ed2  lea     r9, aFailedToInsert_2; "Failed to insert entry [%x]"
0x140043ed9  mov     [rsp+118h+FileInformationClass], eax
0x140043edd  mov     r8d, 4A7h
0x140043ee3  lea     rdx, aAhcpcacheentry_5; "AhcpCacheEntryAcquire"
0x140043eea  mov     ecx, r13d
0x140043eed  call    AslLogCallPrintf
0x140043ef2  jmp     short loc_140043EF9
0x140043ef4  test    r13d, r13d
0x140043ef7  jz      short loc_140043EA9
0x140043ef9  mov     rcx, [r14]; Resource
0x140043efc  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140043f03  nop     dword ptr [rax+rax+00h]
0x140043f08  jmp     short loc_140043EA9
```
