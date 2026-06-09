# SelectSetupEngine(ushort const *,ushort const *,ulong)

- ea: `0x18000a428`
- end: `0x18000a615`
- name: `?SelectSetupEngine@@YAHPEBG0K@Z`
- size: `493`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, __int16)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800088c4`

## callees

- `0x180006af8`
- `0x180006d24`
- `0x180007454`
- `0x180008a6c`
- `0x18000a428`
- `0x18001b980`
- `0x18001ba10`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18000a542`
- `KERNEL32!CompareStringW` at `0x18000a542`
- `KERNEL32!SearchPathW` at `0x18000a582`
- `KERNEL32!SearchPathW` at `0x18000a582`

## string_xrefs

- `0x18000a566`: `SETUPAPI.DLL`
- `0x18000a5c4`: `SETUPAPI.DLL`
- `0x18000a58f`: `UpdateINFEngine`

## pseudocode

```c
__int64 __fastcall SelectSetupEngine(const unsigned __int16 *a1, const unsigned __int16 *a2, __int16 a3)
{
  unsigned int v5; // ebx
  int v6; // esi
  unsigned __int16 *StringField; // rbp
  unsigned __int16 *v8; // rdi
  HWND v9; // rcx
  const unsigned __int16 *v10; // r8
  UINT v11; // edx
  unsigned __int16 *v13; // [rsp+30h] [rbp-1258h] BYREF
  LPWSTR FilePart; // [rsp+38h] [rbp-1250h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-1248h] BYREF
  unsigned __int16 v16[2048]; // [rsp+250h] [rbp-1038h] BYREF

  FilePart = 0;
  v5 = 1;
  if ( (a3 & 0x138) != 0 || ctx )
  {
    dword_1800257F8 = 0;
    v6 = 1;
    if ( ctx )
      return v5;
  }
  else
  {
    v6 = 0;
    dword_1800257F8 = 1;
  }
  if ( (int)GetTranslatedString(a1, a2, L"RequiredEngine", v16, 0x800u, 0) >= 0 )
  {
    v13 = v16;
    StringField = GetStringField(&v13, L",", 34, 1);
    v8 = GetStringField(&v13, L",", 34, 1);
    if ( StringField )
    {
      if ( *StringField )
      {
        if ( v6 || CompareStringW(0x7Fu, 1u, StringField, -1, L"SETUPX", -1) != 2 )
        {
          dword_1800257F8 = 0;
          if ( SearchPathW(0, L"SETUPAPI.DLL", 0, 0x104u, Buffer, &FilePart) )
            return v5;
        }
        else
        {
          dword_1800257F8 = 1;
        }
        if ( !(unsigned int)GetTranslatedInt(a1, a2, L"UpdateINFEngine", 0) )
        {
          v5 = 0;
          if ( v8 && *v8 )
          {
            v9 = hWnd;
            v10 = v8;
            v11 = 1002;
          }
          else
          {
            v10 = L"SETUPAPI.DLL";
            v11 = 1109;
            v9 = 0;
          }
          MsgBox2Param(v9, v11, v10, 0, 0x10u, 0);
        }
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000a428  mov     [rsp+arg_10], rbx
0x18000a42d  mov     [rsp+arg_18], rbp
0x18000a432  push    rsi
0x18000a433  push    rdi
0x18000a434  push    r12
0x18000a436  push    r14
0x18000a438  push    r15
0x18000a43a  mov     eax, 1260h
0x18000a43f  call    _alloca_probe
0x18000a444  sub     rsp, rax
0x18000a447  mov     rax, cs:__security_cookie
0x18000a44e  xor     rax, rsp
0x18000a451  mov     [rsp+1288h+var_38], rax
0x18000a459  movzx   eax, cs:?ctx@@3UADVCONTEXTW@@A; ADVCONTEXTW ctx
0x18000a460  xor     r12d, r12d
0x18000a463  mov     [rsp+1288h+FilePart], r12
0x18000a468  mov     r15, rdx
0x18000a46b  mov     r14, rcx
0x18000a46e  mov     ebx, 1
0x18000a473  test    r8d, 138h
0x18000a47a  jnz     short loc_18000A48C
0x18000a47c  test    ax, ax
0x18000a47f  jnz     short loc_18000A48C
0x18000a481  mov     esi, r12d
0x18000a484  mov     cs:dword_1800257F8, ebx
0x18000a48a  jmp     short loc_18000A49E
0x18000a48c  mov     cs:dword_1800257F8, r12d
0x18000a493  mov     esi, ebx
0x18000a495  test    ax, ax
0x18000a498  jnz     loc_18000A5E7
0x18000a49e  mov     qword ptr [rsp+1288h+cchCount2], r12; unsigned int *
0x18000a4a3  lea     r9, [rsp+1288h+var_1038]; unsigned __int16 *
0x18000a4ab  lea     r8, aRequiredengine; "RequiredEngine"
0x18000a4b2  mov     dword ptr [rsp+1288h+lpString2], 800h; unsigned int
0x18000a4ba  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000a4bf  test    eax, eax
0x18000a4c1  js      loc_18000A5E7
0x18000a4c7  lea     rax, [rsp+1288h+var_1038]
0x18000a4cf  mov     edi, 22h ; '"'
0x18000a4d4  mov     r8d, edi; unsigned __int16
0x18000a4d7  mov     [rsp+1288h+var_1258], rax
0x18000a4dc  mov     r9d, ebx; int
0x18000a4df  lea     rdx, asc_18001E134; ","
0x18000a4e6  lea     rcx, [rsp+1288h+var_1258]; unsigned __int16 **
0x18000a4eb  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x18000a4f0  mov     r8d, edi; unsigned __int16
0x18000a4f3  lea     rdx, asc_18001E134; ","
0x18000a4fa  mov     r9d, ebx; int
0x18000a4fd  lea     rcx, [rsp+1288h+var_1258]; unsigned __int16 **
0x18000a502  mov     rbp, rax
0x18000a505  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x18000a50a  mov     rdi, rax
0x18000a50d  test    rbp, rbp
0x18000a510  jz      loc_18000A5E7
0x18000a516  cmp     [rbp+0], r12w
0x18000a51b  jz      loc_18000A5E7
0x18000a521  test    esi, esi
0x18000a523  jnz     short loc_18000A555
0x18000a525  or      r9d, 0FFFFFFFFh; cchCount1
0x18000a529  lea     rax, aSetupx; "SETUPX"
0x18000a530  mov     [rsp+1288h+cchCount2], r9d; cchCount2
0x18000a535  lea     ecx, [rsi+7Fh]; Locale
0x18000a538  mov     r8, rbp; lpString1
0x18000a53b  mov     [rsp+1288h+lpString2], rax; lpString2
0x18000a540  mov     edx, ebx; dwCmpFlags
0x18000a542  call    cs:__imp_CompareStringW
0x18000a548  cmp     eax, 2
0x18000a54b  jnz     short loc_18000A555
0x18000a54d  mov     cs:dword_1800257F8, ebx
0x18000a553  jmp     short loc_18000A58C
0x18000a555  lea     rax, [rsp+1288h+FilePart]
0x18000a55a  mov     cs:dword_1800257F8, r12d
0x18000a561  mov     qword ptr [rsp+1288h+cchCount2], rax; lpFilePart
0x18000a566  lea     rdx, FileName; "SETUPAPI.DLL"
0x18000a56d  lea     rax, [rsp+1288h+Buffer]
0x18000a572  mov     r9d, 104h; nBufferLength
0x18000a578  xor     r8d, r8d; lpExtension
0x18000a57b  mov     [rsp+1288h+lpString2], rax; lpBuffer
0x18000a580  xor     ecx, ecx; lpPath
0x18000a582  call    cs:__imp_SearchPathW
0x18000a588  test    eax, eax
0x18000a58a  jnz     short loc_18000A5E7
0x18000a58c  xor     r9d, r9d; nDefault
0x18000a58f  lea     r8, aUpdateinfengin; "UpdateINFEngine"
0x18000a596  mov     rdx, r15; Section
0x18000a599  mov     rcx, r14; unsigned __int16 *
0x18000a59c  call    ?GetTranslatedInt@@YAKPEBG00K@Z; GetTranslatedInt(ushort const *,ushort const *,ushort const *,ulong)
0x18000a5a1  test    eax, eax
0x18000a5a3  jnz     short loc_18000A5E7
0x18000a5a5  mov     ebx, r12d
0x18000a5a8  test    rdi, rdi
0x18000a5ab  jz      short loc_18000A5C4
0x18000a5ad  cmp     [rdi], r12w
0x18000a5b1  jz      short loc_18000A5C4
0x18000a5b3  mov     rcx, cs:hWnd
0x18000a5ba  mov     r8, rdi
0x18000a5bd  mov     edx, 3EAh
0x18000a5c2  jmp     short loc_18000A5D2
0x18000a5c4  lea     r8, FileName; "SETUPAPI.DLL"
0x18000a5cb  mov     edx, 455h; uID
0x18000a5d0  xor     ecx, ecx; hWnd
0x18000a5d2  mov     [rsp+1288h+cchCount2], r12d; unsigned int
0x18000a5d7  xor     r9d, r9d; unsigned __int16 *
0x18000a5da  mov     dword ptr [rsp+1288h+lpString2], 10h; unsigned int
0x18000a5e2  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x18000a5e7  mov     eax, ebx
0x18000a5e9  mov     rcx, [rsp+1288h+var_38]
0x18000a5f1  xor     rcx, rsp; StackCookie
0x18000a5f4  call    __security_check_cookie
0x18000a5f9  lea     r11, [rsp+1288h+var_28]
0x18000a601  mov     rbx, [r11+40h]
0x18000a605  mov     rbp, [r11+48h]
0x18000a609  mov     rsp, r11
0x18000a60c  pop     r15
0x18000a60e  pop     r14
0x18000a610  pop     r12
0x18000a612  pop     rdi
0x18000a613  pop     rsi
0x18000a614  retn
```
