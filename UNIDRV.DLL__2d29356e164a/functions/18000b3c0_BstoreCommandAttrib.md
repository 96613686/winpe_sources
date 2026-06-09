# BstoreCommandAttrib

- ea: `0x18000b3c0`
- end: `0x18000b4fe`
- name: `BstoreCommandAttrib`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a2d8`

## callees

- `0x180007220`
- `0x18000a460`
- `0x18000b3c0`
- `0x18000b7e0`
- `0x18004485c`

## string_xrefs

- `0x18000b43b`: `BstoreCommandAttrib`
- `0x18000b4e7`: `BstoreCommandAttrib`
- `0x18000b4be`: `syntax err: the CmdSelect specifier can only be used inside an Option construct.`
- `0x18000b4e0`: `Internal error: BstoreCommandAttrib - invalid CommandID.`
- `0x18000b430`: `unrecognized Unidrv command name: *%0.*s.`

## pseudocode

```c
__int64 __fastcall BstoreCommandAttrib(__int64 a1, __int64 a2)
{
  unsigned int v3; // ecx
  unsigned int v5; // edx
  __int64 v6; // r8
  __int64 v7; // rsi
  __int64 v8; // rcx
  unsigned int i; // eax
  __int64 v10; // r8
  __int64 v11; // rcx
  int v12; // edx
  __int64 v13; // rdx
  unsigned int v15; // [rsp+58h] [rbp+10h] BYREF

  v15 = 0;
  v3 = 0;
  v5 = *(_DWORD *)(a2 + 612);
  while ( 1 )
  {
    if ( v3 >= v5 )
      goto LABEL_22;
    v6 = *(_QWORD *)(a2 + 600);
    v7 = v5 - v3 - 1;
    if ( *(_DWORD *)(v6 + 8 * v7) == 13 )
      break;
    ++v3;
  }
  v8 = *(unsigned int *)(v6 + 8 * v7 + 4);
  if ( (_DWORD)v8 == -1 )
  {
LABEL_22:
    vIdentifySource(a1, a2);
    WriteDbgTraceErrorGpd("BstoreCommandAttrib", "Internal error: BstoreCommandAttrib - invalid CommandID.");
    return 0;
  }
  if ( !(unsigned int)BconvertSymCmdIDtoUnidrvID(v8, &v15, a2) )
  {
    vIdentifySource(a1, a2);
    WriteDbgTraceErrorGpd(
      "BstoreCommandAttrib",
      "unrecognized Unidrv command name: *%0.*s.",
      *(_DWORD *)(a1 + 32),
      *(const char **)(a1 + 24));
    return 0;
  }
  if ( v15 == -2 )
  {
    for ( i = 0; i < (unsigned int)v7; ++i )
    {
      v10 = *(_QWORD *)(a2 + 600);
      v11 = i + 1;
      if ( *(_DWORD *)(v10 + 8LL * i) == 2 )
      {
        v12 = 0;
        if ( (unsigned int)v11 < (unsigned int)v7 )
        {
          do
          {
            if ( *(_DWORD *)(v10 + 8 * v11) == 3 )
              v12 = 1;
            v11 = (unsigned int)(v11 + 1);
          }
          while ( (unsigned int)v11 < (unsigned int)v7 );
          if ( v12 )
          {
            v13 = 396LL * *(unsigned int *)(v10 + 8LL * i + 4) + *(_QWORD *)(a2 + 264) + 132LL;
            return BaddBranchToTree(a1, v13, a2);
          }
        }
        break;
      }
    }
    vIdentifySource(a1, a2);
    WriteDbgTraceErrorGpd(
      "BstoreCommandAttrib",
      "syntax err: the CmdSelect specifier can only be used inside an Option construct.");
    return 0;
  }
  v13 = *(_QWORD *)(a2 + 48) + 4LL * v15;
  return BaddBranchToTree(a1, v13, a2);
}

