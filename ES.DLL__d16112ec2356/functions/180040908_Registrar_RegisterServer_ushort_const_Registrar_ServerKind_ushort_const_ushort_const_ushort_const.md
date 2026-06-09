# Registrar::RegisterServer(ushort const *,Registrar::ServerKind,ushort const *,ushort const *,ushort const *)

- ea: `0x180040908`
- end: `0x180040a4d`
- name: `?RegisterServer@Registrar@@QEAAJPEBGW4ServerKind@1@000@Z`
- size: `325`
- prototype: `int __high(const unsigned __int16 *, enum Registrar::ServerKind, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180035930`

## callees

- `0x180006194`
- `0x1800404ec`
- `0x18004050c`
- `0x1800405dc`
- `0x180040628`
- `0x180040908`
- `0x180043510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180040969`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180040969`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040a22`

## string_xrefs

- `0x1800409d7`: `DllSurrogate`

## pseudocode

```c
__int64 __fastcall Registrar::RegisterServer(
        _DWORD *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int16 *a4)
{
  bool v4; // zf
  const IID *v9; // rcx
  HRESULT v10; // ebx
  __int64 v11; // rdx
  const unsigned __int16 *v12; // r14
  int i; // esi
  int v14; // eax
  HKEY v15; // [rsp+20h] [rbp-79h] BYREF
  LPOLESTR lpsz; // [rsp+28h] [rbp-71h] BYREF
  unsigned __int16 v17[64]; // [rsp+30h] [rbp-69h] BYREF

  v4 = a1[2] == 0;
  lpsz = 0;
  if ( v4 )
    return 2147500037LL;
  v9 = *(const IID **)(*(_QWORD *)a1 + 8LL);
  if ( v9 )
  {
    v10 = StringFromCLSID(v9, &lpsz);
    if ( v10 >= 0 )
    {
      v10 = StringCchPrintfW(v17, 0x3Fu, L"Software\\Classes\\AppID\\%s", lpsz);
      if ( v10 >= 0 )
      {
        v15 = 0;
        v10 = CreateKey(HKEY_LOCAL_MACHINE, v17, a4, &v15);
        if ( v10 >= 0 )
        {
          CreateNamedValue(v15, L"DllSurrogate", &sz);
          AutoCloseHKEY::~AutoCloseHKEY((AutoCloseHKEY *)&v15);
          v12 = lpsz;
          v10 = 0;
          for ( i = 0; i < a1[2]; ++i )
          {
            v14 = Registrar::RegisterComClass(*(_QWORD *)a1 + 48LL * i, v11, a2, v12);
            if ( v14 < 0 )
              v10 = v14;
          }
        }
        else
        {
          AutoCloseHKEY::~AutoCloseHKEY((AutoCloseHKEY *)&v15);
        }
      }
    }
  }
  else
  {
    v10 = -2147418113;
  }
  CoTaskMemFree(lpsz);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180040908  mov     [rsp-8+arg_10], rbx
0x18004090d  push    rbp
0x18004090e  push    rsi
0x18004090f  push    rdi
0x180040910  push    r14
0x180040912  push    r15
0x180040914  lea     rbp, [rsp-27h]
0x180040919  sub     rsp, 0C0h
0x180040920  mov     rax, cs:__security_cookie
0x180040927  xor     rax, rsp
0x18004092a  mov     [rbp+47h+var_30], rax
0x18004092e  cmp     dword ptr [rcx+8], 0
0x180040932  mov     rsi, r9
0x180040935  mov     r15, rdx
0x180040938  mov     [rbp+47h+lpsz], 0
0x180040940  mov     rdi, rcx
0x180040943  jnz     short loc_18004094F
0x180040945  mov     eax, 80004005h
0x18004094a  jmp     loc_180040A2A
0x18004094f  mov     rax, [rcx]
0x180040952  mov     rcx, [rax+8]; rclsid
0x180040956  test    rcx, rcx
0x180040959  jnz     short loc_180040965
0x18004095b  mov     ebx, 8000FFFFh
0x180040960  jmp     loc_180040A1E
0x180040965  lea     rdx, [rbp+47h+lpsz]; lplpsz
0x180040969  call    cs:__imp_StringFromCLSID
0x18004096f  mov     ebx, eax
0x180040971  test    eax, eax
0x180040973  js      loc_180040A1E
0x180040979  mov     r9, [rbp+47h+lpsz]
0x18004097d  lea     r8, aSoftwareClasse; "Software\\Classes\\AppID\\%s"
0x180040984  mov     edx, 3Fh ; '?'; unsigned __int64
0x180040989  lea     rcx, [rbp+47h+var_B0]; unsigned __int16 *
0x18004098d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180040992  mov     ebx, eax
0x180040994  test    eax, eax
0x180040996  js      loc_180040A1E
0x18004099c  lea     r9, [rbp+47h+var_C0]; HKEY *
0x1800409a0  mov     [rbp+47h+var_C0], 0
0x1800409a8  mov     r8, rsi; unsigned __int16 *
0x1800409ab  lea     rdx, [rbp+47h+var_B0]; unsigned __int16 *
0x1800409af  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800409b6  call    ?CreateKey@@YAJPEAUHKEY__@@PEBG1PEAPEAU1@@Z; CreateKey(HKEY__ *,ushort const *,ushort const *,HKEY__ * *)
0x1800409bb  mov     ebx, eax
0x1800409bd  test    eax, eax
0x1800409bf  jns     short loc_1800409CC
0x1800409c1  lea     rcx, [rbp+47h+var_C0]; this
0x1800409c5  call    ??1AutoCloseHKEY@@QEAA@XZ; AutoCloseHKEY::~AutoCloseHKEY(void)
0x1800409ca  jmp     short loc_180040A1E
0x1800409cc  mov     rcx, [rbp+47h+var_C0]; HKEY
0x1800409d0  lea     r8, sz; unsigned __int16 *
0x1800409d7  lea     rdx, aDllsurrogate; "DllSurrogate"
0x1800409de  call    ?CreateNamedValue@@YAJPEAUHKEY__@@PEBG1@Z; CreateNamedValue(HKEY__ *,ushort const *,ushort const *)
0x1800409e3  lea     rcx, [rbp+47h+var_C0]; this
0x1800409e7  call    ??1AutoCloseHKEY@@QEAA@XZ; AutoCloseHKEY::~AutoCloseHKEY(void)
0x1800409ec  mov     r14, [rbp+47h+lpsz]
0x1800409f0  xor     ebx, ebx
0x1800409f2  xor     esi, esi
0x1800409f4  cmp     [rdi+8], ebx
0x1800409f7  jle     short loc_180040A1E
0x1800409f9  movsxd  rax, esi
0x1800409fc  mov     r9, r14
0x1800409ff  mov     r8, r15
0x180040a02  lea     rcx, [rax+rax*2]
0x180040a06  shl     rcx, 4
0x180040a0a  add     rcx, [rdi]
0x180040a0d  call    ?RegisterComClass@Registrar@@CAJAEBUClassInfo@1@W4ServerKind@1@PEBG2@Z; Registrar::RegisterComClass(Registrar::ClassInfo const &,Registrar::ServerKind,ushort const *,ushort const *)
0x180040a12  test    eax, eax
0x180040a14  cmovs   ebx, eax
0x180040a17  inc     esi
0x180040a19  cmp     esi, [rdi+8]
0x180040a1c  jl      short loc_1800409F9
0x180040a1e  mov     rcx, [rbp+47h+lpsz]; pv
0x180040a22  call    cs:__imp_CoTaskMemFree
0x180040a28  mov     eax, ebx
0x180040a2a  mov     rcx, [rbp+47h+var_30]
0x180040a2e  xor     rcx, rsp; StackCookie
0x180040a31  call    __security_check_cookie
0x180040a36  mov     rbx, [rsp+0E0h+arg_10]
0x180040a3e  add     rsp, 0C0h
0x180040a45  pop     r15
0x180040a47  pop     r14
0x180040a49  pop     rdi
0x180040a4a  pop     rsi
0x180040a4b  pop     rbp
0x180040a4c  retn
```
