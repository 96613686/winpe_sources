# Windows::UI::Input::Inking::CInkStrokeContainer::ConvertBytesToVariantByteArray(uchar const *,unsigned __int64,tagVARIANT *)

- ea: `0x180027640`
- end: `0x1800276e8`
- name: `?ConvertBytesToVariantByteArray@CInkStrokeContainer@Inking@Input@UI@Windows@@EEAAJPEBE_KPEAUtagVARIANT@@@Z`
- size: `168`
- prototype: `int(Windows::UI::Input::Inking::CInkStrokeContainer *__hidden this, const unsigned __int8 *, unsigned __int64, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001332c`
- `0x180027640`
- `0x1800f85e8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800276d5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800276d5`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002769c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002769c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800276bb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800276bb`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002765b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002765b`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Inking::CInkStrokeContainer::ConvertBytesToVariantByteArray(
        Windows::UI::Input::Inking::CInkStrokeContainer *this,
        const unsigned __int8 *a2,
        size_t a3,
        struct tagVARIANT *a4)
{
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v8; // rbx
  HRESULT v10; // edi
  void *ppvData; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  Vector = SafeArrayCreateVector(0x11u, 0, a3);
  v8 = Vector;
  if ( Vector )
  {
    ppvData = 0;
    v10 = SafeArrayAccessData(Vector, &ppvData);
    if ( v10 < 0 )
    {
      SafeArrayDestroy(v8);
    }
    else
    {
      memcpy_0(ppvData, a2, a3);
      v10 = SafeArrayUnaccessData(v8);
      if ( v10 >= 0 )
      {
        a4->vt = 8209;
        a4->llVal = (LONGLONG)v8;
      }
    }
    return (unsigned int)v10;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36D,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\directink\\inkmanager\\lib\\strokecollection.cpp",
      (const char *)0x8007000ELL,
      (int)ppvData);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180027640  push    rbx
0x180027642  push    rbp
0x180027643  push    rsi
0x180027644  push    rdi
0x180027645  push    r14
0x180027647  sub     rsp, 30h
0x18002764b  mov     r14, rdx
0x18002764e  mov     ecx, 11h; vt
0x180027653  xor     edx, edx; lLbound
0x180027655  mov     rsi, r9
0x180027658  mov     rbp, r8
0x18002765b  call    cs:__imp_SafeArrayCreateVector
0x180027661  mov     rbx, rax
0x180027664  test    rax, rax
0x180027667  jnz     short loc_18002768B
0x180027669  mov     rcx, [rsp+58h]; this
0x18002766e  lea     r8, aOnecoreuapWind_37; "onecoreuap\\windows\\advcore\\winrt\\di"...
0x180027675  mov     ebx, 8007000Eh
0x18002767a  mov     edx, 36Dh; void *
0x18002767f  mov     r9d, ebx; char *
0x180027682  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027687  mov     eax, ebx
0x180027689  jmp     short loc_1800276DD
0x18002768b  lea     rdx, [rsp+58h+ppvData]; ppvData
0x180027690  mov     [rsp+58h+ppvData], 0
0x180027699  mov     rcx, rbx; psa
0x18002769c  call    cs:__imp_SafeArrayAccessData
0x1800276a2  mov     edi, eax
0x1800276a4  test    eax, eax
0x1800276a6  js      short loc_1800276D2
0x1800276a8  mov     rcx, [rsp+58h+ppvData]; void *
0x1800276ad  mov     r8, rbp; Size
0x1800276b0  mov     rdx, r14; Src
0x1800276b3  call    memcpy_0
0x1800276b8  mov     rcx, rbx; psa
0x1800276bb  call    cs:__imp_SafeArrayUnaccessData
0x1800276c1  mov     edi, eax
0x1800276c3  test    eax, eax
0x1800276c5  js      short loc_1800276DB
0x1800276c7  mov     word ptr [rsi], 2011h
0x1800276cc  mov     [rsi+8], rbx
0x1800276d0  jmp     short loc_1800276DB
0x1800276d2  mov     rcx, rbx; psa
0x1800276d5  call    cs:__imp_SafeArrayDestroy
0x1800276db  mov     eax, edi
0x1800276dd  add     rsp, 30h
0x1800276e1  pop     r14
0x1800276e3  pop     rdi
0x1800276e4  pop     rsi
0x1800276e5  pop     rbp
0x1800276e6  pop     rbx
0x1800276e7  retn
```
