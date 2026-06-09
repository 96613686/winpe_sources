# BipParseConditionString

- ea: `0x18004c4cc`
- end: `0x18004c708`
- name: `BipParseConditionString`
- size: `572`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800486fc`
- `0x180087cc4`

## callees

- `0x180026080`
- `0x18004c4cc`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18004c638`
- `ntdll!RtlCompareUnicodeString` at `0x18004c660`
- `ntdll!RtlCompareUnicodeString` at `0x18004c638`
- `ntdll!RtlCompareUnicodeString` at `0x18004c660`
- `ntdll!RtlGUIDFromString` at `0x18004c607`
- `ntdll!RtlGUIDFromString` at `0x18004c607`
- `ntdll!RtlInitUnicodeString` at `0x18004c50f`
- `ntdll!RtlInitUnicodeString` at `0x18004c520`
- `ntdll!RtlInitUnicodeString` at `0x18004c5db`
- `ntdll!RtlInitUnicodeString` at `0x18004c616`
- `ntdll!RtlInitUnicodeString` at `0x18004c50f`
- `ntdll!RtlInitUnicodeString` at `0x18004c520`
- `ntdll!RtlInitUnicodeString` at `0x18004c5db`
- `ntdll!RtlInitUnicodeString` at `0x18004c616`
- `ntdll!RtlFreeHeap` at `0x18004c6e3`
- `ntdll!RtlFreeHeap` at `0x18004c6e3`
- `ntdll!RtlAllocateHeap` at `0x18004c583`
- `ntdll!RtlAllocateHeap` at `0x18004c583`

## pseudocode

