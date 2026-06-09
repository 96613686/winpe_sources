# WindowsMidiServicesInternal::JsonStringifyObjectToOutParam(winrt::Windows::Data::Json::JsonObject const &,ushort * *)

- ea: `0x18001d33c`
- end: `0x18001d3d1`
- name: `?JsonStringifyObjectToOutParam@WindowsMidiServicesInternal@@YA_NAEBUJsonObject@Json@Data@Windows@winrt@@PEAPEAG@Z`
- size: `149`
- prototype: `bool __fastcall(WindowsMidiServicesInternal *__hidden this, const struct winrt::Windows::Data::Json::JsonObject *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001d680`

## callees

- `0x180004718`
- `0x180004784`
- `0x18001d33c`
- `0x18001d5b0`
- `0x18001e528`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001d3c9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001d3c9`

## pseudocode

```c
bool __fastcall WindowsMidiServicesInternal::JsonStringifyObjectToOutParam(
        WindowsMidiServicesInternal *this,
        const struct winrt::Windows::Data::Json::JsonObject *a2,
        unsigned __int16 **a3)
{
  bool result; // al
  __int64 v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  const unsigned __int16 *v8; // rdx
  void *v9; // rbx
  int v10; // eax
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+38h] [rbp+10h] BYREF
  _BOOL8 v13; // [rsp+40h] [rbp+18h] BYREF

  if ( !a2 )
    return 0;
  try
  {
    v5 = *winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(
            (__int64 *)this,
            &lpMem);
    if ( v5 )
      v8 = *(const unsigned __int16 **)(v5 + 16);
    else
      v8 = &S2;
    wil::make_cotaskmem_string_nothrow((wil *)&v13, v8, v6, v7);
    v9 = lpMem;
    if ( lpMem )
    {
      v10 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v10 )
      {
        if ( v10 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v9);
      }
    }
    result = v13;
    if ( v13 )
    {
      *(_QWORD *)a2 = v13;
      result = 1;
    }
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001d33c  mov     [rsp+arg_0], rbx
0x18001d341  push    rdi
0x18001d342  sub     rsp, 20h
0x18001d346  mov     rdi, rdx
0x18001d349  test    rdx, rdx
0x18001d34c  jnz     short loc_18001D352
0x18001d34e  xor     al, al
0x18001d350  jmp     short loc_18001D3BA
0x18001d352  lea     rdx, [rsp+28h+lpMem]
0x18001d357  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)
0x18001d35c  mov     rax, [rax]
0x18001d35f  test    rax, rax
0x18001d362  jz      short loc_18001D36A
0x18001d364  mov     rdx, [rax+10h]
0x18001d368  jmp     short loc_18001D371
0x18001d36a  lea     rdx, S2; unsigned __int16 *
0x18001d371  lea     rcx, [rsp+28h+arg_10]; this
0x18001d376  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x18001d37b  mov     rbx, [rsp+28h+lpMem]
0x18001d380  test    rbx, rbx
0x18001d383  jz      short loc_18001D3A5
0x18001d385  or      eax, 0FFFFFFFFh
0x18001d388  lock xadd [rbx+18h], eax
0x18001d38d  sub     eax, 1
0x18001d390  jnz     short loc_18001D3C5
0x18001d392  nop
0x18001d393  call    WINRT_IMPL_GetProcessHeap
0x18001d398  mov     rcx, rax; hHeap
0x18001d39b  mov     r8, rbx; lpMem
0x18001d39e  xor     edx, edx; dwFlags
0x18001d3a0  call    WINRT_IMPL_HeapFree
0x18001d3a5  mov     rax, [rsp+28h+arg_10]
0x18001d3aa  test    rax, rax
0x18001d3ad  jz      short loc_18001D3B6
0x18001d3af  mov     [rdi], rax
0x18001d3b2  mov     al, 1
0x18001d3b4  jmp     short loc_18001D3BA
0x18001d3b6  jmp     short loc_18001D3BA
0x18001d3b8  xor     al, al
0x18001d3ba  mov     rbx, [rsp+28h+arg_0]
0x18001d3bf  add     rsp, 20h
0x18001d3c3  pop     rdi
0x18001d3c4  retn
0x18001d3c5  test    eax, eax
0x18001d3c7  jns     short loc_18001D3A5
0x18001d3c9  call    cs:__imp_abort
```
