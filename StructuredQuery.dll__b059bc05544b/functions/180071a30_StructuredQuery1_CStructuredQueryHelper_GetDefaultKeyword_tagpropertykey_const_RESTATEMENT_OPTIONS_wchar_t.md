# StructuredQuery1::CStructuredQueryHelper::GetDefaultKeyword(_tagpropertykey const &,RESTATEMENT_OPTIONS,wchar_t * *)

- ea: `0x180071a30`
- end: `0x180071bd8`
- name: `?GetDefaultKeyword@CStructuredQueryHelper@StructuredQuery1@@UEAAJAEBU_tagpropertykey@@W4RESTATEMENT_OPTIONS@@PEAPEA_W@Z`
- size: `424`
- prototype: `int __high(const struct _tagpropertykey *, enum RESTATEMENT_OPTIONS, wchar_t **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010904`
- `0x180011a6c`
- `0x180071a30`
- `0x18007a9bc`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180071a72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180071a72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180071bb9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180071bb9`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180071b57`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180071b57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180071b90`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::CStructuredQueryHelper::GetDefaultKeyword(
        RTL_SRWLOCK *a1,
        PROPERTYKEY *a2,
        char a3,
        LPWSTR *a4)
{
  int ConditionPropertyNameFromKey; // ebx
  RTL_SRWLOCK *v9; // r12
  PVOID Ptr; // rcx
  wchar_t **v11; // r8
  void *v12; // rsi
  LANGID UserDefaultUILanguage; // ax
  wchar_t **v14; // r9
  __int64 v16; // [rsp+20h] [rbp-20h] BYREF
  __int64 v17; // [rsp+28h] [rbp-18h] BYREF
  __int64 v18; // [rsp+30h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+48h] BYREF

  *a4 = 0;
  ConditionPropertyNameFromKey = StructuredQuery1::CStructuredQueryHelper::_EnsureInitializedParser(a1);
  if ( ConditionPropertyNameFromKey >= 0 )
  {
    v9 = a1 + 8;
    AcquireSRWLockShared(a1 + 8);
    Ptr = a1[13].Ptr;
    v18 = 0;
    ConditionPropertyNameFromKey = (*(__int64 (__fastcall **)(PVOID, __int64 *))(*(_QWORD *)Ptr + 56LL))(Ptr, &v18);
    if ( ConditionPropertyNameFromKey >= 0 )
    {
      v17 = 0;
      ConditionPropertyNameFromKey = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 32LL))(v18, &v17);
      if ( ConditionPropertyNameFromKey >= 0 )
      {
        pv = 0;
        ConditionPropertyNameFromKey = StructuredQuery1::GetConditionPropertyNameFromKey(
                                         a2,
                                         (const struct _tagpropertykey *)&pv,
                                         v11);
        if ( ConditionPropertyNameFromKey >= 0 )
        {
          if ( (a3 & 1) != 0 )
          {
            v12 = 0;
            *a4 = (LPWSTR)pv;
          }
          else
          {
            v12 = pv;
            v16 = 0;
            ConditionPropertyNameFromKey = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64 *))(*(_QWORD *)v17 + 48LL))(
                                             v17,
                                             pv,
                                             &v16);
            if ( !ConditionPropertyNameFromKey )
            {
              pv = 0;
              ConditionPropertyNameFromKey = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v16 + 56LL))(
                                               v16,
                                               &pv);
              if ( ConditionPropertyNameFromKey >= 0 )
              {
                if ( pv )
                {
                  if ( (a3 & 2) != 0 )
                  {
                    UserDefaultUILanguage = GetUserDefaultUILanguage();
                    ConditionPropertyNameFromKey = StructuredQuery1::CoAllocStringLowercased(
                                                     (LPCWSTR)pv,
                                                     UserDefaultUILanguage,
                                                     a4,
                                                     v14);
                    CoTaskMemFree(pv);
                  }
                  else
                  {
                    *a4 = (LPWSTR)pv;
                  }
                }
                else
                {
                  ConditionPropertyNameFromKey = -2147467259;
                }
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
            }
          }
          CoTaskMemFree(v12);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    ReleaseSRWLockShared(v9);
  }
  return (unsigned int)ConditionPropertyNameFromKey;
}

```

## disassembly

