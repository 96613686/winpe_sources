# WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)

- ea: `0x180008830`
- end: `0x1800088c7`
- name: `?WUCompareStringCchI@@YAHPEB_W0I@Z`
- size: `151`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, const wchar_t *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800088d0`
- `0x180049984`
- `0x18004bc70`

## callees

- `0x18000871c`
- `0x180008830`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800088af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800088af`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800088a2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800088a2`

## pseudocode

```c
int __fastcall WUCompareStringCchI(PCNZWCH lpString1, const wchar_t *a2, unsigned int a3)
{
  unsigned __int64 cchCount2; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int64 cchCount1; // [rsp+58h] [rbp+20h] BYREF

  if ( lpString1 )
  {
    if ( a2 )
    {
      cchCount1 = 0;
      cchCount2 = 0;
      if ( SusStrCchLen(lpString1, a3, &cchCount1) >= 0 && SusStrCchLen(a2, a3, &cchCount2) >= 0 )
        return CompareStringW(0x7Fu, 1u, lpString1, cchCount1, a2, cchCount2);
    }
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x180008830  mov     rax, rsp
0x180008833  mov     [rax+10h], rbx
0x180008837  mov     [rax+18h], rsi
0x18000883b  push    rdi
0x18000883c  sub     rsp, 30h
0x180008840  mov     rbx, rdx
0x180008843  mov     rdi, rcx
0x180008846  test    rcx, rcx
0x180008849  jz      short loc_1800088AA
0x18000884b  test    rdx, rdx
0x18000884e  jz      short loc_1800088AA
0x180008850  mov     esi, r8d
0x180008853  lea     r8, [rax+20h]; unsigned __int64 *
0x180008857  mov     edx, esi; unsigned __int64
0x180008859  mov     qword ptr [rax+20h], 0
0x180008861  mov     qword ptr [rax+8], 0
0x180008869  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x18000886e  test    eax, eax
0x180008870  js      short loc_1800088AA
0x180008872  lea     r8, [rsp+38h+arg_0]; unsigned __int64 *
0x180008877  mov     edx, esi; unsigned __int64
0x180008879  mov     rcx, rbx; wchar_t *
0x18000887c  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180008881  test    eax, eax
0x180008883  js      short loc_1800088AA
0x180008885  mov     eax, dword ptr [rsp+38h+arg_0]
0x180008889  mov     edx, 1; dwCmpFlags
0x18000888e  mov     r9d, dword ptr [rsp+38h+cchCount1]; cchCount1
0x180008893  mov     r8, rdi; lpString1
0x180008896  mov     [rsp+38h+cchCount2], eax; cchCount2
0x18000889a  mov     [rsp+38h+lpString2], rbx; lpString2
0x18000889f  lea     ecx, [rdx+7Eh]; Locale
0x1800088a2  call    cs:__imp_CompareStringW
0x1800088a8  jmp     short loc_1800088B7
0x1800088aa  mov     ecx, 57h ; 'W'; dwErrCode
0x1800088af  call    cs:__imp_SetLastError
0x1800088b5  xor     eax, eax
0x1800088b7  mov     rbx, [rsp+38h+arg_8]
0x1800088bc  mov     rsi, [rsp+38h+arg_10]
0x1800088c1  add     rsp, 30h
0x1800088c5  pop     rdi
0x1800088c6  retn
```
