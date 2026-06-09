# CAddressEditBox::_NavigationComplete(ushort const *,int,int)

- ea: `0x1801557c8`
- end: `0x180155a4b`
- name: `?_NavigationComplete@CAddressEditBox@@IEAAJPEBGHH@Z`
- size: `643`
- prototype: `__int64 __fastcall(CAddressEditBox *__hidden this, PCWSTR psz2, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180109704`
- `0x180155ef0`

## callees

- `0x180024f1c`
- `0x180039680`
- `0x1800873cc`
- `0x1800b5990`
- `0x1800e5a00`
- `0x180154f8c`
- `0x1801557c8`
- `0x180210010`

## import_xrefs

- `SHLWAPI!StrCmpW` at `0x1801558f8`
- `SHLWAPI!StrCmpW` at `0x1801558f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801559ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801559ce`
- `USER32!SendMessageW` at `0x180155835`
- `USER32!SendMessageW` at `0x180155863`
- `USER32!SendMessageW` at `0x18015587d`
- `USER32!SendMessageW` at `0x1801558c7`
- `USER32!SendMessageW` at `0x1801558dc`
- `USER32!SendMessageW` at `0x1801559f1`
- `USER32!SendMessageW` at `0x180155a07`
- `USER32!SendMessageW` at `0x180155835`
- `USER32!SendMessageW` at `0x180155863`
- `USER32!SendMessageW` at `0x18015587d`
- `USER32!SendMessageW` at `0x1801558c7`
- `USER32!SendMessageW` at `0x1801558dc`
- `USER32!SendMessageW` at `0x1801559f1`
- `USER32!SendMessageW` at `0x180155a07`
- `USER32!SetWindowTextW` at `0x1801559c4`
- `USER32!SetWindowTextW` at `0x1801559c4`
- `USER32!LockWindowUpdate` at `0x18015583f`
- `USER32!LockWindowUpdate` at `0x180155a0f`
- `USER32!LockWindowUpdate` at `0x18015583f`
- `USER32!LockWindowUpdate` at `0x180155a0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAddressEditBox::_NavigationComplete(HWND *this, PCWSTR psz2, int a3)
{
  int v6; // ebx
  HWND v7; // rcx
  HWND v8; // rcx
  const WCHAR *v9; // rcx
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rcx
  HWND v11; // rdx
  __int64 v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // r14d
  __int64 v15; // rbx
  __int64 v17; // [rsp+20h] [rbp-10h] BYREF
  LPCWSTR lpString; // [rsp+28h] [rbp-8h] BYREF
  WPARAM wParam; // [rsp+60h] [rbp+30h] BYREF
  LPARAM lParam; // [rsp+78h] [rbp+48h] BYREF

  v6 = 0;
  lpString = 0;
  LODWORD(lParam) = 0;
  LODWORD(wParam) = 0;
  if ( !(unsigned int)CAddressEditBox::_CanStompCurrentText((CAddressEditBox *)this) )
  {
    LODWORD(v17) = 0;
    if ( (*((int (__fastcall **)(char *, LPCWSTR *, __int64 *))this[8] + 3))((char *)this + 64, &lpString, &v17) >= 0 )
    {
      SendMessageW(this[13], 0xB0u, (WPARAM)&wParam, (LPARAM)&lParam);
      LockWindowUpdate(this[12]);
    }
  }
  v7 = this[12];
  if ( v7 )
  {
    if ( this[13] && (unsigned int)SendMessageW(v7, 0x157u, 0, 0) )
      SendMessageW(this[13], 0x100u, 0x1Bu, 0);
    if ( a3 )
    {
      v8 = this[30];
      if ( v8 )
      {
        v6 = (*(__int64 (__fastcall **)(HWND, HWND))(*(_QWORD *)v8 + 48LL))(v8, this[33]);
        if ( v6 >= 0 && !(unsigned int)CAddressEditBox::_IsDirty((CAddressEditBox *)this) )
        {
          SendMessageW(this[13], 0xB1u, 0, 0);
          SendMessageW(this[13], 0xB7u, 0, 0);
        }
      }
      else
      {
        v6 = -2147467259;
      }
    }
    v9 = (const WCHAR *)this[26];
    if ( !v9 || StrCmpW(v9, psz2) )
    {
      if ( this[24] )
      {
        if ( v6 >= 0 )
        {
          if ( this[32]
            || (v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))this[31]) == 0
            || (v6 = (**v10)(v10, &GUID_1011fa30_69da_11d2_8599_006097df8c11, this + 32), v6 >= 0) )
          {
            v11 = this[24];
            v12 = -1;
            do
              ++v12;
            while ( *((_WORD *)v11 + v12) );
            v13 = v12 + 1;
            v14 = 2084;
            if ( v13 > 0x824 )
              v14 = v13;
            wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &v17,
              v11,
              v14);
            v15 = v17;
            if ( v17 )
            {
              SHCleanupUrlForDisplay(v17, v14);
              v6 = (*(__int64 (__fastcall **)(HWND, __int64))(*(_QWORD *)this[32] + 24LL))(this[32], v15);
            }
            else
            {
              v6 = -2147024882;
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v17);
          }
        }
      }
    }
  }
  if ( lpString )
  {
    SetWindowTextW(this[13], lpString);
    CoTaskMemFree((LPVOID)lpString);
    if ( (_DWORD)wParam || (_DWORD)lParam )
    {
      SendMessageW(this[13], 0xB1u, (unsigned int)wParam, (unsigned int)lParam);
      SendMessageW(this[13], 0xB9u, 1u, 0);
    }
    LockWindowUpdate(0);
  }
  *((_DWORD *)this + 93) = 0;
  Str_SetPtrPrivateW(this + 24, 0);
  Str_SetPtrPrivateW(this + 26, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1801557c8  mov     [rsp-28h+arg_8], rbx
0x1801557cd  mov     dword ptr [rsp-28h+lParam], r9d
0x1801557d2  push    rbp
0x1801557d3  push    rsi
0x1801557d4  push    rdi
0x1801557d5  push    r14
0x1801557d7  push    r15
0x1801557d9  mov     rbp, rsp
0x1801557dc  sub     rsp, 30h
0x1801557e0  mov     esi, r8d
0x1801557e3  mov     r14, rdx
0x1801557e6  mov     rdi, rcx
0x1801557e9  xor     r15d, r15d
0x1801557ec  mov     ebx, r15d
0x1801557ef  mov     [rbp+lpString], r15
0x1801557f3  mov     dword ptr [rbp+lParam], r15d
0x1801557f7  mov     dword ptr [rbp+wParam], r15d
0x1801557fb  call    ?_CanStompCurrentText@CAddressEditBox@@IEAAHXZ; CAddressEditBox::_CanStompCurrentText(void)
0x180155800  test    eax, eax
0x180155802  jnz     short loc_180155845
0x180155804  mov     dword ptr [rbp+var_10], r15d
0x180155808  lea     rcx, [rdi+40h]
0x18015580c  mov     rax, [rcx]
0x18015580f  lea     r8, [rbp+var_10]
0x180155813  lea     rdx, [rbp+lpString]
0x180155817  mov     rax, [rax+18h]
0x18015581b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155820  test    eax, eax
0x180155822  js      short loc_180155845
0x180155824  lea     r9, [rbp+lParam]; lParam
0x180155828  lea     r8, [rbp+wParam]; wParam
0x18015582c  mov     edx, 0B0h; Msg
0x180155831  mov     rcx, [rdi+68h]; hWnd
0x180155835  call    cs:__imp_SendMessageW
0x18015583b  mov     rcx, [rdi+60h]; hWndLock
0x18015583f  call    cs:__imp_LockWindowUpdate
0x180155845  mov     rcx, [rdi+60h]; hWnd
0x180155849  test    rcx, rcx
0x18015584c  jz      loc_1801559B7
0x180155852  cmp     [rdi+68h], r15
0x180155856  jz      short loc_180155883
0x180155858  xor     r9d, r9d; lParam
0x18015585b  xor     r8d, r8d; wParam
0x18015585e  mov     edx, 157h; Msg
0x180155863  call    cs:__imp_SendMessageW
0x180155869  test    eax, eax
0x18015586b  jz      short loc_180155883
0x18015586d  xor     r9d, r9d; lParam
0x180155870  mov     edx, 100h; Msg
0x180155875  lea     r8d, [r9+1Bh]; wParam
0x180155879  mov     rcx, [rdi+68h]; hWnd
0x18015587d  call    cs:__imp_SendMessageW
0x180155883  test    esi, esi
0x180155885  jz      short loc_1801558E9
0x180155887  mov     rcx, [rdi+0F0h]
0x18015588e  test    rcx, rcx
0x180155891  jz      short loc_1801558E4
0x180155893  mov     rax, [rcx]
0x180155896  mov     rdx, [rdi+108h]
0x18015589d  mov     rax, [rax+30h]
0x1801558a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801558a6  mov     ebx, eax
0x1801558a8  test    eax, eax
0x1801558aa  js      short loc_1801558E9
0x1801558ac  mov     rcx, rdi; this
0x1801558af  call    ?_IsDirty@CAddressEditBox@@IEAAHXZ; CAddressEditBox::_IsDirty(void)
0x1801558b4  test    eax, eax
0x1801558b6  jnz     short loc_1801558E9
0x1801558b8  xor     r9d, r9d; lParam
0x1801558bb  xor     r8d, r8d; wParam
0x1801558be  mov     edx, 0B1h; Msg
0x1801558c3  mov     rcx, [rdi+68h]; hWnd
0x1801558c7  call    cs:__imp_SendMessageW
0x1801558cd  xor     r9d, r9d; lParam
0x1801558d0  xor     r8d, r8d; wParam
0x1801558d3  mov     edx, 0B7h; Msg
0x1801558d8  mov     rcx, [rdi+68h]; hWnd
0x1801558dc  call    cs:__imp_SendMessageW
0x1801558e2  jmp     short loc_1801558E9
0x1801558e4  mov     ebx, 80004005h
0x1801558e9  mov     rcx, [rdi+0D0h]; psz1
0x1801558f0  test    rcx, rcx
0x1801558f3  jz      short loc_180155906
0x1801558f5  mov     rdx, r14; psz2
0x1801558f8  call    cs:__imp_StrCmpW
0x1801558fe  test    eax, eax
0x180155900  jz      loc_1801559B7
0x180155906  cmp     [rdi+0C0h], r15
0x18015590d  jz      loc_1801559B7
0x180155913  test    ebx, ebx
0x180155915  js      loc_1801559B7
0x18015591b  lea     rsi, [rdi+100h]
0x180155922  cmp     [rsi], r15
0x180155925  jnz     short loc_18015594E
0x180155927  mov     rcx, [rdi+0F8h]
0x18015592e  test    rcx, rcx
0x180155931  jz      short loc_18015594E
0x180155933  mov     rax, [rcx]
0x180155936  mov     r8, rsi
0x180155939  lea     rdx, _GUID_1011fa30_69da_11d2_8599_006097df8c11
0x180155940  mov     rax, [rax]
0x180155943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155948  mov     ebx, eax
0x18015594a  test    eax, eax
0x18015594c  js      short loc_1801559B7
0x18015594e  mov     rdx, [rdi+0C0h]
0x180155955  or      rax, 0FFFFFFFFFFFFFFFFh
0x180155959  inc     rax
0x18015595c  cmp     [rdx+rax*2], r15w
0x180155961  jnz     short loc_180155959
0x180155963  inc     eax
0x180155965  mov     r14d, 824h
0x18015596b  cmp     eax, r14d
0x18015596e  cmova   r14d, eax
0x180155972  mov     r8d, r14d
0x180155975  lea     rcx, [rbp+var_10]
0x180155979  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18015597e  nop
0x18015597f  mov     rbx, [rbp+var_10]
0x180155983  test    rbx, rbx
0x180155986  jz      short loc_1801559A9
0x180155988  mov     edx, r14d
0x18015598b  mov     rcx, rbx
0x18015598e  call    SHCleanupUrlForDisplay
0x180155993  mov     rcx, [rsi]
0x180155996  mov     rax, [rcx]
0x180155999  mov     rdx, rbx
0x18015599c  mov     rax, [rax+18h]
0x1801559a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801559a5  mov     ebx, eax
0x1801559a7  jmp     short loc_1801559AE
0x1801559a9  mov     ebx, 8007000Eh
0x1801559ae  lea     rcx, [rbp+var_10]; void *
0x1801559b2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1801559b7  mov     rdx, [rbp+lpString]; lpString
0x1801559bb  test    rdx, rdx
0x1801559be  jz      short loc_180155A15
0x1801559c0  mov     rcx, [rdi+68h]; hWnd
0x1801559c4  call    cs:__imp_SetWindowTextW
0x1801559ca  mov     rcx, [rbp+lpString]; pv
0x1801559ce  call    cs:__imp_CoTaskMemFree
0x1801559d4  mov     eax, dword ptr [rbp+lParam]
0x1801559d7  mov     ecx, dword ptr [rbp+wParam]
0x1801559da  test    ecx, ecx
0x1801559dc  jnz     short loc_1801559E2
0x1801559de  test    eax, eax
0x1801559e0  jz      short loc_180155A0D
0x1801559e2  mov     r9, rax; lParam
0x1801559e5  mov     r8, rcx; wParam
0x1801559e8  mov     edx, 0B1h; Msg
0x1801559ed  mov     rcx, [rdi+68h]; hWnd
0x1801559f1  call    cs:__imp_SendMessageW
0x1801559f7  xor     r9d, r9d; lParam
0x1801559fa  mov     edx, 0B9h; Msg
0x1801559ff  lea     r8d, [r9+1]; wParam
0x180155a03  mov     rcx, [rdi+68h]; hWnd
0x180155a07  call    cs:__imp_SendMessageW
0x180155a0d  xor     ecx, ecx; hWndLock
0x180155a0f  call    cs:__imp_LockWindowUpdate
0x180155a15  mov     [rdi+174h], r15d
0x180155a1c  lea     rcx, [rdi+0C0h]
0x180155a23  xor     edx, edx
0x180155a25  call    Str_SetPtrPrivateW
0x180155a2a  lea     rcx, [rdi+0D0h]
0x180155a31  xor     edx, edx
0x180155a33  call    Str_SetPtrPrivateW
0x180155a38  mov     eax, ebx
0x180155a3a  mov     rbx, [rsp+30h+arg_8]
0x180155a3f  add     rsp, 30h
0x180155a43  pop     r15
0x180155a45  pop     r14
0x180155a47  pop     rdi
0x180155a48  pop     rsi
0x180155a49  pop     rbp
0x180155a4a  retn
```
