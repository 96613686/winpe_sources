# _parsePurposeGroupsNode

- ea: `0x18000c050`
- end: `0x18000c273`
- name: `_parsePurposeGroupsNode`
- size: `547`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, _DWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001670`
- `0x18000c050`
- `0x1800127d0`
- `0x180012bc8`
- `0x1800130e0`
- `0x1800136f4`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000c147`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18000c147`

## pseudocode

```c
__int64 __fastcall parsePurposeGroupsNode(struct IXMLDOMNode *a1, _DWORD *a2)
{
  unsigned int Nodes; // ebx
  int v5; // r14d
  int v6; // esi
  struct IXMLDOMNodeList *v7; // rbx
  __int64 v8; // rdi
  unsigned int NodeStringValue; // eax
  int v10; // eax
  struct IXMLDOMNode *v11; // [rsp+40h] [rbp-49h] BYREF
  struct IXMLDOMNodeList *v12; // [rsp+48h] [rbp-41h] BYREF
  GUID iid; // [rsp+50h] [rbp-39h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-29h] BYREF

  LODWORD(v11) = 0;
  v12 = 0;
  Nodes = XcGetNodes(a1, L"MBNProfileV4:PurposeGroupGuid", &v12, (int *)&v11);
  if ( Nodes )
  {
    if ( v12 )
      ((void (__fastcall *)(struct IXMLDOMNodeList *))v12->lpVtbl->Release)(v12);
    return Nodes;
  }
  else
  {
    v5 = (int)v11;
    if ( (unsigned int)((_DWORD)v11 - 1) > 9 )
    {
      if ( v12 )
        ((void (__fastcall *)(struct IXMLDOMNodeList *))v12->lpVtbl->Release)(v12);
      return 1206;
    }
    else
    {
      v6 = 0;
      v7 = v12;
      if ( (int)v11 <= 0 )
      {
LABEL_17:
        if ( v7 )
          ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
        return 0;
      }
      else
      {
        while ( 1 )
        {
          v11 = 0;
          LODWORD(v8) = XcGetItem(v7, v6, &v11);
          if ( (_DWORD)v8 )
            break;
          iid = 0;
          NodeStringValue = XcGetNodeStringValue(v11, 0, sz, 0x28u, 0, 0, 0);
          v8 = NodeStringValue;
          if ( NodeStringValue )
            goto LABEL_21;
          if ( IIDFromString(sz, &iid) )
          {
            LODWORD(v8) = 1206;
LABEL_21:
            if ( v11 )
              ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
            if ( v7 )
              ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
            return (unsigned int)v8;
          }
          while ( memcmp_0(&iid, (char *)qword_18001F2C0 + 20 * v8 + 4, 0x10u) )
          {
            v8 = (unsigned int)(v8 + 1);
            if ( (unsigned int)v8 >= 0xB )
            {
              v10 = 0;
              goto LABEL_14;
            }
          }
          v10 = *((_DWORD *)qword_18001F2C0 + 5 * v8);
LABEL_14:
          a2[1384] |= v10;
          if ( v11 )
            ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
          if ( ++v6 >= v5 )
            goto LABEL_17;
        }
        if ( v11 )
          ((void (__fastcall *)(struct IXMLDOMNode *))v11->lpVtbl->Release)(v11);
        if ( v7 )
          ((void (__fastcall *)(struct IXMLDOMNodeList *))v7->lpVtbl->Release)(v7);
        return (unsigned int)v8;
      }
    }
  }
}

