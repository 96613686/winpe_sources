# wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,char * &)

- ea: `0x18001012c`
- end: `0x180010271`
- name: `??$str_vprintf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBGAEAPEAD@Z`
- size: `325`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, va_list *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800100b8`

## callees

- `0x180003740`
- `0x180003794`
- `0x180007f3c`
- `0x18000b524`
- `0x180010058`
- `0x18001012c`
- `0x180010c6c`

## string_xrefs

- `0x180010246`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_vprintf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        __int64 a1,
        const wchar_t *a2,
        va_list *a3)
{
  unsigned __int64 v6; // rbx
  __int64 v7; // rdx
  const char *v8; // r9
  _QWORD *v9; // rax
  wchar_t *v10; // rdi
  unsigned int v11; // ebx
  __int64 v12; // rdx
  unsigned __int64 v13; // rsi
  int v14; // eax
  int v16[18]; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  wchar_t *Buffer; // [rsp+88h] [rbp+20h] BYREF

  v6 = vscwprintf(a2, *a3);
  Buffer = 0;
  v9 = wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
         v16,
         v7,
         v6,
         v8);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &Buffer,
    v9);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v16);
  v10 = Buffer;
  if ( !Buffer )
  {
    v11 = -2147024882;
    v12 = 1997;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)v11,
      v16[0]);
    goto LABEL_17;
  }
  v13 = v6 + 1;
  if ( v6 == -1 )
  {
    v11 = -2147024809;
    if ( !v13 )
    {
LABEL_15:
      v12 = 2001;
      goto LABEL_16;
    }
LABEL_14:
    *Buffer = 0;
    goto LABEL_15;
  }
  if ( v13 > 0x7FFFFFFF )
  {
    v11 = -2147024809;
    goto LABEL_14;
  }
  v14 = vsnwprintf(Buffer, v6, a2, *a3);
  if ( v14 < 0 || v14 > v6 )
  {
    v10[v6] = 0;
    v11 = -2147024774;
    if ( (v13 & 0x7FFFFFFFFFFFFFFFLL) != 0 )
      *v10 = 0;
    goto LABEL_15;
  }
  if ( v14 == v6 )
    v10[v6] = 0;
  *(_QWORD *)v16 = v10;
  Buffer = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    a1,
    v16);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v16);
  v11 = 0;
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Buffer);
  return v11;
}

```

## disassembly

```asm
0x18001012c  push    rbx
0x18001012e  push    rbp
0x18001012f  push    rsi
0x180010130  push    rdi
0x180010131  push    r14
0x180010133  push    r15
0x180010135  sub     rsp, 38h
0x180010139  mov     rbp, rdx
0x18001013c  mov     r15, rcx
0x18001013f  mov     rdx, [r8]; ArgList
0x180010142  mov     rcx, rbp; Format
0x180010145  mov     r14, r8
0x180010148  call    _vscwprintf
0x18001014d  movsxd  rbx, eax
0x180010150  lea     rcx, [rsp+68h+var_48]
0x180010155  mov     r8, rbx
0x180010158  mov     [rsp+68h+Buffer], 0
0x180010164  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180010169  mov     rdx, rax
0x18001016c  lea     rcx, [rsp+68h+Buffer]
0x180010174  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180010179  lea     rcx, [rsp+68h+var_48]
0x18001017e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180010183  mov     rdi, [rsp+68h+Buffer]
0x18001018b  test    rdi, rdi
0x18001018e  jnz     short loc_18001019F
0x180010190  mov     ebx, 8007000Eh
0x180010195  mov     edx, 7CDh
0x18001019a  jmp     loc_180010241
0x18001019f  lea     rsi, [rbx+1]
0x1800101a3  test    rsi, rsi
0x1800101a6  jz      loc_18001022D
0x1800101ac  cmp     rsi, 7FFFFFFFh
0x1800101b3  jbe     short loc_1800101BC
0x1800101b5  mov     ebx, 80070057h
0x1800101ba  jmp     short loc_180010237
0x1800101bc  mov     r9, [r14]; Args
0x1800101bf  mov     r8, rbp; Format
0x1800101c2  mov     rdx, rbx; BufferCount
0x1800101c5  mov     rcx, rdi; Buffer
0x1800101c8  call    _vsnwprintf
0x1800101cd  test    eax, eax
0x1800101cf  js      short loc_18001020C
0x1800101d1  cdqe
0x1800101d3  cmp     rax, rbx
0x1800101d6  ja      short loc_18001020C
0x1800101d8  jnz     short loc_1800101E0
0x1800101da  xor     eax, eax
0x1800101dc  mov     [rdi+rbx*2], ax
0x1800101e0  lea     rdx, [rsp+68h+var_48]
0x1800101e5  mov     qword ptr [rsp+68h+var_48], rdi
0x1800101ea  mov     rcx, r15
0x1800101ed  mov     [rsp+68h+Buffer], 0
0x1800101f9  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800101fe  lea     rcx, [rsp+68h+var_48]
0x180010203  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180010208  xor     ebx, ebx
0x18001020a  jmp     short loc_180010255
0x18001020c  xor     eax, eax
0x18001020e  mov     [rdi+rbx*2], ax
0x180010212  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001021c  mov     ebx, 8007007Ah
0x180010221  test    rax, rsi
0x180010224  jbe     short loc_18001023C
0x180010226  xor     eax, eax
0x180010228  mov     [rdi], ax
0x18001022b  jmp     short loc_18001023C
0x18001022d  mov     ebx, 80070057h
0x180010232  test    rsi, rsi
0x180010235  jz      short loc_18001023C
0x180010237  xor     ecx, ecx
0x180010239  mov     [rdi], cx
0x18001023c  mov     edx, 7D1h; void *
0x180010241  mov     rcx, [rsp+68h]; this
0x180010246  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001024d  mov     r9d, ebx; char *
0x180010250  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010255  lea     rcx, [rsp+68h+Buffer]
0x18001025d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180010262  mov     eax, ebx
0x180010264  add     rsp, 38h
0x180010268  pop     r15
0x18001026a  pop     r14
0x18001026c  pop     rdi
0x18001026d  pop     rsi
0x18001026e  pop     rbp
0x18001026f  pop     rbx
0x180010270  retn
```
