# GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)

- ea: `0x180025b8c`
- end: `0x180025c68`
- name: `?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z`
- size: `220`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `16`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800218b8`
- `0x18002197c`
- `0x180021a84`
- `0x180021b8c`
- `0x180021c8c`
- `0x180022690`
- `0x1800227c8`
- `0x180022900`
- `0x180023b4c`
- `0x18002586c`
- `0x1800261ac`
- `0x180026ab0`
- `0x180026c00`
- `0x1800331a8`
- `0x1800332ac`
- `0x180033374`

## callees

- `0x180007134`
- `0x18000a5c8`
- `0x180022a84`
- `0x180025b8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025bce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025bce`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180025bbd`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180025bf4`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180025bbd`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180025bf4`

## pseudocode

```c
__int64 __fastcall GetRedirectionKeyPath(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbx
  __int64 v10; // r9
  int v11; // eax
  unsigned int v12; // ebx
  SIZE_T *p_cb; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  SIZE_T cb; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int16 *v17; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 0;
  LODWORD(cb) = 0;
  p_cb = &cb;
  if ( (unsigned int)GetPersistedRegistryLocationW(a1, a2, a3, 0) == 234 )
  {
    v8 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)cb);
    v17 = v8;
    v9 = v8;
    if ( v8 )
    {
      LODWORD(p_cb) = 0;
      if ( !(unsigned int)GetPersistedRegistryLocationW(a1, a2, v8, (unsigned int)cb) )
      {
        v17 = 0;
        *a3 = v9;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v17);
  }
  if ( *a3 )
    return 0;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  v11 = _AllocStringWorker<CTCoAllocPolicy>(v7, v6, a2, v10);
  v12 = v11;
  if ( v11 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2E,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\OobeRedirectionKeyHelper.h",
    (const char *)(unsigned int)v11,
    (int)p_cb);
  return v12;
}

```

## disassembly

```asm
0x180025b8c  mov     r11, rsp
0x180025b8f  mov     [r11+8], rbx
0x180025b93  mov     [r11+10h], rbp
0x180025b97  push    rsi
0x180025b98  push    rdi
0x180025b99  push    r14
0x180025b9b  sub     rsp, 30h
0x180025b9f  xor     r14d, r14d
0x180025ba2  lea     rax, [r11+18h]
0x180025ba6  xor     r9d, r9d
0x180025ba9  mov     [r8], r14
0x180025bac  mov     [r11+18h], r14d
0x180025bb0  mov     rdi, r8
0x180025bb3  mov     [r11-28h], rax
0x180025bb7  mov     rsi, rdx
0x180025bba  mov     rbp, rcx
0x180025bbd  call    cs:__imp_GetPersistedRegistryLocationW
0x180025bc3  cmp     eax, 0EAh
0x180025bc8  jnz     short loc_180025C10
0x180025bca  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x180025bce  call    cs:__imp_CoTaskMemAlloc
0x180025bd4  mov     [rsp+48h+arg_18], rax
0x180025bd9  mov     rbx, rax
0x180025bdc  test    rax, rax
0x180025bdf  jz      short loc_180025C06
0x180025be1  mov     r9d, dword ptr [rsp+48h+cb]
0x180025be6  mov     r8, rax
0x180025be9  mov     rdx, rsi
0x180025bec  mov     qword ptr [rsp+48h+var_28], r14; int
0x180025bf1  mov     rcx, rbp
0x180025bf4  call    cs:__imp_GetPersistedRegistryLocationW
0x180025bfa  test    eax, eax
0x180025bfc  jnz     short loc_180025C06
0x180025bfe  mov     [rsp+48h+arg_18], r14
0x180025c03  mov     [rdi], rbx
0x180025c06  lea     rcx, [rsp+48h+arg_18]
0x180025c0b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180025c10  cmp     [rdi], r14
0x180025c13  jnz     short loc_180025C53
0x180025c15  or      r9, 0FFFFFFFFFFFFFFFFh
0x180025c19  inc     r9
0x180025c1c  cmp     [rsi+r9*2], r14w
0x180025c21  jnz     short loc_180025C19
0x180025c23  mov     r8, rsi
0x180025c26  mov     [rsp+48h+var_20], rdi
0x180025c2b  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180025c30  mov     ebx, eax
0x180025c32  test    eax, eax
0x180025c34  jns     short loc_180025C53
0x180025c36  mov     rcx, [rsp+48h]; this
0x180025c3b  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\OobeR"...
0x180025c42  mov     r9d, eax; char *
0x180025c45  mov     edx, 2Eh ; '.'; void *
0x180025c4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025c4f  mov     eax, ebx
0x180025c51  jmp     short loc_180025C55
0x180025c53  xor     eax, eax
0x180025c55  mov     rbx, [rsp+48h+arg_0]
0x180025c5a  mov     rbp, [rsp+48h+arg_8]
0x180025c5f  add     rsp, 30h
0x180025c63  pop     r14
0x180025c65  pop     rdi
0x180025c66  pop     rsi
0x180025c67  retn
```