```

## disassembly

```asm
0x18000c050  mov     [rsp-8+arg_10], rbx
0x18000c055  mov     [rsp-8+arg_18], rsi
0x18000c05a  push    rbp
0x18000c05b  push    rdi
0x18000c05c  push    r12
0x18000c05e  push    r14
0x18000c060  push    r15
0x18000c062  lea     rbp, [rsp-37h]
0x18000c067  sub     rsp, 0C0h
0x18000c06e  mov     rax, cs:__security_cookie
0x18000c075  xor     rax, rsp
0x18000c078  mov     [rbp+57h+var_30], rax
0x18000c07c  mov     r12, rdx
0x18000c07f  mov     dword ptr [rbp+57h+var_A0], 0
0x18000c086  mov     [rbp+57h+var_98], 0
0x18000c08e  lea     r9, [rbp+57h+var_A0]; int *
0x18000c092  lea     r8, [rbp+57h+var_98]; struct IXMLDOMNodeList **
0x18000c096  lea     rdx, aMbnprofilev4Pu; "MBNProfileV4:PurposeGroupGuid"
0x18000c09d  call    ?XcGetNodes@@YAKPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJ@Z; XcGetNodes(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *)
0x18000c0a2  mov     ebx, eax
0x18000c0a4  test    eax, eax
0x18000c0a6  jz      short loc_18000C0C5
0x18000c0a8  mov     rcx, [rbp+57h+var_98]
0x18000c0ac  test    rcx, rcx
0x18000c0af  jz      short loc_18000C0BE
0x18000c0b1  mov     rdx, [rcx]
0x18000c0b4  mov     rax, [rdx+10h]
0x18000c0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0bd  nop
0x18000c0be  mov     eax, ebx
0x18000c0c0  jmp     loc_18000C24B
0x18000c0c5  mov     r14d, dword ptr [rbp+57h+var_A0]
0x18000c0c9  lea     eax, [r14-1]
0x18000c0cd  cmp     eax, 9
0x18000c0d0  ja      loc_18000C230
0x18000c0d6  xor     esi, esi
0x18000c0d8  mov     rbx, [rbp+57h+var_98]
0x18000c0dc  test    r14d, r14d
0x18000c0df  jle     loc_18000C1B6
0x18000c0e5  mov     [rbp+57h+var_A0], 0
0x18000c0ed  lea     r8, [rbp+57h+var_A0]; struct IXMLDOMNode **
0x18000c0f1  mov     edx, esi; int
0x18000c0f3  mov     rcx, rbx; struct IXMLDOMNodeList *
0x18000c0f6  call    ?XcGetItem@@YAKPEAUIXMLDOMNodeList@@JPEAPEAUIXMLDOMNode@@@Z; XcGetItem(IXMLDOMNodeList *,long,IXMLDOMNode * *)
0x18000c0fb  mov     edi, eax
0x18000c0fd  test    eax, eax
0x18000c0ff  jnz     loc_18000C201
0x18000c105  xorps   xmm0, xmm0
0x18000c108  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x18000c10c  mov     [rsp+0E0h+var_B0], 0; int *
0x18000c115  mov     [rsp+0E0h+var_B8], 0; unsigned __int16 *
0x18000c11e  mov     [rsp+0E0h+var_C0], eax; int
0x18000c122  lea     r9d, [rax+28h]; unsigned __int64
0x18000c126  lea     r8, [rbp+57h+sz]; unsigned __int16 *
0x18000c12a  xor     edx, edx; unsigned __int16 *
0x18000c12c  mov     rcx, [rbp+57h+var_A0]; struct IXMLDOMNode *
0x18000c130  call    ?XcGetNodeStringValue@@YAKPEAUIXMLDOMNode@@PEBGPEAG_KH1PEAH@Z; XcGetNodeStringValue(IXMLDOMNode *,ushort const *,ushort *,unsigned __int64,int,ushort const *,int *)
0x18000c135  mov     edi, eax
0x18000c137  test    eax, eax
0x18000c139  jnz     loc_18000C1D4
0x18000c13f  lea     rdx, [rbp+57h+iid]; lpiid
0x18000c143  lea     rcx, [rbp+57h+sz]; lpsz
0x18000c147  call    cs:__imp_IIDFromString
0x18000c14d  test    eax, eax
0x18000c14f  jnz     short loc_18000C1CF
0x18000c151  lea     r15, [rdi+rdi*4]
0x18000c155  lea     rdx, qword_18001F2C0
0x18000c15c  lea     rdx, [rdx+4]
0x18000c160  lea     rdx, [rdx+r15*4]; Buf2
0x18000c164  mov     r8d, 10h; Size
0x18000c16a  lea     rcx, [rbp+57h+iid]; Buf1
0x18000c16e  call    memcmp_0
0x18000c173  test    eax, eax
0x18000c175  jz      short loc_18000C182
0x18000c177  inc     edi
0x18000c179  cmp     edi, 0Bh
0x18000c17c  jb      short loc_18000C151
0x18000c17e  xor     eax, eax
0x18000c180  jmp     short loc_18000C18D
0x18000c182  lea     rax, qword_18001F2C0
0x18000c189  mov     eax, [rax+r15*4]
0x18000c18d  or      [r12+15A0h], eax
0x18000c195  mov     rcx, [rbp+57h+var_A0]
0x18000c199  test    rcx, rcx
0x18000c19c  jz      short loc_18000C1AB
0x18000c19e  mov     rax, [rcx]
0x18000c1a1  mov     rax, [rax+10h]
0x18000c1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1aa  nop
0x18000c1ab  inc     esi
0x18000c1ad  cmp     esi, r14d
0x18000c1b0  jl      loc_18000C0E5
0x18000c1b6  test    rbx, rbx
0x18000c1b9  jz      short loc_18000C1CB
0x18000c1bb  mov     rax, [rbx]
0x18000c1be  mov     rcx, rbx
0x18000c1c1  mov     rax, [rax+10h]
0x18000c1c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1ca  nop
0x18000c1cb  xor     eax, eax
0x18000c1cd  jmp     short loc_18000C24B
0x18000c1cf  mov     edi, 4B6h
0x18000c1d4  mov     rcx, [rbp+57h+var_A0]
0x18000c1d8  test    rcx, rcx
0x18000c1db  jz      short loc_18000C1EA
0x18000c1dd  mov     rax, [rcx]
0x18000c1e0  mov     rax, [rax+10h]
0x18000c1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1e9  nop
0x18000c1ea  test    rbx, rbx
0x18000c1ed  jz      short loc_18000C1FF
0x18000c1ef  mov     rcx, [rbx]
0x18000c1f2  mov     rax, [rcx+10h]
0x18000c1f6  mov     rcx, rbx
0x18000c1f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1fe  nop
0x18000c1ff  jmp     short loc_18000C22C
0x18000c201  mov     rcx, [rbp+57h+var_A0]
0x18000c205  test    rcx, rcx
0x18000c208  jz      short loc_18000C217
0x18000c20a  mov     rax, [rcx]
0x18000c20d  mov     rax, [rax+10h]
0x18000c211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c216  nop
0x18000c217  test    rbx, rbx
0x18000c21a  jz      short loc_18000C22C
0x18000c21c  mov     rax, [rbx]
0x18000c21f  mov     rcx, rbx
0x18000c222  mov     rax, [rax+10h]
0x18000c226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c22b  nop
0x18000c22c  mov     eax, edi
0x18000c22e  jmp     short loc_18000C24B
0x18000c230  mov     rcx, [rbp+57h+var_98]
0x18000c234  test    rcx, rcx
0x18000c237  jz      short loc_18000C246
0x18000c239  mov     rax, [rcx]
0x18000c23c  mov     rax, [rax+10h]
0x18000c240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c245  nop
0x18000c246  mov     eax, 4B6h
0x18000c24b  mov     rcx, [rbp+57h+var_30]
0x18000c24f  xor     rcx, rsp; StackCookie
0x18000c252  call    __security_check_cookie
0x18000c257  lea     r11, [rsp+0E0h+var_20]
0x18000c25f  mov     rbx, [r11+40h]
0x18000c263  mov     rsi, [r11+48h]
0x18000c267  mov     rsp, r11
0x18000c26a  pop     r15
0x18000c26c  pop     r14
0x18000c26e  pop     r12
0x18000c270  pop     rdi
0x18000c271  pop     rbp
0x18000c272  retn
```
