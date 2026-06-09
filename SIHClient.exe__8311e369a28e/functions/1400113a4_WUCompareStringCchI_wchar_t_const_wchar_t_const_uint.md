# WUCompareStringCchI(wchar_t const *,wchar_t const *,uint)

- ea: `0x1400113a4`
- end: `0x14001143b`
- name: `?WUCompareStringCchI@@YAHPEB_W0I@Z`
- size: `151`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, const wchar_t *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000f5ac`
- `0x140011444`
- `0x140011dd8`
- `0x14003dcf8`

## callees

- `0x140011290`
- `0x1400113a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011423`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140011423`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140011416`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140011416`

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
0x1400113a4  mov     rax, rsp
0x1400113a7  mov     [rax+10h], rbx
0x1400113ab  mov     [rax+18h], rsi
0x1400113af  push    rdi
0x1400113b0  sub     rsp, 30h
0x1400113b4  mov     rbx, rdx
0x1400113b7  mov     rdi, rcx
0x1400113ba  test    rcx, rcx
0x1400113bd  jz      short loc_14001141E
0x1400113bf  test    rdx, rdx
0x1400113c2  jz      short loc_14001141E
0x1400113c4  mov     esi, r8d
0x1400113c7  lea     r8, [rax+20h]; unsigned __int64 *
0x1400113cb  mov     edx, esi; unsigned __int64
0x1400113cd  mov     qword ptr [rax+20h], 0
0x1400113d5  mov     qword ptr [rax+8], 0
0x1400113dd  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x1400113e2  test    eax, eax
0x1400113e4  js      short loc_14001141E
0x1400113e6  lea     r8, [rsp+38h+arg_0]; unsigned __int64 *
0x1400113eb  mov     edx, esi; unsigned __int64
0x1400113ed  mov     rcx, rbx; wchar_t *
0x1400113f0  call    ?SusStrCchLen@@YAJPEB_W_KPEA_K@Z; SusStrCchLen(wchar_t const *,unsigned __int64,unsigned __int64 *)
0x1400113f5  test    eax, eax
0x1400113f7  js      short loc_14001141E
0x1400113f9  mov     eax, dword ptr [rsp+38h+arg_0]
0x1400113fd  mov     edx, 1; dwCmpFlags
0x140011402  mov     r9d, dword ptr [rsp+38h+cchCount1]; cchCount1
0x140011407  mov     r8, rdi; lpString1
0x14001140a  mov     [rsp+38h+cchCount2], eax; cchCount2
0x14001140e  mov     [rsp+38h+lpString2], rbx; lpString2
0x140011413  lea     ecx, [rdx+7Eh]; Locale
0x140011416  call    cs:__imp_CompareStringW
0x14001141c  jmp     short loc_14001142B
0x14001141e  mov     ecx, 57h ; 'W'; dwErrCode
0x140011423  call    cs:__imp_SetLastError
0x140011429  xor     eax, eax
0x14001142b  mov     rbx, [rsp+38h+arg_8]
0x140011430  mov     rsi, [rsp+38h+arg_10]
0x140011435  add     rsp, 30h
0x140011439  pop     rdi
0x14001143a  retn
```
