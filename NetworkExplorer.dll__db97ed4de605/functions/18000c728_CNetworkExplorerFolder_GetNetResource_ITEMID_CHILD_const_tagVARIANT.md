# CNetworkExplorerFolder::_GetNetResource(_ITEMID_CHILD const *,tagVARIANT *)

- ea: `0x18000c728`
- end: `0x18000c870`
- name: `?_GetNetResource@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMID_CHILD@@PEAUtagVARIANT@@@Z`
- size: `328`
- prototype: `int(CNetworkExplorerFolder *__hidden this, const struct _ITEMID_CHILD *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006030`

## callees

- `0x1800053b0`
- `0x18000bdbc`
- `0x18000be6c`
- `0x18000c728`
- `0x18000f076`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c853`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c853`
- `OLEAUT32!__imp_VariantClear` at `0x18000c849`
- `OLEAUT32!__imp_VariantClear` at `0x18000c849`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000c778`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000c778`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerFolder::_GetNetResource(
        CNetworkExplorerFolder *this,
        const struct _ITEMID_CHILD *a2,
        struct tagVARIANT *a3)
{
  int ComputerName; // edi
  SAFEARRAY *Vector; // rax
  LONGLONG llVal; // rax
  __int64 v7; // rsi
  unsigned __int16 *v8; // rbx
  const unsigned __int16 *v9; // r8
  unsigned __int64 v10; // rdx
  unsigned int v12; // [rsp+28h] [rbp-28h]
  LPVOID pv; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v14; // [rsp+70h] [rbp+20h] BYREF
  unsigned __int16 *v15; // [rsp+88h] [rbp+38h] BYREF

  v14 = (unsigned __int64)this;
  pv = 0;
  ComputerName = CNetworkExplorerFolder::_GetComputerName(this, a2, (unsigned __int16 **)&pv);
  if ( ComputerName >= 0 )
  {
    v14 = 1040;
    Vector = SafeArrayCreateVector(0x11u, 0, 0x850u);
    if ( Vector )
    {
      a3->vt = 8209;
      a3->llVal = (LONGLONG)Vector;
      memset_0(Vector->pvData, 0, 0x850u);
      llVal = a3->llVal;
      v15 = 0;
      v7 = *(_QWORD *)(llVal + 16);
      *(_DWORD *)(v7 + 4) = 0;
      v8 = (unsigned __int16 *)(v7 + 48);
      *(_DWORD *)(v7 + 8) = 2;
      *(_DWORD *)(v7 + 12) = 2;
      ComputerName = StringCchPrintfExW((STRSAFE_LPWSTR)(v7 + 48), 0x410u, &v15, &v14, 0, L"\\\\%s");
      if ( ComputerName < 0 )
        goto LABEL_9;
      v10 = v14;
      *(_QWORD *)(v7 + 24) = v8;
      if ( v10 )
      {
        v8 = v15 + 1;
        --v10;
        ++v15;
        v14 = v10;
      }
      ComputerName = StringCchCopyExW(v8, v10, v9, &v15, &v14, v12);
      if ( ComputerName < 0 )
LABEL_9:
        VariantClear(a3);
      else
        *(_QWORD *)(v7 + 40) = v8;
    }
    else
    {
      ComputerName = -2147024882;
    }
    CoTaskMemFree(pv);
  }
  return (unsigned int)ComputerName;
}

