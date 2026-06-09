# GetResourceStringById(ushort const *,Windows::ApplicationModel::Resources::Core::IResourceMap *,HSTRING__ * *)

- ea: `0x180018550`
- end: `0x180018684`
- name: `?GetResourceStringById@@YAJPEBGPEAUIResourceMap@Core@Resources@ApplicationModel@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::ApplicationModel::Resources::Core::IResourceMap *, HSTRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001868c`

## callees

- `0x180002350`
- `0x180018550`
- `0x18001d6bc`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800185b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800185b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800185f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001862a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800185f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001862a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetResourceStringById(
        const unsigned __int16 *a1,
        struct Windows::ApplicationModel::Resources::Core::IResourceMap *a2,
        HSTRING *a3)
{
  unsigned __int64 v5; // rdx
  __int64 v6; // rdi
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int v10; // ebx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  HSTRING v13; // rax
  HSTRING v14; // rcx
  HSTRING v16; // [rsp+20h] [rbp-40h] BYREF
  __int64 v17; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF

  *a3 = 0;
  v17 = 0;
  string = 0;
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  if ( v5 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v5, (unsigned int)a3);
    __debugbreak();
  }
  if ( (int)v5 + 1 < (unsigned int)v5 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v5, (unsigned int)a3);
    __debugbreak();
  }
  v6 = *(_QWORD *)a2;
  v7 = WindowsCreateStringReference(a1, v5, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    JUMPOUT(0x180018683LL);
  }
  v10 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::IResourceMap *, HSTRING, __int64 *))(v6 + 56))(
          a2,
          string,
          &v17);
  v11 = v17;
  if ( v10 >= 0 )
  {
    if ( v17 )
    {
      v16 = 0;
      v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 80LL);
      WindowsDeleteString(0);
      v16 = 0;
      v10 = v12(v11, &v16);
      if ( v10 < 0 )
      {
        v14 = v16;
      }
      else
      {
        v13 = v16;
        v14 = 0;
        v16 = 0;
        *a3 = v13;
      }
      WindowsDeleteString(v14);
      v11 = v17;
    }
    else
    {
      v10 = -2147024893;
    }
  }
  if ( v11 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180018550  push    rbp
0x180018552  push    rbx
0x180018553  push    rsi
0x180018554  push    rdi
0x180018555  push    r14
0x180018557  mov     rbp, rsp
0x18001855a  sub     rsp, 60h
0x18001855e  mov     rax, cs:__security_cookie
0x180018565  xor     rax, rsp
0x180018568  mov     [rbp+var_10], rax
0x18001856c  mov     rsi, r8
0x18001856f  mov     rbx, rdx
0x180018572  xor     r14d, r14d
0x180018575  mov     [r8], r14
0x180018578  mov     [rbp+var_38], r14
0x18001857c  mov     [rbp+string], r14
0x180018580  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180018584  inc     rdx; int
0x180018587  cmp     [rcx+rdx*2], r14w
0x18001858c  jnz     short loc_180018584
0x18001858e  mov     eax, 0FFFFFFFFh
0x180018593  cmp     rdx, rax
0x180018596  ja      loc_180018671
0x18001859c  lea     eax, [rdx+1]
0x18001859f  cmp     eax, edx
0x1800185a1  jb      loc_180018666
0x1800185a7  mov     rdi, [rbx]
0x1800185aa  lea     r9, [rbp+string]; string
0x1800185ae  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800185b2  call    cs:__imp_WindowsCreateStringReference
0x1800185b8  test    eax, eax
0x1800185ba  js      loc_18001867C
0x1800185c0  lea     r8, [rbp+var_38]
0x1800185c4  mov     rdx, [rbp+string]
0x1800185c8  mov     rcx, rbx
0x1800185cb  mov     rax, [rdi+38h]
0x1800185cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185d4  mov     ebx, eax
0x1800185d6  mov     rdi, [rbp+var_38]
0x1800185da  test    eax, eax
0x1800185dc  js      short loc_180018634
0x1800185de  test    rdi, rdi
0x1800185e1  jnz     short loc_1800185EA
0x1800185e3  mov     ebx, 80070003h
0x1800185e8  jmp     short loc_180018634
0x1800185ea  mov     [rbp+var_40], r14
0x1800185ee  mov     rax, [rdi]
0x1800185f1  mov     rbx, [rax+50h]
0x1800185f5  xor     ecx, ecx; string
0x1800185f7  call    cs:__imp_WindowsDeleteString
0x1800185fd  mov     [rbp+var_40], r14
0x180018601  lea     rdx, [rbp+var_40]
0x180018605  mov     rcx, rdi
0x180018608  mov     rax, rbx
0x18001860b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018610  mov     ebx, eax
0x180018612  test    eax, eax
0x180018614  js      short loc_180018626
0x180018616  mov     rax, [rbp+var_40]
0x18001861a  mov     rcx, r14
0x18001861d  mov     [rbp+var_40], rcx
0x180018621  mov     [rsi], rax
0x180018624  jmp     short loc_18001862A
0x180018626  mov     rcx, [rbp+var_40]; string
0x18001862a  call    cs:__imp_WindowsDeleteString
0x180018630  mov     rdi, [rbp+var_38]
0x180018634  test    rdi, rdi
0x180018637  jz      short loc_18001864D
0x180018639  mov     [rbp+var_38], r14
0x18001863d  mov     rax, [rdi]
0x180018640  mov     rcx, rdi
0x180018643  mov     rax, [rax+10h]
0x180018647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001864c  nop
0x18001864d  mov     eax, ebx
0x18001864f  mov     rcx, [rbp+var_10]
0x180018653  xor     rcx, rsp; StackCookie
0x180018656  call    __security_check_cookie
0x18001865b  add     rsp, 60h
0x18001865f  pop     r14
0x180018661  pop     rdi
0x180018662  pop     rsi
0x180018663  pop     rbx
0x180018664  pop     rbp
0x180018665  retn
0x180018666  mov     ecx, 80070216h; this
0x18001866b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180018670  int     3; Trap to Debugger
0x180018671  mov     ecx, 80070216h; this
0x180018676  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001867b  int     3; Trap to Debugger
0x18001867c  mov     ecx, eax; this
0x18001867e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
