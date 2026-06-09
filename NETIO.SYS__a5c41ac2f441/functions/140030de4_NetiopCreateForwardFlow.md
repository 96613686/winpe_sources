# NetiopCreateForwardFlow

- ea: `0x140030de4`
- end: `0x140030fa4`
- name: `NetiopCreateForwardFlow`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400304b0`

## callees

- `0x140017520`
- `0x1400176d0`
- `0x140030a08`
- `0x140030de4`
- `0x14003a130`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x140030f0f`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14007c68f`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140030f0f`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14007c68f`
- `ntoskrnl!RtlCreateHashTable` at `0x140030f59`
- `ntoskrnl!RtlCreateHashTable` at `0x140030f59`
- `ntoskrnl!KeInitializeSpinLock` at `0x140030ec8`
- `ntoskrnl!KeInitializeSpinLock` at `0x140030ec8`

## pseudocode

```c
_DWORD *__fastcall NetiopCreateForwardFlow(
        __int64 a1,
        __int16 a2,
        _DWORD *a3,
        _DWORD *a4,
        int a5,
        int a6,
        __int64 a7,
        signed __int64 *a8)
{
  __int64 v10; // rax
  __int64 v13; // rbx
  _DWORD *v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rax
  ULONG v18; // edx
  signed __int64 v19; // rbx
  PRTL_DYNAMIC_HASH_TABLE HashTable; // [rsp+20h] [rbp-48h] BYREF
  signed __int64 v21[8]; // [rsp+28h] [rbp-40h] BYREF

  v10 = 1888;
  if ( a2 != 2 )
    v10 = 1896;
  v13 = *(_QWORD *)(v10 + a1);
  v14 = (_DWORD *)PplAllocateFromLookasideList(v13);
  if ( !v14 )
    return 0;
  if ( a8 && !*(_QWORD *)(a1 + 80) )
  {
    v18 = *(_DWORD *)(a1 + 88);
    HashTable = 0;
    if ( !RtlCreateHashTable(&HashTable, v18, 0) )
    {
      PplFreeToLookasideList(v13, v14);
      return 0;
    }
    *(_QWORD *)(a1 + 80) = HashTable;
  }
  v15 = 0;
  v14[34] = a6;
  v14[12] = a5;
  *v14 = 1;
  *((_WORD *)v14 + 4) = a2;
  v14[4] = 0;
  do
  {
    *(_QWORD *)&v14[4 * v15 + 46] = 0;
    v16 = 2 * (v15 + 12);
    ++v15;
    *(_QWORD *)&v14[2 * v16] = 0;
  }
  while ( v15 != 3 );
  if ( a2 == 2 )
  {
    v14[59] = *a4;
    v14[58] = *a3;
  }
  else
  {
    *(_OWORD *)(v14 + 62) = *(_OWORD *)a4;
    *(_OWORD *)(v14 + 58) = *(_OWORD *)a3;
  }
  *(_OWORD *)(v14 + 38) = 0;
  *((_QWORD *)v14 + 21) = 0;
  KeInitializeSpinLock((PKSPIN_LOCK)v14 + 18);
  *((_QWORD *)v14 + 20) = v14 + 38;
  *((_QWORD *)v14 + 19) = v14 + 38;
  v14[44] = 2;
  if ( a8 )
  {
    v19 = _InterlockedIncrement64((volatile signed __int64 *)(a1 + 1904));
    HashTable = 0;
    v21[0] = v19;
    NetiopUpdateFlowHashSignature(v21, 8, &HashTable);
    RtlInsertEntryHashTable(
      *(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 80),
      (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v14 + 26),
      ((_QWORD)HashTable << *(_DWORD *)(a1 + 88)) | 1LL,
      0);
    v14[4] |= 0x10u;
    RoReferenceEx(v14 + 44);
    *a8 = v19;
  }
  RtlInsertEntryHashTable(
    (PRTL_DYNAMIC_HASH_TABLE)(a1 + 16),
    (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v14 + 14),
    (a7 << *(_DWORD *)(a1 + 56)) | 1,
    0);
  v14[4] |= 4u;
  RoReferenceEx(v14 + 44);
  return v14;
}

