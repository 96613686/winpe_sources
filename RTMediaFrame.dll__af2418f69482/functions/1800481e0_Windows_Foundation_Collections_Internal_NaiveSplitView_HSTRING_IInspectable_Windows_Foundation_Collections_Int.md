# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::HasKey(HSTRING__ *,uchar *)

- ea: `0x1800481e0`
- end: `0x180048296`
- name: `?HasKey@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAE@Z`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180048160`

## callees

- `0x18003a818`
- `0x1800481e0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048262`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004827d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048262`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004827d`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::HasKey(
        __int64 a1,
        __int64 a2,
        _BYTE *a3)
{
  int v3; // ebx
  __int64 v4; // rax
  __int64 v8; // rdi
  unsigned int v9; // ebp
  __int64 v10; // rcx
  __int64 v11; // rcx
  HSTRING v12; // rcx
  char v14; // [rsp+50h] [rbp+8h] BYREF
  HSTRING string; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  v3 = 0;
  v4 = *(_QWORD *)(a1 + 40);
  v14 = 0;
  v8 = 0;
  v9 = *(_DWORD *)(v4 + 12);
  while ( v3 >= 0 && (unsigned int)v8 < v9 )
  {
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8 * v8 + 16);
    string = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v10 + 48LL))(v10, &string);
    if ( v3 >= 0 )
    {
      v3 = XWinRT::StringEquals::operator()(v11, a2, string, &v14);
      if ( v3 >= 0 )
      {
        if ( v14 )
        {
          v12 = string;
          *a3 = 1;
          WindowsDeleteString(v12);
          return (unsigned int)v3;
        }
      }
    }
    WindowsDeleteString(string);
    v8 = (unsigned int)(v8 + 1);
    string = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800481e0  mov     [rsp+arg_8], rbx
0x1800481e5  push    rbp
0x1800481e6  push    rsi
0x1800481e7  push    rdi
0x1800481e8  push    r14
0x1800481ea  push    r15
0x1800481ec  sub     rsp, 20h
0x1800481f0  mov     byte ptr [r8], 0
0x1800481f4  xor     ebx, ebx
0x1800481f6  mov     rax, [rcx+28h]
0x1800481fa  mov     rsi, r8
0x1800481fd  mov     r15, rdx
0x180048200  mov     [rsp+48h+arg_0], 0
0x180048205  mov     r14, rcx
0x180048208  xor     edi, edi
0x18004820a  mov     ebp, [rax+0Ch]
0x18004820d  test    ebx, ebx
0x18004820f  js      short loc_180048283
0x180048211  cmp     edi, ebp
0x180048213  jnb     short loc_180048283
0x180048215  mov     rax, [r14+28h]
0x180048219  lea     rdx, [rsp+48h+string]
0x18004821e  mov     rcx, [rax+rdi*8+10h]
0x180048223  mov     [rsp+48h+string], 0
0x18004822c  mov     rax, [rcx]
0x18004822f  mov     rax, [rax+30h]
0x180048233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048238  mov     ebx, eax
0x18004823a  test    eax, eax
0x18004823c  js      short loc_18004825D
0x18004823e  mov     r8, [rsp+48h+string]
0x180048243  lea     r9, [rsp+48h+arg_0]
0x180048248  mov     rdx, r15
0x18004824b  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x180048250  mov     ebx, eax
0x180048252  test    eax, eax
0x180048254  js      short loc_18004825D
0x180048256  cmp     [rsp+48h+arg_0], 0
0x18004825b  jnz     short loc_180048275
0x18004825d  mov     rcx, [rsp+48h+string]; string
0x180048262  call    cs:__imp_WindowsDeleteString
0x180048268  inc     edi
0x18004826a  mov     [rsp+48h+string], 0
0x180048273  jmp     short loc_18004820D
0x180048275  mov     rcx, [rsp+48h+string]; string
0x18004827a  mov     byte ptr [rsi], 1
0x18004827d  call    cs:__imp_WindowsDeleteString
0x180048283  mov     eax, ebx
0x180048285  mov     rbx, [rsp+48h+arg_8]
0x18004828a  add     rsp, 20h
0x18004828e  pop     r15
0x180048290  pop     r14
0x180048292  pop     rdi
0x180048293  pop     rsi
0x180048294  pop     rbp
0x180048295  retn
```
