# wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t const *,unsigned __int64)

- ea: `0x180015608`
- end: `0x180015844`
- name: `??$str_build_nothrow_@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBUstring_view_t@01@_K@Z`
- size: `572`
- prototype: `__int64 __fastcall(int *, __int64, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017db0`

## callees

- `0x180009544`
- `0x180015608`
- `0x18001a8bc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015685`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800157cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015813`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015825`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015685`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800157cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015813`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015825`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800157d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800157d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800157c4`

## string_xrefs

- `0x180015667`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800157f7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        int *a1,
        __int64 a2,
        void *a3)
{
  __int64 v3; // rbp
  __int64 v4; // rsi
  __int64 v6; // rdi
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  void *v11; // rbx
  char *v12; // r8
  char *v13; // r15
  _WORD *v14; // rcx
  unsigned __int64 v15; // rdx
  signed int v16; // edi
  unsigned __int64 v17; // rax
  char *v18; // rdx
  char *v19; // r9
  __int64 v20; // r11
  char *v21; // rcx
  __int64 v22; // rax
  void *v23; // rsi
  DWORD LastError; // edi
  int v25; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID pv; // [rsp+70h] [rbp+18h] BYREF

  pv = a3;
  v3 = a2 + 48;
  v4 = a2;
  v6 = 0;
  v7 = a2;
  do
  {
    v6 += *(_QWORD *)(v7 + 8);
    v7 += 16;
  }
  while ( v7 != v3 );
  pv = 0;
  v8 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
         &pv,
         0,
         v6);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)(unsigned int)v8,
      v25);
    if ( pv )
      CoTaskMemFree(pv);
    return v9;
  }
  v11 = pv;
  v12 = (char *)pv;
  v13 = (char *)pv + 2 * v6 + 2;
  if ( v4 == v3 )
  {
LABEL_35:
    if ( a1 == &v25 )
    {
      if ( v11 )
        CoTaskMemFree(v11);
    }
    else
    {
      v23 = *(void **)a1;
      if ( *(_QWORD *)a1 )
      {
        LastError = GetLastError();
        CoTaskMemFree(v23);
        SetLastError(LastError);
      }
      *(_QWORD *)a1 = v11;
    }
    return 0;
  }
  while ( 1 )
  {
    v14 = *(_WORD **)v4;
    if ( !*(_QWORD *)v4 )
      goto LABEL_34;
    v15 = (v13 - v12) >> 1;
    if ( !v12 )
    {
      if ( v15 )
      {
        v16 = -2147024809;
        goto LABEL_41;
      }
      goto LABEL_13;
    }
    if ( v15 > 0x7FFFFFFF )
      break;
LABEL_13:
    v17 = *(_QWORD *)(v4 + 8);
    if ( v17 < 0x7FFFFFFF )
    {
      if ( v15 )
      {
        v19 = v12;
        v20 = 0;
        do
        {
          if ( !v17 )
            break;
          if ( !*v14 )
            break;
          *(_WORD *)v19 = *v14++;
          v19 += 2;
          --v17;
          ++v20;
          --v15;
        }
        while ( v15 );
        v21 = v19 - 2;
        if ( v15 )
          v21 = v19;
        v22 = v20 - 1;
        v16 = v15 != 0 ? 0 : 0x8007007A;
        *(_WORD *)v21 = 0;
        if ( v15 )
          v22 = v20;
        v18 = &v12[2 * v22];
      }
      else
      {
        v18 = v12;
        v16 = 0;
        if ( v17 && *v14 )
        {
          if ( !v12 )
          {
            v16 = -2147024809;
            goto LABEL_42;
          }
          v16 = -2147024774;
        }
      }
      if ( v16 >= 0 || v16 == -2147024774 )
        v12 = v18;
    }
    else
    {
      v16 = -2147024809;
      if ( v15 )
        *(_WORD *)v12 = 0;
    }
    if ( v16 < 0 )
      goto LABEL_42;
LABEL_34:
    v4 += 16;
    if ( v4 == v3 )
      goto LABEL_35;
  }
  v16 = -2147024809;
