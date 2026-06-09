# wistd::__function::__func<`wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)'::`2'::_lambda_1_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x180017020`
- end: `0x1800170ce`
- name: `??R?$__func@V_lambda_1_@?1???$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEAXPEAUHINSTANCE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@@Z@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `174`
- prototype: `__int64 __fastcall(__int64, WCHAR **, unsigned __int64 *, __int64 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180009524`
- `0x180017020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180017077`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180017077`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180017052`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180017052`

## string_xrefs

- `0x18001709d`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall wistd::__function::Z::$$A6AJPEAG_KPEA_K::Z::__func<`wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>'::`2'::_lambda_1_,AJPEAXPEAUHINSTANCE__,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>> &>::operator()(
        __int64 a1,
        WCHAR **a2,
        unsigned __int64 *a3,
        __int64 **a4)
{
  __int64 *v4; // rdi
  unsigned __int64 v5; // rbx
  WCHAR *v6; // rdx
  void *v7; // r10
  HMODULE *v8; // rax
  DWORD ModuleFileName; // eax
  const char *v10; // r9
  __int64 v11; // r8
  bool v12; // cl
  char v13; // dl
  DWORD ModuleFileNameW; // eax
  __int64 result; // rax
  __int64 v16; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a4;
  v5 = *a3;
  v6 = *a2;
  v7 = **(void ***)(a1 + 8);
  v8 = *(HMODULE **)(a1 + 16);
  if ( v7 )
  {
    ModuleFileName = K32GetModuleFileNameExW(v7, *v8, v6, v5);
    v11 = ModuleFileName;
    if ( !ModuleFileName )
    {
      v12 = 1;
LABEL_4:
      v13 = 0;
      goto LABEL_11;
    }
    v12 = 0;
    if ( ModuleFileName >= v5 - 1 )
      goto LABEL_4;
    goto LABEL_6;
  }
  ModuleFileNameW = GetModuleFileNameW(*v8, v6, v5);
  v11 = ModuleFileNameW;
  if ( ModuleFileNameW && ModuleFileNameW < v5 )
  {
    v12 = 0;
LABEL_6:
    v13 = 1;
    goto LABEL_11;
  }
  v13 = 0;
  v12 = ModuleFileNameW == 0;
LABEL_11:
  if ( v12 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x215,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
             v10);
  v16 = v11 + 1;
  if ( !v13 )
    v16 = 2 * v5;
  result = 0;
  *v4 = v16;
  return result;
}

```

## disassembly

```asm
0x180017020  mov     [rsp+arg_0], rbx
0x180017025  push    rdi
0x180017026  sub     rsp, 20h
0x18001702a  mov     rax, [rcx+8]
0x18001702e  mov     rdi, [r9]
0x180017031  mov     rbx, [r8]
0x180017034  mov     rdx, [rdx]; lpFilename
0x180017037  mov     r10, [rax]
0x18001703a  mov     rax, [rcx+10h]
0x18001703e  mov     rcx, [rax]; hModule
0x180017041  test    r10, r10
0x180017044  jz      short loc_180017074
0x180017046  mov     r8, rdx; lpFilename
0x180017049  mov     r9d, ebx; nSize
0x18001704c  mov     rdx, rcx; hModule
0x18001704f  mov     rcx, r10; hProcess
0x180017052  call    cs:__imp_K32GetModuleFileNameExW
0x180017058  mov     r8d, eax
0x18001705b  test    eax, eax
0x18001705d  jnz     short loc_180017065
0x18001705f  mov     cl, 1
0x180017061  xor     dl, dl
0x180017063  jmp     short loc_180017094
0x180017065  xor     cl, cl
0x180017067  lea     rax, [rbx-1]
0x18001706b  cmp     r8, rax
0x18001706e  jnb     short loc_180017061
0x180017070  mov     dl, 1
0x180017072  jmp     short loc_180017094
0x180017074  mov     r8d, ebx; nSize
0x180017077  call    cs:__imp_GetModuleFileNameW
0x18001707d  mov     r8d, eax
0x180017080  test    eax, eax
0x180017082  jz      short loc_18001708D
0x180017084  cmp     r8, rbx
0x180017087  jnb     short loc_18001708D
0x180017089  xor     cl, cl
0x18001708b  jmp     short loc_180017070
0x18001708d  xor     dl, dl
0x18001708f  test    eax, eax
0x180017091  setz    cl
0x180017094  test    cl, cl
0x180017096  jz      short loc_1800170B0
0x180017098  mov     rcx, [rsp+28h]; this
0x18001709d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800170a4  mov     edx, 215h; void *
0x1800170a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800170ae  jmp     short loc_1800170C3
0x1800170b0  test    dl, dl
0x1800170b2  lea     rax, [rbx+rbx]
0x1800170b6  lea     rcx, [r8+1]
0x1800170ba  cmovz   rcx, rax
0x1800170be  xor     eax, eax
0x1800170c0  mov     [rdi], rcx
0x1800170c3  mov     rbx, [rsp+28h+arg_0]
0x1800170c8  add     rsp, 20h
0x1800170cc  pop     rdi
0x1800170cd  retn
```
