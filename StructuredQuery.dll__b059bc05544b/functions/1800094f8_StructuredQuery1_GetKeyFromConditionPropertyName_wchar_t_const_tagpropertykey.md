# StructuredQuery1::GetKeyFromConditionPropertyName(wchar_t const *,_tagpropertykey *)

- ea: `0x1800094f8`
- end: `0x180009632`
- name: `?GetKeyFromConditionPropertyName@StructuredQuery1@@YAJPEB_WPEAU_tagpropertykey@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(wchar_t *Buffer, const wchar_t *, struct _tagpropertykey *)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008ddc`
- `0x1800091bc`
- `0x180009640`
- `0x18000ddc8`
- `0x18000e4ec`
- `0x180033078`
- `0x18004ee68`
- `0x180063330`
- `0x18006a1cc`
- `0x18006f504`
- `0x180080840`

## callees

- `0x1800094f8`
- `0x18005e85c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009561`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000958c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800095b3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180009561`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000958c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800095b3`
- `PROPSYS!PSPropertyKeyFromString` at `0x180009613`
- `PROPSYS!PSPropertyKeyFromString` at `0x180009613`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18000952b`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18000952b`

## string_xrefs

- `0x1800095c5`: `System.StructuredQuery.Compound.%lu`
- `0x18000959e`: `System.StructuredQuery.Directory`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::GetKeyFromConditionPropertyName(
        wchar_t *Buffer,
        PROPERTYKEY *a2,
        struct _tagpropertykey *a3)
{
  HRESULT v3; // edi
  DWORD pid; // eax

  v3 = 0;
  *a2 = PKEY_Null;
  if ( Buffer )
  {
    if ( *Buffer == 123 )
      return (unsigned int)PSPropertyKeyFromString(Buffer, a2);
    v3 = PSGetPropertyKeyFromName(Buffer, a2);
    if ( v3 < 0 )
    {
      if ( CompareStringW(0x7Fu, 1u, Buffer, -1, L"*", -1) == 2 )
      {
        a2->fmtid = PKEY_FullText.fmtid;
        pid = PKEY_FullText.pid;
      }
      else if ( CompareStringW(0x7Fu, 1u, Buffer, -1, L"System.StructuredQuery.Scope", -1) == 2 )
      {
        a2->fmtid = (GUID)PKEY_SCOPE_PSEUDOPROPERTY;
        pid = 100;
      }
      else
      {
        if ( CompareStringW(0x7Fu, 1u, Buffer, -1, L"System.StructuredQuery.Directory", -1) != 2 )
        {
          if ( swscanf(Buffer, L"System.StructuredQuery.Compound.%lu", &a2->pid) != 1 )
            return (unsigned int)v3;
          a2->fmtid = (GUID)xmmword_18009B810;
          return 0;
        }
        a2->fmtid = (GUID)PKEY_DIRECTORY_PSEUDOPROPERTY;
        pid = 101;
      }
      a2->pid = pid;
      return 0;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800094f8  push    rbx
0x1800094fa  push    rbp
0x1800094fb  push    rsi
0x1800094fc  push    rdi
0x1800094fd  sub     rsp, 38h
0x180009501  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x180009508  xor     edi, edi
0x18000950a  mov     rbx, rdx
0x18000950d  mov     rsi, rcx
0x180009510  movups  xmmword ptr [rdx], xmm0
0x180009513  mov     eax, cs:PKEY_Null.pid
0x180009519  mov     [rdx+10h], eax
0x18000951c  test    rcx, rcx
0x18000951f  jz      short loc_180009537
0x180009521  cmp     word ptr [rcx], 7Bh ; '{'
0x180009525  jz      loc_180009613
0x18000952b  call    cs:__imp_PSGetPropertyKeyFromName
0x180009531  mov     edi, eax
0x180009533  test    eax, eax
0x180009535  js      short loc_180009542
0x180009537  mov     eax, edi
0x180009539  add     rsp, 38h
0x18000953d  pop     rdi
0x18000953e  pop     rsi
0x18000953f  pop     rbp
0x180009540  pop     rbx
0x180009541  retn
0x180009542  or      ebp, 0FFFFFFFFh
0x180009545  lea     rax, StringValue; "*"
0x18000954c  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x180009550  mov     r9d, ebp; cchCount1
0x180009553  mov     r8, rsi; lpString1
0x180009556  mov     [rsp+58h+lpString2], rax; lpString2
0x18000955b  lea     edx, [rbp+2]; dwCmpFlags
0x18000955e  lea     ecx, [rdx+7Eh]; Locale
0x180009561  call    cs:__imp_CompareStringW
0x180009567  cmp     eax, 2
0x18000956a  jz      loc_180009601
0x180009570  lea     edx, [rbp+2]; dwCmpFlags
0x180009573  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x180009577  lea     rax, aSystemStructur_12; "System.StructuredQuery.Scope"
0x18000957e  mov     r9d, ebp; cchCount1
0x180009581  lea     ecx, [rdx+7Eh]; Locale
0x180009584  mov     [rsp+58h+lpString2], rax; lpString2
0x180009589  mov     r8, rsi; lpString1
0x18000958c  call    cs:__imp_CompareStringW
0x180009592  cmp     eax, 2
0x180009595  jz      short loc_1800095EC
0x180009597  lea     edx, [rbp+2]; dwCmpFlags
0x18000959a  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000959e  lea     rax, aSystemStructur_27; "System.StructuredQuery.Directory"
0x1800095a5  mov     r9d, ebp; cchCount1
0x1800095a8  lea     ecx, [rdx+7Eh]; Locale
0x1800095ab  mov     [rsp+58h+lpString2], rax; lpString2
0x1800095b0  mov     r8, rsi; lpString1
0x1800095b3  call    cs:__imp_CompareStringW
0x1800095b9  cmp     eax, 2
0x1800095bc  jz      short loc_180009620
0x1800095be  lea     r8, [rbx+10h]
0x1800095c2  mov     rcx, rsi; Buffer
0x1800095c5  lea     rdx, aSystemStructur; "System.StructuredQuery.Compound.%lu"
0x1800095cc  call    swscanf
0x1800095d1  cmp     eax, 1
0x1800095d4  jnz     loc_180009537
0x1800095da  movups  xmm0, cs:xmmword_18009B810
0x1800095e1  movdqu  xmmword ptr [rbx], xmm0
0x1800095e5  xor     edi, edi
0x1800095e7  jmp     loc_180009537
0x1800095ec  movups  xmm0, cs:PKEY_SCOPE_PSEUDOPROPERTY
0x1800095f3  movups  xmmword ptr [rbx], xmm0
0x1800095f6  mov     eax, cs:dword_18009A318
0x1800095fc  mov     [rbx+10h], eax
0x1800095ff  jmp     short loc_1800095E5
0x180009601  movups  xmm0, xmmword ptr cs:PKEY_FullText.fmtid.Data1
0x180009608  movups  xmmword ptr [rbx], xmm0
0x18000960b  mov     eax, cs:PKEY_FullText.pid
0x180009611  jmp     short loc_1800095FC
0x180009613  call    cs:__imp_PSPropertyKeyFromString
0x180009619  mov     edi, eax
0x18000961b  jmp     loc_180009537
0x180009620  movups  xmm0, cs:PKEY_DIRECTORY_PSEUDOPROPERTY
0x180009627  movups  xmmword ptr [rbx], xmm0
0x18000962a  mov     eax, cs:dword_18009B860
0x180009630  jmp     short loc_1800095FC
```
