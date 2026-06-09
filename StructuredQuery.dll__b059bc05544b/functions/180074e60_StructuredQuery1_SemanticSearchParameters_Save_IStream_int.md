# StructuredQuery1::SemanticSearchParameters::Save(IStream *,int)

- ea: `0x180074e60`
- end: `0x180074ef9`
- name: `?Save@SemanticSearchParameters@StructuredQuery1@@UEAAJPEAUIStream@@H@Z`
- size: `153`
- prototype: `int(StructuredQuery1::SemanticSearchParameters *__hidden this, struct IStream *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180075050`

## callees

- `0x18002a220`
- `0x180060864`
- `0x180074e60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180074e7c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180074e7c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180074e94`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180074eb4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180074e94`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180074eb4`

## string_xrefs

- `0x180074eca`: `onecoreuap\base\appmodel\search\structuredquery\dll\semanticsearchparameters.cpp`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::SemanticSearchParameters::Save(RTL_SRWLOCK *this, struct IStream *a2)
{
  RTL_SRWLOCK *v2; // rbx
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v11; // [rsp+30h] [rbp+8h] BYREF

  v2 = this + 5;
  AcquireSRWLockShared(this + 5);
  v11 = v2;
  v5 = IStream_Write(a2, &this[6], 4u);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v5 = IStream_Write(a2, (char *)&this[6].Ptr + 4, 4u);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v6 = 0;
      goto LABEL_7;
    }
    v7 = 97;
  }
  else
  {
    v7 = 96;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\dll\\semanticsearchparameters.cpp",
    (const char *)(unsigned int)v5,
    v9);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  return v6;
}

```

## disassembly

```asm
0x180074e60  mov     [rsp+arg_8], rbx
0x180074e65  mov     [rsp+arg_10], rsi
0x180074e6a  push    rdi; int
0x180074e6b  sub     rsp, 20h
0x180074e6f  lea     rbx, [rcx+28h]
0x180074e73  mov     rdi, rcx
0x180074e76  mov     rcx, rbx; SRWLock
0x180074e79  mov     rsi, rdx
0x180074e7c  call    cs:__imp_AcquireSRWLockShared
0x180074e82  lea     rdx, [rdi+30h]; pv
0x180074e86  mov     [rsp+28h+arg_0], rbx
0x180074e8b  mov     r8d, 4; cb
0x180074e91  mov     rcx, rsi; pstm
0x180074e94  call    cs:__imp_IStream_Write
0x180074e9a  mov     ebx, eax
0x180074e9c  test    eax, eax
0x180074e9e  jns     short loc_180074EA7
0x180074ea0  mov     edx, 60h ; '`'
0x180074ea5  jmp     short loc_180074EC5
0x180074ea7  lea     rdx, [rdi+34h]; pv
0x180074eab  mov     r8d, 4; cb
0x180074eb1  mov     rcx, rsi; pstm
0x180074eb4  call    cs:__imp_IStream_Write
0x180074eba  mov     ebx, eax
0x180074ebc  test    eax, eax
0x180074ebe  jns     short loc_180074EDB
0x180074ec0  mov     edx, 61h ; 'a'; void *
0x180074ec5  mov     rcx, [rsp+28h]; this
0x180074eca  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\search\\str"...
0x180074ed1  mov     r9d, eax; char *
0x180074ed4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074ed9  jmp     short loc_180074EDD
0x180074edb  xor     ebx, ebx
0x180074edd  lea     rcx, [rsp+28h+arg_0]
0x180074ee2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180074ee7  mov     rsi, [rsp+28h+arg_10]
0x180074eec  mov     eax, ebx
0x180074eee  mov     rbx, [rsp+28h+arg_8]
0x180074ef3  add     rsp, 20h
0x180074ef7  pop     rdi
0x180074ef8  retn
```
