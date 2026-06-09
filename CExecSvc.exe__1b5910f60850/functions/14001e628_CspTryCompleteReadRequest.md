# CspTryCompleteReadRequest

- ea: `0x14001e628`
- end: `0x14001e704`
- name: `CspTryCompleteReadRequest`
- size: `220`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001d83c`
- `0x14001faf0`
- `0x14001ff00`

## callees

- `0x14001dd4c`
- `0x14001ded4`
- `0x14001e20c`
- `0x14001e628`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14001e6de`
- `ntdll!RtlFreeHeap` at `0x14001e6de`

## pseudocode

```c
void __fastcall CspTryCompleteReadRequest(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  void **v5; // rsi
  _BYTE *v6; // rbx
  char v7; // al
  __int64 v8; // rdx
  _QWORD *v9; // rax
  void **v10; // rcx

  v5 = (void **)(a1 + 112);
  while ( 1 )
  {
    v6 = *v5;
    if ( *v5 == v5 )
      break;
    if ( v6[16] )
      *(_DWORD *)(a1 + 136) = 0;
    switch ( *((_DWORD *)v6 + 5) )
    {
      case 1:
        LOBYTE(a3) = 1;
LABEL_14:
        v8 = (__int64)(v6 + 24);
        if ( (*(_BYTE *)(a1 + 132) & 2) != 0 )
          v7 = CspHandleLineRead(a1, v8, a3, a4);
        else
          v7 = CspHandleRawRead(a1, v8, a3);
        goto LABEL_17;
      case 2:
        a3 = 0;
        goto LABEL_14;
      case 3:
        a3 = 0;
        break;
      case 4:
        LOBYTE(a3) = 1;
        break;
      default:
        v6[16] = 0;
        return;
    }
    v7 = CspHandleEventRead(a1, v6 + 24, a3);
LABEL_17:
    v6[16] = 0;
    if ( !v7 )
      return;
    v9 = *(_QWORD **)v6;
    if ( *(_BYTE **)(*(_QWORD *)v6 + 8LL) != v6 || (v10 = (void **)*((_QWORD *)v6 + 1), *v10 != v6) )
      __fastfail(3u);
    *v10 = v9;
    v9[1] = v10;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  }
}

```

## disassembly

```asm
0x14001e628  mov     [rsp+arg_0], rbx
0x14001e62d  mov     [rsp+arg_8], rsi
0x14001e632  push    rdi
0x14001e633  sub     rsp, 20h
0x14001e637  mov     rdi, rcx
0x14001e63a  lea     rsi, [rcx+70h]
0x14001e63e  mov     rbx, [rsi]
0x14001e641  cmp     rbx, rsi
0x14001e644  jz      loc_14001E6ED
0x14001e64a  cmp     byte ptr [rbx+10h], 0
0x14001e64e  jz      short loc_14001E65A
0x14001e650  mov     dword ptr [rdi+88h], 0
0x14001e65a  mov     ecx, [rbx+14h]
0x14001e65d  sub     ecx, 1
0x14001e660  jz      short loc_14001E68C
0x14001e662  sub     ecx, 1
0x14001e665  jz      short loc_14001E687
0x14001e667  sub     ecx, 1
0x14001e66a  jz      short loc_14001E676
0x14001e66c  cmp     ecx, 1
0x14001e66f  jnz     short loc_14001E6E9
0x14001e671  mov     r8b, cl
0x14001e674  jmp     short loc_14001E679
0x14001e676  xor     r8d, r8d
0x14001e679  lea     rdx, [rbx+18h]
0x14001e67d  mov     rcx, rdi
0x14001e680  call    CspHandleEventRead
0x14001e685  jmp     short loc_14001E6AB
0x14001e687  xor     r8d, r8d
0x14001e68a  jmp     short loc_14001E68F
0x14001e68c  mov     r8b, 1
0x14001e68f  test    byte ptr [rdi+84h], 2
0x14001e696  lea     rdx, [rbx+18h]
0x14001e69a  mov     rcx, rdi
0x14001e69d  jz      short loc_14001E6A6
0x14001e69f  call    CspHandleLineRead
0x14001e6a4  jmp     short loc_14001E6AB
0x14001e6a6  call    CspHandleRawRead
0x14001e6ab  mov     byte ptr [rbx+10h], 0
0x14001e6af  test    al, al
0x14001e6b1  jz      short loc_14001E6ED
0x14001e6b3  mov     rax, [rbx]
0x14001e6b6  cmp     [rax+8], rbx
0x14001e6ba  jnz     short loc_14001E6FD
0x14001e6bc  mov     rcx, [rbx+8]
0x14001e6c0  cmp     [rcx], rbx
0x14001e6c3  jnz     short loc_14001E6FD
0x14001e6c5  mov     [rcx], rax
0x14001e6c8  mov     r8, rbx; P
0x14001e6cb  mov     [rax+8], rcx
0x14001e6cf  xor     edx, edx; Flags
0x14001e6d1  mov     rcx, gs:60h
0x14001e6da  mov     rcx, [rcx+30h]; HeapHandle
0x14001e6de  call    cs:__imp_RtlFreeHeap
0x14001e6e4  jmp     loc_14001E63E
0x14001e6e9  mov     byte ptr [rbx+10h], 0
0x14001e6ed  mov     rbx, [rsp+28h+arg_0]
0x14001e6f2  mov     rsi, [rsp+28h+arg_8]
0x14001e6f7  add     rsp, 20h
0x14001e6fb  pop     rdi
0x14001e6fc  retn
0x14001e6fd  mov     ecx, 3
0x14001e702  int     29h; Win8: RtlFailFast(ecx)
```
