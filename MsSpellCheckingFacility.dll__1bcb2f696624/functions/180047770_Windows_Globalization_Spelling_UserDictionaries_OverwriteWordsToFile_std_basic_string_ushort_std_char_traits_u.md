# Windows::Globalization::Spelling::UserDictionaries::OverwriteWordsToFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x180047770`
- end: `0x1800479d6`
- name: `?OverwriteWordsToFile@UserDictionaries@Spelling@Globalization@Windows@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@6@@Z`
- size: `614`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops`

## callers

- `0x18003ff68`
- `0x180040d88`

## callees

- `0x1800202e4`
- `0x1800222ac`
- `0x180022e88`
- `0x180038aa0`
- `0x18003a2ec`
- `0x18003e04c`
- `0x18003e358`
- `0x18003e548`
- `0x18004186c`
- `0x180046e94`
- `0x180047770`
- `0x180047d18`
- `0x180047dd0`
- `0x180047dfc`
- `0x180047f1c`
- `0x18004abc0`
- `0x180061320`
- `0x1800c0010`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180047922`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180047922`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180047962`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180047962`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180047951`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180047951`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Windows::Globalization::Spelling::UserDictionaries::OverwriteWordsToFile(
        const WCHAR *lpFileName,
        __int64 **a2)
{
  __int64 v4; // rax
  _QWORD *v5; // rdx
  __int64 v6; // rax
  HANDLE File; // rbx
  _QWORD *v8; // rdx
  LPCVOID *v9; // rdx
  unsigned int v11; // [rsp+30h] [rbp-D0h]
  __int64 v12; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v13[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v14[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v15[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v16[128]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v17[104]; // [rsp+F8h] [rbp-8h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+160h] [rbp+60h] BYREF
  __m128i si128; // [rsp+170h] [rbp+70h]
  _BYTE v20[64]; // [rsp+180h] [rbp+80h] BYREF
  HANDLE hFile; // [rsp+1C0h] [rbp+C0h]
  _QWORD v22[7]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD *v23; // [rsp+208h] [rbp+108h]

  LODWORD(v12) = 0;
  std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v14);
  std::basic_ostream<unsigned short>::operator<<(v15);
  v4 = **a2;
  v12 = v4;
  while ( !*(_BYTE *)(v4 + 25) )
  {
    v5 = (_QWORD *)(v4 + 32);
    if ( *(_QWORD *)(v4 + 56) > 7u )
      v5 = (_QWORD *)*v5;
    v6 = std::_Insert_string<unsigned short,std::char_traits<unsigned short>,unsigned __int64>(
           v15,
           v5,
           *(_QWORD *)(v4 + 48));
    std::operator<<<unsigned short,std::char_traits<unsigned short>>(v6);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,EventRegistrationToken>>>,std::_Iterator_base0>::operator++(&v12);
    v4 = v12;
  }
  *(_OWORD *)lpBuffer = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpBuffer[0]) = 0;
  LODWORD(v12) = 2;
  std::basic_stringbuf<unsigned short>::_Get_buffer_view(v16, v13);
  if ( v13[0] )
    std::wstring::_Assign<unsigned short>(lpBuffer, v13[0], v13[1]);
  v22[0] = &std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable';
  v22[1] = Windows::Globalization::Spelling::CloseHandleIfValid;
  v23 = v22;
  if ( *((_QWORD *)lpFileName + 3) > 7u )
    lpFileName = *(const WCHAR **)lpFileName;
  File = Windows::Globalization::Spelling::UserDictionaries::AttemptCreateFile(
           lpFileName,
           0x40000000u,
           0,
           0,
           2u,
           0x10000000u,
           v11);
  std::function<int (void *)>::function<int (void *)>(v20, v22);
  hFile = File;
  if ( v23 )
  {
    v8 = v22;
    LOBYTE(v8) = v23 != v22;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v23 + 32LL))(v23, v8);
    File = hFile;
  }
  if ( File == (HANDLE)-1LL )
  {
    std::_Func_class<int,void *>::operator()(v20);
    std::_Func_class<void,UserDictionary *>::_Tidy(v20);
    std::wstring::_Tidy_deallocate(lpBuffer);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(v17);
    std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(v17);
  }
  else
  {
    v9 = lpBuffer;
    if ( si128.m128i_i64[1] > 7uLL )
      v9 = (LPCVOID *)lpBuffer[0];
    if ( WriteFile(File, v9, 2 * si128.m128i_i32[0], 0, 0) && SetEndOfFile(hFile) )
    {
      std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(v20);
      std::wstring::_Tidy_deallocate(lpBuffer);
      std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v14);
      return 1;
    }
    std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(v20);
    std::wstring::_Tidy_deallocate(lpBuffer);
    std::basic_stringstream<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::`vbase destructor'(v14);
  }
  return 0;
}

