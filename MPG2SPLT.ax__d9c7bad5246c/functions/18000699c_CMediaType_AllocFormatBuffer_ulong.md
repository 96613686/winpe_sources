# CMediaType::AllocFormatBuffer(ulong)

- ea: `0x18000699c`
- end: `0x180006a05`
- name: `?AllocFormatBuffer@CMediaType@@QEAAPEAEK@Z`
- size: `105`
- prototype: `unsigned __int8 *(CMediaType *__hidden this, unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180006b54`
- `0x18000ac78`
- `0x18000ad44`
- `0x18001f054`
- `0x18001fff4`

## callees

- `0x18000699c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800069e5`
- `ole32!CoTaskMemFree` at `0x1800069e5`
- `ole32!CoTaskMemAlloc` at `0x1800069be`
- `ole32!CoTaskMemAlloc` at `0x1800069be`

## pseudocode

```c
unsigned __int8 *__fastcall CMediaType::AllocFormatBuffer(CMediaType *this, unsigned int a2)
{
  unsigned __int8 *result; // rax
  unsigned __int8 *v5; // rsi

  if ( *((_DWORD *)this + 18) == a2 )
    return (unsigned __int8 *)*((_QWORD *)this + 10);
  v5 = (unsigned __int8 *)CoTaskMemAlloc(a2);
  if ( v5 )
  {
    if ( *((_DWORD *)this + 18) )
      CoTaskMemFree(*((LPVOID *)this + 10));
    *((_DWORD *)this + 18) = a2;
    result = v5;
    *((_QWORD *)this + 10) = v5;
  }
  else if ( a2 > *((_DWORD *)this + 18) )
  {
    return 0;
  }
  else
  {
    return (unsigned __int8 *)*((_QWORD *)this + 10);
  }
  return result;
}

```

## disassembly

```asm
0x18000699c  mov     [rsp+arg_0], rbx
0x1800069a1  mov     [rsp+arg_8], rsi
0x1800069a6  push    rdi
0x1800069a7  sub     rsp, 20h
0x1800069ab  mov     rbx, rcx
0x1800069ae  mov     edi, edx
0x1800069b0  cmp     [rcx+48h], edx
0x1800069b3  jnz     short loc_1800069BB
0x1800069b5  mov     rax, [rcx+50h]
0x1800069b9  jmp     short loc_1800069F5
0x1800069bb  mov     rcx, rdi; cb
0x1800069be  call    cs:__imp_CoTaskMemAlloc
0x1800069c4  mov     rsi, rax
0x1800069c7  test    rax, rax
0x1800069ca  jnz     short loc_1800069DB
0x1800069cc  cmp     edi, [rbx+48h]
0x1800069cf  ja      short loc_1800069D7
0x1800069d1  mov     rax, [rbx+50h]
0x1800069d5  jmp     short loc_1800069F5
0x1800069d7  xor     eax, eax
0x1800069d9  jmp     short loc_1800069F5
0x1800069db  cmp     dword ptr [rbx+48h], 0
0x1800069df  jz      short loc_1800069EB
0x1800069e1  mov     rcx, [rbx+50h]; pv
0x1800069e5  call    cs:__imp_CoTaskMemFree
0x1800069eb  mov     [rbx+48h], edi
0x1800069ee  mov     rax, rsi
0x1800069f1  mov     [rbx+50h], rsi
0x1800069f5  mov     rbx, [rsp+28h+arg_0]
0x1800069fa  mov     rsi, [rsp+28h+arg_8]
0x1800069ff  add     rsp, 20h
0x180006a03  pop     rdi
0x180006a04  retn
```
