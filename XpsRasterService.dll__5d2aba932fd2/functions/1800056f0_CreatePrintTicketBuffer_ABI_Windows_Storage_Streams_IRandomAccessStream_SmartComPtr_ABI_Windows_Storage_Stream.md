# CreatePrintTicketBuffer(ABI::Windows::Storage::Streams::IRandomAccessStream *,SmartComPtr<ABI::Windows::Storage::Streams::IBuffer> &)

- ea: `0x1800056f0`
- end: `0x18000595c`
- name: `?CreatePrintTicketBuffer@@YAJPEAUIRandomAccessStream@Streams@Storage@Windows@ABI@@AEAV?$SmartComPtr@UIBuffer@Streams@Storage@Windows@ABI@@@@@Z`
- size: `620`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006140`

## callees

- `0x180003180`
- `0x180003580`
- `0x180003d30`
- `0x180003d3c`
- `0x1800056f0`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800057ad`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800057ad`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180005812`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180005812`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CreatePrintTicketBuffer(__int64 a1, _QWORD *a2)
{
  unsigned int ActivationFactory; // ebx
  const WCHAR *v5; // rcx
  WCHAR *v6; // rcx
  HRESULT v7; // eax
  HSTRING v8; // rcx
  PCNZWCH sourceString[2]; // [rsp+30h] [rbp-50h] BYREF
  UINT32 length[4]; // [rsp+40h] [rbp-40h]
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  __int64 v13; // [rsp+58h] [rbp-28h] BYREF
  __int64 v14; // [rsp+60h] [rbp-20h] BYREF
  __int64 v15; // [rsp+68h] [rbp-18h] BYREF
  __int64 v16; // [rsp+70h] [rbp-10h] BYREF

  v13 = 0;
  ActivationFactory = -2147024809;
  v16 = 0;
  v14 = 0;
  string = 0;
  *(_OWORD *)sourceString = 0;
  *(_OWORD *)length = 0;
  std::wstring::_Construct<1,wchar_t const *>((char **)sourceString, L"Windows.Storage.Streams.Buffer", 0x1Eu);
  string = 0;
  v5 = (const WCHAR *)sourceString;
  if ( *(_QWORD *)&length[2] >= 8u )
    v5 = sourceString[0];
  WindowsCreateString_0(v5, length[0], &string);
  if ( *(_QWORD *)&length[2] >= 8u )
  {
    v6 = (WCHAR *)sourceString[0];
    if ( (unsigned __int64)(2LL * *(_QWORD *)&length[2] + 2) >= 0x1000 )
    {
      v6 = (WCHAR *)*((_QWORD *)sourceString[0] - 1);
      if ( (unsigned __int64)((char *)sourceString[0] - (char *)v6 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v6, 2LL * *(_QWORD *)&length[2] + 41);
        __debugbreak();
      }
    }
    operator delete(v6);
  }
  *(__m128i *)length = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(sourceString[0]) = 0;
  if ( a1 )
  {
    ActivationFactory = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 48LL))(a1, &v13);
    if ( !ActivationFactory )
    {
      if ( v13 )
      {
        ActivationFactory = RoGetActivationFactory(string, &GUID_71af914d_c10f_484b_bc50_14bc623b3a27, &v14);
        if ( !ActivationFactory )
        {
          ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v14 + 48LL))(
                                v14,
                                (unsigned int)v13,
                                a2);
          if ( !ActivationFactory )
          {
            ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a1 + 64LL))(
                                  a1,
                                  0,
                                  &v16);
            if ( !ActivationFactory )
            {
              if ( v16 )
              {
                v15 = 0;
                ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v16 + 48LL))(
                                      v16,
                                      *a2,
                                      (unsigned int)v13,
                                      ActivationFactory + 1,
                                      &v15);
                if ( !ActivationFactory )
                {
                  while ( (*(unsigned int (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v15 + 80LL))(v15, a2) == -2147483634 )
                    ;
                  if ( *a2 )
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
                  else
                    ActivationFactory = -2147024809;
                }
                if ( v15 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
              }
            }
          }
        }
      }
      else
      {
        ActivationFactory = -2147024809;
      }
    }
  }
  v7 = WindowsDeleteString_0(string);
  v8 = string;
  if ( !v7 )
    v8 = 0;
  string = v8;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v14 = 0;
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return ActivationFactory;
}

```

