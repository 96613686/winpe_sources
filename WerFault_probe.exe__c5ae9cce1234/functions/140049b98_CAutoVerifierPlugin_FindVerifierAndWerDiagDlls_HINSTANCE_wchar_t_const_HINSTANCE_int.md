# CAutoVerifierPlugin::FindVerifierAndWerDiagDlls(HINSTANCE__ * *,wchar_t const * *,HINSTANCE__ * *,int *)

- ea: `0x140049b98`
- end: `0x140049deb`
- name: `?FindVerifierAndWerDiagDlls@CAutoVerifierPlugin@@AEAAJPEAPEAUHINSTANCE__@@PEAPEB_W0PEAH@Z`
- size: `595`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, HINSTANCE *, const wchar_t **, HINSTANCE *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14004a590`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x14001444c`
- `0x140049b98`
- `0x14005b770`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140049cfa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140049d28`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140049d52`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140049cfa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140049d28`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140049d52`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x140049c88`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x140049c88`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x140049c38`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x140049c38`

## string_xrefs

- `0x140049d1e`: `verifier.dll`
- `0x140049d37`: `verifier.dll`
- `0x140049cf0`: `vrfcore.dll`
- `0x140049d0c`: `vrfcore.dll`
- `0x140049d48`: `werdiagcontroller.dll`

## pseudocode