LABEL_41:
  *(_WORD *)v12 = 0;
LABEL_42:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x791,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (const char *)(unsigned int)v16,
    v25);
  if ( v11 )
    CoTaskMemFree(v11);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180015608  mov     [rsp+arg_0], rbx
0x18001560d  mov     [rsp+arg_8], rbp
0x180015612  mov     [rsp+pv], r8
0x180015617  push    rsi
0x180015618  push    rdi
0x180015619  push    r12
0x18001561b  push    r14
0x18001561d  push    r15
0x18001561f  sub     rsp, 30h
0x180015623  xor     r12d, r12d
0x180015626  lea     rbp, [rdx+30h]
0x18001562a  mov     rsi, rdx
0x18001562d  mov     r14, rcx
0x180015630  mov     edi, r12d
0x180015633  mov     rax, rdx
0x180015636  cmp     rdx, rbp
0x180015639  jz      short loc_180015648
0x18001563b  add     rdi, [rax+8]
0x18001563f  add     rax, 10h
0x180015643  cmp     rax, rbp
0x180015646  jnz     short loc_18001563B
0x180015648  mov     r8, rdi
0x18001564b  mov     [rsp+58h+pv], r12
0x180015650  xor     edx, edx
0x180015652  lea     rcx, [rsp+58h+pv]
0x180015657  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x18001565c  mov     ebx, eax
0x18001565e  test    eax, eax
0x180015660  jns     short loc_180015692
0x180015662  mov     rcx, [rsp+58h]; this
0x180015667  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001566e  mov     r9d, eax; char *
0x180015671  mov     edx, 788h; void *
0x180015676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001567b  mov     rcx, [rsp+58h+pv]; pv
0x180015680  test    rcx, rcx
0x180015683  jz      short loc_18001568B
0x180015685  call    cs:__imp_CoTaskMemFree
0x18001568b  mov     eax, ebx
0x18001568d  jmp     loc_18001582D
0x180015692  mov     rbx, [rsp+58h+pv]
0x180015697  mov     r8, rbx
0x18001569a  lea     r15, [rbx+2]
0x18001569e  lea     r15, [r15+rdi*2]
0x1800156a2  cmp     rsi, rbp
0x1800156a5  jz      loc_1800157B2
0x1800156ab  mov     r9d, 8007007Ah
0x1800156b1  mov     rcx, [rsi]
0x1800156b4  test    rcx, rcx
0x1800156b7  jz      loc_1800157A5
0x1800156bd  mov     rdx, r15
0x1800156c0  sub     rdx, r8
0x1800156c3  sar     rdx, 1
0x1800156c6  test    r8, r8
0x1800156c9  jnz     short loc_1800156E3
0x1800156cb  test    rdx, rdx
0x1800156ce  jz      short loc_1800156F0
0x1800156d0  mov     edi, 80070057h
0x1800156d5  test    rdx, rdx
0x1800156d8  jz      loc_1800157F2
0x1800156de  jmp     loc_1800157EE
0x1800156e3  cmp     rdx, 7FFFFFFFh
0x1800156ea  ja      loc_1800157E9
0x1800156f0  mov     rax, [rsi+8]
0x1800156f4  cmp     rax, 7FFFFFFFh
0x1800156fa  jb      short loc_180015713
0x1800156fc  mov     edi, 80070057h
0x180015701  test    rdx, rdx
0x180015704  jz      loc_1800157A1
0x18001570a  mov     [r8], r12w
0x18001570e  jmp     loc_1800157A1
0x180015713  test    rdx, rdx
0x180015716  jnz     short loc_180015737
0x180015718  mov     rdx, r8
0x18001571b  mov     edi, r12d
0x18001571e  test    rax, rax
0x180015721  jz      short loc_180015795
0x180015723  cmp     [rcx], r12w
0x180015727  jz      short loc_180015795
0x180015729  test    r8, r8
0x18001572c  jz      loc_1800157E2
0x180015732  mov     edi, r9d
0x180015735  jmp     short loc_180015795
0x180015737  mov     r9, r8
0x18001573a  mov     r11, r12
0x18001573d  test    rax, rax
0x180015740  jz      short loc_180015764
0x180015742  movzx   r10d, word ptr [rcx]
0x180015746  test    r10w, r10w
0x18001574a  jz      short loc_180015764
0x18001574c  mov     [r9], r10w
0x180015750  add     rcx, 2
0x180015754  add     r9, 2
0x180015758  dec     rax
0x18001575b  inc     r11
0x18001575e  sub     rdx, 1
0x180015762  jnz     short loc_18001573D
0x180015764  test    rdx, rdx
0x180015767  lea     rcx, [r9-2]
0x18001576b  mov     rax, rdx
0x18001576e  cmovnz  rcx, r9
0x180015772  neg     rax
0x180015775  mov     r9d, 8007007Ah
0x18001577b  lea     rax, [r11-1]
0x18001577f  sbb     edi, edi
0x180015781  not     edi
0x180015783  and     edi, r9d
0x180015786  mov     [rcx], r12w
0x18001578a  test    rdx, rdx
0x18001578d  cmovnz  rax, r11
0x180015791  lea     rdx, [r8+rax*2]
0x180015795  test    edi, edi
0x180015797  jns     short loc_18001579E
0x180015799  cmp     edi, r9d
0x18001579c  jnz     short loc_1800157A1
0x18001579e  mov     r8, rdx
0x1800157a1  test    edi, edi
0x1800157a3  js      short loc_1800157F2
0x1800157a5  add     rsi, 10h
0x1800157a9  cmp     rsi, rbp
0x1800157ac  jnz     loc_1800156B1
0x1800157b2  lea     rax, [rsp+58h+var_38]
0x1800157b7  cmp     r14, rax
0x1800157ba  jz      short loc_18001581D
0x1800157bc  mov     rsi, [r14]
0x1800157bf  test    rsi, rsi
0x1800157c2  jz      short loc_1800157DD
0x1800157c4  call    cs:__imp_GetLastError
0x1800157ca  mov     rcx, rsi; pv
0x1800157cd  mov     edi, eax
0x1800157cf  call    cs:__imp_CoTaskMemFree
0x1800157d5  mov     ecx, edi; dwErrCode
0x1800157d7  call    cs:__imp_SetLastError
0x1800157dd  mov     [r14], rbx
0x1800157e0  jmp     short loc_18001582B
0x1800157e2  mov     edi, 80070057h
0x1800157e7  jmp     short loc_1800157F2
0x1800157e9  mov     edi, 80070057h
0x1800157ee  mov     [r8], r12w
0x1800157f2  mov     rcx, [rsp+58h]; this
0x1800157f7  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800157fe  mov     r9d, edi; char *
0x180015801  mov     edx, 791h; void *
0x180015806  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001580b  test    rbx, rbx
0x18001580e  jz      short loc_180015819
0x180015810  mov     rcx, rbx; pv
0x180015813  call    cs:__imp_CoTaskMemFree
0x180015819  mov     eax, edi
0x18001581b  jmp     short loc_18001582D
0x18001581d  test    rbx, rbx
0x180015820  jz      short loc_18001582B
0x180015822  mov     rcx, rbx; pv
0x180015825  call    cs:__imp_CoTaskMemFree
0x18001582b  xor     eax, eax
0x18001582d  mov     rbx, [rsp+58h+arg_0]
0x180015832  mov     rbp, [rsp+58h+arg_8]
0x180015837  add     rsp, 30h
0x18001583b  pop     r15
0x18001583d  pop     r14
0x18001583f  pop     r12
0x180015841  pop     rdi
0x180015842  pop     rsi
0x180015843  retn
```
