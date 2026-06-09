# StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonics(IMnemonics *,int *,int *,KEYWORD_PREPARATION_OPTIONS,StructuredQuery1::IIndicatorAccumulator *)

- ea: `0x18001c5b4`
- end: `0x18001c6c6`
- name: `?ProcessMnemonics@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEAUIMnemonics@@PEAH1W4KEYWORD_PREPARATION_OPTIONS@@PEAUIIndicatorAccumulator@2@@Z`
- size: `274`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013cbc`
- `0x180019d20`
- `0x18001c8c4`
- `0x180050efc`

## callees

- `0x18001c5b4`
- `0x18001e110`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001c66e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001c66e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c6aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c6aa`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonics(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        int *a4,
        unsigned int a5,
        __int64 a6)
{
  __int64 v6; // rax
  int v9; // ebp
  unsigned int v12; // edi
  int v13; // ebx
  __int64 v15; // r15
  __int64 v16; // rax
  int v17; // eax
  WCHAR *v18; // rcx
  int v19; // eax
  PCNZWCH lpString1; // [rsp+88h] [rbp+10h] BYREF

  v6 = *a2;
  v9 = 0;
  a5 = 0;
  v12 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v6 + 24))(a2, &a5);
  if ( v13 >= 0 )
  {
    v15 = a6;
    do
    {
      if ( v12 >= a5 )
        break;
      v16 = *a2;
      lpString1 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, PCNZWCH *))(v16 + 32))(a2, v12, &lpString1);
      if ( v13 >= 0 )
      {
        v17 = CompareStringW(0x7Fu, 1u, lpString1, -1, L"#NOLABEL", -1);
        v18 = (WCHAR *)lpString1;
        if ( v17 == 2 )
        {
          v9 = 1;
        }
        else if ( *lpString1 != 35 )
        {
          v19 = StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(a1, lpString1, a3, 1, v15);
          v18 = (WCHAR *)lpString1;
          v13 = v19;
        }
        CoTaskMemFree(v18);
      }
      ++v12;
    }
    while ( v13 >= 0 );
  }
  if ( a4 )
    *a4 = v9;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001c5b4  mov     r11, rsp
0x18001c5b7  push    rbx
0x18001c5b8  push    rbp
0x18001c5b9  push    rsi
0x18001c5ba  push    rdi
0x18001c5bb  push    r12
0x18001c5bd  push    r13
0x18001c5bf  push    r14
0x18001c5c1  push    r15
0x18001c5c3  sub     rsp, 38h
0x18001c5c7  mov     rax, [rdx]
0x18001c5ca  mov     r14, rdx
0x18001c5cd  mov     r13, rcx
0x18001c5d0  lea     rdx, [r11+28h]
0x18001c5d4  xor     ebp, ebp
0x18001c5d6  mov     rcx, r14
0x18001c5d9  mov     rsi, r9
0x18001c5dc  mov     [r11+28h], ebp
0x18001c5e0  mov     rax, [rax+18h]
0x18001c5e4  mov     r12, r8
0x18001c5e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5ec  xor     edi, edi
0x18001c5ee  mov     ebx, eax
0x18001c5f0  test    eax, eax
0x18001c5f2  jns     short loc_18001C60E
0x18001c5f4  test    rsi, rsi
0x18001c5f7  jz      short loc_18001C5FB
0x18001c5f9  mov     [rsi], ebp
0x18001c5fb  mov     eax, ebx
0x18001c5fd  add     rsp, 38h
0x18001c601  pop     r15
0x18001c603  pop     r14
0x18001c605  pop     r13
0x18001c607  pop     r12
0x18001c609  pop     rdi
0x18001c60a  pop     rsi
0x18001c60b  pop     rbp
0x18001c60c  pop     rbx
0x18001c60d  retn
0x18001c60e  mov     r15, [rsp+78h+arg_28]
0x18001c616  cmp     edi, [rsp+78h+arg_20]
0x18001c61d  jnb     short loc_18001C5F4
0x18001c61f  mov     rax, [r14]
0x18001c622  lea     r8, [rsp+78h+lpString1]
0x18001c62a  mov     edx, edi
0x18001c62c  mov     [rsp+78h+lpString1], 0
0x18001c638  mov     rcx, r14
0x18001c63b  mov     rax, [rax+20h]
0x18001c63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c644  mov     ebx, eax
0x18001c646  test    eax, eax
0x18001c648  js      short loc_18001C6B0
0x18001c64a  mov     r8, [rsp+78h+lpString1]; lpString1
0x18001c652  lea     rax, aNolabel; "#NOLABEL"
0x18001c659  or      ecx, 0FFFFFFFFh
0x18001c65c  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x18001c660  mov     r9d, ecx; cchCount1
0x18001c663  mov     [rsp+78h+lpString2], rax; lpString2
0x18001c668  lea     edx, [rcx+2]; dwCmpFlags
0x18001c66b  lea     ecx, [rdx+7Eh]; Locale
0x18001c66e  call    cs:__imp_CompareStringW
0x18001c674  mov     rcx, [rsp+78h+lpString1]
0x18001c67c  cmp     eax, 2
0x18001c67f  jz      short loc_18001C6BF
0x18001c681  cmp     word ptr [rcx], 23h ; '#'
0x18001c685  jz      short loc_18001C6AA
0x18001c687  mov     rdx, rcx
0x18001c68a  mov     [rsp+78h+lpString2], r15
0x18001c68f  mov     rcx, r13
0x18001c692  mov     r9d, 1
0x18001c698  mov     r8, r12
0x18001c69b  call    ?ProcessMnemonic@CSchemaFromPropertySystem@StructuredQuery1@@AEAAJPEB_WPEAHW4KEYWORD_PREPARATION_OPTIONS@@PEAUIIndicatorAccumulator@2@@Z; StructuredQuery1::CSchemaFromPropertySystem::ProcessMnemonic(wchar_t const *,int *,KEYWORD_PREPARATION_OPTIONS,StructuredQuery1::IIndicatorAccumulator *)
0x18001c6a0  mov     rcx, [rsp+78h+lpString1]; pv
0x18001c6a8  mov     ebx, eax
0x18001c6aa  call    cs:__imp_CoTaskMemFree
0x18001c6b0  inc     edi
0x18001c6b2  test    ebx, ebx
0x18001c6b4  jns     loc_18001C616
0x18001c6ba  jmp     loc_18001C5F4
0x18001c6bf  mov     ebp, 1
0x18001c6c4  jmp     short loc_18001C6AA
```
