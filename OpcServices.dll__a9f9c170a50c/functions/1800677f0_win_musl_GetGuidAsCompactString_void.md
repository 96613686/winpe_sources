# win_musl::GetGuidAsCompactString(void)

- ea: `0x1800677f0`
- end: `0x180067980`
- name: `?GetGuidAsCompactString@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ`
- size: `400`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180067218`
- `0x1800f9a14`

## callees

- `0x180015a68`
- `0x18001a810`
- `0x1800517a0`
- `0x1800677f0`
- `0x1800cd38c`
- `0x1800cd878`
- `0x1800d5fe4`
- `0x180117716`
- `0x180117740`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180067830`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180067830`

## string_xrefs

- `0x180067926`: `Call to CoCreateGuid failed with HResult 0x%X.`

## pseudocode

```c
__int64 __fastcall win_musl::GetGuidAsCompactString(__int64 a1)
{
  HRESULT v2; // ebx
  signed int i; // ebx
  unsigned __int8 v4; // r9
  __int64 j; // r10
  unsigned int v6; // r9d
  __int64 v7; // rcx
  GUID pguid; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t v11[32]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t v12[512]; // [rsp+140h] [rbp+40h] BYREF

  pguid = 0;
  v2 = CoCreateGuid(&pguid);
  if ( v2 < 0 )
  {
    memset_0(v12, 0, sizeof(v12));
    StringCchPrintfW(v12, 0x200u, L"Call to CoCreateGuid failed with HResult 0x%X.", (unsigned int)v2);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x63u,
      v2,
      (struct win_musl::TStringEllipseBase *)v12);
    throw (SplException::THResultException *)pExceptionObject;
  }
  for ( i = 0; memcmp_0(&pguid, &GUID_NULL, 0x10u) && (unsigned int)i < 0x1D; ++i )
  {
    v4 = 0;
    for ( j = 0; j != 16; ++j )
    {
      v6 = *((unsigned __int8 *)&pguid.Data1 + j) + (v4 << 8);
      *((_BYTE *)&pguid.Data1 + j) = v6 / 0x25;
      v4 = v6 % 0x25;
    }
    v7 = i;
    v11[v7] = aAbcdefghijklmn[v4];
  }
  if ( (unsigned __int64)(2LL * i) >= 0x3C )
    _report_rangecheckfailure();
  v11[i] = 0;
  std::wstring::wstring(a1, v11);
  return a1;
}

```

## disassembly

```asm
0x1800677f0  mov     [rsp-8+arg_8], rbx
0x1800677f5  mov     [rsp-8+arg_10], rdi
0x1800677fa  push    rbp
0x1800677fb  lea     rbp, [rsp-450h]
0x180067803  sub     rsp, 550h
0x18006780a  mov     rax, cs:__security_cookie
0x180067811  xor     rax, rsp
0x180067814  mov     [rbp+450h+var_10], rax
0x18006781b  mov     qword ptr [rsp+550h+pguid.Data1], rcx
0x180067820  mov     rdi, rcx
0x180067823  xorps   xmm0, xmm0
0x180067826  lea     rcx, [rsp+550h+pguid]; pguid
0x18006782b  movups  xmmword ptr [rsp+550h+pguid.Data1], xmm0
0x180067830  call    cs:__imp_CoCreateGuid
0x180067836  mov     ebx, eax
0x180067838  test    eax, eax
0x18006783a  js      loc_180067912
0x180067840  xor     ebx, ebx
0x180067842  mov     r8d, 10h; Size
0x180067848  lea     rdx, GUID_NULL; Buf2
0x18006784f  lea     rcx, [rsp+550h+pguid]; Buf1
0x180067854  call    memcmp_0
0x180067859  test    eax, eax
0x18006785b  jz      short loc_1800678C7
0x18006785d  cmp     ebx, 1Dh
0x180067860  jnb     short loc_1800678C7
0x180067862  xor     r9b, r9b
0x180067865  xor     r10d, r10d
0x180067868  movzx   eax, byte ptr [rsp+r10+550h+pguid.Data1]
0x18006786e  movzx   r9d, r9b
0x180067872  shl     r9d, 8
0x180067876  add     r9d, eax
0x180067879  mov     eax, 0BACF914Dh
0x18006787e  mul     r9d
0x180067881  mov     r8d, r9d
0x180067884  sub     r8d, edx
0x180067887  shr     r8d, 1
0x18006788a  add     r8d, edx
0x18006788d  shr     r8d, 5
0x180067891  movzx   eax, r8b
0x180067895  imul    ecx, eax, 25h ; '%'
0x180067898  mov     byte ptr [rsp+r10+550h+pguid.Data1], r8b
0x18006789d  inc     r10
0x1800678a0  sub     r9b, cl
0x1800678a3  cmp     r10, 10h
0x1800678a7  jnz     short loc_180067868
0x1800678a9  movsxd  rcx, ebx
0x1800678ac  lea     rdx, aAbcdefghijklmn; "abcdefghijklmnopqrstuvwxyz_0123456789"
0x1800678b3  movzx   eax, r9b
0x1800678b7  inc     ebx
0x1800678b9  movzx   eax, word ptr [rdx+rax*2]
0x1800678bd  mov     [rbp+rcx*2+450h+var_450], ax
0x1800678c2  jmp     loc_180067842
0x1800678c7  movsxd  rcx, ebx
0x1800678ca  lea     rax, [rcx+rcx]
0x1800678ce  cmp     rax, 3Ch ; '<'
0x1800678d2  jnb     loc_18006797A
0x1800678d8  xor     ecx, ecx
0x1800678da  lea     rdx, [rbp+450h+var_450]
0x1800678de  mov     [rbp+rax+450h+var_450], cx
0x1800678e3  mov     rcx, rdi
0x1800678e6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800678eb  mov     rax, rdi
0x1800678ee  mov     rcx, [rbp+450h+var_10]
0x1800678f5  xor     rcx, rsp; StackCookie
0x1800678f8  call    __security_check_cookie
0x1800678fd  lea     r11, [rsp+550h+var_s0]
0x180067905  mov     rbx, [r11+18h]
0x180067909  mov     rdi, [r11+20h]
0x18006790d  mov     rsp, r11
0x180067910  pop     rbp
0x180067911  retn
0x180067912  xor     edx, edx; Val
0x180067914  lea     rcx, [rbp+450h+var_410]; void *
0x180067918  mov     r8d, 400h; Size
0x18006791e  call    memset_0
0x180067923  mov     r9d, ebx
0x180067926  lea     r8, aCallToCocreate; "Call to CoCreateGuid failed with HResul"...
0x18006792d  mov     edx, 200h; unsigned __int64
0x180067932  lea     rcx, [rbp+450h+var_410]; wchar_t *
0x180067936  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18006793b  lea     rax, [rbp+450h+var_410]
0x18006793f  mov     [rsp+550h+var_520], rax; struct win_musl::TStringEllipseBase *
0x180067944  lea     r9, word_18013A0B6
0x18006794b  mov     [rsp+550h+var_528], ebx; unsigned int
0x18006794f  lea     r8, aNoFilename; "(no filename)"
0x180067956  lea     rcx, [rsp+550h+pExceptionObject]; this
0x18006795b  mov     [rsp+550h+var_530], 63h ; 'c'; unsigned int
0x180067963  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180067968  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18006796f  lea     rcx, [rsp+550h+pExceptionObject]; pExceptionObject
0x180067974  call    _CxxThrowException_0
0x18006797a  call    __report_rangecheckfailure
```
