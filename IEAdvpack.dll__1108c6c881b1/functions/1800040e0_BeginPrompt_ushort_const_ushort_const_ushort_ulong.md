# BeginPrompt(ushort const *,ushort const *,ushort *,ulong)

- ea: `0x1800040e0`
- end: `0x1800042c9`
- name: `?BeginPrompt@@YAHPEBG0PEAGK@Z`
- size: `489`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004880`

## callees

- `0x1800040e0`
- `0x180007454`
- `0x180008a6c`
- `0x18001b980`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800042a0`
- `KERNEL32!LocalFree` at `0x1800042a0`
- `KERNEL32!LocalAlloc` at `0x180004175`
- `KERNEL32!LocalAlloc` at `0x180004175`
- `KERNEL32!CompareStringW` at `0x18000423a`
- `KERNEL32!CompareStringW` at `0x18000423a`

## pseudocode

```c
__int64 __fastcall BeginPrompt(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int v5; // ebx
  unsigned __int16 *v6; // rsi
  int v7; // eax
  unsigned int v9[4]; // [rsp+30h] [rbp-338h] BYREF
  WCHAR String1[128]; // [rsp+40h] [rbp-328h] BYREF
  WCHAR AppName[256]; // [rsp+140h] [rbp-228h] BYREF

  if ( (int)GetTranslatedString(a1, a2, L"BeginPrompt", AppName, 0x100u, v9) >= 0 )
  {
    if ( (int)GetTranslatedString(a1, AppName, L"Title", a3, 0x100u, v9) >= 0 )
      pszTitleString = a3;
    v6 = (unsigned __int16 *)LocalAlloc(0x40u, 0x1000u);
    if ( v6 )
    {
      if ( (int)GetTranslatedString(a1, AppName, L"Prompt", v6, 0x800u, v9) >= 0 )
      {
        GetTranslatedString(a1, AppName, L"ButtonType", String1, 0x80u, v9);
        v7 = CompareStringW(0x7Fu, 1u, String1, -1, L"YESNO", -1);
        v5 = MsgBox2Param(hWnd, 0x3EAu, v6, 0, 0x20u, v7 != 2 ? 257 : 260);
        if ( !v5 )
        {
          MsgBox2Param(hWnd, 0x44Eu, 0, 0, 0x10u, 0);
          v5 = 2;
        }
      }
      else
      {
        v5 = 1;
      }
      LocalFree(v6);
      if ( v5 == 7 )
        return 2;
    }
    else
    {
      MsgBox2Param(hWnd, 0x44Eu, 0, 0, 0x10u, 0);
      return 2;
    }
  }
  else
  {
    return 1;
  }
  return v5;
}

```

## disassembly