```asm
0x180071a30  mov     [rsp-28h+arg_0], rbx
0x180071a35  mov     [rsp-28h+arg_8], rsi
0x180071a3a  push    rbp
0x180071a3b  push    rdi
0x180071a3c  push    r12
0x180071a3e  push    r14
0x180071a40  push    r15
0x180071a42  mov     rbp, rsp
0x180071a45  sub     rsp, 40h
0x180071a49  mov     rdi, r9
0x180071a4c  mov     qword ptr [r9], 0
0x180071a53  mov     r14d, r8d
0x180071a56  mov     r15, rdx
0x180071a59  mov     rsi, rcx
0x180071a5c  call    ?_EnsureInitializedParser@CStructuredQueryHelper@StructuredQuery1@@AEAAJXZ; StructuredQuery1::CStructuredQueryHelper::_EnsureInitializedParser(void)
0x180071a61  mov     ebx, eax
0x180071a63  test    eax, eax
0x180071a65  js      loc_180071BBF
0x180071a6b  lea     r12, [rsi+40h]
0x180071a6f  mov     rcx, r12; SRWLock
0x180071a72  call    cs:__imp_AcquireSRWLockShared
0x180071a78  mov     rcx, [rsi+68h]
0x180071a7c  lea     rdx, [rbp+var_10]
0x180071a80  mov     [rbp+var_10], 0
0x180071a88  mov     rax, [rcx]
0x180071a8b  mov     rax, [rax+38h]
0x180071a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071a94  mov     ebx, eax
0x180071a96  test    eax, eax
0x180071a98  js      loc_180071BB6
0x180071a9e  mov     rcx, [rbp+var_10]
0x180071aa2  lea     rdx, [rbp+var_18]
0x180071aa6  mov     [rbp+var_18], 0
0x180071aae  mov     rax, [rcx]
0x180071ab1  mov     rax, [rax+20h]
0x180071ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071aba  mov     ebx, eax
0x180071abc  test    eax, eax
0x180071abe  js      loc_180071BA6
0x180071ac4  lea     rdx, [rbp+pv]; struct _tagpropertykey *
0x180071ac8  mov     [rbp+pv], 0
0x180071ad0  mov     rcx, r15; propkey
0x180071ad3  call    ?GetConditionPropertyNameFromKey@StructuredQuery1@@YAJAEBU_tagpropertykey@@PEAPEA_W@Z; StructuredQuery1::GetConditionPropertyNameFromKey(_tagpropertykey const &,wchar_t * *)
0x180071ad8  mov     ebx, eax
0x180071ada  test    eax, eax
0x180071adc  js      loc_180071B96
0x180071ae2  test    r14b, 1
0x180071ae6  jz      short loc_180071AF6
0x180071ae8  mov     rax, [rbp+pv]
0x180071aec  xor     esi, esi
0x180071aee  mov     [rdi], rax
0x180071af1  jmp     loc_180071B8D
0x180071af6  mov     rcx, [rbp+var_18]
0x180071afa  lea     r8, [rbp+var_20]
0x180071afe  mov     rsi, [rbp+pv]
0x180071b02  mov     [rbp+var_20], 0
0x180071b0a  mov     rdx, rsi
0x180071b0d  mov     rax, [rcx]
0x180071b10  mov     rax, [rax+30h]
0x180071b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071b19  mov     ebx, eax
0x180071b1b  test    eax, eax
0x180071b1d  jnz     short loc_180071B8D
0x180071b1f  mov     rcx, [rbp+var_20]
0x180071b23  lea     rdx, [rbp+pv]
0x180071b27  mov     [rbp+pv], 0
0x180071b2f  mov     rax, [rcx]
0x180071b32  mov     rax, [rax+38h]
0x180071b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071b3b  mov     ebx, eax
0x180071b3d  test    eax, eax
0x180071b3f  js      short loc_180071B7D
0x180071b41  mov     rax, [rbp+pv]
0x180071b45  test    rax, rax
0x180071b48  jnz     short loc_180071B51
0x180071b4a  mov     ebx, 80004005h
0x180071b4f  jmp     short loc_180071B7D
0x180071b51  test    r14b, 2
0x180071b55  jz      short loc_180071B7A
0x180071b57  call    cs:__imp_GetUserDefaultUILanguage
0x180071b5d  mov     rcx, [rbp+pv]; lpSrcStr
0x180071b61  mov     r8, rdi; unsigned int
0x180071b64  movzx   edx, ax; Locale
0x180071b67  call    ?CoAllocStringLowercased@StructuredQuery1@@YAJPEB_WKPEAPEA_W@Z; StructuredQuery1::CoAllocStringLowercased(wchar_t const *,ulong,wchar_t * *)
0x180071b6c  mov     rcx, [rbp+pv]; pv
0x180071b70  mov     ebx, eax
0x180071b72  call    cs:__imp_CoTaskMemFree
0x180071b78  jmp     short loc_180071B7D
0x180071b7a  mov     [rdi], rax
0x180071b7d  mov     rcx, [rbp+var_20]
0x180071b81  mov     rax, [rcx]
0x180071b84  mov     rax, [rax+10h]
0x180071b88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071b8d  mov     rcx, rsi; pv
0x180071b90  call    cs:__imp_CoTaskMemFree
0x180071b96  mov     rcx, [rbp+var_18]
0x180071b9a  mov     rax, [rcx]
0x180071b9d  mov     rax, [rax+10h]
0x180071ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ba6  mov     rcx, [rbp+var_10]
0x180071baa  mov     rax, [rcx]
0x180071bad  mov     rax, [rax+10h]
0x180071bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071bb6  mov     rcx, r12; SRWLock
0x180071bb9  call    cs:__imp_ReleaseSRWLockShared
0x180071bbf  mov     rsi, [rsp+40h+arg_8]
0x180071bc4  mov     eax, ebx
0x180071bc6  mov     rbx, [rsp+40h+arg_0]
0x180071bcb  add     rsp, 40h
0x180071bcf  pop     r15
0x180071bd1  pop     r14
0x180071bd3  pop     r12
0x180071bd5  pop     rdi
0x180071bd6  pop     rbp
0x180071bd7  retn
```
