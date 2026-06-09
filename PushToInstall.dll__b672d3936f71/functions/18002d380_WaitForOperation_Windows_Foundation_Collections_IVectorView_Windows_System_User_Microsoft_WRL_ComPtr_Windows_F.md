# WaitForOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>(Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>> const &)

- ea: `0x18002d380`
- end: `0x18002d5af`
- name: `??$WaitForOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@@YAXAEBV?$ComPtr@U?$IAsyncOperation@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002fc74`

## callees

- `0x18002008c`
- `0x18002d114`
- `0x18002d380`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002d3e1`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18002d3e1`

## string_xrefs

- `0x18002d4cf`: `onecoreuap\enduser\winstore\pushtoinstall\inc\util.h`
- `0x18002d550`: `onecoreuap\enduser\winstore\pushtoinstall\inc\util.h`
- `0x18002d565`: `onecoreuap\enduser\winstore\pushtoinstall\inc\util.h`
- `0x18002d57a`: `onecoreuap\enduser\winstore\pushtoinstall\inc\util.h`
- `0x18002d58f`: `onecoreuap\enduser\winstore\pushtoinstall\inc\util.h`

## pseudocode

```c
__int64 __fastcall WaitForOperation<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>(
        _QWORD *a1)
{
  int v2; // eax
  HRESULT v3; // ebx
  char *v4; // rcx
  int v5; // eax
  __int64 result; // rax
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  int lpdwindexa; // [rsp+20h] [rbp-20h]
  __int64 v12; // [rsp+30h] [rbp-10h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  int v15; // [rsp+60h] [rbp+20h] BYREF
  char *v16; // [rsp+68h] [rbp+28h] BYREF
  DWORD dwindex; // [rsp+70h] [rbp+30h] BYREF
  __int64 v18; // [rsp+78h] [rbp+38h] BYREF

  MakeCom<EventDelegate<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,>(&v12);
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a1 + 48LL))(*a1, v12);
  if ( v2 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\inc\\util.h",
      (const char *)(unsigned int)v2,
      lpdwindex);
  dwindex = 0;
  pHandles = *(HANDLE *)(v12 + 56);
  v3 = CoWaitForMultipleHandles(0x18u, 0x7530u, 1u, &pHandles, &dwindex);
  if ( v3 == -2147417835 )
  {
    v16 = 0;
    if ( (**(int (__fastcall ***)(_QWORD, GUID *, char **))*a1)(*a1, &GUID_00000036_0000_0000_c000_000000000046, &v16) >= 0 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v16 + 72LL))(v16);
    v3 = -2147023436;
    v4 = v16;
    if ( v16 )
    {
      v16 = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\inc\\util.h",
      (const char *)(unsigned int)v3,
      lpdwindexa);
  v18 = 0;
  v5 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a1)(
         *a1,
         &GUID_00000036_0000_0000_c000_000000000046,
         &v18);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\inc\\util.h",
      (const char *)(unsigned int)v5,
      lpdwindexa);
  v15 = 0;
  result = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 56LL))(v18, &v15);
  if ( (int)result < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\inc\\util.h",
      (const char *)(unsigned int)result,
      lpdwindexa);
  if ( v15 == 3 )
  {
    LODWORD(v16) = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v18 + 64LL))(v18, &v16);
    if ( v7 >= 0 )
    {
      if ( (int)v16 >= 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x68,
          (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\inc\\util.h",
          (const char *)0x8000FFFFLL,
          lpdwindexa);
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\inc\\util.h",
        (const char *)(unsigned int)v16,
        lpdwindexa);
    }
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\inc\\util.h",
      (const char *)(unsigned int)v7,
      lpdwindexa);
  }
  v8 = v18;
  if ( v18 )
  {
    v18 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = v12;
  if ( v12 )
  {
    v12 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return result;
}

```

## disassembly

