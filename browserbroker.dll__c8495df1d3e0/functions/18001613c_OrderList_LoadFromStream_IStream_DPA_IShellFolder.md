# OrderList_LoadFromStream(IStream *,_DPA * *,IShellFolder *)

- ea: `0x18001613c`
- end: `0x180016216`
- name: `?OrderList_LoadFromStream@@YAJPEAUIStream@@PEAPEAU_DPA@@PEAUIShellFolder@@@Z`
- size: `218`
- prototype: `__int64 __fastcall(struct IStream *pstream, struct _DPA **, struct IShellFolder *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015544`

## callees

- `0x18001613c`

## import_xrefs

- `iertutil!__imp_DPA_DestroyCallback` at `0x1800161ae`
- `iertutil!__imp_DPA_DestroyCallback` at `0x1800161ae`
- `iertutil!__imp_DPA_LoadStream` at `0x180016189`
- `iertutil!__imp_DPA_LoadStream` at `0x180016189`
- `iertutil!__imp_DPA_Sort` at `0x1800161ef`
- `iertutil!__imp_DPA_Sort` at `0x1800161ef`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18001616e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x18001616e`

## pseudocode

```c
__int64 __fastcall OrderList_LoadFromStream(struct IStream *pstream, struct _DPA **a2, struct IShellFolder *a3)
{
  struct _DPA *v6; // r9
  __int64 result; // rax
  LPARAM lParam[2]; // [rsp+20h] [rbp-30h] BYREF
  __int128 v9; // [rsp+30h] [rbp-20h]
  __int64 v10; // [rsp+40h] [rbp-10h]
  HDPA phdpa; // [rsp+78h] [rbp+28h] BYREF
  __int64 pv; // [rsp+88h] [rbp+38h] BYREF

  phdpa = 0;
  pv = 0;
  if ( IStream_Read(pstream, &pv, 8u) >= 0 )
  {
    DPA_LoadStream(&phdpa, (PFNDPASTREAM)OrderItem_LoadFromStream, pstream, a3);
    v6 = phdpa;
    if ( HIDWORD(pv) != 2 )
    {
      if ( !phdpa )
        goto LABEL_9;
      DPA_DestroyCallback(phdpa, OrderItem_FreeItem, (void *)1);
      v6 = 0;
      phdpa = 0;
    }
    if ( !v6 || !a3 )
      goto LABEL_9;
    lParam[0] = 0;
    v10 = 0;
    lParam[1] = (LPARAM)a3;
    v9 = 0;
    DPA_Sort(v6, OrderItem_Compare, (LPARAM)lParam);
  }
  v6 = phdpa;
LABEL_9:
  *a2 = v6;
  result = 2147500037LL;
  if ( v6 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x18001613c  mov     [rsp-18h+arg_0], rbx
0x180016141  push    rbp
0x180016142  push    rsi
0x180016143  push    rdi
0x180016144  mov     rbp, rsp
0x180016147  sub     rsp, 50h
0x18001614b  mov     rbx, r8
0x18001614e  mov     [rbp+phdpa], 0
0x180016156  mov     rsi, rdx
0x180016159  mov     [rbp+pv], 0
0x180016161  mov     r8d, 8; cb
0x180016167  lea     rdx, [rbp+pv]; pv
0x18001616b  mov     rdi, rcx
0x18001616e  call    cs:__imp_IStream_Read
0x180016174  test    eax, eax
0x180016176  js      short loc_1800161F5
0x180016178  mov     r9, rbx; pvInstData
0x18001617b  lea     rdx, ?OrderItem_LoadFromStream@@YAJPEAU_DPASTREAMINFO@@PEAUIStream@@PEAX@Z; pfn
0x180016182  mov     r8, rdi; pstream
0x180016185  lea     rcx, [rbp+phdpa]; phdpa
0x180016189  call    cs:__imp_DPA_LoadStream
0x18001618f  cmp     dword ptr [rbp+pv+4], 2
0x180016193  mov     r9, [rbp+phdpa]
0x180016197  jz      short loc_1800161BB
0x180016199  test    r9, r9
0x18001619c  jz      short loc_1800161F9
0x18001619e  mov     r8d, 1; pData
0x1800161a4  lea     rdx, ?OrderItem_FreeItem@@YAHPEAX0@Z; pfnCB
0x1800161ab  mov     rcx, r9; hdpa
0x1800161ae  call    cs:__imp_DPA_DestroyCallback
0x1800161b4  xor     r9d, r9d
0x1800161b7  mov     [rbp+phdpa], r9
0x1800161bb  test    r9, r9
0x1800161be  jz      short loc_1800161F9
0x1800161c0  test    rbx, rbx
0x1800161c3  jz      short loc_1800161F9
0x1800161c5  xorps   xmm0, xmm0
0x1800161c8  mov     [rbp+lParam], 0
0x1800161d0  lea     r8, [rbp+lParam]; lParam
0x1800161d4  mov     [rbp+var_10], 0
0x1800161dc  lea     rdx, ?OrderItem_Compare@@YAHPEAX0_J@Z; pfnCompare
0x1800161e3  mov     [rbp+var_28], rbx
0x1800161e7  mov     rcx, r9; hdpa
0x1800161ea  movdqu  [rbp+var_20], xmm0
0x1800161ef  call    cs:__imp_DPA_Sort
0x1800161f5  mov     r9, [rbp+phdpa]
0x1800161f9  mov     rbx, [rsp+50h+arg_0]
0x1800161fe  xor     ecx, ecx
0x180016200  test    r9, r9
0x180016203  mov     [rsi], r9
0x180016206  mov     eax, 80004005h
0x18001620b  cmovnz  eax, ecx
0x18001620e  add     rsp, 50h
0x180016212  pop     rdi
0x180016213  pop     rsi
0x180016214  pop     rbp
0x180016215  retn
```
