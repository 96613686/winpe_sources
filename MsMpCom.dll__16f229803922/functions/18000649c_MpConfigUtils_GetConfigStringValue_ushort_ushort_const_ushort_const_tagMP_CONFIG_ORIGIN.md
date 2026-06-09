# MpConfigUtils::GetConfigStringValue(ushort * *,ushort const *,ushort const *,tagMP_CONFIG_ORIGIN *)

- ea: `0x18000649c`
- end: `0x1800065ae`
- name: `?GetConfigStringValue@MpConfigUtils@@YAJPEAPEAGPEBG1PEAW4tagMP_CONFIG_ORIGIN@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(MpConfigUtils *__hidden this, unsigned __int16 **, const unsigned __int16 *, const unsigned __int16 *, enum tagMP_CONFIG_ORIGIN *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800057f4`

## callees

- `0x18000649c`
- `0x18000a010`

## import_xrefs

- `mpclient!MpClientUtilExportFunctions` at `0x1800064b8`
- `mpclient!MpClientUtilExportFunctions` at `0x1800064e5`
- `mpclient!MpClientUtilExportFunctions` at `0x1800064b8`
- `mpclient!MpClientUtilExportFunctions` at `0x1800064e5`
- `mpclient!MpConfigGetValueAlloc` at `0x180006588`
- `mpclient!MpConfigGetValueAlloc` at `0x180006588`
- `mpclient!MpConfigClose` at `0x18000659e`
- `mpclient!MpConfigClose` at `0x18000659e`
- `mpclient!MpConfigOpen` at `0x18000654d`
- `mpclient!MpConfigOpen` at `0x18000654d`

## string_xrefs

- `0x18000650f`: `LocalCopyDirectory`
- `0x180006581`: `LocalCopyDirectory`

## pseudocode

