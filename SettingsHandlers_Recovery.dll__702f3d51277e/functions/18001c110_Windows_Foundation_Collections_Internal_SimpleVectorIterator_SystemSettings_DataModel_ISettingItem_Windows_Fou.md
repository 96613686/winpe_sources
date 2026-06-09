# Windows::Foundation::Collections::Internal::SimpleVectorIterator<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,XWinRT::IntVersionTag,1>::MoveNext(uchar *)

- ea: `0x18001c110`
- end: `0x18001c1b9`
- name: `?MoveNext@?$SimpleVectorIterator@PEAUISettingItem@DataModel@SystemSettings@@V?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@UEAAJPEAE@Z`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001c110`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18001c1a6`
- `api-ms-win-core-winrt-error-l1-1-0!RoTransformError` at `0x18001c1a6`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001c12d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001c169`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001c194`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001c12d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001c169`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001c194`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleVectorIterator<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,XWinRT::IntVersionTag,1>::MoveNext(
        __int64 a1,
        bool *a2)
{
  int v3; // ebx
  __int64 v5; // rbp
  __int64 v6; // rdx
  bool v7; // zf
  unsigned __int32 v8; // eax

  *a2 = 0;
  v3 = *(_DWORD *)(a1 + 80);
  if ( v3 >= 0 )
  {
    v5 = *(_QWORD *)(a1 + 64);
    LODWORD(v6) = *(_DWORD *)(a1 + 72);
    while ( 1 )
    {
      *a2 = 0;
      if ( (unsigned int)v6 >= *(_DWORD *)(a1 + 76) )
        break;
      v3 = 0;
      *a2 = (unsigned int)(v6 + 1) < *(_DWORD *)(a1 + 76);
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 72), v6 + 1, v6);
      v7 = (_DWORD)v6 == v8;
      v6 = v8;
      if ( v7 )
        goto LABEL_8;
      *a2 = 0;
    }
    v3 = -2147483637;
    RoOriginateError(2147483659LL, 0);
LABEL_8:
    if ( *(_DWORD *)(a1 + 84) != (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)(v5 + 40) + 24LL))(
                                   v5 + 40,
                                   v6) )
    {
      *(_DWORD *)(a1 + 80) = -2147483636;
      if ( v3 < 0 )
      {
        RoTransformError((unsigned int)v3, 2147483660LL, 0);
      }
      else
      {
        RoOriginateError(2147483660LL, 0);
        *a2 = 0;
      }
      return (unsigned int)-2147483636;
    }
  }
  else
  {
    RoOriginateError((unsigned int)v3, 0);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001c110  push    rbx
0x18001c112  push    rbp
0x18001c113  push    rsi
0x18001c114  push    rdi
0x18001c115  sub     rsp, 28h
0x18001c119  mov     byte ptr [rdx], 0
0x18001c11c  mov     rsi, rdx
0x18001c11f  mov     ebx, [rcx+50h]
0x18001c122  mov     rdi, rcx
0x18001c125  test    ebx, ebx
0x18001c127  jns     short loc_18001C135
0x18001c129  xor     edx, edx
0x18001c12b  mov     ecx, ebx
0x18001c12d  call    cs:__imp_RoOriginateError
0x18001c133  jmp     short loc_18001C1AE
0x18001c135  mov     rbp, [rcx+40h]
0x18001c139  mov     edx, [rcx+48h]
0x18001c13c  mov     byte ptr [rsi], 0
0x18001c13f  cmp     edx, [rdi+4Ch]
0x18001c142  jnb     short loc_18001C160
0x18001c144  lea     ecx, [rdx+1]
0x18001c147  cmp     ecx, [rdi+4Ch]
0x18001c14a  setb    al
0x18001c14d  xor     ebx, ebx
0x18001c14f  mov     [rsi], al
0x18001c151  mov     eax, edx
0x18001c153  lock cmpxchg [rdi+48h], ecx
0x18001c158  mov     edx, eax
0x18001c15a  jz      short loc_18001C16F
0x18001c15c  mov     [rsi], bl
0x18001c15e  jmp     short loc_18001C13C
0x18001c160  mov     ebx, 8000000Bh
0x18001c165  xor     edx, edx
0x18001c167  mov     ecx, ebx
0x18001c169  call    cs:__imp_RoOriginateError
0x18001c16f  lea     rcx, [rbp+28h]
0x18001c173  mov     rax, [rcx]
0x18001c176  mov     rax, [rax+18h]
0x18001c17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c17f  cmp     [rdi+54h], eax
0x18001c182  jz      short loc_18001C1AE
0x18001c184  mov     ebp, 8000000Ch
0x18001c189  mov     [rdi+50h], ebp
0x18001c18c  test    ebx, ebx
0x18001c18e  js      short loc_18001C19F
0x18001c190  xor     edx, edx
0x18001c192  mov     ecx, ebp
0x18001c194  call    cs:__imp_RoOriginateError
0x18001c19a  mov     byte ptr [rsi], 0
0x18001c19d  jmp     short loc_18001C1AC
0x18001c19f  xor     r8d, r8d
0x18001c1a2  mov     edx, ebp
0x18001c1a4  mov     ecx, ebx
0x18001c1a6  call    cs:__imp_RoTransformError
0x18001c1ac  mov     ebx, ebp
0x18001c1ae  mov     eax, ebx
0x18001c1b0  add     rsp, 28h
0x18001c1b4  pop     rdi
0x18001c1b5  pop     rsi
0x18001c1b6  pop     rbp
0x18001c1b7  pop     rbx
0x18001c1b8  retn
```
