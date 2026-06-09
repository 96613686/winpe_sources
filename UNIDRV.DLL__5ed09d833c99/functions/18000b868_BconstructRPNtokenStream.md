# BconstructRPNtokenStream

- ea: `0x18000b868`
- end: `0x18000bccc`
- name: `BconstructRPNtokenStream`
- size: `1124`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800745c8`

## callees

- `0x180007150`
- `0x18000aa88`
- `0x18000b868`
- `0x18000c814`
- `0x180046e5c`

## string_xrefs

- `0x18000b91d`: `Command parameter: arithmetic syntax error in value construct.`
- `0x18000b98f`: `Command parameter: arithmetic syntax error in value construct.`
- `0x18000bc93`: `Command parameter: arithmetic syntax error in value construct.`
- `0x18000b924`: `BconstructRPNtokenStream`
- `0x18000b9b5`: `BconstructRPNtokenStream`
- `0x18000b9c8`: `BconstructRPNtokenStream`
- `0x18000bbd7`: `BconstructRPNtokenStream`
- `0x18000bc4d`: `BconstructRPNtokenStream`
- `0x18000bca3`: `BconstructRPNtokenStream`
- `0x18000b9ae`: `Command parameter: syntax error in value construct.`
- `0x18000bbd0`: `Command parameter: syntax error in value construct.`
- `0x18000bbe3`: `  comma used outside of function argument list.`
- `0x18000bc9c`: `Command parameter: syntax error in value construct - unmatched  OP_OPENPAR.`
- `0x18000bc46`: `Command parameter: syntax error in value construct - unmatched  OP_CLOSEPAR.`

## pseudocode

```c
__int64 __fastcall BconstructRPNtokenStream(__int64 a1, _DWORD *a2, __int64 a3)
{
  int v3; // edi
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v9; // [rsp+38h] [rbp-10h]
  __int64 v10; // [rsp+90h] [rbp+48h]
  unsigned int v11; // [rsp+98h] [rbp+50h] BYREF
  int v12; // [rsp+A0h] [rbp+58h]
  int v13; // [rsp+A8h] [rbp+60h]

  v10 = a1;
  v3 = 0;
  v9 = *(_QWORD *)(a3 + 144);
  a2[1] = *(_DWORD *)(a3 + 156);
  *a2 = 0;
  v13 = 0;
  v12 = 0;
  v11 = 0;
  while ( 1 )
  {
    v6 = BparseArithmeticToken(a1);
    if ( !v6 )
      break;
    if ( v3 )
    {
      WriteDbgTraceErrorGpd(
        (__int64)"BconstructRPNtokenStream",
        "Command parameter: arithmetic syntax error in value construct.");
      v6 = 0;
    }
    v13 = ++v3;
    if ( !v6 )
      break;
    v6 = BallocElementFromMasterTable(6, &v11, (_DWORD *)a3);
    if ( !v6 )
      break;
    v7 = v11;
    ++*a2;
    *(_DWORD *)(v9 + 8 * v7 + 4) = 0;
    *(_DWORD *)(v9 + 8 * v7) = 0;
    a1 = v10;
  }
  *(_QWORD *)a2 = 0;
  return v6;
}

