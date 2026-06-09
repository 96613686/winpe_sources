# SdbpOpenDatabaseInMemory

- ea: `0x140038fd8`
- end: `0x14003913c`
- name: `SdbpOpenDatabaseInMemory`
- size: `356`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003bd8c`

## callees

- `0x140037088`
- `0x140038fd8`
- `0x140039144`
- `0x1400393a4`
- `0x1400394b4`
- `0x14003bf18`
- `0x14003c368`
- `0x140045f30`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140039019`
- `ntdll!RtlAllocateHeap` at `0x140039019`

## string_xrefs

- `0x140039079`: `Can't read database header`
- `0x140039034`: `SdbpOpenDatabaseInMemory`
- `0x140039086`: `SdbpOpenDatabaseInMemory`
- `0x1400390e8`: `SdbpOpenDatabaseInMemory`
- `0x140039125`: `SdbpValidateAndApplyCompatFlags failed [%x]`

## pseudocode

```c
void *__fastcall SdbpOpenDatabaseInMemory(__int64 a1, int a2, unsigned int a3)
{
  _QWORD *Heap; // rax
  void *v7; // rbx
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
  *((_DWORD *)Heap + 5) = a2;
  *((_DWORD *)Heap + 4) = 0;
  *((_DWORD *)Heap + 6) |= 1u;
  Heap[1] = a1;
  *Heap = 0;
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
0x140038fd8  push    rbx
0x140038fda  push    rbp
0x140038fdb  push    rsi
0x140038fdc  push    rdi
0x140038fdd  sub     rsp, 58h
0x140038fe1  mov     rax, cs:__security_cookie
0x140038fe8  xor     rax, rsp
0x140038feb  mov     [rsp+78h+var_38], rax
0x140038ff0  xor     eax, eax
0x140038ff2  mov     rbp, rcx
0x140038ff5  mov     rcx, gs:60h
0x140038ffe  mov     esi, r8d
0x140039001  mov     edi, edx
0x140039003  mov     [rsp+78h+var_48], rax
0x140039008  mov     r8d, 0A80h; Size
0x14003900e  mov     [rsp+78h+var_40], eax
0x140039012  lea     edx, [rax+8]; Flags
0x140039015  mov     rcx, [rcx+30h]; HeapHandle
0x140039019  call    cs:__imp_RtlAllocateHeap
0x14003901f  mov     rbx, rax
0x140039022  test    rax, rax
0x140039025  jnz     short loc_140039045
0x140039027  lea     r9, aFailedToAlloca_10; "Failed to allocate DB structure"
0x14003902e  mov     r8d, 0B4Bh
0x140039034  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x14003903b  lea     ecx, [rax+1]
0x14003903e  call    AslLogCallPrintf
0x140039043  jmp     short loc_1400390A9
0x140039045  mov     [rax+14h], edi
0x140039048  lea     r8, [rsp+78h+var_48]
0x14003904d  mov     edi, 1
0x140039052  mov     dword ptr [rax+10h], 0
0x140039059  or      [rax+18h], edi
0x14003905c  xor     edx, edx
0x14003905e  mov     rcx, rbx
0x140039061  mov     [rax+8], rbp
0x140039065  mov     qword ptr [rax], 0
0x14003906c  lea     r9d, [rdi+0Bh]
0x140039070  call    SdbpReadMappedData
0x140039075  test    eax, eax
0x140039077  jnz     short loc_1400390C1
0x140039079  lea     r9, aCanTReadDataba; "Can't read database header"
0x140039080  mov     r8d, 0B56h
0x140039086  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x14003908d  mov     ecx, edi
0x14003908f  call    AslLogCallPrintf
0x140039094  mov     rcx, gs:60h
0x14003909d  mov     rdx, rbx
0x1400390a0  mov     rcx, [rcx+30h]
0x1400390a4  call    AslFree
0x1400390a9  xor     eax, eax
0x1400390ab  mov     rcx, [rsp+78h+var_38]
0x1400390b0  xor     rcx, rsp; StackCookie
0x1400390b3  call    __security_check_cookie
0x1400390b8  add     rsp, 58h
0x1400390bc  pop     rdi
0x1400390bd  pop     rsi
0x1400390be  pop     rbp
0x1400390bf  pop     rbx
0x1400390c0  retn
0x1400390c1  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x1400390c6  test    eax, eax
0x1400390c8  jz      short loc_1400390FC
0x1400390ca  mov     eax, [rsp+78h+var_40]
0x1400390ce  cmp     eax, 66626473h
0x1400390d3  jz      short loc_1400390FC
0x1400390d5  test    sil, 2
0x1400390d9  jnz     short loc_1400390FC
0x1400390db  lea     r9, aMagicDoesNotMa; "Magic does not match a valid value: [0x"...
0x1400390e2  mov     r8d, 0B5Ch
0x1400390e8  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x1400390ef  mov     [rsp+78h+var_58], eax
0x1400390f3  mov     ecx, edi
0x1400390f5  call    AslLogCallPrintf
0x1400390fa  jmp     short loc_140039094
0x1400390fc  mov     r8d, esi
0x1400390ff  lea     rdx, [rsp+78h+var_48]
0x140039104  mov     rcx, rbx
0x140039107  call    SdbpValidateAndApplyCompatFlags
0x14003910c  test    eax, eax
0x14003910e  jz      short loc_140039094
0x140039110  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x140039115  test    eax, eax
0x140039117  jz      short loc_140039134
0x140039119  mov     rcx, rbx
0x14003911c  call    SdbpValidateRootTagSizes
0x140039121  test    eax, eax
0x140039123  jns     short loc_140039134
0x140039125  lea     r9, aSdbpvalidatean_0; "SdbpValidateAndApplyCompatFlags failed "...
0x14003912c  mov     r8d, 0B68h
0x140039132  jmp     short loc_1400390E8
0x140039134  mov     rax, rbx
0x140039137  jmp     loc_1400390AB
```
