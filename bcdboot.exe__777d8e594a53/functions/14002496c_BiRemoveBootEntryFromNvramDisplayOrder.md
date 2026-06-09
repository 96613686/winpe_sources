# BiRemoveBootEntryFromNvramDisplayOrder

- ea: `0x14002496c`
- end: `0x140024a20`
- name: `BiRemoveBootEntryFromNvramDisplayOrder`
- size: `180`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140021f58`

## callees

- `0x140024714`
- `0x14002496c`
- `0x140024a28`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140024a08`
- `ntdll!RtlFreeHeap` at `0x140024a08`

## pseudocode

```c
__int64 __fastcall BiRemoveBootEntryFromNvramDisplayOrder(__int64 a1)
{
  int v2; // eax
  _DWORD *v3; // rbx
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  unsigned int v9; // [rsp+38h] [rbp+10h] BYREF
  PVOID P; // [rsp+40h] [rbp+18h] BYREF

  v9 = 0;
  P = 0;
  v2 = BiQueryBootEntryOrder(&P, &v9);
  v3 = P;
  v4 = v2;
  if ( v2 < 0 )
    goto LABEL_10;
  v5 = v9;
  v6 = 0;
  if ( v9 )
  {
    while ( *((_DWORD *)P + v6) != *(_DWORD *)(*(_QWORD *)(a1 + 40) + 8LL) )
    {
      v6 = (unsigned int)(v6 + 1);
      if ( (unsigned int)v6 >= v9 )
        goto LABEL_5;
    }
    goto LABEL_6;
  }
LABEL_5:
  if ( (_DWORD)v6 != v9 )
  {
LABEL_6:
    v5 = v9 - 1;
    if ( (unsigned int)v6 < (unsigned int)v5 )
    {
      do
      {
        v7 = (unsigned int)(v6 + 1);
        v3[v6] = v3[v7];
        v6 = v7;
      }
      while ( (unsigned int)v7 < (unsigned int)v5 );
    }
  }
  if ( v9 != (_DWORD)v5 )
    v4 = BiSetBootEntryOrder(v3, v5);
LABEL_10:
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  return v4;
}

```

## disassembly

```asm
0x14002496c  mov     rax, rsp
0x14002496f  mov     [rax+8], rbx
0x140024973  mov     [rax+20h], rsi
0x140024977  push    rdi
0x140024978  sub     rsp, 20h
0x14002497c  mov     rsi, rcx
0x14002497f  mov     dword ptr [rax+10h], 0
0x140024986  lea     rcx, [rax+18h]
0x14002498a  mov     qword ptr [rax+18h], 0
0x140024992  lea     rdx, [rax+10h]
0x140024996  call    BiQueryBootEntryOrder
0x14002499b  mov     rbx, [rsp+28h+P]
0x1400249a0  mov     edi, eax
0x1400249a2  test    eax, eax
0x1400249a4  js      short loc_1400249F1
0x1400249a6  mov     rcx, [rsi+28h]
0x1400249aa  mov     edx, [rsp+28h+arg_8]
0x1400249ae  mov     r8d, [rcx+8]
0x1400249b2  xor     ecx, ecx
0x1400249b4  test    edx, edx
0x1400249b6  jz      short loc_1400249C4
0x1400249b8  cmp     [rbx+rcx*4], r8d
0x1400249bc  jz      short loc_1400249C8
0x1400249be  inc     ecx
0x1400249c0  cmp     ecx, edx
0x1400249c2  jb      short loc_1400249B8
0x1400249c4  cmp     ecx, edx
0x1400249c6  jz      short loc_1400249E1
0x1400249c8  dec     edx
0x1400249ca  cmp     ecx, edx
0x1400249cc  jnb     short loc_1400249E1
0x1400249ce  lea     r8d, [rcx+1]
0x1400249d2  mov     eax, [rbx+r8*4]
0x1400249d6  mov     [rbx+rcx*4], eax
0x1400249d9  mov     ecx, r8d
0x1400249dc  cmp     r8d, edx
0x1400249df  jb      short loc_1400249CE
0x1400249e1  cmp     [rsp+28h+arg_8], edx
0x1400249e5  jz      short loc_1400249F1
0x1400249e7  mov     rcx, rbx
0x1400249ea  call    BiSetBootEntryOrder
0x1400249ef  mov     edi, eax
0x1400249f1  test    rbx, rbx
0x1400249f4  jz      short loc_140024A0E
0x1400249f6  mov     rcx, gs:60h
0x1400249ff  mov     r8, rbx; P
0x140024a02  xor     edx, edx; Flags
0x140024a04  mov     rcx, [rcx+30h]; HeapHandle
0x140024a08  call    cs:__imp_RtlFreeHeap
0x140024a0e  mov     rbx, [rsp+28h+arg_0]
0x140024a13  mov     eax, edi
0x140024a15  mov     rsi, [rsp+28h+arg_18]
0x140024a1a  add     rsp, 20h
0x140024a1e  pop     rdi
0x140024a1f  retn
```
