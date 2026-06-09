# Windows::Registry::GetSystemValue(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x180023440`
- end: `0x180023568`
- name: `?GetSystemValue@Registry@Windows@@UEAA?AV?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$basic_zstring_view@_W@wil@@00@Z`
- size: `296`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180009380`
- `0x180023440`
- `0x180033b00`
- `0x1800343b4`
- `0x180034a30`
- `0x18003ba50`
- `0x180056500`

## string_xrefs

- `0x180023556`: `C:\__w\1\s\src\orchestrator\system\Windows\Registry.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Registry::GetSystemValue(__int64 a1, __int64 a2, __int128 *a3, _OWORD *a4, __int128 *a5)
{
  char v6; // cl
  char v7; // dl
  int v9; // [rsp+20h] [rbp-41h]
  __int128 v10; // [rsp+40h] [rbp-21h] BYREF
  int v11[4]; // [rsp+50h] [rbp-11h] BYREF
  __int128 v12; // [rsp+60h] [rbp-1h] BYREF
  char *v13; // [rsp+70h] [rbp+Fh] BYREF
  _QWORD v14[4]; // [rsp+78h] [rbp+17h] BYREF
  char v15; // [rsp+98h] [rbp+37h]
  char v16; // [rsp+A0h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]

  v10 = *a5;
  *(_OWORD *)v11 = *a4;
  v12 = *a3;
  Windows::Registry::GetValue(a1, (__int64)&v13, (__int64)a3, &v12, v11, (const WCHAR **)&v10);
  if ( (int)v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\Windows\\Registry.hpp",
      (const char *)(unsigned int)v13,
      v9);
  v6 = v16;
  if ( !v16 )
    std::_Throw_bad_optional_access();
  *(_BYTE *)(a2 + 32) = -1;
  v7 = v15;
  if ( v15 != -1 )
  {
    if ( v15 )
    {
      if ( v15 == 1 )
      {
        *(_QWORD *)a2 = v14[0];
        *(_BYTE *)(a2 + 32) = 1;
      }
      else
      {
        std::wstring::wstring(a2, v14);
        *(_BYTE *)(a2 + 32) = 2;
        v6 = v16;
        v7 = v15;
      }
    }
    else
    {
      *(_DWORD *)a2 = v14[0];
      *(_BYTE *)(a2 + 32) = 0;
    }
  }
  if ( v6 && v7 != -1 && v7 && v7 != 1 )
    std::wstring::~wstring(v14);
  return a2;
}

```

## disassembly

```asm
0x180023440  mov     [rsp-8+arg_0], rbx
0x180023445  push    rbp
0x180023446  lea     rbp, [rsp-4Fh]
0x18002344b  sub     rsp, 0B0h
0x180023452  mov     rax, cs:__security_cookie
0x180023459  xor     rax, rsp
0x18002345c  mov     [rbp+4Fh+var_8], rax
0x180023460  mov     rbx, rdx
0x180023463  mov     [rbp+4Fh+var_78], rdx
0x180023467  mov     rax, [rbp+4Fh+arg_20]
0x18002346b  movups  xmm0, xmmword ptr [rax]
0x18002346e  movdqu  [rbp+4Fh+var_70], xmm0
0x180023473  movups  xmm1, xmmword ptr [r9]
0x180023477  movdqu  xmmword ptr [rbp+4Fh+var_60], xmm1
0x18002347c  movups  xmm0, xmmword ptr [r8]
0x180023480  movdqu  [rbp+4Fh+var_50], xmm0
0x180023485  lea     rax, [rbp+4Fh+var_70]
0x180023489  mov     [rsp+0B0h+var_88], rax
0x18002348e  lea     rax, [rbp+4Fh+var_60]
0x180023492  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x180023497  lea     r9, [rbp+4Fh+var_50]
0x18002349b  lea     rdx, [rbp+4Fh+var_40]
0x18002349f  call    ?GetValue@Registry@Windows@@QEAA?AU?$pair@JV?$optional@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@11@Z; Windows::Registry::GetValue(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x1800234a4  nop
0x1800234a5  mov     rcx, [rbp+57h]; this
0x1800234a9  mov     r9d, dword ptr [rbp+4Fh+var_40]; char *
0x1800234ad  test    r9d, r9d
0x1800234b0  js      loc_180023556
0x1800234b6  mov     cl, [rbp+4Fh+var_10]
0x1800234b9  test    cl, cl
0x1800234bb  jz      loc_180023550
0x1800234c1  mov     byte ptr [rbx+20h], 0FFh
0x1800234c5  movsx   rdx, [rbp+4Fh+var_18]
0x1800234ca  mov     rax, rdx
0x1800234cd  add     rax, 1
0x1800234d1  jz      short loc_18002350D
0x1800234d3  sub     rax, 1
0x1800234d7  jz      short loc_180023504
0x1800234d9  cmp     rax, 1
0x1800234dd  jz      short loc_1800234F7
0x1800234df  lea     rdx, [rbp+4Fh+var_38]
0x1800234e3  mov     rcx, rbx
0x1800234e6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800234eb  mov     byte ptr [rbx+20h], 2
0x1800234ef  mov     cl, [rbp+4Fh+var_10]
0x1800234f2  mov     dl, [rbp+4Fh+var_18]
0x1800234f5  jmp     short loc_18002350D
0x1800234f7  mov     rax, [rbp+4Fh+var_38]
0x1800234fb  mov     [rbx], rax
0x1800234fe  mov     byte ptr [rbx+20h], 1
0x180023502  jmp     short loc_18002350D
0x180023504  mov     eax, dword ptr [rbp+4Fh+var_38]
0x180023507  mov     [rbx], eax
0x180023509  mov     byte ptr [rbx+20h], 0
0x18002350d  test    cl, cl
0x18002350f  jz      short loc_180023530
0x180023511  movsx   rax, dl
0x180023515  add     rax, 1
0x180023519  jz      short loc_180023530
0x18002351b  sub     rax, 1
0x18002351f  jz      short loc_180023530
0x180023521  cmp     rax, 1
0x180023525  jz      short loc_180023530
0x180023527  lea     rcx, [rbp+4Fh+var_38]; void *
0x18002352b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023530  mov     rax, rbx
0x180023533  mov     rcx, [rbp+4Fh+var_8]
0x180023537  xor     rcx, rsp; StackCookie
0x18002353a  call    __security_check_cookie
0x18002353f  mov     rbx, [rsp+0B0h+arg_0]
0x180023547  add     rsp, 0B0h
0x18002354e  pop     rbp
0x18002354f  retn
0x180023550  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x180023556  lea     r8, aCW1SSrcOrchest_6; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18002355d  mov     edx, 24h ; '$'; void *
0x180023562  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
