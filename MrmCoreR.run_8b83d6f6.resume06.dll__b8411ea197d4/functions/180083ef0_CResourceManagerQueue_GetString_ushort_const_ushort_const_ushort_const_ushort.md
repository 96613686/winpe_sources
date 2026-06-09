# CResourceManagerQueue::GetString(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180083ef0`
- end: `0x18008413f`
- name: `?GetString@CResourceManagerQueue@@UEAAJPEBG00PEAPEAG@Z`
- size: `591`
- prototype: `int(CResourceManagerQueue *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18002c8d0`
- `0x180032980`
- `0x180032ab0`
- `0x180083ef0`
- `0x180084154`
- `0x180084174`
- `0x1800862f0`
- `0x18008a6a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180083fac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008405a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180083fac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008405a`

## string_xrefs

- `0x1800840ca`: `onecoreuap\base\mrt\runtime\com\dllsrv\resourcemanagerqueue.cpp`
- `0x180084103`: `onecoreuap\base\mrt\runtime\com\dllsrv\resourcemanagerqueue.cpp`
- `0x180083f92`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x180084040`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall CResourceManagerQueue::GetString(
        CResourceManagerQueue *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  int String; // eax
  const char *v9; // r9
  unsigned __int64 v10; // rbx
  _WORD *v11; // rax
  unsigned __int16 *v12; // rdi
  unsigned int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // r9
  int v16; // eax
  _WORD *v17; // rax
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v21; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v23[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v24[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( !a2 || !a5 )
  {
    v13 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\resourcemanagerqueue.cpp",
      (const char *)0x80070057LL,
      v19);
    return v13;
  }
  v21 = 0;
  v22 = 0;
  *a5 = 0;
  String = Microsoft::Resources::Runtime::CResourceManagerQueueInternal::GetString(this, a2, a3, a4, v24, 0x104u, &v22);
  v10 = v22;
  if ( String >= 0 )
  {
    if ( v22 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v9);
    v17 = CoTaskMemAlloc(2 * v22 + 2);
    if ( v17 )
    {
      *v17 = 0;
      v17[v10] = 0;
    }
    v23[0] = v17;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &v21,
      v23);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v23);
    v12 = v21;
    if ( !v21 )
    {
      v13 = -2147024882;
      v14 = 51;
      v15 = 2147942414LL;
      goto LABEL_21;
    }
    v16 = StringCchCopyW(v21, v22, v24);
    v13 = v16;
    if ( v16 < 0 )
    {
      v14 = 53;
      goto LABEL_20;
    }
LABEL_22:
    v21 = 0;
    *a5 = v12;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
    return 0;
  }
  if ( v22 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v9);
  v11 = CoTaskMemAlloc(2 * v22 + 2);
  if ( v11 )
  {
    *v11 = 0;
    v11[v10] = 0;
  }
  v23[0] = v11;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    &v21,
    v23);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v23);
  v12 = v21;
  if ( v21 )
  {
    v16 = Microsoft::Resources::Runtime::CResourceManagerQueueInternal::GetString(
            (Microsoft::Resources::Runtime::CResourceManagerQueueInternal *)&v22,
            a2,
            a3,
            a4,
            v21,
            v22,
            &v22);
    v13 = v16;
    if ( v16 < 0 )
    {
      v14 = 45;
LABEL_20:
      v15 = (unsigned int)v16;
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  v13 = -2147024882;
  v14 = 41;
  v15 = 2147942414LL;
LABEL_21:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\resourcemanagerqueue.cpp",
    (const char *)v15,
    v20);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v21);
  return v13;
}

```

## disassembly

