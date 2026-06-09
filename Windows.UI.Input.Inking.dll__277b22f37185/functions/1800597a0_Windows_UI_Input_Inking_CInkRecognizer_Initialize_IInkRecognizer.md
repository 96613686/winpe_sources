# Windows::UI::Input::Inking::CInkRecognizer::Initialize(IInkRecognizer *)

- ea: `0x1800597a0`
- end: `0x180059857`
- name: `?Initialize@CInkRecognizer@Inking@Input@UI@Windows@@UEAAJPEAUIInkRecognizer@@@Z`
- size: `183`
- prototype: `__int64 __fastcall(Windows::UI::Input::Inking::CInkRecognizer *__hidden this, struct IInkRecognizer *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001332c`
- `0x1800597a0`
- `0x1800fb010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180059846`
- `OLEAUT32!__imp_SysFreeString` at `0x180059846`
- `OLEAUT32!__imp_SysStringLen` at `0x180059819`
- `OLEAUT32!__imp_SysStringLen` at `0x180059819`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005982a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005982a`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::CInkRecognizer::Initialize(HSTRING *this, struct IInkRecognizer *a2)
{
  struct IInkRecognizerVtbl *lpVtbl; // rax
  int v6; // eax
  HRESULT String; // edi
  UINT v8; // eax
  int v9; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  BSTR pbstr; // [rsp+58h] [rbp+10h] BYREF

  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    pbstr = 0;
    v6 = ((__int64 (__fastcall *)(struct IInkRecognizer *, BSTR *))lpVtbl->get_Name)(a2, &pbstr);
    String = v6;
    if ( v6 >= 0 )
    {
      v8 = SysStringLen(pbstr);
      String = WindowsCreateString(pbstr, v8, this + 6);
      if ( String >= 0 )
      {
        if ( this[6] )
          this[5] = (HSTRING)a2;
      }
      SysFreeString(pbstr);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\recognizer.cpp",
        (const char *)(unsigned int)v6,
        v9);
    }
    return (unsigned int)String;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\recognizer.cpp",
      (const char *)0x80004003LL,
      v9);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800597a0  push    rbx
0x1800597a2  push    rbp
0x1800597a3  push    rsi
0x1800597a4  push    rdi
0x1800597a5  sub     rsp, 28h
0x1800597a9  mov     rbx, rdx
0x1800597ac  mov     rsi, rcx
0x1800597af  test    rdx, rdx
0x1800597b2  jnz     short loc_1800597D6
0x1800597b4  mov     rcx, [rsp+48h]; this
0x1800597b9  lea     r8, aOnecoreuapWind_46; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x1800597c0  mov     ebx, 80004003h
0x1800597c5  mov     edx, 28h ; '('; void *
0x1800597ca  mov     r9d, ebx; char *
0x1800597cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800597d2  mov     eax, ebx
0x1800597d4  jmp     short loc_18005984E
0x1800597d6  mov     rax, [rdx]
0x1800597d9  mov     rcx, rbx
0x1800597dc  lea     rdx, [rsp+48h+pbstr]
0x1800597e1  mov     [rsp+48h+pbstr], 0
0x1800597ea  mov     rax, [rax+38h]
0x1800597ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597f3  mov     edi, eax
0x1800597f5  test    eax, eax
0x1800597f7  jns     short loc_180059814
0x1800597f9  mov     rcx, [rsp+48h]; this
0x1800597fe  lea     r8, aOnecoreuapWind_46; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180059805  mov     r9d, eax; char *
0x180059808  mov     edx, 2Ch ; ','; void *
0x18005980d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059812  jmp     short loc_18005984C
0x180059814  mov     rcx, [rsp+48h+pbstr]; pbstr
0x180059819  call    cs:__imp_SysStringLen
0x18005981f  mov     rcx, [rsp+48h+pbstr]; sourceString
0x180059824  lea     r8, [rsi+30h]; string
0x180059828  mov     edx, eax; length
0x18005982a  call    cs:__imp_WindowsCreateString
0x180059830  mov     edi, eax
0x180059832  test    eax, eax
0x180059834  js      short loc_180059841
0x180059836  cmp     qword ptr [rsi+30h], 0
0x18005983b  jz      short loc_180059841
0x18005983d  mov     [rsi+28h], rbx
0x180059841  mov     rcx, [rsp+48h+pbstr]; bstrString
0x180059846  call    cs:__imp_SysFreeString
0x18005984c  mov     eax, edi
0x18005984e  add     rsp, 28h
0x180059852  pop     rdi
0x180059853  pop     rsi
0x180059854  pop     rbp
0x180059855  pop     rbx
0x180059856  retn
```
