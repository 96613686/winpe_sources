# EdppCreateFileObject(ushort const *,_OBJECT_ATTRIBUTES *,_UNICODE_STRING * *)

- ea: `0x140005a10`
- end: `0x140005aea`
- name: `?EdppCreateFileObject@@YAJPEBGPEAU_OBJECT_ATTRIBUTES@@PEAPEAU_UNICODE_STRING@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, struct _OBJECT_ATTRIBUTES *, struct _UNICODE_STRING **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002e2dc`
- `0x14002e3cc`

## callees

- `0x140005a10`
- `0x140006c40`
- `0x140006f40`
- `0x14002dfa0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140005aa5`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005aa5`

## pseudocode

```c
__int64 __fastcall EdppCreateFileObject(
        const unsigned __int16 *Src,
        struct _OBJECT_ATTRIBUTES *a2,
        struct _UNICODE_STRING **a3)
{
  __int64 v3; // rdi
  unsigned int v5; // esi
  unsigned __int16 v8; // di
  _QWORD *v9; // rbp
  struct _UNICODE_STRING *v10; // rbx

  v3 = -1;
  v5 = 0;
  do
    ++v3;
  while ( Src[v3] );
  v8 = 2 * (v3 + 1);
  v9 = (_QWORD *)EdpAuditLibMemAlloc((unsigned __int16)(v8 + 24));
  if ( v9 )
  {
    v10 = (struct _UNICODE_STRING *)EdpAuditLibMemAlloc(16);
    memset(v9, 0, (unsigned __int16)(v8 + 24));
    *(_OWORD *)v9 = xmmword_1400159D0;
    v9[2] = 0x5C007300650063LL;
    memmove(v9 + 3, Src, v8);
    RtlInitUnicodeString(v10, (PCWSTR)v9);
    a2->Length = 48;
    a2->RootDirectory = 0;
    a2->SecurityDescriptor = 0;
    a2->SecurityQualityOfService = 0;
    a2->Attributes = 512;
    a2->ObjectName = v10;
    *a3 = v10;
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return v5;
}

```

## disassembly

```asm
0x140005a10  push    rbx
0x140005a12  push    rbp
0x140005a13  push    rsi
0x140005a14  push    rdi
0x140005a15  push    r12
0x140005a17  push    r13
0x140005a19  push    r14
0x140005a1b  push    r15
0x140005a1d  sub     rsp, 28h
0x140005a21  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140005a25  mov     r13, r8
0x140005a28  xor     esi, esi
0x140005a2a  mov     r15, rdx
0x140005a2d  mov     r14, rcx
0x140005a30  inc     rdi
0x140005a33  cmp     [rcx+rdi*2], si
0x140005a37  jnz     short loc_140005A30
0x140005a39  inc     di
0x140005a3c  add     di, di
0x140005a3f  lea     eax, [rdi+18h]
0x140005a42  movzx   r12d, ax
0x140005a46  mov     ecx, r12d
0x140005a49  call    EdpAuditLibMemAlloc
0x140005a4e  mov     rbp, rax
0x140005a51  test    rax, rax
0x140005a54  jnz     short loc_140005A5D
0x140005a56  mov     esi, 0C0000017h
0x140005a5b  jmp     short loc_140005AD6
0x140005a5d  mov     ecx, 10h
0x140005a62  call    EdpAuditLibMemAlloc
0x140005a67  mov     r8, r12; Size
0x140005a6a  xor     edx, edx; Val
0x140005a6c  mov     rcx, rbp; void *
0x140005a6f  mov     rbx, rax
0x140005a72  call    memset
0x140005a77  movups  xmm0, cs:xmmword_1400159D0
0x140005a7e  movzx   r8d, di; Size
0x140005a82  lea     rcx, [rbp+18h]; void *
0x140005a86  mov     rdx, r14; Src
0x140005a89  movups  xmmword ptr [rbp+0], xmm0
0x140005a8d  movsd   xmm1, cs:qword_1400159E0
0x140005a95  movsd   qword ptr [rbp+10h], xmm1
0x140005a9a  call    memmove
0x140005a9f  mov     rdx, rbp; SourceString
0x140005aa2  mov     rcx, rbx; DestinationString
0x140005aa5  call    cs:__imp_RtlInitUnicodeString
0x140005aac  nop     dword ptr [rax+rax+00h]
0x140005ab1  xor     eax, eax
0x140005ab3  mov     dword ptr [r15], 30h ; '0'
0x140005aba  mov     [r15+8], rax
0x140005abe  mov     [r15+20h], rax
0x140005ac2  mov     [r15+28h], rax
0x140005ac6  mov     dword ptr [r15+18h], 200h
0x140005ace  mov     [r15+10h], rbx
0x140005ad2  mov     [r13+0], rbx
0x140005ad6  mov     eax, esi
0x140005ad8  add     rsp, 28h
0x140005adc  pop     r15
0x140005ade  pop     r14
0x140005ae0  pop     r13
0x140005ae2  pop     r12
0x140005ae4  pop     rdi
0x140005ae5  pop     rsi
0x140005ae6  pop     rbp
0x140005ae7  pop     rbx
0x140005ae8  retn
```