```asm
0x1800040e0  push    rbx
0x1800040e2  push    rsi
0x1800040e3  push    rdi
0x1800040e4  sub     rsp, 350h
0x1800040eb  mov     rax, cs:__security_cookie
0x1800040f2  xor     rax, rsp
0x1800040f5  mov     [rsp+368h+var_28], rax
0x1800040fd  lea     rax, [rsp+368h+var_338]
0x180004102  mov     rdi, r8
0x180004105  mov     qword ptr [rsp+368h+cchCount2], rax; unsigned int *
0x18000410a  lea     r9, [rsp+368h+AppName]; unsigned __int16 *
0x180004112  mov     esi, 100h
0x180004117  lea     r8, aBeginprompt; "BeginPrompt"
0x18000411e  mov     dword ptr [rsp+368h+lpString2], esi; unsigned int
0x180004122  mov     rbx, rcx
0x180004125  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000412a  test    eax, eax
0x18000412c  jns     short loc_180004138
0x18000412e  mov     ebx, 1
0x180004133  jmp     loc_1800042AC
0x180004138  lea     rax, [rsp+368h+var_338]
0x18000413d  mov     r9, rdi; unsigned __int16 *
0x180004140  mov     qword ptr [rsp+368h+cchCount2], rax; unsigned int *
0x180004145  lea     r8, aTitle; "Title"
0x18000414c  lea     rdx, [rsp+368h+AppName]; lpAppName
0x180004154  mov     dword ptr [rsp+368h+lpString2], esi; unsigned int
0x180004158  mov     rcx, rbx; unsigned __int16 *
0x18000415b  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x180004160  test    eax, eax
0x180004162  js      short loc_18000416B
0x180004164  mov     cs:pszTitleString, rdi
0x18000416b  mov     edx, 1000h; uBytes
0x180004170  mov     ecx, 40h ; '@'; uFlags
0x180004175  call    cs:__imp_LocalAlloc
0x18000417b  mov     rsi, rax
0x18000417e  test    rax, rax
0x180004181  jnz     short loc_1800041AE
0x180004183  mov     rcx, cs:hWnd; hWnd
0x18000418a  xor     r9d, r9d; unsigned __int16 *
0x18000418d  mov     [rsp+368h+cchCount2], eax; unsigned int
0x180004191  xor     r8d, r8d; unsigned __int16 *
0x180004194  mov     edx, 44Eh; uID
0x180004199  mov     dword ptr [rsp+368h+lpString2], 10h; unsigned int
0x1800041a1  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x1800041a6  lea     ebx, [rsi+2]
0x1800041a9  jmp     loc_1800042AC
0x1800041ae  lea     rax, [rsp+368h+var_338]
0x1800041b3  mov     r9, rsi; unsigned __int16 *
0x1800041b6  mov     qword ptr [rsp+368h+cchCount2], rax; unsigned int *
0x1800041bb  lea     r8, aPrompt; "Prompt"
0x1800041c2  lea     rdx, [rsp+368h+AppName]; lpAppName
0x1800041ca  mov     dword ptr [rsp+368h+lpString2], 800h; unsigned int
0x1800041d2  mov     rcx, rbx; unsigned __int16 *
0x1800041d5  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x1800041da  mov     edi, 2
0x1800041df  test    eax, eax
0x1800041e1  jns     short loc_1800041EB
0x1800041e3  lea     ebx, [rdi-1]
0x1800041e6  jmp     loc_18000429D
0x1800041eb  lea     rax, [rsp+368h+var_338]
0x1800041f0  mov     rcx, rbx; unsigned __int16 *
0x1800041f3  mov     qword ptr [rsp+368h+cchCount2], rax; unsigned int *
0x1800041f8  lea     r9, [rsp+368h+String1]; unsigned __int16 *
0x1800041fd  lea     r8, aButtontype; "ButtonType"
0x180004204  mov     dword ptr [rsp+368h+lpString2], 80h; unsigned int
0x18000420c  lea     rdx, [rsp+368h+AppName]; lpAppName
0x180004214  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x180004219  or      r9d, 0FFFFFFFFh; cchCount1
0x18000421d  lea     rax, String2; "YESNO"
0x180004224  mov     [rsp+368h+cchCount2], r9d; cchCount2
0x180004229  lea     r8, [rsp+368h+String1]; lpString1
0x18000422e  mov     [rsp+368h+lpString2], rax; lpString2
0x180004233  lea     edx, [r9+2]; dwCmpFlags
0x180004237  lea     ecx, [rdx+7Eh]; Locale
0x18000423a  call    cs:__imp_CompareStringW
0x180004240  mov     r8, rsi; unsigned __int16 *
0x180004243  mov     edx, 3EAh; uID
0x180004248  sub     eax, edi
0x18000424a  neg     eax
0x18000424c  sbb     ecx, ecx
0x18000424e  xor     r9d, r9d; unsigned __int16 *
0x180004251  and     ecx, 0FFFFFFFDh
0x180004254  add     ecx, 104h
0x18000425a  mov     [rsp+368h+cchCount2], ecx; unsigned int
0x18000425e  mov     rcx, cs:hWnd; hWnd
0x180004265  mov     dword ptr [rsp+368h+lpString2], 20h ; ' '; unsigned int
0x18000426d  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x180004272  mov     ebx, eax
0x180004274  test    eax, eax
0x180004276  jnz     short loc_18000429D
0x180004278  mov     rcx, cs:hWnd; hWnd
0x18000427f  xor     r9d, r9d; unsigned __int16 *
0x180004282  mov     [rsp+368h+cchCount2], eax; unsigned int
0x180004286  xor     r8d, r8d; unsigned __int16 *
0x180004289  mov     edx, 44Eh; uID
0x18000428e  mov     dword ptr [rsp+368h+lpString2], 10h; unsigned int
0x180004296  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x18000429b  mov     ebx, edi
0x18000429d  mov     rcx, rsi; hMem
0x1800042a0  call    cs:__imp_LocalFree
0x1800042a6  cmp     ebx, 7
0x1800042a9  cmovz   ebx, edi
0x1800042ac  mov     eax, ebx
0x1800042ae  mov     rcx, [rsp+368h+var_28]
0x1800042b6  xor     rcx, rsp; StackCookie
0x1800042b9  call    __security_check_cookie
0x1800042be  add     rsp, 350h
0x1800042c5  pop     rdi
0x1800042c6  pop     rsi
0x1800042c7  pop     rbx
0x1800042c8  retn
```
