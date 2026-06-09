# JDictsDictionaryManifest::Initialize(ushort const *,int)

- ea: `0x180016a80`
- end: `0x180016bb6`
- name: `?Initialize@JDictsDictionaryManifest@@UEAAJPEBGH@Z`
- size: `310`
- prototype: `__int64 __fastcall(JDictsDictionaryManifest *this, char *, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180005ca4`
- `0x18000cef4`
- `0x1800163b8`
- `0x180016a80`
- `0x180016e68`
- `0x1800199a4`
- `0x18001aa50`
- `0x180024010`

## string_xrefs

- `0x180016aca`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\jdictsdictionarymanifest.cpp`

## pseudocode

```c
__int64 __fastcall JDictsDictionaryManifest::Initialize(JDictsDictionaryManifest *this, char *a2, int a3)
{
  struct IJDictsIndexer **v6; // r15
  __int64 v7; // rcx
  int Instance; // esi
  __int64 v9; // rdx
  __int64 result; // rax
  _QWORD *v11; // r14
  __int64 v12; // rcx
  unsigned __int64 v13; // r8
  unsigned __int64 v14; // r8
  __int64 last_of; // rax
  int v16; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v6 = (struct IJDictsIndexer **)((char *)this + 24);
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    *v6 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  Instance = JDictsIndexerSatori::CreateInstance(v6);
  if ( Instance < 0 )
  {
    v9 = 82;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\jdictsdictionarymanifest.cpp",
      (const char *)(unsigned int)Instance,
      v16);
    return (unsigned int)Instance;
  }
  v11 = (_QWORD *)((char *)this + 16);
  v12 = *((_QWORD *)this + 2);
  if ( v12 )
  {
    *v11 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  Instance = JDictsDataBlocksForGUID::CreateInstance((struct IJDictsDataBlocksForGUID **)this + 2);
  if ( Instance < 0 )
  {
    v9 = 83;
    goto LABEL_5;
  }
  result = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD, struct IJDictsIndexer *, int))(*(_QWORD *)*v11 + 24LL))(
             *v11,
             a2,
             0,
             *v6,
             a3);
  if ( (int)result >= 0 )
  {
    if ( *(_WORD *)a2 )
    {
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)&a2[2 * v13] );
    }
    else
    {
      v13 = 0;
    }
    std::wstring::assign((_QWORD *)this + 4, a2, v13);
    if ( *(_WORD *)a2 )
    {
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)&a2[2 * v14] );
    }
    else
    {
      v14 = 0;
    }
    std::wstring::assign((_QWORD *)this + 8, a2, v14);
    last_of = std::wstring::find_last_of((char *)this + 64);
    if ( last_of != -1 )
      std::wstring::resize((char *)this + 64, last_of + 1);
    *((_DWORD *)this + 2) = 1;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180016a80  push    rbx
0x180016a82  push    rbp
0x180016a83  push    rsi
0x180016a84  push    rdi
0x180016a85  push    r12
0x180016a87  push    r14
0x180016a89  push    r15
0x180016a8b  sub     rsp, 30h
0x180016a8f  mov     ebp, r8d
0x180016a92  mov     rbx, rdx
0x180016a95  mov     rdi, rcx
0x180016a98  lea     r15, [rcx+18h]
0x180016a9c  mov     rcx, [r15]
0x180016a9f  xor     r12d, r12d
0x180016aa2  test    rcx, rcx
0x180016aa5  jz      short loc_180016AB7
0x180016aa7  mov     [r15], r12
0x180016aaa  mov     rax, [rcx]
0x180016aad  mov     rax, [rax+10h]
0x180016ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ab6  nop
0x180016ab7  mov     rcx, r15; struct IJDictsIndexer **
0x180016aba  call    ?CreateInstance@JDictsIndexerSatori@@SAJPEAPEAUIJDictsIndexer@@@Z; JDictsIndexerSatori::CreateInstance(IJDictsIndexer * *)
0x180016abf  mov     esi, eax
0x180016ac1  test    eax, eax
0x180016ac3  jns     short loc_180016AE5
0x180016ac5  mov     edx, 52h ; 'R'; void *
0x180016aca  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180016ad1  mov     r9d, esi; char *
0x180016ad4  mov     rcx, [rsp+68h]; this
0x180016ad9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016ade  mov     eax, esi
0x180016ae0  jmp     loc_180016BA7
0x180016ae5  lea     r14, [rdi+10h]
0x180016ae9  mov     rcx, [r14]
0x180016aec  test    rcx, rcx
0x180016aef  jz      short loc_180016B01
0x180016af1  mov     [r14], r12
0x180016af4  mov     rax, [rcx]
0x180016af7  mov     rax, [rax+10h]
0x180016afb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b00  nop
0x180016b01  mov     rcx, r14; struct IJDictsDataBlocksForGUID **
0x180016b04  call    ?CreateInstance@JDictsDataBlocksForGUID@@SAJPEAPEAUIJDictsDataBlocksForGUID@@@Z; JDictsDataBlocksForGUID::CreateInstance(IJDictsDataBlocksForGUID * *)
0x180016b09  mov     esi, eax
0x180016b0b  test    eax, eax
0x180016b0d  jns     short loc_180016B16
0x180016b0f  mov     edx, 53h ; 'S'
0x180016b14  jmp     short loc_180016ACA
0x180016b16  mov     rcx, [r14]
0x180016b19  mov     rax, [rcx]
0x180016b1c  mov     [rsp+68h+var_48], ebp
0x180016b20  mov     r9, [r15]
0x180016b23  xor     r8d, r8d
0x180016b26  mov     rdx, rbx
0x180016b29  mov     rax, [rax+18h]
0x180016b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b32  test    eax, eax
0x180016b34  js      short loc_180016BA7
0x180016b36  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180016b3a  cmp     [rbx], r12w
0x180016b3e  jnz     short loc_180016B45
0x180016b40  mov     r8, r12
0x180016b43  jmp     short loc_180016B52
0x180016b45  mov     r8, rbp
0x180016b48  inc     r8
0x180016b4b  cmp     [rbx+r8*2], r12w
0x180016b50  jnz     short loc_180016B48
0x180016b52  lea     rcx, [rdi+20h]; void *
0x180016b56  mov     rdx, rbx; Src
0x180016b59  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180016b5e  cmp     [rbx], r12w
0x180016b62  jnz     short loc_180016B69
0x180016b64  mov     r8, r12
0x180016b67  jmp     short loc_180016B76
0x180016b69  mov     r8, rbp
0x180016b6c  inc     r8
0x180016b6f  cmp     [rbx+r8*2], r12w
0x180016b74  jnz     short loc_180016B6C
0x180016b76  lea     rsi, [rdi+40h]
0x180016b7a  mov     rdx, rbx; Src
0x180016b7d  mov     rcx, rsi; void *
0x180016b80  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180016b85  mov     rcx, rsi
0x180016b88  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_last_of(ushort,unsigned __int64)
0x180016b8d  cmp     rax, rbp
0x180016b90  jz      short loc_180016B9E
0x180016b92  lea     rdx, [rax+1]
0x180016b96  mov     rcx, rsi
0x180016b99  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::resize(unsigned __int64)
0x180016b9e  mov     dword ptr [rdi+8], 1
0x180016ba5  xor     eax, eax
0x180016ba7  add     rsp, 30h
0x180016bab  pop     r15
0x180016bad  pop     r14
0x180016baf  pop     r12
0x180016bb1  pop     rdi
0x180016bb2  pop     rsi
0x180016bb3  pop     rbp
0x180016bb4  pop     rbx
0x180016bb5  retn
```
