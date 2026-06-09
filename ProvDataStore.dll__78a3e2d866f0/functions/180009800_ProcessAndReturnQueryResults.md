# ProcessAndReturnQueryResults

- ea: `0x180009800`
- end: `0x180009a18`
- name: `ProcessAndReturnQueryResults`
- size: `536`
- prototype: `void __fastcall(__int64 **, __int64, _QWORD *, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009aa0`
- `0x180009bd0`

## callees

- `0x18000108c`
- `0x1800085e4`
- `0x180009800`
- `0x18000a2e4`
- `0x18000a304`
- `0x180010f4e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800099cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800099cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800098be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800098be`

## string_xrefs

- `0x180009a06`: `onecoreuap\admin\prov\multivariant\common\inc\mvtypes.h`

## pseudocode

```c
void __fastcall ProcessAndReturnQueryResults(__int64 **a1, __int64 a2, _QWORD *a3, unsigned int *a4)
{
  unsigned __int64 v6; // r8
  unsigned int v7; // r14d
  int v8; // ebx
  SIZE_T v9; // rax
  void *v10; // rdx
  char *v11; // rbp
  __int64 v12; // r8
  const char *v13; // r9
  unsigned int v14; // r12d
  __int64 *v15; // rbx
  __int64 *v16; // rdi
  _DWORD *v17; // rsi
  __int64 v18; // r15
  int v19; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int *v21; // [rsp+80h] [rbp+8h] BYREF
  _QWORD *v22; // [rsp+90h] [rbp+18h]

  v22 = a3;
  *a3 = 0;
  *a4 = 0;
  v6 = ((char *)a1[1] - (char *)*a1) >> 4;
  v7 = v6;
  if ( v6 > 0xFFFFFFFF )
    v7 = -1;
  v8 = -2147024362;
  if ( v6 > 0xFFFFFFFF )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x8D,
      (int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\masterdatastore.cpp",
      v6 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
      v19);
  if ( v7 )
  {
    ____Sort_PEAV__shared_ptr_VCConfigSet___std___JP6AHV__shared_ptr___CBVCConfigSet___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSet___0_0_JP6AHV__shared_ptr___CBVCConfigSet___0_2__E_Z(
      *a1,
      a1[1],
      v6,
      (unsigned int (__fastcall *)(_QWORD *, _QWORD *))CompareConfigSet);
    v21 = 0;
    v9 = 104LL * v7;
    if ( is_mul_ok(v7, 0x68u) )
      v8 = 0;
    else
      v9 = -1;
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x3B,
        (int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\mvtypes.h",
        (const char *)(unsigned int)v8,
        v19);
    v11 = (char *)CoTaskMemRealloc(0, v9);
    if ( !v11 )
      wil::details::in1diag3::_Throw_NullAlloc(retaddr, v10, v12, v13);
    v14 = 0;
    v15 = *a1;
    v16 = a1[1];
    while ( v15 != v16 )
    {
      v17 = (_DWORD *)*v15;
      v18 = 104LL * v14;
      *(_DWORD *)&v11[v18] = *(_DWORD *)*v15;
      *(_DWORD *)&v11[v18 + 4] = v17[1];
      *(_QWORD *)&v11[v18 + 8] = *((_QWORD *)v17 + 1);
      *(_QWORD *)&v11[v18 + 16] = *((_QWORD *)v17 + 2);
      *(_QWORD *)&v11[v18 + 24] = *((_QWORD *)v17 + 3);
      *(_DWORD *)&v11[v18 + 32] = v17[8];
      *(_QWORD *)&v11[v18 + 40] = *((_QWORD *)v17 + 5);
      *(_QWORD *)&v11[v18 + 56] = *((_QWORD *)v17 + 7);
      *(_QWORD *)&v11[v18 + 64] = *((_QWORD *)v17 + 8);
      *(_DWORD *)&v11[v18 + 72] = v17[18];
      *(_QWORD *)&v11[v18 + 76] = (unsigned int)v17[19];
      memset_0(v17, 0, 0x68u);
      *((_QWORD *)v17 + 14) = 0;
      *((_QWORD *)v17 + 13) = 0;
      *((_BYTE *)v17 + 120) = 0;
      if ( (unsigned int)dword_180019000 > 4 )
      {
        v21 = *(int **)&v11[v18 + 8];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)&dword_180019000,
          (__int64)byte_180015519,
          0,
          0,
          &v21);
      }
      ++v14;
      v15 += 2;
    }
    *v22 = v11;
    *a4 = v7;
    CoTaskMemFree(0);
  }
}

```

