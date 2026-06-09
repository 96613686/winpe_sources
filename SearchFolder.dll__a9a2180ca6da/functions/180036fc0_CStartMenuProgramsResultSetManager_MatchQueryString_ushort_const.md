# CStartMenuProgramsResultSetManager::_MatchQueryString(ushort const *)

- ea: `0x180036fc0`
- end: `0x1800370da`
- name: `?_MatchQueryString@CStartMenuProgramsResultSetManager@@AEAAKPEBG@Z`
- size: `282`
- prototype: `__int64 __fastcall(CStartMenuProgramsResultSetManager *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003489c`
- `0x180034dc8`

## callees

- `0x180021de4`
- `0x180036fc0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003700d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180037033`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003700d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180037033`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037095`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180037088`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x1800370c3`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x180037088`
- `api-ms-win-core-localization-l1-2-0!FindNLSString` at `0x1800370c3`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x180036fef`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x180037061`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x180036fef`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyboardLayout` at `0x180037061`

## pseudocode

```c
__int64 __fastcall CStartMenuProgramsResultSetManager::_MatchQueryString(
        CStartMenuProgramsResultSetManager *this,
        const unsigned __int16 *a2)
{
  int v2; // eax
  unsigned int NLSString; // edi
  const WCHAR *lpString2; // rbx
  unsigned __int16 KeyboardLayout; // ax
  int NLSStringFlags; // eax
  const WCHAR *v9; // rbx
  DWORD v10; // r15d
  unsigned __int16 v11; // ax

  v2 = *((_DWORD *)this + 36);
  if ( v2 )
  {
    NLSString = -1;
    if ( v2 == 2 )
    {
      lpString2 = (const WCHAR *)*((_QWORD *)this + 12);
      KeyboardLayout = (unsigned __int16)GetKeyboardLayout(0);
      if ( CompareStringW(KeyboardLayout, 1u, a2, -1, lpString2, -1) == 2
        || CompareStringW(0x400u, 1u, a2, -1, *((PCNZWCH *)this + 12), -1) == 2 )
      {
        return 0;
      }
    }
  }
  else
  {
    NLSStringFlags = GetNLSStringFlags(1);
    v9 = (const WCHAR *)*((_QWORD *)this + 12);
    v10 = NLSStringFlags | 0x100000;
    v11 = (unsigned __int16)GetKeyboardLayout(0);
    NLSString = FindNLSString(v11, v10, a2, -1, v9, -1, 0);
    if ( NLSString == -1 && GetLastError() )
      return (unsigned int)FindNLSString(0x800u, v10, a2, -1, *((LPCWSTR *)this + 12), -1, 0);
  }
  return NLSString;
}

```

## disassembly

```asm
0x180036fc0  push    rbx
0x180036fc2  push    rbp
0x180036fc3  push    rsi
0x180036fc4  push    rdi
0x180036fc5  push    r14
0x180036fc7  push    r15
0x180036fc9  sub     rsp, 48h
0x180036fcd  mov     eax, [rcx+90h]
0x180036fd3  mov     r14, rdx
0x180036fd6  mov     rbp, rcx
0x180036fd9  test    eax, eax
0x180036fdb  jz      short loc_180037049
0x180036fdd  or      edi, 0FFFFFFFFh
0x180036fe0  cmp     eax, 2
0x180036fe3  jnz     loc_1800370CB
0x180036fe9  mov     rbx, [rcx+60h]
0x180036fed  xor     ecx, ecx; idThread
0x180036fef  call    cs:__imp_GetKeyboardLayout
0x180036ff5  or      esi, 0FFFFFFFFh
0x180036ff8  movzx   ecx, ax; Locale
0x180036ffb  mov     [rsp+78h+cchCount2], esi; cchCount2
0x180036fff  mov     r8, r14; lpString1
0x180037002  mov     r9d, esi; cchCount1
0x180037005  mov     [rsp+78h+lpString2], rbx; lpString2
0x18003700a  lea     edx, [rsi+2]; dwCmpFlags
0x18003700d  call    cs:__imp_CompareStringW
0x180037013  cmp     eax, 2
0x180037016  jz      short loc_180037042
0x180037018  mov     rax, [rbp+60h]
0x18003701c  lea     edx, [rsi+2]; dwCmpFlags
0x18003701f  mov     [rsp+78h+cchCount2], esi; cchCount2
0x180037023  mov     r9d, esi; cchCount1
0x180037026  mov     r8, r14; lpString1
0x180037029  mov     [rsp+78h+lpString2], rax; lpString2
0x18003702e  mov     ecx, 400h; Locale
0x180037033  call    cs:__imp_CompareStringW
0x180037039  cmp     eax, 2
0x18003703c  jnz     loc_1800370CB
0x180037042  xor     edi, edi
0x180037044  jmp     loc_1800370CB
0x180037049  mov     ecx, 1
0x18003704e  call    GetNLSStringFlags
0x180037053  mov     rbx, [rbp+60h]
0x180037057  mov     r15d, eax
0x18003705a  xor     ecx, ecx; idThread
0x18003705c  bts     r15d, 14h
0x180037061  call    cs:__imp_GetKeyboardLayout
0x180037067  or      esi, 0FFFFFFFFh
0x18003706a  mov     [rsp+78h+pcchFound], 0; pcchFound
0x180037073  movzx   ecx, ax; Locale
0x180037076  mov     r9d, esi; cchSource
0x180037079  mov     [rsp+78h+cchCount2], esi; cchValue
0x18003707d  mov     r8, r14; lpStringSource
0x180037080  mov     edx, r15d; dwFindNLSStringFlags
0x180037083  mov     [rsp+78h+lpString2], rbx; lpStringValue
0x180037088  call    cs:__imp_FindNLSString
0x18003708e  mov     edi, eax
0x180037090  cmp     eax, 0FFFFFFFFh
0x180037093  jnz     short loc_1800370CB
0x180037095  call    cs:__imp_GetLastError
0x18003709b  test    eax, eax
0x18003709d  jz      short loc_1800370CB
0x18003709f  mov     rax, [rbp+60h]
0x1800370a3  mov     r9d, esi; cchSource
0x1800370a6  mov     [rsp+78h+pcchFound], 0; pcchFound
0x1800370af  mov     r8, r14; lpStringSource
0x1800370b2  mov     [rsp+78h+cchCount2], esi; cchValue
0x1800370b6  mov     edx, r15d; dwFindNLSStringFlags
0x1800370b9  mov     ecx, 800h; Locale
0x1800370be  mov     [rsp+78h+lpString2], rax; lpStringValue
0x1800370c3  call    cs:__imp_FindNLSString
0x1800370c9  mov     edi, eax
0x1800370cb  mov     eax, edi
0x1800370cd  add     rsp, 48h
0x1800370d1  pop     r15
0x1800370d3  pop     r14
0x1800370d5  pop     rdi
0x1800370d6  pop     rsi
0x1800370d7  pop     rbp
0x1800370d8  pop     rbx
0x1800370d9  retn
```
