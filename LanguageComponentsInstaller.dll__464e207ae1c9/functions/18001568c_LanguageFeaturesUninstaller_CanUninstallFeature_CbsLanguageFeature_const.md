# LanguageFeaturesUninstaller::CanUninstallFeature(CbsLanguageFeature const &)

- ea: `0x18001568c`
- end: `0x1800157a8`
- name: `?CanUninstallFeature@LanguageFeaturesUninstaller@@AEBA_NAEBVCbsLanguageFeature@@@Z`
- size: `284`
- prototype: `char __fastcall(LanguageFeaturesUninstaller *this, const struct CbsLanguageFeature *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180010094`

## callees

- `0x180003520`
- `0x180005d68`
- `0x180006380`
- `0x18001568c`
- `0x1800180b4`
- `0x180023df0`

## pseudocode

```c
char __fastcall LanguageFeaturesUninstaller::CanUninstallFeature(
        LanguageFeaturesUninstaller *this,
        const struct CbsLanguageFeature *a2)
{
  int v2; // eax
  char v4; // dl
  int v5; // eax
  char v6; // cl
  const WCHAR *v7; // rdx
  wchar_t *v8; // rbx
  const wchar_t *v9; // rdx
  wchar_t *v10; // r8
  const wchar_t *v11; // rcx
  wchar_t *S2[4]; // [rsp+20h] [rbp-38h] BYREF

  v2 = *((_DWORD *)a2 + 17);
  v4 = *((_BYTE *)a2 + 80);
  v5 = v2 & 0x40;
  if ( v4 && (*((_BYTE *)a2 + 76) & 0x40) != 0 )
  {
    v6 = 1;
LABEL_5:
    if ( !v5 || !v6 )
      return 0;
    goto LABEL_7;
  }
  v6 = 0;
  if ( v4 )
    goto LABEL_5;
LABEL_7:
  if ( v5 )
  {
    v7 = *((_QWORD *)a2 + 22) <= 7u ? (const WCHAR *)((char *)a2 + 152) : (const WCHAR *)*((_QWORD *)a2 + 19);
    if ( (unsigned int)GetLanguagesClosenessScore(L"zxx", v7) != 100 )
    {
      if ( *((_DWORD *)a2 + 46) != 1 )
        return 1;
      std::wstring::wstring((__int64)S2, (__int64)a2 + 152);
      v8 = &S1;
      while ( 1 )
      {
        v9 = (const wchar_t *)S2;
        v10 = (wchar_t *)*((_QWORD *)v8 + 2);
        if ( S2[3] > (wchar_t *)7 )
          v9 = S2[0];
        v11 = *((_QWORD *)v8 + 3) <= 7u ? v8 : *(const wchar_t **)v8;
        if ( v10 == S2[2] && (!v10 || !wmemcmp(v11, v9, (size_t)v10)) )
          break;
        v8 += 16;
        if ( v8 == (wchar_t *)&dword_180037B20 )
        {
          std::wstring::~wstring((char **)S2);
          return 1;
        }
      }
      std::wstring::~wstring((char **)S2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001568c  mov     [rsp+arg_0], rbx
0x180015691  push    rdi
0x180015692  sub     rsp, 50h
0x180015696  mov     rax, cs:__security_cookie
0x18001569d  xor     rax, rsp
0x1800156a0  mov     [rsp+58h+var_18], rax
0x1800156a5  mov     eax, [rdx+44h]
0x1800156a8  mov     rdi, rdx
0x1800156ab  mov     dl, [rdx+50h]
0x1800156ae  and     eax, 40h
0x1800156b1  test    dl, dl
0x1800156b3  jz      short loc_1800156BF
0x1800156b5  test    byte ptr [rdi+4Ch], 40h
0x1800156b9  jz      short loc_1800156BF
0x1800156bb  mov     cl, 1
0x1800156bd  jmp     short loc_1800156C5
0x1800156bf  xor     cl, cl
0x1800156c1  test    dl, dl
0x1800156c3  jz      short loc_1800156E1
0x1800156c5  test    eax, eax
0x1800156c7  jnz     short loc_1800156D9
0x1800156c9  test    cl, cl
0x1800156cb  jnz     loc_18001578E
0x1800156d1  test    eax, eax
0x1800156d3  jz      loc_18001578E
0x1800156d9  test    cl, cl
0x1800156db  jz      loc_18001578E
0x1800156e1  test    eax, eax
0x1800156e3  jz      loc_18001578E
0x1800156e9  lea     rbx, [rdi+98h]
0x1800156f0  cmp     qword ptr [rbx+18h], 7
0x1800156f5  jbe     short loc_1800156FC
0x1800156f7  mov     rdx, [rbx]
0x1800156fa  jmp     short loc_1800156FF
0x1800156fc  mov     rdx, rbx; PCWSTR
0x1800156ff  mov     rcx, cs:off_18002B500; sourceString
0x180015706  call    ?GetLanguagesClosenessScore@@YAHQEBG0@Z; GetLanguagesClosenessScore(ushort const * const,ushort const * const)
0x18001570b  cmp     eax, 64h ; 'd'
0x18001570e  jz      short loc_18001578E
0x180015710  cmp     dword ptr [rdi+0B8h], 1
0x180015717  jnz     short loc_180015780
0x180015719  mov     rdx, rbx
0x18001571c  lea     rcx, [rsp+58h+S2]
0x180015721  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180015726  lea     rbx, S1
0x18001572d  cmp     [rsp+58h+var_20], 7
0x180015733  lea     rdx, [rsp+58h+S2]
0x180015738  mov     r8, [rbx+10h]; N
0x18001573c  cmova   rdx, [rsp+58h+S2]; S2
0x180015742  cmp     qword ptr [rbx+18h], 7
0x180015747  jbe     short loc_18001574E
0x180015749  mov     rcx, [rbx]
0x18001574c  jmp     short loc_180015751
0x18001574e  mov     rcx, rbx; S1
0x180015751  cmp     r8, [rsp+58h+var_28]
0x180015756  jnz     short loc_180015766
0x180015758  test    r8, r8
0x18001575b  jz      short loc_180015784
0x18001575d  call    wmemcmp
0x180015762  test    eax, eax
0x180015764  jz      short loc_180015784
0x180015766  add     rbx, 20h ; ' '
0x18001576a  lea     rax, dword_180037B20
0x180015771  cmp     rbx, rax
0x180015774  jnz     short loc_18001572D
0x180015776  lea     rcx, [rsp+58h+S2]; void *
0x18001577b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180015780  mov     al, 1
0x180015782  jmp     short loc_180015790
0x180015784  lea     rcx, [rsp+58h+S2]; void *
0x180015789  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001578e  xor     al, al
0x180015790  mov     rcx, [rsp+58h+var_18]
0x180015795  xor     rcx, rsp; StackCookie
0x180015798  call    __security_check_cookie
0x18001579d  mov     rbx, [rsp+58h+arg_0]
0x1800157a2  add     rsp, 50h
0x1800157a6  pop     rdi
0x1800157a7  retn
```
