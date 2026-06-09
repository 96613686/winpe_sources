# ExpandOfflineFolderPath(ushort *,ulong,ushort *,ushort *,ushort const *,ushort *)

- ea: `0x180002270`
- end: `0x1800023c4`
- name: `?ExpandOfflineFolderPath@@YAJPEAGK00PEBG0@Z`
- size: `340`
- prototype: `__int64 __fastcall(PWSTR pszPath, void *, unsigned __int16 *, const char *, const unsigned __int16 *Source, unsigned __int16 *pszMore)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180002c64`

## callees

- `0x180002270`
- `0x180002c40`
- `0x1800039dc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800022e3`
- `msvcrt!memcpy_s` at `0x1800022e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002378`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002385`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002378`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002385`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800022c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800022c4`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x180002305`
- `api-ms-win-core-path-l1-1-0!PathCchStripToRoot` at `0x180002305`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180002357`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180002357`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18000232d`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18000232d`

## pseudocode

```c
__int64 __fastcall ExpandOfflineFolderPath(
        PWSTR pszPath,
        void *a2,
        unsigned __int16 *a3,
        const char *a4,
        const unsigned __int16 *Source,
        unsigned __int16 *pszMore)
{
  __int64 v9; // rcx
  const unsigned __int16 *v10; // rax
  rsize_t v11; // rsi
  WCHAR *v12; // rax
  unsigned int v13; // r8d
  WCHAR *v14; // rbx
  __int64 v15; // rsi
  __int64 v16; // rdx
  HRESULT v17; // eax
  unsigned int v18; // r8d
  unsigned int v19; // edi
  __int64 v20; // rdx
  int v22; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !Source )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, a2, (unsigned int)a3, a4);
  v9 = 0x7FFFFFFF;
  v10 = Source;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v11 = 2 * (v10 - Source);
  v12 = (WCHAR *)CoTaskMemAlloc(v11 + 2);
  v14 = v12;
  if ( v12 )
  {
    memcpy_s(v12, v11 + 2, Source, v11);
    v14[v11 / 2] = 0;
    v15 = -1;
    v16 = -1;
    do
      ++v16;
    while ( v14[v16] );
    v17 = PathCchStripToRoot(v14, v16 + 1);
    v19 = v17;
    if ( v17 < 0 )
    {
      v20 = 327;
LABEL_15:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v20, v18, (const char *)(unsigned int)v17, v22);
      CoTaskMemFree(v14);
      return v19;
    }
    v17 = PathCchCombine(pszPath, 0x104u, v14, pszMore);
    v19 = v17;
    if ( v17 < 0 )
    {
      v20 = 328;
      goto LABEL_15;
    }
    do
      ++v15;
    while ( *(_WORD *)&a4[2 * v15] );
    v17 = PathCchAppend(pszPath, 0x104u, &a3[v15 + 1]);
    v19 = v17;
    if ( v17 < 0 )
    {
      v20 = 331;
      goto LABEL_15;
    }
    CoTaskMemFree(v14);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x146, v13, (const char *)0x8007000ELL, v22);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180002270  push    rbx
