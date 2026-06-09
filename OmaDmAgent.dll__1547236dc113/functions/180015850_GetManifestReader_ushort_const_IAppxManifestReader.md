# GetManifestReader(ushort const *,IAppxManifestReader * *)

- ea: `0x180015850`
- end: `0x180015a26`
- name: `?GetManifestReader@@YAJPEBGPEAPEAUIAppxManifestReader@@@Z`
- size: `470`
- prototype: `__int64 __fastcall(LPCWSTR pszFile, struct IAppxManifestReader **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015a2c`

## callees

- `0x18000a2c0`
- `0x180015850`
- `0x180021010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800158a9`
- `ole32!CoCreateInstance` at `0x1800158a9`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x180015905`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x180015905`

## pseudocode

```c
__int64 __fastcall GetManifestReader(LPCWSTR pszFile, struct IAppxManifestReader **a2)
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
         &GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781,
         0,
         1u,
         &GUID_beb94909_e451_438b_b5a7_d79e767b75d8,
         &ppv);
  if ( v4 >= 0 )
  {
    v4 = SHCreateStreamOnFileEx(pszFile, 0x10u, 0, 0, 0, &ppstm);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, IStream *, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, ppstm, &v9);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64, struct IAppxManifestReader **))(*(_QWORD *)v9 + 56LL))(v9, a2);
        if ( v4 >= 0 )
          goto LABEL_20;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_20;
        v6 = 19;
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_20;
        v6 = 18;
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_20;
      v6 = 17;
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCWSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_20;
    v6 = 16;
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
0x180015850  mov     [rsp-18h+arg_8], rbx
0x180015855  push    rbp
0x180015856  push    rsi
0x180015857  push    rdi
0x180015858  mov     rbp, rsp
0x18001585b  sub     rsp, 30h
0x18001585f  mov     [rbp+arg_18], 0
0x180015867  mov     rsi, rdx
0x18001586a  mov     [rbp+arg_0], 0
0x180015872  mov     rdi, rcx
0x180015875  mov     [rbp+arg_10], 0
0x18001587d  test    rcx, rcx
0x180015880  jnz     short loc_18001588C
0x180015882  mov     ebx, 80070057h
0x180015887  jmp     loc_180015A16
0x18001588c  xor     edx, edx; pUnkOuter
0x18001588e  lea     rax, [rbp+arg_18]
0x180015892  lea     r9, _GUID_beb94909_e451_438b_b5a7_d79e767b75d8; riid
0x180015899  mov     [rsp+30h+ppv], rax; ppv
0x18001589e  lea     rcx, _GUID_5842a140_ff9f_4166_8f5c_62f5b7b0c781; rclsid
0x1800158a5  lea     r8d, [rdx+1]; dwClsContext
0x1800158a9  call    cs:__imp_CoCreateInstance
0x1800158b0  nop     dword ptr [rax+rax+00h]
0x1800158b5  mov     ebx, eax
0x1800158b7  test    eax, eax
0x1800158b9  jns     short loc_1800158E6
0x1800158bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158c2  lea     rax, WPP_GLOBAL_Control
0x1800158c9  cmp     rcx, rax
0x1800158cc  jz      loc_1800159C7
0x1800158d2  test    byte ptr [rcx+1Ch], 4
0x1800158d6  jz      loc_1800159C7
0x1800158dc  mov     edx, 10h
0x1800158e1  jmp     loc_1800159B4
0x1800158e6  xor     r9d, r9d; fCreate
0x1800158e9  lea     rax, [rbp+arg_0]
0x1800158ed  mov     [rsp+30h+ppstm], rax; ppstm
0x1800158f2  xor     r8d, r8d; dwAttributes
0x1800158f5  mov     rcx, rdi; pszFile
0x1800158f8  mov     [rsp+30h+ppv], 0; pstmTemplate
0x180015901  lea     edx, [r9+10h]; grfMode
0x180015905  call    cs:__imp_SHCreateStreamOnFileEx
0x18001590c  nop     dword ptr [rax+rax+00h]
0x180015911  mov     ebx, eax
0x180015913  test    eax, eax
0x180015915  jns     short loc_18001593F
0x180015917  mov     rcx, cs:WPP_GLOBAL_Control
0x18001591e  lea     rax, WPP_GLOBAL_Control
0x180015925  cmp     rcx, rax
0x180015928  jz      loc_1800159C7
0x18001592e  test    byte ptr [rcx+1Ch], 4
0x180015932  jz      loc_1800159C7
0x180015938  mov     edx, 11h
0x18001593d  jmp     short loc_1800159B4
0x18001593f  mov     rcx, [rbp+arg_18]
0x180015943  lea     r8, [rbp+arg_10]
0x180015947  mov     rdx, [rbp+arg_0]
0x18001594b  mov     rax, [rcx]
0x18001594e  mov     rax, [rax+20h]
0x180015952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015957  mov     ebx, eax
0x180015959  test    eax, eax
0x18001595b  jns     short loc_18001597D
0x18001595d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015964  lea     rax, WPP_GLOBAL_Control
0x18001596b  cmp     rcx, rax
0x18001596e  jz      short loc_1800159C7
0x180015970  test    byte ptr [rcx+1Ch], 4
0x180015974  jz      short loc_1800159C7
0x180015976  mov     edx, 12h
0x18001597b  jmp     short loc_1800159B4
0x18001597d  mov     rcx, [rbp+arg_10]
0x180015981  mov     rdx, rsi
0x180015984  mov     rax, [rcx]
0x180015987  mov     rax, [rax+38h]
0x18001598b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015990  mov     ebx, eax
0x180015992  test    eax, eax
0x180015994  jns     short loc_1800159C7
0x180015996  mov     rcx, cs:WPP_GLOBAL_Control
0x18001599d  lea     rax, WPP_GLOBAL_Control
0x1800159a4  cmp     rcx, rax
0x1800159a7  jz      short loc_1800159C7
0x1800159a9  test    byte ptr [rcx+1Ch], 4
0x1800159ad  jz      short loc_1800159C7
0x1800159af  mov     edx, 13h
0x1800159b4  mov     rcx, [rcx+10h]
0x1800159b8  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x1800159bf  mov     r9d, ebx
0x1800159c2  call    WPP_SF_d
0x1800159c7  mov     rcx, [rbp+arg_0]
0x1800159cb  test    rcx, rcx
0x1800159ce  jz      short loc_1800159E4
0x1800159d0  mov     rax, [rcx]
0x1800159d3  mov     rax, [rax+10h]
0x1800159d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159dc  mov     [rbp+arg_0], 0
0x1800159e4  mov     rcx, [rbp+arg_10]
0x1800159e8  test    rcx, rcx
0x1800159eb  jz      short loc_180015A01
0x1800159ed  mov     rax, [rcx]
0x1800159f0  mov     rax, [rax+10h]
0x1800159f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159f9  mov     [rbp+arg_10], 0
0x180015a01  mov     rcx, [rbp+arg_18]
0x180015a05  test    rcx, rcx
0x180015a08  jz      short loc_180015A16
0x180015a0a  mov     rax, [rcx]
0x180015a0d  mov     rax, [rax+10h]
0x180015a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a16  mov     eax, ebx
0x180015a18  mov     rbx, [rsp+30h+arg_8]
0x180015a1d  add     rsp, 30h
0x180015a21  pop     rdi
0x180015a22  pop     rsi
0x180015a23  pop     rbp
0x180015a24  retn
```
