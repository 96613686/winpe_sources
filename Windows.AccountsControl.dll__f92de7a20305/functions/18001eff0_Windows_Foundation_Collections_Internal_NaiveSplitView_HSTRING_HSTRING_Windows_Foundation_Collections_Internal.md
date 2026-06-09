# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::HasKey(HSTRING__ *,uchar *)

- ea: `0x18001eff0`
- end: `0x18001f0a6`
- name: `?HasKey@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAU1@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U73456@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAE@Z`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ef70`
- `0x1800620f0`

## callees

- `0x18001cf00`
- `0x18001eff0`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f08d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f072`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f08d`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::HasKey(
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
  v6 = *(_DWORD *)(*(_QWORD *)(a1 + 40) + 12LL);
  v12 = 0;
  v7 = 0;
  for ( i = 0; v7 >= 0 && (unsigned int)i < v6; i = (unsigned int)(i + 1) )
  {
    v9 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8 * i + 16);
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
0x18001eff0  mov     [rsp+arg_8], rbx
0x18001eff5  push    rbp
0x18001eff6  push    rsi
0x18001eff7  push    rdi
0x18001eff8  push    r14
0x18001effa  push    r15
0x18001effc  sub     rsp, 20h
0x18001f000  mov     rsi, r8
0x18001f003  mov     r15, rdx
0x18001f006  mov     r14, rcx
0x18001f009  mov     byte ptr [r8], 0
0x18001f00d  mov     rax, [rcx+28h]
0x18001f011  mov     ebp, [rax+0Ch]
0x18001f014  mov     [rsp+48h+arg_0], 0
0x18001f019  xor     ebx, ebx
0x18001f01b  xor     edi, edi
0x18001f01d  test    ebx, ebx
0x18001f01f  js      short loc_18001F093
0x18001f021  cmp     edi, ebp
0x18001f023  jnb     short loc_18001F093
0x18001f025  mov     rax, [r14+28h]
0x18001f029  mov     rcx, [rax+rdi*8+10h]
0x18001f02e  mov     [rsp+48h+string], 0
0x18001f037  mov     rax, [rcx]
0x18001f03a  lea     rdx, [rsp+48h+string]
0x18001f03f  mov     rax, [rax+30h]
0x18001f043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f048  mov     ebx, eax
0x18001f04a  test    eax, eax
0x18001f04c  js      short loc_18001F06D
0x18001f04e  lea     r9, [rsp+48h+arg_0]
0x18001f053  mov     r8, [rsp+48h+string]
0x18001f058  mov     rdx, r15
0x18001f05b  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x18001f060  mov     ebx, eax
0x18001f062  test    eax, eax
0x18001f064  js      short loc_18001F06D
0x18001f066  cmp     [rsp+48h+arg_0], 0
0x18001f06b  jnz     short loc_18001F085
0x18001f06d  mov     rcx, [rsp+48h+string]; string
0x18001f072  call    cs:__imp_WindowsDeleteString
0x18001f078  mov     [rsp+48h+string], 0
0x18001f081  inc     edi
0x18001f083  jmp     short loc_18001F01D
0x18001f085  mov     byte ptr [rsi], 1
0x18001f088  mov     rcx, [rsp+48h+string]; string
0x18001f08d  call    cs:__imp_WindowsDeleteString
0x18001f093  mov     eax, ebx
0x18001f095  mov     rbx, [rsp+48h+arg_8]
0x18001f09a  add     rsp, 20h
0x18001f09e  pop     r15
0x18001f0a0  pop     r14
0x18001f0a2  pop     rdi
0x18001f0a3  pop     rsi
0x18001f0a4  pop     rbp
0x18001f0a5  retn
```
