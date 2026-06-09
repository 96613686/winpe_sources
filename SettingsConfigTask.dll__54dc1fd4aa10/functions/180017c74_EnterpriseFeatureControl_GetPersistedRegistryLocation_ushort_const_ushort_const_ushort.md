# EnterpriseFeatureControl::GetPersistedRegistryLocation(ushort const *,ushort const *,ushort * *)

- ea: `0x180017c74`
- end: `0x180017db5`
- name: `?GetPersistedRegistryLocation@EnterpriseFeatureControl@@CAJPEBG0PEAPEAG@Z`
- size: `321`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180019ffc`

## callees

- `0x18000972c`
- `0x180010248`
- `0x180012940`
- `0x180017c74`
- `0x18001b968`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180017cd8`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180017d69`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180017cd8`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180017d69`

## string_xrefs

- `0x180017cd1`: `WindowsUpdate`
- `0x180017d62`: `WindowsUpdate`
- `0x180017cca`: `SOFTWARE\Microsoft\WindowsUpdate`
- `0x180017d4f`: `SOFTWARE\Microsoft\WindowsUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnterpriseFeatureControl::GetPersistedRegistryLocation(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int PersistedRegistryLocationW; // eax
  __int64 v7; // rdx
  unsigned __int16 *v8; // rbx
  unsigned int v9; // eax
  const unsigned __int16 **v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  const unsigned __int16 *v13; // [rsp+40h] [rbp+8h] BYREF
  const unsigned __int16 *v14; // [rsp+48h] [rbp+10h] BYREF

  v14 = a2;
  v13 = a1;
  if ( !a3 )
  {
    v4 = -2147467261;
    v5 = 87;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)v4,
      (int)v11);
    return v4;
  }
  LODWORD(v14) = 0;
  v11 = &v14;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"WindowsUpdate",
                                 L"SOFTWARE\\Microsoft\\WindowsUpdate",
                                 0,
                                 0);
  v4 = PersistedRegistryLocationW;
  if ( !PersistedRegistryLocationW )
  {
    v4 = -2147418113;
    v5 = 93;
    goto LABEL_3;
  }
  if ( PersistedRegistryLocationW == 234 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v13,
      v7,
      (unsigned int)v14);
    v8 = (unsigned __int16 *)v13;
    if ( v13 )
    {
      v9 = GetPersistedRegistryLocationW(
             L"WindowsUpdate",
             L"SOFTWARE\\Microsoft\\WindowsUpdate",
             v13,
             (unsigned int)v14);
      if ( v9 )
      {
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x63,
               (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
               (const char *)v9,
               0);
      }
      else
      {
        *a3 = v8;
        v4 = 0;
        v13 = 0;
      }
    }
    else
    {
      v4 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
        (const char *)0x8007000ELL,
        (int)&v14);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
  }
  else
  {
    if ( PersistedRegistryLocationW > 0 )
      v4 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( (v4 & 0x80000000) != 0 )
    {
      v5 = 94;
      goto LABEL_3;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180017c74  mov     [rsp+arg_10], rbx
0x180017c79  mov     [rsp+arg_8], rdx
0x180017c7e  mov     [rsp+arg_0], rcx
0x180017c83  push    rdi
0x180017c84  sub     rsp, 30h
0x180017c88  mov     rdi, r8
0x180017c8b  test    r8, r8
0x180017c8e  jnz     short loc_180017CB2
0x180017c90  mov     ebx, 80004003h
0x180017c95  lea     edx, [r8+57h]; void *
0x180017c99  mov     rcx, [rsp+38h]; this
0x180017c9e  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180017ca5  mov     r9d, ebx; char *
0x180017ca8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017cad  jmp     loc_180017DA8
0x180017cb2  lea     rax, [rsp+38h+arg_8]
0x180017cb7  mov     dword ptr [rsp+38h+arg_8], 0
0x180017cbf  xor     r9d, r9d
0x180017cc2  mov     qword ptr [rsp+38h+var_18], rax; int
0x180017cc7  xor     r8d, r8d
0x180017cca  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate"
0x180017cd1  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x180017cd8  call    cs:__imp_GetPersistedRegistryLocationW
0x180017cde  mov     ebx, eax
0x180017ce0  test    eax, eax
0x180017ce2  jnz     short loc_180017CEE
0x180017ce4  mov     ebx, 8000FFFFh
0x180017ce9  lea     edx, [rax+5Dh]
0x180017cec  jmp     short loc_180017C99
0x180017cee  cmp     eax, 0EAh
0x180017cf3  jz      short loc_180017D11
0x180017cf5  test    eax, eax
0x180017cf7  jle     short loc_180017D02
0x180017cf9  movzx   ebx, ax
0x180017cfc  or      ebx, 80070000h
0x180017d02  test    ebx, ebx
0x180017d04  jns     loc_180017DA8
0x180017d0a  mov     edx, 5Eh ; '^'
0x180017d0f  jmp     short loc_180017C99
0x180017d11  mov     r8d, dword ptr [rsp+38h+arg_8]
0x180017d16  lea     rcx, [rsp+38h+arg_0]
0x180017d1b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180017d20  mov     rbx, [rsp+38h+arg_0]
0x180017d25  test    rbx, rbx
0x180017d28  jnz     short loc_180017D4A
0x180017d2a  mov     rcx, [rsp+38h]; this
0x180017d2f  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180017d36  mov     ebx, 8007000Eh
0x180017d3b  mov     edx, 61h ; 'a'; void *
0x180017d40  mov     r9d, ebx; char *
0x180017d43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d48  jmp     short loc_180017D9E
0x180017d4a  mov     r9d, dword ptr [rsp+38h+arg_8]
0x180017d4f  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate"
0x180017d56  mov     r8, rbx
0x180017d59  mov     qword ptr [rsp+38h+var_18], 0; unsigned int
0x180017d62  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x180017d69  call    cs:__imp_GetPersistedRegistryLocationW
0x180017d6f  test    eax, eax
0x180017d71  jz      short loc_180017D90
0x180017d73  mov     rcx, [rsp+38h]; this
0x180017d78  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180017d7f  mov     r9d, eax; char *
0x180017d82  mov     edx, 63h ; 'c'; void *
0x180017d87  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180017d8c  mov     ebx, eax
0x180017d8e  jmp     short loc_180017D9E
0x180017d90  mov     [rdi], rbx
0x180017d93  xor     ebx, ebx
0x180017d95  mov     [rsp+38h+arg_0], 0
0x180017d9e  lea     rcx, [rsp+38h+arg_0]
0x180017da3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180017da8  mov     eax, ebx
0x180017daa  mov     rbx, [rsp+38h+arg_10]
0x180017daf  add     rsp, 30h
0x180017db3  pop     rdi
0x180017db4  retn
```
