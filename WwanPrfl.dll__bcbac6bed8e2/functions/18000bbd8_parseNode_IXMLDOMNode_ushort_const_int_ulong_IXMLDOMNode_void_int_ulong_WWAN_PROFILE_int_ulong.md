# _parseNode(IXMLDOMNode *,ushort const *,int,ulong (*)(IXMLDOMNode *,void *,int,ulong),WWAN_PROFILE *,int,ulong)

- ea: `0x18000bbd8`
- end: `0x18000bc8e`
- name: `?_parseNode@@YAKPEAUIXMLDOMNode@@PEBGHP6AK0PEAXHK@ZPEAUWWAN_PROFILE@@HK@Z`
- size: `182`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, const unsigned __int16 *, int, unsigned int (*)(struct IXMLDOMNode *, void *, int, unsigned int), struct WWAN_PROFILE *, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b670`
- `0x18000bc94`
- `0x18000c4a0`
- `0x18000f26c`
- `0x180011ba0`

## callees

- `0x18000bbd8`
- `0x1800131e4`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall _parseNode(
        struct IXMLDOMNode *a1,
        const unsigned __int16 *a2,
        int a3,
        unsigned int (*a4)(struct IXMLDOMNode *, void *, int, unsigned int),
        struct WWAN_PROFILE *a5,
        unsigned int a6,
        unsigned int a7)
{
  unsigned int SingleNode; // eax
  unsigned int v10; // ebx
  struct IXMLDOMNode *v12; // [rsp+30h] [rbp-18h] BYREF

  v12 = 0;
  SingleNode = XcGetSingleNode(a1, a2, &v12);
  v10 = SingleNode;
  if ( !SingleNode )
  {
    v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, struct WWAN_PROFILE *, _QWORD, _QWORD))a4)(v12, a5, a6, a7);
    if ( v12 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v12->lpVtbl->Release)(v12);
    return v10;
  }
  if ( !a3 || SingleNode != 1168 )
  {
    if ( v12 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v12->lpVtbl->Release)(v12);
    return v10;
  }
  if ( v12 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v12->lpVtbl->Release)(v12);
  return 0;
}

```

## disassembly

```asm
0x18000bbd8  mov     rax, rsp
0x18000bbdb  mov     [rax+8], rbx
0x18000bbdf  mov     [rax+10h], rsi
0x18000bbe3  push    rdi
0x18000bbe4  sub     rsp, 40h
0x18000bbe8  mov     rsi, r9
0x18000bbeb  mov     edi, r8d
0x18000bbee  mov     qword ptr [rax-18h], 0
0x18000bbf6  lea     r8, [rax-18h]; struct IXMLDOMNode **
0x18000bbfa  call    ?XcGetSingleNode@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAU1@@Z; XcGetSingleNode(IXMLDOMNode *,ushort const *,IXMLDOMNode * *)
0x18000bbff  mov     ebx, eax
0x18000bc01  test    eax, eax
0x18000bc03  jz      short loc_18000BC44
0x18000bc05  test    edi, edi
0x18000bc07  jz      short loc_18000BC2B
0x18000bc09  cmp     eax, 490h
0x18000bc0e  jnz     short loc_18000BC2B
0x18000bc10  mov     rcx, [rsp+48h+var_18]
0x18000bc15  test    rcx, rcx
0x18000bc18  jz      short loc_18000BC27
0x18000bc1a  mov     rax, [rcx]
0x18000bc1d  mov     rax, [rax+10h]
0x18000bc21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc26  nop
0x18000bc27  xor     eax, eax
0x18000bc29  jmp     short loc_18000BC7E
0x18000bc2b  mov     rcx, [rsp+48h+var_18]
0x18000bc30  test    rcx, rcx
0x18000bc33  jz      short loc_18000BC42
0x18000bc35  mov     rax, [rcx]
0x18000bc38  mov     rax, [rax+10h]
0x18000bc3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc41  nop
0x18000bc42  jmp     short loc_18000BC7C
0x18000bc44  mov     r9d, [rsp+48h+arg_30]
0x18000bc4c  mov     r8d, [rsp+48h+arg_28]
0x18000bc51  mov     rdx, [rsp+48h+arg_20]
0x18000bc56  mov     rcx, [rsp+48h+var_18]
0x18000bc5b  mov     rax, rsi
0x18000bc5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc63  mov     ebx, eax
0x18000bc65  mov     rcx, [rsp+48h+var_18]
0x18000bc6a  test    rcx, rcx
0x18000bc6d  jz      short loc_18000BC7C
0x18000bc6f  mov     rdx, [rcx]
0x18000bc72  mov     rax, [rdx+10h]
0x18000bc76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc7b  nop
0x18000bc7c  mov     eax, ebx
0x18000bc7e  mov     rbx, [rsp+48h+arg_0]
0x18000bc83  mov     rsi, [rsp+48h+arg_8]
0x18000bc88  add     rsp, 40h
0x18000bc8c  pop     rdi
0x18000bc8d  retn
```
