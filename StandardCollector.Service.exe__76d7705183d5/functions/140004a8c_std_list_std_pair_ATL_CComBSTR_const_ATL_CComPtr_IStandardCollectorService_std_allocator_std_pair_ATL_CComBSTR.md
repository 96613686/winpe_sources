# std::list<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>>::~list<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>>(void)

- ea: `0x140004a8c`
- end: `0x140004b09`
- name: `??1?$list@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@@2@@std@@QEAA@XZ`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140004958`
- `0x140014e12`

## callees

- `0x140004a8c`
- `0x14001382c`
- `0x140014c70`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140004ad2`
- `OLEAUT32!__imp_SysFreeString` at `0x140004ad2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::list<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>::~list<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>>(
        void **a1)
{
  void **v2; // rdx
  void *v3; // rbx
  void *v4; // rsi
  __int64 v5; // rcx

  v2 = (void **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = *v2;
  if ( *v2 )
  {
    do
    {
      v4 = *(void **)v3;
      v5 = *((_QWORD *)v3 + 3);
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      SysFreeString(*((BSTR *)v3 + 2));
      operator delete(v3);
      v3 = v4;
    }
    while ( v4 );
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x140004a8c  mov     [rsp+arg_8], rbx
0x140004a91  mov     [rsp+arg_10], rsi
0x140004a96  push    rdi
0x140004a97  sub     rsp, 20h
0x140004a9b  mov     rdi, rcx
0x140004a9e  mov     rdx, [rcx]
0x140004aa1  mov     rax, [rdx+8]
0x140004aa5  mov     qword ptr [rax], 0
0x140004aac  mov     rbx, [rdx]
0x140004aaf  test    rbx, rbx
0x140004ab2  jz      short loc_140004AED
0x140004ab4  mov     rsi, [rbx]
0x140004ab7  mov     rcx, [rbx+18h]
0x140004abb  test    rcx, rcx
0x140004abe  jz      short loc_140004ACE
0x140004ac0  mov     rax, [rcx]
0x140004ac3  mov     rax, [rax+10h]
0x140004ac7  call    cs:__guard_dispatch_icall_fptr
0x140004acd  nop
0x140004ace  mov     rcx, [rbx+10h]; bstrString
0x140004ad2  call    cs:__imp_SysFreeString
0x140004ad8  mov     edx, 20h ; ' '
0x140004add  mov     rcx, rbx; Block
0x140004ae0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004ae5  mov     rbx, rsi
0x140004ae8  test    rsi, rsi
0x140004aeb  jnz     short loc_140004AB4
0x140004aed  mov     edx, 20h ; ' '
0x140004af2  mov     rcx, [rdi]; Block
0x140004af5  mov     rbx, [rsp+28h+arg_8]
0x140004afa  mov     rsi, [rsp+28h+arg_10]
0x140004aff  add     rsp, 20h
0x140004b03  pop     rdi
0x140004b04  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
