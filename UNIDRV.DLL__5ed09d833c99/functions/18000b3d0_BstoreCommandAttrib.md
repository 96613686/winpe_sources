# BstoreCommandAttrib

- ea: `0x18000b3d0`
- end: `0x18000b50f`
- name: `BstoreCommandAttrib`
- size: `319`
- prototype: `_BOOL8 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a2d0`

## callees

- `0x180007150`
- `0x18000a45c`
- `0x18000b3d0`
- `0x18000b800`
- `0x180045aa4`

## string_xrefs

- `0x18000b44b`: `BstoreCommandAttrib`
- `0x18000b4f7`: `BstoreCommandAttrib`
- `0x18000b4ce`: `syntax err: the CmdSelect specifier can only be used inside an Option construct.`
- `0x18000b4f0`: `Internal error: BstoreCommandAttrib - invalid CommandID.`
- `0x18000b440`: `unrecognized Unidrv command name: *%0.*s.`

## pseudocode

```c
_BOOL8 __fastcall BstoreCommandAttrib(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // ecx
  unsigned int v6; // edx
  __int64 v7; // rsi
  int v8; // ecx
  __int64 v9; // r8
  unsigned int i; // eax
  __int64 v11; // rcx
  int v12; // edx
  unsigned int *v13; // rdx
  unsigned int v15; // [rsp+58h] [rbp+10h] BYREF

  v15 = 0;
  v4 = 0;
  v6 = *(_DWORD *)(a2 + 612);
  while ( 1 )
  {
    if ( v4 >= v6 )
      goto LABEL_22;
    a3 = *(_QWORD *)(a2 + 600);
    v7 = v6 - v4 - 1;
    if ( *(_DWORD *)(a3 + 8 * v7) == 13 )
      break;
    ++v4;
  }
  v8 = *(_DWORD *)(a3 + 8 * v7 + 4);
  if ( v8 == -1 )
  {
LABEL_22:
    vIdentifySource((_DWORD *)a1, a2, a3);
    WriteDbgTraceErrorGpd((__int64)"BstoreCommandAttrib", "Internal error: BstoreCommandAttrib - invalid CommandID.");
    return 0;
  }
  if ( !(unsigned int)BconvertSymCmdIDtoUnidrvID(v8, &v15, a2) )
  {
    vIdentifySource((_DWORD *)a1, a2, v9);
    WriteDbgTraceErrorGpd(
      (__int64)"BstoreCommandAttrib",
      "unrecognized Unidrv command name: *%0.*s.",
      *(_DWORD *)(a1 + 32),
      *(const char **)(a1 + 24));
    return 0;
  }
  if ( v15 == -2 )
  {
    for ( i = 0; i < (unsigned int)v7; ++i )
    {
      v9 = *(_QWORD *)(a2 + 600);
      v11 = i + 1;
      if ( *(_DWORD *)(v9 + 8LL * i) == 2 )
      {
        v12 = 0;
        if ( (unsigned int)v11 < (unsigned int)v7 )
        {
          do
          {
            if ( *(_DWORD *)(v9 + 8 * v11) == 3 )
              v12 = 1;
            v11 = (unsigned int)(v11 + 1);
          }
          while ( (unsigned int)v11 < (unsigned int)v7 );
          if ( v12 )
          {
            v13 = (unsigned int *)(396LL * *(unsigned int *)(v9 + 8LL * i + 4) + *(_QWORD *)(a2 + 264) + 132LL);
            return BaddBranchToTree(a1, v13, a2);
          }
        }
        break;
      }
    }
    vIdentifySource((_DWORD *)a1, a2, v9);
    WriteDbgTraceErrorGpd(
      (__int64)"BstoreCommandAttrib",
      "syntax err: the CmdSelect specifier can only be used inside an Option construct.");
    return 0;
  }
  v13 = (unsigned int *)(*(_QWORD *)(a2 + 48) + 4LL * v15);
  return BaddBranchToTree(a1, v13, a2);
}

```

## disassembly

