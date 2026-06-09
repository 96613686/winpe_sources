# Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::ChunkView::Lookup(HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus *)

- ea: `0x1800184c0`
- end: `0x1800185af`
- name: `?Lookup@ChunkView@?$NaiveSplitView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@PEAW4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@6@@Z`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800183b0`

## callees

- `0x180014924`
- `0x1800184c0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001857f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018553`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001857f`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::NaiveSplitView<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::ChunkView::Lookup(
        __int64 a1,
        __int64 a2,
        _DWORD *a3)
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
          v6 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v10 + 56LL))(v10, a3);
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
0x1800184c0  mov     [rsp+arg_8], rbx
0x1800184c5  push    rbp
0x1800184c6  push    rsi
0x1800184c7  push    rdi
0x1800184c8  push    r12
0x1800184ca  push    r13
0x1800184cc  push    r14
0x1800184ce  push    r15
0x1800184d0  sub     rsp, 20h
0x1800184d4  mov     r15, r8
0x1800184d7  mov     r12, rdx
0x1800184da  mov     r13, rcx
0x1800184dd  xor     ebx, ebx
0x1800184df  mov     rax, [rcx+48h]
0x1800184e3  mov     ebp, [rax+0Ch]
0x1800184e6  xor     dil, dil
0x1800184e9  mov     [rsp+58h+arg_0], dil
0x1800184ee  xor     esi, esi
0x1800184f0  test    ebx, ebx
0x1800184f2  js      loc_180018593
0x1800184f8  cmp     esi, ebp
0x1800184fa  jnb     loc_180018589
0x180018500  mov     rax, [r13+48h]
0x180018504  mov     r14, [rax+rsi*8+10h]
0x180018509  mov     [rsp+58h+string], 0
0x180018512  mov     rax, [r14]
0x180018515  lea     rdx, [rsp+58h+string]
0x18001851a  mov     rcx, r14
0x18001851d  mov     rax, [rax+30h]
0x180018521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018526  mov     ebx, eax
0x180018528  test    eax, eax
0x18001852a  js      short loc_18001854E
0x18001852c  lea     r9, [rsp+58h+arg_0]
0x180018531  mov     r8, [rsp+58h+string]
0x180018536  mov     rdx, r12
0x180018539  call    ??RStringEquals@XWinRT@@QEBAJPEAUHSTRING__@@0PEA_N@Z; XWinRT::StringEquals::operator()(HSTRING__ *,HSTRING__ *,bool *)
0x18001853e  mov     ebx, eax
0x180018540  mov     dil, [rsp+58h+arg_0]
0x180018545  test    eax, eax
0x180018547  js      short loc_18001854E
0x180018549  test    dil, dil
0x18001854c  jnz     short loc_180018566
0x18001854e  mov     rcx, [rsp+58h+string]; string
0x180018553  call    cs:__imp_WindowsDeleteString
0x180018559  mov     [rsp+58h+string], 0
0x180018562  inc     esi
0x180018564  jmp     short loc_1800184F0
0x180018566  mov     rax, [r14]
0x180018569  mov     rdx, r15
0x18001856c  mov     rcx, r14
0x18001856f  mov     rax, [rax+38h]
0x180018573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018578  mov     ebx, eax
0x18001857a  mov     rcx, [rsp+58h+string]; string
0x18001857f  call    cs:__imp_WindowsDeleteString
0x180018585  test    ebx, ebx
0x180018587  js      short loc_180018593
0x180018589  test    dil, dil
0x18001858c  jnz     short loc_180018598
0x18001858e  mov     ebx, 8000000Bh
0x180018593  xor     eax, eax
0x180018595  mov     [r15], eax
0x180018598  mov     eax, ebx
0x18001859a  mov     rbx, [rsp+58h+arg_8]
0x18001859f  add     rsp, 20h
0x1800185a3  pop     r15
0x1800185a5  pop     r14
0x1800185a7  pop     r13
0x1800185a9  pop     r12
0x1800185ab  pop     rdi
0x1800185ac  pop     rsi
0x1800185ad  pop     rbp
0x1800185ae  retn
```
