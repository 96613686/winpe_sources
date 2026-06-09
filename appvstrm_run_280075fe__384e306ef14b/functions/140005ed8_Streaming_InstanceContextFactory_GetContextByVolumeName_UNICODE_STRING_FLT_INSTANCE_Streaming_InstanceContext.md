# Streaming::InstanceContextFactory::GetContextByVolumeName(_UNICODE_STRING,_FLT_INSTANCE * &,Streaming::InstanceContext &)

- ea: `0x140005ed8`
- end: `0x140005fb2`
- name: `?GetContextByVolumeName@InstanceContextFactory@Streaming@@QEAAJU_UNICODE_STRING@@AEAPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z`
- size: `218`
- prototype: `int(Streaming::InstanceContextFactory *__hidden this, struct _UNICODE_STRING *__struct_ptr, struct _FLT_INSTANCE **, struct Streaming::InstanceContext *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400020c8`
- `0x140007c24`
- `0x1400084b0`
- `0x140008bdc`
- `0x140008dc4`
- `0x14000935c`

## callees

- `0x140005ed8`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140005f43`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140005f43`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005f92`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005f92`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005f86`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005f86`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140005f1d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140005f1d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005f0a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005f0a`
- `FLTMGR!FltReferenceContext` at `0x140005f60`
- `FLTMGR!FltReferenceContext` at `0x140005f60`

## pseudocode

```c
__int64 __fastcall Streaming::InstanceContextFactory::GetContextByVolumeName(
        PERESOURCE *this,
        struct _UNICODE_STRING *a2,
        POWNER_ENTRY *a3,
        struct Streaming::InstanceContext *a4)
{
  bool v4; // si
  unsigned int v9; // ebp
  PERESOURCE i; // rbx
  struct _ERESOURCE *v11; // rcx

  v4 = 0;
  v9 = -1071906795;
  if ( this[3] )
  {
    KeEnterCriticalRegion();
    v4 = ExAcquireResourceSharedLite(this[3], 1u) == 1;
  }
  for ( i = *this; i != (PERESOURCE)this; i = (PERESOURCE)i->SystemResourcesList.Flink )
  {
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)&i->Reserved2, a2, 1u) )
    {
      FltReferenceContext(i);
      *(_QWORD *)a4 = i;
      v9 = 0;
      *a3 = i->OwnerTable;
      break;
    }
  }
  if ( v4 )
  {
    v11 = this[3];
    if ( v11 )
    {
      ExReleaseResourceLite(v11);
      KeLeaveCriticalRegion();
    }
  }
  return v9;
}

```

## disassembly

```asm
0x140005ed8  push    rbx
0x140005eda  push    rbp
0x140005edb  push    rsi
0x140005edc  push    rdi
0x140005edd  push    r12
0x140005edf  push    r13
0x140005ee1  push    r14
0x140005ee3  push    r15
0x140005ee5  sub     rsp, 28h
0x140005ee9  xor     sil, sil
0x140005eec  mov     r14, r9
0x140005eef  cmp     qword ptr [rcx+18h], 0
0x140005ef4  mov     r15, r8
0x140005ef7  mov     r12, rdx
0x140005efa  mov     rdi, rcx
0x140005efd  mov     ebp, 0C01C0015h
0x140005f02  mov     r13d, 1
0x140005f08  jz      short loc_140005F34
0x140005f0a  call    cs:__imp_KeEnterCriticalRegion
0x140005f11  nop     dword ptr [rax+rax+00h]
0x140005f16  mov     rcx, [rdi+18h]; Resource
0x140005f1a  mov     dl, r13b; Wait
0x140005f1d  call    cs:__imp_ExAcquireResourceSharedLite
0x140005f24  nop     dword ptr [rax+rax+00h]
0x140005f29  cmp     al, r13b
0x140005f2c  movzx   esi, sil
0x140005f30  cmovz   esi, r13d
0x140005f34  mov     rbx, [rdi]
0x140005f37  jmp     short loc_140005F56
0x140005f39  lea     rcx, [rbx+50h]; String1
0x140005f3d  mov     r8b, r13b; CaseInSensitive
0x140005f40  mov     rdx, r12; String2
0x140005f43  call    cs:__imp_RtlEqualUnicodeString
0x140005f4a  nop     dword ptr [rax+rax+00h]
0x140005f4f  test    al, al
0x140005f51  jnz     short loc_140005F5D
0x140005f53  mov     rbx, [rbx]
0x140005f56  cmp     rbx, rdi
0x140005f59  jnz     short loc_140005F39
0x140005f5b  jmp     short loc_140005F78
0x140005f5d  mov     rcx, rbx; Context
0x140005f60  call    cs:__imp_FltReferenceContext
0x140005f67  nop     dword ptr [rax+rax+00h]
0x140005f6c  mov     [r14], rbx
0x140005f6f  xor     ebp, ebp
0x140005f71  mov     rax, [rbx+10h]
0x140005f75  mov     [r15], rax
0x140005f78  test    sil, sil
0x140005f7b  jz      short loc_140005F9E
0x140005f7d  mov     rcx, [rdi+18h]; Resource
0x140005f81  test    rcx, rcx
0x140005f84  jz      short loc_140005F9E
0x140005f86  call    cs:__imp_ExReleaseResourceLite
0x140005f8d  nop     dword ptr [rax+rax+00h]
0x140005f92  call    cs:__imp_KeLeaveCriticalRegion
0x140005f99  nop     dword ptr [rax+rax+00h]
0x140005f9e  mov     eax, ebp
0x140005fa0  add     rsp, 28h
0x140005fa4  pop     r15
0x140005fa6  pop     r14
0x140005fa8  pop     r13
0x140005faa  pop     r12
0x140005fac  pop     rdi
0x140005fad  pop     rsi
0x140005fae  pop     rbp
0x140005faf  pop     rbx
0x140005fb0  retn
```
