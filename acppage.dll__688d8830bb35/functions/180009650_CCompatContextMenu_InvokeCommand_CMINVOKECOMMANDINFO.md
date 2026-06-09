# CCompatContextMenu::InvokeCommand(_CMINVOKECOMMANDINFO *)

- ea: `0x180009650`
- end: `0x1800096d8`
- name: `?InvokeCommand@CCompatContextMenu@@UEAAJPEAU_CMINVOKECOMMANDINFO@@@Z`
- size: `136`
- prototype: `__int64 __fastcall(const WCHAR *this, struct _CMINVOKECOMMANDINFO *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009650`
- `0x18000c8e4`

## import_xrefs

- `KERNEL32!lstrcmpiA` at `0x1800096a8`
- `KERNEL32!lstrcmpiA` at `0x1800096a8`
- `SHLWAPI!StrCmpIW` at `0x18000968b`
- `SHLWAPI!StrCmpIW` at `0x18000968b`

## pseudocode

```c
__int64 __fastcall CCompatContextMenu::InvokeCommand(const WCHAR *this, struct _CMINVOKECOMMANDINFO *a2)
{
  int v3; // edi
  int v4; // eax
  bool v5; // zf

  v3 = -2147467259;
  if ( a2->cbSize != 104 || (a2->fMask & 0x4000) == 0 )
  {
    if ( WORD1(a2->lpVerb) )
    {
      v4 = lstrcmpiA(a2->lpVerb, "Troubleshoot");
      goto LABEL_5;
    }
LABEL_8:
    v5 = LOWORD(a2->lpVerb) == 0;
    goto LABEL_9;
  }
  if ( !WORD1(a2[1].hwnd) )
    goto LABEL_8;
  v4 = StrCmpIW((PCWSTR)a2[1].hwnd, L"Troubleshoot");
LABEL_5:
  v5 = v4 == 0;
LABEL_9:
  if ( v5 )
  {
    v3 = InvokeProgramCompatibilityWizard(this + 36, (int)a2);
    if ( v3 >= 0 )
      return 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180009650  mov     [rsp+arg_0], rbx
0x180009655  mov     [rsp+arg_8], rsi
0x18000965a  push    rdi
0x18000965b  sub     rsp, 20h
0x18000965f  cmp     dword ptr [rdx], 68h ; 'h'
0x180009662  mov     rax, rdx
0x180009665  mov     rsi, rcx
0x180009668  mov     edi, 80004005h
0x18000966d  jnz     short loc_180009695
0x18000966f  test    dword ptr [rdx+4], 4000h
0x180009676  jz      short loc_180009695
0x180009678  xor     ebx, ebx
0x18000967a  cmp     [rdx+42h], bx
0x18000967e  jz      short loc_1800096B0
0x180009680  mov     rcx, [rax+40h]; psz1
0x180009684  lea     rdx, psz2; "Troubleshoot"
0x18000968b  call    cs:__imp_StrCmpIW
0x180009691  test    eax, eax
0x180009693  jmp     short loc_1800096B4
0x180009695  xor     ebx, ebx
0x180009697  cmp     [rdx+12h], bx
0x18000969b  jz      short loc_1800096B0
0x18000969d  mov     rcx, [rax+10h]; lpString1
0x1800096a1  lea     rdx, String2; "Troubleshoot"
0x1800096a8  call    cs:__imp_lstrcmpiA
0x1800096ae  jmp     short loc_180009691
0x1800096b0  cmp     [rdx+10h], bx
0x1800096b4  jnz     short loc_1800096C6
0x1800096b6  lea     rcx, [rsi+48h]; pszUrl
0x1800096ba  call    ?InvokeProgramCompatibilityWizard@@YAJPEBGH@Z; InvokeProgramCompatibilityWizard(ushort const *,int)
0x1800096bf  test    eax, eax
0x1800096c1  mov     edi, eax
0x1800096c3  cmovns  edi, ebx
0x1800096c6  mov     rbx, [rsp+28h+arg_0]
0x1800096cb  mov     eax, edi
0x1800096cd  mov     rsi, [rsp+28h+arg_8]
0x1800096d2  add     rsp, 20h
0x1800096d6  pop     rdi
0x1800096d7  retn
```
