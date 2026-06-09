# _anonymous_namespace_::StripUsername

- ea: `0x180046d74`
- end: `0x180046f16`
- name: `_anonymous_namespace_::StripUsername`
- size: `418`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800210bc`
- `0x18002195c`

## callees

- `0x1800133c4`
- `0x180022110`
- `0x18003d35c`
- `0x180046798`
- `0x180046d74`
- `0x1800609f8`
- `0x180060c18`
- `0x18006affc`
- `0x1800760d0`
- `0x1800764d0`
- `0x18007704c`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x180046dc2`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180046dc2`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::StripUsername(_QWORD *a1)
{
  int BasicProfileFolderPath; // ebx
  unsigned __int64 v3; // r9
  unsigned __int64 v4; // rax
  _QWORD *v5; // r14
  __int64 v7; // rdx
  __int64 v8; // rdi
  char *v9; // rbx
  __int64 v10; // rax
  unsigned __int64 v11; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE Src[32]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v13[40]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v14[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  memset_0(v14, 0, 0x208u);
  BasicProfileFolderPath = GetBasicProfileFolderPath(5, 0, v14, 260);
  if ( BasicProfileFolderPath >= 0 )
  {
    v3 = -1;
    do
      ++v3;
    while ( v14[v3] );
    v4 = a1[2];
    if ( a1[3] <= 7u )
      v5 = a1;
    else
      v5 = (_QWORD *)*a1;
    if ( v3 > v4 )
      return 0;
    if ( v3 )
    {
      v9 = (char *)v5 + 2 * v4;
      v10 = _std_search_2(v5, v9, v14);
      if ( (char *)v10 == v9 )
        return 0;
      v8 = (v10 - (__int64)v5) >> 1;
      if ( v8 == -1 )
        return 0;
    }
    else
    {
      v8 = 0;
    }
    v11 = 0;
    BasicProfileFolderPath = StringCchLengthW(v14, 0x104u, &v11);
    if ( BasicProfileFolderPath < 0 )
    {
      v7 = 245;
      goto LABEL_10;
    }
    std::wstring::wstring(Src, L"%USERPROFILE%");
    std::wstring::substr(a1, v13, v8 + v11, -1);
    std::wstring::_Append<unsigned short>(Src);
    std::wstring::~wstring(v13);
    std::wstring::operator=(a1, Src);
    std::wstring::~wstring(Src);
    return 0;
  }
  v7 = 237;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\kspflowtracing.cpp",
    (const char *)(unsigned int)BasicProfileFolderPath,
    v11);
  return (unsigned int)BasicProfileFolderPath;
}

```

## disassembly

