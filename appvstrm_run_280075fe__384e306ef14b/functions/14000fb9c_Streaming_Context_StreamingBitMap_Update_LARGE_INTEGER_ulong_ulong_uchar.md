# Streaming::Context::StreamingBitMap::Update(_LARGE_INTEGER,ulong,ulong &,uchar)

- ea: `0x14000fb9c`
- end: `0x14000fcf6`
- name: `?Update@StreamingBitMap@Context@Streaming@@QEAAET_LARGE_INTEGER@@KAEAKE@Z`
- size: `346`
- prototype: `unsigned __int8 __usercall@<al>(PRTL_BITMAP BitMapHeader@<rcx>, union _LARGE_INTEGER@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned __int8)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000984c`

## callees

- `0x14000fb9c`

## import_xrefs

- `ntoskrnl!RtlSetBits` at `0x14000fc6d`
- `ntoskrnl!RtlSetBits` at `0x14000fc6d`
- `ntoskrnl!RtlAreBitsSet` at `0x14000fc55`
- `ntoskrnl!RtlAreBitsSet` at `0x14000fcac`
- `ntoskrnl!RtlAreBitsSet` at `0x14000fc55`
- `ntoskrnl!RtlAreBitsSet` at `0x14000fcac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000fcd5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000fcd5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fcc9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000fcc9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000fc23`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000fc23`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000fc10`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000fc10`

## pseudocode

```c
unsigned __int8 __fastcall Streaming::Context::StreamingBitMap::Update(
        PRTL_BITMAP BitMapHeader,
        union _LARGE_INTEGER a2,
        unsigned int a3,
        unsigned int *a4)
{
  unsigned int v4; // r14d
  LONGLONG v7; // rbp
  unsigned int v8; // r15d
  bool v10; // di
  unsigned int v11; // esi
  int v12; // eax
  struct _ERESOURCE *v13; // rcx
  unsigned __int8 v15; // [rsp+90h] [rbp+28h]

  *a4 = 0;
  v4 = a3;
  v7 = a2.QuadPart / 0x10000;
  v8 = HIWORD(a3) + ((_WORD)a3 != 0);
  if ( v8 + (unsigned int)(a2.QuadPart / 0x10000) > 8 * BitMapHeader[1].SizeOfBitMap )
    return 0;
  v10 = 0;
  v15 = 0;
  if ( *(_QWORD *)&BitMapHeader[3].SizeOfBitMap )
  {
    KeEnterCriticalRegion();
    v10 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)&BitMapHeader[3].SizeOfBitMap, 1u) == 1;
    v15 = v10;
  }
  v11 = 0;
  if ( v8 )
  {
    do
    {
      if ( !RtlAreBitsSet(BitMapHeader, v7, 1u) )
      {
        RtlSetBits(BitMapHeader, v7, 1u);
        v12 = v4;
        if ( v4 > 0x10000 )
          v12 = 0x10000;
        *a4 += v12;
      }
      LODWORD(v7) = v7 + 1;
      v4 -= 0x10000;
      ++v11;
    }
    while ( v11 < v8 );
    v10 = v15;
  }
  LOBYTE(BitMapHeader[3].Buffer) = RtlAreBitsSet(BitMapHeader, 0, 8 * BitMapHeader[1].SizeOfBitMap);
  if ( v10 )
  {
    v13 = *(struct _ERESOURCE **)&BitMapHeader[3].SizeOfBitMap;
    if ( v13 )
    {
      ExReleaseResourceLite(v13);
      KeLeaveCriticalRegion();
    }
  }
  return 1;
}

