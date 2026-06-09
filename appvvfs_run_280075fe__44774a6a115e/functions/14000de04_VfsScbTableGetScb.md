# VfsScbTableGetScb

- ea: `0x14000de04`
- end: `0x14000df2e`
- name: `VfsScbTableGetScb`
- size: `298`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400037ac`
- `0x140003978`
- `0x14000f188`

## callees

- `0x14000de04`
- `0x140013b00`
- `0x140014000`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000de96`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000de96`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14000deab`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14000deab`
- `ntoskrnl!RtlCopySid` at `0x14000de75`
- `ntoskrnl!RtlCopySid` at `0x14000de75`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000def7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000def7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000deeb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000deeb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000de85`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000de85`

## pseudocode

```c
__int64 __fastcall VfsScbTableGetScb(__int64 a1, _OWORD *a2, void *a3, char a4, _BYTE *a5)
{
  __int64 v9; // rdi
  __int128 v10; // xmm1
  struct _ERESOURCE *v11; // rbx
  _QWORD *v12; // rax
  _OWORD Buffer[7]; // [rsp+20h] [rbp-A8h] BYREF

  memset(Buffer, 0, 0x64u);
  v9 = 0;
  if ( a5 )
    *a5 = 0;
  v10 = a2[1];
  Buffer[0] = *a2;
  Buffer[1] = v10;
  RtlCopySid(0x44u, &Buffer[2], a3);
  v11 = *(struct _ERESOURCE **)(a1 + 8);
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite(v11, 1u);
  v12 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 16), Buffer);
  if ( v12 )
  {
    v9 = v12[14];
    if ( (*(_DWORD *)(v9 + 272) & 1) != 0 && a5 )
    {
      *a5 = 1;
      v9 = 0;
    }
    else if ( v9 && a4 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 276));
    }
  }
  ExReleaseResourceLite(*(PERESOURCE *)(a1 + 8));
  KeLeaveCriticalRegion();
  return v9;
}

```

## disassembly

```asm
0x14000de04  mov     [rsp+arg_8], rbx
0x14000de09  push    rbp
0x14000de0a  push    rsi
0x14000de0b  push    rdi
0x14000de0c  push    r14
0x14000de0e  push    r15
0x14000de10  sub     rsp, 0A0h
0x14000de17  mov     rax, cs:__security_cookie
0x14000de1e  xor     rax, rsp
0x14000de21  mov     [rsp+0C8h+var_38], rax
0x14000de29  mov     rsi, [rsp+0C8h+arg_20]
0x14000de31  mov     rbx, rdx
0x14000de34  xor     edx, edx; Val
0x14000de36  mov     r15, r8
0x14000de39  mov     rbp, rcx
0x14000de3c  mov     r14b, r9b
0x14000de3f  lea     rcx, [rsp+0C8h+Buffer]; void *
0x14000de44  lea     r8d, [rdx+64h]; Size
0x14000de48  call    memset
0x14000de4d  xor     edi, edi
0x14000de4f  test    rsi, rsi
0x14000de52  jz      short loc_14000DE57
0x14000de54  mov     [rsi], dil
0x14000de57  movups  xmm0, xmmword ptr [rbx]
0x14000de5a  mov     r8, r15; SourceSid
0x14000de5d  lea     rdx, [rsp+0C8h+DestinationSid]; DestinationSid
0x14000de62  movups  xmm1, xmmword ptr [rbx+10h]
0x14000de66  mov     ecx, 44h ; 'D'; DestinationSidLength
0x14000de6b  movaps  [rsp+0C8h+Buffer], xmm0
0x14000de70  movaps  [rsp+0C8h+var_98], xmm1
0x14000de75  call    cs:__imp_RtlCopySid
0x14000de7c  nop     dword ptr [rax+rax+00h]
0x14000de81  mov     rbx, [rbp+8]
0x14000de85  call    cs:__imp_KeEnterCriticalRegion
0x14000de8c  nop     dword ptr [rax+rax+00h]
0x14000de91  mov     dl, 1; Wait
0x14000de93  mov     rcx, rbx; Resource
0x14000de96  call    cs:__imp_ExAcquireResourceSharedLite
0x14000de9d  nop     dword ptr [rax+rax+00h]
0x14000dea2  lea     rcx, [rbp+10h]; Table
0x14000dea6  lea     rdx, [rsp+0C8h+Buffer]; Buffer
0x14000deab  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14000deb2  nop     dword ptr [rax+rax+00h]
0x14000deb7  test    rax, rax
0x14000deba  jz      short loc_14000DEE7
0x14000debc  mov     rdi, [rax+70h]
0x14000dec0  mov     eax, [rdi+110h]
0x14000dec6  test    al, 1
0x14000dec8  jz      short loc_14000DED6
0x14000deca  test    rsi, rsi
0x14000decd  jz      short loc_14000DED6
0x14000decf  mov     byte ptr [rsi], 1
0x14000ded2  xor     edi, edi
0x14000ded4  jmp     short loc_14000DEE7
0x14000ded6  test    rdi, rdi
0x14000ded9  jz      short loc_14000DEE7
0x14000dedb  test    r14b, r14b
0x14000dede  jz      short loc_14000DEE7
0x14000dee0  lock inc dword ptr [rdi+114h]
0x14000dee7  mov     rcx, [rbp+8]; Resource
0x14000deeb  call    cs:__imp_ExReleaseResourceLite
0x14000def2  nop     dword ptr [rax+rax+00h]
0x14000def7  call    cs:__imp_KeLeaveCriticalRegion
0x14000defe  nop     dword ptr [rax+rax+00h]
0x14000df03  mov     rax, rdi
0x14000df06  mov     rcx, [rsp+0C8h+var_38]
0x14000df0e  xor     rcx, rsp; StackCookie
0x14000df11  call    __security_check_cookie
0x14000df16  mov     rbx, [rsp+0C8h+arg_8]
0x14000df1e  add     rsp, 0A0h
0x14000df25  pop     r15
0x14000df27  pop     r14
0x14000df29  pop     rdi
0x14000df2a  pop     rsi
0x14000df2b  pop     rbp
0x14000df2c  retn
```
