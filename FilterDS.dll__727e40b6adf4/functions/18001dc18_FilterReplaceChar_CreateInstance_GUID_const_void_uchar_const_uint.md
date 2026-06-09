# FilterReplaceChar::CreateInstance(_GUID const &,void * *,uchar const *,uint)

- ea: `0x18001dc18`
- end: `0x18001dd52`
- name: `?CreateInstance@FilterReplaceChar@@SAJAEBU_GUID@@PEAPEAXPEBEI@Z`
- size: `314`
- prototype: `__int64 __fastcall(const struct _GUID *, void **, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180017840`

## callees

- `0x180001a30`
- `0x180005ca4`
- `0x18001b410`
- `0x18001dc18`
- `0x180021816`
- `0x180024010`

## string_xrefs

- `0x18001dcea`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\filterreplacechar.cpp`

## pseudocode

```c
__int64 __fastcall FilterReplaceChar::CreateInstance(
        const struct _GUID *a1,
        void **a2,
        const unsigned __int8 *a3,
        unsigned int a4)
{
  int v7; // eax
  const char *v8; // r9
  unsigned int v9; // edi
  FilterChar *v10; // rbx
  int v11; // eax
  unsigned int v12; // edi
  __int64 result; // rax
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a2 = 0;
  v7 = memcmp_0(&GUID_5b67a2c6_4097_4004_9db9_0c604f924636, &GUID_5b67a2c6_4097_4004_9db9_0c604f924636, 0x10u);
  try
  {
    if ( v7 && memcmp_0(&GUID_5b67a2c6_4097_4004_9db9_0c604f924636, &GUID_5885afb0_480a_4c73_b602_76f2f1e03001, 0x10u) )
      return (unsigned int)-2147467262;
    v10 = (FilterChar *)operator new(0x28u);
    if ( v10 )
    {
      *(_QWORD *)v10 = &FilterReplaceChar::`vftable';
      *((_QWORD *)v10 + 1) = 0;
      *((_QWORD *)v10 + 2) = 0;
      *((_QWORD *)v10 + 3) = 0;
      *((_DWORD *)v10 + 8) = 0;
      (*(void (__fastcall **)(FilterChar *))(*(_QWORD *)v10 + 8LL))(v10);
    }
    v11 = FilterChar::init(v10, a3, a4);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v9 = (**(__int64 (__fastcall ***)(FilterChar *, GUID *, void **))v10)(
             v10,
             &GUID_5b67a2c6_4097_4004_9db9_0c604f924636,
             a2);
      (*(void (__fastcall **)(FilterChar *))(*(_QWORD *)v10 + 16LL))(v10);
      return v9;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\filterreplacechar.cpp",
      (const char *)(unsigned int)v11,
      v14);
    if ( v10 )
      (*(void (__fastcall **)(FilterChar *))(*(_QWORD *)v10 + 16LL))(v10);
    result = v12;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x45,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\fil"
                                         "terreplacechar.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x18001dc18  mov     [rsp+arg_0], rcx
0x18001dc1d  push    rbx
0x18001dc1e  push    rsi
0x18001dc1f  push    rdi
0x18001dc20  push    r14
0x18001dc22  sub     rsp, 28h
0x18001dc26  mov     edi, r9d
0x18001dc29  mov     r14, r8
0x18001dc2c  mov     rsi, rdx
0x18001dc2f  mov     qword ptr [rdx], 0
0x18001dc36  mov     ebx, 10h
0x18001dc3b  mov     r8d, ebx; Size
0x18001dc3e  lea     rdx, _GUID_5b67a2c6_4097_4004_9db9_0c604f924636; Buf2
0x18001dc45  lea     rcx, _GUID_5b67a2c6_4097_4004_9db9_0c604f924636; Buf1
0x18001dc4c  call    memcmp_0
0x18001dc51  test    eax, eax
0x18001dc53  jz      short loc_18001DC79
0x18001dc55  mov     r8d, ebx; Size
0x18001dc58  lea     rdx, _GUID_5885afb0_480a_4c73_b602_76f2f1e03001; Buf2
0x18001dc5f  lea     rcx, _GUID_5b67a2c6_4097_4004_9db9_0c604f924636; Buf1
0x18001dc66  call    memcmp_0
0x18001dc6b  test    eax, eax
0x18001dc6d  jz      short loc_18001DC79
0x18001dc6f  mov     edi, 80004002h
0x18001dc74  jmp     loc_18001DD3F
0x18001dc79  mov     ecx, 28h ; '('; Size
0x18001dc7e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dc83  mov     rbx, rax
0x18001dc86  test    rbx, rbx
0x18001dc89  jz      short loc_18001DCB4
0x18001dc8b  lea     rax, ??_7FilterReplaceChar@@6B@; const FilterReplaceChar::`vftable'
0x18001dc92  mov     [rbx], rax
0x18001dc95  mov     qword ptr [rbx+8], 0
0x18001dc9d  mov     qword ptr [rbx+10h], 0
0x18001dca5  mov     qword ptr [rbx+18h], 0
0x18001dcad  mov     dword ptr [rbx+20h], 0
0x18001dcb4  mov     [rsp+48h+arg_0], rbx
0x18001dcb9  test    rbx, rbx
0x18001dcbc  jz      short loc_18001DCCE
0x18001dcbe  mov     rax, [rbx]
0x18001dcc1  mov     rcx, rbx
0x18001dcc4  mov     rax, [rax+8]
0x18001dcc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dccd  nop
0x18001dcce  mov     r8d, edi; unsigned int
0x18001dcd1  mov     rdx, r14; unsigned __int8 *
0x18001dcd4  mov     rcx, rbx; this
0x18001dcd7  call    ?init@FilterChar@@IEAAJPEBEI@Z; FilterChar::init(uchar const *,uint)
0x18001dcdc  mov     edi, eax
0x18001dcde  test    eax, eax
0x18001dce0  jns     short loc_18001DD15
0x18001dce2  mov     rcx, [rsp+48h]; this
0x18001dce7  mov     r9d, eax; char *
0x18001dcea  lea     r8, aMincoreTextinp_23; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x18001dcf1  mov     edx, 3Ch ; '<'; void *
0x18001dcf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dcfb  nop
0x18001dcfc  test    rbx, rbx
0x18001dcff  jz      short loc_18001DD11
0x18001dd01  mov     rax, [rbx]
0x18001dd04  mov     rcx, rbx
0x18001dd07  mov     rax, [rax+10h]
0x18001dd0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd10  nop
0x18001dd11  mov     eax, edi
0x18001dd13  jmp     short loc_18001DD47
0x18001dd15  mov     rax, [rbx]
0x18001dd18  mov     r8, rsi
0x18001dd1b  lea     rdx, _GUID_5b67a2c6_4097_4004_9db9_0c604f924636
0x18001dd22  mov     rcx, rbx
0x18001dd25  mov     rax, [rax]
0x18001dd28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd2d  mov     edi, eax
0x18001dd2f  mov     rcx, [rbx]
0x18001dd32  mov     rax, [rcx+10h]
0x18001dd36  mov     rcx, rbx
0x18001dd39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd3e  nop
0x18001dd3f  mov     eax, edi
0x18001dd41  jmp     short loc_18001DD47
0x18001dd43  mov     eax, dword ptr [rsp+48h+arg_0]
0x18001dd47  add     rsp, 28h
0x18001dd4b  pop     r14
0x18001dd4d  pop     rdi
0x18001dd4e  pop     rsi
0x18001dd4f  pop     rbx
0x18001dd50  retn
```
