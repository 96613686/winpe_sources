# wil::details::ScopeExitFn__lambda_6d7c75502897615018b925a2c4a14103___::_ScopeExitFn__lambda_6d7c75502897615018b925a2c4a14103___

- ea: `0x18002e784`
- end: `0x18002e80e`
- name: `wil::details::ScopeExitFn__lambda_6d7c75502897615018b925a2c4a14103___::_ScopeExitFn__lambda_6d7c75502897615018b925a2c4a14103___`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800506fa`

## callees

- `0x18002e784`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002e7bd`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e7bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e7e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e7e7`

## pseudocode

```c
LPVOID *__fastcall wil::details::ScopeExitFn__lambda_6d7c75502897615018b925a2c4a14103___::_ScopeExitFn__lambda_6d7c75502897615018b925a2c4a14103___(
        __int64 a1)
{
  LPVOID *result; // rax
  __int64 i; // rsi

  if ( *(_BYTE *)(a1 + 16) )
  {
    *(_BYTE *)(a1 + 16) = 0;
    result = *(LPVOID **)a1;
    if ( **(_QWORD **)a1 )
    {
      for ( i = 0; (unsigned int)i < **(_DWORD **)(a1 + 8); i = (unsigned int)(i + 1) )
      {
        SysFreeString(*(BSTR *)(**(_QWORD **)a1 + 8 * i));
        *(_QWORD *)(**(_QWORD **)a1 + 8 * i) = 0;
      }
      CoTaskMemFree(**(LPVOID **)a1);
      result = *(LPVOID **)a1;
      **(_QWORD **)a1 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002e784  mov     [rsp+arg_0], rbx
0x18002e789  mov     [rsp+arg_8], rsi
0x18002e78e  push    rdi
0x18002e78f  sub     rsp, 20h
0x18002e793  cmp     byte ptr [rcx+10h], 0
0x18002e797  mov     rdi, rcx
0x18002e79a  jz      short loc_18002E7FD
0x18002e79c  mov     byte ptr [rcx+10h], 0
0x18002e7a0  mov     rax, [rcx]
0x18002e7a3  cmp     qword ptr [rax], 0
0x18002e7a7  jz      short loc_18002E7FD
0x18002e7a9  mov     rax, [rcx+8]
0x18002e7ad  xor     esi, esi
0x18002e7af  cmp     [rax], esi
0x18002e7b1  jbe     short loc_18002E7E1
0x18002e7b3  mov     rax, [rdi]
0x18002e7b6  mov     rcx, [rax]
0x18002e7b9  mov     rcx, [rcx+rsi*8]; bstrString
0x18002e7bd  call    cs:__imp_SysFreeString
0x18002e7c4  nop     dword ptr [rax+rax+00h]
0x18002e7c9  mov     rax, [rdi]
0x18002e7cc  mov     rcx, [rax]
0x18002e7cf  mov     qword ptr [rcx+rsi*8], 0
0x18002e7d7  inc     esi
0x18002e7d9  mov     rax, [rdi+8]
0x18002e7dd  cmp     esi, [rax]
0x18002e7df  jb      short loc_18002E7B3
0x18002e7e1  mov     rcx, [rdi]
0x18002e7e4  mov     rcx, [rcx]; pv
0x18002e7e7  call    cs:__imp_CoTaskMemFree
0x18002e7ee  nop     dword ptr [rax+rax+00h]
0x18002e7f3  mov     rax, [rdi]
0x18002e7f6  mov     qword ptr [rax], 0
0x18002e7fd  mov     rbx, [rsp+28h+arg_0]
0x18002e802  mov     rsi, [rsp+28h+arg_8]
0x18002e807  add     rsp, 20h
0x18002e80b  pop     rdi
0x18002e80c  retn
```
