# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::Lookup(HSTRING__ *,IInspectable * *)

- ea: `0x180023200`
- end: `0x1800232f1`
- name: `?Lookup@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800230d0`

## callees

- `0x180018bf0`
- `0x180023200`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023293`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800232bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180023293`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800232bf`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::ChunkView::Lookup(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  int v6; // ebx
  unsigned int v7; // ebp
  char v8; // di
  __int64 v9; // rsi
  __int64 v10; // r14
  __int64 v11; // rcx
  char v13; // [rsp+60h] [rbp+8h] BYREF
  HSTRING string; // [rsp+78h] [rbp+20h] BYREF

  v6 = 0;
  v7 = *(_DWORD *)(*(_QWORD *)(a1 + 40) + 12LL);
  v8 = 0;
  v13 = 0;
  v9 = 0;
  while ( v6 >= 0 )
  {
    if ( (unsigned int)v9 >= v7 )
      goto LABEL_9;
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8 * v9 + 16);
    string = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v10 + 48LL))(v10, &string);
    if ( v6 >= 0 )
    {
      v6 = XWinRT::StringEquals::operator()(v11, a2, string, &v13);
      v8 = v13;
      if ( v6 >= 0 )
      {
        if ( v13 )
        {
          v6 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v10 + 56LL))(v10, a3);
          WindowsDeleteString(string);
          if ( v6 < 0 )
            break;
LABEL_9:
          if ( v8 )
            return (unsigned int)v6;
          v6 = -2147483637;
          break;
        }
      }
    }
    WindowsDeleteString(string);
    string = 0;
    v9 = (unsigned int)(v9 + 1);
  }
  *a3 = 0;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180023200  mov     [rsp+arg_8], rbx
0x180023205  push    rbp
0x180023206  push    rsi
0x180023207  push    rdi
0x180023208  push    r12
0x18002320a  push    r13
0x18002320c  push    r14
0x18002320e  push    r15
0x180023210  sub     rsp, 20h
0x180023214  mov     r15, r8
0x180023217  mov     r12, rdx
0x18002321a  mov     r13, rcx
0x18002321d  xor     ebx, ebx
0x18002321f  mov     rax, [rcx+28h]
0x180023223  mov     ebp, [rax+0Ch]
0x180023226  xor     dil, dil
0x180023229  mov     [rsp+58h+arg_0], dil
0x18002322e  xor     esi, esi
0x180023230  test    ebx, ebx
0x180023232  js      loc_1800232D3
0x180023238  cmp     esi, ebp
0x18002323a  jnb     loc_1800232C9
0x180023240  mov     rax, [r13+28h]
0x180023244  mov     r14, [rax+rsi*8+10h]
0x180023249  mov     [rsp+58h+string], 0
0x180023252  mov     rax, [r14]
0x180023255  lea     rdx, [rsp+58h+string]
0x18002325a  mov     rcx, r14
0x18002325d  mov     rax, [rax+30h]
0x180023261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023266  mov     ebx, eax
0x180023268  test    eax, eax
0x18002326a  js      short loc_18002328E
0x18002326c  lea     r9, [rsp+58h+arg_0]
0x180023271  mov     r8, [rsp+58h+string]
0x180023276  mov     rdx, r12
0x180023279  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x18002327e  mov     ebx, eax
0x180023280  mov     dil, [rsp+58h+arg_0]
0x180023285  test    eax, eax
0x180023287  js      short loc_18002328E
0x180023289  test    dil, dil
0x18002328c  jnz     short loc_1800232A6
0x18002328e  mov     rcx, [rsp+58h+string]; string
0x180023293  call    cs:__imp_WindowsDeleteString
0x180023299  mov     [rsp+58h+string], 0
0x1800232a2  inc     esi
0x1800232a4  jmp     short loc_180023230
0x1800232a6  mov     rax, [r14]
0x1800232a9  mov     rdx, r15
0x1800232ac  mov     rcx, r14
0x1800232af  mov     rax, [rax+38h]
0x1800232b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232b8  mov     ebx, eax
0x1800232ba  mov     rcx, [rsp+58h+string]; string
0x1800232bf  call    cs:__imp_WindowsDeleteString
0x1800232c5  test    ebx, ebx
0x1800232c7  js      short loc_1800232D3
0x1800232c9  test    dil, dil
0x1800232cc  jnz     short loc_1800232DA
0x1800232ce  mov     ebx, 8000000Bh
0x1800232d3  mov     qword ptr [r15], 0
0x1800232da  mov     eax, ebx
0x1800232dc  mov     rbx, [rsp+58h+arg_8]
0x1800232e1  add     rsp, 20h
0x1800232e5  pop     r15
0x1800232e7  pop     r14
0x1800232e9  pop     r13
0x1800232eb  pop     r12
0x1800232ed  pop     rdi
0x1800232ee  pop     rsi
0x1800232ef  pop     rbp
0x1800232f0  retn
```
