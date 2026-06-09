# SetVariantAsByteArray(tagVARIANT *,ulong,uchar *)

- ea: `0x180036a90`
- end: `0x180036b2e`
- name: `?SetVariantAsByteArray@@YAJPEAUtagVARIANT@@KPEAE@Z`
- size: `158`
- prototype: `int(struct tagVARIANT *, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180036b40`

## callees

- `0x180023d6e`
- `0x180036a90`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCreate` at `0x180036ad3`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180036ad3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180036af1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180036af1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180036b16`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180036b16`

## pseudocode

```c
__int64 __fastcall SetVariantAsByteArray(struct tagVARIANT *a1, unsigned int a2, unsigned __int8 *a3)
{
  size_t v3; // rdi
  SAFEARRAY *v6; // rax
  unsigned __int64 v8; // [rsp+30h] [rbp+8h] BYREF
  void *ppvData; // [rsp+48h] [rbp+20h] BYREF

  v3 = a2;
  a1->vt = 8209;
  a1->llVal = 0;
  ppvData = 0;
  v8 = a2;
  v6 = SafeArrayCreate(0x11u, 1u, (SAFEARRAYBOUND *)&v8);
  a1->llVal = (LONGLONG)v6;
  if ( !v6 )
    return 2147942414LL;
  if ( SafeArrayAccessData(v6, &ppvData) < 0 )
    return 2147549183LL;
  memcpy_0(ppvData, a3, v3);
  SafeArrayUnaccessData(a1->parray);
  return 0;
}

```

## disassembly

```asm
0x180036a90  mov     rax, rsp
0x180036a93  mov     [rax+10h], rbx
0x180036a97  mov     [rax+18h], rsi
0x180036a9b  push    rdi
0x180036a9c  sub     rsp, 20h
0x180036aa0  mov     edi, edx
0x180036aa2  mov     rbx, rcx
0x180036aa5  mov     word ptr [rcx], 2011h
0x180036aaa  mov     rsi, r8
0x180036aad  mov     qword ptr [rcx+8], 0
0x180036ab5  lea     r8, [rax+8]; rgsabound
0x180036ab9  mov     ecx, 11h; vt
0x180036abe  mov     qword ptr [rax+20h], 0
0x180036ac6  mov     dword ptr [rax+0Ch], 0
0x180036acd  mov     [rax+8], edi
0x180036ad0  lea     edx, [rcx-10h]; cDims
0x180036ad3  call    cs:__imp_SafeArrayCreate
0x180036ad9  mov     [rbx+8], rax
0x180036add  test    rax, rax
0x180036ae0  jnz     short loc_180036AE9
0x180036ae2  mov     eax, 8007000Eh
0x180036ae7  jmp     short loc_180036B1E
0x180036ae9  lea     rdx, [rsp+28h+ppvData]; ppvData
0x180036aee  mov     rcx, rax; psa
0x180036af1  call    cs:__imp_SafeArrayAccessData
0x180036af7  test    eax, eax
0x180036af9  jns     short loc_180036B02
0x180036afb  mov     eax, 8000FFFFh
0x180036b00  jmp     short loc_180036B1E
0x180036b02  mov     rcx, [rsp+28h+ppvData]; void *
0x180036b07  mov     r8, rdi; Size
0x180036b0a  mov     rdx, rsi; Src
0x180036b0d  call    memcpy_0
0x180036b12  mov     rcx, [rbx+8]; psa
0x180036b16  call    cs:__imp_SafeArrayUnaccessData
0x180036b1c  xor     eax, eax
0x180036b1e  mov     rbx, [rsp+28h+arg_8]
0x180036b23  mov     rsi, [rsp+28h+arg_10]
0x180036b28  add     rsp, 20h
0x180036b2c  pop     rdi
0x180036b2d  retn
```
