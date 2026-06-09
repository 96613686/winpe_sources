# SrpIsWindowsSigned

- ea: `0x140023934`
- end: `0x140023a3a`
- name: `SrpIsWindowsSigned`
- size: `262`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140030ff0`
- `0x140034550`

## callees

- `0x140023934`
- `0x140026088`
- `0x140026140`

## import_xrefs

- `ntoskrnl!SeCompareSigningLevels` at `0x14002398d`
- `ntoskrnl!SeCompareSigningLevels` at `0x140023a13`
- `ntoskrnl!SeCompareSigningLevels` at `0x14002398d`
- `ntoskrnl!SeCompareSigningLevels` at `0x140023a13`
- `ntoskrnl!ZwGetCachedSigningLevel` at `0x140023978`
- `ntoskrnl!ZwGetCachedSigningLevel` at `0x1400239fe`
- `ntoskrnl!ZwGetCachedSigningLevel` at `0x140023978`
- `ntoskrnl!ZwGetCachedSigningLevel` at `0x1400239fe`
- `ntoskrnl!ZwSetCachedSigningLevel` at `0x1400239cd`
- `ntoskrnl!ZwSetCachedSigningLevel` at `0x1400239cd`

## pseudocode

```c
char __fastcall SrpIsWindowsSigned(__int64 a1, __int64 a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  char v5; // bl
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // rcx
  _DWORD v10[4]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v11; // [rsp+68h] [rbp+28h] BYREF
  char v12; // [rsp+70h] [rbp+30h] BYREF
  char v13; // [rsp+78h] [rbp+38h] BYREF

  v11 = a2;
  v10[0] = 0;
  v12 = 0;
  v13 = 0;
  if ( (int)ZwGetCachedSigningLevel(a2, v10, &v12, 0, 0, 0) >= 0 )
  {
    LOBYTE(v4) = v12;
    LOBYTE(v3) = 12;
    if ( (unsigned int)SeCompareSigningLevels(v4, v3) )
      return 1;
  }
  v5 = 0;
  AiSigningLevelCacheExists(a1, &v13);
  if ( !v13 )
  {
    LOBYTE(v6) = 12;
    if ( (int)ZwSetCachedSigningLevel(5, v6, &v11) < 0
      || (int)ZwGetCachedSigningLevel(v11, v10, &v12, 0, 0, 0) < 0
      || (LOBYTE(v8) = v12, LOBYTE(v7) = 12, !(unsigned int)SeCompareSigningLevels(v8, v7)) )
    {
      AiSetSigningLevelCache(a1);
      return v5;
    }
    return 1;
  }
  return v5;
}

```

## disassembly

```asm
0x140023934  mov     [rsp-18h+arg_8], rdx
0x140023939  push    rbp
0x14002393a  push    rbx
0x14002393b  push    rdi
0x14002393c  mov     rbp, rsp
0x14002393f  sub     rsp, 40h
0x140023943  mov     rax, rdx
0x140023946  mov     [rsp+40h+var_18], 0
0x14002394f  mov     rdi, rcx
0x140023952  mov     [rbp+var_10], 0
0x140023959  mov     rcx, rax
0x14002395c  mov     [rbp+arg_10], 0
0x140023960  xor     r9d, r9d
0x140023963  mov     [rbp+arg_18], 0
0x140023967  lea     r8, [rbp+arg_10]
0x14002396b  mov     [rsp+40h+var_20], 0
0x140023974  lea     rdx, [rbp+var_10]
0x140023978  call    cs:__imp_ZwGetCachedSigningLevel
0x14002397f  nop     dword ptr [rax+rax+00h]
0x140023984  test    eax, eax
0x140023986  js      short loc_1400239A1
0x140023988  mov     cl, [rbp+arg_10]
0x14002398b  mov     dl, 0Ch
0x14002398d  call    cs:__imp_SeCompareSigningLevels
0x140023994  nop     dword ptr [rax+rax+00h]
0x140023999  test    eax, eax
0x14002399b  jnz     loc_140023A23
0x1400239a1  lea     rdx, [rbp+arg_18]
0x1400239a5  mov     rcx, rdi
0x1400239a8  xor     bl, bl
0x1400239aa  call    AiSigningLevelCacheExists
0x1400239af  cmp     [rbp+arg_18], bl
0x1400239b2  jnz     short loc_140023A2F
0x1400239b4  mov     rax, [rbp+arg_8]
0x1400239b8  lea     r8, [rbp+arg_8]
0x1400239bc  mov     r9d, 1
0x1400239c2  mov     [rsp+40h+var_20], rax
0x1400239c7  mov     dl, 0Ch
0x1400239c9  lea     ecx, [r9+4]
0x1400239cd  call    cs:__imp_ZwSetCachedSigningLevel
0x1400239d4  nop     dword ptr [rax+rax+00h]
0x1400239d9  test    eax, eax
0x1400239db  js      short loc_140023A27
0x1400239dd  mov     rcx, [rbp+arg_8]
0x1400239e1  lea     r8, [rbp+arg_10]
0x1400239e5  mov     [rsp+40h+var_18], 0
0x1400239ee  lea     rdx, [rbp+var_10]
0x1400239f2  xor     r9d, r9d
0x1400239f5  mov     [rsp+40h+var_20], 0
0x1400239fe  call    cs:__imp_ZwGetCachedSigningLevel
0x140023a05  nop     dword ptr [rax+rax+00h]
0x140023a0a  test    eax, eax
0x140023a0c  js      short loc_140023A27
0x140023a0e  mov     cl, [rbp+arg_10]
0x140023a11  mov     dl, 0Ch
0x140023a13  call    cs:__imp_SeCompareSigningLevels
0x140023a1a  nop     dword ptr [rax+rax+00h]
0x140023a1f  test    eax, eax
0x140023a21  jz      short loc_140023A27
0x140023a23  mov     bl, 1
0x140023a25  jmp     short loc_140023A2F
0x140023a27  mov     rcx, rdi
0x140023a2a  call    AiSetSigningLevelCache
0x140023a2f  mov     al, bl
0x140023a31  add     rsp, 40h
0x140023a35  pop     rdi
0x140023a36  pop     rbx
0x140023a37  pop     rbp
0x140023a38  retn
```
