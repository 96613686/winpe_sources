# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002c20`
- end: `0x180002d23`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `259`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001e88`
- `0x180002c20`
- `0x180002e3c`
- `0x18000b606`
- `0x18000c010`

## string_xrefs

- `0x180002cff`: `CClassFactory::CreateInstance`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v5; // ebx
  __int64 (***v7)(void); // rcx
  __int64 (*v8)(void); // rax
  int v9; // eax
  int v10; // edx
  int v11; // ecx
  __int64 v12; // [rsp+0h] [rbp-38h] BYREF

  if ( a4 )
    *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v5 = -2147467262;
  if ( (*(_QWORD *)&IID_IWPWordBreaker.Data1 == *(_QWORD *)&a3->Data1
     && *(_QWORD *)IID_IWPWordBreaker.Data4 == *(_QWORD *)a3->Data4
     || *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&a3->Data1 && *(_QWORD *)IID_IUnknown.Data4 == *(_QWORD *)a3->Data4)
    && !memcmp_0(qword_18000EF80, &g_clsid, 0x10u) )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v7 = (__int64 (***)(void))operator new(0x10u);
      if ( v7 )
      {
        *v7 = (__int64 (**)(void))&LatinBreaker::`vftable';
        v7[1] = 0;
        _InterlockedIncrement(&g_dwObjectCount);
      }
      v8 = **v7;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
          McTemplateU0sqq_EventWriteTransfer(
            (unsigned int)v7,
            (unsigned int)&v12,
            (const char *)(unsigned int)"CClassFactory::CreateInstance",
            123,
            14);
        v5 = -2147024882;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180002D0D);
        return v5;
      }
    }
    v9 = v8();
    v5 = v9;
    if ( v9 < 0 && (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      McTemplateU0sqq_EventWriteTransfer(v11, v10, (const char *)(unsigned int)"CClassFactory::CreateInstance", 126, v9);
  }
  return v5;
}

```

## disassembly

```asm
0x180002c20  mov     [rsp+arg_0], rbx
0x180002c25  mov     [rsp+arg_10], rsi
0x180002c2a  push    rdi
0x180002c2b  sub     rsp, 30h
0x180002c2f  mov     rsi, r9
0x180002c32  mov     rdi, r8
0x180002c35  test    r9, r9
0x180002c38  jz      short loc_180002C41
0x180002c3a  mov     qword ptr [r9], 0
0x180002c41  test    rdx, rdx
0x180002c44  jz      short loc_180002C50
0x180002c46  mov     eax, 80040110h
0x180002c4b  jmp     loc_180002D13
0x180002c50  mov     ebx, 80004002h
0x180002c55  mov     rax, qword ptr cs:IID_IWPWordBreaker.Data1
0x180002c5c  cmp     rax, [r8]
0x180002c5f  jnz     short loc_180002C6E
0x180002c61  mov     rax, qword ptr cs:IID_IWPWordBreaker.Data4
0x180002c68  cmp     rax, [r8+8]
0x180002c6c  jz      short loc_180002C8F
0x180002c6e  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x180002c75  cmp     rax, [r8]
0x180002c78  jnz     loc_180002D11
0x180002c7e  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x180002c85  cmp     rax, [r8+8]
0x180002c89  jnz     loc_180002D11
0x180002c8f  mov     r8d, 10h; Size
0x180002c95  lea     rdx, g_clsid; Buf2
0x180002c9c  lea     rcx, qword_18000EF80; Buf1
0x180002ca3  call    memcmp_0
0x180002ca8  test    eax, eax
0x180002caa  jnz     short loc_180002D11
0x180002cac  lea     ecx, [rax+10h]; Size
0x180002caf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002cb4  mov     rcx, rax
0x180002cb7  test    rcx, rcx
0x180002cba  jz      short loc_180002CD5
0x180002cbc  lea     rax, ??_7LatinBreaker@@6B@; const LatinBreaker::`vftable'
0x180002cc3  mov     [rcx], rax
0x180002cc6  mov     qword ptr [rcx+8], 0
0x180002cce  lock inc cs:?g_dwObjectCount@@3JA; long g_dwObjectCount
0x180002cd5  mov     rax, [rcx]
0x180002cd8  mov     r8, rsi
0x180002cdb  mov     rdx, rdi
0x180002cde  mov     rax, [rax]
0x180002ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ce6  mov     ebx, eax
0x180002ce8  test    eax, eax
0x180002cea  jns     short loc_180002D11
0x180002cec  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180002cf3  jz      short loc_180002D11
0x180002cf5  mov     [rsp+38h+var_18], eax
0x180002cf9  mov     r9d, 7Eh ; '~'
0x180002cff  lea     r8, aCclassfactoryC; "CClassFactory::CreateInstance"
0x180002d06  call    McTemplateU0sqq_EventWriteTransfer
0x180002d0b  jmp     short loc_180002D11
0x180002d0d  mov     ebx, [rsp+38h+arg_8]
0x180002d11  mov     eax, ebx
0x180002d13  mov     rbx, [rsp+38h+arg_0]
0x180002d18  mov     rsi, [rsp+38h+arg_10]
0x180002d1d  add     rsp, 30h
0x180002d21  pop     rdi
0x180002d22  retn
```