```c
__int64 __fastcall BipParseConditionString(unsigned __int16 *a1, int *a2, PVOID *a3)
{
  NTSTATUS v5; // ebx
  unsigned int v7; // edi
  const WCHAR *v8; // r13
  unsigned __int64 v9; // rcx
  __int64 v10; // rax
  unsigned int v11; // edi
  char *Heap; // rax
  char *v13; // rdx
  const WCHAR *v14; // r14
  char *v15; // r15
  unsigned int v16; // eax
  __int64 v17; // rax
  const WCHAR *v18; // r13
  __int64 v19; // r14
  int v20; // ecx
  UNICODE_STRING String1; // [rsp+20h] [rbp-48h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+30h] [rbp-38h] BYREF
  UNICODE_STRING String2; // [rsp+40h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF
  const WCHAR *v26; // [rsp+B0h] [rbp+48h]

  v5 = 0;
  *a3 = 0;
  String1 = 0;
  GuidString = 0;
  DestinationString = 0;
  String2 = 0;
  RtlInitUnicodeString(&DestinationString, L"False");
  RtlInitUnicodeString(&String2, L"True");
  v7 = 0;
  v8 = (const WCHAR *)(*((_QWORD *)a1 + 1) + 2 * ((unsigned __int64)*a1 >> 1));
  *v8 = 0;
  v9 = *((_QWORD *)a1 + 1);
  v26 = v8;
  if ( v9 >= (unsigned __int64)v8 )
    goto LABEL_27;
  do
  {
    ++v7;
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(v9 + 2 * v10) );
    v9 += 2 * v10 + 2;
  }
  while ( v9 < (unsigned __int64)v8 );
  if ( v7 )
  {
    v11 = v7 >> 1;
    Heap = (char *)RtlAllocateHeap(BipHeap, 0, 32 * v11);
    *a3 = Heap;
    v13 = Heap;
    if ( Heap )
    {
      v14 = (const WCHAR *)*((_QWORD *)a1 + 1);
      v15 = &Heap[16 * v11];
      *a2 = 0;
      v16 = 0;
      while ( v14 < v8 && v16 < v11 )
      {
        *(_QWORD *)&v13[16 * v16] = &v15[16 * v16];
        RtlInitUnicodeString(&GuidString, v14);
        v17 = -1;
        do
          ++v17;
        while ( v14[v17] );
        v18 = &v14[v17 + 1];
        v5 = RtlGUIDFromString(&GuidString, (GUID *)&v15[16 * *a2]);
        RtlInitUnicodeString(&String1, v18);
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        if ( RtlCompareUnicodeString(&String1, &String2, 1u) )
        {
          if ( RtlCompareUnicodeString(&String1, &DestinationString, 1u) )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_S(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                45,
                WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids,
                String1.Buffer);
            v5 = -1073741811;
            goto LABEL_25;
          }
          v20 = *a2;
          v13 = (char *)*a3;
          *((_BYTE *)*a3 + 16 * (unsigned int)*a2 + 8) = 0;
        }
        else
        {
          v20 = *a2;
          v13 = (char *)*a3;
          *((_BYTE *)*a3 + 16 * (unsigned int)*a2 + 8) = 1;
        }
        v16 = v20 + 1;
        v14 = &v18[v19 + 1];
        v8 = v26;
        *a2 = v20 + 1;
      }
      if ( v5 >= 0 )
        return (unsigned int)v5;
    }
    else
    {
      v5 = -1073741801;
    }
LABEL_25:
    if ( *a3 )
    {
      RtlFreeHeap(BipHeap, 0, *a3);
      *a3 = 0;
    }
  }
  else
  {
LABEL_27:
    *a3 = 0;
    *a2 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004c4cc  push    rbp
0x18004c4ce  push    rbx
0x18004c4cf  push    rsi
0x18004c4d0  push    rdi
0x18004c4d1  push    r12
0x18004c4d3  push    r13
0x18004c4d5  push    r14
0x18004c4d7  push    r15
0x18004c4d9  mov     rbp, rsp
0x18004c4dc  sub     rsp, 68h
0x18004c4e0  xorps   xmm0, xmm0
0x18004c4e3  xorps   xmm1, xmm1
0x18004c4e6  mov     r12, rdx
0x18004c4e9  mov     r14, rcx
0x18004c4ec  xor     ebx, ebx
0x18004c4ee  lea     rdx, aFalse; "False"
0x18004c4f5  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004c4f9  mov     [r8], rbx
0x18004c4fc  movups  xmmword ptr [rbp+String1.Length], xmm0
0x18004c500  mov     rsi, r8
0x18004c503  movups  xmmword ptr [rbp+GuidString.Length], xmm1
0x18004c507  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004c50b  movups  xmmword ptr [rbp+String2.Length], xmm1
0x18004c50f  call    cs:__imp_RtlInitUnicodeString
0x18004c515  lea     rdx, aTrue; "True"
0x18004c51c  lea     rcx, [rbp+String2]; DestinationString
0x18004c520  call    cs:__imp_RtlInitUnicodeString
0x18004c526  movzx   ecx, word ptr [r14]
0x18004c52a  mov     edi, ebx
0x18004c52c  mov     rax, [r14+8]
0x18004c530  shr     rcx, 1
0x18004c533  lea     r13, [rax+rcx*2]
0x18004c537  mov     [r13+0], bx
0x18004c53c  mov     rcx, [r14+8]
0x18004c540  mov     [rbp+arg_0], r13
0x18004c544  cmp     rcx, r13
0x18004c547  jnb     loc_18004C6EE
0x18004c54d  inc     edi
0x18004c54f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004c553  inc     rax
0x18004c556  cmp     [rcx+rax*2], bx
0x18004c55a  jnz     short loc_18004C553
0x18004c55c  lea     rcx, [rcx+rax*2]
0x18004c560  add     rcx, 2
0x18004c564  cmp     rcx, r13
0x18004c567  jb      short loc_18004C54D
0x18004c569  test    edi, edi
0x18004c56b  jz      loc_18004C6EE
0x18004c571  mov     rcx, cs:BipHeap; HeapHandle
0x18004c578  xor     edx, edx; Flags
0x18004c57a  shr     edi, 1
0x18004c57c  mov     r8d, edi
0x18004c57f  shl     r8d, 5; Size
0x18004c583  call    cs:__imp_RtlAllocateHeap
0x18004c589  mov     [rsi], rax
0x18004c58c  mov     rdx, rax
0x18004c58f  test    rax, rax
0x18004c592  jnz     short loc_18004C59E
0x18004c594  mov     ebx, 0C0000017h
0x18004c599  jmp     loc_18004C6D0
0x18004c59e  mov     r14, [r14+8]
0x18004c5a2  mov     r15d, edi
0x18004c5a5  shl     r15, 4
0x18004c5a9  add     r15, rax
0x18004c5ac  xor     r8d, r8d
0x18004c5af  mov     [r12], r8d
0x18004c5b3  mov     eax, r8d
0x18004c5b6  cmp     r14, r13
0x18004c5b9  jnb     loc_18004C6CC
0x18004c5bf  cmp     eax, edi
0x18004c5c1  jnb     loc_18004C6CC
0x18004c5c7  mov     ecx, eax
0x18004c5c9  add     rcx, rcx
0x18004c5cc  lea     rax, [r15+rcx*8]
0x18004c5d0  mov     [rdx+rcx*8], rax
0x18004c5d4  mov     rdx, r14; SourceString
0x18004c5d7  lea     rcx, [rbp+GuidString]; DestinationString
0x18004c5db  call    cs:__imp_RtlInitUnicodeString
0x18004c5e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004c5e5  xor     ecx, ecx
0x18004c5e7  inc     rax
0x18004c5ea  cmp     [r14+rax*2], cx
0x18004c5ef  jnz     short loc_18004C5E7
0x18004c5f1  mov     edx, [r12]
0x18004c5f5  lea     rcx, [rbp+GuidString]; GuidString
0x18004c5f9  inc     rax
0x18004c5fc  shl     rdx, 4
0x18004c600  add     rdx, r15; Guid
0x18004c603  lea     r13, [r14+rax*2]
0x18004c607  call    cs:__imp_RtlGUIDFromString
0x18004c60d  mov     rdx, r13; SourceString
0x18004c610  lea     rcx, [rbp+String1]; DestinationString
0x18004c614  mov     ebx, eax
0x18004c616  call    cs:__imp_RtlInitUnicodeString
0x18004c61c  or      r14, 0FFFFFFFFFFFFFFFFh
0x18004c620  xor     eax, eax
0x18004c622  inc     r14
0x18004c625  cmp     [r13+r14*2+0], ax
0x18004c62b  jnz     short loc_18004C622
0x18004c62d  mov     r8b, 1; CaseInsensitive
0x18004c630  lea     rdx, [rbp+String2]; String2
0x18004c634  lea     rcx, [rbp+String1]; String1
0x18004c638  call    cs:__imp_RtlCompareUnicodeString
0x18004c63e  test    eax, eax
0x18004c640  jnz     short loc_18004C655
0x18004c642  mov     ecx, [r12]
0x18004c646  mov     rdx, [rsi]
0x18004c649  mov     eax, ecx
0x18004c64b  add     rax, rax
0x18004c64e  mov     byte ptr [rdx+rax*8+8], 1
0x18004c653  jmp     short loc_18004C67E
0x18004c655  mov     r8b, 1; CaseInsensitive
0x18004c658  lea     rdx, [rbp+DestinationString]; String2
0x18004c65c  lea     rcx, [rbp+String1]; String1
0x18004c660  call    cs:__imp_RtlCompareUnicodeString
0x18004c666  xor     r8d, r8d
0x18004c669  test    eax, eax
0x18004c66b  jnz     short loc_18004C699
0x18004c66d  mov     ecx, [r12]
0x18004c671  mov     rdx, [rsi]
0x18004c674  mov     eax, ecx
0x18004c676  add     rax, rax
0x18004c679  mov     [rdx+rax*8+8], r8b
0x18004c67e  lea     r14, ds:2[r14*2]
0x18004c686  lea     eax, [rcx+1]
0x18004c689  add     r14, r13
0x18004c68c  mov     r13, [rbp+arg_0]
0x18004c690  mov     [r12], eax
0x18004c694  jmp     loc_18004C5B6
0x18004c699  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c6a0  test    byte ptr [rcx+1Ch], 8
0x18004c6a4  jz      short loc_18004C6C5
0x18004c6a6  cmp     byte ptr [rcx+19h], 2
0x18004c6aa  jb      short loc_18004C6C5
0x18004c6ac  mov     r9, [rbp+String1.Buffer]
0x18004c6b0  lea     r8, WPP_00ce70eff5b13500e7a162950ad2fc75_Traceguids
0x18004c6b7  mov     rcx, [rcx+10h]
0x18004c6bb  mov     edx, 2Dh ; '-'
0x18004c6c0  call    WPP_SF_S
0x18004c6c5  mov     ebx, 0C000000Dh
0x18004c6ca  jmp     short loc_18004C6D0
0x18004c6cc  test    ebx, ebx
0x18004c6ce  jns     short loc_18004C6F5
0x18004c6d0  mov     r8, [rsi]; P
0x18004c6d3  xor     edi, edi
0x18004c6d5  test    r8, r8
0x18004c6d8  jz      short loc_18004C6F5
0x18004c6da  mov     rcx, cs:BipHeap; HeapHandle
0x18004c6e1  xor     edx, edx; Flags
0x18004c6e3  call    cs:__imp_RtlFreeHeap
0x18004c6e9  mov     [rsi], rdi
0x18004c6ec  jmp     short loc_18004C6F5
0x18004c6ee  mov     [rsi], rbx
0x18004c6f1  mov     [r12], ebx
0x18004c6f5  mov     eax, ebx
0x18004c6f7  add     rsp, 68h
0x18004c6fb  pop     r15
0x18004c6fd  pop     r14
0x18004c6ff  pop     r13
0x18004c701  pop     r12
0x18004c703  pop     rdi
0x18004c704  pop     rsi
0x18004c705  pop     rbx
0x18004c706  pop     rbp
0x18004c707  retn
```