```

## disassembly

```asm
0x180047770  mov     [rsp-8+arg_8], rbx
0x180047775  mov     [rsp-8+arg_10], rdi
0x18004777a  push    rbp
0x18004777b  lea     rbp, [rsp-120h]
0x180047783  sub     rsp, 220h
0x18004778a  mov     rax, cs:__security_cookie
0x180047791  xor     rax, rsp
0x180047794  mov     [rbp+120h+var_10], rax
0x18004779b  mov     rbx, rdx
0x18004779e  mov     rdi, rcx
0x1800477a1  mov     dword ptr [rsp+220h+var_1E0], 0
0x1800477a9  lea     rcx, [rsp+220h+var_1C0]
0x1800477ae  call    ??0?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x1800477b3  nop
0x1800477b4  lea     rcx, [rsp+220h+var_1B0]
0x1800477b9  call    ??6?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV01@G@Z; std::basic_ostream<ushort>::operator<<(ushort)
0x1800477be  mov     rax, [rbx]
0x1800477c1  mov     rax, [rax]
0x1800477c4  mov     [rsp+220h+var_1E0], rax
0x1800477c9  cmp     byte ptr [rax+19h], 0
0x1800477cd  jnz     short loc_180047804
0x1800477cf  lea     rdx, [rax+20h]
0x1800477d3  mov     r8, [rdx+10h]
0x1800477d7  cmp     qword ptr [rdx+18h], 7
0x1800477dc  jbe     short loc_1800477E1
0x1800477de  mov     rdx, [rdx]
0x1800477e1  lea     rcx, [rsp+220h+var_1B0]
0x1800477e6  call    ??$_Insert_string@GU?$char_traits@G@std@@_K@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@QEBG_K@Z; std::_Insert_string<ushort,std::char_traits<ushort>,unsigned __int64>(std::basic_ostream<ushort> &,ushort const * const,unsigned __int64)
0x1800477eb  mov     rcx, rax
0x1800477ee  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x1800477f3  lea     rcx, [rsp+220h+var_1E0]
0x1800477f8  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKUEventRegistrationToken@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,EventRegistrationToken>>>,std::_Iterator_base0>::operator++(void)
0x1800477fd  mov     rax, [rsp+220h+var_1E0]
0x180047802  jmp     short loc_1800477C9
0x180047804  xorps   xmm0, xmm0
0x180047807  movups  xmmword ptr [rbp+120h+lpBuffer], xmm0
0x18004780b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180047813  movdqu  [rbp+120h+var_B0], xmm1
0x180047818  xor     eax, eax
0x18004781a  mov     word ptr [rbp+120h+lpBuffer], ax
0x18004781e  lea     ebx, [rax+2]
0x180047821  mov     dword ptr [rsp+220h+var_1E0], ebx
0x180047825  lea     rdx, [rsp+220h+var_1D8]
0x18004782a  lea     rcx, [rsp+220h+var_1A8]
0x18004782f  call    ?_Get_buffer_view@?$basic_stringbuf@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AU_Buffer_view@12@XZ; std::basic_stringbuf<ushort>::_Get_buffer_view(void)
0x180047834  mov     rdx, [rsp+220h+var_1D8]
0x180047839  test    rdx, rdx
0x18004783c  jz      short loc_18004784D
0x18004783e  mov     r8, [rsp+220h+var_1D0]
0x180047843  lea     rcx, [rbp+120h+lpBuffer]
0x180047847  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18004784c  nop
0x18004784d  lea     rax, ??_7?$_Func_impl_no_alloc@P6AHPEAX@ZHPEAX@std@@6B@; const std::_Func_impl_no_alloc<int (*)(void *),int,void *>::`vftable'
0x180047854  mov     [rbp+120h+var_50], rax
0x18004785b  lea     rax, Windows__Globalization__Spelling__CloseHandleIfValid
0x180047862  mov     [rbp+120h+var_48], rax
0x180047869  lea     rax, [rbp+120h+var_50]
0x180047870  mov     [rbp+120h+var_18], rax
0x180047877  cmp     qword ptr [rdi+18h], 7
0x18004787c  jbe     short loc_180047881
0x18004787e  mov     rdi, [rdi]
0x180047881  mov     [rsp+220h+var_1F8], 10000000h; DWORD
0x180047889  mov     dword ptr [rsp+220h+lpOverlapped], ebx; DWORD
0x18004788d  xor     r9d, r9d; lpSecurityAttributes
0x180047890  xor     r8d, r8d; dwShareMode
0x180047893  mov     edx, 40000000h; dwDesiredAccess
0x180047898  mov     rcx, rdi; lpFileName
0x18004789b  call    ?AttemptCreateFile@UserDictionaries@Spelling@Globalization@Windows@@CAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKK@Z; Windows::Globalization::Spelling::UserDictionaries::AttemptCreateFile(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,ulong)
0x1800478a0  mov     rbx, rax
0x1800478a3  lea     rdx, [rbp+120h+var_50]
0x1800478aa  lea     rcx, [rbp+120h+var_A0]
0x1800478b1  call    ??0?$function@$$A6AHPEAX@Z@std@@QEAA@$$QEAV01@@Z; std::function<int (void *)>::function<int (void *)>(std::function<int (void *)> &&)
0x1800478b6  mov     [rbp+120h+hFile], rbx
0x1800478bd  mov     rcx, [rbp+120h+var_18]
0x1800478c4  test    rcx, rcx
0x1800478c7  jz      short loc_1800478E9
0x1800478c9  mov     rax, [rcx]
0x1800478cc  lea     rdx, [rbp+120h+var_50]
0x1800478d3  cmp     rcx, rdx
0x1800478d6  setnz   dl
0x1800478d9  mov     rax, [rax+20h]
0x1800478dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800478e2  mov     rbx, [rbp+120h+hFile]
0x1800478e9  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800478ed  jnz     short loc_18004792D
0x1800478ef  mov     rdx, rbx
0x1800478f2  lea     rcx, [rbp+120h+var_A0]
0x1800478f9  call    ??R?$_Func_class@HPEAX@std@@QEBAHPEAX@Z; std::_Func_class<int,void *>::operator()(void *)
0x1800478fe  lea     rcx, [rbp+120h+var_A0]
0x180047905  call    ?_Tidy@?$_Func_class@XPEAVUserDictionary@@@std@@IEAAXXZ; std::_Func_class<void,UserDictionary *>::_Tidy(void)
0x18004790a  nop
0x18004790b  lea     rcx, [rbp+120h+lpBuffer]
0x18004790f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180047914  nop
0x180047915  lea     rcx, [rbp+120h+var_128]
0x180047919  call    ??1?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEAA@XZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)
0x18004791e  lea     rcx, [rbp+120h+var_128]
0x180047922  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x180047928  jmp     loc_1800479B0
0x18004792d  mov     r8d, dword ptr [rbp+120h+var_B0]
0x180047931  lea     rdx, [rbp+120h+lpBuffer]
0x180047935  cmp     qword ptr [rbp+120h+var_B0+8], 7
0x18004793a  cmova   rdx, [rbp+120h+lpBuffer]; lpBuffer
0x18004793f  add     r8d, r8d; nNumberOfBytesToWrite
0x180047942  mov     [rsp+220h+lpOverlapped], 0; lpOverlapped
0x18004794b  xor     r9d, r9d; lpNumberOfBytesWritten
0x18004794e  mov     rcx, rbx; hFile
0x180047951  call    cs:__imp_WriteFile
0x180047957  test    eax, eax
0x180047959  jz      short loc_180047990
0x18004795b  mov     rcx, [rbp+120h+hFile]; hFile
0x180047962  call    cs:__imp_SetEndOfFile
0x180047968  test    eax, eax
0x18004796a  jz      short loc_180047990
0x18004796c  lea     rcx, [rbp+120h+var_A0]
0x180047973  call    ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
0x180047978  lea     rcx, [rbp+120h+lpBuffer]
0x18004797c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180047981  nop
0x180047982  lea     rcx, [rsp+220h+var_1C0]
0x180047987  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x18004798c  mov     al, 1
0x18004798e  jmp     short loc_1800479B2
0x180047990  lea     rcx, [rbp+120h+var_A0]
0x180047997  call    ??1?$unique_ptr@XV?$function@$$A6AHPEAX@Z@std@@@std@@QEAA@XZ; std::unique_ptr<void,std::function<int (void *)>>::~unique_ptr<void,std::function<int (void *)>>(void)
0x18004799c  lea     rcx, [rbp+120h+lpBuffer]
0x1800479a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800479a5  nop
0x1800479a6  lea     rcx, [rsp+220h+var_1C0]
0x1800479ab  call    ??_D?$basic_stringstream@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXXZ; std::basic_stringstream<ushort,std::char_traits<ushort>,std::allocator<ushort>>::`vbase destructor'(void)
0x1800479b0  xor     al, al
0x1800479b2  mov     rcx, [rbp+120h+var_10]
0x1800479b9  xor     rcx, rsp; StackCookie
0x1800479bc  call    __security_check_cookie
0x1800479c1  lea     r11, [rsp+220h+var_s0]
0x1800479c9  mov     rbx, [r11+18h]
0x1800479cd  mov     rdi, [r11+20h]
0x1800479d1  mov     rsp, r11
0x1800479d4  pop     rbp
0x1800479d5  retn
```
