# Windows::Registry::TryGetSystemValue(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x180033bf0`
- end: `0x180033e40`
- name: `?TryGetSystemValue@Registry@Windows@@UEAA?AV?$optional@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@V?$basic_zstring_view@_W@wil@@00@Z`
- size: `592`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000d6a8`
- `0x18000d948`
- `0x180011a18`

## callees

- `0x180009380`
- `0x180033b00`
- `0x180033bf0`
- `0x180034a30`
- `0x18003ba50`
- `0x180056500`

## string_xrefs

- `0x180033e2b`: `C:\__w\1\s\src\orchestrator\system\Windows\Registry.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::Registry::TryGetSystemValue(__int64 a1, __int64 a2, __int128 *a3, _OWORD *a4, __int128 *a5)
{
  _QWORD *v7; // rdx
  char v8; // di
  __int64 v9; // rax
  int v10; // ecx
  char v11; // di
  int v13; // [rsp+20h] [rbp-E0h]
  _QWORD v14[4]; // [rsp+38h] [rbp-C8h] BYREF
  char v15; // [rsp+58h] [rbp-A8h]
  char v16; // [rsp+60h] [rbp-A0h]
  __int128 v17; // [rsp+70h] [rbp-90h] BYREF
  __int64 v18; // [rsp+80h] [rbp-80h]
  int v19[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v20; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v21[4]; // [rsp+B0h] [rbp-50h] BYREF
  char v22; // [rsp+D0h] [rbp-30h]
  char v23; // [rsp+D8h] [rbp-28h]
  char *v24; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v25[4]; // [rsp+E8h] [rbp-18h] BYREF
  char v26; // [rsp+108h] [rbp+8h]
  char v27; // [rsp+110h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v18 = a2;
  v17 = *a5;
  *(_OWORD *)v19 = *a4;
  v20 = *a3;
  Windows::Registry::GetValue(a1, (__int64)&v24, (__int64)a3, &v20, v19, (const WCHAR **)&v17);
  if ( (int)v24 < 0 && (_DWORD)v24 != -2147023728 && (_DWORD)v24 != -2147024894 && (_DWORD)v24 != -2147023878 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\Windows\\Registry.hpp",
      (const char *)(unsigned int)v24,
      v13);
  if ( (int)v24 < 0 )
  {
    v23 = 0;
    v7 = v21;
    v8 = 1;
    v9 = v21[0];
    v10 = v21[0];
    goto LABEL_22;
  }
  v16 = 0;
  if ( !v27 )
  {
    v9 = v14[0];
    v10 = v14[0];
    goto LABEL_21;
  }
  *(_QWORD *)&v17 = v14;
  v15 = -1;
  switch ( v26 )
  {
    case -1:
      v9 = v14[0];
      goto LABEL_18;
    case 0:
      v10 = v25[0];
      LODWORD(v14[0]) = v25[0];
      v15 = 0;
      v9 = v14[0];
      goto LABEL_19;
    case 1:
      v9 = v25[0];
      v14[0] = v25[0];
      v15 = 1;
LABEL_18:
      v10 = v9;
      goto LABEL_19;
  }
  std::wstring::wstring(v14, v25);
  v15 = 2;
  v9 = v14[0];
  v10 = v14[0];
LABEL_19:
  v16 = 1;
LABEL_21:
  v7 = v14;
  v8 = 2;
LABEL_22:
  *(_BYTE *)(a2 + 40) = 0;
  if ( *((_BYTE *)v7 + 40) )
  {
    *(_QWORD *)&v17 = a2;
    *(_BYTE *)(a2 + 32) = -1;
    if ( *((char *)v7 + 32) != -1 )
    {
      if ( *((_BYTE *)v7 + 32) )
      {
        if ( *((_BYTE *)v7 + 32) == 1 )
        {
          *(_QWORD *)a2 = v9;
          *(_BYTE *)(a2 + 32) = 1;
        }
        else
        {
          std::wstring::wstring(a2, v7);
          *(_BYTE *)(a2 + 32) = 2;
        }
      }
      else
      {
        *(_DWORD *)a2 = v10;
        *(_BYTE *)(a2 + 32) = 0;
      }
    }
    *(_BYTE *)(a2 + 40) = 1;
  }
  v11 = v8 | 4;
  if ( (v11 & 2) != 0 )
  {
    v11 &= ~2u;
    if ( v16 )
    {
      if ( v15 != -1 && v15 && v15 != 1 )
        std::wstring::~wstring(v14);
    }
  }
  if ( (v11 & 1) != 0 && v23 && v22 != -1 && v22 && v22 != 1 )
    std::wstring::~wstring(v21);
  if ( v27 && v26 != -1 && v26 && v26 != 1 )
    std::wstring::~wstring(v25);
  return a2;
}

```

## disassembly

```asm
0x180033bf0  push    rbp
0x180033bf2  push    rbx
0x180033bf3  push    rdi
0x180033bf4  lea     rbp, [rsp-20h]
0x180033bf9  sub     rsp, 120h
0x180033c00  mov     rax, cs:__security_cookie
0x180033c07  xor     rax, rsp
0x180033c0a  mov     [rbp+30h+var_18], rax
0x180033c0e  mov     rbx, rdx
0x180033c11  mov     [rbp+30h+var_B0], rdx
0x180033c15  mov     rax, [rbp+30h+arg_20]
0x180033c19  mov     [rsp+130h+var_100], 0
0x180033c21  movups  xmm0, xmmword ptr [rax]
0x180033c24  movdqu  [rsp+130h+var_C0], xmm0
0x180033c2a  movups  xmm1, xmmword ptr [r9]
0x180033c2e  movdqu  xmmword ptr [rbp+30h+var_A0], xmm1
0x180033c33  movups  xmm0, xmmword ptr [r8]
0x180033c37  movdqu  [rbp+30h+var_90], xmm0
0x180033c3c  lea     rax, [rsp+130h+var_C0]
0x180033c41  mov     [rsp+130h+var_108], rax
0x180033c46  lea     rax, [rbp+30h+var_A0]
0x180033c4a  mov     qword ptr [rsp+130h+var_110], rax; int
0x180033c4f  lea     r9, [rbp+30h+var_90]
0x180033c53  lea     rdx, [rbp+30h+var_50]
0x180033c57  call    ?GetValue@Registry@Windows@@QEAA?AU?$pair@JV?$optional@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@11@Z; Windows::Registry::GetValue(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180033c5c  nop
0x180033c5d  mov     eax, dword ptr [rbp+30h+var_50]
0x180033c60  test    eax, eax
0x180033c62  jns     short loc_180033C7D
0x180033c64  cmp     eax, 80070490h
0x180033c69  jz      short loc_180033C7D
0x180033c6b  cmp     eax, 80070002h
0x180033c70  jz      short loc_180033C7D
0x180033c72  cmp     eax, 800703FAh
0x180033c77  jz      short loc_180033C7D
0x180033c79  mov     cl, 1
0x180033c7b  jmp     short loc_180033C7F
0x180033c7d  xor     cl, cl
0x180033c7f  mov     r10, [rbp+38h]
0x180033c83  test    cl, cl
0x180033c85  jnz     loc_180033E28
0x180033c8b  test    eax, eax
0x180033c8d  jns     short loc_180033CA6
0x180033c8f  mov     [rbp+30h+var_58], cl
0x180033c92  lea     rdx, [rbp+30h+var_80]
0x180033c96  mov     edi, 1
0x180033c9b  mov     rax, [rbp+30h+var_80]
0x180033c9f  mov     ecx, eax
0x180033ca1  jmp     loc_180033D36
0x180033ca6  mov     [rsp+130h+var_D0], 0
0x180033cab  cmp     [rbp+30h+var_20], 0
0x180033caf  jz      short loc_180033D25
0x180033cb1  lea     rax, [rsp+130h+var_F8]
0x180033cb6  mov     qword ptr [rsp+130h+var_C0], rax
0x180033cbb  mov     [rsp+130h+var_D8], 0FFh
0x180033cc0  movsx   rax, [rbp+30h+var_28]
0x180033cc5  add     rax, 1
0x180033cc9  jz      short loc_180033D17
0x180033ccb  sub     rax, 1
0x180033ccf  jz      short loc_180033D04
0x180033cd1  cmp     rax, 1
0x180033cd5  jz      short loc_180033CF4
0x180033cd7  lea     rdx, [rbp+30h+var_48]
0x180033cdb  lea     rcx, [rsp+130h+var_F8]
0x180033ce0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180033ce5  mov     [rsp+130h+var_D8], 2
0x180033cea  mov     rax, [rsp+130h+var_F8]
0x180033cef  mov     rcx, rax
0x180033cf2  jmp     short loc_180033D1E
0x180033cf4  mov     rax, [rbp+30h+var_48]
0x180033cf8  mov     [rsp+130h+var_F8], rax
0x180033cfd  mov     [rsp+130h+var_D8], 1
0x180033d02  jmp     short loc_180033D1C
0x180033d04  mov     ecx, dword ptr [rbp+30h+var_48]
0x180033d07  mov     dword ptr [rsp+130h+var_F8], ecx
0x180033d0b  mov     [rsp+130h+var_D8], 0
0x180033d10  mov     rax, [rsp+130h+var_F8]
0x180033d15  jmp     short loc_180033D1E
0x180033d17  mov     rax, [rsp+130h+var_F8]
0x180033d1c  mov     ecx, eax
0x180033d1e  mov     [rsp+130h+var_D0], 1
0x180033d23  jmp     short loc_180033D2C
0x180033d25  mov     rax, [rsp+130h+var_F8]
0x180033d2a  mov     ecx, eax
0x180033d2c  lea     rdx, [rsp+130h+var_F8]
0x180033d31  mov     edi, 2
0x180033d36  mov     [rsp+130h+var_100], edi
0x180033d3a  mov     byte ptr [rbx+28h], 0
0x180033d3e  cmp     byte ptr [rdx+28h], 0
0x180033d42  jz      short loc_180033D85
0x180033d44  mov     qword ptr [rsp+130h+var_C0], rbx
0x180033d49  mov     byte ptr [rbx+20h], 0FFh
0x180033d4d  movsx   r8, byte ptr [rdx+20h]
0x180033d52  add     r8, 1
0x180033d56  jz      short loc_180033D81
0x180033d58  sub     r8, 1
0x180033d5c  jz      short loc_180033D7B
0x180033d5e  cmp     r8, 1
0x180033d62  jz      short loc_180033D72
0x180033d64  mov     rcx, rbx
0x180033d67  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180033d6c  mov     byte ptr [rbx+20h], 2
0x180033d70  jmp     short loc_180033D81
0x180033d72  mov     [rbx], rax
0x180033d75  mov     byte ptr [rbx+20h], 1
0x180033d79  jmp     short loc_180033D81
0x180033d7b  mov     [rbx], ecx
0x180033d7d  mov     byte ptr [rbx+20h], 0
0x180033d81  mov     byte ptr [rbx+28h], 1
0x180033d85  or      edi, 4
0x180033d88  test    dil, 2
0x180033d8c  jz      short loc_180033DBB
0x180033d8e  and     edi, 0FFFFFFFDh
0x180033d91  cmp     [rsp+130h+var_D0], 0
0x180033d96  jz      short loc_180033DBB
0x180033d98  movsx   rax, [rsp+130h+var_D8]
0x180033d9e  add     rax, 1
0x180033da2  jz      short loc_180033DBB
0x180033da4  sub     rax, 1
0x180033da8  jz      short loc_180033DBB
0x180033daa  cmp     rax, 1
0x180033dae  jz      short loc_180033DBB
0x180033db0  lea     rcx, [rsp+130h+var_F8]; void *
0x180033db5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033dba  nop
0x180033dbb  test    dil, 1
0x180033dbf  jz      short loc_180033DE8
0x180033dc1  cmp     [rbp+30h+var_58], 0
0x180033dc5  jz      short loc_180033DE8
0x180033dc7  movsx   rax, [rbp+30h+var_60]
0x180033dcc  add     rax, 1
0x180033dd0  jz      short loc_180033DE8
0x180033dd2  sub     rax, 1
0x180033dd6  jz      short loc_180033DE8
0x180033dd8  cmp     rax, 1
0x180033ddc  jz      short loc_180033DE8
0x180033dde  lea     rcx, [rbp+30h+var_80]; void *
0x180033de2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033de7  nop
0x180033de8  cmp     [rbp+30h+var_20], 0
0x180033dec  jz      short loc_180033E0E
0x180033dee  movsx   rax, [rbp+30h+var_28]
0x180033df3  add     rax, 1
0x180033df7  jz      short loc_180033E0E
0x180033df9  sub     rax, 1
0x180033dfd  jz      short loc_180033E0E
0x180033dff  cmp     rax, 1
0x180033e03  jz      short loc_180033E0E
0x180033e05  lea     rcx, [rbp+30h+var_48]; void *
0x180033e09  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033e0e  mov     rax, rbx
0x180033e11  mov     rcx, [rbp+30h+var_18]
0x180033e15  xor     rcx, rsp; StackCookie
0x180033e18  call    __security_check_cookie
0x180033e1d  add     rsp, 120h
0x180033e24  pop     rdi
0x180033e25  pop     rbx
0x180033e26  pop     rbp
0x180033e27  retn
0x180033e28  mov     r9d, eax; char *
0x180033e2b  lea     r8, aCW1SSrcOrchest_6; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180033e32  mov     edx, 2Eh ; '.'; void *
0x180033e37  mov     rcx, r10; this
0x180033e3a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
