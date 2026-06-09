# EdppDeleteLogFile

- ea: `0x14002e3cc`
- end: `0x14002e455`
- name: `EdppDeleteLogFile`
- size: `137`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14002ba70`
- `0x14002e9d8`

## callees

- `0x140005a10`
- `0x14002e3cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002e42a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e43b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e42a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e43b`
- `ntoskrnl!ZwDeleteFile` at `0x14002e407`
- `ntoskrnl!ZwDeleteFile` at `0x14002e407`

## pseudocode

```c
__int64 __fastcall EdppDeleteLogFile(const unsigned __int16 *a1)
{
  NTSTATUS v1; // edi
  PVOID v2; // rbx
  void *v3; // rcx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-38h] BYREF
  PVOID P; // [rsp+68h] [rbp+10h] BYREF

  P = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v1 = EdppCreateFileObject(a1, &ObjectAttributes, (struct _UNICODE_STRING **)&P);
  if ( v1 >= 0 )
    v1 = ZwDeleteFile(&ObjectAttributes);
  v2 = P;
  if ( P )
  {
    v3 = (void *)*((_QWORD *)P + 1);
    if ( v3 )
      ExFreePoolWithTag(v3, 0);
    ExFreePoolWithTag(v2, 0);
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14002e3cc  mov     rax, rsp
0x14002e3cf  mov     [rax+8], rbx
0x14002e3d3  push    rdi
0x14002e3d4  sub     rsp, 50h
0x14002e3d8  xorps   xmm0, xmm0
0x14002e3db  mov     qword ptr [rax+10h], 0
0x14002e3e3  lea     r8, [rax+10h]; struct _UNICODE_STRING **
0x14002e3e7  lea     rdx, [rax-38h]; struct _OBJECT_ATTRIBUTES *
0x14002e3eb  movups  xmmword ptr [rax-38h], xmm0
0x14002e3ef  movups  xmmword ptr [rax-28h], xmm0
0x14002e3f3  movups  xmmword ptr [rax-18h], xmm0
0x14002e3f7  call    ?EdppCreateFileObject@@YAJPEBGPEAU_OBJECT_ATTRIBUTES@@PEAPEAU_UNICODE_STRING@@@Z; EdppCreateFileObject(ushort const *,_OBJECT_ATTRIBUTES *,_UNICODE_STRING * *)
0x14002e3fc  mov     edi, eax
0x14002e3fe  test    eax, eax
0x14002e400  js      short loc_14002E415
0x14002e402  lea     rcx, [rsp+58h+ObjectAttributes]; ObjectAttributes
0x14002e407  call    cs:__imp_ZwDeleteFile
0x14002e40e  nop     dword ptr [rax+rax+00h]
0x14002e413  mov     edi, eax
0x14002e415  mov     rbx, [rsp+58h+P]
0x14002e41a  test    rbx, rbx
0x14002e41d  jz      short loc_14002E447
0x14002e41f  mov     rcx, [rbx+8]; P
0x14002e423  test    rcx, rcx
0x14002e426  jz      short loc_14002E436
0x14002e428  xor     edx, edx; Tag
0x14002e42a  call    cs:__imp_ExFreePoolWithTag
0x14002e431  nop     dword ptr [rax+rax+00h]
0x14002e436  xor     edx, edx; Tag
0x14002e438  mov     rcx, rbx; P
0x14002e43b  call    cs:__imp_ExFreePoolWithTag
0x14002e442  nop     dword ptr [rax+rax+00h]
0x14002e447  mov     rbx, [rsp+58h+arg_0]
0x14002e44c  mov     eax, edi
0x14002e44e  add     rsp, 50h
0x14002e452  pop     rdi
0x14002e453  retn
```
