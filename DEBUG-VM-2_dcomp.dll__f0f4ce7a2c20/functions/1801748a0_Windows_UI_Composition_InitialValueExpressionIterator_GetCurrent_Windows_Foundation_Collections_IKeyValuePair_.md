# Windows::UI::Composition::InitialValueExpressionIterator::GetCurrent(Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> * *)

- ea: `0x1801748a0`
- end: `0x1801749b3`
- name: `?GetCurrent@InitialValueExpressionIterator@Composition@UI@Windows@@QEAAJPEAPEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@4@@Z`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180174d80`

## callees

- `0x18001358c`
- `0x18008baac`
- `0x1800c983c`
- `0x1801748a0`
- `0x180174a54`
- `0x180174a78`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174902`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801749a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174902`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180174991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801749a3`

## string_xrefs

- `0x180174962`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtinitialvalueexpressioniterator.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::InitialValueExpressionIterator::GetCurrent(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rcx
  _QWORD *v5; // rax
  Windows::UI::Composition::ExpressionAnimation *v6; // rbx
  int Expression; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  HSTRING v11[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HSTRING string; // [rsp+50h] [rbp+20h] BYREF
  __int64 v14; // [rsp+58h] [rbp+28h] BYREF
  HSTRING newString; // [rsp+60h] [rbp+30h] BYREF
  HSTRING v16; // [rsp+68h] [rbp+38h] BYREF

  *a2 = 0;
  v3 = *(_QWORD *)(a1 + 88);
  newString = 0;
  string = 0;
  v5 = *(_QWORD **)(a1 + 80);
  v14 = 0;
  if ( v3 == *v5 )
    goto LABEL_8;
  v16 = *(HSTRING *)(v3 + 32);
  Microsoft::WRL::Wrappers::HString::Set(&newString, &v16);
  v6 = *(Windows::UI::Composition::ExpressionAnimation **)(*(_QWORD *)(a1 + 88) + 40LL);
  WindowsDeleteString(string);
  string = 0;
  Expression = Windows::UI::Composition::ExpressionAnimation::GetExpression(v6, &string);
  v8 = Expression;
  if ( Expression >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(&v14);
    v16 = string;
    v11[0] = newString;
    Expression = Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Make(
                   v11,
                   &v16,
                   &v14);
    v8 = Expression;
    if ( Expression < 0 )
    {
      v9 = 116;
      goto LABEL_6;
    }
    *a2 = v14;
    v14 = 0;
LABEL_8:
    v8 = 0;
    goto LABEL_9;
  }
  v9 = 111;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtinitialvalueexpressioniterator.cpp",
    (const char *)(unsigned int)Expression,
    (int)v11[0]);
LABEL_9:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(&v14);
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(newString);
  return v8;
}

```

## disassembly

```asm
0x1801748a0  push    rbp
0x1801748a2  push    rbx
0x1801748a3  push    rdi
0x1801748a4  mov     rbp, rsp
0x1801748a7  sub     rsp, 30h
0x1801748ab  mov     qword ptr [rdx], 0
0x1801748b2  mov     rbx, rcx
0x1801748b5  mov     rcx, [rcx+58h]
0x1801748b9  mov     rdi, rdx
0x1801748bc  mov     [rbp+newString], 0
0x1801748c4  mov     [rbp+string], 0
0x1801748cc  mov     rax, [rbx+50h]
0x1801748d0  mov     [rbp+arg_8], 0
0x1801748d8  cmp     rcx, [rax]
0x1801748db  jz      loc_180174982
0x1801748e1  mov     rax, [rcx+20h]
0x1801748e5  lea     rdx, [rbp+arg_18]; HSTRING *
0x1801748e9  lea     rcx, [rbp+newString]; newString
0x1801748ed  mov     [rbp+arg_18], rax
0x1801748f1  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1801748f6  mov     rax, [rbx+58h]
0x1801748fa  mov     rcx, [rbp+string]; string
0x1801748fe  mov     rbx, [rax+28h]
0x180174902  call    cs:__imp_WindowsDeleteString
0x180174908  lea     rdx, [rbp+string]; HSTRING *
0x18017490c  mov     [rbp+string], 0
0x180174914  mov     rcx, rbx; this
0x180174917  call    ?GetExpression@ExpressionAnimation@Composition@UI@Windows@@QEAAJPEAPEAUHSTRING__@@@Z; Windows::UI::Composition::ExpressionAnimation::GetExpression(HSTRING__ * *)
0x18017491c  mov     ebx, eax
0x18017491e  test    eax, eax
0x180174920  jns     short loc_180174929
0x180174922  mov     edx, 6Fh ; 'o'
0x180174927  jmp     short loc_18017495E
0x180174929  lea     rcx, [rbp+arg_8]
0x18017492d  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(void)
0x180174932  mov     rax, [rbp+string]
0x180174936  lea     r8, [rbp+arg_8]
0x18017493a  mov     [rbp+arg_18], rax
0x18017493e  lea     rdx, [rbp+arg_18]
0x180174942  mov     rax, [rbp+newString]
0x180174946  lea     rcx, [rbp+var_10]
0x18017494a  mov     [rbp+var_10], rax
0x18017494e  call    ?Make@?$SimpleKeyValuePair@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@$0A@@Internal@Collections@Foundation@Windows@@SAJAEBQEAUHSTRING__@@0PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Make(HSTRING__ * const &,HSTRING__ * const &,Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x180174953  mov     ebx, eax
0x180174955  test    eax, eax
0x180174957  jns     short loc_180174973
0x180174959  mov     edx, 74h ; 't'; void *
0x18017495e  mov     rcx, [rbp+18h]; this
0x180174962  lea     r8, aOnecoreuapWind_249; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180174969  mov     r9d, eax; char *
0x18017496c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180174971  jmp     short loc_180174984
0x180174973  mov     rax, [rbp+arg_8]
0x180174977  mov     [rdi], rax
0x18017497a  mov     [rbp+arg_8], 0
0x180174982  xor     ebx, ebx
0x180174984  lea     rcx, [rbp+arg_8]
0x180174988  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(void)
0x18017498d  mov     rcx, [rbp+string]; string
0x180174991  call    cs:__imp_WindowsDeleteString
0x180174997  mov     rcx, [rbp+newString]; string
0x18017499b  mov     [rbp+string], 0
0x1801749a3  call    cs:__imp_WindowsDeleteString
0x1801749a9  mov     eax, ebx
0x1801749ab  add     rsp, 30h
0x1801749af  pop     rdi
0x1801749b0  pop     rbx
0x1801749b1  pop     rbp
0x1801749b2  retn
```
