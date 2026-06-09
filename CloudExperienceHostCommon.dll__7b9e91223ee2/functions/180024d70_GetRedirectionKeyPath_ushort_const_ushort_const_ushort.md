# GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)

- ea: `0x180024d70`
- end: `0x180024e4c`
- name: `?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z`
- size: `220`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `17`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003af4`
- `0x180004b80`
- `0x180004db0`
- `0x180004edc`
- `0x180022c50`
- `0x180023c4c`
- `0x180024cbc`
- `0x18002583c`
- `0x180026668`
- `0x180026848`
- `0x180048cb8`
- `0x18005880c`
- `0x1800588dc`
- `0x1800589e0`
- `0x180058ab8`
- `0x180058b90`
- `0x180058cb8`

## callees

- `0x1800128a4`
- `0x1800153f8`
- `0x1800231e0`
- `0x180024d70`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180024da1`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180024dd8`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180024da1`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180024dd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024db2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024db2`

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
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
  }
  if ( *a3 )
    return 0;
  v10 = -1;
  do
    ++v10;
  while ( a2[v10] );
  v11 = _AllocStringWorker<CTCoAllocPolicy>(v7, v6, a2);
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
0x180024d70  mov     r11, rsp
0x180024d73  mov     [r11+8], rbx
0x180024d77  mov     [r11+10h], rbp
0x180024d7b  push    rsi
0x180024d7c  push    rdi
0x180024d7d  push    r14
0x180024d7f  sub     rsp, 30h
0x180024d83  xor     r14d, r14d
0x180024d86  lea     rax, [r11+18h]
0x180024d8a  xor     r9d, r9d
0x180024d8d  mov     [r8], r14
0x180024d90  mov     [r11+18h], r14d
0x180024d94  mov     rdi, r8
0x180024d97  mov     [r11-28h], rax
0x180024d9b  mov     rsi, rdx
0x180024d9e  mov     rbp, rcx
0x180024da1  call    cs:__imp_GetPersistedRegistryLocationW
0x180024da7  cmp     eax, 0EAh
0x180024dac  jnz     short loc_180024DF4
0x180024dae  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x180024db2  call    cs:__imp_CoTaskMemAlloc
0x180024db8  mov     [rsp+48h+arg_18], rax
0x180024dbd  mov     rbx, rax
0x180024dc0  test    rax, rax
0x180024dc3  jz      short loc_180024DEA
0x180024dc5  mov     r9d, dword ptr [rsp+48h+cb]
0x180024dca  mov     r8, rax
0x180024dcd  mov     rdx, rsi
0x180024dd0  mov     qword ptr [rsp+48h+var_28], r14; int
0x180024dd5  mov     rcx, rbp
0x180024dd8  call    cs:__imp_GetPersistedRegistryLocationW
0x180024dde  test    eax, eax
0x180024de0  jnz     short loc_180024DEA
0x180024de2  mov     [rsp+48h+arg_18], r14
0x180024de7  mov     [rdi], rbx
0x180024dea  lea     rcx, [rsp+48h+arg_18]
0x180024def  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180024df4  cmp     [rdi], r14
0x180024df7  jnz     short loc_180024E37
0x180024df9  or      r9, 0FFFFFFFFFFFFFFFFh
0x180024dfd  inc     r9
0x180024e00  cmp     [rsi+r9*2], r14w
0x180024e05  jnz     short loc_180024DFD
0x180024e07  mov     r8, rsi
0x180024e0a  mov     [rsp+48h+var_20], rdi
0x180024e0f  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180024e14  mov     ebx, eax
0x180024e16  test    eax, eax
0x180024e18  jns     short loc_180024E37
0x180024e1a  mov     rcx, [rsp+48h]; this
0x180024e1f  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\shell\\inc\\OobeR"...
0x180024e26  mov     r9d, eax; char *
0x180024e29  mov     edx, 2Eh ; '.'; void *
0x180024e2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024e33  mov     eax, ebx
0x180024e35  jmp     short loc_180024E39
0x180024e37  xor     eax, eax
0x180024e39  mov     rbx, [rsp+48h+arg_0]
0x180024e3e  mov     rbp, [rsp+48h+arg_8]
0x180024e43  add     rsp, 30h
0x180024e47  pop     r14
0x180024e49  pop     rdi
0x180024e4a  pop     rsi
0x180024e4b  retn
```