0x180002272  push    rbp
0x180002273  push    rsi
0x180002274  push    rdi
0x180002275  push    r12
0x180002277  push    r13
0x180002279  push    r14
0x18000227b  push    r15
0x18000227d  sub     rsp, 28h
0x180002281  mov     rdi, [rsp+68h+Source]
0x180002289  xor     r13d, r13d
0x18000228c  mov     r15, r9
0x18000228f  mov     r12, r8
0x180002292  mov     r14, rcx
0x180002295  test    rdi, rdi
0x180002298  jz      loc_1800023B9
0x18000229e  mov     ecx, 7FFFFFFFh
0x1800022a3  mov     rax, rdi
0x1800022a6  cmp     [rax], r13w
0x1800022aa  jz      short loc_1800022B6
0x1800022ac  add     rax, 2
0x1800022b0  sub     rcx, 1
0x1800022b4  jnz     short loc_1800022A6
0x1800022b6  sub     rax, rdi
0x1800022b9  sar     rax, 1
0x1800022bc  lea     rsi, [rax+rax]
0x1800022c0  lea     rcx, [rsi+2]; cb
0x1800022c4  call    cs:__imp_CoTaskMemAlloc
0x1800022ca  mov     rbx, rax
0x1800022cd  test    rax, rax
0x1800022d0  jz      loc_18000238F
0x1800022d6  mov     r9, rsi; SourceSize
0x1800022d9  lea     rdx, [rsi+2]; DestinationSize
0x1800022dd  mov     r8, rdi; Source
0x1800022e0  mov     rcx, rax; Destination
0x1800022e3  call    cs:__imp_memcpy_s
0x1800022e9  mov     [rsi+rbx], r13w
0x1800022ee  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800022f2  mov     rdx, rsi
0x1800022f5  inc     rdx
0x1800022f8  cmp     [rbx+rdx*2], r13w
0x1800022fd  jnz     short loc_1800022F5
0x1800022ff  inc     rdx; cchPath
0x180002302  mov     rcx, rbx; pszPath
0x180002305  call    cs:__imp_PathCchStripToRoot
0x18000230b  mov     edi, eax
0x18000230d  test    eax, eax
0x18000230f  jns     short loc_180002318
0x180002311  mov     edx, 147h
0x180002316  jmp     short loc_180002368
0x180002318  mov     r9, [rsp+68h+pszMore]; pszMore
0x180002320  mov     ebp, 104h
0x180002325  mov     edx, ebp; cchPathOut
0x180002327  mov     r8, rbx; pszPathIn
0x18000232a  mov     rcx, r14; pszPathOut
0x18000232d  call    cs:__imp_PathCchCombine
0x180002333  mov     edi, eax
0x180002335  test    eax, eax
0x180002337  jns     short loc_18000233E
0x180002339  lea     edx, [rbp+44h]
0x18000233c  jmp     short loc_180002368
0x18000233e  inc     rsi
0x180002341  cmp     [r15+rsi*2], r13w
0x180002346  jnz     short loc_18000233E
0x180002348  lea     r8, [r12+2]
0x18000234d  mov     rdx, rbp; cchPath
0x180002350  lea     r8, [r8+rsi*2]; pszMore
0x180002354  mov     rcx, r14; pszPath
0x180002357  call    cs:__imp_PathCchAppend
0x18000235d  mov     edi, eax
0x18000235f  test    eax, eax
0x180002361  jns     short loc_180002382
0x180002363  mov     edx, 14Bh; void *
0x180002368  mov     rcx, [rsp+68h]; this
0x18000236d  mov     r9d, eax; char *
0x180002370  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002375  mov     rcx, rbx; pv
0x180002378  call    cs:__imp_CoTaskMemFree
0x18000237e  mov     eax, edi
0x180002380  jmp     short loc_1800023A8
0x180002382  mov     rcx, rbx; pv
0x180002385  call    cs:__imp_CoTaskMemFree
0x18000238b  xor     eax, eax
0x18000238d  jmp     short loc_1800023A8
0x18000238f  mov     rcx, [rsp+68h]; this
0x180002394  mov     ebx, 8007000Eh
0x180002399  mov     r9d, ebx; char *
0x18000239c  mov     edx, 146h; void *
0x1800023a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800023a6  mov     eax, ebx
0x1800023a8  add     rsp, 28h
0x1800023ac  pop     r15
0x1800023ae  pop     r14
0x1800023b0  pop     r13
0x1800023b2  pop     r12
0x1800023b4  pop     rdi
0x1800023b5  pop     rsi
0x1800023b6  pop     rbp
0x1800023b7  pop     rbx
0x1800023b8  retn
0x1800023b9  mov     rcx, [rsp+68h]; this
0x1800023be  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