```asm
0x18002d380  push    rbp
0x18002d382  push    rbx
0x18002d383  push    rdi
0x18002d384  mov     rbp, rsp
0x18002d387  sub     rsp, 40h
0x18002d38b  mov     rdi, rcx
0x18002d38e  lea     rcx, [rbp+var_10]
0x18002d392  call    ??$MakeCom@V?$EventDelegate@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@@$$V@@YA?AV?$ComPtr@V?$EventDelegate@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@@@WRL@Microsoft@@XZ; MakeCom<EventDelegate<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,>(void)
0x18002d397  nop
0x18002d398  mov     rcx, [rdi]
0x18002d39b  mov     rax, [rcx]
0x18002d39e  mov     rdx, [rbp+var_10]
0x18002d3a2  mov     rax, [rax+30h]
0x18002d3a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3ab  test    eax, eax
0x18002d3ad  js      loc_18002D549
0x18002d3b3  mov     [rbp+dwindex], 0
0x18002d3ba  mov     rax, [rbp+var_10]
0x18002d3be  mov     rcx, [rax+38h]
0x18002d3c2  mov     [rbp+pHandles], rcx
0x18002d3c6  lea     rax, [rbp+dwindex]
0x18002d3ca  mov     qword ptr [rsp+40h+lpdwindex], rax; int
0x18002d3cf  lea     r9, [rbp+pHandles]; pHandles
0x18002d3d3  mov     edx, 7530h; dwTimeout
0x18002d3d8  mov     ecx, 18h; dwFlags
0x18002d3dd  lea     r8d, [rcx-17h]; cHandles
0x18002d3e1  call    cs:__imp_CoWaitForMultipleHandles
0x18002d3e7  mov     ebx, eax
0x18002d3e9  cmp     eax, 80010115h
0x18002d3ee  jnz     short loc_18002D449
0x18002d3f0  mov     [rbp+arg_8], 0
0x18002d3f8  mov     rcx, [rdi]
0x18002d3fb  mov     rax, [rcx]
0x18002d3fe  lea     r8, [rbp+arg_8]
0x18002d402  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18002d409  mov     rax, [rax]
0x18002d40c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d411  nop
0x18002d412  test    eax, eax
0x18002d414  js      short loc_18002D426
0x18002d416  mov     rcx, [rbp+arg_8]
0x18002d41a  mov     rax, [rcx]
0x18002d41d  mov     rax, [rax+48h]
0x18002d421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d426  mov     ebx, 800705B4h
0x18002d42b  mov     rcx, [rbp+arg_8]
0x18002d42f  test    rcx, rcx
0x18002d432  jz      short loc_18002D449
0x18002d434  mov     [rbp+arg_8], 0
0x18002d43c  mov     rax, [rcx]
0x18002d43f  mov     rax, [rax+10h]
0x18002d443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d448  nop
0x18002d449  mov     rcx, [rbp+18h]; this
0x18002d44d  test    ebx, ebx
0x18002d44f  js      loc_18002D562
0x18002d455  mov     [rbp+arg_18], 0
0x18002d45d  mov     rcx, [rdi]
0x18002d460  mov     rax, [rcx]
0x18002d463  lea     r8, [rbp+arg_18]
0x18002d467  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18002d46e  mov     rax, [rax]
0x18002d471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d476  nop
0x18002d477  mov     rcx, [rbp+18h]; this
0x18002d47b  test    eax, eax
0x18002d47d  js      loc_18002D577
0x18002d483  mov     [rbp+arg_0], 0
0x18002d48a  mov     rcx, [rbp+arg_18]
0x18002d48e  mov     rax, [rcx]
0x18002d491  lea     rdx, [rbp+arg_0]
0x18002d495  mov     rax, [rax+38h]
0x18002d499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d49e  mov     rcx, [rbp+18h]; this
0x18002d4a2  test    eax, eax
0x18002d4a4  js      loc_18002D58C
0x18002d4aa  cmp     [rbp+arg_0], 3
0x18002d4ae  jnz     short loc_18002D4E9
0x18002d4b0  mov     dword ptr [rbp+arg_8], 0
0x18002d4b7  mov     rcx, [rbp+arg_18]
0x18002d4bb  mov     rax, [rcx]
0x18002d4be  lea     rdx, [rbp+arg_8]
0x18002d4c2  mov     rax, [rax+40h]
0x18002d4c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4cb  mov     rcx, [rbp+18h]; this
0x18002d4cf  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002d4d6  test    eax, eax
0x18002d4d8  js      loc_18002D5A1
0x18002d4de  mov     r9d, dword ptr [rbp+arg_8]; char *
0x18002d4e2  test    r9d, r9d
0x18002d4e5  js      short loc_18002D53E
0x18002d4e7  jmp     short loc_18002D52D
0x18002d4e9  mov     rcx, [rbp+arg_18]
0x18002d4ed  test    rcx, rcx
0x18002d4f0  jz      short loc_18002D507
0x18002d4f2  mov     [rbp+arg_18], 0
0x18002d4fa  mov     rax, [rcx]
0x18002d4fd  mov     rax, [rax+10h]
0x18002d501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d506  nop
0x18002d507  mov     rcx, [rbp+var_10]
0x18002d50b  test    rcx, rcx
0x18002d50e  jz      short loc_18002D525
0x18002d510  mov     [rbp+var_10], 0
0x18002d518  mov     rax, [rcx]
0x18002d51b  mov     rax, [rax+10h]
0x18002d51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d524  nop
0x18002d525  add     rsp, 40h
0x18002d529  pop     rdi
0x18002d52a  pop     rbx
0x18002d52b  pop     rbp
0x18002d52c  retn
0x18002d52d  mov     r9d, 8000FFFFh; char *
0x18002d533  mov     edx, 68h ; 'h'; void *
0x18002d538  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d53e  mov     edx, 67h ; 'g'; void *
0x18002d543  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d549  mov     rcx, [rbp+18h]; this
0x18002d54d  mov     r9d, eax; char *
0x18002d550  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002d557  mov     edx, 48h ; 'H'; void *
0x18002d55c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d562  mov     r9d, ebx; char *
0x18002d565  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002d56c  mov     edx, 5Dh ; ']'; void *
0x18002d571  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d577  mov     r9d, eax; char *
0x18002d57a  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002d581  mov     edx, 60h ; '`'; void *
0x18002d586  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d58c  mov     r9d, eax; char *
0x18002d58f  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18002d596  mov     edx, 63h ; 'c'; void *
0x18002d59b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d5a1  mov     r9d, eax; char *
0x18002d5a4  mov     edx, 66h ; 'f'; void *
0x18002d5a9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
