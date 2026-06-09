# PathCombine(ushort const *,ushort const *,ushort * *)

- ea: `0x18001b5a0`
- end: `0x18001b6aa`
- name: `?PathCombine@@YAKPEBG0PEAPEAG@Z`
- size: `266`
- prototype: `__int64 __fastcall(wchar_t *Source, wchar_t *, unsigned __int16 **)`
- caller_count: `11`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000d760`
- `0x18000f0d8`
- `0x180011a94`
- `0x18001ab50`
- `0x1800398d0`
- `0x180039ea8`
- `0x18003b920`
- `0x18003cc10`
- `0x1800402b0`
- `0x1800404f0`
- `0x180040cc0`

## callees

- `0x18001b5a0`
- `0x18003aef8`
- `0x18003b7b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b611`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b611`

## pseudocode

```c
__int64 __fastcall PathCombine(wchar_t *Source, wchar_t *a2, unsigned __int16 **a3)
{
  __int64 v3; // rdi
  __int64 v5; // rbx
  unsigned int v9; // eax
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // r14
  wchar_t *v13; // r14

  v3 = -1;
  v5 = -1;
  do
    ++v5;
  while ( Source[v5] );
  while ( a2[++v3] != 0 )
    ;
  v9 = v3 + v5;
  if ( (int)v3 + (int)v5 < (unsigned int)v5 || v9 + 2 < v9 )
    return 534;
  v11 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (v9 + 2));
  v12 = v11;
  if ( v11 )
  {
    *a3 = v11;
    wcscpy_s(v11, (unsigned int)(v5 + 1), Source);
    v13 = &v12[(unsigned int)v5];
    if ( (_DWORD)v5 )
    {
      if ( Source[(unsigned int)(v5 - 1)] != 92 )
        wcscpy_s(v13++, 2u, L"\\");
    }
    wcscpy_s(v13, (unsigned int)(v3 + 1), a2);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_13ef719d6c39382471689e3834fa0ad3_Traceguids);
    return 14;
  }
}

```

## disassembly

```asm
0x18001b5a0  mov     [rsp+arg_8], rbx
0x18001b5a5  mov     [rsp+arg_10], rbp
0x18001b5aa  push    rsi
0x18001b5ab  push    rdi
0x18001b5ac  push    r15
0x18001b5ae  sub     rsp, 20h
0x18001b5b2  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001b5b9  mov     r15, r8
0x18001b5bc  mov     rbx, rdi
0x18001b5bf  mov     rsi, rdx
0x18001b5c2  mov     rbp, rcx
0x18001b5c5  inc     rbx
0x18001b5c8  cmp     word ptr [rcx+rbx*2], 0
0x18001b5cd  jnz     short loc_18001B5C5
0x18001b5cf  nop
0x18001b5d0  cmp     word ptr [rdx+rdi*2+2], 0
0x18001b5d6  lea     rdi, [rdi+1]
0x18001b5da  jnz     short loc_18001B5D0
0x18001b5dc  lea     eax, [rdi+rbx]
0x18001b5df  cmp     eax, ebx
0x18001b5e1  jnb     short loc_18001B5FB
0x18001b5e3  mov     eax, 216h
0x18001b5e8  mov     rbx, [rsp+38h+arg_8]
0x18001b5ed  mov     rbp, [rsp+38h+arg_10]
0x18001b5f2  add     rsp, 20h
0x18001b5f6  pop     r15
0x18001b5f8  pop     rdi
0x18001b5f9  pop     rsi
0x18001b5fa  retn
0x18001b5fb  lea     ecx, [rax+2]
0x18001b5fe  cmp     ecx, eax
0x18001b600  jb      short loc_18001B5E3
0x18001b602  mov     edx, ecx
0x18001b604  mov     ecx, 40h ; '@'; uFlags
0x18001b609  add     rdx, rdx; uBytes
0x18001b60c  mov     [rsp+38h+arg_0], r14
0x18001b611  call    cs:__imp_LocalAlloc
0x18001b617  mov     r14, rax
0x18001b61a  test    rax, rax
0x18001b61d  jz      short loc_18001B675
0x18001b61f  lea     edx, [rbx+1]; SizeInWords
0x18001b622  mov     [r15], rax
0x18001b625  mov     r8, rbp; Source
0x18001b628  mov     rcx, rax; Destination
0x18001b62b  call    wcscpy_s
0x18001b630  mov     eax, ebx
0x18001b632  lea     r14, [r14+rax*2]
0x18001b636  test    ebx, ebx
0x18001b638  jnz     short loc_18001B651
0x18001b63a  lea     edx, [rdi+1]; SizeInWords
0x18001b63d  mov     r8, rsi; Source
0x18001b640  mov     rcx, r14; Destination
0x18001b643  call    wcscpy_s
0x18001b648  xor     eax, eax
0x18001b64a  mov     r14, [rsp+38h+arg_0]
0x18001b64f  jmp     short loc_18001B5E8
0x18001b651  dec     ebx
0x18001b653  cmp     word ptr [rbp+rbx*2+0], 5Ch ; '\'
0x18001b659  jz      short loc_18001B63A
0x18001b65b  lea     r8, Source; "\\"
0x18001b662  mov     edx, 2; SizeInWords
0x18001b667  mov     rcx, r14; Destination
0x18001b66a  call    wcscpy_s
0x18001b66f  add     r14, 2
0x18001b673  jmp     short loc_18001B63A
0x18001b675  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b67c  lea     rax, WPP_GLOBAL_Control
0x18001b683  cmp     rcx, rax
0x18001b686  jz      short loc_18001B6A3
0x18001b688  test    byte ptr [rcx+1Ch], 2
0x18001b68c  jz      short loc_18001B6A3
0x18001b68e  mov     rcx, [rcx+10h]
0x18001b692  lea     r8, WPP_13ef719d6c39382471689e3834fa0ad3_Traceguids
0x18001b699  mov     edx, 0Ah
0x18001b69e  call    WPP_SF_
0x18001b6a3  mov     eax, 0Eh
0x18001b6a8  jmp     short loc_18001B64A
```