```

## disassembly

```asm
0x18000b868  mov     [rsp-40h+arg_0], rcx
0x18000b86d  push    rbp
0x18000b86e  push    rbx
0x18000b86f  push    rsi
0x18000b870  push    rdi
0x18000b871  push    r12
0x18000b873  push    r13
0x18000b875  push    r14
0x18000b877  push    r15
0x18000b879  mov     rbp, rsp
0x18000b87c  sub     rsp, 48h
0x18000b880  mov     rax, [r8+270h]
0x18000b887  xor     edi, edi
0x18000b889  mov     [rbp+var_20], rax
0x18000b88d  xor     r13d, r13d
0x18000b890  mov     eax, [r8+278h]
0x18000b897  mov     r12, r8
0x18000b89a  mov     [rbp+var_28], eax
0x18000b89d  mov     r15, rdx
0x18000b8a0  mov     rax, [r8+90h]
0x18000b8a7  xor     r14d, r14d
0x18000b8aa  mov     [rbp+var_10], rax
0x18000b8ae  mov     eax, [r8+9Ch]
0x18000b8b5  mov     [rdx+4], eax
0x18000b8b8  mov     [rdx], edi
0x18000b8ba  mov     [rbp+var_18], 0
0x18000b8c2  mov     [rbp+arg_18], edi
0x18000b8c5  mov     [rbp+arg_10], r13d
0x18000b8c9  mov     [rbp+arg_8], edi
0x18000b8cc  mov     r8, r12
0x18000b8cf  lea     rdx, [rbp+var_18]
0x18000b8d3  call    BparseArithmeticToken
0x18000b8d8  mov     ebx, eax
0x18000b8da  test    eax, eax
0x18000b8dc  jz      loc_18000BCB1
0x18000b8e2  mov     esi, dword ptr [rbp+var_18+4]
0x18000b8e5  cmp     esi, 7
0x18000b8e8  jg      short loc_18000B93C
0x18000b8ea  jz      short loc_18000B960
0x18000b8ec  mov     edx, esi
0x18000b8ee  test    esi, esi
0x18000b8f0  jz      short loc_18000B918
0x18000b8f2  sub     edx, 1
0x18000b8f5  jz      short loc_18000B918
0x18000b8f7  sub     edx, 1
0x18000b8fa  jz      loc_18000B98A
0x18000b900  sub     edx, 1
0x18000b903  jz      loc_18000B98A
0x18000b909  sub     edx, 1
0x18000b90c  jz      short loc_18000B960
0x18000b90e  sub     edx, 1
0x18000b911  jz      short loc_18000B960
0x18000b913  cmp     edx, 1
0x18000b916  jmp     short loc_18000B95A
0x18000b918  cmp     r13d, edi
0x18000b91b  jz      short loc_18000B932
0x18000b91d  lea     rdx, aCommandParamet_7; "Command parameter: arithmetic syntax er"...
0x18000b924  lea     rcx, aBconstructrpnt; "BconstructRPNtokenStream"
0x18000b92b  call    WriteDbgTraceErrorGpd
0x18000b930  xor     ebx, ebx
0x18000b932  inc     edi
0x18000b934  mov     [rbp+arg_18], edi
0x18000b937  jmp     loc_18000B9D6
0x18000b93c  mov     ecx, esi
0x18000b93e  sub     ecx, 8
0x18000b941  jz      short loc_18000B960
0x18000b943  sub     ecx, 1
0x18000b946  jz      short loc_18000B9A0
0x18000b948  sub     ecx, 1
0x18000b94b  jz      short loc_18000B998
0x18000b94d  sub     ecx, 1
0x18000b950  jz      short loc_18000B98A
0x18000b952  sub     ecx, 1
0x18000b955  jz      short loc_18000B998
0x18000b957  cmp     ecx, 2
0x18000b95a  jnz     loc_18000B9FD
0x18000b960  lea     ecx, [r13+1]
0x18000b964  cmp     ecx, edi
0x18000b966  jz      loc_18000B9F7
0x18000b96c  lea     eax, [rdi+1]
0x18000b96f  cmp     ecx, eax
0x18000b971  jnz     loc_18000BC93
0x18000b977  mov     [rbp+arg_10], r13d
0x18000b97b  cmp     esi, 5
0x18000b97e  jnz     short loc_18000B9E0
0x18000b980  mov     esi, 0Dh
0x18000b985  mov     dword ptr [rbp+var_18+4], esi
0x18000b988  jmp     short loc_18000B9FD
0x18000b98a  cmp     edi, r13d
0x18000b98d  jz      short loc_18000B9FD
0x18000b98f  lea     rdx, aCommandParamet_7; "Command parameter: arithmetic syntax er"...
0x18000b996  jmp     short loc_18000B9C8
0x18000b998  lea     eax, [r13+1]
0x18000b99c  cmp     edi, eax
0x18000b99e  jmp     short loc_18000B98D
0x18000b9a0  test    edi, edi
0x18000b9a2  jnz     short loc_18000B9AE
0x18000b9a4  test    r13d, r13d
0x18000b9a7  jnz     short loc_18000B9AE
0x18000b9a9  test    r14d, r14d
0x18000b9ac  jz      short loc_18000B9FD
0x18000b9ae  lea     rdx, aCommandParamet_9; "Command parameter: syntax error in valu"...
0x18000b9b5  lea     rcx, aBconstructrpnt; "BconstructRPNtokenStream"
0x18000b9bc  call    WriteDbgTraceErrorGpd
0x18000b9c1  lea     rdx, aOpMaxRepeatMus; "  OP_MAX_REPEAT must appear as the oute"...
0x18000b9c8  lea     rcx, aBconstructrpnt; "BconstructRPNtokenStream"
0x18000b9cf  call    WriteDbgTraceErrorGpd
0x18000b9d4  xor     ebx, ebx
0x18000b9d6  test    ebx, ebx
0x18000b9d8  jz      loc_18000BCB1
0x18000b9de  jmp     short loc_18000B9FD
0x18000b9e0  cmp     esi, 4
0x18000b9e3  jnz     loc_18000BC93
0x18000b9e9  mov     esi, 0Fh
0x18000b9ee  mov     [rbp+arg_10], r13d
0x18000b9f2  mov     dword ptr [rbp+var_18+4], esi
0x18000b9f5  jmp     short loc_18000B9FD
0x18000b9f7  mov     r13d, ecx
0x18000b9fa  mov     [rbp+arg_10], ecx
0x18000b9fd  cmp     esi, 7
0x18000ba00  jg      loc_18000BB09
0x18000ba06  jz      short loc_18000BA40
0x18000ba08  mov     ecx, esi
0x18000ba0a  test    esi, esi
0x18000ba0c  jz      loc_18000BAD8
0x18000ba12  sub     ecx, 1
0x18000ba15  jz      loc_18000BAD8
0x18000ba1b  sub     ecx, 1
0x18000ba1e  jz      loc_18000BC64
0x18000ba24  sub     ecx, 1
0x18000ba27  jz      loc_18000BC64
0x18000ba2d  sub     ecx, 1
0x18000ba30  jz      short loc_18000BA40
0x18000ba32  sub     ecx, 1
0x18000ba35  jz      short loc_18000BA40
0x18000ba37  cmp     ecx, 1
0x18000ba3a  jnz     loc_18000BAC6
0x18000ba40  test    r14d, r14d
0x18000ba43  jz      short loc_18000BAAB
0x18000ba45  mov     r13, [rbp+var_20]
0x18000ba49  mov     edi, r14d
0x18000ba4c  movsxd  rcx, esi
0x18000ba4f  mov     eax, [r13+rdi*4-4]
0x18000ba54  mov     eax, [r12+rax*4+868h]
0x18000ba5c  cmp     [r12+rcx*4+868h], eax
0x18000ba64  ja      short loc_18000BAA4
0x18000ba66  mov     r8, r12
0x18000ba69  lea     rdx, [rbp+arg_8]
0x18000ba6d  mov     ecx, 6
0x18000ba72  call    BallocElementFromMasterTable
0x18000ba77  mov     ebx, eax
0x18000ba79  test    eax, eax
0x18000ba7b  jz      short loc_18000BAA4
0x18000ba7d  inc     dword ptr [r15]
0x18000ba80  mov     eax, [rbp+arg_8]
0x18000ba83  mov     rcx, [rbp+var_10]
0x18000ba87  lea     rcx, [rcx+rax*8]
0x18000ba8b  mov     eax, [r13+rdi*4-4]
0x18000ba90  mov     [rcx+4], eax
0x18000ba93  mov     dword ptr [rcx], 0
0x18000ba99  call    bDivByZeroCheck
0x18000ba9e  add     r14d, 0FFFFFFFFh
0x18000baa2  jnz     short loc_18000BA49
0x18000baa4  mov     r13d, [rbp+arg_10]
0x18000baa8  mov     edi, [rbp+arg_18]
0x18000baab  cmp     r14d, [rbp+var_28]
0x18000baaf  sbb     eax, eax
0x18000bab1  and     ebx, eax
0x18000bab3  jz      loc_18000BCAF
0x18000bab9  mov     rcx, [rbp+var_20]
0x18000babd  mov     eax, r14d
0x18000bac0  mov     [rcx+rax*4], esi
0x18000bac3  inc     r14d
0x18000bac6  cmp     esi, 0Ah
0x18000bac9  jz      loc_18000BCB8
0x18000bacf  mov     rcx, [rbp+arg_0]
0x18000bad3  jmp     loc_18000B8CC
0x18000bad8  mov     r8, r12
0x18000badb  lea     rdx, [rbp+arg_8]
0x18000badf  mov     ecx, 6
0x18000bae4  call    BallocElementFromMasterTable
0x18000bae9  mov     ebx, eax
0x18000baeb  test    eax, eax
0x18000baed  jz      loc_18000BCB1
0x18000baf3  mov     ecx, [rbp+arg_8]
0x18000baf6  mov     rdx, [rbp+var_10]
0x18000bafa  inc     dword ptr [r15]
0x18000bafd  mov     eax, dword ptr [rbp+var_18]
0x18000bb00  mov     [rdx+rcx*8+4], esi
0x18000bb04  mov     [rdx+rcx*8], eax
0x18000bb07  jmp     short loc_18000BAC6
0x18000bb09  mov     ecx, esi
0x18000bb0b  sub     ecx, 8
0x18000bb0e  jz      loc_18000BA40
0x18000bb14  sub     ecx, 1
0x18000bb17  jz      loc_18000BC64
0x18000bb1d  sub     ecx, 1
0x18000bb20  jz      short loc_18000BB3E
0x18000bb22  sub     ecx, 1
0x18000bb25  jz      loc_18000BC64
0x18000bb2b  sub     ecx, 1
0x18000bb2e  jz      short loc_18000BB3E
0x18000bb30  sub     ecx, 1
0x18000bb33  jz      loc_18000BA40
0x18000bb39  cmp     ecx, 1
0x18000bb3c  jnz     short loc_18000BAC6
0x18000bb3e  test    r14d, r14d
0x18000bb41  jz      short loc_18000BBAF
0x18000bb43  mov     rdx, [rbp+var_20]
0x18000bb47  mov     edi, r14d
0x18000bb4a  movsxd  rcx, esi
0x18000bb4d  mov     eax, [rdx+rdi*4-4]
0x18000bb51  mov     eax, [r12+rax*4+868h]
0x18000bb59  cmp     [r12+rcx*4+868h], eax
0x18000bb61  ja      loc_18000BBEF
0x18000bb67  mov     r8, r12
0x18000bb6a  lea     rdx, [rbp+arg_8]
0x18000bb6e  mov     ecx, 6
0x18000bb73  call    BallocElementFromMasterTable
0x18000bb78  mov     ebx, eax
0x18000bb7a  test    eax, eax
0x18000bb7c  jz      loc_18000BCB1
0x18000bb82  inc     dword ptr [r15]
0x18000bb85  mov     eax, [rbp+arg_8]
0x18000bb88  mov     rcx, [rbp+var_10]
0x18000bb8c  lea     rcx, [rcx+rax*8]
0x18000bb90  mov     rax, [rbp+var_20]
0x18000bb94  mov     eax, [rax+rdi*4-4]
0x18000bb98  mov     [rcx+4], eax
0x18000bb9b  mov     dword ptr [rcx], 0
0x18000bba1  call    bDivByZeroCheck
0x18000bba6  add     r14d, 0FFFFFFFFh
0x18000bbaa  jnz     short loc_18000BB43
0x18000bbac  mov     edi, [rbp+arg_18]
0x18000bbaf  mov     rdx, [rbp+var_20]
0x18000bbb3  cmp     esi, 0Eh
0x18000bbb6  jnz     short loc_18000BBF4
0x18000bbb8  test    r14d, r14d
0x18000bbbb  jz      short loc_18000BBD0
0x18000bbbd  mov     eax, r14d
0x18000bbc0  mov     ecx, [rdx+rax*4-4]
0x18000bbc4  sub     ecx, 2
0x18000bbc7  cmp     ecx, 1
0x18000bbca  jbe     loc_18000BC5B
0x18000bbd0  lea     rdx, aCommandParamet_9; "Command parameter: syntax error in valu"...
0x18000bbd7  lea     rcx, aBconstructrpnt; "BconstructRPNtokenStream"
0x18000bbde  call    WriteDbgTraceErrorGpd
0x18000bbe3  lea     rdx, aCommaUsedOutsi; "  comma used outside of function argume"...
0x18000bbea  jmp     loc_18000BCA3
0x18000bbef  mov     edi, [rbp+arg_18]
0x18000bbf2  jmp     short loc_18000BBB3
0x18000bbf4  cmp     esi, 0Ah
0x18000bbf7  jnz     short loc_18000BC32
0x18000bbf9  test    r14d, r14d
0x18000bbfc  jnz     loc_18000BC9C
0x18000bc02  mov     r8, r12
0x18000bc05  lea     rdx, [rbp+arg_8]
0x18000bc09  lea     ecx, [rsi-4]
0x18000bc0c  call    BallocElementFromMasterTable
0x18000bc11  mov     ebx, eax
0x18000bc13  test    eax, eax
0x18000bc15  jz      loc_18000BCB1
0x18000bc1b  mov     eax, [rbp+arg_8]
0x18000bc1e  mov     rcx, [rbp+var_10]
0x18000bc22  inc     dword ptr [r15]
0x18000bc25  mov     [rcx+rax*8+4], esi
0x18000bc29  mov     [rcx+rax*8], r14d
0x18000bc2d  jmp     loc_18000BAC6
0x18000bc32  test    r14d, r14d
0x18000bc35  jz      short loc_18000BC46
0x18000bc37  mov     eax, r14d
0x18000bc3a  cmp     dword ptr [rdx+rax*4-4], 0Bh
0x18000bc3f  jnz     short loc_18000BC46
0x18000bc41  dec     r14d
0x18000bc44  jmp     short loc_18000BC5B
0x18000bc46  lea     rdx, aCommandParamet; "Command parameter: syntax error in valu"...
0x18000bc4d  lea     rcx, aBconstructrpnt; "BconstructRPNtokenStream"
0x18000bc54  call    WriteDbgTraceErrorGpd
0x18000bc59  xor     ebx, ebx
0x18000bc5b  test    ebx, ebx
0x18000bc5d  jz      short loc_18000BCB1
0x18000bc5f  jmp     loc_18000BAC6
0x18000bc64  lea     ecx, [r14+1]
0x18000bc68  cmp     ecx, [rbp+var_28]
0x18000bc6b  sbb     eax, eax
0x18000bc6d  and     ebx, eax
0x18000bc6f  jz      short loc_18000BCB1
0x18000bc71  mov     rdx, [rbp+var_20]
0x18000bc75  mov     eax, r14d
0x18000bc78  mov     r14d, ecx
0x18000bc7b  mov     dword ptr [rdx+rax*4], 0Bh
0x18000bc82  cmp     esi, 0Bh
0x18000bc85  jz      loc_18000BAC6
0x18000bc8b  mov     [rdx+rcx*4], esi
0x18000bc8e  jmp     loc_18000BAC3
0x18000bc93  lea     rdx, aCommandParamet_7; "Command parameter: arithmetic syntax er"...
0x18000bc9a  jmp     short loc_18000BCA3
0x18000bc9c  lea     rdx, aCommandParamet_14; "Command parameter: syntax error in valu"...
0x18000bca3  lea     rcx, aBconstructrpnt; "BconstructRPNtokenStream"
0x18000bcaa  call    WriteDbgTraceErrorGpd
  ... truncated ...
```
