# BiGetNtPartitionPath

- ea: `0x1400171b4`
- end: `0x14001730f`
- name: `BiGetNtPartitionPath`
- size: `347`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x140015160`

## callees

- `0x1400171b4`
- `0x1400182d8`
- `0x140018498`
- `0x140020ba4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14001721b`
- `ntdll!RtlAllocateHeap` at `0x14001721b`
- `ntdll!RtlFreeHeap` at `0x140017249`
- `ntdll!RtlFreeHeap` at `0x140017269`
- `ntdll!RtlFreeHeap` at `0x1400172f1`
- `ntdll!RtlFreeHeap` at `0x140017249`
- `ntdll!RtlFreeHeap` at `0x140017269`
- `ntdll!RtlFreeHeap` at `0x1400172f1`

## pseudocode

```c
__int64 __fastcall BiGetNtPartitionPath(int a1, _QWORD *a2)
{
  int v3; // ebx
  char v5; // al
  __int64 v6; // rax
  __int128 v7; // [rsp+30h] [rbp-30h] BYREF
  __int128 P; // [rsp+40h] [rbp-20h] BYREF
  __int128 v9; // [rsp+50h] [rbp-10h] BYREF

  v7 = 0;
  P = 0;
  v9 = 0;
  v3 = BiVerifyBootPartition(a1, (unsigned int)&v9, (unsigned int)&v9 + 8, (unsigned int)&P + 8, (__int64)&v7 + 8, 0);
  if ( v3 >= 0 )
  {
    *(_QWORD *)&P = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x6Au);
    if ( (_QWORD)P )
    {
      if ( *((_QWORD *)&v7 + 1) && !(_QWORD)v9 )
      {
        v5 = BYTE1(v7);
        if ( !*((_QWORD *)&v9 + 1) )
          v5 = 1;
        BYTE1(v7) = v5;
      }
      v3 = SyspartEnumerateDisks(BiGetNtPartitionPathCallback, &v7);
      if ( v3 >= 0 )
      {
        if ( (_BYTE)v7 )
        {
          if ( (int)BiTranslateSymbolicLink((PCWSTR)P) < 0 )
          {
            v6 = P;
          }
          else
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)P);
            v6 = 0;
            *(_QWORD *)&P = 0;
          }
          *a2 = v6;
          v3 = 0;
          goto LABEL_6;
        }
        v3 = -1073741811;
      }
    }
    else
    {
      v3 = -1073741801;
    }
  }
  if ( (_QWORD)P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)P);
LABEL_6:
  if ( *((_QWORD *)&v7 + 1) )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)&v7 + 1));
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400171b4  mov     r11, rsp
0x1400171b7  mov     [r11+8], rbx
0x1400171bb  mov     [r11+10h], rdi
0x1400171bf  push    rbp
0x1400171c0  mov     rbp, rsp
0x1400171c3  sub     rsp, 60h
0x1400171c7  xorps   xmm0, xmm0
0x1400171ca  mov     qword ptr [r11-40h], 0
0x1400171d2  mov     rdi, rdx
0x1400171d5  mov     [rbp+arg_10], 0
0x1400171dd  lea     rax, [rbp+var_28]
0x1400171e1  lea     rdx, [rbp+var_10]
0x1400171e5  mov     [r11-48h], rax
0x1400171e9  lea     r9, [rbp+var_18]
0x1400171ed  lea     r8, [rbp+var_10+8]
0x1400171f1  movups  xmmword ptr [rbp-30h], xmm0
0x1400171f5  movups  xmmword ptr [rbp-20h], xmm0
0x1400171f9  movups  [rbp+var_10], xmm0
0x1400171fd  call    BiVerifyBootPartition
0x140017202  mov     ebx, eax
0x140017204  test    eax, eax
0x140017206  js      short loc_14001722F
0x140017208  mov     rcx, gs:60h
0x140017211  xor     edx, edx; Flags
0x140017213  mov     rcx, [rcx+30h]; HeapHandle
0x140017217  lea     r8d, [rdx+6Ah]; Size
0x14001721b  call    cs:__imp_RtlAllocateHeap
0x140017221  mov     [rbp+P], rax
0x140017225  test    rax, rax
0x140017228  jnz     short loc_140017281
0x14001722a  mov     ebx, 0C0000017h
0x14001722f  cmp     [rbp+P], 0
0x140017234  jz      short loc_14001724F
0x140017236  mov     rcx, gs:60h
0x14001723f  xor     edx, edx; Flags
0x140017241  mov     r8, [rbp+P]; P
0x140017245  mov     rcx, [rcx+30h]; HeapHandle
0x140017249  call    cs:__imp_RtlFreeHeap
0x14001724f  cmp     [rbp+var_28], 0
0x140017254  jz      short loc_14001726F
0x140017256  mov     rcx, gs:60h
0x14001725f  xor     edx, edx; Flags
0x140017261  mov     r8, [rbp+var_28]; P
0x140017265  mov     rcx, [rcx+30h]; HeapHandle
0x140017269  call    cs:__imp_RtlFreeHeap
0x14001726f  mov     rdi, [rsp+60h+arg_8]
0x140017274  mov     eax, ebx
0x140017276  mov     rbx, [rsp+60h+arg_0]
0x14001727b  add     rsp, 60h
0x14001727f  pop     rbp
0x140017280  retn
0x140017281  cmp     [rbp+var_28], 0
0x140017286  jz      short loc_1400172A3
0x140017288  cmp     qword ptr [rbp+var_10], 0
0x14001728d  jnz     short loc_1400172A3
0x14001728f  movzx   eax, [rbp+var_2F]
0x140017293  mov     ecx, 1
0x140017298  cmp     qword ptr [rbp+var_10+8], 0
0x14001729d  cmovz   eax, ecx
0x1400172a0  mov     [rbp+var_2F], al
0x1400172a3  lea     rdx, [rbp+var_30]
0x1400172a7  lea     rcx, BiGetNtPartitionPathCallback
0x1400172ae  call    SyspartEnumerateDisks
0x1400172b3  mov     ebx, eax
0x1400172b5  test    eax, eax
0x1400172b7  js      loc_14001722F
0x1400172bd  cmp     [rbp+var_30], 0
0x1400172c1  jnz     short loc_1400172CD
0x1400172c3  mov     ebx, 0C000000Dh
0x1400172c8  jmp     loc_14001722F
0x1400172cd  mov     rcx, [rbp+P]; SourceString
0x1400172d1  lea     rdx, [rbp+arg_10]
0x1400172d5  call    BiTranslateSymbolicLink
0x1400172da  test    eax, eax
0x1400172dc  js      short loc_140017301
0x1400172de  mov     rcx, gs:60h
0x1400172e7  xor     edx, edx; Flags
0x1400172e9  mov     r8, [rbp+P]; P
0x1400172ed  mov     rcx, [rcx+30h]; HeapHandle
0x1400172f1  call    cs:__imp_RtlFreeHeap
0x1400172f7  mov     rax, [rbp+arg_10]
0x1400172fb  mov     [rbp+P], rax
0x1400172ff  jmp     short loc_140017305
0x140017301  mov     rax, [rbp+P]
0x140017305  mov     [rdi], rax
0x140017308  xor     ebx, ebx
0x14001730a  jmp     loc_14001724F
```
