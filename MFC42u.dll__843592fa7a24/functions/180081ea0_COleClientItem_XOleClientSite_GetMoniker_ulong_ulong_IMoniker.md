# COleClientItem::XOleClientSite::GetMoniker(ulong,ulong,IMoniker * *)

- ea: `0x180081ea0`
- end: `0x1800820b8`
- name: `?GetMoniker@XOleClientSite@COleClientItem@@UEAAJKKPEAPEAUIMoniker@@@Z`
- size: `536`
- prototype: `int(COleClientItem::XOleClientSite *__hidden this, unsigned int, unsigned int, struct IMoniker **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000a150`
- `0x180011480`
- `0x18001d860`
- `0x180081ea0`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18008200d`
- `msvcrt!swprintf_s` at `0x18008200d`
- `OLE32!CreateGenericComposite` at `0x180081f65`
- `OLE32!CreateGenericComposite` at `0x180081f65`
- `OLE32!CreateItemMoniker` at `0x180082022`
- `OLE32!CreateItemMoniker` at `0x180082022`

## pseudocode

```c
__int64 __fastcall COleClientItem::XOleClientSite::GetMoniker(
        COleClientItem::XOleClientSite *this,
        unsigned int a2,
        int a3,
        struct IMoniker **a4)
{
  __int64 v4; // rbx
  __int64 Data; // r15
  __int64 v10; // r12
  CObject *v11; // rbx
  int v12; // esi
  int v13; // esi
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  bool v17; // cf
  LPMONIKER pmkFirst; // [rsp+30h] [rbp-88h] BYREF
  LPMONIKER pmkRest; // [rsp+38h] [rbp-80h] BYREF
  wchar_t Buffer[24]; // [rsp+40h] [rbp-78h] BYREF

  v4 = *((_QWORD *)this - 17);
  Data = CThreadLocal<_AFX_THREAD_STATE>::GetData();
  v10 = *(_QWORD *)(Data + 8);
  *(_QWORD *)(Data + 8) = v4;
  v11 = (CObject *)*((_QWORD *)this - 16);
  *a4 = 0;
  v12 = a3 - 1;
  if ( !v12 )
  {
    *a4 = (struct IMoniker *)(*(__int64 (__fastcall **)(CObject *, _QWORD))(*(_QWORD *)v11 + 432LL))(v11, a2);
    goto LABEL_22;
  }
  v13 = v12 - 1;
  if ( v13 )
  {
    if ( v13 == 1 )
    {
      v14 = *(_QWORD *)this;
      pmkFirst = 0;
      pmkRest = 0;
      (*(void (__fastcall **)(COleClientItem::XOleClientSite *, _QWORD, __int64, LPMONIKER *))(v14 + 32))(
        this,
        a2,
        1,
        &pmkFirst);
      (*(void (__fastcall **)(COleClientItem::XOleClientSite *, _QWORD, __int64, LPMONIKER *))(*(_QWORD *)this + 32LL))(
        this,
        a2,
        2,
        &pmkRest);
      if ( pmkFirst && pmkRest )
        CreateGenericComposite(pmkFirst, pmkRest, a4);
      _AfxRelease((struct IUnknown **)&pmkFirst);
      _AfxRelease((struct IUnknown **)&pmkRest);
    }
  }
  else if ( (unsigned int)CObject::IsKindOf(v11, (const struct CRuntimeClass *)&COleLinkingDoc::classCOleLinkingDoc) )
  {
    v15 = (*(__int64 (__fastcall **)(CObject *, _QWORD))(*(_QWORD *)v11 + 432LL))(v11, a2);
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      if ( a2 == 1 )
      {
        if ( !*((_BYTE *)this - 67) )
          goto LABEL_22;
      }
      else if ( a2 != 2 )
      {
        if ( a2 == 3 )
        {
          *((_BYTE *)this - 67) = 0;
          goto LABEL_22;
        }
        if ( a2 != 4 )
          goto LABEL_22;
      }
      swprintf_s(Buffer, 0x15u, L"Embedding %lu", *((unsigned int *)this - 26));
      CreateItemMoniker(L"\\", Buffer, a4);
      if ( a2 != 4 && *a4 && !*((_BYTE *)this - 67) )
      {
        v16 = *((_QWORD *)this - 15);
        *((_BYTE *)this - 67) = 1;
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v16 + 56LL))(v16, 2, *a4);
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this - 16) + 200LL))(*((_QWORD *)this - 16), 1);
      }
    }
  }