```c
__int64 __fastcall MpConfigUtils::GetConfigStringValue(
        MpConfigUtils *this,
        unsigned __int16 **a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 (**v7)(void); // rax
  __int64 result; // rax
  int v9; // eax
  unsigned __int16 **v10; // rcx
  unsigned int v11; // ebx
  unsigned int ValueAlloc; // eax
  unsigned __int16 **v13; // [rsp+68h] [rbp+28h] BYREF
  const unsigned __int16 *v14; // [rsp+70h] [rbp+30h] BYREF
  const unsigned __int16 *v15; // [rsp+78h] [rbp+38h] BYREF

  v15 = a4;
  v14 = a3;
  v13 = a2;
  v5 = MpClientUtilExportFunctions();
  if ( !(*(unsigned int (**)(void))(v5 + 112))() )
    goto LABEL_6;
  v6 = `MpClientMiscConfigExportFunctions'::`2'::gs_aFuncs;
  LODWORD(v14) = 2;
  LODWORD(v15) = 0;
  if ( !`MpClientMiscConfigExportFunctions'::`2'::gs_aFuncs )
  {
    v7 = (__int64 (**)(void))MpClientUtilExportFunctions();
    v6 = (*v7)();
    `MpClientMiscConfigExportFunctions'::`2'::gs_aFuncs = v6;
  }
  result = (*(__int64 (__fastcall **)(const wchar_t *, const wchar_t *, const unsigned __int16 **, const unsigned __int16 **, MpConfigUtils *, _QWORD))(v6 + 40))(
             L"Real-Time Protection",
             L"LocalCopyDirectory",
             &v14,
             &v15,
             this,
             0);
  if ( (int)(result + 0x80000000) >= 0 && (_DWORD)result != -2147024894 )
  {
LABEL_6:
    v13 = 0;
    v9 = MpConfigOpen(L"Real-Time Protection", &v13);
    v10 = v13;
    v11 = v9;
    if ( v9 < 0
      || (LODWORD(v14) = 2,
          LODWORD(v15) = 0,
          ValueAlloc = MpConfigGetValueAlloc(v13, L"LocalCopyDirectory", &v14, &v15, this, 0),
          v10 = v13,
          v11 = ValueAlloc,
          v13) )
    {
      if ( v10 )
        MpConfigClose();
    }
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x18000649c  mov     [rsp-18h+arg_18], r9
0x1800064a1  mov     [rsp-18h+arg_10], r8
0x1800064a6  mov     [rsp-18h+arg_8], rdx
0x1800064ab  push    rbp
0x1800064ac  push    rbx
0x1800064ad  push    rdi
0x1800064ae  mov     rbp, rsp
0x1800064b1  sub     rsp, 40h
0x1800064b5  mov     rdi, rcx
0x1800064b8  call    cs:__imp_MpClientUtilExportFunctions
0x1800064be  mov     rax, [rax+70h]
0x1800064c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064c7  test    eax, eax
0x1800064c9  jz      short loc_18000653A
0x1800064cb  mov     rax, cs:?gs_aFuncs@?1??MpClientMiscConfigExportFunctions@@9@4PEBUtagMP_CLIENT_MISC_CONFIG_EXPORT_FUNCTIONS@@EB; tagMP_CLIENT_MISC_CONFIG_EXPORT_FUNCTIONS const * const `MpClientMiscConfigExportFunctions'::`2'::gs_aFuncs
0x1800064d2  mov     dword ptr [rbp+arg_10], 2
0x1800064d9  mov     dword ptr [rbp+arg_18], 0
0x1800064e0  test    rax, rax
0x1800064e3  jnz     short loc_1800064FA
0x1800064e5  call    cs:__imp_MpClientUtilExportFunctions
0x1800064eb  mov     rax, [rax]
0x1800064ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064f3  mov     cs:?gs_aFuncs@?1??MpClientMiscConfigExportFunctions@@9@4PEBUtagMP_CLIENT_MISC_CONFIG_EXPORT_FUNCTIONS@@EB, rax; tagMP_CLIENT_MISC_CONFIG_EXPORT_FUNCTIONS const * const `MpClientMiscConfigExportFunctions'::`2'::gs_aFuncs
0x1800064fa  mov     rax, [rax+28h]
0x1800064fe  lea     r9, [rbp+arg_18]
0x180006502  mov     [rsp+40h+var_18], 0
0x18000650b  lea     r8, [rbp+arg_10]
0x18000650f  lea     rdx, aLocalcopydirec; "LocalCopyDirectory"
0x180006516  mov     [rsp+40h+var_20], rdi
0x18000651b  lea     rcx, aRealTimeProtec; "Real-Time Protection"
0x180006522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006527  mov     edx, 80000000h
0x18000652c  lea     ecx, [rax+rdx]
0x18000652f  test    edx, ecx
0x180006531  jnz     short loc_1800065A6
0x180006533  cmp     eax, 80070002h
0x180006538  jz      short loc_1800065A6
0x18000653a  lea     rdx, [rbp+arg_8]
0x18000653e  mov     [rbp+arg_8], 0
0x180006546  lea     rcx, aRealTimeProtec; "Real-Time Protection"
0x18000654d  call    cs:__imp_MpConfigOpen
0x180006553  mov     rcx, [rbp+arg_8]
0x180006557  mov     ebx, eax
0x180006559  test    eax, eax
0x18000655b  js      short loc_180006599
0x18000655d  mov     dword ptr [rbp+arg_10], 2
0x180006564  mov     dword ptr [rbp+arg_18], 0
0x18000656b  mov     [rsp+40h+var_18], 0
0x180006574  lea     r9, [rbp+arg_18]
0x180006578  lea     r8, [rbp+arg_10]
0x18000657c  mov     [rsp+40h+var_20], rdi
0x180006581  lea     rdx, aLocalcopydirec; "LocalCopyDirectory"
0x180006588  call    cs:__imp_MpConfigGetValueAlloc
0x18000658e  mov     rcx, [rbp+arg_8]
0x180006592  mov     ebx, eax
0x180006594  test    rcx, rcx
0x180006597  jz      short loc_1800065A4
0x180006599  test    rcx, rcx
0x18000659c  jz      short loc_1800065A4
0x18000659e  call    cs:__imp_MpConfigClose
0x1800065a4  mov     eax, ebx
0x1800065a6  add     rsp, 40h
0x1800065aa  pop     rdi
0x1800065ab  pop     rbx
0x1800065ac  pop     rbp
0x1800065ad  retn
```
