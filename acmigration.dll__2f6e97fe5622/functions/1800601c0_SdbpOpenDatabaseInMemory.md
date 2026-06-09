# SdbpOpenDatabaseInMemory

- ea: `0x1800601c0`
- end: `0x180060328`
- name: `SdbpOpenDatabaseInMemory`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180061e78`

## callees

- `0x180001cf0`
- `0x1800543c0`
- `0x18005da8c`
- `0x1800601c0`
- `0x180060330`
- `0x180060674`
- `0x180060750`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180060204`
- `ntdll!RtlAllocateHeap` at `0x180060204`
- `ntdll!RtlFreeHeap` at `0x180060291`
- `ntdll!RtlFreeHeap` at `0x180060291`

## string_xrefs

- `0x180060264`: `Can't read database header`
- `0x18006021f`: `SdbpOpenDatabaseInMemory`
- `0x180060271`: `SdbpOpenDatabaseInMemory`
- `0x1800602d7`: `SdbpOpenDatabaseInMemory`
- `0x180060311`: `SdbpValidateAndApplyCompatFlags failed [%x]`

## pseudocode

```c
void *__fastcall SdbpOpenDatabaseInMemory(__int64 a1, int a2)
{
  _QWORD *Heap; // rax
  void *v5; // rbx
  int v7; // eax
  const char *v8; // r9
  __int64 v9; // r8
  __int64 v10; // [rsp+30h] [rbp-28h] BYREF
  int v11; // [rsp+38h] [rbp-20h]

  v10 = 0;
  v11 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v5 = Heap;
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
  if ( !(unsigned int)SdbpReadMappedData(Heap, 0, &v10, 12) )
  {
    AslLogCallPrintf(1, "SdbpOpenDatabaseInMemory", 2902, "Can't read database header");
LABEL_5:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    return 0;
  }
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    v7 = v11;
    if ( v11 != 1717724275 )
    {
      v8 = "Magic does not match a valid value: [0x%lx]";
      v9 = 2908;
LABEL_10:
      AslLogCallPrintf(1, "SdbpOpenDatabaseInMemory", v9, v8, v7);
      goto LABEL_5;
    }
  }
  if ( !(unsigned int)SdbpValidateAndApplyCompatFlags(v5, &v10) )
    goto LABEL_5;
  if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
  {
    v7 = SdbpValidateRootTagSizes(v5);
    if ( v7 < 0 )
    {
      v8 = "SdbpValidateAndApplyCompatFlags failed [%x]";
      v9 = 2920;
      goto LABEL_10;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800601c0  mov     [rsp+arg_0], rbx
0x1800601c5  mov     [rsp+arg_8], rsi
0x1800601ca  push    rdi
0x1800601cb  sub     rsp, 50h
0x1800601cf  mov     rax, cs:__security_cookie
0x1800601d6  xor     rax, rsp
0x1800601d9  mov     [rsp+58h+var_18], rax
0x1800601de  xor     eax, eax
0x1800601e0  mov     rsi, rcx
0x1800601e3  mov     rcx, gs:60h
0x1800601ec  mov     edi, edx
0x1800601ee  mov     r8d, 0A80h; Size
0x1800601f4  mov     [rsp+58h+var_28], rax
0x1800601f9  mov     [rsp+58h+var_20], eax
0x1800601fd  lea     edx, [rax+8]; Flags
0x180060200  mov     rcx, [rcx+30h]; HeapHandle
0x180060204  call    cs:__imp_RtlAllocateHeap
0x18006020a  mov     rbx, rax
0x18006020d  test    rax, rax
0x180060210  jnz     short loc_180060230
0x180060212  lea     r9, aFailedToAlloca_9; "Failed to allocate DB structure"
0x180060219  mov     r8d, 0B4Bh
0x18006021f  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x180060226  lea     ecx, [rax+1]
0x180060229  call    AslLogCallPrintf
0x18006022e  jmp     short loc_180060297
0x180060230  mov     [rax+14h], edi
0x180060233  lea     r8, [rsp+58h+var_28]
0x180060238  mov     edi, 1
0x18006023d  mov     dword ptr [rax+10h], 0
0x180060244  or      [rax+18h], edi
0x180060247  xor     edx, edx
0x180060249  mov     rcx, rbx
0x18006024c  mov     [rax+8], rsi
0x180060250  mov     qword ptr [rax], 0
0x180060257  lea     r9d, [rdi+0Bh]
0x18006025b  call    SdbpReadMappedData
0x180060260  test    eax, eax
0x180060262  jnz     short loc_1800602B6
0x180060264  lea     r9, aCanTReadDataba; "Can't read database header"
0x18006026b  mov     r8d, 0B56h
0x180060271  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x180060278  mov     ecx, edi
0x18006027a  call    AslLogCallPrintf
0x18006027f  mov     rcx, gs:60h
0x180060288  mov     r8, rbx; P
0x18006028b  xor     edx, edx; Flags
0x18006028d  mov     rcx, [rcx+30h]; HeapHandle
0x180060291  call    cs:__imp_RtlFreeHeap
0x180060297  xor     eax, eax
0x180060299  mov     rcx, [rsp+58h+var_18]
0x18006029e  xor     rcx, rsp; StackCookie
0x1800602a1  call    __security_check_cookie
0x1800602a6  mov     rbx, [rsp+58h+arg_0]
0x1800602ab  mov     rsi, [rsp+58h+arg_8]
0x1800602b0  add     rsp, 50h
0x1800602b4  pop     rdi
0x1800602b5  retn
0x1800602b6  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x1800602bb  test    eax, eax
0x1800602bd  jz      short loc_1800602EB
0x1800602bf  mov     eax, [rsp+58h+var_20]
0x1800602c3  cmp     eax, 66626473h
0x1800602c8  jz      short loc_1800602EB
0x1800602ca  lea     r9, aMagicDoesNotMa; "Magic does not match a valid value: [0x"...
0x1800602d1  mov     r8d, 0B5Ch
0x1800602d7  lea     rdx, aSdbpopendataba; "SdbpOpenDatabaseInMemory"
0x1800602de  mov     [rsp+58h+var_38], eax
0x1800602e2  mov     ecx, edi
0x1800602e4  call    AslLogCallPrintf
0x1800602e9  jmp     short loc_18006027F
0x1800602eb  lea     rdx, [rsp+58h+var_28]
0x1800602f0  mov     rcx, rbx
0x1800602f3  call    SdbpValidateAndApplyCompatFlags
0x1800602f8  test    eax, eax
0x1800602fa  jz      short loc_18006027F
0x1800602fc  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x180060301  test    eax, eax
0x180060303  jz      short loc_180060320
0x180060305  mov     rcx, rbx
0x180060308  call    SdbpValidateRootTagSizes
0x18006030d  test    eax, eax
0x18006030f  jns     short loc_180060320
0x180060311  lea     r9, aSdbpvalidatean_0; "SdbpValidateAndApplyCompatFlags failed "...
0x180060318  mov     r8d, 0B68h
0x18006031e  jmp     short loc_1800602D7
0x180060320  mov     rax, rbx
0x180060323  jmp     loc_180060299
```