```asm
0x180046d74  push    rbp
0x180046d76  push    rbx
0x180046d77  push    rsi
0x180046d78  push    rdi
0x180046d79  push    r14
0x180046d7b  push    r15
0x180046d7d  lea     rbp, [rsp-198h]
0x180046d85  sub     rsp, 298h
0x180046d8c  mov     rax, cs:__security_cookie
0x180046d93  xor     rax, rsp
0x180046d96  mov     [rbp+1C0h+var_40], rax
0x180046d9d  mov     rsi, rcx
0x180046da0  xor     edx, edx; Val
0x180046da2  mov     r8d, 208h; Size
0x180046da8  lea     rcx, [rsp+2C0h+var_250]; void *
0x180046dad  call    memset_0
0x180046db2  mov     r9d, 104h
0x180046db8  lea     r8, [rsp+2C0h+var_250]
0x180046dbd  xor     edx, edx
0x180046dbf  lea     ecx, [rdx+5]
0x180046dc2  call    cs:__imp_GetBasicProfileFolderPath
0x180046dc9  nop     dword ptr [rax+rax+00h]
0x180046dce  mov     ebx, eax
0x180046dd0  xor     r15d, r15d
0x180046dd3  test    eax, eax
0x180046dd5  js      short loc_180046E28
0x180046dd7  lea     rax, [rsp+2C0h+var_250]
0x180046ddc  or      r9, 0FFFFFFFFFFFFFFFFh
0x180046de0  inc     r9
0x180046de3  cmp     [rax+r9*2], r15w
0x180046de8  jnz     short loc_180046DE0
0x180046dea  mov     rax, [rsi+10h]
0x180046dee  cmp     qword ptr [rsi+18h], 7
0x180046df3  jbe     short loc_180046E23
0x180046df5  mov     r14, [rsi]
0x180046df8  cmp     r9, rax
0x180046dfb  jbe     loc_180046EE4
0x180046e01  xor     eax, eax
0x180046e03  mov     rcx, [rbp+1C0h+var_40]
0x180046e0a  xor     rcx, rsp; StackCookie
0x180046e0d  call    __security_check_cookie
0x180046e12  add     rsp, 298h
0x180046e19  pop     r15
0x180046e1b  pop     r14
0x180046e1d  pop     rdi
0x180046e1e  pop     rsi
0x180046e1f  pop     rbx
0x180046e20  pop     rbp
0x180046e21  retn
0x180046e23  mov     r14, rsi
0x180046e26  jmp     short loc_180046DF8
0x180046e28  mov     edx, 0EDh; void *
0x180046e2d  lea     r8, aOnecoreBaseNgs_18; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x180046e34  mov     r9d, ebx; char *
0x180046e37  mov     rcx, [rbp+1C8h]; this
0x180046e3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046e43  mov     eax, ebx
0x180046e45  jmp     short loc_180046E03
0x180046e47  sub     rdi, r14
0x180046e4a  sar     rdi, 1
0x180046e4d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180046e51  jz      short loc_180046E01
0x180046e53  mov     [rsp+2C0h+var_2A0], r15
0x180046e58  lea     r8, [rsp+2C0h+var_2A0]; unsigned __int64 *
0x180046e5d  mov     edx, 104h; unsigned __int64
0x180046e62  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x180046e67  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180046e6c  mov     ebx, eax
0x180046e6e  test    eax, eax
0x180046e70  jns     short loc_180046E79
0x180046e72  mov     edx, 0F5h
0x180046e77  jmp     short loc_180046E2D
0x180046e79  lea     rdx, aUserprofile; "%USERPROFILE%"
0x180046e80  lea     rcx, [rsp+2C0h+Src]
0x180046e85  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180046e8a  mov     r8, [rsp+2C0h+var_2A0]
0x180046e8f  add     r8, rdi
0x180046e92  or      r9, 0FFFFFFFFFFFFFFFFh
0x180046e96  lea     rdx, [rsp+2C0h+var_278]
0x180046e9b  mov     rcx, rsi
0x180046e9e  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180046ea3  mov     r8, [rax+10h]
0x180046ea7  cmp     qword ptr [rax+18h], 7
0x180046eac  jbe     short loc_180046EB1
0x180046eae  mov     rax, [rax]
0x180046eb1  mov     rdx, rax
0x180046eb4  lea     rcx, [rsp+2C0h+Src]; Src
0x180046eb9  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180046ebe  lea     rcx, [rsp+2C0h+var_278]
0x180046ec3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180046ec8  lea     rdx, [rsp+2C0h+Src]
0x180046ecd  mov     rcx, rsi
0x180046ed0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180046ed5  lea     rcx, [rsp+2C0h+Src]
0x180046eda  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180046edf  jmp     loc_180046E01
0x180046ee4  test    r9, r9
0x180046ee7  jnz     short loc_180046EF1
0x180046ee9  mov     rdi, r15
0x180046eec  jmp     loc_180046E53
0x180046ef1  lea     rbx, [r14+rax*2]
0x180046ef5  lea     r8, [rsp+2C0h+var_250]
0x180046efa  mov     rdx, rbx
0x180046efd  mov     rcx, r14
0x180046f00  call    __std_search_2
0x180046f05  mov     rdi, rax
0x180046f08  cmp     rax, rbx
0x180046f0b  jz      loc_180046E01
0x180046f11  jmp     loc_180046E47
```
