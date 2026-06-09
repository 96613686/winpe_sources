# GetImageName(ushort * *)

- ea: `0x18001238c`
- end: `0x18001246f`
- name: `?GetImageName@@YAJPEAPEAG@Z`
- size: `227`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012478`

## callees

- `0x18000df74`
- `0x18000e574`
- `0x180012154`
- `0x18001238c`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012434`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012442`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012434`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012442`

## pseudocode

```c
__int64 __fastcall GetImageName(unsigned __int16 **a1)
{
  int ExeNameAndAppId; // eax
  unsigned __int16 *v3; // rdi
  unsigned int v4; // ebx
  int v5; // eax
  LPVOID pv; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 *v8; // [rsp+38h] [rbp-230h] BYREF
  unsigned __int16 v9[264]; // [rsp+40h] [rbp-228h] BYREF

  pv = 0;
  v8 = 0;
  ExeNameAndAppId = GetExeNameAndAppId((unsigned __int16 **)&pv, &v8);
  v3 = v8;
  v4 = ExeNameAndAppId;
  if ( ExeNameAndAppId >= 0 )
  {
    v5 = v8 ? StringCbPrintfW(v9, 0x20Au, L"%s-%s", pv, v8) : StringCbPrintfW(v9, 0x20Au, L"%s", pv);
    v4 = v5;
    if ( v5 >= 0 )
      v4 = DuplicateString(v9, a1);
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( v3 )
    CoTaskMemFree(v3);
  return v4;
}

```

## disassembly

```asm
0x18001238c  mov     [rsp+arg_8], rbx
0x180012391  mov     [rsp+arg_10], rbp
0x180012396  push    rdi
0x180012397  sub     rsp, 260h
0x18001239e  mov     rax, cs:__security_cookie
0x1800123a5  xor     rax, rsp
0x1800123a8  mov     [rsp+268h+var_18], rax
0x1800123b0  mov     rbp, rcx
0x1800123b3  mov     [rsp+268h+pv], 0
0x1800123bc  lea     rcx, [rsp+268h+pv]; unsigned __int16 **
0x1800123c1  mov     [rsp+268h+var_230], 0
0x1800123ca  lea     rdx, [rsp+268h+var_230]; unsigned __int16 **
0x1800123cf  call    ?GetExeNameAndAppId@@YAJPEAPEAG0@Z; GetExeNameAndAppId(ushort * *,ushort * *)
0x1800123d4  mov     rdi, [rsp+268h+var_230]
0x1800123d9  mov     ebx, eax
0x1800123db  test    eax, eax
0x1800123dd  js      short loc_180012427
0x1800123df  mov     r9, [rsp+268h+pv]
0x1800123e4  mov     edx, 20Ah; unsigned __int64
0x1800123e9  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x1800123ee  test    rdi, rdi
0x1800123f1  jz      short loc_180012406
0x1800123f3  lea     r8, aSS; "%s-%s"
0x1800123fa  mov     [rsp+268h+var_248], rdi
0x1800123ff  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012404  jmp     short loc_180012412
0x180012406  lea     r8, aS_0; "%s"
0x18001240d  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180012412  mov     ebx, eax
0x180012414  test    eax, eax
0x180012416  js      short loc_180012427
0x180012418  mov     rdx, rbp; unsigned __int16 **
0x18001241b  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x180012420  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x180012425  mov     ebx, eax
0x180012427  cmp     [rsp+268h+pv], 0
0x18001242d  jz      short loc_18001243A
0x18001242f  mov     rcx, [rsp+268h+pv]; pv
0x180012434  call    cs:__imp_CoTaskMemFree
0x18001243a  test    rdi, rdi
0x18001243d  jz      short loc_180012448
0x18001243f  mov     rcx, rdi; pv
0x180012442  call    cs:__imp_CoTaskMemFree
0x180012448  mov     eax, ebx
0x18001244a  mov     rcx, [rsp+268h+var_18]
0x180012452  xor     rcx, rsp; StackCookie
0x180012455  call    __security_check_cookie
0x18001245a  lea     r11, [rsp+268h+var_8]
0x180012462  mov     rbx, [r11+18h]
0x180012466  mov     rbp, [r11+20h]
0x18001246a  mov     rsp, r11
0x18001246d  pop     rdi
0x18001246e  retn
```