```

## disassembly

```asm
0x18000c728  mov     [rsp-18h+arg_8], rbx
0x18000c72d  mov     [rsp-18h+arg_10], rsi
0x18000c732  mov     [rsp-18h+arg_0], rcx
0x18000c737  push    rbp
0x18000c738  push    rdi
0x18000c739  push    r14
0x18000c73b  mov     rbp, rsp
0x18000c73e  sub     rsp, 50h
0x18000c742  mov     r14, r8
0x18000c745  mov     [rbp+pv], 0
0x18000c74d  lea     r8, [rbp+pv]; unsigned __int16 **
0x18000c751  call    ?_GetComputerName@CNetworkExplorerFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAG@Z; CNetworkExplorerFolder::_GetComputerName(_ITEMIDLIST_RELATIVE const *,ushort * *)
0x18000c756  mov     edi, eax
0x18000c758  test    eax, eax
0x18000c75a  js      loc_18000C859
0x18000c760  mov     ebx, 850h
0x18000c765  mov     edi, 410h
0x18000c76a  mov     r8d, ebx; cElements
0x18000c76d  mov     [rbp+arg_0], rdi
0x18000c771  mov     ecx, 11h; vt
0x18000c776  xor     edx, edx; lLbound
0x18000c778  call    cs:__imp_SafeArrayCreateVector
0x18000c77e  test    rax, rax
0x18000c781  jnz     short loc_18000C78D
0x18000c783  mov     edi, 8007000Eh
0x18000c788  jmp     loc_18000C84F
0x18000c78d  mov     word ptr [r14], 2011h
0x18000c793  mov     r8, rbx; Size
0x18000c796  mov     [r14+8], rax
0x18000c79a  xor     edx, edx; Val
0x18000c79c  mov     rcx, [rax+10h]; void *
0x18000c7a0  call    memset_0
0x18000c7a5  mov     rax, [r14+8]
0x18000c7a9  lea     r9, [rbp+arg_0]; unsigned __int64 *
0x18000c7ad  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x18000c7b1  mov     [rbp+arg_18], 0
0x18000c7b9  mov     rdx, rdi; unsigned __int64
0x18000c7bc  mov     rsi, [rax+10h]
0x18000c7c0  mov     dword ptr [rsi+4], 0
0x18000c7c7  lea     rbx, [rsi+30h]
0x18000c7cb  mov     dword ptr [rsi+8], 2
0x18000c7d2  mov     rcx, rbx; pszDest
0x18000c7d5  mov     dword ptr [rsi+0Ch], 2
0x18000c7dc  mov     rax, [rbp+pv]
0x18000c7e0  mov     [rsp+50h+var_20], rax
0x18000c7e5  lea     rax, aS; "\\\\%s"
0x18000c7ec  mov     [rsp+50h+var_28], rax; unsigned int
0x18000c7f1  mov     [rsp+50h+var_30], 0; unsigned int
0x18000c7fa  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18000c7ff  mov     edi, eax
0x18000c801  test    eax, eax
0x18000c803  js      short loc_18000C846
0x18000c805  mov     rdx, [rbp+arg_0]
0x18000c809  mov     [rsi+18h], rbx
0x18000c80d  test    rdx, rdx
0x18000c810  jz      short loc_18000C825
0x18000c812  mov     rbx, [rbp+arg_18]
0x18000c816  add     rbx, 2
0x18000c81a  dec     rdx; unsigned __int64
0x18000c81d  mov     [rbp+arg_18], rbx
0x18000c821  mov     [rbp+arg_0], rdx
0x18000c825  lea     rax, [rbp+arg_0]
0x18000c829  mov     rcx, rbx; unsigned __int16 *
0x18000c82c  lea     r9, [rbp+arg_18]; unsigned __int16 **
0x18000c830  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x18000c835  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18000c83a  mov     edi, eax
0x18000c83c  test    eax, eax
0x18000c83e  js      short loc_18000C846
0x18000c840  mov     [rsi+28h], rbx
0x18000c844  jmp     short loc_18000C84F
0x18000c846  mov     rcx, r14; pvarg
0x18000c849  call    cs:__imp_VariantClear
0x18000c84f  mov     rcx, [rbp+pv]; pv
0x18000c853  call    cs:__imp_CoTaskMemFree
0x18000c859  lea     r11, [rsp+50h+var_s0]
0x18000c85e  mov     eax, edi
0x18000c860  mov     rbx, [r11+28h]
0x18000c864  mov     rsi, [r11+30h]
0x18000c868  mov     rsp, r11
0x18000c86b  pop     r14
0x18000c86d  pop     rdi
0x18000c86e  pop     rbp
0x18000c86f  retn
```