```c
__int64 __fastcall CAutoVerifierPlugin::FindVerifierAndWerDiagDlls(
        CAutoVerifierPlugin *this,
        HINSTANCE *a2,
        const wchar_t **a3,
        HINSTANCE *a4,
        int *a5)
{
  void *v9; // rcx
  DWORD v10; // esi
  HMODULE v11; // rbx
  const wchar_t *v12; // r12
  DWORD v13; // r14d
  __int64 v14; // rax
  WCHAR *v15; // rcx
  unsigned __int64 v16; // rax
  __int64 v17; // rdx
  WCHAR *v18; // rdi
  DWORD cbNeeded; // [rsp+20h] [rbp-E0h] BYREF
  CAutoVerifierPlugin *v21; // [rsp+28h] [rbp-D8h]
  HINSTANCE *v22; // [rsp+30h] [rbp-D0h]
  HINSTANCE *v23; // [rsp+38h] [rbp-C8h]
  const wchar_t **v24; // [rsp+40h] [rbp-C0h]
  HMODULE hModule[512]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[264]; // [rsp+1050h] [rbp+F50h] BYREF

  v24 = a3;
  v23 = a2;
  v21 = this;
  v22 = a4;
  memset_0(hModule, 0, sizeof(hModule));
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v9 = (void *)*((_QWORD *)this + 98);
  cbNeeded = 0;
  Filename[0] = 0;
  if ( K32EnumProcessModules(v9, hModule, 0x1000u, &cbNeeded) && cbNeeded <= 0x1000 )
  {
    v10 = cbNeeded >> 3;
    v11 = 0;
    v12 = 0;
    v13 = 0;
    if ( !(cbNeeded >> 3) )
      return 2147942526LL;
    do
    {
      if ( K32GetModuleFileNameExW(*((HANDLE *)v21 + 98), hModule[v13], Filename, 0x104u) )
      {
        v14 = -1;
        do
          ++v14;
        while ( Filename[v14] );
        v15 = &Filename[v14];
        while ( 1 )
        {
          v18 = v15;
          if ( v15 <= Filename )
            break;
          v16 = *--v15;
          LOWORD(v16) = v16 - 47;
          if ( (unsigned __int16)v16 <= 0x2Du )
          {
            v17 = 0x200000000801LL;
            if ( _bittest64(&v17, v16) )
              break;
          }
        }
        if ( v18 )
        {
          if ( (unsigned int)_o__wcsicmp(v18, L"vrfcore.dll") )
          {
            if ( v11 || (unsigned int)_o__wcsicmp(v18, L"verifier.dll") )
            {
              if ( !(unsigned int)_o__wcsicmp(v18, L"werdiagcontroller.dll") )
                *v22 = hModule[v13];
            }
            else
            {
              v11 = hModule[v13];
              v12 = L"verifier.dll";
              *a5 = 1;
            }
          }
          else
          {
            v11 = hModule[v13];
            v12 = L"vrfcore.dll";
            *a5 = 0;
          }
        }
      }
      ++v13;
    }
    while ( v13 < v10 );
    if ( v11 )
    {
      *v23 = v11;
      *v24 = v12;
      return 0;
    }
    else
    {
      return 2147942526LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x140049b98  push    rbp
0x140049b9a  push    rbx
0x140049b9b  push    rsi
0x140049b9c  push    rdi
0x140049b9d  push    r12
0x140049b9f  push    r13
0x140049ba1  push    r14
0x140049ba3  push    r15
0x140049ba5  lea     rbp, [rsp-1178h]
0x140049bad  mov     eax, 1278h
0x140049bb2  call    _alloca_probe
0x140049bb7  sub     rsp, rax
0x140049bba  mov     rax, cs:__security_cookie
0x140049bc1  xor     rax, rsp
0x140049bc4  mov     [rbp+11B0h+var_50], rax
0x140049bcb  mov     r13, [rbp+11B0h+arg_20]
0x140049bd2  mov     rdi, r8
0x140049bd5  mov     [rsp+12B0h+var_1270], r8
0x140049bda  mov     rbx, rdx
0x140049bdd  mov     [rsp+12B0h+var_1278], rdx
0x140049be2  mov     r14, rcx
0x140049be5  mov     [rsp+12B0h+var_1288], rcx
0x140049bea  mov     r12d, 1000h
0x140049bf0  mov     r8d, r12d; Size
0x140049bf3  mov     [rsp+12B0h+var_1280], r9
0x140049bf8  xor     edx, edx; Val
0x140049bfa  lea     rcx, [rsp+12B0h+hModule]; void *
0x140049bff  mov     rsi, r9
0x140049c02  call    memset_0
0x140049c07  xor     r15d, r15d
0x140049c0a  lea     r9, [rsp+12B0h+cbNeeded]; lpcbNeeded
0x140049c0f  mov     [rbx], r15
0x140049c12  lea     rdx, [rsp+12B0h+hModule]; lphModule
0x140049c17  mov     [rdi], r15
0x140049c1a  mov     r8d, r12d; cb
0x140049c1d  mov     [rsi], r15
0x140049c20  mov     [r13+0], r15d
0x140049c24  mov     rcx, [r14+310h]; hProcess
0x140049c2b  mov     [rsp+12B0h+cbNeeded], r15d
0x140049c30  mov     [rbp+11B0h+Filename], r15w
0x140049c38  call    cs:__imp_K32EnumProcessModules
0x140049c3e  test    eax, eax
0x140049c40  jz      loc_140049D95
0x140049c46  mov     esi, [rsp+12B0h+cbNeeded]
0x140049c4a  cmp     esi, r12d
0x140049c4d  ja      loc_140049D95
0x140049c53  shr     esi, 3
0x140049c56  mov     ebx, r15d
0x140049c59  mov     r12d, r15d
0x140049c5c  mov     r14d, r15d
0x140049c5f  test    esi, esi
0x140049c61  jz      loc_140049D8E
0x140049c67  mov     rax, [rsp+12B0h+var_1288]
0x140049c6c  lea     r8, [rbp+11B0h+Filename]; lpFilename
0x140049c73  mov     r15d, r14d
0x140049c76  mov     r9d, 104h; nSize
0x140049c7c  mov     rcx, [rax+310h]; hProcess
0x140049c83  mov     rdx, [rsp+r15*8+12B0h+hModule]; hModule
0x140049c88  call    cs:__imp_K32GetModuleFileNameExW
0x140049c8e  xor     r8d, r8d
0x140049c91  test    eax, eax
0x140049c93  jz      loc_140049D69
0x140049c99  lea     rcx, [rbp+11B0h+Filename]
0x140049ca0  or      rax, 0FFFFFFFFFFFFFFFFh
0x140049ca4  inc     rax
0x140049ca7  cmp     [rcx+rax*2], r8w
0x140049cac  jnz     short loc_140049CA4
0x140049cae  lea     rcx, [rbp+11B0h+Filename]
0x140049cb5  lea     rcx, [rcx+rax*2]
0x140049cb9  jmp     short loc_140049CDC
0x140049cbb  sub     rcx, 2
0x140049cbf  movzx   eax, word ptr [rcx]
0x140049cc2  sub     ax, 2Fh ; '/'
0x140049cc6  cmp     ax, 2Dh ; '-'
0x140049cca  ja      short loc_140049CDC
0x140049ccc  mov     rdx, 200000000801h
0x140049cd6  bt      rdx, rax
0x140049cda  jb      short loc_140049CEB
0x140049cdc  lea     rax, [rbp+11B0h+Filename]
0x140049ce3  mov     rdi, rcx
0x140049ce6  cmp     rcx, rax
0x140049ce9  ja      short loc_140049CBB
0x140049ceb  test    rdi, rdi
0x140049cee  jz      short loc_140049D69
0x140049cf0  lea     rdx, aVrfcoreDll; "vrfcore.dll"
0x140049cf7  mov     rcx, rdi
0x140049cfa  call    cs:__imp__o__wcsicmp
0x140049d00  xor     r8d, r8d
0x140049d03  test    eax, eax
0x140049d05  jnz     short loc_140049D19
0x140049d07  mov     rbx, [rsp+r15*8+12B0h+hModule]
0x140049d0c  lea     r12, aVrfcoreDll; "vrfcore.dll"
0x140049d13  mov     [r13+0], r8d
0x140049d17  jmp     short loc_140049D69
0x140049d19  test    rbx, rbx
0x140049d1c  jnz     short loc_140049D48
0x140049d1e  lea     rdx, aVerifierDll; "verifier.dll"
0x140049d25  mov     rcx, rdi
0x140049d28  call    cs:__imp__o__wcsicmp
0x140049d2e  test    eax, eax
0x140049d30  jnz     short loc_140049D48
0x140049d32  mov     rbx, [rsp+r15*8+12B0h+hModule]
0x140049d37  lea     r12, aVerifierDll; "verifier.dll"
0x140049d3e  mov     dword ptr [r13+0], 1
0x140049d46  jmp     short loc_140049D69
0x140049d48  lea     rdx, aWerdiagcontrol; "werdiagcontroller.dll"
0x140049d4f  mov     rcx, rdi
0x140049d52  call    cs:__imp__o__wcsicmp
0x140049d58  test    eax, eax
0x140049d5a  jnz     short loc_140049D69
0x140049d5c  mov     rcx, [rsp+12B0h+var_1280]
0x140049d61  mov     rax, [rsp+r15*8+12B0h+hModule]
0x140049d66  mov     [rcx], rax
0x140049d69  inc     r14d
0x140049d6c  cmp     r14d, esi
0x140049d6f  jb      loc_140049C67
0x140049d75  test    rbx, rbx
0x140049d78  jz      short loc_140049D8E
0x140049d7a  mov     rax, [rsp+12B0h+var_1278]
0x140049d7f  mov     [rax], rbx
0x140049d82  mov     rax, [rsp+12B0h+var_1270]
0x140049d87  mov     [rax], r12
0x140049d8a  xor     eax, eax
0x140049d8c  jmp     short loc_140049DC8
0x140049d8e  mov     eax, 8007007Eh
0x140049d93  jmp     short loc_140049DC8
0x140049d95  mov     rcx, cs:WPP_GLOBAL_Control
0x140049d9c  lea     rax, WPP_GLOBAL_Control
0x140049da3  cmp     rcx, rax
0x140049da6  jz      short loc_140049DC3
0x140049da8  test    byte ptr [rcx+1Ch], 1
0x140049dac  jz      short loc_140049DC3
0x140049dae  mov     rcx, [rcx+10h]
0x140049db2  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x140049db9  mov     edx, 0Eh
0x140049dbe  call    WPP_SF_
0x140049dc3  mov     eax, 80004005h
0x140049dc8  mov     rcx, [rbp+11B0h+var_50]
0x140049dcf  xor     rcx, rsp; StackCookie
0x140049dd2  call    __security_check_cookie
0x140049dd7  add     rsp, 1278h
0x140049dde  pop     r15
0x140049de0  pop     r14
0x140049de2  pop     r13
0x140049de4  pop     r12
0x140049de6  pop     rdi
0x140049de7  pop     rsi
0x140049de8  pop     rbx
0x140049de9  pop     rbp
0x140049dea  retn
```
