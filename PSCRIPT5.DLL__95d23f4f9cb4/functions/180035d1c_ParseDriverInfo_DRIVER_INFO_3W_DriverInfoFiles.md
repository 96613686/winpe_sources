# ParseDriverInfo(_DRIVER_INFO_3W *,DriverInfoFiles *)

- ea: `0x180035d1c`
- end: `0x180035e36`
- name: `?ParseDriverInfo@@YAXPEAU_DRIVER_INFO_3W@@PEAUDriverInfoFiles@@@Z`
- size: `282`
- prototype: `void(struct _DRIVER_INFO_3W *, struct DriverInfoFiles *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180033ecc`
- `0x1800343d0`

## callees

- `0x18000283c`
- `0x1800028d8`
- `0x180035d1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180035d75`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180035dd8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180035d75`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180035dd8`

## string_xrefs

- `0x180035d84`: `-manifest.ini`
- `0x180035de3`: `-manifest.ini`

## pseudocode

```c
void __fastcall ParseDriverInfo(struct _DRIVER_INFO_3W *a1, const wchar_t **a2)
{
  const wchar_t *pDependentFiles; // rcx
  wchar_t *v5; // rax
  const wchar_t *v6; // rbx
  __int64 v7; // rax
  wchar_t *v8; // rax
  __int64 v9; // rax

  memset_0(a2, 0, 0x50u);
  *a2 = a1->pConfigFile;
  a2[1] = a1->pDriverPath;
  a2[2] = a1->pDataFile;
  a2[4] = a1->pDependentFiles;
  if ( a1->cVersion >= 4 )
  {
    pDependentFiles = a1->pDependentFiles;
    if ( !pDependentFiles )
      return;
    v5 = wcsrchr(pDependentFiles, 0x2Du);
    if ( !v5 || wcsicmp(v5, L"-manifest.ini") )
      return;
    a2[3] = a1->pDependentFiles;
  }
  v6 = a2[4];
  if ( v6 )
  {
    do
    {
      v7 = -1;
      do
        ++v7;
      while ( v6[v7] );
      v6 += v7 + 1;
      if ( a2[7] )
      {
        a2[9] = v6;
        if ( !*v6 )
          return;
        v9 = -1;
        do
          ++v9;
        while ( v6[v9] );
        if ( !v6[v9 + 1] )
          a2[6] = v6;
      }
      else
      {
        a2[5] = v6;
        if ( v6 )
        {
          v8 = wcsrchr(v6, 0x2Du);
          if ( v8 )
          {
            if ( !wcsicmp(v8, L"-manifest.ini") )
            {
              a2[7] = v6;
              a2[8] = v6;
            }
          }
        }
      }
    }
    while ( *v6 );
  }
}

```

## disassembly

```asm
0x180035d1c  mov     [rsp+arg_0], rbx
0x180035d21  mov     [rsp+arg_8], rsi
0x180035d26  push    rdi
0x180035d27  sub     rsp, 20h
0x180035d2b  mov     rdi, rdx
0x180035d2e  mov     rbx, rcx
0x180035d31  xor     edx, edx; Val
0x180035d33  mov     rcx, rdi; void *
0x180035d36  lea     r8d, [rdx+50h]; Size
0x180035d3a  call    memset_0
0x180035d3f  mov     rax, [rbx+28h]
0x180035d43  xor     esi, esi
0x180035d45  mov     [rdi], rax
0x180035d48  mov     rax, [rbx+18h]
0x180035d4c  mov     [rdi+8], rax
0x180035d50  mov     rax, [rbx+20h]
0x180035d54  mov     [rdi+10h], rax
0x180035d58  mov     rax, [rbx+38h]
0x180035d5c  mov     [rdi+20h], rax
0x180035d60  cmp     dword ptr [rbx], 4
0x180035d63  jb      short loc_180035DA3
0x180035d65  mov     rcx, [rbx+38h]; Str
0x180035d69  test    rcx, rcx
0x180035d6c  jz      loc_180035E26
0x180035d72  lea     edx, [rsi+2Dh]; Ch
0x180035d75  call    cs:__imp_wcsrchr
0x180035d7b  test    rax, rax
0x180035d7e  jz      loc_180035E26
0x180035d84  lea     rdx, aManifestIni; "-manifest.ini"
0x180035d8b  mov     rcx, rax; String1
0x180035d8e  call    _wcsicmp
0x180035d93  test    eax, eax
0x180035d95  jnz     loc_180035E26
0x180035d9b  mov     rax, [rbx+38h]
0x180035d9f  mov     [rdi+18h], rax
0x180035da3  mov     rbx, [rdi+20h]
0x180035da7  test    rbx, rbx
0x180035daa  jz      short loc_180035E26
0x180035dac  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035db0  inc     rax
0x180035db3  cmp     [rbx+rax*2], si
0x180035db7  jnz     short loc_180035DB0
0x180035db9  lea     rbx, [rbx+rax*2]
0x180035dbd  add     rbx, 2
0x180035dc1  cmp     [rdi+38h], rsi
0x180035dc5  jnz     short loc_180035E00
0x180035dc7  mov     [rdi+28h], rbx
0x180035dcb  test    rbx, rbx
0x180035dce  jz      short loc_180035E21
0x180035dd0  mov     edx, 2Dh ; '-'; Ch
0x180035dd5  mov     rcx, rbx; Str
0x180035dd8  call    cs:__imp_wcsrchr
0x180035dde  test    rax, rax
0x180035de1  jz      short loc_180035E21
0x180035de3  lea     rdx, aManifestIni; "-manifest.ini"
0x180035dea  mov     rcx, rax; String1
0x180035ded  call    _wcsicmp
0x180035df2  test    eax, eax
0x180035df4  jnz     short loc_180035E21
0x180035df6  mov     [rdi+38h], rbx
0x180035dfa  mov     [rdi+40h], rbx
0x180035dfe  jmp     short loc_180035E21
0x180035e00  mov     [rdi+48h], rbx
0x180035e04  cmp     [rbx], si
0x180035e07  jz      short loc_180035E26
0x180035e09  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035e0d  inc     rax
0x180035e10  cmp     [rbx+rax*2], si
0x180035e14  jnz     short loc_180035E0D
0x180035e16  cmp     [rbx+rax*2+2], si
0x180035e1b  jnz     short loc_180035E21
0x180035e1d  mov     [rdi+30h], rbx
0x180035e21  cmp     [rbx], si
0x180035e24  jnz     short loc_180035DAC
0x180035e26  mov     rbx, [rsp+28h+arg_0]
0x180035e2b  mov     rsi, [rsp+28h+arg_8]
0x180035e30  add     rsp, 20h
0x180035e34  pop     rdi
0x180035e35  retn
```
