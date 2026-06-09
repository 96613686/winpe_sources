# CFilterSink::AddCompleted(long)

- ea: `0x14003c188`
- end: `0x14003c2f8`
- name: `?AddCompleted@CFilterSink@@QEAAJJ@Z`
- size: `368`
- prototype: `int(CFilterSink *__hidden this, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14002a090`
- `0x14002d394`

## callees

- `0x14000e898`
- `0x140015958`
- `0x1400317a8`
- `0x14003241c`
- `0x14003c188`
- `0x14003d6f8`
- `0x14003d790`
- `0x14003e324`
- `0x14003e344`
- `0x14003e5f0`
- `0x140070010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14003c2d4`
- `OLEAUT32!__imp_SysFreeString` at `0x14003c2d4`
- `OLEAUT32!__imp_SysStringLen` at `0x14003c232`
- `OLEAUT32!__imp_SysStringLen` at `0x14003c232`
- `OLEAUT32!__imp_GetErrorInfo` at `0x14003c1bf`
- `OLEAUT32!__imp_GetErrorInfo` at `0x14003c1bf`

## string_xrefs

- `0x14003c1d5`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx"`
- `0x14003c2bd`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrsink.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFilterSink::AddCompleted(CFilterSink *this, unsigned int a2)
{
  UINT v4; // edi
  const wchar_t *v5; // r9
  unsigned int v6; // r10d
  int v7; // ebx
  unsigned int v8; // r15d
  unsigned int v9; // r8d
  const wchar_t *v10; // rdx
  int v12; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  BSTR pbstr; // [rsp+60h] [rbp+8h] BYREF
  IErrorInfo *v15; // [rsp+70h] [rbp+18h] BYREF

  v12 = -2;
  v15 = 0;
  pbstr = 0;
  v4 = 0;
  if ( !GetErrorInfo(0, &v15) )
  {
    SearchIndexerTrace::Verbose(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrsink.cxx\"",
      (const wchar_t *)0x227,
      (unsigned int)L"[SrchFilterDaemon] FLTRDMN: Got an Error Info - now grabbing it",
      v5,
      -2);
    if ( ((int (__fastcall *)(IErrorInfo *, BSTR *))v15->lpVtbl->GetDescription)(v15, &pbstr) >= 0 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrsink.cxx\"",
        (const wchar_t *)0x230,
        (unsigned int)L"[SrchFilterDaemon] FLTRDMN: Errorinfo is \"%ls\"",
        pbstr);
      v4 = SysStringLen(pbstr);
      if ( v4 > 0x3E8 )
        v4 = 1000;
    }
    else
    {
      SearchIndexerTrace::Warning(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\fltrsink.cxx\"",
        (const wchar_t *)0x22C,
        (unsigned int)L"[SrchFilterDaemon] FLTRDMN: Could not retrieve error description 0x%08x",
        (const wchar_t *)a2);
    }
  }
  CPipeSerStream::SwitchCountOn((CFilterSink *)((char *)this + 2592));
  v7 = 0;
  v8 = v6 + 2;
  do
  {
    if ( v7 >= 0 )
    {
      v7 = CFilterSink::PutHeader(this, v6, a2, 5);
      if ( v7 >= 0 )
      {
        if ( v4 )
        {
          v9 = v4;
          v10 = pbstr;
        }
        else
        {
          v9 = 0;
          v10 = &dword_14007696C;
        }
        v7 = CFilterSink::PutText(this, v10, v9);
      }
    }
    CPipeSerStream::SwitchCountOff((CFilterSink *)((char *)this + 2592));
    --v8;
  }
  while ( v8 );
  if ( a2 == -2147024882 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x258,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrsink.cxx",
      (const char *)0x8007000ELL,
      v12);
  SysFreeString(pbstr);
  TComPointer<IBindCtx>::~TComPointer<IBindCtx>(&v15);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14003c188  mov     rax, rsp
