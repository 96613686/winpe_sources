# GetFaxPrinterName(void *)

- ea: `0x18001a7a0`
- end: `0x18001a825`
- name: `?GetFaxPrinterName@@YAPEAGPEAX@Z`
- size: `133`
- prototype: `unsigned __int16 *__fastcall(void *)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016de4`
- `0x18001a82c`
- `0x18001ad28`
- `0x18001ba58`
- `0x180025df0`

## callees

- `0x18001a7a0`
- `0x18002fe1c`
- `0x18003d510`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001a7f4`
- `msvcrt!_wcsicmp` at `0x18001a7f4`
- `KERNEL32!GetComputerNameW` at `0x18001a7dc`
- `KERNEL32!GetComputerNameW` at `0x18001a7dc`

## pseudocode

```c
unsigned __int16 *__fastcall GetFaxPrinterName(_QWORD *a1, __int64 a2)
{
  __int64 v2; // r8
  const wchar_t *v3; // rbx
  DWORD nSize; // [rsp+20h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+28h] [rbp-30h] BYREF

  v2 = 0;
  if ( !a1 )
    return (unsigned __int16 *)GetFaxPrinterNameOnServer(a1, a2, v2);
  v3 = *(const wchar_t **)(a1[4] + 72LL);
  if ( !v3 )
    return (unsigned __int16 *)GetFaxPrinterNameOnServer(a1, a2, v2);
  nSize = 16;
  if ( GetComputerNameW(Buffer, &nSize) )
  {
    v2 = (unsigned __int64)v3 & -(__int64)(_wcsicmp(Buffer, v3) != 0);
    return (unsigned __int16 *)GetFaxPrinterNameOnServer(a1, a2, v2);
  }
  return 0;
}

```

## disassembly

```asm
0x18001a7a0  push    rbx
0x18001a7a2  sub     rsp, 50h
0x18001a7a6  mov     rax, cs:__security_cookie
0x18001a7ad  xor     rax, rsp
0x18001a7b0  mov     [rsp+58h+var_10], rax
0x18001a7b5  xor     r8d, r8d
0x18001a7b8  test    rcx, rcx
0x18001a7bb  jz      short loc_18001A808
0x18001a7bd  mov     rax, [rcx+20h]
0x18001a7c1  mov     rbx, [rax+48h]
0x18001a7c5  test    rbx, rbx
0x18001a7c8  jz      short loc_18001A808
0x18001a7ca  lea     rdx, [rsp+58h+nSize]; nSize
0x18001a7cf  mov     [rsp+58h+nSize], 10h
0x18001a7d7  lea     rcx, [rsp+58h+Buffer]; lpBuffer
0x18001a7dc  call    cs:__imp_GetComputerNameW
0x18001a7e3  nop     dword ptr [rax+rax+00h]
0x18001a7e8  test    eax, eax
0x18001a7ea  jz      short loc_18001A821
0x18001a7ec  mov     rdx, rbx; String2
0x18001a7ef  lea     rcx, [rsp+58h+Buffer]; String1
0x18001a7f4  call    cs:__imp__wcsicmp
0x18001a7fb  nop     dword ptr [rax+rax+00h]
0x18001a800  neg     eax
0x18001a802  sbb     r8, r8
0x18001a805  and     r8, rbx
0x18001a808  call    GetFaxPrinterNameOnServer
0x18001a80d  mov     rcx, [rsp+58h+var_10]
0x18001a812  xor     rcx, rsp; StackCookie
0x18001a815  call    __security_check_cookie
0x18001a81a  add     rsp, 50h
0x18001a81e  pop     rbx
0x18001a81f  retn
0x18001a821  xor     eax, eax
0x18001a823  jmp     short loc_18001A80D
```
