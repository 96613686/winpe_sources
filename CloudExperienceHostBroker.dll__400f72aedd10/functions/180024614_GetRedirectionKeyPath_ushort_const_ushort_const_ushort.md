# GetRedirectionKeyPath(ushort const *,ushort const *,ushort * *)

- ea: `0x180024614`
- end: `0x1800246f0`
- name: `?GetRedirectionKeyPath@@YAJPEBG0PEAPEAG@Z`
- size: `220`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007278`
- `0x180007f14`
- `0x180008038`
- `0x1800201bc`
- `0x180024dd4`

## callees

- `0x180008344`
- `0x180012408`
- `0x180020f04`
- `0x180024614`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180024645`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002467c`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180024645`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x18002467c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024656`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
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
0x180024614  mov     r11, rsp
0x180024617  mov     [r11+8], rbx
0x18002461b  mov     [r11+10h], rbp
0x18002461f  push    rsi
0x180024620  push    rdi
0x180024621  push    r14
0x180024623  sub     rsp, 30h
0x180024627  xor     r14d, r14d
0x18002462a  lea     rax, [r11+18h]
0x18002462e  xor     r9d, r9d
0x180024631  mov     [r8], r14
0x180024634  mov     [r11+18h], r14d
0x180024638  mov     rdi, r8
0x18002463b  mov     [r11-28h], rax
0x18002463f  mov     rsi, rdx
0x180024642  mov     rbp, rcx
0x180024645  call    cs:__imp_GetPersistedRegistryLocationW
0x18002464b  cmp     eax, 0EAh
0x180024650  jnz     short loc_180024698
0x180024652  mov     ecx, dword ptr [rsp+48h+cb]; cb
0x180024656  call    cs:__imp_CoTaskMemAlloc
0x18002465c  mov     [rsp+48h+arg_18], rax
0x180024661  mov     rbx, rax
0x180024664  test    rax, rax
0x180024667  jz      short loc_18002468E
0x180024669  mov     r9d, dword ptr [rsp+48h+cb]
0x18002466e  mov     r8, rax
0x180024671  mov     rdx, rsi
0x180024674  mov     qword ptr [rsp+48h+var_28], r14; int
0x180024679  mov     rcx, rbp
0x18002467c  call    cs:__imp_GetPersistedRegistryLocationW
0x180024682  test    eax, eax
0x180024684  jnz     short loc_18002468E
0x180024686  mov     [rsp+48h+arg_18], r14
0x18002468b  mov     [rdi], rbx
0x18002468e  lea     rcx, [rsp+48h+arg_18]
0x180024693  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180024698  cmp     [rdi], r14
0x18002469b  jnz     short loc_1800246DB
0x18002469d  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800246a1  inc     r9
0x1800246a4  cmp     [rsi+r9*2], r14w
0x1800246a9  jnz     short loc_1800246A1
0x1800246ab  mov     r8, rsi
0x1800246ae  mov     [rsp+48h+var_20], rdi
0x1800246b3  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800246b8  mov     ebx, eax
0x1800246ba  test    eax, eax
0x1800246bc  jns     short loc_1800246DB
0x1800246be  mov     rcx, [rsp+48h]; this
0x1800246c3  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\OobeR"...
0x1800246ca  mov     r9d, eax; char *
0x1800246cd  mov     edx, 2Eh ; '.'; void *
0x1800246d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800246d7  mov     eax, ebx
0x1800246d9  jmp     short loc_1800246DD
0x1800246db  xor     eax, eax
0x1800246dd  mov     rbx, [rsp+48h+arg_0]
0x1800246e2  mov     rbp, [rsp+48h+arg_8]
0x1800246e7  add     rsp, 30h
0x1800246eb  pop     r14
0x1800246ed  pop     rdi
0x1800246ee  pop     rsi
0x1800246ef  retn
```
