# AiInitializeSoftwarePathMacroList

- ea: `0x140028040`
- end: `0x1400281ab`
- name: `AiInitializeSoftwarePathMacroList`
- size: `363`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140027ebc`
- `0x1400333b0`

## callees

- `0x140028040`
- `0x1400281b4`
- `0x1400284d8`
- `0x14002948c`
- `0x1400328b0`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028191`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140028191`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140028064`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140028064`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140028079`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140028079`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140028185`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140028185`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400280d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400280e8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002811b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400280d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400280e8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002811b`

## pseudocode

```c
__int64 AiInitializeSoftwarePathMacroList()
{
  __int64 v0; // rcx
  int v1; // ebx
  unsigned int i; // esi
  __int64 v3; // rdi
  int v4; // eax
  __int128 v6; // [rsp+20h] [rbp-40h] BYREF
  struct _UNICODE_STRING v7; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING v9; // [rsp+50h] [rbp-10h] BYREF

  v9 = 0;
  DestinationString = 0;
  v7 = 0;
  v6 = 0;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&qword_1400195B0, 0);
  if ( AipPathMacroList )
  {
    v1 = 0;
  }
  else
  {
    for ( i = 0; i < 2; ++i )
    {
      v3 = 4LL * i;
      if ( !LODWORD(AipRegistryPathMacros[v3 + 3]) && (!HIDWORD(AipRegistryPathMacros[v3 + 3]) || dword_140019584) )
      {
        RtlInitUnicodeString(&DestinationString, AipRegistryPathMacros[v3 + 1]);
        RtlInitUnicodeString(&v7, AipRegistryPathMacros[v3 + 2]);
        *((_QWORD *)&v6 + 1) = 0;
        v4 = AiRegReadStringValue(0, &DestinationString, &v7, &v6);
        if ( v4 < 0 )
        {
          v1 = 0;
          if ( v4 != -1073741772 )
            v1 = v4;
          goto LABEL_18;
        }
        RtlInitUnicodeString(&v9, AipRegistryPathMacros[v3]);
        v1 = AipAddPathMacro(&v9, &v6, 14);
        if ( v1 < 0 )
        {
          AiFree(*((void **)&v6 + 1));
          goto LABEL_18;
        }
        LODWORD(AipRegistryPathMacros[v3 + 3]) = 1;
      }
    }
    v1 = AipExpandPathMacros(v0);
    if ( v1 >= 0 )
      AipPathMacroList = 1;
  }
LABEL_18:
  ExReleasePushLockExclusiveEx(&qword_1400195B0, 0);
  KeLeaveCriticalRegion();
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140028040  push    rbp
0x140028042  push    rbx
0x140028043  push    rsi
0x140028044  push    rdi
0x140028045  push    r15
0x140028047  mov     rbp, rsp
0x14002804a  sub     rsp, 60h
0x14002804e  xorps   xmm0, xmm0
0x140028051  xorps   xmm1, xmm1
0x140028054  movups  xmmword ptr [rbp+var_10.Length], xmm0
0x140028058  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14002805c  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x140028060  movups  [rbp+var_40], xmm1
0x140028064  call    cs:__imp_KeEnterCriticalRegion
0x14002806b  nop     dword ptr [rax+rax+00h]
0x140028070  xor     edx, edx
0x140028072  lea     rcx, qword_1400195B0
0x140028079  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140028080  nop     dword ptr [rax+rax+00h]
0x140028085  cmp     cs:AipPathMacroList, 0
0x14002808c  jz      short loc_140028095
0x14002808e  xor     ebx, ebx
0x140028090  jmp     loc_14002817C
0x140028095  xor     esi, esi
0x140028097  lea     r15, AipRegistryPathMacros
0x14002809e  cmp     esi, 2
0x1400280a1  jnb     loc_140028167
0x1400280a7  mov     edi, esi
0x1400280a9  shl     rdi, 5
0x1400280ad  cmp     dword ptr [rdi+r15+18h], 0
0x1400280b3  jnz     loc_140028149
0x1400280b9  cmp     dword ptr [rdi+r15+1Ch], 0
0x1400280bf  jz      short loc_1400280CA
0x1400280c1  cmp     cs:dword_140019584, 0
0x1400280c8  jz      short loc_140028149
0x1400280ca  mov     rdx, [rdi+r15+8]; SourceString
0x1400280cf  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400280d3  call    cs:__imp_RtlInitUnicodeString
0x1400280da  nop     dword ptr [rax+rax+00h]
0x1400280df  mov     rdx, [rdi+r15+10h]; SourceString
0x1400280e4  lea     rcx, [rbp+var_30]; DestinationString
0x1400280e8  call    cs:__imp_RtlInitUnicodeString
0x1400280ef  nop     dword ptr [rax+rax+00h]
0x1400280f4  lea     r9, [rbp+var_40]
0x1400280f8  mov     qword ptr [rbp+var_40+8], 0
0x140028100  lea     r8, [rbp+var_30]
0x140028104  xor     ecx, ecx
0x140028106  lea     rdx, [rbp+DestinationString]
0x14002810a  call    AiRegReadStringValue
0x14002810f  test    eax, eax
0x140028111  js      short loc_14002815B
0x140028113  mov     rdx, [rdi+r15]; SourceString
0x140028117  lea     rcx, [rbp+var_10]; DestinationString
0x14002811b  call    cs:__imp_RtlInitUnicodeString
0x140028122  nop     dword ptr [rax+rax+00h]
0x140028127  mov     r8d, 0Eh
0x14002812d  lea     rdx, [rbp+var_40]
0x140028131  lea     rcx, [rbp+var_10]
0x140028135  call    AipAddPathMacro
0x14002813a  mov     ebx, eax
0x14002813c  test    eax, eax
0x14002813e  js      short loc_140028150
0x140028140  mov     dword ptr [rdi+r15+18h], 1
0x140028149  inc     esi
0x14002814b  jmp     loc_14002809E
0x140028150  mov     rcx, qword ptr [rbp+var_40+8]
0x140028154  call    AiFree
0x140028159  jmp     short loc_14002817C
0x14002815b  xor     ebx, ebx
0x14002815d  cmp     eax, 0C0000034h
0x140028162  cmovnz  ebx, eax
0x140028165  jmp     short loc_14002817C
0x140028167  call    AipExpandPathMacros
0x14002816c  mov     ebx, eax
0x14002816e  test    eax, eax
0x140028170  js      short loc_14002817C
0x140028172  mov     cs:AipPathMacroList, 1
0x14002817c  xor     edx, edx
0x14002817e  lea     rcx, qword_1400195B0
0x140028185  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14002818c  nop     dword ptr [rax+rax+00h]
0x140028191  call    cs:__imp_KeLeaveCriticalRegion
0x140028198  nop     dword ptr [rax+rax+00h]
0x14002819d  mov     eax, ebx
0x14002819f  add     rsp, 60h
0x1400281a3  pop     r15
0x1400281a5  pop     rdi
0x1400281a6  pop     rsi
0x1400281a7  pop     rbx
0x1400281a8  pop     rbp
0x1400281a9  retn
```
