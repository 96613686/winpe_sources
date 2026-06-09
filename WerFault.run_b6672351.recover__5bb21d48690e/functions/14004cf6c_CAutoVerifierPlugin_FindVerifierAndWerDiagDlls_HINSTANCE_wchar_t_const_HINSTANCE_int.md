# CAutoVerifierPlugin::FindVerifierAndWerDiagDlls(HINSTANCE__ * *,wchar_t const * *,HINSTANCE__ * *,int *)

- ea: `0x14004cf6c`
- end: `0x14004d1e2`
- name: `?FindVerifierAndWerDiagDlls@CAutoVerifierPlugin@@AEAAJPEAPEAUHINSTANCE__@@PEAPEB_W0PEAH@Z`
- size: `630`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, HINSTANCE *, const wchar_t **, HINSTANCE *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14004d9bc`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x140014ee4`
- `0x14004cf6c`
- `0x14005f510`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004d0de`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004d112`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004d142`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004d0de`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004d112`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004d142`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x14004d062`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x14004d062`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x14004d00c`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x14004d00c`

## string_xrefs

- `0x14004d108`: `verifier.dll`
- `0x14004d127`: `verifier.dll`
- `0x14004d0d4`: `vrfcore.dll`
- `0x14004d0f6`: `vrfcore.dll`
- `0x14004d138`: `werdiagcontroller.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  int v19; // eax
  __int64 v20; // r8
  DWORD cbNeeded; // [rsp+20h] [rbp-E0h] BYREF
  CAutoVerifierPlugin *v23; // [rsp+28h] [rbp-D8h]
  HINSTANCE *v24; // [rsp+30h] [rbp-D0h]
  HINSTANCE *v25; // [rsp+38h] [rbp-C8h]
  const wchar_t **v26; // [rsp+40h] [rbp-C0h]
  HMODULE hModule[512]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[264]; // [rsp+1050h] [rbp+F50h] BYREF

  v26 = a3;
  v25 = a2;
  v23 = this;
  v24 = a4;
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
      if ( K32GetModuleFileNameExW(*((HANDLE *)v23 + 98), hModule[v13], Filename, 0x104u) )
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
          v19 = _o__wcsicmp(v18, L"vrfcore.dll", 0);
          v20 = 0;
          if ( v19 )
          {
            if ( v11 || (unsigned int)_o__wcsicmp(v18, L"verifier.dll", 0) )
            {
              if ( !(unsigned int)_o__wcsicmp(v18, L"werdiagcontroller.dll", v20) )
                *v24 = hModule[v13];
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
      *v25 = v11;
      *v26 = v12;
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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids);
    }
    return 2147500037LL;
  }
}

```

## disassembly

