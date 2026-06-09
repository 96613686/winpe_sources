# VfsInsertMappingEntry

- ea: `0x140008fb0`
- end: `0x1400090c1`
- name: `VfsInsertMappingEntry`
- size: `273`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140009784`

## callees

- `0x140008910`
- `0x140008fb0`
- `0x140012548`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140009012`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140009012`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000909b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000909b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000908f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000908f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140008fea`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140008fea`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008fd9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140008fd9`

## pseudocode

```c
__int64 __fastcall VfsInsertMappingEntry(__int64 a1, __int64 a2)
{
  struct _ERESOURCE *v2; // rbx
  UNICODE_STRING *v3; // rdi
  LONG v6; // r14d
  const UNICODE_STRING *v7; // rsi
  const UNICODE_STRING *i; // rbx
  int v9; // esi
  __int64 **Buffer; // rax
  UNICODE_STRING *v12; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(struct _ERESOURCE **)a1;
  v3 = 0;
  v12 = 0;
  v6 = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(v2, 1u);
  v7 = (const UNICODE_STRING *)(a1 + 8);
  for ( i = *(const UNICODE_STRING **)(a1 + 8); i != v7; i = *(const UNICODE_STRING **)&i->Length )
  {
    v12 = (UNICODE_STRING *)i;
    v3 = (UNICODE_STRING *)i;
    v6 = RtlCompareUnicodeString((PCUNICODE_STRING)(a2 + 8), i + 1, 1u);
    if ( v6 < 1 )
      break;
  }
  if ( *(const UNICODE_STRING **)&v7->Length == v7 || (v9 = 0, v6) )
  {
    v9 = VfsCreateMappingPrefixTable((PCUNICODE_STRING)(a2 + 8), &v12);
    if ( v9 < 0 )
      goto LABEL_13;
    Buffer = (__int64 **)i->Buffer;
    if ( *Buffer != (__int64 *)i )
      __fastfail(3u);
    v3 = v12;
    *(_QWORD *)&v12->Length = i;
    v3->Buffer = (wchar_t *)Buffer;
    *Buffer = (__int64 *)v3;
    i->Buffer = &v3->Length;
  }
  if ( v3 )
    v9 = VfsPrefixTreeInsert(*(_QWORD *)&v3[2].Length, *(_QWORD *)(a2 + 40), *(_QWORD *)(a2 + 48), a2);
LABEL_13:
  ExReleaseResourceLite(*(PERESOURCE *)a1);
  KeLeaveCriticalRegion();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140008fb0  mov     [rsp+arg_8], rbx
0x140008fb5  mov     [rsp+arg_10], rbp
0x140008fba  push    rsi
0x140008fbb  push    rdi
0x140008fbc  push    r12
0x140008fbe  push    r14
0x140008fc0  push    r15
0x140008fc2  sub     rsp, 20h
0x140008fc6  mov     rbx, [rcx]
0x140008fc9  xor     edi, edi
0x140008fcb  mov     [rsp+48h+arg_0], rdi
0x140008fd0  mov     rbp, rdx
0x140008fd3  mov     r15, rcx
0x140008fd6  xor     r14d, r14d
0x140008fd9  call    cs:__imp_KeEnterCriticalRegion
0x140008fe0  nop     dword ptr [rax+rax+00h]
0x140008fe5  mov     dl, 1; Wait
0x140008fe7  mov     rcx, rbx; Resource
0x140008fea  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140008ff1  nop     dword ptr [rax+rax+00h]
0x140008ff6  lea     rsi, [r15+8]
0x140008ffa  mov     rbx, [rsi]
0x140008ffd  jmp     short loc_140009029
0x140008fff  lea     rdx, [rbx+10h]; String2
0x140009003  mov     [rsp+48h+arg_0], rbx
0x140009008  mov     r8b, 1; CaseInSensitive
0x14000900b  lea     rcx, [rbp+8]; String1
0x14000900f  mov     rdi, rbx
0x140009012  call    cs:__imp_RtlCompareUnicodeString
0x140009019  nop     dword ptr [rax+rax+00h]
0x14000901e  mov     r14d, eax
0x140009021  cmp     eax, 1
0x140009024  jl      short loc_14000902E
0x140009026  mov     rbx, [rbx]
0x140009029  cmp     rbx, rsi
0x14000902c  jnz     short loc_140008FFF
0x14000902e  cmp     [rsi], rsi
0x140009031  jz      short loc_14000903A
0x140009033  xor     esi, esi
0x140009035  test    r14d, r14d
0x140009038  jz      short loc_140009071
0x14000903a  lea     rcx, [rbp+8]; SourceString
0x14000903e  lea     rdx, [rsp+48h+arg_0]
0x140009043  call    VfsCreateMappingPrefixTable
0x140009048  mov     esi, eax
0x14000904a  test    eax, eax
0x14000904c  js      short loc_14000908C
0x14000904e  mov     rax, [rbx+8]
0x140009052  cmp     [rax], rbx
0x140009055  jz      short loc_14000905E
0x140009057  mov     ecx, 3
0x14000905c  int     29h; Win8: RtlFailFast(ecx)
0x14000905e  mov     rdi, [rsp+48h+arg_0]
0x140009063  mov     [rdi], rbx
0x140009066  mov     [rdi+8], rax
0x14000906a  mov     [rax], rdi
0x14000906d  mov     [rbx+8], rdi
0x140009071  test    rdi, rdi
0x140009074  jz      short loc_14000908C
0x140009076  mov     r8, [rbp+30h]
0x14000907a  mov     r9, rbp
0x14000907d  mov     rdx, [rbp+28h]
0x140009081  mov     rcx, [rdi+20h]
0x140009085  call    VfsPrefixTreeInsert
0x14000908a  mov     esi, eax
0x14000908c  mov     rcx, [r15]; Resource
0x14000908f  call    cs:__imp_ExReleaseResourceLite
0x140009096  nop     dword ptr [rax+rax+00h]
0x14000909b  call    cs:__imp_KeLeaveCriticalRegion
0x1400090a2  nop     dword ptr [rax+rax+00h]
0x1400090a7  mov     rbx, [rsp+48h+arg_8]
0x1400090ac  mov     eax, esi
0x1400090ae  mov     rbp, [rsp+48h+arg_10]
0x1400090b3  add     rsp, 20h
0x1400090b7  pop     r15
0x1400090b9  pop     r14
0x1400090bb  pop     r12
0x1400090bd  pop     rdi
0x1400090be  pop     rsi
0x1400090bf  retn
```