```

## disassembly

```asm
0x140030de4  push    rbx
0x140030de6  push    rbp
0x140030de7  push    rsi
0x140030de8  push    rdi
0x140030de9  push    r12
0x140030deb  push    r14
0x140030ded  push    r15
0x140030def  sub     rsp, 30h
0x140030df3  mov     rsi, rcx
0x140030df6  movzx   ebp, dx
0x140030df9  mov     eax, 760h
0x140030dfe  mov     edx, 2
0x140030e03  cmp     bp, dx
0x140030e06  mov     r14, r9
0x140030e09  mov     r12, r8
0x140030e0c  lea     ecx, [rax+8]
0x140030e0f  cmovnz  eax, ecx
0x140030e12  mov     rbx, [rax+rsi]
0x140030e16  mov     rcx, rbx
0x140030e19  call    PplAllocateFromLookasideList
0x140030e1e  mov     rdi, rax
0x140030e21  test    rax, rax
0x140030e24  jz      loc_140030F74
0x140030e2a  mov     r15, [rsp+68h+arg_38]
0x140030e32  test    r15, r15
0x140030e35  jnz     loc_140030F3A
0x140030e3b  mov     eax, [rsp+68h+arg_28]
0x140030e42  xor     ecx, ecx
0x140030e44  mov     [rdi+88h], eax
0x140030e4a  mov     eax, [rsp+68h+arg_20]
0x140030e51  mov     [rdi+30h], eax
0x140030e54  mov     dword ptr [rdi], 1
0x140030e5a  mov     [rdi+8], bp
0x140030e5e  mov     dword ptr [rdi+10h], 0
0x140030e65  mov     rax, rcx
0x140030e68  add     rax, rax
0x140030e6b  mov     qword ptr [rdi+rax*8+0B8h], 0
0x140030e77  lea     rax, [rcx+0Ch]
0x140030e7b  add     rax, rax
0x140030e7e  inc     rcx
0x140030e81  mov     qword ptr [rdi+rax*8], 0
0x140030e89  cmp     rcx, 3
0x140030e8d  jnz     short loc_140030E65
0x140030e8f  lea     eax, [rcx-1]
0x140030e92  cmp     bp, ax
0x140030e95  jnz     loc_140030F78
0x140030e9b  mov     eax, [r14]
0x140030e9e  mov     [rdi+0ECh], eax
0x140030ea4  mov     eax, [r12]
0x140030ea8  mov     [rdi+0E8h], eax
0x140030eae  lea     rbx, [rdi+98h]
0x140030eb5  xorps   xmm0, xmm0
0x140030eb8  xor     eax, eax
0x140030eba  lea     rcx, [rdi+90h]; SpinLock
0x140030ec1  movups  xmmword ptr [rbx], xmm0
0x140030ec4  mov     [rbx+10h], rax
0x140030ec8  call    cs:__imp_KeInitializeSpinLock
0x140030ecf  nop     dword ptr [rax+rax+00h]
0x140030ed4  mov     [rbx+8], rbx
0x140030ed8  lea     r14, [rdi+0B0h]
0x140030edf  mov     [rbx], rbx
0x140030ee2  mov     dword ptr [r14], 2
0x140030ee9  test    r15, r15
0x140030eec  jnz     loc_14007C642
0x140030ef2  mov     ecx, [rsi+38h]
0x140030ef5  lea     rdx, [rdi+38h]; Entry
0x140030ef9  mov     r8, [rsp+68h+arg_30]
0x140030f01  xor     r9d, r9d; Context
0x140030f04  shl     r8, cl
0x140030f07  lea     rcx, [rsi+10h]; HashTable
0x140030f0b  or      r8, 1; Signature
0x140030f0f  call    cs:__imp_RtlInsertEntryHashTable
0x140030f16  nop     dword ptr [rax+rax+00h]
0x140030f1b  or      dword ptr [rdi+10h], 4
0x140030f1f  mov     rcx, r14
0x140030f22  call    RoReferenceEx
0x140030f27  mov     rax, rdi
0x140030f2a  add     rsp, 30h
0x140030f2e  pop     r15
0x140030f30  pop     r14
0x140030f32  pop     r12
0x140030f34  pop     rdi
0x140030f35  pop     rsi
0x140030f36  pop     rbp
0x140030f37  pop     rbx
0x140030f38  retn
0x140030f3a  cmp     qword ptr [rsi+50h], 0
0x140030f3f  jnz     loc_140030E3B
0x140030f45  mov     edx, [rsi+58h]; Shift
0x140030f48  lea     rcx, [rsp+68h+HashTable]; HashTable
0x140030f4d  xor     r8d, r8d; Flags
0x140030f50  mov     [rsp+68h+HashTable], 0
0x140030f59  call    cs:__imp_RtlCreateHashTable
0x140030f60  nop     dword ptr [rax+rax+00h]
0x140030f65  test    al, al
0x140030f67  jnz     short loc_140030F96
0x140030f69  mov     rdx, rdi
0x140030f6c  mov     rcx, rbx
0x140030f6f  call    PplFreeToLookasideList
0x140030f74  xor     eax, eax
0x140030f76  jmp     short loc_140030F2A
0x140030f78  movups  xmm0, xmmword ptr [r14]
0x140030f7c  movdqu  xmmword ptr [rdi+0F8h], xmm0
0x140030f84  movups  xmm1, xmmword ptr [r12]
0x140030f89  movdqu  xmmword ptr [rdi+0E8h], xmm1
0x140030f91  jmp     loc_140030EAE
0x140030f96  mov     rax, [rsp+68h+HashTable]
0x140030f9b  mov     [rsi+50h], rax
0x140030f9f  jmp     loc_140030E3B
0x14007c642  mov     ebx, 1
0x14007c647  lock xadd [rsi+770h], rbx
0x14007c650  inc     rbx
0x14007c653  mov     [rsp+68h+HashTable], 0
0x14007c65c  lea     r8, [rsp+68h+HashTable]
0x14007c661  mov     [rsp+68h+var_40], rbx
0x14007c666  mov     edx, 8
0x14007c66b  lea     rcx, [rsp+68h+var_40]
0x14007c670  call    NetiopUpdateFlowHashSignature
0x14007c675  mov     ecx, [rsi+58h]
0x14007c678  lea     rdx, [rdi+68h]; Entry
0x14007c67c  mov     r8, [rsp+68h+HashTable]
0x14007c681  xor     r9d, r9d; Context
0x14007c684  shl     r8, cl
0x14007c687  mov     rcx, [rsi+50h]; HashTable
0x14007c68b  or      r8, 1; Signature
0x14007c68f  call    cs:__imp_RtlInsertEntryHashTable
0x14007c696  nop     dword ptr [rax+rax+00h]
0x14007c69b  or      dword ptr [rdi+10h], 10h
0x14007c69f  mov     rcx, r14
0x14007c6a2  call    RoReferenceEx
0x14007c6a7  mov     [r15], rbx
0x14007c6aa  jmp     loc_140030EF2
```
