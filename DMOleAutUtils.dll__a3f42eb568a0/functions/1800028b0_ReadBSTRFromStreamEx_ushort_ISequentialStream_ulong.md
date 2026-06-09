# ReadBSTRFromStreamEx(ushort * *,ISequentialStream *,ulong)

- ea: `0x1800028b0`
- end: `0x1800029c2`
- name: `?ReadBSTRFromStreamEx@@YAJPEAPEAGPEAUISequentialStream@@K@Z`
- size: `274`
- prototype: `__int64 __fastcall(unsigned __int16 **, struct ISequentialStream *, UINT)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800028a0`
- `0x180002d30`

## callees

- `0x180001cbc`
- `0x180001cc8`
- `0x1800028b0`
- `0x180004010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800029a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800029a6`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180002987`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180002987`

## pseudocode

```c
__int64 __fastcall ReadBSTRFromStreamEx(unsigned __int16 **a1, struct ISequentialStream *a2, UINT a3)
{
  CHAR *v3; // rdi
  int v7; // ebx
  CHAR *v8; // rax
  unsigned __int16 *v9; // rax
  UINT len; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  len = 0;
  v12 = 0;
  if ( a1 && a2 )
  {
    v7 = ((__int64 (__fastcall *)(struct ISequentialStream *, UINT *, __int64, int *))a2->lpVtbl->Read)(
           a2,
           &len,
           4,
           &v12);
    if ( v7 >= 0 )
    {
      if ( v12 == 4 )
      {
        if ( a3 < len || a3 - len < 4 )
        {
          v7 = -2147024362;
          goto LABEL_17;
        }
        if ( (len & 1) == 0 )
        {
          v8 = (CHAR *)operator new[](len, (const struct std::nothrow_t *)&std::nothrow);
          v3 = v8;
          if ( !v8 )
          {
LABEL_11:
            v7 = -2147024882;
            goto LABEL_17;
          }
          v7 = ((__int64 (__fastcall *)(struct ISequentialStream *, CHAR *, _QWORD, int *))a2->lpVtbl->Read)(
                 a2,
                 v8,
                 len,
                 &v12);
          if ( v7 < 0 )
            goto LABEL_17;
          if ( len == v12 )
          {
            v9 = SysAllocStringByteLen(v3, len);
            if ( v9 )
            {
              *a1 = v9;
              goto LABEL_17;
            }
            goto LABEL_11;
          }
        }
      }
      v7 = -2147467259;
    }
  }
  else
  {
    v7 = -2147467261;
  }
LABEL_17:
  operator delete(v3);
  SysFreeString(0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800028b0  mov     rax, rsp
0x1800028b3  mov     [rax+10h], rbx
0x1800028b7  mov     [rax+18h], rsi
0x1800028bb  push    rdi
0x1800028bc  push    r14
0x1800028be  push    r15
0x1800028c0  sub     rsp, 30h
0x1800028c4  xor     edi, edi
0x1800028c6  mov     dword ptr [rax+8], 0
0x1800028cd  mov     dword ptr [rax+20h], 0
0x1800028d4  mov     esi, r8d
0x1800028d7  mov     r14, rdx
0x1800028da  mov     r15, rcx
0x1800028dd  test    rcx, rcx
0x1800028e0  jnz     short loc_1800028EC
0x1800028e2  mov     ebx, 80004003h
0x1800028e7  jmp     loc_18000299C
0x1800028ec  test    r14, r14
0x1800028ef  jz      short loc_1800028E2
0x1800028f1  mov     rax, [rdx]
0x1800028f4  lea     r9, [rsp+48h+arg_18]
0x1800028f9  mov     r8d, 4
0x1800028ff  lea     rdx, [rsp+48h+len]
0x180002904  mov     rcx, r14
0x180002907  mov     rax, [rax+18h]
0x18000290b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002910  mov     ebx, eax
0x180002912  test    eax, eax
0x180002914  js      loc_18000299C
0x18000291a  cmp     [rsp+48h+arg_18], 4
0x18000291f  jz      short loc_180002928
0x180002921  mov     ebx, 80004005h
0x180002926  jmp     short loc_18000299C
0x180002928  mov     eax, [rsp+48h+len]
0x18000292c  cmp     esi, eax
0x18000292e  jb      short loc_180002997
0x180002930  sub     esi, eax
0x180002932  cmp     esi, 4
0x180002935  jb      short loc_180002997
0x180002937  test    al, 1
0x180002939  jnz     short loc_180002921
0x18000293b  mov     ecx, eax; unsigned __int64
0x18000293d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002944  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180002949  mov     rdi, rax
0x18000294c  test    rax, rax
0x18000294f  jnz     short loc_180002958
0x180002951  mov     ebx, 8007000Eh
0x180002956  jmp     short loc_18000299C
0x180002958  mov     rax, [r14]
0x18000295b  lea     r9, [rsp+48h+arg_18]
0x180002960  mov     r8d, [rsp+48h+len]
0x180002965  mov     rdx, rdi
0x180002968  mov     rcx, r14
0x18000296b  mov     rax, [rax+18h]
0x18000296f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002974  mov     ebx, eax
0x180002976  test    eax, eax
0x180002978  js      short loc_18000299C
0x18000297a  mov     edx, [rsp+48h+len]; len
0x18000297e  cmp     edx, [rsp+48h+arg_18]
0x180002982  jnz     short loc_180002921
0x180002984  mov     rcx, rdi; psz
0x180002987  call    cs:__imp_SysAllocStringByteLen
0x18000298d  test    rax, rax
0x180002990  jz      short loc_180002951
0x180002992  mov     [r15], rax
0x180002995  jmp     short loc_18000299C
0x180002997  mov     ebx, 80070216h
0x18000299c  mov     rcx, rdi; Block
0x18000299f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800029a4  xor     ecx, ecx; bstrString
0x1800029a6  call    cs:__imp_SysFreeString
0x1800029ac  mov     rsi, [rsp+48h+arg_10]
0x1800029b1  mov     eax, ebx
0x1800029b3  mov     rbx, [rsp+48h+arg_8]
0x1800029b8  add     rsp, 30h
0x1800029bc  pop     r15
0x1800029be  pop     r14
0x1800029c0  pop     rdi
0x1800029c1  retn
```
