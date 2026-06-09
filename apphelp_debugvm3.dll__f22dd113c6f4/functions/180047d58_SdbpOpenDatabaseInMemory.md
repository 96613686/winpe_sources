# SdbpOpenDatabaseInMemory

- ea: `0x180047d58`
- end: `0x180047ebc`
- name: `SdbpOpenDatabaseInMemory`
- size: `356`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180047ba0`
- `0x1800500bc`

## callees

- `0x18000ef24`
- `0x18000f080`
- `0x18000f114`
- `0x180018f20`
- `0x180030414`
- `0x180032d2c`
- `0x180047d58`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180047d99`
- `ntdll!RtlAllocateHeap` at `0x180047d99`

## string_xrefs

- `0x180047df9`: `Can't read database header`
- `0x180047db4`: `SdbpOpenDatabaseInMemory`
- `0x180047e06`: `SdbpOpenDatabaseInMemory`
- `0x180047e68`: `SdbpOpenDatabaseInMemory`
- `0x180047ea5`: `SdbpValidateAndApplyCompatFlags failed [%x]`

## pseudocode

```c
_DWORD *__fastcall SdbpOpenDatabaseInMemory(__int64 a1, int a2, unsigned int a3)
{
  _DWORD *Heap; // rax
  _DWORD *v7; // rbx
  int v9; // eax
  const char *v10; // r9
  __int64 v11; // r8
  __int64 v12; // [rsp+30h] [rbp-48h] BYREF
  int v13; // [rsp+38h] [rbp-40h]

  v12 = 0;
  v13 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v7 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "SdbpOpenDatabaseInMemory", 2891, "Failed to allocate DB structure");
    return 0;
  }
  Heap[5] = a2;
  Heap[4] = 0;
  Heap[6] |= 1u;
  *((_QWORD *)Heap + 1) = a1;
  *(_QWORD *)Heap = 0;
  if ( !(unsigned int)SdbpReadMappedData(Heap, 0, &v12, 12) )
  {
    AslLogCallPrintf(1, "SdbpOpenDatabaseInMemory", 2902, "Can't read database header");
LABEL_5:
    AslFree(NtCurrentPeb()->ProcessHeap, v7);
    return 0;
  }
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    v9 = v13;
    if ( v13 != 1717724275 && (a3 & 2) == 0 )
    {
      v10 = "Magic does not match a valid value: [0x%lx]";
      v11 = 2908;
LABEL_11:
      AslLogCallPrintf(1, "SdbpOpenDatabaseInMemory", v11, v10, v9);
      goto LABEL_5;
    }
  }
  if ( !(unsigned int)SdbpValidateAndApplyCompatFlags(v7, &v12, a3) )
    goto LABEL_5;
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    v9 = SdbpValidateRootTagSizes(v7);
    if ( v9 < 0 )
    {
      v10 = "SdbpValidateAndApplyCompatFlags failed [%x]";
      v11 = 2920;
      goto LABEL_11;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180047d58  push    rbx
0x180047d5a  push    rbp
0x180047d5b  push    rsi
0x180047d5c  push    rdi
0x180047d5d  sub     rsp, 58h
0x180047d61  mov     rax, cs:__security_cookie
0x180047d68  xor     rax, rsp
0x180047d6b  mov     [rsp+78h+var_38], rax
0x180047d70  xor     eax, eax
0x180047d72  mov     rbp, rcx
0x180047d75  mov     rcx, gs:60h
0x180047d7e  mov     esi, r8d
0x180047d81  mov     edi, edx
0x180047d83  mov     [rsp+78h+var_48], rax
0x180047d88  mov     r8d, 0A80h; Size
0x180047d8e  mov     [rsp+78h+var_40], eax
0x180047d92  lea     edx, [rax+8]; Flags
0x180047d95  mov     rcx, [rcx+30h]; HeapHandle
0x180047d99  call    cs:__imp_RtlAllocateHeap
0x180047d9f  mov     rbx, rax
0x180047da2  test    rax, rax
0x180047da5  jnz     short loc_180047DC5
0x180047da7  lea     r9, aFailedToAlloca_27; "Failed to allocate DB structure"
0x180047dae  mov     r8d, 0B4Bh
0x180047db4  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x180047dbb  lea     ecx, [rax+1]
0x180047dbe  call    AslLogCallPrintf
0x180047dc3  jmp     short loc_180047E29
0x180047dc5  mov     [rax+14h], edi
0x180047dc8  lea     r8, [rsp+78h+var_48]
0x180047dcd  mov     edi, 1
0x180047dd2  mov     dword ptr [rax+10h], 0
0x180047dd9  or      [rax+18h], edi
0x180047ddc  xor     edx, edx
0x180047dde  mov     rcx, rbx
0x180047de1  mov     [rax+8], rbp
0x180047de5  mov     qword ptr [rax], 0
0x180047dec  lea     r9d, [rdi+0Bh]
0x180047df0  call    SdbpReadMappedData
0x180047df5  test    eax, eax
0x180047df7  jnz     short loc_180047E41
0x180047df9  lea     r9, aCanTReadDataba; "Can't read database header"
0x180047e00  mov     r8d, 0B56h
0x180047e06  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x180047e0d  mov     ecx, edi
0x180047e0f  call    AslLogCallPrintf
0x180047e14  mov     rcx, gs:60h
0x180047e1d  mov     rdx, rbx
0x180047e20  mov     rcx, [rcx+30h]
0x180047e24  call    AslFree
0x180047e29  xor     eax, eax
0x180047e2b  mov     rcx, [rsp+78h+var_38]
0x180047e30  xor     rcx, rsp; StackCookie
0x180047e33  call    __security_check_cookie
0x180047e38  add     rsp, 58h
0x180047e3c  pop     rdi
0x180047e3d  pop     rsi
0x180047e3e  pop     rbp
0x180047e3f  pop     rbx
0x180047e40  retn
0x180047e41  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x180047e46  test    eax, eax
0x180047e48  jz      short loc_180047E7C
0x180047e4a  mov     eax, [rsp+78h+var_40]
0x180047e4e  cmp     eax, 66626473h
0x180047e53  jz      short loc_180047E7C
0x180047e55  test    sil, 2
0x180047e59  jnz     short loc_180047E7C
0x180047e5b  lea     r9, aMagicDoesNotMa; "Magic does not match a valid value: [0x"...
0x180047e62  mov     r8d, 0B5Ch
0x180047e68  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x180047e6f  mov     [rsp+78h+var_58], eax
0x180047e73  mov     ecx, edi
0x180047e75  call    AslLogCallPrintf
0x180047e7a  jmp     short loc_180047E14
0x180047e7c  mov     r8d, esi
0x180047e7f  lea     rdx, [rsp+78h+var_48]
0x180047e84  mov     rcx, rbx
0x180047e87  call    SdbpValidateAndApplyCompatFlags
0x180047e8c  test    eax, eax
0x180047e8e  jz      short loc_180047E14
0x180047e90  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x180047e95  test    eax, eax
0x180047e97  jz      short loc_180047EB4
0x180047e99  mov     rcx, rbx
0x180047e9c  call    SdbpValidateRootTagSizes
0x180047ea1  test    eax, eax
0x180047ea3  jns     short loc_180047EB4
0x180047ea5  lea     r9, aSdbpvalidatean_0; "SdbpValidateAndApplyCompatFlags failed "...
0x180047eac  mov     r8d, 0B68h
0x180047eb2  jmp     short loc_180047E68
0x180047eb4  mov     rax, rbx
0x180047eb7  jmp     loc_180047E2B
```
