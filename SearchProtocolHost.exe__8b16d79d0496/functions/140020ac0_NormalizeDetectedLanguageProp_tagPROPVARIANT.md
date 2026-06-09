# NormalizeDetectedLanguageProp(tagPROPVARIANT * *)

- ea: `0x140020ac0`
- end: `0x140020b77`
- name: `?NormalizeDetectedLanguageProp@@YAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(struct tagPROPVARIANT **)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x14002a090`
- `0x14002d394`

## callees

- `0x140015958`
- `0x140020ac0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140020b2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140020b2d`

## string_xrefs

- `0x140020ad7`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx"`
- `0x140020b47`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx"`

## pseudocode

```c
__int64 __fastcall NormalizeDetectedLanguageProp(struct tagPROPVARIANT **a1, __int64 a2, __int64 a3, const wchar_t *a4)
{
  const wchar_t *v4; // r8
  __int64 v5; // rdx
  __int64 v7; // rbx
  _DWORD *v8; // rdx
  const wchar_t *v9; // r9
  int v10; // eax

  if ( !a1 )
  {
    v4 = (const wchar_t *)L"[SrchFilterDaemon] NULL pointer passed into NormalizeDetectedLanguageProp. Returning E_INVALIDARG.";
    v5 = 6559;
LABEL_3:
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrdaemon.cxx\"",
      (const wchar_t *)v5,
      (unsigned int)v4,
      a4);
    return 2147942487LL;
  }
  v7 = (__int64)*a1;
  if ( !*a1 )
  {
    v4 = L"[SrchFilterDaemon] NULL pointer in NormalizeDetectedLanguageProp. Returning E_INVALIDARG.";
    v5 = 6567;
    goto LABEL_3;
  }
  if ( *(_WORD *)v7 == 19 )
  {
    v8 = CoTaskMemAlloc(4u);
    if ( !v8 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrdaemon.cxx\"",
        (const wchar_t *)0x19BC,
        (unsigned int)L"[SrchFilterDaemon] Out of memory! Returning E_OUTOFMEMORY.",
        v9);
      return 2147942414LL;
    }
    v10 = *(_DWORD *)(v7 + 8);
    *(_DWORD *)(v7 + 8) = 1;
    *(_WORD *)v7 = 4115;
    *(_QWORD *)(v7 + 16) = v8;
    *v8 = v10;
  }
  else if ( *(_WORD *)v7 != 4115 )
  {
    v4 = L"[SrchFilterDaemon] Unknown detected language property type. Returning E_INVALIDARG.";
    v5 = 6576;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x140020ac0  push    rbx
0x140020ac2  sub     rsp, 20h
0x140020ac6  test    rcx, rcx
0x140020ac9  jnz     short loc_140020AED
0x140020acb  lea     r8, aSrchfilterdaem; "[SrchFilterDaemon] NULL pointer passed "...
0x140020ad2  mov     edx, 199Fh; wchar_t *
0x140020ad7  lea     rcx, aOnecoreuapBase_54; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x140020ade  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x140020ae3  mov     eax, 80070057h
0x140020ae8  jmp     loc_140020B71
0x140020aed  mov     rbx, [rcx]
0x140020af0  test    rbx, rbx
0x140020af3  jnz     short loc_140020B03
0x140020af5  lea     r8, aSrchfilterdaem_41; "[SrchFilterDaemon] NULL pointer in Norm"...
0x140020afc  mov     edx, 19A7h
0x140020b01  jmp     short loc_140020AD7
0x140020b03  movzx   eax, word ptr [rbx]
0x140020b06  mov     ecx, 13h
0x140020b0b  cmp     cx, ax
0x140020b0e  jz      short loc_140020B28
0x140020b10  mov     ecx, 1013h
0x140020b15  cmp     cx, ax
0x140020b18  jz      short loc_140020B6F
0x140020b1a  lea     r8, aSrchfilterdaem_38; "[SrchFilterDaemon] Unknown detected lan"...
0x140020b21  mov     edx, 19B0h
0x140020b26  jmp     short loc_140020AD7
0x140020b28  mov     ecx, 4; cb
0x140020b2d  call    cs:__imp_CoTaskMemAlloc
0x140020b33  mov     rdx, rax
0x140020b36  test    rax, rax
0x140020b39  jnz     short loc_140020B5A
0x140020b3b  lea     r8, aSrchfilterdaem_30; "[SrchFilterDaemon] Out of memory! Retur"...
0x140020b42  mov     edx, 19BCh; wchar_t *
0x140020b47  lea     rcx, aOnecoreuapBase_54; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x140020b4e  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x140020b53  mov     eax, 8007000Eh
0x140020b58  jmp     short loc_140020B71
0x140020b5a  mov     eax, [rbx+8]
0x140020b5d  mov     dword ptr [rbx+8], 1
0x140020b64  mov     word ptr [rbx], 1013h
0x140020b69  mov     [rbx+10h], rdx
0x140020b6d  mov     [rdx], eax
0x140020b6f  xor     eax, eax
0x140020b71  add     rsp, 20h
0x140020b75  pop     rbx
0x140020b76  retn
```
