# CBatchedFilter::Read(uchar *)

- ea: `0x140041b60`
- end: `0x140041d8c`
- name: `?Read@CBatchedFilter@@UEAAJPEAE@Z`
- size: `556`
- prototype: `__int64 __fastcall(CBatchedFilter *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005570`
- `0x14000cce4`
- `0x140028044`
- `0x14003ec78`
- `0x14003f078`
- `0x14003f7f0`
- `0x140041b60`
- `0x140042744`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140041c77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140041c77`

## string_xrefs

- `0x140041c01`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrbatch.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CBatchedFilter::Read(CBatchedFilter *this, bool *a2)
{
  __int64 result; // rax
  _QWORD *v5; // rdi
  _DWORD *v6; // r13
  _QWORD *v7; // rdx
  int v8; // eax
  unsigned int v9; // esi
  unsigned __int64 i; // r14
  unsigned __int64 v11; // rax
  __int64 v12; // rsi
  _QWORD *v13; // rsi
  __int64 v14; // rax
  int v15; // edx
  int v16; // edx
  __int64 v17; // rdx
  bool v18; // cf
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  int v20; // [rsp+78h] [rbp+10h]
  void *v21; // [rsp+80h] [rbp+18h] BYREF

  v20 = 0;
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = (_QWORD *)((char *)this + 112);
  try
  {
    while ( 1 )
    {
      ++*((_DWORD *)this + 24);
      *(_QWORD *)((char *)this + 100) = 0;
      v6 = (_DWORD *)((char *)this + 92);
      if ( *((_DWORD *)this + 24) < *((_DWORD *)this + 23) )
        goto LABEL_18;
      CBatchedFilter::Cleanup((CBatchedFilter *)((char *)this - 8));
      v7 = (_QWORD *)((char *)this + 120);
      if ( *((_QWORD *)this + 18) > 7u )
        v7 = (_QWORD *)*v7;
      v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD, _QWORD))(**((_QWORD **)this + 8) + 24LL))(
             *((_QWORD *)this + 8),
             v7,
             *((unsigned int *)this + 22),
             *v5);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x183,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrbatch.hxx",
          (const char *)(unsigned int)v8,
          (_DWORD)this + 92);
        return v9;
      }
      for ( i = 0; ; ++i )
      {
        v11 = (unsigned int)*v6;
        if ( i >= v11 )
          break;
        v12 = *v5;
        if ( !*(_DWORD *)(*v5 + 72 * i + 56) && *(_QWORD *)(v12 + 72 * i + 64) )
        {
          v21 = operator new(0x20u);
          v13 = (_QWORD *)std::wstring::wstring(v21, *(_QWORD *)(v12 + 72 * i + 64));
          v21 = v13;
          v20 |= 1u;
          CoTaskMemFree(*(LPVOID *)(*v5 + 72 * i + 64));
          if ( v13[3] > 7u )
            v13 = (_QWORD *)*v13;
          std::vector<std::unique_ptr<std::wstring>>::emplace_back<std::unique_ptr<std::wstring>>(
            (char *)this + 216,
            &v21);
          *(_QWORD *)(*v5 + 72 * i + 64) = v13;
          std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(&v21);
        }
      }
      if ( *((_DWORD *)this + 24) < (unsigned int)v11 )
      {
LABEL_18:
        v14 = *v5;
        if ( *(_DWORD *)(*v5 + 72LL * *((unsigned int *)this + 24) + 4) == 3 )
        {
          v15 = *(_DWORD *)(v14 + 72LL * *((unsigned int *)this + 24));
          if ( v15 )
          {
            result = 2147500037LL;
            if ( v15 < 0 )
              return (unsigned int)v15;
            return result;
          }
          if ( !(unsigned __int8)CBatchedFilter::TryGetText(
                                   v14 + 8 + 72LL * *((unsigned int *)this + 24),
                                   (char *)this + 152) )
            return 2147500037LL;
        }
        else if ( *(_DWORD *)(v14 + 72LL * *((unsigned int *)this + 24) + 4) == 4 )
        {
          v16 = *(_DWORD *)(v14 + 72LL * *((unsigned int *)this + 24));
          if ( v16 )
          {
            result = 2147500037LL;
            if ( v16 < 0 )
              return (unsigned int)v16;
            return result;
          }
          if ( !(unsigned __int8)CBatchedFilter::TryGetText(
                                   v14 + 8 + 72LL * *((unsigned int *)this + 24),
                                   (char *)this + 184) )
            return 2147500037LL;
        }
      }
      v17 = *((unsigned int *)this + 24);
      v18 = (unsigned int)v17 < *v6;
      if ( (unsigned int)v17 >= *v6 )
        goto LABEL_36;
      if ( *(_DWORD *)(*v5 + 72 * v17 + 4) != 3 && *(_DWORD *)(*v5 + 72 * v17 + 4) != 4 )
      {
        v18 = (unsigned int)v17 < *v6;
LABEL_36:
        *a2 = v18;
        return 0;
      }
    }
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<0>(retaddr, 444);
  }
  return result;
}

```

