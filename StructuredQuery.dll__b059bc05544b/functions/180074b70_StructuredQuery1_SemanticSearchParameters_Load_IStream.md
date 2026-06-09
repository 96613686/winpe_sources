# StructuredQuery1::SemanticSearchParameters::Load(IStream *)

- ea: `0x180074b70`
- end: `0x180074c09`
- name: `?Load@SemanticSearchParameters@StructuredQuery1@@UEAAJPEAUIStream@@@Z`
- size: `153`
- prototype: `int(StructuredQuery1::SemanticSearchParameters *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180074ce0`

## callees

- `0x18002a220`
- `0x18005c03c`
- `0x180074b70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180074b8c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180074b8c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180074ba4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180074bc4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180074ba4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180074bc4`

## string_xrefs

- `0x180074bda`: `onecoreuap\base\appmodel\search\structuredquery\dll\semanticsearchparameters.cpp`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::SemanticSearchParameters::Load(RTL_SRWLOCK *this, struct IStream *a2)
{
  RTL_SRWLOCK *v2; // rbx
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v11; // [rsp+30h] [rbp+8h] BYREF

  v2 = this + 5;
  AcquireSRWLockExclusive(this + 5);
  v11 = v2;
  v5 = IStream_Read(a2, &this[6], 4u);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v5 = IStream_Read(a2, (char *)&this[6].Ptr + 4, 4u);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v6 = 0;
      goto LABEL_7;
    }
    v7 = 107;
  }
  else
  {
    v7 = 106;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\dll\\semanticsearchparameters.cpp",
    (const char *)(unsigned int)v5,
    v9);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  return v6;
}

```

## disassembly

```asm
0x180074b70  mov     [rsp+arg_8], rbx
0x180074b75  mov     [rsp+arg_10], rsi
0x180074b7a  push    rdi; int
0x180074b7b  sub     rsp, 20h
0x180074b7f  lea     rbx, [rcx+28h]
0x180074b83  mov     rdi, rcx
0x180074b86  mov     rcx, rbx; SRWLock
0x180074b89  mov     rsi, rdx
0x180074b8c  call    cs:__imp_AcquireSRWLockExclusive
0x180074b92  lea     rdx, [rdi+30h]; pv
0x180074b96  mov     [rsp+28h+arg_0], rbx
0x180074b9b  mov     r8d, 4; cb
0x180074ba1  mov     rcx, rsi; pstm
0x180074ba4  call    cs:__imp_IStream_Read
0x180074baa  mov     ebx, eax
0x180074bac  test    eax, eax
0x180074bae  jns     short loc_180074BB7
0x180074bb0  mov     edx, 6Ah ; 'j'
0x180074bb5  jmp     short loc_180074BD5
0x180074bb7  lea     rdx, [rdi+34h]; pv
0x180074bbb  mov     r8d, 4; cb
0x180074bc1  mov     rcx, rsi; pstm
0x180074bc4  call    cs:__imp_IStream_Read
0x180074bca  mov     ebx, eax
0x180074bcc  test    eax, eax
0x180074bce  jns     short loc_180074BEB
0x180074bd0  mov     edx, 6Bh ; 'k'; void *
0x180074bd5  mov     rcx, [rsp+28h]; this
0x180074bda  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\search\\str"...
0x180074be1  mov     r9d, eax; char *
0x180074be4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074be9  jmp     short loc_180074BED
0x180074beb  xor     ebx, ebx
0x180074bed  lea     rcx, [rsp+28h+arg_0]
0x180074bf2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180074bf7  mov     rsi, [rsp+28h+arg_10]
0x180074bfc  mov     eax, ebx
0x180074bfe  mov     rbx, [rsp+28h+arg_8]
0x180074c03  add     rsp, 20h
0x180074c07  pop     rdi
0x180074c08  retn
```
