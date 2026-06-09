# WindowsMidiServicesInternal::JsonStringifyObjectToOutParam(winrt::Windows::Data::Json::JsonObject const &,ushort * *)

- ea: `0x180017584`
- end: `0x180017619`
- name: `?JsonStringifyObjectToOutParam@WindowsMidiServicesInternal@@YA_NAEBUJsonObject@Json@Data@Windows@winrt@@PEAPEAG@Z`
- size: `149`
- prototype: `bool __fastcall(WindowsMidiServicesInternal *__hidden this, const struct winrt::Windows::Data::Json::JsonObject *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180018710`

## callees

- `0x18000509c`
- `0x180005108`
- `0x180017584`
- `0x18001863c`
- `0x18001b9ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017611`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180017611`

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
0x180017584  mov     [rsp+arg_0], rbx
0x180017589  push    rdi
0x18001758a  sub     rsp, 20h
0x18001758e  mov     rdi, rdx
0x180017591  test    rdx, rdx
0x180017594  jnz     short loc_18001759A
0x180017596  xor     al, al
0x180017598  jmp     short loc_180017602
0x18001759a  lea     rdx, [rsp+28h+lpMem]
0x18001759f  call    ?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)
0x1800175a4  mov     rax, [rax]
0x1800175a7  test    rax, rax
0x1800175aa  jz      short loc_1800175B2
0x1800175ac  mov     rdx, [rax+10h]
0x1800175b0  jmp     short loc_1800175B9
0x1800175b2  lea     rdx, S2; unsigned __int16 *
0x1800175b9  lea     rcx, [rsp+28h+arg_10]; this
0x1800175be  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x1800175c3  mov     rbx, [rsp+28h+lpMem]
0x1800175c8  test    rbx, rbx
0x1800175cb  jz      short loc_1800175ED
0x1800175cd  or      eax, 0FFFFFFFFh
0x1800175d0  lock xadd [rbx+18h], eax
0x1800175d5  sub     eax, 1
0x1800175d8  jnz     short loc_18001760D
0x1800175da  nop
0x1800175db  call    WINRT_IMPL_GetProcessHeap
0x1800175e0  mov     rcx, rax; hHeap
0x1800175e3  mov     r8, rbx; lpMem
0x1800175e6  xor     edx, edx; dwFlags
0x1800175e8  call    WINRT_IMPL_HeapFree
0x1800175ed  mov     rax, [rsp+28h+arg_10]
0x1800175f2  test    rax, rax
0x1800175f5  jz      short loc_1800175FE
0x1800175f7  mov     [rdi], rax
0x1800175fa  mov     al, 1
0x1800175fc  jmp     short loc_180017602
0x1800175fe  jmp     short loc_180017602
0x180017600  xor     al, al
0x180017602  mov     rbx, [rsp+28h+arg_0]
0x180017607  add     rsp, 20h
0x18001760b  pop     rdi
0x18001760c  retn
0x18001760d  test    eax, eax
0x18001760f  jns     short loc_1800175ED
0x180017611  call    cs:__imp_abort
```