## disassembly

```asm
0x180009800  mov     [rsp+arg_8], rbx
0x180009805  mov     [rsp+arg_10], r8
0x18000980a  push    rbp
0x18000980b  push    rsi
0x18000980c  push    rdi
0x18000980d  push    r12
0x18000980f  push    r13
0x180009811  push    r14
0x180009813  push    r15
0x180009815  sub     rsp, 40h
0x180009819  mov     r13, r9
0x18000981c  mov     eax, edx
0x18000981e  mov     rdi, rcx
0x180009821  xor     r15d, r15d
0x180009824  mov     [r8], r15
0x180009827  mov     [r9], r15d
0x18000982a  mov     rdx, [rcx+8]
0x18000982e  mov     r8, rdx
0x180009831  sub     r8, [rcx]
0x180009834  sar     r8, 4
0x180009838  mov     r10d, 0FFFFFFFFh
0x18000983e  cmp     r8, r10
0x180009841  mov     r14d, r8d
0x180009844  jbe     short loc_180009849
0x180009846  mov     r14d, r10d
0x180009849  cmp     r10, r8
0x18000984c  sbb     r9d, r9d
0x18000984f  mov     ebx, 80070216h
0x180009854  and     r9d, ebx; char *
0x180009857  mov     rcx, [rsp+78h]; this
0x18000985c  cmp     r8, r10
0x18000985f  ja      loc_1800099F1
0x180009865  test    r14d, r14d
0x180009868  jz      loc_1800099D3
0x18000986e  lea     r9, ?CompareConfigSet@@YAHV?$shared_ptr@$$CBVCConfigSet@@@std@@0@Z; CompareConfigSet(std::shared_ptr<CConfigSet const>,std::shared_ptr<CConfigSet const>)
0x180009875  lea     rcx, ?CompareConfigSet@@YAHV?$shared_ptr@$$CBVCConfigSet@@@std@@0@Z; CompareConfigSet(std::shared_ptr<CConfigSet const>,std::shared_ptr<CConfigSet const>)
0x18000987c  cmp     eax, 2
0x18000987f  cmovnz  r9, rcx
0x180009883  mov     rcx, [rdi]
0x180009886  call    ??$_Sort@PEAV?$shared_ptr@VCConfigSet@@@std@@_JP6AHV?$shared_ptr@$$CBVCConfigSet@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSet@@@0@0_JP6AHV?$shared_ptr@$$CBVCConfigSet@@@0@2@_E@Z
0x18000988b  mov     [rsp+78h+arg_0], r15
0x180009893  mov     ecx, r14d
0x180009896  mov     eax, 68h ; 'h'
0x18000989b  mul     rcx
0x18000989e  test    rdx, rdx
0x1800098a1  jnz     short loc_1800098A8
0x1800098a3  mov     ebx, r15d
0x1800098a6  jmp     short loc_1800098AC
0x1800098a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800098ac  mov     rcx, [rsp+78h]; this
0x1800098b1  test    ebx, ebx
0x1800098b3  js      loc_180009A03
0x1800098b9  mov     rdx, rax; cb
0x1800098bc  xor     ecx, ecx; pv
0x1800098be  call    cs:__imp_CoTaskMemRealloc
0x1800098c4  mov     rbp, rax
0x1800098c7  mov     rcx, [rsp+78h]; this
0x1800098cc  test    rax, rax
0x1800098cf  jz      loc_1800099EB
0x1800098d5  mov     r12d, r15d
0x1800098d8  mov     rbx, [rdi]
0x1800098db  mov     rdi, [rdi+8]
0x1800098df  cmp     rbx, rdi
0x1800098e2  jz      loc_1800099BC
0x1800098e8  mov     rsi, [rbx]
0x1800098eb  mov     eax, r12d
0x1800098ee  imul    r15, rax, 68h ; 'h'
0x1800098f2  mov     eax, [rsi]
0x1800098f4  mov     [r15+rbp], eax
0x1800098f8  mov     eax, [rsi+4]
0x1800098fb  mov     [r15+rbp+4], eax
0x180009900  mov     rax, [rsi+8]
0x180009904  mov     [r15+rbp+8], rax
0x180009909  mov     rax, [rsi+10h]
0x18000990d  mov     [r15+rbp+10h], rax
0x180009912  mov     rax, [rsi+18h]
0x180009916  mov     [r15+rbp+18h], rax
0x18000991b  mov     eax, [rsi+20h]
0x18000991e  mov     [r15+rbp+20h], eax
0x180009923  mov     rax, [rsi+28h]
0x180009927  mov     [r15+rbp+28h], rax
0x18000992c  mov     rax, [rsi+38h]
0x180009930  mov     [r15+rbp+38h], rax
0x180009935  mov     rax, [rsi+40h]
0x180009939  mov     [r15+rbp+40h], rax
0x18000993e  mov     eax, [rsi+48h]
0x180009941  mov     [r15+rbp+48h], eax
0x180009946  mov     eax, [rsi+4Ch]
0x180009949  mov     [r15+rbp+4Ch], eax
0x18000994e  mov     dword ptr [r15+rbp+50h], 0
0x180009957  xor     edx, edx; Val
0x180009959  lea     r8d, [rdx+68h]; Size
0x18000995d  mov     rcx, rsi; void *
0x180009960  call    memset_0
0x180009965  xor     eax, eax
0x180009967  mov     [rsi+70h], rax
0x18000996b  mov     [rsi+68h], rax
0x18000996f  mov     [rsi+78h], al
0x180009972  mov     eax, cs:dword_180019000
0x180009978  cmp     eax, 4
0x18000997b  jbe     short loc_1800099B0
0x18000997d  mov     rax, [r15+rbp+8]
0x180009982  mov     [rsp+78h+arg_0], rax
0x18000998a  lea     rax, [rsp+78h+arg_0]
0x180009992  mov     qword ptr [rsp+78h+var_58], rax
0x180009997  xor     r9d, r9d
0x18000999a  xor     r8d, r8d
0x18000999d  lea     rdx, byte_180015519
0x1800099a4  lea     rcx, dword_180019000
0x1800099ab  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800099b0  inc     r12d
0x1800099b3  add     rbx, 10h
0x1800099b7  jmp     loc_1800098DF
0x1800099bc  mov     rax, [rsp+78h+arg_10]
0x1800099c4  mov     [rax], rbp
0x1800099c7  mov     [r13+0], r14d
0x1800099cb  xor     ecx, ecx; pv
0x1800099cd  call    cs:__imp_CoTaskMemFree
0x1800099d3  mov     rbx, [rsp+78h+arg_8]
0x1800099db  add     rsp, 40h
0x1800099df  pop     r15
0x1800099e1  pop     r14
0x1800099e3  pop     r13
0x1800099e5  pop     r12
0x1800099e7  pop     rdi
0x1800099e8  pop     rsi
0x1800099e9  pop     rbp
0x1800099ea  retn
0x1800099eb  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800099f1  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800099f8  mov     edx, 8Dh; void *
0x1800099fd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180009a03  mov     r9d, ebx; char *
0x180009a06  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180009a0d  mov     edx, 3Bh ; ';'; void *
0x180009a12  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
