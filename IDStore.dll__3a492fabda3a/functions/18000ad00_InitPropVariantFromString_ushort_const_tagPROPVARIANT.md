# InitPropVariantFromString(ushort const *,tagPROPVARIANT *)

- ea: `0x18000ad00`
- end: `0x18000ad99`
- name: `?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `153`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800183dc`

## callees

- `0x18000ad00`
- `0x18000fb96`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ad47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ad47`

## pseudocode

```c
__int64 __fastcall InitPropVariantFromString(const unsigned __int16 *Src, struct tagPROPVARIANT *a2)
{
  unsigned __int64 v4; // rax
  size_t v5; // rsi
  void *v6; // rax
  LARGE_INTEGER v7; // rdi
  __int64 result; // rax

  v4 = -1;
  do
    ++v4;
  while ( Src[v4] );
  if ( v4 < 0x7FFFFFFF && (v5 = 2 * v4 + 2, v6 = CoTaskMemAlloc(v5), (v7.QuadPart = (LONGLONG)v6) != 0) )
  {
    memcpy_0(v6, Src, v5);
    result = 0;
    a2->vt = 31;
    a2->hVal = v7;
  }
  else
  {
    *(_OWORD *)&a2->vt = 0;
    a2->bstrblobVal.pData = 0;
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000ad00  mov     [rsp+arg_10], rbx
0x18000ad05  push    r14
0x18000ad07  sub     rsp, 20h
0x18000ad0b  mov     r14, rdx
0x18000ad0e  mov     rbx, rcx
0x18000ad11  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000ad18  nop     dword ptr [rax+rax+00000000h]
0x18000ad20  inc     rax
0x18000ad23  cmp     word ptr [rcx+rax*2], 0
0x18000ad28  jnz     short loc_18000AD20
0x18000ad2a  mov     [rsp+28h+arg_0], rsi
0x18000ad2f  mov     [rsp+28h+arg_8], rdi
0x18000ad34  cmp     rax, 7FFFFFFFh
0x18000ad3a  jnb     short loc_18000AD85
0x18000ad3c  lea     rsi, ds:2[rax*2]
0x18000ad44  mov     rcx, rsi; cb
0x18000ad47  call    cs:__imp_CoTaskMemAlloc
0x18000ad4d  mov     rdi, rax
0x18000ad50  test    rax, rax
0x18000ad53  jz      short loc_18000AD85
0x18000ad55  mov     r8, rsi; Size
0x18000ad58  mov     rdx, rbx; Src
0x18000ad5b  mov     rcx, rax; void *
0x18000ad5e  call    memcpy_0
0x18000ad63  xor     eax, eax
0x18000ad65  mov     word ptr [r14], 1Fh
0x18000ad6b  mov     [r14+8], rdi
0x18000ad6f  mov     rdi, [rsp+28h+arg_8]
0x18000ad74  mov     rsi, [rsp+28h+arg_0]
0x18000ad79  mov     rbx, [rsp+28h+arg_10]
0x18000ad7e  add     rsp, 20h
0x18000ad82  pop     r14
0x18000ad84  retn
0x18000ad85  xorps   xmm0, xmm0
0x18000ad88  xor     ecx, ecx
0x18000ad8a  movups  xmmword ptr [r14], xmm0
0x18000ad8e  mov     [r14+10h], rcx
0x18000ad92  mov     eax, 8007000Eh
0x18000ad97  jmp     short loc_18000AD6F
```
