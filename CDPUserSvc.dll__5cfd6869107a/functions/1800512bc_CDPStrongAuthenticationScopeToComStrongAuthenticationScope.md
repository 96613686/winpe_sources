# CDPStrongAuthenticationScopeToComStrongAuthenticationScope

- ea: `0x1800512bc`
- end: `0x180051359`
- name: `CDPStrongAuthenticationScopeToComStrongAuthenticationScope`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180051490`

## callees

- `0x180002a4c`
- `0x18001e798`
- `0x1800512bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180051345`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180051345`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005132e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005132e`

## string_xrefs

- `0x1800512dc`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
__int64 __fastcall CDPStrongAuthenticationScopeToComStrongAuthenticationScope(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v6; // rax
  const char *v7; // rdi
  __int64 v8; // rcx
  rsize_t v9; // rbp
  char *v10; // rax
  char *v11; // rsi
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a1 )
  {
    v3 = -2147024809;
    v4 = 1041;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)v3,
      v12);
    return v3;
  }
  if ( !a2 )
  {
    v3 = -2147467261;
    v4 = 1042;
    goto LABEL_3;
  }
  *(_DWORD *)(a2 + 8) = *(_DWORD *)(a1 + 32);
  v6 = std::_String_val<std::_Simple_types<char>>::_Myptr(a1);
  *(_QWORD *)a2 = 0;
  v7 = (const char *)v6;
  if ( v6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_BYTE *)(v6 + v8) );
    v9 = v8 + 1;
    v10 = (char *)CoTaskMemAlloc(v8 + 1);
    v11 = v10;
    if ( v10 )
    {
      strcpy_s(v10, v9, v7);
      *(_QWORD *)a2 = v11;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800512bc  push    rbx
0x1800512be  push    rbp
0x1800512bf  push    rsi
0x1800512c0  push    rdi
0x1800512c1  sub     rsp, 28h
0x1800512c5  mov     rbx, rdx
0x1800512c8  test    rcx, rcx
0x1800512cb  jnz     short loc_1800512EF
0x1800512cd  mov     ebx, 80070057h
0x1800512d2  mov     edx, 411h; void *
0x1800512d7  mov     rcx, [rsp+48h]; this
0x1800512dc  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800512e3  mov     r9d, ebx; char *
0x1800512e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800512eb  mov     eax, ebx
0x1800512ed  jmp     short loc_180051350
0x1800512ef  test    rbx, rbx
0x1800512f2  jnz     short loc_180051300
0x1800512f4  mov     ebx, 80004003h
0x1800512f9  mov     edx, 412h
0x1800512fe  jmp     short loc_1800512D7
0x180051300  mov     eax, [rcx+20h]
0x180051303  mov     [rdx+8], eax
0x180051306  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18005130b  mov     qword ptr [rbx], 0
0x180051312  mov     rdi, rax
0x180051315  test    rax, rax
0x180051318  jz      short loc_18005134E
0x18005131a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005131e  inc     rcx
0x180051321  cmp     byte ptr [rax+rcx], 0
0x180051325  jnz     short loc_18005131E
0x180051327  lea     rbp, [rcx+1]
0x18005132b  mov     rcx, rbp; cb
0x18005132e  call    cs:__imp_CoTaskMemAlloc
0x180051334  mov     rsi, rax
0x180051337  test    rax, rax
0x18005133a  jz      short loc_18005134E
0x18005133c  mov     r8, rdi; Source
0x18005133f  mov     rdx, rbp; SizeInBytes
0x180051342  mov     rcx, rax; Destination
0x180051345  call    cs:__imp_strcpy_s
0x18005134b  mov     [rbx], rsi
0x18005134e  xor     eax, eax
0x180051350  add     rsp, 28h
0x180051354  pop     rdi
0x180051355  pop     rsi
0x180051356  pop     rbp
0x180051357  pop     rbx
0x180051358  retn
```