## disassembly

```asm
0x140041b60  mov     rax, rsp
0x140041b63  push    rdi
0x140041b64  push    r12
0x140041b66  push    r13
0x140041b68  push    r14
0x140041b6a  push    r15
0x140041b6c  sub     rsp, 40h
0x140041b70  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x140041b78  mov     [rax+8], rbx
0x140041b7c  mov     [rax+20h], rsi
0x140041b80  mov     r12, rdx
0x140041b83  mov     rbx, rcx
0x140041b86  mov     [rsp+68h+arg_8], 0
0x140041b8e  test    rdx, rdx
0x140041b91  jnz     short loc_140041B9D
0x140041b93  mov     eax, 80004003h
0x140041b98  jmp     loc_140041D71
0x140041b9d  mov     byte ptr [rdx], 0
0x140041ba0  lea     rdi, [rcx+70h]
0x140041ba4  inc     dword ptr [rbx+60h]
0x140041ba7  mov     qword ptr [rbx+64h], 0
0x140041baf  lea     r13, [rbx+5Ch]
0x140041bb3  mov     eax, [r13+0]
0x140041bb7  cmp     [rbx+60h], eax
0x140041bba  jb      loc_140041CBD
0x140041bc0  lea     rcx, [rbx-8]; this
0x140041bc4  call    ?Cleanup@CBatchedFilter@@AEAAXXZ; CBatchedFilter::Cleanup(void)
0x140041bc9  mov     rcx, [rbx+40h]
0x140041bcd  mov     rax, [rcx]
0x140041bd0  lea     rdx, [rbx+78h]
0x140041bd4  cmp     qword ptr [rdx+18h], 7
0x140041bd9  jbe     short loc_140041BDE
0x140041bdb  mov     rdx, [rdx]
0x140041bde  mov     qword ptr [rsp+68h+var_48], r13; int
0x140041be3  mov     r9, [rdi]
0x140041be6  mov     r8d, [rbx+58h]
0x140041bea  mov     rax, [rax+18h]
0x140041bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041bf3  mov     esi, eax
0x140041bf5  test    eax, eax
0x140041bf7  jns     short loc_140041C19
0x140041bf9  mov     rcx, [rsp+68h]; this
0x140041bfe  mov     r9d, eax; char *
0x140041c01  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\appmodel\\search\\sea"...
0x140041c08  mov     edx, 183h; void *
0x140041c0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140041c12  mov     eax, esi
0x140041c14  jmp     loc_140041D71
0x140041c19  xor     r14d, r14d
0x140041c1c  mov     eax, [r13+0]
0x140041c20  cmp     r14, rax
0x140041c23  jnb     loc_140041CB8
0x140041c29  lea     r15, [r14+r14*8]
0x140041c2d  mov     rsi, [rdi]
0x140041c30  cmp     dword ptr [rsi+r15*8+38h], 0
0x140041c36  jnz     short loc_140041CB0
0x140041c38  cmp     qword ptr [rsi+r15*8+40h], 0
0x140041c3e  jz      short loc_140041CB0
0x140041c40  mov     ecx, 20h ; ' '; Size
0x140041c45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140041c4a  mov     [rsp+68h+arg_10], rax
0x140041c52  mov     rdx, [rsi+r15*8+40h]
0x140041c57  mov     rcx, rax
0x140041c5a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x140041c5f  mov     rsi, rax
0x140041c62  mov     [rsp+68h+arg_10], rax
0x140041c6a  or      [rsp+68h+arg_8], 1
0x140041c6f  mov     rcx, [rdi]
0x140041c72  mov     rcx, [rcx+r15*8+40h]; pv
0x140041c77  call    cs:__imp_CoTaskMemFree
0x140041c7d  cmp     qword ptr [rsi+18h], 7
0x140041c82  jbe     short loc_140041C87
0x140041c84  mov     rsi, [rsi]
0x140041c87  lea     rcx, [rbx+0D8h]
0x140041c8e  lea     rdx, [rsp+68h+arg_10]
0x140041c96  call    ??$emplace_back@V?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@?$vector@V?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@V?$allocator@V?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@2@@std@@QEAAAEAV?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<std::wstring>>::emplace_back<std::unique_ptr<std::wstring>>(std::unique_ptr<std::wstring> &&)
0x140041c9b  mov     rax, [rdi]
0x140041c9e  mov     [rax+r15*8+40h], rsi
0x140041ca3  lea     rcx, [rsp+68h+arg_10]
0x140041cab  call    ??1?$unique_ptr@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$default_delete@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::wstring>::~unique_ptr<std::wstring>(void)
0x140041cb0  inc     r14
0x140041cb3  jmp     loc_140041C1C
0x140041cb8  cmp     [rbx+60h], eax
0x140041cbb  jnb     short loc_140041D38
0x140041cbd  mov     eax, [rbx+60h]
0x140041cc0  lea     rcx, [rax+rax*8]
0x140041cc4  mov     rax, [rdi]
0x140041cc7  cmp     dword ptr [rax+rcx*8+4], 3
0x140041ccc  jnz     short loc_140041D01
0x140041cce  mov     edx, [rax+rcx*8]
0x140041cd1  test    edx, edx
0x140041cd3  jz      short loc_140041CE2
0x140041cd5  mov     eax, 80004005h
0x140041cda  cmovs   eax, edx
0x140041cdd  jmp     loc_140041D71
0x140041ce2  lea     rdx, [rbx+98h]
0x140041ce9  add     rax, 8
0x140041ced  lea     rcx, [rax+rcx*8]
0x140041cf1  call    ?TryGetText@CBatchedFilter@@CA_NAEBUtagPROPVARIANT@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; CBatchedFilter::TryGetText(tagPROPVARIANT const &,std::wstring &)
0x140041cf6  test    al, al
0x140041cf8  jnz     short loc_140041D38
0x140041cfa  mov     eax, 80004005h
0x140041cff  jmp     short loc_140041D71
0x140041d01  cmp     dword ptr [rax+rcx*8+4], 4
0x140041d06  jnz     short loc_140041D38
0x140041d08  mov     edx, [rax+rcx*8]
0x140041d0b  test    edx, edx
0x140041d0d  jz      short loc_140041D19
0x140041d0f  mov     eax, 80004005h
0x140041d14  cmovs   eax, edx
0x140041d17  jmp     short loc_140041D71
0x140041d19  lea     rdx, [rbx+0B8h]
0x140041d20  add     rax, 8
0x140041d24  lea     rcx, [rax+rcx*8]
0x140041d28  call    ?TryGetText@CBatchedFilter@@CA_NAEBUtagPROPVARIANT@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; CBatchedFilter::TryGetText(tagPROPVARIANT const &,std::wstring &)
0x140041d2d  test    al, al
0x140041d2f  jnz     short loc_140041D38
0x140041d31  mov     eax, 80004005h
0x140041d36  jmp     short loc_140041D71
0x140041d38  mov     edx, [rbx+60h]
0x140041d3b  cmp     edx, [r13+0]
0x140041d3f  jnb     short loc_140041D62
0x140041d41  lea     rcx, [rdx+rdx*8]
0x140041d45  mov     rax, [rdi]
0x140041d48  cmp     dword ptr [rax+rcx*8+4], 3
0x140041d4d  jz      loc_140041BA4
0x140041d53  cmp     dword ptr [rax+rcx*8+4], 4
0x140041d58  jz      loc_140041BA4
0x140041d5e  cmp     edx, [r13+0]
0x140041d62  setb    al
0x140041d65  mov     [r12], al
0x140041d69  xor     eax, eax
0x140041d6b  jmp     short loc_140041D71
0x140041d6d  mov     eax, [rsp+68h+arg_8]
0x140041d71  lea     r11, [rsp+68h+var_28]
0x140041d76  mov     rbx, [r11+30h]
0x140041d7a  mov     rsi, [r11+48h]
0x140041d7e  mov     rsp, r11
0x140041d81  pop     r15
0x140041d83  pop     r14
0x140041d85  pop     r13
0x140041d87  pop     r12
0x140041d89  pop     rdi
0x140041d8a  retn
```
