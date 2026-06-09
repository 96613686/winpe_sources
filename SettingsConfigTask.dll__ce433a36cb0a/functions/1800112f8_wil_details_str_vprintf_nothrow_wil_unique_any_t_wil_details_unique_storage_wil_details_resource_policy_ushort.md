# wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,char * &)

- ea: `0x1800112f8`
- end: `0x180011418`
- name: `??$str_vprintf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBGAEAPEAD@Z`
- size: `288`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, va_list *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800112c0`

## callees

- `0x180002c84`
- `0x18000972c`
- `0x180010248`
- `0x1800112f8`
- `0x180012940`
- `0x180012dd0`
- `0x18001bee8`

## string_xrefs

- `0x1800113f1`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        __int64 a1,
        const wchar_t *a2,
        va_list *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rdx
  const char *v8; // r9
  _QWORD *v9; // rax
  STRSAFE_LPWSTR v10; // rsi
  HRESULT v11; // ebx
  __int64 v12; // rdx
  size_t v13; // rdi
  int argList; // [rsp+20h] [rbp-28h]
  va_list argLista; // [rsp+20h] [rbp-28h]
  size_t pcchNewDestLength[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]
  STRSAFE_LPWSTR pszDest; // [rsp+98h] [rbp+50h] BYREF

  v6 = vscwprintf(a2, *a3);
  pszDest = 0;
  v9 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         pcchNewDestLength,
         v7,
         v6,
         v8);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &pszDest,
    v9);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(pcchNewDestLength);
  v10 = pszDest;
  if ( !pszDest )
  {
    v11 = -2147024882;
    v12 = 1997;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      (const char *)(unsigned int)v11,
      argList);
    goto LABEL_13;
  }
  v13 = v6 + 1;
  if ( !v13 )
  {
    v11 = -2147024809;
    goto LABEL_11;
  }
  if ( v13 > 0x7FFFFFFF )
  {
    v11 = -2147024809;
    *pszDest = 0;
LABEL_11:
    v12 = 2001;
    goto LABEL_12;
  }
  argLista = *a3;
  pcchNewDestLength[0] = 0;
  v11 = StringVPrintfWorkerW_0(pszDest, v13, pcchNewDestLength, a2, argLista);
  if ( v11 < 0 )
  {
    if ( (v13 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
      *v10 = 0;
    goto LABEL_11;
  }
  pcchNewDestLength[0] = (size_t)v10;
  pszDest = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    a1,
    pcchNewDestLength);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(pcchNewDestLength);
  v11 = 0;
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszDest);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800112f8  push    rbp
0x1800112fa  push    rbx
0x1800112fb  push    rsi
0x1800112fc  push    rdi
0x1800112fd  push    r14
0x1800112ff  push    r15
0x180011301  mov     rbp, rsp
0x180011304  sub     rsp, 48h
0x180011308  mov     r15, rdx
0x18001130b  mov     r14, rcx
0x18001130e  mov     rdx, [r8]; ArgList
0x180011311  mov     rcx, r15; Format
0x180011314  mov     rbx, r8
0x180011317  call    _vscwprintf
0x18001131c  movsxd  rdi, eax
0x18001131f  lea     rcx, [rbp+pcchNewDestLength]
0x180011323  mov     r8, rdi
0x180011326  mov     [rbp+pszDest], 0
0x18001132e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180011333  mov     rdx, rax
0x180011336  lea     rcx, [rbp+pszDest]
0x18001133a  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18001133f  lea     rcx, [rbp+pcchNewDestLength]
0x180011343  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180011348  mov     rsi, [rbp+pszDest]
0x18001134c  test    rsi, rsi
0x18001134f  jnz     short loc_180011360
0x180011351  mov     ebx, 8007000Eh
0x180011356  mov     edx, 7CDh
0x18001135b  jmp     loc_1800113ED
0x180011360  add     rdi, 1
0x180011364  jz      short loc_1800113D9
0x180011366  cmp     rdi, 7FFFFFFFh
0x18001136d  jbe     short loc_180011376
0x18001136f  mov     ebx, 80070057h
0x180011374  jmp     short loc_1800113E3
0x180011376  mov     rax, [rbx]
0x180011379  lea     r8, [rbp+pcchNewDestLength]; pcchNewDestLength
0x18001137d  mov     r9, r15; pszFormat
0x180011380  mov     [rsp+48h+argList], rax; argList
0x180011385  mov     rdx, rdi; cchDest
0x180011388  mov     [rbp+pcchNewDestLength], 0
0x180011390  mov     rcx, rsi; pszDest
0x180011393  call    StringVPrintfWorkerW_0
0x180011398  mov     ebx, eax
0x18001139a  test    eax, eax
0x18001139c  jns     short loc_1800113B4
0x18001139e  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800113a8  test    rax, rdi
0x1800113ab  jbe     short loc_1800113E8
0x1800113ad  xor     eax, eax
0x1800113af  mov     [rsi], ax
0x1800113b2  jmp     short loc_1800113E8
0x1800113b4  lea     rdx, [rbp+pcchNewDestLength]
0x1800113b8  mov     [rbp+pcchNewDestLength], rsi
0x1800113bc  mov     rcx, r14
0x1800113bf  mov     [rbp+pszDest], 0
0x1800113c7  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800113cc  lea     rcx, [rbp+pcchNewDestLength]
0x1800113d0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800113d5  xor     ebx, ebx
0x1800113d7  jmp     short loc_180011400
0x1800113d9  mov     ebx, 80070057h
0x1800113de  test    rdi, rdi
0x1800113e1  jz      short loc_1800113E8
0x1800113e3  xor     ecx, ecx
0x1800113e5  mov     [rsi], cx
0x1800113e8  mov     edx, 7D1h; void *
0x1800113ed  mov     rcx, [rbp+30h]; this
0x1800113f1  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800113f8  mov     r9d, ebx; char *
0x1800113fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011400  lea     rcx, [rbp+pszDest]
0x180011404  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180011409  mov     eax, ebx
0x18001140b  add     rsp, 48h
0x18001140f  pop     r15
0x180011411  pop     r14
0x180011413  pop     rdi
0x180011414  pop     rsi
0x180011415  pop     rbx
0x180011416  pop     rbp
0x180011417  retn
```
