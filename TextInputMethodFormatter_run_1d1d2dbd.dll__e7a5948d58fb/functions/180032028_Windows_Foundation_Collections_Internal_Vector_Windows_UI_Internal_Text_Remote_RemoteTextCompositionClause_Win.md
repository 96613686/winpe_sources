# Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>::IndexOfInternal(Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause *,uint,Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,uint *,uchar *)

- ea: `0x180032028`
- end: `0x1800320d3`
- name: `?IndexOfInternal@?$Vector@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@U?$DefaultEqualityPredicate@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4Collections@Foundation@6@U?$DefaultLifetimeTraits@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4896@U?$DefaultVectorOptions@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@4896@@Internal@Collections@Foundation@Windows@@AEAAJPEAURemoteTextCompositionClause@Remote@Text@2UI@5@IU678295@PEAIPEAE@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031f90`

## callees

- `0x180006a14`
- `0x180032028`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180032075`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180032075`

## string_xrefs

- `0x180032086`: `mincore\TextInput\Dev\Virtualization\TextInputMethodFormatter\dll\VectorPredicates.h`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::Vector<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause>>::IndexOfInternal(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        HSTRING *a4,
        unsigned int *a5,
        _BYTE *a6)
{
  unsigned int v6; // ebx
  unsigned int v7; // edi
  HSTRING v11; // rdx
  HSTRING v12; // rcx
  HRESULT v13; // eax
  int v15; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  INT32 result; // [rsp+50h] [rbp+18h] BYREF

  v6 = 0;
  v7 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      if ( (v6 & 0x80000000) != 0 )
        return v6;
      if ( a4[1] != *(HSTRING *)(a2 + 16LL * v7 + 8) )
        goto LABEL_7;
      v11 = *(HSTRING *)(a2 + 16LL * v7);
      v12 = *a4;
      result = 0;
      v13 = WindowsCompareStringOrdinal(v12, v11, &result);
      v6 = v13;
      if ( v13 >= 0 )
        break;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"mincore\\TextInput\\Dev\\Virtualization\\TextInputMethodFormatter\\dll\\VectorPredicates.h",
        (const char *)(unsigned int)v13,
        v15);
LABEL_8:
      if ( ++v7 >= a3 )
        return v6;
    }
    if ( !result )
    {
      v6 = 0;
      *a6 = 1;
      *a5 = v7;
      return v6;
    }
LABEL_7:
    v6 = 0;
    goto LABEL_8;
  }
  return v6;
}

```

## disassembly

```asm
0x180032028  mov     [rsp+arg_0], rbx
0x18003202d  mov     [rsp+arg_8], rbp
0x180032032  push    rsi
0x180032033  push    rdi
0x180032034  push    r14; int
0x180032036  sub     rsp, 20h
0x18003203a  xor     ebx, ebx
0x18003203c  xor     edi, edi
0x18003203e  mov     r14, r9
0x180032041  mov     esi, r8d
0x180032044  mov     rbp, rdx
0x180032047  test    r8d, r8d
0x18003204a  jz      short loc_1800320BE
0x18003204c  test    ebx, ebx
0x18003204e  js      short loc_1800320BE
0x180032050  mov     rax, [r14+8]
0x180032054  mov     edx, edi
0x180032056  add     rdx, rdx
0x180032059  cmp     rax, [rbp+rdx*8+8]
0x18003205e  jnz     short loc_1800320A3
0x180032060  mov     rdx, [rbp+rdx*8+0]; string2
0x180032065  lea     r8, [rsp+38h+result]; result
0x18003206a  mov     rcx, [r14]; string1
0x18003206d  mov     [rsp+38h+result], 0
0x180032075  call    cs:__imp_WindowsCompareStringOrdinal
0x18003207b  mov     ebx, eax
0x18003207d  test    eax, eax
0x18003207f  jns     short loc_18003209C
0x180032081  mov     rcx, [rsp+38h]; this
0x180032086  lea     r8, aMincoreTextinp_11; "mincore\\TextInput\\Dev\\Virtualization"...
0x18003208d  mov     r9d, eax; char *
0x180032090  mov     edx, 1Ch; void *
0x180032095  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003209a  jmp     short loc_1800320A5
0x18003209c  cmp     [rsp+38h+result], 0
0x1800320a1  jz      short loc_1800320AD
0x1800320a3  xor     ebx, ebx
0x1800320a5  inc     edi
0x1800320a7  cmp     edi, esi
0x1800320a9  jb      short loc_18003204C
0x1800320ab  jmp     short loc_1800320BE
0x1800320ad  mov     rax, [rsp+38h+arg_28]
0x1800320b2  xor     ebx, ebx
0x1800320b4  mov     byte ptr [rax], 1
0x1800320b7  mov     rax, [rsp+38h+arg_20]
0x1800320bc  mov     [rax], edi
0x1800320be  mov     rbp, [rsp+38h+arg_8]
0x1800320c3  mov     eax, ebx
0x1800320c5  mov     rbx, [rsp+38h+arg_0]
0x1800320ca  add     rsp, 20h
0x1800320ce  pop     r14
0x1800320d0  pop     rdi
0x1800320d1  pop     rsi
0x1800320d2  retn
```
