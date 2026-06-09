# _com_issue_errorex(long,IUnknown *,_GUID const &)

- ea: `0x180036b04`
- end: `0x180036b96`
- name: `?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z`
- size: `146`
- prototype: `void __fastcall __noreturn(int, struct IUnknown *, const struct _GUID *)`
- caller_count: `47`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003e60`
- `0x180003fa0`
- `0x180004220`
- `0x180005380`
- `0x180005ad0`
- `0x180005b50`
- `0x180007a20`
- `0x1800083e0`
- `0x180008680`
- `0x180016540`
- `0x18001681c`
- `0x180016bf4`
- `0x180017aa4`
- `0x180018860`
- `0x180019a6c`
- `0x18001a5f4`
- `0x18002b720`
- `0x18002c2a0`
- `0x18002cd48`
- `0x18002d9c0`
- `0x180030a3c`
- `0x180031d50`
- `0x180032594`
- `0x18003a2a0`
- `0x18003a5b0`
- `0x18003a5fc`
- `0x18003a854`
- `0x18003b510`
- `0x18003b808`
- `0x180049c00`
- `0x18004ee2c`
- `0x18004fe50`
- `0x18004fe88`
- `0x18004feec`
- `0x18004ff24`
- `0x180051e88`
- `0x180051ed0`
- `0x180051fe8`
- `0x180052098`
- `0x1800520ec`
- `0x180052168`
- `0x180052660`
- `0x1800541b8`
- `0x180054e8c`
- `0x180059f80`
- `0x18005a590`
- `0x18005a7d0`

## callees

- `0x180036b04`
- `0x180036b9c`
- `0x1800b0010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x180036b76`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180036b76`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall __noreturn _com_issue_errorex(int a1, struct IUnknown *a2, const struct _GUID *a3)
{
  struct IErrorInfo *v5; // rdx
  struct IUnknownVtbl *lpVtbl; // rax
  int v8; // ebx
  __int64 v9; // [rsp+38h] [rbp+10h] BYREF
  IErrorInfo *pperrinfo; // [rsp+48h] [rbp+20h] BYREF

  v5 = 0;
  pperrinfo = 0;
  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    v9 = 0;
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
           a2,
           &GUID_df0b3d60_548f_101b_8e65_08002b2bd119,
           &v9) < 0
      || (v8 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *))(*(_QWORD *)v9 + 24LL))(v9, a3),
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9),
          v8)
      || !GetErrorInfo(0, &pperrinfo) )
    {
      v5 = pperrinfo;
    }
    else
    {
      v5 = 0;
      pperrinfo = 0;
    }
  }
  _com_raise_error(a1, v5);
}

```

## disassembly

```asm
0x180036b04  mov     r11, rsp
0x180036b07  mov     [r11+8], rbx
0x180036b0b  push    rdi
0x180036b0c  sub     rsp, 20h
0x180036b10  mov     r9, rdx
0x180036b13  mov     rbx, r8
0x180036b16  xor     edx, edx
0x180036b18  mov     edi, ecx
0x180036b1a  mov     [r11+20h], rdx
0x180036b1e  test    r9, r9
0x180036b21  jz      short loc_180036B8E
0x180036b23  mov     rax, [r9]
0x180036b26  lea     r8, [r11+10h]
0x180036b2a  mov     [r11+10h], rdx
0x180036b2e  mov     rcx, r9
0x180036b31  lea     rdx, _GUID_df0b3d60_548f_101b_8e65_08002b2bd119
0x180036b38  mov     rax, [rax]
0x180036b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b40  test    eax, eax
0x180036b42  js      short loc_180036B89
0x180036b44  mov     rcx, [rsp+28h+arg_8]
0x180036b49  mov     rdx, rbx
0x180036b4c  mov     rax, [rcx]
0x180036b4f  mov     rax, [rax+18h]
0x180036b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b58  mov     rcx, [rsp+28h+arg_8]
0x180036b5d  mov     ebx, eax
0x180036b5f  mov     rdx, [rcx]
0x180036b62  mov     rax, [rdx+10h]
0x180036b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036b6b  test    ebx, ebx
0x180036b6d  jnz     short loc_180036B89
0x180036b6f  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x180036b74  xor     ecx, ecx; dwReserved
0x180036b76  call    cs:__imp_GetErrorInfo
0x180036b7c  test    eax, eax
0x180036b7e  jz      short loc_180036B89
0x180036b80  xor     edx, edx
0x180036b82  mov     [rsp+28h+pperrinfo], rdx
0x180036b87  jmp     short loc_180036B8E
0x180036b89  mov     rdx, [rsp+28h+pperrinfo]; struct IErrorInfo *
0x180036b8e  mov     ecx, edi; int
0x180036b90  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
