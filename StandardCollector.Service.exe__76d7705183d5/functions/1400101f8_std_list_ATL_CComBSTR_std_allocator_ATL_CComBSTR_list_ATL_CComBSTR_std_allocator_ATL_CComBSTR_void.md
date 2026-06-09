# std::list<ATL::CComBSTR,std::allocator<ATL::CComBSTR>>::~list<ATL::CComBSTR,std::allocator<ATL::CComBSTR>>(void)

- ea: `0x1400101f8`
- end: `0x14001025e`
- name: `??1?$list@VCComBSTR@ATL@@V?$allocator@VCComBSTR@ATL@@@std@@@std@@QEAA@XZ`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140015890`
- `0x140015c50`

## callees

- `0x1400101f8`
- `0x14001382c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140010227`
- `OLEAUT32!__imp_SysFreeString` at `0x140010227`

## pseudocode

```c
void __fastcall std::list<ATL::CComBSTR>::~list<ATL::CComBSTR>(void **a1)
{
  void **v1; // rdx
  BSTR *v3; // rdi
  BSTR v4; // rbx

  v1 = (void **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = (BSTR *)*v1;
  if ( *v1 )
  {
    do
    {
      v4 = *v3;
      SysFreeString(v3[2]);
      operator delete(v3);
      v3 = (BSTR *)v4;
    }
    while ( v4 );
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x1400101f8  mov     [rsp+arg_8], rbx
0x1400101fd  mov     [rsp+arg_10], rsi
0x140010202  push    rdi
0x140010203  sub     rsp, 20h
0x140010207  mov     rdx, [rcx]
0x14001020a  mov     rsi, rcx
0x14001020d  mov     rax, [rdx+8]
0x140010211  mov     qword ptr [rax], 0
0x140010218  mov     rdi, [rdx]
0x14001021b  test    rdi, rdi
0x14001021e  jz      short loc_140010242
0x140010220  mov     rcx, [rdi+10h]; bstrString
0x140010224  mov     rbx, [rdi]
0x140010227  call    cs:__imp_SysFreeString
0x14001022d  mov     edx, 18h
0x140010232  mov     rcx, rdi; Block
0x140010235  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001023a  mov     rdi, rbx
0x14001023d  test    rbx, rbx
0x140010240  jnz     short loc_140010220
0x140010242  mov     rcx, [rsi]; Block
0x140010245  mov     edx, 18h
0x14001024a  mov     rbx, [rsp+28h+arg_8]
0x14001024f  mov     rsi, [rsp+28h+arg_10]
0x140010254  add     rsp, 20h
0x140010258  pop     rdi
0x140010259  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