```asm
0x14004cf6c  push    rbp
0x14004cf6e  push    rbx
0x14004cf6f  push    rsi
0x14004cf70  push    rdi
0x14004cf71  push    r12
0x14004cf73  push    r13
0x14004cf75  push    r14
0x14004cf77  push    r15
0x14004cf79  lea     rbp, [rsp-1178h]
0x14004cf81  mov     eax, 1278h
0x14004cf86  call    _alloca_probe
0x14004cf8b  sub     rsp, rax
0x14004cf8e  mov     rax, cs:__security_cookie
0x14004cf95  xor     rax, rsp
0x14004cf98  mov     [rbp+11B0h+var_50], rax
0x14004cf9f  mov     r13, [rbp+11B0h+arg_20]
0x14004cfa6  mov     rdi, r8
0x14004cfa9  mov     [rsp+12B0h+var_1270], r8
0x14004cfae  mov     rbx, rdx
0x14004cfb1  mov     [rsp+12B0h+var_1278], rdx
0x14004cfb6  mov     r14, rcx
0x14004cfb9  mov     [rsp+12B0h+var_1288], rcx
0x14004cfbe  mov     r12d, 1000h
0x14004cfc4  mov     r8d, r12d; Size
0x14004cfc7  mov     [rsp+12B0h+var_1280], r9
0x14004cfcc  xor     edx, edx; Val
0x14004cfce  lea     rcx, [rsp+12B0h+hModule]; void *
0x14004cfd3  mov     rsi, r9
0x14004cfd6  call    memset_0
0x14004cfdb  xor     r15d, r15d
0x14004cfde  lea     r9, [rsp+12B0h+cbNeeded]; lpcbNeeded
0x14004cfe3  mov     [rbx], r15
0x14004cfe6  lea     rdx, [rsp+12B0h+hModule]; lphModule
0x14004cfeb  mov     [rdi], r15
0x14004cfee  mov     r8d, r12d; cb
0x14004cff1  mov     [rsi], r15
0x14004cff4  mov     [r13+0], r15d
0x14004cff8  mov     rcx, [r14+310h]; hProcess
0x14004cfff  mov     [rsp+12B0h+cbNeeded], r15d
0x14004d004  mov     [rbp+11B0h+Filename], r15w
0x14004d00c  call    cs:__imp_K32EnumProcessModules
0x14004d013  nop     dword ptr [rax+rax+00h]
0x14004d018  test    eax, eax
0x14004d01a  jz      loc_14004D18B
0x14004d020  mov     esi, [rsp+12B0h+cbNeeded]
0x14004d024  cmp     esi, r12d
0x14004d027  ja      loc_14004D18B
0x14004d02d  shr     esi, 3
0x14004d030  mov     ebx, r15d
0x14004d033  mov     r12d, r15d
0x14004d036  mov     r14d, r15d
0x14004d039  test    esi, esi
0x14004d03b  jz      loc_14004D184
0x14004d041  mov     rax, [rsp+12B0h+var_1288]
0x14004d046  lea     r8, [rbp+11B0h+Filename]; lpFilename
0x14004d04d  mov     r15d, r14d
0x14004d050  mov     r9d, 104h; nSize
0x14004d056  mov     rcx, [rax+310h]; hProcess
0x14004d05d  mov     rdx, [rsp+r15*8+12B0h+hModule]; hModule
0x14004d062  call    cs:__imp_K32GetModuleFileNameExW
0x14004d069  nop     dword ptr [rax+rax+00h]
0x14004d06e  xor     r8d, r8d
0x14004d071  test    eax, eax
0x14004d073  jz      loc_14004D15F
0x14004d079  lea     rcx, [rbp+11B0h+Filename]
0x14004d080  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004d084  inc     rax
0x14004d087  cmp     [rcx+rax*2], r8w
0x14004d08c  jnz     short loc_14004D084
0x14004d08e  lea     rcx, [rbp+11B0h+Filename]
0x14004d095  lea     rcx, [rcx+rax*2]
0x14004d099  jmp     short loc_14004D0BC
0x14004d09b  sub     rcx, 2
0x14004d09f  movzx   eax, word ptr [rcx]
0x14004d0a2  sub     ax, 2Fh ; '/'
0x14004d0a6  cmp     ax, 2Dh ; '-'
0x14004d0aa  ja      short loc_14004D0BC
0x14004d0ac  mov     rdx, 200000000801h
0x14004d0b6  bt      rdx, rax
0x14004d0ba  jb      short loc_14004D0CB
0x14004d0bc  lea     rax, [rbp+11B0h+Filename]
0x14004d0c3  mov     rdi, rcx
0x14004d0c6  cmp     rcx, rax
0x14004d0c9  ja      short loc_14004D09B
0x14004d0cb  test    rdi, rdi
0x14004d0ce  jz      loc_14004D15F
0x14004d0d4  lea     rdx, aVrfcoreDll; "vrfcore.dll"
0x14004d0db  mov     rcx, rdi
0x14004d0de  call    cs:__imp__o__wcsicmp
0x14004d0e5  nop     dword ptr [rax+rax+00h]
0x14004d0ea  xor     r8d, r8d
0x14004d0ed  test    eax, eax
0x14004d0ef  jnz     short loc_14004D103
0x14004d0f1  mov     rbx, [rsp+r15*8+12B0h+hModule]
0x14004d0f6  lea     r12, aVrfcoreDll; "vrfcore.dll"
0x14004d0fd  mov     [r13+0], r8d
0x14004d101  jmp     short loc_14004D15F
0x14004d103  test    rbx, rbx
0x14004d106  jnz     short loc_14004D138
0x14004d108  lea     rdx, aVerifierDll; "verifier.dll"
0x14004d10f  mov     rcx, rdi
0x14004d112  call    cs:__imp__o__wcsicmp
0x14004d119  nop     dword ptr [rax+rax+00h]
0x14004d11e  test    eax, eax
0x14004d120  jnz     short loc_14004D138
0x14004d122  mov     rbx, [rsp+r15*8+12B0h+hModule]
0x14004d127  lea     r12, aVerifierDll; "verifier.dll"
0x14004d12e  mov     dword ptr [r13+0], 1
0x14004d136  jmp     short loc_14004D15F
0x14004d138  lea     rdx, aWerdiagcontrol; "werdiagcontroller.dll"
0x14004d13f  mov     rcx, rdi
0x14004d142  call    cs:__imp__o__wcsicmp
0x14004d149  nop     dword ptr [rax+rax+00h]
0x14004d14e  test    eax, eax
0x14004d150  jnz     short loc_14004D15F
0x14004d152  mov     rcx, [rsp+12B0h+var_1280]
0x14004d157  mov     rax, [rsp+r15*8+12B0h+hModule]
0x14004d15c  mov     [rcx], rax
0x14004d15f  inc     r14d
0x14004d162  cmp     r14d, esi
0x14004d165  jb      loc_14004D041
0x14004d16b  test    rbx, rbx
0x14004d16e  jz      short loc_14004D184
0x14004d170  mov     rax, [rsp+12B0h+var_1278]
0x14004d175  mov     [rax], rbx
0x14004d178  mov     rax, [rsp+12B0h+var_1270]
0x14004d17d  mov     [rax], r12
0x14004d180  xor     eax, eax
0x14004d182  jmp     short loc_14004D1BE
0x14004d184  mov     eax, 8007007Eh
0x14004d189  jmp     short loc_14004D1BE
0x14004d18b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d192  lea     rax, WPP_GLOBAL_Control
0x14004d199  cmp     rcx, rax
0x14004d19c  jz      short loc_14004D1B9
0x14004d19e  test    byte ptr [rcx+1Ch], 1
0x14004d1a2  jz      short loc_14004D1B9
0x14004d1a4  mov     rcx, [rcx+10h]
0x14004d1a8  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x14004d1af  mov     edx, 0Eh
0x14004d1b4  call    WPP_SF_
0x14004d1b9  mov     eax, 80004005h
0x14004d1be  mov     rcx, [rbp+11B0h+var_50]
0x14004d1c5  xor     rcx, rsp; StackCookie
0x14004d1c8  call    __security_check_cookie
0x14004d1cd  add     rsp, 1278h
0x14004d1d4  pop     r15
0x14004d1d6  pop     r14
0x14004d1d8  pop     r13
0x14004d1da  pop     r12
0x14004d1dc  pop     rdi
0x14004d1dd  pop     rsi
0x14004d1de  pop     rbx
0x14004d1df  pop     rbp
0x14004d1e0  retn
```
