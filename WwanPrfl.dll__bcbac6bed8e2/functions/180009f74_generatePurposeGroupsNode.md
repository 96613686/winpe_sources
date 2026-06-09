# _generatePurposeGroupsNode

- ea: `0x180009f74`
- end: `0x18000a0ea`
- name: `_generatePurposeGroupsNode`
- size: `374`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a298`

## callees

- `0x180001670`
- `0x180009f74`
- `0x180011f90`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a030`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000a030`

## string_xrefs

- `0x180009fc9`: `http://www.microsoft.com/networking/WWAN/profile/v4`
- `0x18000a051`: `http://www.microsoft.com/networking/WWAN/profile/v4`

## pseudocode

```c
__int64 __fastcall generatePurposeGroupsNode(struct IXMLDOMDocument2 *a1, struct IXMLDOMNode *a2, __int64 a3)
{
  unsigned int v5; // ebx
  __int64 v7; // rdi
  struct IXMLDOMNode *v8; // rbx
  unsigned int v9; // esi
  struct IXMLDOMNode *v10; // [rsp+30h] [rbp-98h] BYREF
  OLECHAR sz[40]; // [rsp+40h] [rbp-88h] BYREF

  if ( !*(_DWORD *)(a3 + 5536) )
    return 0;
  v10 = 0;
  v5 = XcAddChildElement(
         a1,
         a2,
         (OLECHAR *)L"PurposeGroups",
         (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4",
         0,
         &v10);
  if ( v5 )
  {
    if ( v10 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v10->lpVtbl->Release)(v10);
    return v5;
  }
  v7 = 0;
  v8 = v10;
  while ( 1 )
  {
    if ( (*((_DWORD *)qword_18001F2C0 + 5 * v7) & *(_DWORD *)(a3 + 5536)) == 0 )
      goto LABEL_10;
    if ( !StringFromGUID2((const GUID *const)((char *)qword_18001F2C0 + 20 * v7 + 4), sz, 40) )
      break;
    v9 = XcAddChildElement(
           a1,
           v8,
           (OLECHAR *)L"PurposeGroupGuid",
           (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v4",
           sz,
           0);
    if ( v9 )
    {
      if ( v8 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
      return v9;
    }
LABEL_10:
    v7 = (unsigned int)(v7 + 1);
    if ( (unsigned int)v7 >= 0xB )
    {
      if ( v8 )
        ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
      return 0;
    }
  }
  if ( v8 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v8->lpVtbl->Release)(v8);
  return 1206;
}

```

## disassembly

```asm
0x180009f74  mov     [rsp+arg_10], rbx
0x180009f79  push    rbp
0x180009f7a  push    rsi
0x180009f7b  push    rdi
0x180009f7c  push    r12
0x180009f7e  push    r14
0x180009f80  sub     rsp, 0A0h
0x180009f87  mov     rax, cs:__security_cookie
0x180009f8e  xor     rax, rsp
0x180009f91  mov     [rsp+0C8h+var_38], rax
0x180009f99  mov     rbp, r8
0x180009f9c  mov     r14, rcx
0x180009f9f  cmp     dword ptr [r8+15A0h], 0
0x180009fa7  jz      loc_18000A08C
0x180009fad  mov     [rsp+0C8h+var_98], 0
0x180009fb6  lea     rax, [rsp+0C8h+var_98]
0x180009fbb  mov     [rsp+0C8h+var_A0], rax; struct IXMLDOMNode **
0x180009fc0  mov     [rsp+0C8h+var_A8], 0; OLECHAR *
0x180009fc9  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x180009fd0  lea     r8, aPurposegroups; "PurposeGroups"
0x180009fd7  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180009fdc  mov     ebx, eax
0x180009fde  test    eax, eax
0x180009fe0  jz      short loc_18000A000
0x180009fe2  mov     rcx, [rsp+0C8h+var_98]
0x180009fe7  test    rcx, rcx
0x180009fea  jz      short loc_180009FF9
0x180009fec  mov     rdx, [rcx]
0x180009fef  mov     rax, [rdx+10h]
0x180009ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ff8  nop
0x180009ff9  mov     eax, ebx
0x180009ffb  jmp     loc_18000A08E
0x18000a000  xor     edi, edi
0x18000a002  lea     r12, qword_18001F2C0
0x18000a009  mov     rbx, [rsp+0C8h+var_98]
0x18000a00e  lea     rcx, [rdi+rdi*4]
0x18000a012  mov     eax, [r12+rcx*4]
0x18000a016  test    [rbp+15A0h], eax
0x18000a01c  jz      short loc_18000A070
0x18000a01e  inc     rcx
0x18000a021  lea     rcx, [r12+rcx*4]; rguid
0x18000a025  mov     r8d, 28h ; '('; cchMax
0x18000a02b  lea     rdx, [rsp+0C8h+sz]; lpsz
0x18000a030  call    cs:__imp_StringFromGUID2
0x18000a036  test    eax, eax
0x18000a038  jz      loc_18000A0CE
0x18000a03e  mov     [rsp+0C8h+var_A0], 0; struct IXMLDOMNode **
0x18000a047  lea     rax, [rsp+0C8h+sz]
0x18000a04c  mov     [rsp+0C8h+var_A8], rax; OLECHAR *
0x18000a051  lea     r9, aHttpWwwMicroso_5; "http://www.microsoft.com/networking/WWA"...
0x18000a058  lea     r8, aPurposegroupgu; "PurposeGroupGuid"
0x18000a05f  mov     rdx, rbx; struct IXMLDOMNode *
0x18000a062  mov     rcx, r14; struct IXMLDOMDocument2 *
0x18000a065  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000a06a  mov     esi, eax
0x18000a06c  test    eax, eax
0x18000a06e  jnz     short loc_18000A0B5
0x18000a070  inc     edi
0x18000a072  cmp     edi, 0Bh
0x18000a075  jb      short loc_18000A00E
0x18000a077  test    rbx, rbx
0x18000a07a  jz      short loc_18000A08C
0x18000a07c  mov     rax, [rbx]
0x18000a07f  mov     rcx, rbx
0x18000a082  mov     rax, [rax+10h]
0x18000a086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a08b  nop
0x18000a08c  xor     eax, eax
0x18000a08e  mov     rcx, [rsp+0C8h+var_38]
0x18000a096  xor     rcx, rsp; StackCookie
0x18000a099  call    __security_check_cookie
0x18000a09e  mov     rbx, [rsp+0C8h+arg_10]
0x18000a0a6  add     rsp, 0A0h
0x18000a0ad  pop     r14
0x18000a0af  pop     r12
0x18000a0b1  pop     rdi
0x18000a0b2  pop     rsi
0x18000a0b3  pop     rbp
0x18000a0b4  retn
0x18000a0b5  test    rbx, rbx
0x18000a0b8  jz      short loc_18000A0CA
0x18000a0ba  mov     rax, [rbx]
0x18000a0bd  mov     rcx, rbx
0x18000a0c0  mov     rax, [rax+10h]
0x18000a0c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0c9  nop
0x18000a0ca  mov     eax, esi
0x18000a0cc  jmp     short loc_18000A08E
0x18000a0ce  test    rbx, rbx
0x18000a0d1  jz      short loc_18000A0E3
0x18000a0d3  mov     rax, [rbx]
0x18000a0d6  mov     rcx, rbx
0x18000a0d9  mov     rax, [rax+10h]
0x18000a0dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0e2  nop
0x18000a0e3  mov     eax, 4B6h
0x18000a0e8  jmp     short loc_18000A08E
```
