# wprt::ProcCallback::PerformAction(IDocumentGenerator &)

- ea: `0x1800077f0`
- end: `0x18000795a`
- name: `?PerformAction@ProcCallback@wprt@@UEAAXAEAVIDocumentGenerator@@@Z`
- size: `362`
- prototype: `void __fastcall(wprt::ProcCallback *__hidden this, struct IDocumentGenerator *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x180003180`
- `0x180003580`
- `0x180003d30`
- `0x180003d3c`
- `0x1800077f0`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800078a4`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800078a4`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800078cd`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800078cd`

## string_xrefs

- `0x180007835`: `Windows.Storage.Streams.InMemoryRandomAccessStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall wprt::ProcCallback::PerformAction(wprt::ProcCallback *this, struct IDocumentGenerator *a2)
{
  const WCHAR *v4; // rcx
  WCHAR *v5; // rcx
  HRESULT v6; // eax
  HSTRING v7; // rcx
  PCNZWCH sourceString[2]; // [rsp+30h] [rbp-48h] BYREF
  UINT32 length[4]; // [rsp+40h] [rbp-38h]
  HSTRING string; // [rsp+50h] [rbp-28h] BYREF
  __int64 v11; // [rsp+58h] [rbp-20h] BYREF

  v11 = 0;
  string = 0;
  *(_OWORD *)sourceString = 0;
  *(_OWORD *)length = 0;
  std::wstring::_Construct<1,wchar_t const *>(sourceString, L"Windows.Storage.Streams.InMemoryRandomAccessStream");
  string = 0;
  v4 = (const WCHAR *)sourceString;
  if ( *(_QWORD *)&length[2] >= 8u )
    v4 = sourceString[0];
  WindowsCreateString_0(v4, length[0], &string);
  if ( *(_QWORD *)&length[2] >= 8u )
  {
    v5 = (WCHAR *)sourceString[0];
    if ( (unsigned __int64)(2LL * *(_QWORD *)&length[2] + 2) >= 0x1000 )
    {
      v5 = (WCHAR *)*((_QWORD *)sourceString[0] - 1);
      if ( (unsigned __int64)((char *)sourceString[0] - (char *)v5 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v5, 2LL * *(_QWORD *)&length[2] + 41);
        __debugbreak();
      }
    }
    operator delete(v5);
  }
  *(__m128i *)length = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(sourceString[0]) = 0;
  RoActivateInstance(string, &v11);
  (**(void (__fastcall ***)(struct IDocumentGenerator *, __int64, _QWORD, _QWORD))a2)(
    a2,
    v11,
    **((unsigned int **)this + 2),
    *(unsigned int *)(*((_QWORD *)this + 2) + 4LL));
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 8LL))(*((_QWORD *)this + 1), v11);
  v6 = WindowsDeleteString_0(string);
  v7 = string;
  if ( !v6 )
    v7 = 0;
  string = v7;
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
}

```

## disassembly

```asm
0x1800077f0  mov     [rsp+arg_10], rbx
0x1800077f5  mov     [rsp+arg_18], rsi
0x1800077fa  push    rdi
0x1800077fb  sub     rsp, 70h
0x1800077ff  mov     rax, cs:__security_cookie
0x180007806  xor     rax, rsp
0x180007809  mov     [rsp+78h+var_18], rax
0x18000780e  mov     rdi, rdx
0x180007811  mov     rbx, rcx
0x180007814  xor     esi, esi
0x180007816  mov     [rsp+78h+var_20], rsi
0x18000781b  mov     [rsp+78h+string], rsi
0x180007820  xorps   xmm0, xmm0
0x180007823  movups  xmmword ptr [rsp+78h+sourceString], xmm0
0x180007828  xorps   xmm1, xmm1
0x18000782b  movdqu  xmmword ptr [rsp+78h+length], xmm1
0x180007831  lea     r8d, [rsi+32h]
0x180007835  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_InMemoryRandomAccessStream@@3QB_WB; "Windows.Storage.Streams.InMemoryRandomA"...
0x18000783c  lea     rcx, [rsp+78h+sourceString]
0x180007841  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180007846  mov     [rsp+78h+string], rsi
0x18000784b  lea     rcx, [rsp+78h+sourceString]
0x180007850  cmp     qword ptr [rsp+78h+length+8], 8
0x180007856  cmovnb  rcx, [rsp+78h+sourceString]; sourceString
0x18000785c  lea     r8, [rsp+78h+string]; string
0x180007861  mov     edx, [rsp+78h+length]; length
0x180007865  call    WindowsCreateString_0
0x18000786a  nop
0x18000786b  mov     rdx, qword ptr [rsp+78h+length+8]
0x180007870  cmp     rdx, 8
0x180007874  jb      short loc_1800078B0
0x180007876  lea     rdx, ds:2[rdx*2]
0x18000787e  mov     rcx, [rsp+78h+sourceString]; Block
0x180007883  mov     rax, rcx
0x180007886  cmp     rdx, 1000h
0x18000788d  jb      short loc_1800078AB
0x18000788f  add     rdx, 27h ; '''
0x180007893  mov     rcx, [rcx-8]
0x180007897  sub     rax, rcx
0x18000789a  add     rax, 0FFFFFFFFFFFFFFF8h
0x18000789e  cmp     rax, 1Fh
0x1800078a2  jbe     short loc_1800078AB
0x1800078a4  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x1800078aa  int     3; Trap to Debugger
0x1800078ab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800078b0  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800078b8  movdqu  xmmword ptr [rsp+78h+length], xmm0
0x1800078be  mov     word ptr [rsp+78h+sourceString], si
0x1800078c3  lea     rdx, [rsp+78h+var_20]
0x1800078c8  mov     rcx, [rsp+78h+string]
0x1800078cd  call    cs:__imp_RoActivateInstance
0x1800078d3  mov     rax, [rdi]
0x1800078d6  mov     rdx, [rbx+10h]
0x1800078da  mov     r9d, [rdx+4]
0x1800078de  mov     r8d, [rdx]
0x1800078e1  mov     rdx, [rsp+78h+var_20]
0x1800078e6  mov     rcx, rdi
0x1800078e9  mov     rax, [rax]
0x1800078ec  call    cs:__guard_dispatch_icall_fptr
0x1800078f2  mov     rcx, [rbx+8]
0x1800078f6  mov     rax, [rcx]
0x1800078f9  mov     rdx, [rsp+78h+var_20]
0x1800078fe  mov     rax, [rax+8]
0x180007902  call    cs:__guard_dispatch_icall_fptr
0x180007908  nop
0x180007909  mov     rcx, [rsp+78h+string]; string
0x18000790e  call    WindowsDeleteString_0
0x180007913  mov     rcx, [rsp+78h+string]
0x180007918  test    eax, eax
0x18000791a  cmovz   rcx, rsi
0x18000791e  mov     [rsp+78h+string], rcx
0x180007923  mov     rcx, [rsp+78h+var_20]
0x180007928  test    rcx, rcx
0x18000792b  jz      short loc_18000793B
0x18000792d  mov     rax, [rcx]
0x180007930  mov     rax, [rax+10h]
0x180007934  call    cs:__guard_dispatch_icall_fptr
0x18000793a  nop
0x18000793b  mov     rcx, [rsp+78h+var_18]
0x180007940  xor     rcx, rsp; StackCookie
0x180007943  call    __security_check_cookie
0x180007948  lea     r11, [rsp+78h+var_8]
0x18000794d  mov     rbx, [r11+20h]
0x180007951  mov     rsi, [r11+28h]
0x180007955  mov     rsp, r11
0x180007958  pop     rdi
0x180007959  retn
```
