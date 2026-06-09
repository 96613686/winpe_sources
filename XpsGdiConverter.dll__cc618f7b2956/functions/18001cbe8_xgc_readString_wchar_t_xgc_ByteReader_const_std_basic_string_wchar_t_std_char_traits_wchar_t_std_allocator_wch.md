# xgc::readString<wchar_t>(xgc::ByteReader const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,uint)

- ea: `0x18001cbe8`
- end: `0x18001ccbc`
- name: `??$readString@_W@xgc@@YAXAEBUByteReader@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@Z`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001f444`
- `0x180020c14`

## callees

- `0x18000d524`
- `0x18001c058`
- `0x18001cbe8`
- `0x1800228f0`
- `0x180037278`
- `0x1800372e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001cc92`
- `KERNEL32!GetLastError` at `0x18001cc92`

## pseudocode

```c
__int64 __fastcall xgc::readString<wchar_t>(__int64 **a1, __int64 a2, int a3)
{
  unsigned __int64 v3; // rsi
  __int64 result; // rax
  unsigned __int64 v7; // rdi
  _WORD *v8; // rbx
  __int64 *v9; // rcx
  const char *v10; // rdx
  __int64 v11; // r8
  xpsrdr *v12; // rcx
  _WORD *v13; // rcx
  signed int LastError; // eax
  int v15; // edx
  const char *v16; // r8
  int v17; // r9d
  _WORD *Destination; // [rsp+48h] [rbp+10h] BYREF

  v3 = *(_QWORD *)(a2 + 16);
  result = std::wstring::begin(a2, &Destination);
  v7 = 0;
  if ( v3 )
  {
    v8 = Destination;
    do
    {
      v9 = *a1;
      LOWORD(Destination) = 0;
      v10 = (const char *)(unsigned int)(a3 + 2 * v7);
      v11 = *v9;
      v12 = (xpsrdr *)(v9[1] - *v9);
      if ( v12 < (xpsrdr *)(v10 + 2) )
        xpsrdr::ThrowLogicException(v12, v10, v11);
      if ( memcpy_s(&Destination, 2u, &v10[v11], 2u) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( LastError >= 0 )
          LastError = -2147467259;
        xpsrdr::ThrowHRException((xpsrdr *)(unsigned int)LastError, v15, v16, v17);
      }
      xgc::SwapBytes<wchar_t>(&Destination);
      result = (unsigned __int16)Destination;
      v13 = v8++;
      ++v7;
      *v13 = (_WORD)Destination;
    }
    while ( v7 < v3 );
  }
  return result;
}

```

## disassembly

```asm
0x18001cbe8  mov     [rsp+arg_0], rbx
0x18001cbed  mov     [rsp+arg_10], rsi
0x18001cbf2  push    rdi
0x18001cbf3  push    r14
0x18001cbf5  push    r15
0x18001cbf7  sub     rsp, 20h
0x18001cbfb  mov     rsi, [rdx+10h]
0x18001cbff  mov     rax, rdx
0x18001cc02  mov     r15, rcx
0x18001cc05  lea     rdx, [rsp+38h+Destination]
0x18001cc0a  mov     rcx, rax
0x18001cc0d  mov     r14d, r8d
0x18001cc10  call    ?begin@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@2@XZ; std::wstring::begin(void)
0x18001cc15  xor     edi, edi
0x18001cc17  test    rsi, rsi
0x18001cc1a  jz      short loc_18001CC7E
0x18001cc1c  mov     rbx, [rsp+38h+Destination]
0x18001cc21  mov     rcx, [r15]
0x18001cc24  xor     eax, eax
0x18001cc26  mov     word ptr [rsp+38h+Destination], ax
0x18001cc2b  lea     eax, [r14+rdi*2]
0x18001cc2f  mov     edx, eax; char *
0x18001cc31  add     rax, 2
0x18001cc35  mov     r8, [rcx]; int
0x18001cc38  mov     rcx, [rcx+8]
0x18001cc3c  sub     rcx, r8; this
0x18001cc3f  cmp     rcx, rax
0x18001cc42  jb      short loc_18001CCB6
0x18001cc44  add     r8, rdx; Source
0x18001cc47  lea     rcx, [rsp+38h+Destination]; Destination
0x18001cc4c  mov     edx, 2; DestinationSize
0x18001cc51  mov     r9d, edx; SourceSize
0x18001cc54  call    memcpy_s
0x18001cc59  test    eax, eax
0x18001cc5b  jnz     short loc_18001CC92
0x18001cc5d  lea     rcx, [rsp+38h+Destination]
0x18001cc62  call    ??$SwapBytes@_W@xgc@@YAXPEA_W@Z; xgc::SwapBytes<wchar_t>(wchar_t *)
0x18001cc67  movzx   eax, word ptr [rsp+38h+Destination]
0x18001cc6c  mov     rcx, rbx
0x18001cc6f  add     rbx, 2
0x18001cc73  inc     rdi
0x18001cc76  mov     [rcx], ax
0x18001cc79  cmp     rdi, rsi
0x18001cc7c  jb      short loc_18001CC21
0x18001cc7e  mov     rbx, [rsp+38h+arg_0]
0x18001cc83  mov     rsi, [rsp+38h+arg_10]
0x18001cc88  add     rsp, 20h
0x18001cc8c  pop     r15
0x18001cc8e  pop     r14
0x18001cc90  pop     rdi
0x18001cc91  retn
0x18001cc92  call    cs:__imp_GetLastError
0x18001cc98  test    eax, eax
0x18001cc9a  jle     short loc_18001CCA4
0x18001cc9c  movzx   eax, ax
0x18001cc9f  or      eax, 80070000h
0x18001cca4  mov     ecx, 80004005h
0x18001cca9  test    eax, eax
0x18001ccab  cmovns  eax, ecx
0x18001ccae  mov     ecx, eax; this
0x18001ccb0  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18001ccb6  call    ?ThrowLogicException@xpsrdr@@YAXPEBDH@Z; xpsrdr::ThrowLogicException(char const *,int)
```
