# CSiteWithAgileServices::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x18003a0e0`
- end: `0x18003a1d7`
- name: `?QueryService@CSiteWithAgileServices@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `247`
- prototype: `int(CSiteWithAgileServices *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x1800114f4`
- `0x18003a0e0`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a15b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a15b`
- `SHCORE!IUnknown_QueryService` at `0x18003a1b0`
- `SHCORE!IUnknown_QueryService` at `0x18003a1b0`

## pseudocode

```c
__int64 __fastcall CSiteWithAgileServices::QueryService(
        CSiteWithAgileServices *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT Service; // edi
  unsigned int i; // r10d
  __int128 *v10; // r8
  __int64 v11; // rax
  int j; // ecx
  __int64 v13; // rax
  IUnknown **v14; // rax
  char v16; // [rsp+50h] [rbp+8h] BYREF

  *a4 = 0;
  Service = -2147467262;
  for ( i = 0; i < 6; ++i )
  {
    v10 = &xmmword_1800A9950[i];
    v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)v10;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)v10 )
      v11 = *(_QWORD *)a2->Data4 - *((_QWORD *)v10 + 1);
    if ( !v11 )
      return (unsigned int)Service;
  }
  Service = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *, const struct _GUID *))(**((_QWORD **)this + 13)
                                                                                          + 24LL))(
              *((_QWORD *)this + 13),
              a2,
              a3);
  if ( Service < 0 )
  {
    if ( *((_DWORD *)this + 28) == GetCurrentThreadId() )
    {
LABEL_15:
      v14 = (IUnknown **)CWRLObjectWithGITSite::SiteUnk((char *)this + 16, &v16);
      Service = IUnknown_QueryService(*v14, a2, a3, a4);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v16);
    }
    else
    {
      for ( j = 0; !j; j = 1 )
      {
        v13 = *(_QWORD *)&a2->Data1 - qword_1800A99B0[0];
        if ( *(_QWORD *)&a2->Data1 == qword_1800A99B0[0] )
          v13 = *(_QWORD *)a2->Data4 - qword_1800A99B0[1];
        if ( !v13 )
          goto LABEL_15;
      }
    }
  }
  return (unsigned int)Service;
}

```

## disassembly

```asm
0x18003a0e0  mov     [rsp+arg_8], rbx
0x18003a0e5  mov     [rsp+arg_10], rbp
0x18003a0ea  push    rsi
0x18003a0eb  push    rdi
0x18003a0ec  push    r14
0x18003a0ee  sub     rsp, 30h
0x18003a0f2  mov     r14, r9
0x18003a0f5  mov     qword ptr [r9], 0
0x18003a0fc  mov     rbp, r8
0x18003a0ff  mov     rbx, rdx
0x18003a102  mov     rsi, rcx
0x18003a105  mov     edi, 80004002h
0x18003a10a  xor     r10d, r10d
0x18003a10d  cmp     r10d, 6
0x18003a111  jnb     short loc_18003A142
0x18003a113  lea     rax, xmmword_1800A9950
0x18003a11a  mov     r8d, r10d
0x18003a11d  shl     r8, 4
0x18003a121  add     r8, rax
0x18003a124  mov     rax, [rdx]
0x18003a127  sub     rax, [r8]
0x18003a12a  jnz     short loc_18003A134
0x18003a12c  mov     rax, [rdx+8]
0x18003a130  sub     rax, [r8+8]
0x18003a134  test    rax, rax
0x18003a137  jz      loc_18003A1C2
0x18003a13d  inc     r10d
0x18003a140  jmp     short loc_18003A10D
0x18003a142  mov     rcx, [rcx+68h]
0x18003a146  mov     r8, rbp
0x18003a149  mov     rax, [rcx]
0x18003a14c  mov     rax, [rax+18h]
0x18003a150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a155  mov     edi, eax
0x18003a157  test    eax, eax
0x18003a159  jns     short loc_18003A1C2
0x18003a15b  call    cs:__imp_GetCurrentThreadId
0x18003a161  cmp     [rsi+70h], eax
0x18003a164  jz      short loc_18003A196
0x18003a166  xor     ecx, ecx
0x18003a168  cmp     ecx, 1
0x18003a16b  jnb     short loc_18003A1C2
0x18003a16d  lea     rax, qword_1800A99B0
0x18003a174  mov     edx, ecx
0x18003a176  shl     rdx, 4
0x18003a17a  add     rdx, rax
0x18003a17d  mov     rax, [rbx]
0x18003a180  sub     rax, [rdx]
0x18003a183  jnz     short loc_18003A18D
0x18003a185  mov     rax, [rbx+8]
0x18003a189  sub     rax, [rdx+8]
0x18003a18d  test    rax, rax
0x18003a190  jz      short loc_18003A196
0x18003a192  inc     ecx
0x18003a194  jmp     short loc_18003A168
0x18003a196  lea     rcx, [rsi+10h]
0x18003a19a  lea     rdx, [rsp+48h+arg_0]
0x18003a19f  call    ?SiteUnk@CWRLObjectWithGITSite@@IEAA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; CWRLObjectWithGITSite::SiteUnk(void)
0x18003a1a4  mov     r9, r14; ppvOut
0x18003a1a7  mov     r8, rbp; riid
0x18003a1aa  mov     rdx, rbx; guidService
0x18003a1ad  mov     rcx, [rax]; punk
0x18003a1b0  call    cs:__imp_IUnknown_QueryService
0x18003a1b6  lea     rcx, [rsp+48h+arg_0]
0x18003a1bb  mov     edi, eax
0x18003a1bd  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18003a1c2  mov     rbx, [rsp+48h+arg_8]
0x18003a1c7  mov     eax, edi
0x18003a1c9  mov     rbp, [rsp+48h+arg_10]
0x18003a1ce  add     rsp, 30h
0x18003a1d2  pop     r14
0x18003a1d4  pop     rdi
0x18003a1d5  pop     rsi
0x18003a1d6  retn
```
