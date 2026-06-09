# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::ChunkView::HasKey(HSTRING__ *,uchar *)

- ea: `0x180017ad0`
- end: `0x180017b86`
- name: `?HasKey@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAE@Z`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017a50`

## callees

- `0x180014924`
- `0x180017ad0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017b52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017b6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017b52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017b6d`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::ChunkView::HasKey(
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
0x180017ad0  mov     [rsp+arg_8], rbx
0x180017ad5  push    rbp
0x180017ad6  push    rsi
0x180017ad7  push    rdi
0x180017ad8  push    r14
0x180017ada  push    r15
0x180017adc  sub     rsp, 20h
0x180017ae0  mov     rsi, r8
0x180017ae3  mov     r15, rdx
0x180017ae6  mov     r14, rcx
0x180017ae9  mov     byte ptr [r8], 0
0x180017aed  mov     rax, [rcx+48h]
0x180017af1  mov     ebp, [rax+0Ch]
0x180017af4  mov     [rsp+48h+arg_0], 0
0x180017af9  xor     ebx, ebx
0x180017afb  xor     edi, edi
0x180017afd  test    ebx, ebx
0x180017aff  js      short loc_180017B73
0x180017b01  cmp     edi, ebp
0x180017b03  jnb     short loc_180017B73
0x180017b05  mov     rax, [r14+48h]
0x180017b09  mov     rcx, [rax+rdi*8+10h]
0x180017b0e  mov     [rsp+48h+string], 0
0x180017b17  mov     rax, [rcx]
0x180017b1a  lea     rdx, [rsp+48h+string]
0x180017b1f  mov     rax, [rax+30h]
0x180017b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b28  mov     ebx, eax
0x180017b2a  test    eax, eax
0x180017b2c  js      short loc_180017B4D
0x180017b2e  lea     r9, [rsp+48h+arg_0]
0x180017b33  mov     r8, [rsp+48h+string]
0x180017b38  mov     rdx, r15
0x180017b3b  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x180017b40  mov     ebx, eax
0x180017b42  test    eax, eax
0x180017b44  js      short loc_180017B4D
0x180017b46  cmp     [rsp+48h+arg_0], 0
0x180017b4b  jnz     short loc_180017B65
0x180017b4d  mov     rcx, [rsp+48h+string]; string
0x180017b52  call    cs:__imp_WindowsDeleteString
0x180017b58  mov     [rsp+48h+string], 0
0x180017b61  inc     edi
0x180017b63  jmp     short loc_180017AFD
0x180017b65  mov     byte ptr [rsi], 1
0x180017b68  mov     rcx, [rsp+48h+string]; string
0x180017b6d  call    cs:__imp_WindowsDeleteString
0x180017b73  mov     eax, ebx
0x180017b75  mov     rbx, [rsp+48h+arg_8]
0x180017b7a  add     rsp, 20h
0x180017b7e  pop     r15
0x180017b80  pop     r14
0x180017b82  pop     rdi
0x180017b83  pop     rsi
0x180017b84  pop     rbp
0x180017b85  retn
```