```asm
0x180083ef0  push    rbp
0x180083ef2  push    rbx
0x180083ef3  push    rsi
0x180083ef4  push    rdi
0x180083ef5  push    r12
0x180083ef7  push    r14
0x180083ef9  push    r15
0x180083efb  lea     rbp, [rsp-180h]
0x180083f03  sub     rsp, 280h
0x180083f0a  mov     rax, cs:__security_cookie
0x180083f11  xor     rax, rsp
0x180083f14  mov     [rbp+1B0h+var_40], rax
0x180083f1b  mov     rsi, [rbp+1B0h+arg_20]
0x180083f22  mov     r12, r9
0x180083f25  mov     r15, r8
0x180083f28  mov     r14, rdx
0x180083f2b  test    rdx, rdx
0x180083f2e  jz      loc_1800840FC
0x180083f34  test    rsi, rsi
0x180083f37  jz      loc_1800840FC
0x180083f3d  lea     rax, [rsp+2B0h+var_268]
0x180083f42  mov     [rsp+2B0h+var_270], 0
0x180083f4b  mov     [rsp+2B0h+var_280], rax; unsigned __int64 *
0x180083f50  lea     rax, [rsp+2B0h+var_250]
0x180083f55  mov     [rsp+2B0h+var_288], 104h; unsigned __int64
0x180083f5e  mov     [rsp+2B0h+var_290], rax; int
0x180083f63  mov     [rsp+2B0h+var_268], 0
0x180083f6c  mov     qword ptr [rsi], 0
0x180083f73  call    ?GetString@CResourceManagerQueueInternal@Runtime@Resources@Microsoft@@QEAAJPEBG00PEAG_KPEA_K@Z; Microsoft::Resources::Runtime::CResourceManagerQueueInternal::GetString(ushort const *,ushort const *,ushort const *,ushort *,unsigned __int64,unsigned __int64 *)
0x180083f78  mov     rbx, [rsp+2B0h+var_268]
0x180083f7d  test    eax, eax
0x180083f7f  jns     loc_180084033
0x180083f85  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180083f89  jnz     short loc_180083FA4
0x180083f8b  mov     rcx, [rbp+1B8h]; this
0x180083f92  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180083f99  mov     edx, 0F89h; void *
0x180083f9e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180083fa4  lea     rcx, ds:2[rbx*2]; cb
0x180083fac  call    cs:__imp_CoTaskMemAlloc
0x180083fb2  test    rax, rax
0x180083fb5  jz      short loc_180083FC0
0x180083fb7  xor     ecx, ecx
0x180083fb9  mov     [rax], cx
0x180083fbc  mov     [rax+rbx*2], cx
0x180083fc0  lea     rdx, [rsp+2B0h+var_260]
0x180083fc5  mov     [rsp+2B0h+var_260], rax
0x180083fca  lea     rcx, [rsp+2B0h+var_270]
0x180083fcf  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180083fd4  lea     rcx, [rsp+2B0h+var_260]
0x180083fd9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180083fde  mov     rdi, [rsp+2B0h+var_270]
0x180083fe3  test    rdi, rdi
0x180083fe6  jnz     short loc_180083FF8
0x180083fe8  mov     ebx, 8007000Eh
0x180083fed  lea     edx, [rdi+29h]
0x180083ff0  mov     r9d, ebx
0x180083ff3  jmp     loc_1800840C3
0x180083ff8  mov     rax, [rsp+2B0h+var_268]
0x180083ffd  lea     rcx, [rsp+2B0h+var_268]; this
0x180084002  mov     [rsp+2B0h+var_280], rcx; unsigned __int64 *
0x180084007  mov     r9, r12; unsigned __int16 *
0x18008400a  mov     [rsp+2B0h+var_288], rax; unsigned __int64
0x18008400f  mov     r8, r15; unsigned __int16 *
0x180084012  mov     rdx, r14; unsigned __int16 *
0x180084015  mov     [rsp+2B0h+var_290], rdi; unsigned __int16 *
0x18008401a  call    ?GetString@CResourceManagerQueueInternal@Runtime@Resources@Microsoft@@QEAAJPEBG00PEAG_KPEA_K@Z; Microsoft::Resources::Runtime::CResourceManagerQueueInternal::GetString(ushort const *,ushort const *,ushort const *,ushort *,unsigned __int64,unsigned __int64 *)
0x18008401f  mov     ebx, eax
0x180084021  test    eax, eax
0x180084023  jns     loc_1800840E2
0x180084029  mov     edx, 2Dh ; '-'
0x18008402e  jmp     loc_1800840C0
0x180084033  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180084037  jnz     short loc_180084052
0x180084039  mov     rcx, [rbp+1B8h]; this
0x180084040  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180084047  mov     edx, 0F89h; void *
0x18008404c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180084052  lea     rcx, ds:2[rbx*2]; cb
0x18008405a  call    cs:__imp_CoTaskMemAlloc
0x180084060  test    rax, rax
0x180084063  jz      short loc_18008406E
0x180084065  xor     ecx, ecx
0x180084067  mov     [rax], cx
0x18008406a  mov     [rax+rbx*2], cx
0x18008406e  lea     rdx, [rsp+2B0h+var_260]
0x180084073  mov     [rsp+2B0h+var_260], rax
0x180084078  lea     rcx, [rsp+2B0h+var_270]
0x18008407d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180084082  lea     rcx, [rsp+2B0h+var_260]
0x180084087  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18008408c  mov     rdi, [rsp+2B0h+var_270]
0x180084091  test    rdi, rdi
0x180084094  jnz     short loc_1800840A3
0x180084096  mov     ebx, 8007000Eh
0x18008409b  lea     edx, [rdi+33h]
0x18008409e  mov     r9d, ebx
0x1800840a1  jmp     short loc_1800840C3
0x1800840a3  mov     rdx, [rsp+2B0h+var_268]; unsigned __int64
0x1800840a8  lea     r8, [rsp+2B0h+var_250]; unsigned __int16 *
0x1800840ad  mov     rcx, rdi; unsigned __int16 *
0x1800840b0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800840b5  mov     ebx, eax
0x1800840b7  test    eax, eax
0x1800840b9  jns     short loc_1800840E2
0x1800840bb  mov     edx, 35h ; '5'; void *
0x1800840c0  mov     r9d, eax; char *
0x1800840c3  mov     rcx, [rbp+1B8h]; this
0x1800840ca  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x1800840d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800840d6  lea     rcx, [rsp+2B0h+var_270]
0x1800840db  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800840e0  jmp     short loc_18008411C
0x1800840e2  lea     rcx, [rsp+2B0h+var_270]
0x1800840e7  mov     [rsp+2B0h+var_270], 0
0x1800840f0  mov     [rsi], rdi
0x1800840f3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800840f8  xor     eax, eax
0x1800840fa  jmp     short loc_18008411E
0x1800840fc  mov     rcx, [rbp+1B8h]; this
0x180084103  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x18008410a  mov     ebx, 80070057h
0x18008410f  mov     edx, 1Bh; void *
0x180084114  mov     r9d, ebx; char *
0x180084117  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008411c  mov     eax, ebx
0x18008411e  mov     rcx, [rbp+1B0h+var_40]
0x180084125  xor     rcx, rsp; StackCookie
0x180084128  call    __security_check_cookie
0x18008412d  add     rsp, 280h
0x180084134  pop     r15
0x180084136  pop     r14
0x180084138  pop     r12
0x18008413a  pop     rdi
0x18008413b  pop     rsi
0x18008413c  pop     rbx
0x18008413d  pop     rbp
0x18008413e  retn
```
