# BCryptIumGetClaimPaddingInfo

- ea: `0x140012aac`
- end: `0x140012bd9`
- name: `BCryptIumGetClaimPaddingInfo`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140013124`

## callees

- `0x140012aac`
- `0x140037a1c`
- `0x140037b10`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140012b41`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x140012b41`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140012bbd`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140012bbd`

## string_xrefs

- `0x140012baf`: `onecore\ds\security\cryptoapi\ncrypt\ium\trustlet\bcryptiumkeyattest.cxx`

## pseudocode

```c
__int64 __fastcall BCryptIumGetClaimPaddingInfo(void *a1, _QWORD *a2, _DWORD *a3, _QWORD *a4)
{
  unsigned int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rax
  int v9; // esi
  int IsRsaKey; // eax

  *a4 = 0;
  *a3 = 0;
  if ( !a2 )
  {
    v5 = -1073741595;
    v6 = 676;
    v7 = 3221225701LL;
LABEL_14:
    VBS_ATTEST_TRACE_ERROR_IN(v7, "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\trustlet\\bcryptiumkeyattest.cxx", v6);
    goto LABEL_15;
  }
  v8 = a2[2];
  if ( v8 )
    v9 = **(_DWORD **)(v8 + 8);
  else
    v9 = 0;
  IsRsaKey = VBSAttestationIsRsaKey(a1);
  v5 = IsRsaKey;
  if ( IsRsaKey < 0 )
  {
    v6 = 686;
    v7 = (unsigned int)IsRsaKey;
    goto LABEL_14;
  }
  if ( v9 )
  {
    v6 = 693;
LABEL_13:
    v7 = 3221225485LL;
    v5 = -1073741811;
    goto LABEL_14;
  }
  if ( a2[3] || a2[4] )
  {
    v6 = 729;
    goto LABEL_13;
  }
LABEL_15:
  LocalFree(0);
  return v5;
}

```

## disassembly

```asm
0x140012aac  mov     [rsp+arg_0], rbx
0x140012ab1  mov     [rsp+arg_10], rsi
0x140012ab6  push    rdi
0x140012ab7  push    r14
0x140012ab9  push    r15
0x140012abb  sub     rsp, 20h
0x140012abf  mov     [rsp+38h+arg_8], 0
0x140012ac4  mov     r14, r9
0x140012ac7  mov     qword ptr [r9], 0
0x140012ace  mov     r15, r8
0x140012ad1  mov     dword ptr [r8], 0
0x140012ad8  mov     rdi, rdx
0x140012adb  test    rdx, rdx
0x140012ade  jnz     short loc_140012AF2
0x140012ae0  mov     ebx, 0C00000E5h
0x140012ae5  mov     r8d, 2A4h
0x140012aeb  mov     ecx, ebx; hObject
0x140012aed  jmp     loc_140012BAF
0x140012af2  mov     rax, [rdx+10h]
0x140012af6  test    rax, rax
0x140012af9  jz      short loc_140012B03
0x140012afb  mov     rax, [rax+8]
0x140012aff  mov     esi, [rax]
0x140012b01  jmp     short loc_140012B05
0x140012b03  xor     esi, esi
0x140012b05  lea     rdx, [rsp+38h+arg_8]
0x140012b0a  call    VBSAttestationIsRsaKey
0x140012b0f  mov     ebx, eax
0x140012b11  test    eax, eax
0x140012b13  jns     short loc_140012B22
0x140012b15  mov     r8d, 2AEh
0x140012b1b  mov     ecx, eax
0x140012b1d  jmp     loc_140012BAF
0x140012b22  cmp     [rsp+38h+arg_8], 0
0x140012b27  jz      short loc_140012B88
0x140012b29  cmp     esi, 8
0x140012b2c  jnz     short loc_140012B8C
0x140012b2e  cmp     qword ptr [rdi+18h], 0
0x140012b33  jz      short loc_140012B80
0x140012b35  cmp     qword ptr [rdi+20h], 0
0x140012b3a  jz      short loc_140012B80
0x140012b3c  lea     edx, [rsi+8]; uBytes
0x140012b3f  xor     ecx, ecx; uFlags
0x140012b41  call    cs:__imp_LocalAlloc
0x140012b47  mov     rdx, rax
0x140012b4a  test    rax, rax
0x140012b4d  jnz     short loc_140012B5C
0x140012b4f  mov     ebx, 0C0000017h
0x140012b54  mov     r8d, 2C9h
0x140012b5a  jmp     short loc_140012AEB
0x140012b5c  mov     rax, [rdi+18h]
0x140012b60  mov     dword ptr [r15], 8
0x140012b67  mov     [r14], rdx
0x140012b6a  mov     rcx, [rax+8]
0x140012b6e  mov     rax, [rdi+20h]
0x140012b72  mov     [rdx], rcx
0x140012b75  mov     rcx, [rax+8]
0x140012b79  mov     eax, [rcx]
0x140012b7b  mov     [rdx+8], eax
0x140012b7e  jmp     short loc_140012BBB
0x140012b80  mov     r8d, 2C0h
0x140012b86  jmp     short loc_140012BA8
0x140012b88  test    esi, esi
0x140012b8a  jz      short loc_140012B94
0x140012b8c  mov     r8d, 2B5h
0x140012b92  jmp     short loc_140012BA8
0x140012b94  cmp     qword ptr [rdi+18h], 0
0x140012b99  jnz     short loc_140012BA2
0x140012b9b  cmp     qword ptr [rdi+20h], 0
0x140012ba0  jz      short loc_140012BBB
0x140012ba2  mov     r8d, 2D9h
0x140012ba8  mov     ecx, 0C000000Dh
0x140012bad  mov     ebx, ecx
0x140012baf  lea     rdx, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x140012bb6  call    VBS_ATTEST_TRACE_ERROR_IN
0x140012bbb  xor     ecx, ecx; hMem
0x140012bbd  call    cs:__imp_LocalFree
0x140012bc3  mov     rsi, [rsp+38h+arg_10]
0x140012bc8  mov     eax, ebx
0x140012bca  mov     rbx, [rsp+38h+arg_0]
0x140012bcf  add     rsp, 20h
0x140012bd3  pop     r15
0x140012bd5  pop     r14
0x140012bd7  pop     rdi
0x140012bd8  retn
```
