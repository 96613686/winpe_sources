# InvalidateCachedTokens(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<IInspectable *>> &)

- ea: `0x180036420`
- end: `0x18003665e`
- name: `?InvalidateCachedTokens@@YAXAEAV?$ComPtr@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004d7f4`

## callees

- `0x18002008c`
- `0x18002c4b8`
- `0x1800357d8`
- `0x180036420`
- `0x18004f010`

## string_xrefs

- `0x180036491`: `onecoreuap\enduser\winstore\pushtoinstall\lib\identity.cpp`
- `0x1800365f8`: `onecoreuap\enduser\winstore\pushtoinstall\lib\identity.cpp`
- `0x18003660d`: `onecoreuap\enduser\winstore\pushtoinstall\lib\identity.cpp`
- `0x180036622`: `onecoreuap\enduser\winstore\pushtoinstall\lib\identity.cpp`
- `0x180036637`: `onecoreuap\enduser\winstore\pushtoinstall\lib\identity.cpp`
- `0x18003664b`: `onecoreuap\enduser\winstore\pushtoinstall\lib\identity.cpp`
- `0x180036484`: `InvalidateCachedTokens`
- `0x180036470`: `Invalidating (%d) cached token(s).`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall InvalidateCachedTokens(_QWORD *a1)
{
  _QWORD *v1; // rsi
  __int64 v2; // rcx
  int v3; // eax
  unsigned int i; // edi
  int v5; // eax
  int v6; // eax
  int v7; // eax
  HRESULT v8; // edx
  __int64 v9; // r8
  int v10; // eax
  const char *v11; // r9
  int (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v13; // rcx
  __int64 (__fastcall ***v14)(_QWORD, GUID *, _QWORD *); // rcx
  int v15; // [rsp+20h] [rbp-48h]
  int v16; // [rsp+20h] [rbp-48h]
  __int64 v17; // [rsp+40h] [rbp-28h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int v22; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v23; // [rsp+80h] [rbp+18h]
  int (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // [rsp+88h] [rbp+20h] BYREF

  v1 = a1;
  v2 = *a1;
  if ( v2 )
  {
    v22 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v2 + 56LL))(v2, &v22);
    if ( v3 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x40,
        (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\identity.cpp",
        (const char *)(unsigned int)v3,
        v15);
    if ( v22 )
    {
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\identity.cpp",
        0x43u,
        "InvalidateCachedTokens",
        -1,
        L"Invalidating (%d) cached token(s).");
      for ( i = 0; ; ++i )
      {
        v23 = i;
        if ( i >= v22 )
          break;
        v18 = 0;
        try
        {
          v5 = (*(__int64 (**)(void))(*(_QWORD *)*v1 + 48LL))();
          if ( v5 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x4A,
              (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\identity.cpp",
              (const char *)(unsigned int)v5,
              v16);
          v17 = 0;
          v6 = (**v18)(v18, &GUID_c12a8305_d1f8_4483_8d54_38fe292784ff, &v17);
          if ( v6 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x4D,
              (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\identity.cpp",
              (const char *)(unsigned int)v6,
              v16);
          v24 = 0;
          v7 = (*(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v17 + 72LL))(
                 v17,
                 &v24);
          if ( v7 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x50,
              (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\identity.cpp",
              (const char *)(unsigned int)v7,
              v16);
          WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(
            v24,
            v8,
            v9);
          v10 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v24)[8])(v24);
          if ( v10 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x52,
              (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\identity.cpp",
              (const char *)(unsigned int)v10,
              v16);
          v12 = v24;
          if ( v24 )
          {
            v24 = 0;
            ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v12)[2])(v12);
          }
          v13 = v17;
          if ( v17 )
          {
            v17 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
          v14 = v18;
          if ( v18 )
          {
            v18 = 0;
            ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v14)[2])(v14);
          }
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x54,
            (unsigned int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\identity.cpp",
            v11);
          v1 = a1;
          i = v23;
          continue;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180036420  mov     [rsp+arg_0], rcx
0x180036425  push    rsi
0x180036426  push    rdi
0x180036427  sub     rsp, 58h
0x18003642b  mov     rsi, rcx
0x18003642e  mov     rcx, [rcx]
0x180036431  test    rcx, rcx
0x180036434  jz      loc_1800365EE
0x18003643a  mov     [rsp+68h+arg_8], 0
0x180036442  mov     rax, [rcx]
0x180036445  lea     rdx, [rsp+68h+arg_8]
0x18003644a  mov     rax, [rax+38h]
0x18003644e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036453  mov     rcx, [rsp+68h]; this
0x180036458  test    eax, eax
0x18003645a  js      loc_1800365F5
0x180036460  mov     eax, [rsp+68h+arg_8]
0x180036464  test    eax, eax
0x180036466  jz      loc_1800365EE
0x18003646c  mov     [rsp+68h+var_38], eax
0x180036470  lea     rax, aInvalidatingDC; "Invalidating (%d) cached token(s)."
0x180036477  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18003647c  mov     [rsp+68h+var_48], 0FFFFFFFFh; int
0x180036484  lea     r9, aInvalidatecach; "InvalidateCachedTokens"
0x18003648b  mov     r8d, 43h ; 'C'; unsigned int
0x180036491  lea     rdx, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180036498  lea     ecx, [r8-40h]; unsigned int
0x18003649c  call    ?LogMessage@@YAXIPEBDI0JPEBGZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,...)
0x1800364a1  xor     edi, edi
0x1800364a3  mov     [rsp+68h+arg_10], edi
0x1800364aa  cmp     edi, [rsp+68h+arg_8]
0x1800364ae  jnb     loc_1800365EE
0x1800364b4  mov     [rsp+68h+var_20], 0
0x1800364bd  mov     rcx, [rsi]
0x1800364c0  mov     rax, [rcx]
0x1800364c3  lea     r8, [rsp+68h+var_20]
0x1800364c8  mov     edx, edi
0x1800364ca  mov     rax, [rax+30h]
0x1800364ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364d3  mov     rcx, [rsp+68h]; this
0x1800364d8  test    eax, eax
0x1800364da  js      loc_18003660A
0x1800364e0  mov     [rsp+68h+var_28], 0
0x1800364e9  mov     rcx, [rsp+68h+var_20]
0x1800364ee  mov     rax, [rcx]
0x1800364f1  lea     r8, [rsp+68h+var_28]
0x1800364f6  lea     rdx, _GUID_c12a8305_d1f8_4483_8d54_38fe292784ff
0x1800364fd  mov     rax, [rax]
0x180036500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036505  nop
0x180036506  mov     rcx, [rsp+68h]; this
0x18003650b  test    eax, eax
0x18003650d  js      loc_18003661F
0x180036513  mov     [rsp+68h+arg_18], 0
0x18003651f  mov     rcx, [rsp+68h+var_28]
0x180036524  mov     rax, [rcx]
0x180036527  lea     rdx, [rsp+68h+arg_18]
0x18003652f  mov     rax, [rax+48h]
0x180036533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036538  mov     rcx, [rsp+68h]; this
0x18003653d  test    eax, eax
0x18003653f  js      loc_180036634
0x180036545  mov     rcx, [rsp+68h+arg_18]
0x18003654d  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x180036552  mov     rcx, [rsp+68h+arg_18]
0x18003655a  mov     rax, [rcx]
0x18003655d  mov     rax, [rax+40h]
0x180036561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036566  mov     rcx, [rsp+68h]; this
0x18003656b  test    eax, eax
0x18003656d  js      loc_180036648
0x180036573  mov     rcx, [rsp+68h+arg_18]
0x18003657b  test    rcx, rcx
0x18003657e  jz      short loc_180036599
0x180036580  mov     [rsp+68h+arg_18], 0
0x18003658c  mov     rax, [rcx]
0x18003658f  mov     rax, [rax+10h]
0x180036593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036598  nop
0x180036599  mov     rcx, [rsp+68h+var_28]
0x18003659e  test    rcx, rcx
0x1800365a1  jz      short loc_1800365B9
0x1800365a3  mov     [rsp+68h+var_28], 0
0x1800365ac  mov     rax, [rcx]
0x1800365af  mov     rax, [rax+10h]
0x1800365b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365b8  nop
0x1800365b9  mov     rcx, [rsp+68h+var_20]
0x1800365be  test    rcx, rcx
0x1800365c1  jz      short loc_1800365D9
0x1800365c3  mov     [rsp+68h+var_20], 0
0x1800365cc  mov     rax, [rcx]
0x1800365cf  mov     rax, [rax+10h]
0x1800365d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800365d8  nop
0x1800365d9  jmp     short loc_1800365E7
0x1800365db  mov     rsi, [rsp+68h+arg_0]
0x1800365e0  mov     edi, [rsp+68h+arg_10]
0x1800365e7  inc     edi
0x1800365e9  jmp     loc_1800364A3
0x1800365ee  add     rsp, 58h
0x1800365f2  pop     rdi
0x1800365f3  pop     rsi
0x1800365f4  retn
0x1800365f5  mov     r9d, eax; char *
0x1800365f8  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x1800365ff  mov     edx, 40h ; '@'; void *
0x180036604  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003660a  mov     r9d, eax; char *
0x18003660d  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180036614  mov     edx, 4Ah ; 'J'; void *
0x180036619  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003661f  mov     r9d, eax; char *
0x180036622  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180036629  mov     edx, 4Dh ; 'M'; void *
0x18003662e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180036634  mov     r9d, eax; char *
0x180036637  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x18003663e  mov     edx, 50h ; 'P'; void *
0x180036643  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180036648  mov     r9d, eax; char *
0x18003664b  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180036652  mov     edx, 52h ; 'R'; void *
0x180036657  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
