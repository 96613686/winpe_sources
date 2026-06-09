# _generateodemDMProfilePurposesNode

- ea: `0x18000f05c`
- end: `0x18000f1d2`
- name: `_generateodemDMProfilePurposesNode`
- size: `374`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *, struct IXMLDOMNode *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ec80`

## callees

- `0x180001670`
- `0x18000f05c`
- `0x180011f90`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f118`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f118`

## string_xrefs

- `0x18000f0b1`: `http://www.microsoft.com/networking/WWAN/profile/v7`
- `0x18000f139`: `http://www.microsoft.com/networking/WWAN/profile/v7`

## pseudocode

```c
__int64 __fastcall generateodemDMProfilePurposesNode(struct IXMLDOMDocument2 *a1, struct IXMLDOMNode *a2, __int64 a3)
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
         (OLECHAR *)L"ModemDMProfilePurposes",
         (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v7",
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
    if ( (*((_DWORD *)qword_18001F480 + 5 * v7) & *(_DWORD *)(a3 + 5536)) == 0 )
      goto LABEL_10;
    if ( !StringFromGUID2((const GUID *const)((char *)qword_18001F480 + 20 * v7 + 4), sz, 40) )
      break;
    v9 = XcAddChildElement(
           a1,
           v8,
           (OLECHAR *)L"DMProfilePurposeGuid",
           (OLECHAR *)L"http://www.microsoft.com/networking/WWAN/profile/v7",
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
0x18000f05c  mov     [rsp+arg_10], rbx
0x18000f061  push    rbp
0x18000f062  push    rsi
0x18000f063  push    rdi
0x18000f064  push    r12
0x18000f066  push    r14
0x18000f068  sub     rsp, 0A0h
0x18000f06f  mov     rax, cs:__security_cookie
0x18000f076  xor     rax, rsp
0x18000f079  mov     [rsp+0C8h+var_38], rax
0x18000f081  mov     rbp, r8
0x18000f084  mov     r14, rcx
0x18000f087  cmp     dword ptr [r8+15A0h], 0
0x18000f08f  jz      loc_18000F174
0x18000f095  mov     [rsp+0C8h+var_98], 0
0x18000f09e  lea     rax, [rsp+0C8h+var_98]
0x18000f0a3  mov     [rsp+0C8h+var_A0], rax; struct IXMLDOMNode **
0x18000f0a8  mov     [rsp+0C8h+var_A8], 0; OLECHAR *
0x18000f0b1  lea     r9, aHttpWwwMicroso_4; "http://www.microsoft.com/networking/WWA"...
0x18000f0b8  lea     r8, aModemdmprofile; "ModemDMProfilePurposes"
0x18000f0bf  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000f0c4  mov     ebx, eax
0x18000f0c6  test    eax, eax
0x18000f0c8  jz      short loc_18000F0E8
0x18000f0ca  mov     rcx, [rsp+0C8h+var_98]
0x18000f0cf  test    rcx, rcx
0x18000f0d2  jz      short loc_18000F0E1
0x18000f0d4  mov     rdx, [rcx]
0x18000f0d7  mov     rax, [rdx+10h]
0x18000f0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0e0  nop
0x18000f0e1  mov     eax, ebx
0x18000f0e3  jmp     loc_18000F176
0x18000f0e8  xor     edi, edi
0x18000f0ea  lea     r12, qword_18001F480
0x18000f0f1  mov     rbx, [rsp+0C8h+var_98]
0x18000f0f6  lea     rcx, [rdi+rdi*4]
0x18000f0fa  mov     eax, [r12+rcx*4]
0x18000f0fe  test    [rbp+15A0h], eax
0x18000f104  jz      short loc_18000F158
0x18000f106  inc     rcx
0x18000f109  lea     rcx, [r12+rcx*4]; rguid
0x18000f10d  mov     r8d, 28h ; '('; cchMax
0x18000f113  lea     rdx, [rsp+0C8h+sz]; lpsz
0x18000f118  call    cs:__imp_StringFromGUID2
0x18000f11e  test    eax, eax
0x18000f120  jz      loc_18000F1B6
0x18000f126  mov     [rsp+0C8h+var_A0], 0; struct IXMLDOMNode **
0x18000f12f  lea     rax, [rsp+0C8h+sz]
0x18000f134  mov     [rsp+0C8h+var_A8], rax; OLECHAR *
0x18000f139  lea     r9, aHttpWwwMicroso_4; "http://www.microsoft.com/networking/WWA"...
0x18000f140  lea     r8, aDmprofilepurpo; "DMProfilePurposeGuid"
0x18000f147  mov     rdx, rbx; struct IXMLDOMNode *
0x18000f14a  mov     rcx, r14; struct IXMLDOMDocument2 *
0x18000f14d  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18000f152  mov     esi, eax
0x18000f154  test    eax, eax
0x18000f156  jnz     short loc_18000F19D
0x18000f158  inc     edi
0x18000f15a  cmp     edi, 0Bh
0x18000f15d  jb      short loc_18000F0F6
0x18000f15f  test    rbx, rbx
0x18000f162  jz      short loc_18000F174
0x18000f164  mov     rax, [rbx]
0x18000f167  mov     rcx, rbx
0x18000f16a  mov     rax, [rax+10h]
0x18000f16e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f173  nop
0x18000f174  xor     eax, eax
0x18000f176  mov     rcx, [rsp+0C8h+var_38]
0x18000f17e  xor     rcx, rsp; StackCookie
0x18000f181  call    __security_check_cookie
0x18000f186  mov     rbx, [rsp+0C8h+arg_10]
0x18000f18e  add     rsp, 0A0h
0x18000f195  pop     r14
0x18000f197  pop     r12
0x18000f199  pop     rdi
0x18000f19a  pop     rsi
0x18000f19b  pop     rbp
0x18000f19c  retn
0x18000f19d  test    rbx, rbx
0x18000f1a0  jz      short loc_18000F1B2
0x18000f1a2  mov     rax, [rbx]
0x18000f1a5  mov     rcx, rbx
0x18000f1a8  mov     rax, [rax+10h]
0x18000f1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1b1  nop
0x18000f1b2  mov     eax, esi
0x18000f1b4  jmp     short loc_18000F176
0x18000f1b6  test    rbx, rbx
0x18000f1b9  jz      short loc_18000F1CB
0x18000f1bb  mov     rax, [rbx]
0x18000f1be  mov     rcx, rbx
0x18000f1c1  mov     rax, [rax+10h]
0x18000f1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1ca  nop
0x18000f1cb  mov     eax, 4B6h
0x18000f1d0  jmp     short loc_18000F176
```
