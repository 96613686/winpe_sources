# StateRepoHelpers::ExplorerCommandVerb::ExplorerCommandVerb(ushort const *,ushort const *,_GUID)

- ea: `0x18000606c`
- end: `0x180006184`
- name: `??0ExplorerCommandVerb@StateRepoHelpers@@QEAA@PEBG0U_GUID@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(StateRepoHelpers::ExplorerCommandVerb *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001cda4`

## callees

- `0x18000606c`
- `0x1800069b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000615d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000617b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000615d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000617b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000614a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006168`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000614a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006168`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006112`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006155`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006173`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800060d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006112`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006155`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006173`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
StateRepoHelpers::ExplorerCommandVerb *__fastcall StateRepoHelpers::ExplorerCommandVerb::ExplorerCommandVerb(
        void **this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _GUID *a4)
{
  void **v7; // rsi
  void *v8; // r14
  void *v9; // rbp
  void *v10; // rcx
  void *v11; // r14
  void *v12; // rbp
  void *v13; // rcx
  DWORD LastError; // ebx
  DWORD v16; // ebx
  void *v17; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v18[6]; // [rsp+28h] [rbp-30h] BYREF

  *this = 0;
  v7 = this + 1;
  this[1] = 0;
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v17,
    a2);
  if ( this == &v17 )
  {
    v10 = v17;
  }
  else
  {
    v8 = v17;
    v9 = *this;
    if ( *this )
    {
      LastError = GetLastError();
      CoTaskMemFree(v9);
      SetLastError(LastError);
    }
    *this = v8;
    v10 = 0;
    v17 = 0;
  }
  if ( v10 )
    CoTaskMemFree(v10);
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    v18,
    a3);
  if ( v7 == v18 )
  {
    v13 = (void *)v18[0];
  }
  else
  {
    v11 = (void *)v18[0];
    v12 = *v7;
    if ( *v7 )
    {
      v16 = GetLastError();
      CoTaskMemFree(v12);
      SetLastError(v16);
    }
    *v7 = v11;
    v13 = 0;
    v18[0] = 0;
  }
  if ( v13 )
    CoTaskMemFree(v13);
  *((struct _GUID *)this + 1) = *a4;
  return (StateRepoHelpers::ExplorerCommandVerb *)this;
}

```

## disassembly

```asm
0x18000606c  mov     rax, rsp
0x18000606f  mov     [rax+10h], rbx
0x180006073  mov     [rax+18h], rbp
0x180006077  mov     [rax+8], rcx
0x18000607b  push    rsi
0x18000607c  push    rdi
0x18000607d  push    r12
0x18000607f  push    r14
0x180006081  push    r15
0x180006083  sub     rsp, 30h
0x180006087  mov     r12, r9
0x18000608a  mov     r15, r8
0x18000608d  mov     rdi, rcx
0x180006090  mov     qword ptr [rcx], 0
0x180006097  lea     rsi, [rcx+8]
0x18000609b  mov     qword ptr [rsi], 0
0x1800060a2  lea     rcx, [rax-38h]
0x1800060a6  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800060ab  lea     rax, [rsp+58h+var_38]
0x1800060b0  cmp     rdi, rax
0x1800060b3  jz      loc_18000613C
0x1800060b9  mov     r14, [rsp+58h+var_38]
0x1800060be  mov     rbp, [rdi]
0x1800060c1  test    rbp, rbp
0x1800060c4  jnz     loc_18000614A
0x1800060ca  mov     [rdi], r14
0x1800060cd  xor     ecx, ecx; pv
0x1800060cf  mov     [rsp+58h+var_38], rcx
0x1800060d4  test    rcx, rcx
0x1800060d7  jz      short loc_1800060DF
0x1800060d9  call    cs:__imp_CoTaskMemFree
0x1800060df  mov     rdx, r15
0x1800060e2  lea     rcx, [rsp+58h+var_30]
0x1800060e7  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800060ec  lea     rax, [rsp+58h+var_30]
0x1800060f1  cmp     rsi, rax
0x1800060f4  jz      short loc_180006143
0x1800060f6  mov     r14, [rsp+58h+var_30]
0x1800060fb  mov     rbp, [rsi]
0x1800060fe  test    rbp, rbp
0x180006101  jnz     short loc_180006168
0x180006103  mov     [rsi], r14
0x180006106  xor     ecx, ecx; pv
0x180006108  mov     [rsp+58h+var_30], rcx
0x18000610d  test    rcx, rcx
0x180006110  jz      short loc_180006118
0x180006112  call    cs:__imp_CoTaskMemFree
0x180006118  movaps  xmm0, xmmword ptr [r12]
0x18000611d  movdqu  xmmword ptr [rdi+10h], xmm0
0x180006122  mov     rax, rdi
0x180006125  mov     rbx, [rsp+58h+arg_8]
0x18000612a  mov     rbp, [rsp+58h+arg_10]
0x18000612f  add     rsp, 30h
0x180006133  pop     r15
0x180006135  pop     r14
0x180006137  pop     r12
0x180006139  pop     rdi
0x18000613a  pop     rsi
0x18000613b  retn
0x18000613c  mov     rcx, [rsp+58h+var_38]
0x180006141  jmp     short loc_1800060D4
0x180006143  mov     rcx, [rsp+58h+var_30]
0x180006148  jmp     short loc_18000610D
0x18000614a  call    cs:__imp_GetLastError
0x180006150  mov     ebx, eax
0x180006152  mov     rcx, rbp; pv
0x180006155  call    cs:__imp_CoTaskMemFree
0x18000615b  mov     ecx, ebx; dwErrCode
0x18000615d  call    cs:__imp_SetLastError
0x180006163  jmp     loc_1800060CA
0x180006168  call    cs:__imp_GetLastError
0x18000616e  mov     ebx, eax
0x180006170  mov     rcx, rbp; pv
0x180006173  call    cs:__imp_CoTaskMemFree
0x180006179  mov     ecx, ebx; dwErrCode
0x18000617b  call    cs:__imp_SetLastError
0x180006181  jmp     short loc_180006103
```
