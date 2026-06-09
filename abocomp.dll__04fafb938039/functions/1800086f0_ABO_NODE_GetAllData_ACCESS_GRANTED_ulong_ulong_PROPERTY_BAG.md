# ABO_NODE::GetAllData(ACCESS_GRANTED,ulong,ulong,PROPERTY_BAG *)

- ea: `0x1800086f0`
- end: `0x1800087b6`
- name: `?GetAllData@ABO_NODE@@QEAAJW4ACCESS_GRANTED@@KKPEAVPROPERTY_BAG@@@Z`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d040`
- `0x18000d8f0`

## callees

- `0x1800086f0`
- `0x18000fa00`
- `0x18000ffd8`

## import_xrefs

- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008740`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000875d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008771`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008740`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000875d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180008771`

## pseudocode

```c
__int64 __fastcall ABO_NODE::GetAllData(__int64 a1, unsigned int a2, int a3, int a4, PROPERTY_BAG *a5)
{
  int v8; // ebx
  __int64 i; // rdi
  __int64 v10; // r13
  unsigned int *Ptr; // rax

  if ( a5 )
  {
    v8 = 0;
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 200); i = (unsigned int)(i + 1) )
    {
      v10 = *(_QWORD *)(*(_QWORD *)(a1 + 192) + 8 * i);
      Ptr = (unsigned int *)BUFFER::QueryPtr((BUFFER *)(v10 + 16));
      if ( PROPERTY_ENTRY::IsReadAccessAllowed(*Ptr, a2)
        && (!a3 || a3 == *((_DWORD *)BUFFER::QueryPtr((BUFFER *)(v10 + 16)) + 2))
        && (!a4 || a4 == *((_DWORD *)BUFFER::QueryPtr((BUFFER *)(v10 + 16)) + 3)) )
      {
        v8 = PROPERTY_BAG::AddEntry(a5, (struct PROPERTY_ENTRY *)v10, 0);
        if ( v8 < 0 )
          break;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800086f0  mov     [rsp+arg_0], rbx
0x1800086f5  mov     [rsp+arg_10], rbp
0x1800086fa  mov     [rsp+arg_8], edx
0x1800086fe  push    rsi
0x1800086ff  push    rdi
0x180008700  push    r13
0x180008702  push    r14
0x180008704  push    r15
0x180008706  sub     rsp, 20h
0x18000870a  cmp     [rsp+48h+arg_20], 0
0x180008710  mov     r14d, r9d
0x180008713  mov     r15d, r8d
0x180008716  mov     rsi, rcx
0x180008719  jnz     short loc_180008722
0x18000871b  mov     ebx, 80070057h
0x180008720  jmp     short loc_18000879D
0x180008722  xor     ebx, ebx
0x180008724  xor     edi, edi
0x180008726  cmp     [rcx+0C8h], ebx
0x18000872c  jbe     short loc_18000879D
0x18000872e  mov     rax, [rsi+0C0h]
0x180008735  mov     r13, [rax+rdi*8]
0x180008739  lea     rbp, [r13+10h]
0x18000873d  mov     rcx, rbp
0x180008740  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180008746  mov     edx, [rsp+48h+arg_8]
0x18000874a  mov     ecx, [rax]
0x18000874c  call    ?IsReadAccessAllowed@PROPERTY_ENTRY@@SAHKW4ACCESS_GRANTED@@@Z; PROPERTY_ENTRY::IsReadAccessAllowed(ulong,ACCESS_GRANTED)
0x180008751  test    eax, eax
0x180008753  jz      short loc_180008793
0x180008755  test    r15d, r15d
0x180008758  jz      short loc_180008769
0x18000875a  mov     rcx, rbp
0x18000875d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180008763  cmp     r15d, [rax+8]
0x180008767  jnz     short loc_180008793
0x180008769  test    r14d, r14d
0x18000876c  jz      short loc_18000877D
0x18000876e  mov     rcx, rbp
0x180008771  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180008777  cmp     r14d, [rax+0Ch]
0x18000877b  jnz     short loc_180008793
0x18000877d  mov     rcx, [rsp+48h+arg_20]; this
0x180008782  xor     r8d, r8d; int
0x180008785  mov     rdx, r13; struct PROPERTY_ENTRY *
0x180008788  call    ?AddEntry@PROPERTY_BAG@@QEAAJPEAVPROPERTY_ENTRY@@H@Z; PROPERTY_BAG::AddEntry(PROPERTY_ENTRY *,int)
0x18000878d  mov     ebx, eax
0x18000878f  test    eax, eax
0x180008791  js      short loc_18000879D
0x180008793  inc     edi
0x180008795  cmp     edi, [rsi+0C8h]
0x18000879b  jb      short loc_18000872E
0x18000879d  mov     rbp, [rsp+48h+arg_10]
0x1800087a2  mov     eax, ebx
0x1800087a4  mov     rbx, [rsp+48h+arg_0]
0x1800087a9  add     rsp, 20h
0x1800087ad  pop     r15
0x1800087af  pop     r14
0x1800087b1  pop     r13
0x1800087b3  pop     rdi
0x1800087b4  pop     rsi
0x1800087b5  retn
```
