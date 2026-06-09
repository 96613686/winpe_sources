# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::ChunkView::HasKey(HSTRING__ *,uchar *)

- ea: `0x18005cc60`
- end: `0x18005cd16`
- name: `?HasKey@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAE@Z`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005cbe0`

## callees

- `0x18005acc4`
- `0x18005cc60`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cce2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ccfd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cce2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ccfd`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::ChunkView::HasKey(
        __int64 a1,
        __int64 a2,
        _BYTE *a3)
{
  unsigned int v6; // ebp
  int v7; // ebx
  __int64 i; // rdi
  __int64 v9; // rcx
  __int64 v10; // rcx
  char v12; // [rsp+50h] [rbp+8h] BYREF
  HSTRING string; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  v6 = *(_DWORD *)(*(_QWORD *)(a1 + 72) + 12LL);
  v12 = 0;
  v7 = 0;
  for ( i = 0; v7 >= 0 && (unsigned int)i < v6; i = (unsigned int)(i + 1) )
  {
    v9 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 8 * i + 16);
    string = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v9 + 48LL))(v9, &string);
    if ( v7 >= 0 )
    {
      v7 = XWinRT::StringEquals::operator()(v10, a2, string, &v12);
      if ( v7 >= 0 )
      {
        if ( v12 )
        {
          *a3 = 1;
          WindowsDeleteString(string);
          return (unsigned int)v7;
        }
      }
    }
    WindowsDeleteString(string);
    string = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005cc60  mov     [rsp+arg_8], rbx
0x18005cc65  push    rbp
0x18005cc66  push    rsi
0x18005cc67  push    rdi
0x18005cc68  push    r14
0x18005cc6a  push    r15
0x18005cc6c  sub     rsp, 20h
0x18005cc70  mov     rsi, r8
0x18005cc73  mov     r15, rdx
0x18005cc76  mov     r14, rcx
0x18005cc79  mov     byte ptr [r8], 0
0x18005cc7d  mov     rax, [rcx+48h]
0x18005cc81  mov     ebp, [rax+0Ch]
0x18005cc84  mov     [rsp+48h+arg_0], 0
0x18005cc89  xor     ebx, ebx
0x18005cc8b  xor     edi, edi
0x18005cc8d  test    ebx, ebx
0x18005cc8f  js      short loc_18005CD03
0x18005cc91  cmp     edi, ebp
0x18005cc93  jnb     short loc_18005CD03
0x18005cc95  mov     rax, [r14+48h]
0x18005cc99  mov     rcx, [rax+rdi*8+10h]
0x18005cc9e  mov     [rsp+48h+string], 0
0x18005cca7  mov     rax, [rcx]
0x18005ccaa  lea     rdx, [rsp+48h+string]
0x18005ccaf  mov     rax, [rax+30h]
0x18005ccb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ccb8  mov     ebx, eax
0x18005ccba  test    eax, eax
0x18005ccbc  js      short loc_18005CCDD
0x18005ccbe  lea     r9, [rsp+48h+arg_0]
0x18005ccc3  mov     r8, [rsp+48h+string]
0x18005ccc8  mov     rdx, r15
0x18005cccb  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x18005ccd0  mov     ebx, eax
0x18005ccd2  test    eax, eax
0x18005ccd4  js      short loc_18005CCDD
0x18005ccd6  cmp     [rsp+48h+arg_0], 0
0x18005ccdb  jnz     short loc_18005CCF5
0x18005ccdd  mov     rcx, [rsp+48h+string]; string
0x18005cce2  call    cs:__imp_WindowsDeleteString
0x18005cce8  mov     [rsp+48h+string], 0
0x18005ccf1  inc     edi
0x18005ccf3  jmp     short loc_18005CC8D
0x18005ccf5  mov     byte ptr [rsi], 1
0x18005ccf8  mov     rcx, [rsp+48h+string]; string
0x18005ccfd  call    cs:__imp_WindowsDeleteString
0x18005cd03  mov     eax, ebx
0x18005cd05  mov     rbx, [rsp+48h+arg_8]
0x18005cd0a  add     rsp, 20h
0x18005cd0e  pop     r15
0x18005cd10  pop     r14
0x18005cd12  pop     rdi
0x18005cd13  pop     rsi
0x18005cd14  pop     rbp
0x18005cd15  retn
```