## disassembly

```asm
0x1800056f0  mov     [rsp-18h+arg_10], rbx
0x1800056f5  mov     [rsp-18h+arg_18], rsi
0x1800056fa  push    rbp
0x1800056fb  push    rdi
0x1800056fc  push    r14
0x1800056fe  mov     rbp, rsp
0x180005701  sub     rsp, 80h
0x180005708  mov     rax, cs:__security_cookie
0x18000570f  xor     rax, rsp
0x180005712  mov     [rbp+var_8], rax
0x180005716  mov     rdi, rdx
0x180005719  mov     rsi, rcx
0x18000571c  xor     r14d, r14d
0x18000571f  mov     [rbp+var_28], r14
0x180005723  mov     ebx, 80070057h
0x180005728  mov     [rbp+var_10], r14
0x18000572c  mov     [rbp+var_20], r14
0x180005730  mov     [rbp+string], r14
0x180005734  xorps   xmm0, xmm0
0x180005737  movups  xmmword ptr [rbp+sourceString], xmm0
0x18000573b  xorps   xmm1, xmm1
0x18000573e  movdqu  xmmword ptr [rbp+length], xmm1
0x180005743  lea     r8d, [r14+1Eh]
0x180005747  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_Buffer@@3QB_WB; "Windows.Storage.Streams.Buffer"
0x18000574e  lea     rcx, [rbp+sourceString]
0x180005752  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005757  mov     [rbp+string], r14
0x18000575b  lea     rcx, [rbp+sourceString]
0x18000575f  cmp     qword ptr [rbp+length+8], 8
0x180005764  cmovnb  rcx, [rbp+sourceString]; sourceString
0x180005769  lea     r8, [rbp+string]; string
0x18000576d  mov     edx, [rbp+length]; length
0x180005770  call    WindowsCreateString_0
0x180005775  nop
0x180005776  mov     rdx, qword ptr [rbp+length+8]
0x18000577a  cmp     rdx, 8
0x18000577e  jb      short loc_1800057B9
0x180005780  lea     rdx, ds:2[rdx*2]
0x180005788  mov     rcx, [rbp+sourceString]; Block
0x18000578c  mov     rax, rcx
0x18000578f  cmp     rdx, 1000h
0x180005796  jb      short loc_1800057B4
0x180005798  add     rdx, 27h ; '''
0x18000579c  mov     rcx, [rcx-8]
0x1800057a0  sub     rax, rcx
0x1800057a3  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800057a7  cmp     rax, 1Fh
0x1800057ab  jbe     short loc_1800057B4
0x1800057ad  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x1800057b3  int     3; Trap to Debugger
0x1800057b4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800057b9  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800057c1  movdqu  xmmword ptr [rbp+length], xmm0
0x1800057c6  mov     word ptr [rbp+sourceString], r14w
0x1800057cb  test    rsi, rsi
0x1800057ce  jz      loc_1800058EE
0x1800057d4  mov     rax, [rsi]
0x1800057d7  lea     rdx, [rbp+var_28]
0x1800057db  mov     rcx, rsi
0x1800057de  mov     rax, [rax+30h]
0x1800057e2  call    cs:__guard_dispatch_icall_fptr
0x1800057e8  mov     ebx, eax
0x1800057ea  test    eax, eax
0x1800057ec  jnz     loc_1800058EE
0x1800057f2  cmp     [rbp+var_28], 0
0x1800057f7  jnz     short loc_180005803
0x1800057f9  mov     ebx, 80070057h
0x1800057fe  jmp     loc_1800058EE
0x180005803  lea     r8, [rbp+var_20]
0x180005807  lea     rdx, _GUID_71af914d_c10f_484b_bc50_14bc623b3a27
0x18000580e  mov     rcx, [rbp+string]
0x180005812  call    cs:__imp_RoGetActivationFactory
0x180005818  mov     ebx, eax
0x18000581a  test    eax, eax
0x18000581c  jnz     loc_1800058EE
0x180005822  mov     rcx, [rbp+var_20]
0x180005826  mov     rax, [rcx]
0x180005829  mov     r8, rdi
0x18000582c  mov     edx, dword ptr [rbp+var_28]
0x18000582f  mov     rax, [rax+30h]
0x180005833  call    cs:__guard_dispatch_icall_fptr
0x180005839  mov     ebx, eax
0x18000583b  test    eax, eax
0x18000583d  jnz     loc_1800058EE
0x180005843  mov     rax, [rsi]
0x180005846  lea     r8, [rbp+var_10]
0x18000584a  xor     edx, edx
0x18000584c  mov     rcx, rsi
0x18000584f  mov     rax, [rax+40h]
0x180005853  call    cs:__guard_dispatch_icall_fptr
0x180005859  mov     ebx, eax
0x18000585b  test    eax, eax
0x18000585d  jnz     loc_1800058EE
0x180005863  mov     rcx, [rbp+var_10]
0x180005867  test    rcx, rcx
0x18000586a  jz      loc_1800058EE
0x180005870  mov     [rbp+var_18], r14
0x180005874  mov     rax, [rcx]
0x180005877  lea     rdx, [rbp+var_18]
0x18000587b  mov     [rsp+80h+var_60], rdx
0x180005880  lea     r9d, [rbx+1]
0x180005884  mov     r8d, dword ptr [rbp+var_28]
0x180005888  mov     rdx, [rdi]
0x18000588b  mov     rax, [rax+30h]
0x18000588f  call    cs:__guard_dispatch_icall_fptr
0x180005895  mov     ebx, eax
0x180005897  test    eax, eax
0x180005899  jnz     short loc_1800058D7
0x18000589b  nop     dword ptr [rax+rax+00h]
0x1800058a0  mov     rcx, [rbp+var_18]
0x1800058a4  mov     rax, [rcx]
0x1800058a7  mov     rdx, rdi
0x1800058aa  mov     rax, [rax+50h]
0x1800058ae  call    cs:__guard_dispatch_icall_fptr
0x1800058b4  cmp     eax, 8000000Eh
0x1800058b9  jz      short loc_1800058A0
0x1800058bb  mov     rcx, [rdi]
0x1800058be  test    rcx, rcx
0x1800058c1  jz      short loc_1800058D2
0x1800058c3  mov     rax, [rcx]
0x1800058c6  mov     rax, [rax+10h]
0x1800058ca  call    cs:__guard_dispatch_icall_fptr
0x1800058d0  jmp     short loc_1800058D7
0x1800058d2  mov     ebx, 80070057h
0x1800058d7  mov     rcx, [rbp+var_18]
0x1800058db  test    rcx, rcx
0x1800058de  jz      short loc_1800058EE
0x1800058e0  mov     rax, [rcx]
0x1800058e3  mov     rax, [rax+10h]
0x1800058e7  call    cs:__guard_dispatch_icall_fptr
0x1800058ed  nop
0x1800058ee  mov     rcx, [rbp+string]; string
0x1800058f2  call    WindowsDeleteString_0
0x1800058f7  mov     rcx, [rbp+string]
0x1800058fb  test    eax, eax
0x1800058fd  cmovz   rcx, r14
0x180005901  mov     [rbp+string], rcx
0x180005905  mov     rcx, [rbp+var_20]
0x180005909  test    rcx, rcx
0x18000590c  jz      short loc_18000591B
0x18000590e  mov     rax, [rcx]
0x180005911  mov     rax, [rax+10h]
0x180005915  call    cs:__guard_dispatch_icall_fptr
0x18000591b  mov     [rbp+var_20], r14
0x18000591f  mov     rcx, [rbp+var_10]
0x180005923  test    rcx, rcx
0x180005926  jz      short loc_180005936
0x180005928  mov     rax, [rcx]
0x18000592b  mov     rax, [rax+10h]
0x18000592f  call    cs:__guard_dispatch_icall_fptr
0x180005935  nop
0x180005936  mov     eax, ebx
0x180005938  mov     rcx, [rbp+var_8]
0x18000593c  xor     rcx, rsp; StackCookie
0x18000593f  call    __security_check_cookie
0x180005944  lea     r11, [rsp+80h+var_s0]
0x18000594c  mov     rbx, [r11+30h]
0x180005950  mov     rsi, [r11+38h]
0x180005954  mov     rsp, r11
0x180005957  pop     r14
0x180005959  pop     rdi
0x18000595a  pop     rbp
0x18000595b  retn
```
