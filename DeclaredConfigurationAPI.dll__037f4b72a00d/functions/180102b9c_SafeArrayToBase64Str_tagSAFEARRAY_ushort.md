# SafeArrayToBase64Str(tagSAFEARRAY *,ushort * *)

- ea: `0x180102b9c`
- end: `0x180102c41`
- name: `?SafeArrayToBase64Str@@YAJPEAUtagSAFEARRAY@@PEAPEAG@Z`
- size: `165`
- prototype: `__int64 __fastcall(SAFEARRAY *psa, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180014850`
- `0x18005adc8`
- `0x1800b7b20`
- `0x180121750`

## callees

- `0x180102b9c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102c18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180102c18`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180102bf0`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180102bf0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180102bd7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180102bd7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180102c29`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180102c29`
- `DMCmnUtils!EncodeBase64W` at `0x180102c0e`
- `DMCmnUtils!EncodeBase64W` at `0x180102c0e`

## pseudocode

```c
__int64 __fastcall SafeArrayToBase64Str(SAFEARRAY *psa, unsigned __int16 **a2)
{
  HRESULT UBound; // ebx
  LONG plUbound; // [rsp+30h] [rbp+8h] BYREF
  void *ppvData; // [rsp+40h] [rbp+18h] BYREF

  ppvData = 0;
  plUbound = 0;
  if ( psa && a2 )
  {
    UBound = SafeArrayAccessData(psa, &ppvData);
    if ( UBound >= 0 )
    {
      UBound = SafeArrayGetUBound(psa, 1u, &plUbound);
      if ( UBound >= 0 )
        UBound = EncodeBase64W((const unsigned __int8 *)ppvData, ++plUbound, a2);
    }
  }
  else
  {
    UBound = -2147024809;
  }
  LocalFree(0);
  if ( ppvData )
    SafeArrayUnaccessData(psa);
  return (unsigned int)UBound;
}

```

## disassembly

```asm
0x180102b9c  mov     rax, rsp
0x180102b9f  mov     [rax+10h], rbx
0x180102ba3  mov     [rax+20h], rsi
0x180102ba7  push    rdi
0x180102ba8  sub     rsp, 20h
0x180102bac  mov     qword ptr [rax+18h], 0
0x180102bb4  mov     rsi, rdx
0x180102bb7  mov     dword ptr [rax+8], 0
0x180102bbe  mov     rdi, rcx
0x180102bc1  test    rcx, rcx
0x180102bc4  jnz     short loc_180102BCD
0x180102bc6  mov     ebx, 80070057h
0x180102bcb  jmp     short loc_180102C16
0x180102bcd  test    rsi, rsi
0x180102bd0  jz      short loc_180102BC6
0x180102bd2  lea     rdx, [rsp+28h+ppvData]; ppvData
0x180102bd7  call    cs:__imp_SafeArrayAccessData
0x180102bdd  mov     ebx, eax
0x180102bdf  test    eax, eax
0x180102be1  js      short loc_180102C16
0x180102be3  lea     r8, [rsp+28h+plUbound]; plUbound
0x180102be8  mov     edx, 1; nDim
0x180102bed  mov     rcx, rdi; psa
0x180102bf0  call    cs:__imp_SafeArrayGetUBound
0x180102bf6  mov     ebx, eax
0x180102bf8  test    eax, eax
0x180102bfa  js      short loc_180102C16
0x180102bfc  mov     edx, [rsp+28h+plUbound]
0x180102c00  mov     r8, rsi
0x180102c03  mov     rcx, [rsp+28h+ppvData]
0x180102c08  inc     edx
0x180102c0a  mov     [rsp+28h+plUbound], edx
0x180102c0e  call    cs:__imp_?EncodeBase64W@@YAJPEBEHPEAPEAG@Z; EncodeBase64W(uchar const *,int,ushort * *)
0x180102c14  mov     ebx, eax
0x180102c16  xor     ecx, ecx; hMem
0x180102c18  call    cs:__imp_LocalFree
0x180102c1e  cmp     [rsp+28h+ppvData], 0
0x180102c24  jz      short loc_180102C2F
0x180102c26  mov     rcx, rdi; psa
0x180102c29  call    cs:__imp_SafeArrayUnaccessData
0x180102c2f  mov     rsi, [rsp+28h+arg_18]
0x180102c34  mov     eax, ebx
0x180102c36  mov     rbx, [rsp+28h+arg_8]
0x180102c3b  add     rsp, 20h
0x180102c3f  pop     rdi
0x180102c40  retn
```