LABEL_22:
  v17 = *a4 != 0;
  *(_QWORD *)(Data + 8) = v10;
  return v17 ? 0 : 0x80004005;
}

```

## disassembly

```asm
0x180081ea0  push    rbx
0x180081ea2  push    rbp
0x180081ea3  push    rsi
0x180081ea4  push    rdi
0x180081ea5  push    r12
0x180081ea7  push    r14
0x180081ea9  push    r15
0x180081eab  sub     rsp, 80h
0x180081eb2  mov     rax, cs:__security_cookie
0x180081eb9  xor     rax, rsp
0x180081ebc  mov     [rsp+0B8h+var_48], rax
0x180081ec1  mov     rbx, [rcx-88h]
0x180081ec8  mov     r14, r9
0x180081ecb  mov     esi, r8d
0x180081ece  mov     ebp, edx
0x180081ed0  mov     rdi, rcx
0x180081ed3  call    ?GetData@?$CThreadLocal@V_AFX_THREAD_STATE@@@@QEAAPEAV_AFX_THREAD_STATE@@XZ; CThreadLocal<_AFX_THREAD_STATE>::GetData(void)
0x180081ed8  mov     r15, rax
0x180081edb  mov     r12, [rax+8]
0x180081edf  mov     [rax+8], rbx
0x180081ee3  mov     rbx, [rdi-80h]
0x180081ee7  mov     qword ptr [r14], 0
0x180081eee  sub     esi, 1
0x180081ef1  jz      loc_18008206F
0x180081ef7  sub     esi, 1
0x180081efa  jz      loc_180081F84
0x180081f00  cmp     esi, 1
0x180081f03  jnz     loc_180082086
0x180081f09  mov     rax, [rdi]
0x180081f0c  lea     r9, [rsp+0B8h+pmkFirst]
0x180081f11  mov     r8d, esi
0x180081f14  mov     [rsp+0B8h+pmkFirst], 0
0x180081f1d  mov     edx, ebp
0x180081f1f  mov     [rsp+0B8h+pmkRest], 0
0x180081f28  mov     rcx, rdi
0x180081f2b  mov     rax, [rax+20h]
0x180081f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081f34  mov     rax, [rdi]
0x180081f37  lea     r9, [rsp+0B8h+pmkRest]
0x180081f3c  lea     r8d, [rsi+1]
0x180081f40  mov     edx, ebp
0x180081f42  mov     rcx, rdi
0x180081f45  mov     rax, [rax+20h]
0x180081f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081f4e  mov     rcx, [rsp+0B8h+pmkFirst]; pmkFirst
0x180081f53  test    rcx, rcx
0x180081f56  jz      short loc_180081F6B
0x180081f58  mov     rdx, [rsp+0B8h+pmkRest]; pmkRest
0x180081f5d  test    rdx, rdx
0x180081f60  jz      short loc_180081F6B
0x180081f62  mov     r8, r14; ppmkComposite
0x180081f65  call    cs:__imp_CreateGenericComposite
0x180081f6b  lea     rcx, [rsp+0B8h+pmkFirst]; struct IUnknown **
0x180081f70  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x180081f75  lea     rcx, [rsp+0B8h+pmkRest]; struct IUnknown **
0x180081f7a  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x180081f7f  jmp     loc_180082086
0x180081f84  lea     rdx, ?classCOleLinkingDoc@COleLinkingDoc@@2UCRuntimeClass@@B; struct CRuntimeClass *
0x180081f8b  mov     rcx, rbx; this
0x180081f8e  call    ?IsKindOf@CObject@@QEBAHPEBUCRuntimeClass@@@Z; CObject::IsKindOf(CRuntimeClass const *)
0x180081f93  test    eax, eax
0x180081f95  jz      loc_180082086
0x180081f9b  mov     rax, [rbx]
0x180081f9e  mov     edx, ebp
0x180081fa0  mov     rcx, rbx
0x180081fa3  mov     rax, [rax+1B0h]
0x180081faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081faf  mov     rdx, rax
0x180081fb2  test    rax, rax
0x180081fb5  jz      loc_180082086
0x180081fbb  mov     rcx, [rax]
0x180081fbe  mov     rax, [rcx+10h]
0x180081fc2  mov     rcx, rdx
0x180081fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081fca  mov     eax, ebp
0x180081fcc  sub     eax, 1
0x180081fcf  jz      short loc_180081FEE
0x180081fd1  sub     eax, 1
0x180081fd4  jz      short loc_180081FF8
0x180081fd6  sub     eax, 1
0x180081fd9  jz      short loc_180081FE5
0x180081fdb  cmp     eax, 1
0x180081fde  jz      short loc_180081FF8
0x180081fe0  jmp     loc_180082086
0x180081fe5  mov     byte ptr [rdi-43h], 0
0x180081fe9  jmp     loc_180082086
0x180081fee  cmp     byte ptr [rdi-43h], 0
0x180081ff2  jz      loc_180082086
0x180081ff8  mov     r9d, [rdi-68h]
0x180081ffc  lea     r8, aEmbeddingLu; "Embedding %lu"
0x180082003  mov     edx, 15h; BufferCount
0x180082008  lea     rcx, [rsp+0B8h+Buffer]; Buffer
0x18008200d  call    cs:__imp_swprintf_s
0x180082013  mov     r8, r14; ppmk
0x180082016  lea     rdx, [rsp+0B8h+Buffer]; lpszItem
0x18008201b  lea     rcx, szDelim; "\\"
0x180082022  call    cs:__imp_CreateItemMoniker
0x180082028  cmp     ebp, 4
0x18008202b  jz      short loc_180082086
0x18008202d  cmp     qword ptr [r14], 0
0x180082031  jz      short loc_180082086
0x180082033  cmp     byte ptr [rdi-43h], 0
0x180082037  jnz     short loc_180082086
0x180082039  mov     rcx, [rdi-78h]
0x18008203d  mov     edx, 2
0x180082042  mov     byte ptr [rdi-43h], 1
0x180082046  mov     r8, [r14]
0x180082049  mov     rax, [rcx]
0x18008204c  mov     rax, [rax+38h]
0x180082050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082055  mov     rcx, [rdi-80h]
0x180082059  mov     edx, 1
0x18008205e  mov     rax, [rcx]
0x180082061  mov     rax, [rax+0C8h]
0x180082068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008206d  jmp     short loc_180082086
0x18008206f  mov     rax, [rbx]
0x180082072  mov     edx, ebp
0x180082074  mov     rcx, rbx
0x180082077  mov     rax, [rax+1B0h]
0x18008207e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082083  mov     [r14], rax
0x180082086  mov     rax, [r14]
0x180082089  neg     rax
0x18008208c  mov     [r15+8], r12
0x180082090  sbb     eax, eax
0x180082092  not     eax
0x180082094  and     eax, 80004005h
0x180082099  mov     rcx, [rsp+0B8h+var_48]
0x18008209e  xor     rcx, rsp; StackCookie
0x1800820a1  call    __security_check_cookie
0x1800820a6  add     rsp, 80h
0x1800820ad  pop     r15
0x1800820af  pop     r14
0x1800820b1  pop     r12
0x1800820b3  pop     rdi
0x1800820b4  pop     rsi
0x1800820b5  pop     rbp
0x1800820b6  pop     rbx
0x1800820b7  retn
```
