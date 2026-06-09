# DiagHubCommon::ScopeGuard__lambda_8017555b0e8eeaa262dab9ca44e216e7___::_ScopeGuard__lambda_8017555b0e8eeaa262dab9ca44e216e7___

- ea: `0x18000817c`
- end: `0x180008285`
- name: `DiagHubCommon::ScopeGuard__lambda_8017555b0e8eeaa262dab9ca44e216e7___::_ScopeGuard__lambda_8017555b0e8eeaa262dab9ca44e216e7___`
- size: `265`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005530`
- `0x18004b98e`

## callees

- `0x18000817c`
- `0x18003d864`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000824e`
- `ole32!CoTaskMemFree` at `0x180008265`
- `ole32!CoTaskMemFree` at `0x18000824e`
- `ole32!CoTaskMemFree` at `0x180008265`
- `OLEAUT32!__imp_SysFreeString` at `0x1800081fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180008228`
- `OLEAUT32!__imp_SysFreeString` at `0x180008238`
- `OLEAUT32!__imp_SysFreeString` at `0x1800081fc`
- `OLEAUT32!__imp_SysFreeString` at `0x180008228`
- `OLEAUT32!__imp_SysFreeString` at `0x180008238`

## string_xrefs

- `0x1800081cf`: `Removing IStandardCollectorGraphingAgent ({%08x-xxxx-xxxx-xxxx-xxxxxxxxxxxx}) - graph data callback returned 0x%08x`

## pseudocode

```c
void __fastcall DiagHubCommon::ScopeGuard__lambda_8017555b0e8eeaa262dab9ca44e216e7___::_ScopeGuard__lambda_8017555b0e8eeaa262dab9ca44e216e7___(
        int **a1)
{
  __int64 i; // rsi
  __int64 *v3; // rax
  __int64 v4; // r14
  unsigned int v5; // r15d
  char *v6; // rcx
  char *v7; // rax
  __int64 v8; // rbx
  int v9; // [rsp+20h] [rbp-28h]

  if ( **a1 < 0 )
  {
    *((_BYTE *)a1[1] + 8) = 1;
    if ( *((_QWORD *)_logger + 14) != *((_QWORD *)_logger + 15) )
    {
      v9 = **a1;
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 112),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
        L"Removing IStandardCollectorGraphingAgent ({%08x-xxxx-xxxx-xxxx-xxxxxxxxxxxx}) - graph data callback returned 0x%08x",
        (unsigned int)*a1[2],
        v9);
    }
    for ( i = 0; (unsigned int)i < *a1[4]; i = (unsigned int)(i + 1) )
    {
      v3 = (__int64 *)a1[3];
      v4 = *v3;
      SysFreeString(*(BSTR *)(*v3 + 40 * i + 16));
      v5 = 0;
      v6 = *(char **)(v4 + 40 * i + 32);
      if ( v6 )
      {
        v7 = *(char **)(v4 + 40 * i + 32);
        do
        {
          v6 = v7;
          if ( v5 >= *(_DWORD *)(v4 + 40 * i + 24) )
            break;
          v8 = 32LL * v5;
          SysFreeString(*(BSTR *)&v7[v8 + 24]);
          SysFreeString(*(BSTR *)(*(_QWORD *)(v4 + 40 * i + 32) + v8 + 16));
          ++v5;
          v6 = *(char **)(v4 + 40 * i + 32);
          v7 = v6;
        }
        while ( v6 );
      }
      CoTaskMemFree(v6);
    }
    CoTaskMemFree(*(LPVOID *)a1[3]);
  }
}

```

## disassembly

```asm
0x18000817c  mov     [rsp+arg_0], rbx
0x180008181  mov     [rsp+arg_8], rbp
0x180008186  mov     [rsp+arg_10], rsi
0x18000818b  push    rdi
0x18000818c  push    r14
0x18000818e  push    r15
0x180008190  sub     rsp, 30h
0x180008194  mov     rdi, rcx
0x180008197  mov     rax, [rcx]
0x18000819a  cmp     dword ptr [rax], 0
0x18000819d  jge     loc_18000826C
0x1800081a3  mov     rax, [rcx+8]
0x1800081a7  mov     byte ptr [rax+8], 1
0x1800081ab  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800081b2  add     rcx, 70h ; 'p'; this
0x1800081b6  mov     rax, [rcx+8]
0x1800081ba  cmp     [rcx], rax
0x1800081bd  jz      short loc_1800081E2
0x1800081bf  mov     rax, [rdi]
0x1800081c2  mov     r9, [rdi+10h]
0x1800081c6  mov     eax, [rax]
0x1800081c8  mov     [rsp+48h+var_28], eax
0x1800081cc  mov     r9d, [r9]
0x1800081cf  lea     r8, aRemovingIstand_8; "Removing IStandardCollectorGraphingAgen"...
0x1800081d6  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800081dd  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800081e2  xor     esi, esi
0x1800081e4  mov     rax, [rdi+20h]
0x1800081e8  cmp     [rax], esi
0x1800081ea  jbe     short loc_18000825E
0x1800081ec  lea     rbp, [rsi+rsi*4]
0x1800081f0  mov     rax, [rdi+18h]
0x1800081f4  mov     r14, [rax]
0x1800081f7  mov     rcx, [r14+rbp*8+10h]; bstrString
0x1800081fc  call    cs:__imp_SysFreeString
0x180008202  xor     r15d, r15d
0x180008205  mov     rcx, [r14+rbp*8+20h]
0x18000820a  test    rcx, rcx
0x18000820d  jz      short loc_18000824E
0x18000820f  mov     rax, rcx
0x180008212  mov     rcx, rax
0x180008215  cmp     r15d, [r14+rbp*8+18h]
0x18000821a  jnb     short loc_18000824E
0x18000821c  mov     ebx, r15d
0x18000821f  shl     rbx, 5
0x180008223  mov     rcx, [rbx+rax+18h]; bstrString
0x180008228  call    cs:__imp_SysFreeString
0x18000822e  mov     rcx, [r14+rbp*8+20h]
0x180008233  mov     rcx, [rcx+rbx+10h]; bstrString
0x180008238  call    cs:__imp_SysFreeString
0x18000823e  inc     r15d
0x180008241  mov     rcx, [r14+rbp*8+20h]; pv
0x180008246  mov     rax, rcx
0x180008249  test    rcx, rcx
0x18000824c  jnz     short loc_180008212
0x18000824e  call    cs:__imp_CoTaskMemFree
0x180008254  inc     esi
0x180008256  mov     rax, [rdi+20h]
0x18000825a  cmp     esi, [rax]
0x18000825c  jb      short loc_1800081EC
0x18000825e  mov     rcx, [rdi+18h]
0x180008262  mov     rcx, [rcx]; pv
0x180008265  call    cs:__imp_CoTaskMemFree
0x18000826b  nop
0x18000826c  mov     rbx, [rsp+48h+arg_0]
0x180008271  mov     rbp, [rsp+48h+arg_8]
0x180008276  mov     rsi, [rsp+48h+arg_10]
0x18000827b  add     rsp, 30h
0x18000827f  pop     r15
0x180008281  pop     r14
0x180008283  pop     rdi
0x180008284  retn
```
