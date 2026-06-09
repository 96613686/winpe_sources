# SrpDeleteEnterpriseContextToken

- ea: `0x140005568`
- end: `0x14000562e`
- name: `SrpDeleteEnterpriseContextToken`
- size: `198`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003c8c`

## callees

- `0x140004410`
- `0x140004838`
- `0x140005568`

## import_xrefs

- `ntoskrnl!SeSetSecurityAttributesTokenEx` at `0x140005605`
- `ntoskrnl!SeSetSecurityAttributesTokenEx` at `0x140005605`

## pseudocode

```c
__int64 __fastcall SrpDeleteEnterpriseContextToken(__int64 a1, __int64 a2)
{
  char v4; // bp
  int AttributesFromContext; // eax
  __int64 v6; // r9
  PVOID v7; // rdi
  unsigned int v8; // ebx
  _BYTE v9[56]; // [rsp+40h] [rbp-38h] BYREF
  PVOID P; // [rsp+88h] [rbp+10h] BYREF
  char v11; // [rsp+98h] [rbp+20h] BYREF

  P = 0;
  v11 = 0;
  memset(v9, 0, 32);
  if ( !a1 )
    return 3221225485LL;
  v4 = EdppSingleInstanceAttributes;
  LOBYTE(a2) = 1;
  AttributesFromContext = CreateAttributesFromContext(
                            (__int64)v9,
                            a2,
                            EdppSingleInstanceAttributes == 0,
                            0,
                            (__int64 *)&P);
  v7 = P;
  v8 = AttributesFromContext;
  if ( AttributesFromContext >= 0 )
  {
    LOBYTE(v6) = v4;
    v8 = SeSetSecurityAttributesTokenEx(a1, 0, 0, v6, SrpReplaceOperations, P, &v11);
  }
  DeleteAttributes(v7);
  return v8;
}

```

## disassembly

```asm
0x140005568  mov     rax, rsp
0x14000556b  mov     [rax+8], rbx
0x14000556f  mov     [rax+20h], r9b
0x140005573  mov     [rax+10h], rdx
0x140005577  push    rbp
0x140005578  push    rsi
0x140005579  push    rdi
0x14000557a  sub     rsp, 60h
0x14000557e  mov     qword ptr [rax+10h], 0
0x140005586  xorps   xmm0, xmm0
0x140005589  mov     byte ptr [rax+20h], 0
0x14000558d  mov     rsi, rcx
0x140005590  movups  xmmword ptr [rax-38h], xmm0
0x140005594  movups  xmmword ptr [rax-28h], xmm0
0x140005598  test    rcx, rcx
0x14000559b  jnz     short loc_1400055A4
0x14000559d  mov     eax, 0C000000Dh
0x1400055a2  jmp     short loc_14000561D
0x1400055a4  mov     bpl, cs:EdppSingleInstanceAttributes
0x1400055ab  lea     rax, [rsp+78h+P]
0x1400055b3  test    bpl, bpl
0x1400055b6  mov     [rsp+78h+var_58], rax
0x1400055bb  mov     dl, 1
0x1400055bd  lea     rcx, [rsp+78h+var_38]
0x1400055c2  setz    r8b
0x1400055c6  xor     r9d, r9d
0x1400055c9  call    CreateAttributesFromContext
0x1400055ce  mov     rdi, [rsp+78h+P]
0x1400055d6  mov     ebx, eax
0x1400055d8  test    eax, eax
0x1400055da  js      short loc_140005613
0x1400055dc  lea     rax, [rsp+78h+arg_18]
0x1400055e4  mov     r9b, bpl
0x1400055e7  mov     [rsp+78h+var_48], rax
0x1400055ec  xor     r8d, r8d
0x1400055ef  lea     rax, SrpReplaceOperations
0x1400055f6  mov     [rsp+78h+var_50], rdi
0x1400055fb  xor     edx, edx
0x1400055fd  mov     [rsp+78h+var_58], rax
0x140005602  mov     rcx, rsi
0x140005605  call    cs:__imp_SeSetSecurityAttributesTokenEx
0x14000560c  nop     dword ptr [rax+rax+00h]
0x140005611  mov     ebx, eax
0x140005613  mov     rcx, rdi; P
0x140005616  call    DeleteAttributes
0x14000561b  mov     eax, ebx
0x14000561d  mov     rbx, [rsp+78h+arg_0]
0x140005625  add     rsp, 60h
0x140005629  pop     rdi
0x14000562a  pop     rsi
0x14000562b  pop     rbp
0x14000562c  retn
```
