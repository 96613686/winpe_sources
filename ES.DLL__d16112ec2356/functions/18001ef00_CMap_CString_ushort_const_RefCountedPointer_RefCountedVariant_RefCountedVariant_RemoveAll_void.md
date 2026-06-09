# CMap<CString,ushort const *,RefCountedPointer<RefCountedVariant>,RefCountedVariant *>::RemoveAll(void)

- ea: `0x18001ef00`
- end: `0x18001efac`
- name: `?RemoveAll@?$CMap@VCString@@PEBGV?$RefCountedPointer@URefCountedVariant@@@@PEAURefCountedVariant@@@@QEAAXXZ`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ee50`

## callees

- `0x18001ef00`
- `0x18001efb4`
- `0x18002c694`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ef38`

## pseudocode

```c
void __fastcall CMap<CString,unsigned short const *,RefCountedPointer<RefCountedVariant>,RefCountedVariant *>::RemoveAll(
        __int64 a1)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rbx
  unsigned int i; // ebx
  _QWORD *j; // rsi

  if ( *(_QWORD *)a1 )
  {
    for ( i = 0; i < *(_DWORD *)(a1 + 8); ++i )
    {
      for ( j = *(_QWORD **)(*(_QWORD *)a1 + 8LL * i); j; j = (_QWORD *)*j )
      {
        DestructElements<RefCountedPointer<RefCountedVariant>>(j + 3);
        DestructElements<CString>((CString *)(j + 2));
      }
    }
  }
  CoTaskMemFree(*(LPVOID *)a1);
  v2 = *(_QWORD **)(a1 + 24);
  *(_QWORD *)a1 = 0;
  *(_DWORD *)(a1 + 12) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  if ( v2 )
  {
    do
    {
      v3 = (_QWORD *)*v2;
      CoTaskMemFree(v2);
      v2 = v3;
    }
    while ( v3 );
  }
  *(_QWORD *)(a1 + 24) = 0;
}

```

## disassembly

```asm
0x18001ef00  mov     [rsp+arg_8], rbx
0x18001ef05  mov     [rsp+arg_10], rbp
0x18001ef0a  push    rdi
0x18001ef0b  sub     rsp, 20h
0x18001ef0f  xor     ebp, ebp
0x18001ef11  mov     rdi, rcx
0x18001ef14  cmp     [rcx], rbp
0x18001ef17  jnz     short loc_18001EF5A
0x18001ef19  mov     rcx, [rdi]; pv
0x18001ef1c  call    cs:__imp_CoTaskMemFree
0x18001ef22  mov     rcx, [rdi+18h]; pv
0x18001ef26  mov     [rdi], rbp
0x18001ef29  mov     [rdi+0Ch], ebp
0x18001ef2c  mov     [rdi+10h], rbp
0x18001ef30  test    rcx, rcx
0x18001ef33  jz      short loc_18001EF46
0x18001ef35  mov     rbx, [rcx]
0x18001ef38  call    cs:__imp_CoTaskMemFree
0x18001ef3e  mov     rcx, rbx
0x18001ef41  test    rbx, rbx
0x18001ef44  jnz     short loc_18001EF35
0x18001ef46  mov     rbx, [rsp+28h+arg_8]
0x18001ef4b  mov     [rdi+18h], rbp
0x18001ef4f  mov     rbp, [rsp+28h+arg_10]
0x18001ef54  add     rsp, 20h
0x18001ef58  pop     rdi
0x18001ef59  retn
0x18001ef5a  mov     ebx, ebp
0x18001ef5c  cmp     [rcx+8], ebx
0x18001ef5f  jbe     short loc_18001EF19
0x18001ef61  mov     [rsp+28h+arg_0], rsi
0x18001ef66  nop     word ptr [rax+rax+00000000h]
0x18001ef70  mov     rax, [rdi]
0x18001ef73  mov     ecx, ebx
0x18001ef75  mov     rsi, [rax+rcx*8]
0x18001ef79  test    rsi, rsi
0x18001ef7c  jnz     short loc_18001EF90
0x18001ef7e  inc     ebx
0x18001ef80  cmp     ebx, [rdi+8]
0x18001ef83  jb      short loc_18001EF70
0x18001ef85  mov     rsi, [rsp+28h+arg_0]
0x18001ef8a  jmp     short loc_18001EF19
0x18001ef90  lea     rcx, [rsi+18h]
0x18001ef94  call    ??$DestructElements@V?$RefCountedPointer@URefCountedVariant@@@@@@YAXPEAV?$RefCountedPointer@URefCountedVariant@@@@H@Z; DestructElements<RefCountedPointer<RefCountedVariant>>(RefCountedPointer<RefCountedVariant> *,int)
0x18001ef99  lea     rcx, [rsi+10h]; this
0x18001ef9d  call    ??$DestructElements@VCString@@@@YAXPEAVCString@@H@Z; DestructElements<CString>(CString *,int)
0x18001efa2  mov     rsi, [rsi]
0x18001efa5  test    rsi, rsi
0x18001efa8  jz      short loc_18001EF7E
0x18001efaa  jmp     short loc_18001EF90
```