```

## disassembly

```asm
0x14000fb9c  push    rbx
0x14000fb9e  push    rbp
0x14000fb9f  push    rsi
0x14000fba0  push    rdi
0x14000fba1  push    r12
0x14000fba3  push    r13
0x14000fba5  push    r14
0x14000fba7  push    r15
0x14000fba9  sub     rsp, 28h
0x14000fbad  xor     r15d, r15d
0x14000fbb0  mov     r10d, r8d
0x14000fbb3  mov     rax, rdx
0x14000fbb6  mov     dword ptr [r9], 0
0x14000fbbd  cqo
0x14000fbbf  mov     r14d, r8d
0x14000fbc2  mov     rbx, rcx
0x14000fbc5  movzx   edx, dx
0x14000fbc8  add     rax, rdx
0x14000fbcb  mov     r12, r9
0x14000fbce  sar     rax, 10h
0x14000fbd2  test    r8w, r8w
0x14000fbd6  mov     rbp, rax
0x14000fbd9  setnz   r15b
0x14000fbdd  shr     r10, 10h
0x14000fbe1  add     r15d, r10d
0x14000fbe4  lea     ecx, [r15+rax]
0x14000fbe8  mov     eax, [rbx+10h]
0x14000fbeb  shl     eax, 3
0x14000fbee  cmp     ecx, eax
0x14000fbf0  jbe     short loc_14000FBF9
0x14000fbf2  xor     al, al
0x14000fbf4  jmp     loc_14000FCE4
0x14000fbf9  xor     dil, dil
0x14000fbfc  mov     r13d, 1
0x14000fc02  cmp     qword ptr [rbx+30h], 0
0x14000fc07  mov     dword ptr [rsp+68h+arg_20], edi
0x14000fc0e  jz      short loc_14000FC41
0x14000fc10  call    cs:__imp_KeEnterCriticalRegion
0x14000fc17  nop     dword ptr [rax+rax+00h]
0x14000fc1c  mov     rcx, [rbx+30h]; Resource
0x14000fc20  mov     dl, r13b; Wait
0x14000fc23  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000fc2a  nop     dword ptr [rax+rax+00h]
0x14000fc2f  cmp     al, r13b
0x14000fc32  movzx   edi, dil
0x14000fc36  cmovz   edi, r13d
0x14000fc3a  mov     dword ptr [rsp+68h+arg_20], edi
0x14000fc41  xor     esi, esi
0x14000fc43  test    r15d, r15d
0x14000fc46  jz      short loc_14000FC9F
0x14000fc48  mov     edi, 10000h
0x14000fc4d  mov     r8d, r13d; Length
0x14000fc50  mov     edx, ebp; StartingIndex
0x14000fc52  mov     rcx, rbx; BitMapHeader
0x14000fc55  call    cs:__imp_RtlAreBitsSet
0x14000fc5c  nop     dword ptr [rax+rax+00h]
0x14000fc61  test    al, al
0x14000fc63  jnz     short loc_14000FC86
0x14000fc65  mov     r8d, r13d; NumberToSet
0x14000fc68  mov     edx, ebp; StartingIndex
0x14000fc6a  mov     rcx, rbx; BitMapHeader
0x14000fc6d  call    cs:__imp_RtlSetBits
0x14000fc74  nop     dword ptr [rax+rax+00h]
0x14000fc79  cmp     r14d, edi
0x14000fc7c  mov     eax, r14d
0x14000fc7f  cmova   eax, edi
0x14000fc82  add     [r12], eax
0x14000fc86  add     ebp, r13d
0x14000fc89  add     r14d, 0FFFF0000h
0x14000fc90  add     esi, r13d
0x14000fc93  cmp     esi, r15d
0x14000fc96  jb      short loc_14000FC4D
0x14000fc98  mov     edi, dword ptr [rsp+68h+arg_20]
0x14000fc9f  mov     r8d, [rbx+10h]
0x14000fca3  xor     edx, edx; StartingIndex
0x14000fca5  shl     r8d, 3; Length
0x14000fca9  mov     rcx, rbx; BitMapHeader
0x14000fcac  call    cs:__imp_RtlAreBitsSet
0x14000fcb3  nop     dword ptr [rax+rax+00h]
0x14000fcb8  mov     [rbx+38h], al
0x14000fcbb  test    dil, dil
0x14000fcbe  jz      short loc_14000FCE1
0x14000fcc0  mov     rcx, [rbx+30h]; Resource
0x14000fcc4  test    rcx, rcx
0x14000fcc7  jz      short loc_14000FCE1
0x14000fcc9  call    cs:__imp_ExReleaseResourceLite
0x14000fcd0  nop     dword ptr [rax+rax+00h]
0x14000fcd5  call    cs:__imp_KeLeaveCriticalRegion
0x14000fcdc  nop     dword ptr [rax+rax+00h]
0x14000fce1  mov     al, r13b
0x14000fce4  add     rsp, 28h
0x14000fce8  pop     r15
0x14000fcea  pop     r14
0x14000fcec  pop     r13
0x14000fcee  pop     r12
0x14000fcf0  pop     rdi
0x14000fcf1  pop     rsi
0x14000fcf2  pop     rbp
0x14000fcf3  pop     rbx
0x14000fcf4  retn
```
