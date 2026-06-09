# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::ChunkView::Lookup(HSTRING__ *,IInspectable * *)

- ea: `0x18005dac0`
- end: `0x18005dbb1`
- name: `?Lookup@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@4567@U?$DefaultLifetimeTraits@PEAUIInspectable@@@4567@U?$HashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@4567@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005d980`

## callees

- `0x18005acc4`
- `0x18005dac0`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005db53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005db7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005db53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005db7f`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::ChunkView::Lookup(
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
  v7 = *(_DWORD *)(*(_QWORD *)(a1 + 72) + 12LL);
  v8 = 0;
  v13 = 0;
  v9 = 0;
  while ( v6 >= 0 )
  {
    if ( (unsigned int)v9 >= v7 )
      goto LABEL_9;
    v10 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 8 * v9 + 16);
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
0x18005dac0  mov     [rsp+arg_8], rbx
0x18005dac5  push    rbp
0x18005dac6  push    rsi
0x18005dac7  push    rdi
0x18005dac8  push    r12
0x18005daca  push    r13
0x18005dacc  push    r14
0x18005dace  push    r15
0x18005dad0  sub     rsp, 20h
0x18005dad4  mov     r15, r8
0x18005dad7  mov     r12, rdx
0x18005dada  mov     r13, rcx
0x18005dadd  xor     ebx, ebx
0x18005dadf  mov     rax, [rcx+48h]
0x18005dae3  mov     ebp, [rax+0Ch]
0x18005dae6  xor     dil, dil
0x18005dae9  mov     [rsp+58h+arg_0], dil
0x18005daee  xor     esi, esi
0x18005daf0  test    ebx, ebx
0x18005daf2  js      loc_18005DB93
0x18005daf8  cmp     esi, ebp
0x18005dafa  jnb     loc_18005DB89
0x18005db00  mov     rax, [r13+48h]
0x18005db04  mov     r14, [rax+rsi*8+10h]
0x18005db09  mov     [rsp+58h+string], 0
0x18005db12  mov     rax, [r14]
0x18005db15  lea     rdx, [rsp+58h+string]
0x18005db1a  mov     rcx, r14
0x18005db1d  mov     rax, [rax+30h]
0x18005db21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db26  mov     ebx, eax
0x18005db28  test    eax, eax
0x18005db2a  js      short loc_18005DB4E
0x18005db2c  lea     r9, [rsp+58h+arg_0]
0x18005db31  mov     r8, [rsp+58h+string]
0x18005db36  mov     rdx, r12
0x18005db39  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x18005db3e  mov     ebx, eax
0x18005db40  mov     dil, [rsp+58h+arg_0]
0x18005db45  test    eax, eax
0x18005db47  js      short loc_18005DB4E
0x18005db49  test    dil, dil
0x18005db4c  jnz     short loc_18005DB66
0x18005db4e  mov     rcx, [rsp+58h+string]; string
0x18005db53  call    cs:__imp_WindowsDeleteString
0x18005db59  mov     [rsp+58h+string], 0
0x18005db62  inc     esi
0x18005db64  jmp     short loc_18005DAF0
0x18005db66  mov     rax, [r14]
0x18005db69  mov     rdx, r15
0x18005db6c  mov     rcx, r14
0x18005db6f  mov     rax, [rax+38h]
0x18005db73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005db78  mov     ebx, eax
0x18005db7a  mov     rcx, [rsp+58h+string]; string
0x18005db7f  call    cs:__imp_WindowsDeleteString
0x18005db85  test    ebx, ebx
0x18005db87  js      short loc_18005DB93
0x18005db89  test    dil, dil
0x18005db8c  jnz     short loc_18005DB9A
0x18005db8e  mov     ebx, 8000000Bh
0x18005db93  mov     qword ptr [r15], 0
0x18005db9a  mov     eax, ebx
0x18005db9c  mov     rbx, [rsp+58h+arg_8]
0x18005dba1  add     rsp, 20h
0x18005dba5  pop     r15
0x18005dba7  pop     r14
0x18005dba9  pop     r13
0x18005dbab  pop     r12
0x18005dbad  pop     rdi
0x18005dbae  pop     rsi
0x18005dbaf  pop     rbp
0x18005dbb0  retn
```