0x14003c18b  push    rbp
0x14003c18c  push    rsi
0x14003c18d  push    rdi
0x14003c18e  push    r14
0x14003c190  push    r15
0x14003c192  sub     rsp, 30h
0x14003c196  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x14003c19e  mov     [rax+10h], rbx
0x14003c1a2  mov     ebp, edx
0x14003c1a4  mov     rsi, rcx
0x14003c1a7  mov     qword ptr [rax+18h], 0
0x14003c1af  mov     qword ptr [rax+8], 0
0x14003c1b7  xor     edi, edi
0x14003c1b9  lea     rdx, [rax+18h]; pperrinfo
0x14003c1bd  xor     ecx, ecx; dwReserved
0x14003c1bf  call    cs:__imp_GetErrorInfo
0x14003c1c5  test    eax, eax
0x14003c1c7  jnz     short loc_14003C244
0x14003c1c9  lea     r8, aSrchfilterdaem_14; "[SrchFilterDaemon] FLTRDMN: Got an Erro"...
0x14003c1d0  mov     edx, 227h; wchar_t *
0x14003c1d5  lea     rbx, aOnecoreuapBase_25; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14003c1dc  mov     rcx, rbx; this
0x14003c1df  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x14003c1e4  mov     rcx, [rsp+58h+arg_10]
0x14003c1e9  mov     rax, [rcx]
0x14003c1ec  lea     rdx, [rsp+58h+pbstr]
0x14003c1f1  mov     rax, [rax+28h]
0x14003c1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c1fa  mov     rcx, rbx; this
0x14003c1fd  test    eax, eax
0x14003c1ff  jns     short loc_14003C217
0x14003c201  mov     r9d, ebp; wchar_t *
0x14003c204  lea     r8, aSrchfilterdaem_8; "[SrchFilterDaemon] FLTRDMN: Could not r"...
0x14003c20b  mov     edx, 22Ch; wchar_t *
0x14003c210  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x14003c215  jmp     short loc_14003C244
0x14003c217  mov     r9, [rsp+58h+pbstr]; wchar_t *
0x14003c21c  lea     r8, aSrchfilterdaem_33; "[SrchFilterDaemon] FLTRDMN: Errorinfo i"...
0x14003c223  mov     edx, 230h; wchar_t *
0x14003c228  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14003c22d  mov     rcx, [rsp+58h+pbstr]; pbstr
0x14003c232  call    cs:__imp_SysStringLen
0x14003c238  mov     edi, eax
0x14003c23a  mov     eax, 3E8h
0x14003c23f  cmp     edi, eax
0x14003c241  cmova   edi, eax
0x14003c244  xor     r10d, r10d
0x14003c247  lea     r14, [rsi+0A20h]
0x14003c24e  mov     rcx, r14; this
0x14003c251  call    ?SwitchCountOn@CPipeSerStream@@QEAAXXZ; CPipeSerStream::SwitchCountOn(void)
0x14003c256  xor     ebx, ebx
0x14003c258  lea     r15d, [r10+2]
0x14003c25c  test    ebx, ebx
0x14003c25e  js      short loc_14003C29C
0x14003c260  mov     r9d, 5; unsigned int
0x14003c266  mov     r8d, ebp; int
0x14003c269  mov     edx, r10d; unsigned int
0x14003c26c  mov     rcx, rsi; this
0x14003c26f  call    ?PutHeader@CFilterSink@@AEAAJKJK@Z; CFilterSink::PutHeader(ulong,long,ulong)
0x14003c274  mov     ebx, eax
0x14003c276  test    eax, eax
0x14003c278  js      short loc_14003C29C
0x14003c27a  mov     rcx, rsi; this
0x14003c27d  test    edi, edi
0x14003c27f  jz      short loc_14003C28B
0x14003c281  mov     r8d, edi
0x14003c284  mov     rdx, [rsp+58h+pbstr]
0x14003c289  jmp     short loc_14003C295
0x14003c28b  xor     r8d, r8d; unsigned int
0x14003c28e  lea     rdx, dword_14007696C; wchar_t *
0x14003c295  call    ?PutText@CFilterSink@@AEAAJPEB_WK@Z; CFilterSink::PutText(wchar_t const *,ulong)
0x14003c29a  mov     ebx, eax
0x14003c29c  mov     r10d, [r14]
0x14003c29f  mov     rcx, r14; this
0x14003c2a2  call    ?SwitchCountOff@CPipeSerStream@@QEAAXXZ; CPipeSerStream::SwitchCountOff(void)
0x14003c2a7  sub     r15d, 1
0x14003c2ab  jnz     short loc_14003C25C
0x14003c2ad  mov     r9d, 8007000Eh; char *
0x14003c2b3  cmp     ebp, r9d
0x14003c2b6  jnz     short loc_14003C2CF
0x14003c2b8  mov     rcx, [rsp+58h]; this
0x14003c2bd  lea     r8, aOnecoreuapBase_26; "onecoreuap\\base\\appmodel\\search\\sea"...
0x14003c2c4  mov     edx, 258h; void *
0x14003c2c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14003c2cf  mov     rcx, [rsp+58h+pbstr]; bstrString
0x14003c2d4  call    cs:__imp_SysFreeString
0x14003c2da  nop
0x14003c2db  lea     rcx, [rsp+58h+arg_10]
0x14003c2e0  call    ??1?$TComPointer@UIBindCtx@@@@QEAA@XZ; TComPointer<IBindCtx>::~TComPointer<IBindCtx>(void)
0x14003c2e5  mov     eax, ebx
0x14003c2e7  mov     rbx, [rsp+58h+arg_8]
0x14003c2ec  add     rsp, 30h
0x14003c2f0  pop     r15
0x14003c2f2  pop     r14
0x14003c2f4  pop     rdi
0x14003c2f5  pop     rsi
0x14003c2f6  pop     rbp
0x14003c2f7  retn
```
