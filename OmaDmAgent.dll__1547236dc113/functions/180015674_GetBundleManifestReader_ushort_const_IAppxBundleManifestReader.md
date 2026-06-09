# GetBundleManifestReader(ushort const *,IAppxBundleManifestReader * *)

- ea: `0x180015674`
- end: `0x18001584a`
- name: `?GetBundleManifestReader@@YAJPEBGPEAPEAUIAppxBundleManifestReader@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(LPCWSTR pszFile, struct IAppxBundleManifestReader **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015a2c`

## callees

- `0x18000a2c0`
- `0x180015674`
- `0x180021010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800156cd`
- `ole32!CoCreateInstance` at `0x1800156cd`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x180015729`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x180015729`

## pseudocode

```c
__int64 __fastcall GetBundleManifestReader(LPCWSTR pszFile, struct IAppxBundleManifestReader **a2)
{
  HRESULT v4; // ebx
  LPCWSTR v5; // rcx
  __int64 v6; // rdx
  IStream *ppstm; // [rsp+50h] [rbp+20h] BYREF
  __int64 v9; // [rsp+60h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp+38h] BYREF

  ppv = 0;
  ppstm = 0;
  v9 = 0;
  if ( !pszFile )
    return (unsigned int)-2147024809;
  v4 = CoCreateInstance(
         &GUID_378e0446_5384_43b7_8877_e7dbdd883446,
         0,
         1u,
         &GUID_bba65864_965f_4a5f_855f_f074bdbf3a7b,
         &ppv);
  if ( v4 >= 0 )
  {
    v4 = SHCreateStreamOnFileEx(pszFile, 0x10u, 0, 0, 0, &ppstm);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, IStream *, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, ppstm, &v9);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64, struct IAppxBundleManifestReader **))(*(_QWORD *)v9 + 40LL))(v9, a2);
        if ( v4 >= 0 )
          goto LABEL_20;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_20;
        v6 = 23;
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_20;
        v6 = 22;
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_20;
      v6 = 21;
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_20;
    v6 = 20;
  }
  WPP_SF_d(*((_QWORD *)v5 + 2), v6, &WPP_17887b334fcf349edf3df6ab34803119_Traceguids, (unsigned int)v4);
LABEL_20:
  if ( ppstm )
  {
    ((void (__fastcall *)(IStream *))ppstm->lpVtbl->Release)(ppstm);
    ppstm = 0;
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v9 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015674  mov     [rsp-18h+arg_8], rbx
0x180015679  push    rbp
0x18001567a  push    rsi
0x18001567b  push    rdi
0x18001567c  mov     rbp, rsp
0x18001567f  sub     rsp, 30h
0x180015683  mov     [rbp+arg_18], 0
0x18001568b  mov     rsi, rdx
0x18001568e  mov     [rbp+arg_0], 0
0x180015696  mov     rdi, rcx
0x180015699  mov     [rbp+arg_10], 0
0x1800156a1  test    rcx, rcx
0x1800156a4  jnz     short loc_1800156B0
0x1800156a6  mov     ebx, 80070057h
0x1800156ab  jmp     loc_18001583A
0x1800156b0  xor     edx, edx; pUnkOuter
0x1800156b2  lea     rax, [rbp+arg_18]
0x1800156b6  lea     r9, _GUID_bba65864_965f_4a5f_855f_f074bdbf3a7b; riid
0x1800156bd  mov     [rsp+30h+ppv], rax; ppv
0x1800156c2  lea     rcx, _GUID_378e0446_5384_43b7_8877_e7dbdd883446; rclsid
0x1800156c9  lea     r8d, [rdx+1]; dwClsContext
0x1800156cd  call    cs:__imp_CoCreateInstance
0x1800156d4  nop     dword ptr [rax+rax+00h]
0x1800156d9  mov     ebx, eax
0x1800156db  test    eax, eax
0x1800156dd  jns     short loc_18001570A
0x1800156df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156e6  lea     rax, WPP_GLOBAL_Control
0x1800156ed  cmp     rcx, rax
0x1800156f0  jz      loc_1800157EB
0x1800156f6  test    byte ptr [rcx+1Ch], 4
0x1800156fa  jz      loc_1800157EB
0x180015700  mov     edx, 14h
0x180015705  jmp     loc_1800157D8
0x18001570a  xor     r9d, r9d; fCreate
0x18001570d  lea     rax, [rbp+arg_0]
0x180015711  mov     [rsp+30h+ppstm], rax; ppstm
0x180015716  xor     r8d, r8d; dwAttributes
0x180015719  mov     rcx, rdi; pszFile
0x18001571c  mov     [rsp+30h+ppv], 0; pstmTemplate
0x180015725  lea     edx, [r9+10h]; grfMode
0x180015729  call    cs:__imp_SHCreateStreamOnFileEx
0x180015730  nop     dword ptr [rax+rax+00h]
0x180015735  mov     ebx, eax
0x180015737  test    eax, eax
0x180015739  jns     short loc_180015763
0x18001573b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015742  lea     rax, WPP_GLOBAL_Control
0x180015749  cmp     rcx, rax
0x18001574c  jz      loc_1800157EB
0x180015752  test    byte ptr [rcx+1Ch], 4
0x180015756  jz      loc_1800157EB
0x18001575c  mov     edx, 15h
0x180015761  jmp     short loc_1800157D8
0x180015763  mov     rcx, [rbp+arg_18]
0x180015767  lea     r8, [rbp+arg_10]
0x18001576b  mov     rdx, [rbp+arg_0]
0x18001576f  mov     rax, [rcx]
0x180015772  mov     rax, [rax+20h]
0x180015776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001577b  mov     ebx, eax
0x18001577d  test    eax, eax
0x18001577f  jns     short loc_1800157A1
0x180015781  mov     rcx, cs:WPP_GLOBAL_Control
0x180015788  lea     rax, WPP_GLOBAL_Control
0x18001578f  cmp     rcx, rax
0x180015792  jz      short loc_1800157EB
0x180015794  test    byte ptr [rcx+1Ch], 4
0x180015798  jz      short loc_1800157EB
0x18001579a  mov     edx, 16h
0x18001579f  jmp     short loc_1800157D8
0x1800157a1  mov     rcx, [rbp+arg_10]
0x1800157a5  mov     rdx, rsi
0x1800157a8  mov     rax, [rcx]
0x1800157ab  mov     rax, [rax+28h]
0x1800157af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157b4  mov     ebx, eax
0x1800157b6  test    eax, eax
0x1800157b8  jns     short loc_1800157EB
0x1800157ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800157c1  lea     rax, WPP_GLOBAL_Control
0x1800157c8  cmp     rcx, rax
0x1800157cb  jz      short loc_1800157EB
0x1800157cd  test    byte ptr [rcx+1Ch], 4
0x1800157d1  jz      short loc_1800157EB
0x1800157d3  mov     edx, 17h
0x1800157d8  mov     rcx, [rcx+10h]
0x1800157dc  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x1800157e3  mov     r9d, ebx
0x1800157e6  call    WPP_SF_d
0x1800157eb  mov     rcx, [rbp+arg_0]
0x1800157ef  test    rcx, rcx
0x1800157f2  jz      short loc_180015808
0x1800157f4  mov     rax, [rcx]
0x1800157f7  mov     rax, [rax+10h]
0x1800157fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015800  mov     [rbp+arg_0], 0
0x180015808  mov     rcx, [rbp+arg_10]
0x18001580c  test    rcx, rcx
0x18001580f  jz      short loc_180015825
0x180015811  mov     rax, [rcx]
0x180015814  mov     rax, [rax+10h]
0x180015818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001581d  mov     [rbp+arg_10], 0
0x180015825  mov     rcx, [rbp+arg_18]
0x180015829  test    rcx, rcx
0x18001582c  jz      short loc_18001583A
0x18001582e  mov     rax, [rcx]
0x180015831  mov     rax, [rax+10h]
0x180015835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001583a  mov     eax, ebx
0x18001583c  mov     rbx, [rsp+30h+arg_8]
0x180015841  add     rsp, 30h
0x180015845  pop     rdi
0x180015846  pop     rsi
0x180015847  pop     rbp
0x180015848  retn
```