```asm
0x18000b3d0  push    rbx
0x18000b3d2  push    rbp
0x18000b3d3  push    rsi
0x18000b3d4  push    rdi
0x18000b3d5  sub     rsp, 28h
0x18000b3d9  mov     rdi, rcx
0x18000b3dc  mov     [rsp+48h+arg_8], 0
0x18000b3e4  xor     ecx, ecx
0x18000b3e6  mov     rbx, rdx
0x18000b3e9  mov     edx, [rdx+264h]
0x18000b3ef  lea     ebp, [rcx+1]
0x18000b3f2  cmp     ecx, edx
0x18000b3f4  jnb     loc_18000B4E5
0x18000b3fa  mov     r8, [rbx+258h]
0x18000b401  mov     esi, edx
0x18000b403  sub     esi, ecx
0x18000b405  dec     esi
0x18000b407  cmp     dword ptr [r8+rsi*8], 0Dh
0x18000b40c  jz      short loc_18000B412
0x18000b40e  add     ecx, ebp
0x18000b410  jmp     short loc_18000B3F2
0x18000b412  mov     ecx, [r8+rsi*8+4]
0x18000b417  cmp     ecx, 0FFFFFFFFh
0x18000b41a  jz      loc_18000B4E5
0x18000b420  mov     r8, rbx
0x18000b423  lea     rdx, [rsp+48h+arg_8]
0x18000b428  call    BconvertSymCmdIDtoUnidrvID
0x18000b42d  test    eax, eax
0x18000b42f  jnz     short loc_18000B45C
0x18000b431  mov     rdx, rbx
0x18000b434  mov     rcx, rdi
0x18000b437  call    vIdentifySource
0x18000b43c  mov     r9, [rdi+18h]
0x18000b440  lea     rdx, aUnrecognizedUn; "unrecognized Unidrv command name: *%0.*"...
0x18000b447  mov     r8d, [rdi+20h]
0x18000b44b  lea     rcx, aBstorecommanda; "BstoreCommandAttrib"
0x18000b452  call    WriteDbgTraceErrorGpd
0x18000b457  jmp     loc_18000B503
0x18000b45c  cmp     [rsp+48h+arg_8], 0FFFFFFFEh
0x18000b461  jnz     short loc_18000B4D7
0x18000b463  xor     eax, eax
0x18000b465  cmp     eax, esi
0x18000b467  jnb     short loc_18000B4C3
0x18000b469  mov     r8, [rbx+258h]
0x18000b470  lea     ecx, [rax+1]
0x18000b473  mov     r9d, eax
0x18000b476  cmp     dword ptr [r8+r9*8], 2
0x18000b47b  jz      short loc_18000B481
0x18000b47d  mov     eax, ecx
0x18000b47f  jmp     short loc_18000B465
0x18000b481  xor     edx, edx
0x18000b483  cmp     ecx, esi
0x18000b485  jnb     short loc_18000B4C3
0x18000b487  cmp     dword ptr [r8+rcx*8], 3
0x18000b48c  cmovz   edx, ebp
0x18000b48f  add     ecx, ebp
0x18000b491  cmp     ecx, esi
0x18000b493  jb      short loc_18000B487
0x18000b495  test    edx, edx
0x18000b497  jz      short loc_18000B4C3
0x18000b499  mov     eax, [r8+r9*8+4]
0x18000b49e  mov     rdx, [rbx+108h]
0x18000b4a5  imul    rcx, rax, 18Ch
0x18000b4ac  add     rdx, 84h
0x18000b4b3  add     rdx, rcx
0x18000b4b6  mov     r8, rbx
0x18000b4b9  mov     rcx, rdi
0x18000b4bc  call    BaddBranchToTree
0x18000b4c1  jmp     short loc_18000B505
0x18000b4c3  mov     rdx, rbx
0x18000b4c6  mov     rcx, rdi
0x18000b4c9  call    vIdentifySource
0x18000b4ce  lea     rdx, aSyntaxErrTheCm; "syntax err: the CmdSelect specifier can"...
0x18000b4d5  jmp     short loc_18000B4F7
0x18000b4d7  mov     ecx, [rsp+48h+arg_8]
0x18000b4db  mov     rax, [rbx+30h]
0x18000b4df  lea     rdx, [rax+rcx*4]
0x18000b4e3  jmp     short loc_18000B4B6
0x18000b4e5  mov     rdx, rbx
0x18000b4e8  mov     rcx, rdi
0x18000b4eb  call    vIdentifySource
0x18000b4f0  lea     rdx, aInternalErrorB_0; "Internal error: BstoreCommandAttrib - i"...
0x18000b4f7  lea     rcx, aBstorecommanda; "BstoreCommandAttrib"
0x18000b4fe  call    WriteDbgTraceErrorGpd
0x18000b503  xor     eax, eax
0x18000b505  add     rsp, 28h
0x18000b509  pop     rdi
0x18000b50a  pop     rsi
0x18000b50b  pop     rbp
0x18000b50c  pop     rbx
0x18000b50d  retn
```