```

## disassembly

```asm
0x18000b3c0  push    rbx
0x18000b3c2  push    rbp
0x18000b3c3  push    rsi
0x18000b3c4  push    rdi
0x18000b3c5  sub     rsp, 28h
0x18000b3c9  mov     rdi, rcx
0x18000b3cc  mov     [rsp+48h+arg_8], 0
0x18000b3d4  xor     ecx, ecx
0x18000b3d6  mov     rbx, rdx
0x18000b3d9  mov     edx, [rdx+264h]
0x18000b3df  lea     ebp, [rcx+1]
0x18000b3e2  cmp     ecx, edx
0x18000b3e4  jnb     loc_18000B4D5
0x18000b3ea  mov     r8, [rbx+258h]
0x18000b3f1  mov     esi, edx
0x18000b3f3  sub     esi, ecx
0x18000b3f5  dec     esi
0x18000b3f7  cmp     dword ptr [r8+rsi*8], 0Dh
0x18000b3fc  jz      short loc_18000B402
0x18000b3fe  add     ecx, ebp
0x18000b400  jmp     short loc_18000B3E2
0x18000b402  mov     ecx, [r8+rsi*8+4]
0x18000b407  cmp     ecx, 0FFFFFFFFh
0x18000b40a  jz      loc_18000B4D5
0x18000b410  mov     r8, rbx
0x18000b413  lea     rdx, [rsp+48h+arg_8]
0x18000b418  call    BconvertSymCmdIDtoUnidrvID
0x18000b41d  test    eax, eax
0x18000b41f  jnz     short loc_18000B44C
0x18000b421  mov     rdx, rbx
0x18000b424  mov     rcx, rdi
0x18000b427  call    vIdentifySource
0x18000b42c  mov     r9, [rdi+18h]
0x18000b430  lea     rdx, aUnrecognizedUn; "unrecognized Unidrv command name: *%0.*"...
0x18000b437  mov     r8d, [rdi+20h]
0x18000b43b  lea     rcx, aBstorecommanda; "BstoreCommandAttrib"
0x18000b442  call    WriteDbgTraceErrorGpd
0x18000b447  jmp     loc_18000B4F3
0x18000b44c  cmp     [rsp+48h+arg_8], 0FFFFFFFEh
0x18000b451  jnz     short loc_18000B4C7
0x18000b453  xor     eax, eax
0x18000b455  cmp     eax, esi
0x18000b457  jnb     short loc_18000B4B3
0x18000b459  mov     r8, [rbx+258h]
0x18000b460  lea     ecx, [rax+1]
0x18000b463  mov     r9d, eax
0x18000b466  cmp     dword ptr [r8+r9*8], 2
0x18000b46b  jz      short loc_18000B471
0x18000b46d  mov     eax, ecx
0x18000b46f  jmp     short loc_18000B455
0x18000b471  xor     edx, edx
0x18000b473  cmp     ecx, esi
0x18000b475  jnb     short loc_18000B4B3
0x18000b477  cmp     dword ptr [r8+rcx*8], 3
0x18000b47c  cmovz   edx, ebp
0x18000b47f  add     ecx, ebp
0x18000b481  cmp     ecx, esi
0x18000b483  jb      short loc_18000B477
0x18000b485  test    edx, edx
0x18000b487  jz      short loc_18000B4B3
0x18000b489  mov     eax, [r8+r9*8+4]
0x18000b48e  mov     rdx, [rbx+108h]
0x18000b495  imul    rcx, rax, 18Ch
0x18000b49c  add     rdx, 84h
0x18000b4a3  add     rdx, rcx
0x18000b4a6  mov     r8, rbx
0x18000b4a9  mov     rcx, rdi
0x18000b4ac  call    BaddBranchToTree
0x18000b4b1  jmp     short loc_18000B4F5
0x18000b4b3  mov     rdx, rbx
0x18000b4b6  mov     rcx, rdi
0x18000b4b9  call    vIdentifySource
0x18000b4be  lea     rdx, aSyntaxErrTheCm; "syntax err: the CmdSelect specifier can"...
0x18000b4c5  jmp     short loc_18000B4E7
0x18000b4c7  mov     ecx, [rsp+48h+arg_8]
0x18000b4cb  mov     rax, [rbx+30h]
0x18000b4cf  lea     rdx, [rax+rcx*4]
0x18000b4d3  jmp     short loc_18000B4A6
0x18000b4d5  mov     rdx, rbx
0x18000b4d8  mov     rcx, rdi
0x18000b4db  call    vIdentifySource
0x18000b4e0  lea     rdx, aInternalErrorB_0; "Internal error: BstoreCommandAttrib - i"...
0x18000b4e7  lea     rcx, aBstorecommanda; "BstoreCommandAttrib"
0x18000b4ee  call    WriteDbgTraceErrorGpd
0x18000b4f3  xor     eax, eax
0x18000b4f5  add     rsp, 28h
0x18000b4f9  pop     rdi
0x18000b4fa  pop     rsi
0x18000b4fb  pop     rbp
0x18000b4fc  pop     rbx
0x18000b4fd  retn
```
