# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18007541c`
- end: `0x1800754ba`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800753a8`

## callees

- `0x18007541c`
- `0x18007695a`
- `0x1800769f4`
- `0x18008251f`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180075491`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180075491`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007545f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007545f`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1)
{
  const wchar_t *v2; // rax
  __int64 v3; // rdx
  size_t v4; // rbx
  size_t v5; // rbp
  char *v6; // rax
  char *v7; // rdi

  v2 = L"3ed497c5-2c9c-41cc-9288-63a5564e901d";
  v3 = 0x7FFFFFFF;
  do
  {
    if ( !*v2 )
      break;
    ++v2;
    --v3;
  }
  while ( v3 );
  v4 = 2 * (v2 - L"3ed497c5-2c9c-41cc-9288-63a5564e901d");
  v5 = v4 + 2;
  v6 = (char *)CoTaskMemAlloc(v4 + 2);
  v7 = v6;
  if ( v6 )
  {
    if ( v4 )
    {
      if ( v5 < v4 )
      {
        memset_0(v6, 0, v5);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v6, L"3ed497c5-2c9c-41cc-9288-63a5564e901d", v4);
      }
    }
    *(_WORD *)&v7[v4] = 0;
  }
  *a1 = v7;
  return a1;
}

```

## disassembly

```asm
0x18007541c  push    rbx
0x18007541e  push    rbp
0x18007541f  push    rsi
0x180075420  push    rdi
0x180075421  push    r14
0x180075423  push    r15
0x180075425  sub     rsp, 28h
0x180075429  lea     r15, a3ed497c52c9c41; "3ed497c5-2c9c-41cc-9288-63a5564e901d"
0x180075430  mov     rsi, rcx
0x180075433  mov     rax, r15
0x180075436  mov     edx, 7FFFFFFFh
0x18007543b  xor     r14d, r14d
0x18007543e  cmp     [rax], r14w
0x180075442  jz      short loc_18007544E
0x180075444  add     rax, 2
0x180075448  sub     rdx, 1
0x18007544c  jnz     short loc_18007543E
0x18007544e  sub     rax, r15
0x180075451  sar     rax, 1
0x180075454  lea     rbx, [rax+rax]
0x180075458  lea     rbp, [rbx+2]
0x18007545c  mov     rcx, rbp; cb
0x18007545f  call    cs:__imp_CoTaskMemAlloc
0x180075465  mov     rdi, rax
0x180075468  test    rax, rax
0x18007546b  jz      short loc_1800754A7
0x18007546d  test    rbx, rbx
0x180075470  jz      short loc_1800754A2
0x180075472  mov     rcx, rax; void *
0x180075475  cmp     rbp, rbx
0x180075478  jb      short loc_180075487
0x18007547a  mov     r8, rbx; Size
0x18007547d  mov     rdx, r15; Src
0x180075480  call    memcpy_0
0x180075485  jmp     short loc_1800754A2
0x180075487  mov     r8, rbp; Size
0x18007548a  xor     edx, edx; Val
0x18007548c  call    memset_0
0x180075491  call    cs:__imp__o__errno
0x180075497  mov     dword ptr [rax], 22h ; '"'
0x18007549d  call    _invalid_parameter_noinfo
0x1800754a2  mov     [rbx+rdi], r14w
0x1800754a7  mov     [rsi], rdi
0x1800754aa  mov     rax, rsi
0x1800754ad  add     rsp, 28h
0x1800754b1  pop     r15
0x1800754b3  pop     r14
0x1800754b5  pop     rdi
0x1800754b6  pop     rsi
0x1800754b7  pop     rbp
0x1800754b8  pop     rbx
0x1800754b9  retn
```
