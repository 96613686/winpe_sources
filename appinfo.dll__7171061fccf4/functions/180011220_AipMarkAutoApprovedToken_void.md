# AipMarkAutoApprovedToken(void *)

- ea: `0x180011220`
- end: `0x18001139d`
- name: `?AipMarkAutoApprovedToken@@YAJPEAX@Z`
- size: `381`
- prototype: `NTSTATUS __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800290b4`

## callees

- `0x180011220`
- `0x180046e1a`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001129c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001129c`
- `ntdll!NtSetInformationToken` at `0x180011386`
- `ntdll!NtSetInformationToken` at `0x180011386`

## pseudocode

```c
NTSTATUS __fastcall AipMarkAutoApprovedToken(HANDLE TokenHandle)
{
  __int16 v2; // ax
  __int16 *v3; // rcx
  char v4; // dl
  __int64 v5; // xmm0_8
  __int64 *v6; // rax
  __int128 v7; // xmm0
  _DWORD v9[2]; // [rsp+40h] [rbp-29h] BYREF
  __int128 v10; // [rsp+48h] [rbp-21h] BYREF
  __int128 TokenInformation; // [rsp+58h] [rbp-11h] BYREF
  __int16 v12; // [rsp+70h] [rbp+7h] BYREF
  __int64 v13; // [rsp+72h] [rbp+9h] BYREF
  int v14; // [rsp+7Ah] [rbp+11h]
  __int16 v15; // [rsp+7Eh] [rbp+15h]
  __int16 v16; // [rsp+80h] [rbp+17h]
  int v17; // [rsp+84h] [rbp+1Bh]
  int v18; // [rsp+88h] [rbp+1Fh]
  __int64 *v19; // [rsp+90h] [rbp+27h]
  __int128 v20; // [rsp+98h] [rbp+2Fh]
  __int16 v21; // [rsp+A8h] [rbp+3Fh]
  int v22; // [rsp+ACh] [rbp+43h]
  int v23; // [rsp+B0h] [rbp+47h]
  __int64 *v24; // [rsp+B8h] [rbp+4Fh]
  int pvData; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD pcbData; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+7Fh] BYREF

  v12 = 0;
  TokenInformation = 0;
  memset_0(&v13, 0, 0x4Eu);
  pvData = 0;
  pcbData = 4;
  v10 = 0;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
         L"AutoApproveHardeningClaims",
         0x10u,
         0,
         &pvData,
         &pcbData)
    || pvData )
  {
    v2 = 28;
    v3 = word_1800492B2;
    v4 = 1;
  }
  else
  {
    v2 = 24;
    v3 = word_18004B632;
    v4 = 0;
  }
  v5 = *(_QWORD *)v3;
  v12 = v2;
  v14 = *((_DWORD *)v3 + 2);
  v15 = v3[6];
  v19 = &v27;
  v6 = (__int64 *)L"\"$";
  if ( !v4 )
    v6 = &qword_1800492D0;
  v13 = v5;
  v18 = 1;
  v23 = 1;
  *(_QWORD *)&v10 = 0x200000001LL;
  v7 = *(_OWORD *)v6;
  v16 = 2;
  v24 = &v27;
  v21 = 2;
  *((_QWORD *)&v10 + 1) = &v12;
  *(_QWORD *)&TokenInformation = &v10;
  *((_QWORD *)&TokenInformation + 1) = v9;
  v27 = 0;
  v17 = 192;
  v20 = v7;
  v22 = 64;
  v9[0] = 4;
  v9[1] = 4;
  return NtSetInformationToken(TokenHandle, TokenSecurityAttributes, &TokenInformation, 0x10u);
}

```

## disassembly

```asm
0x180011220  mov     [rsp-8+arg_0], rbx
0x180011225  push    rbp
0x180011226  lea     rbp, [rsp-57h]
0x18001122b  sub     rsp, 0C0h
0x180011232  xor     eax, eax
0x180011234  mov     rbx, rcx
0x180011237  xorps   xmm0, xmm0
0x18001123a  mov     [rbp+57h+var_50], ax
0x18001123e  xor     edx, edx; Val
0x180011240  lea     rcx, [rbp+57h+var_4E]; void *
0x180011244  movups  [rbp+57h+TokenInformation], xmm0
0x180011248  lea     r8d, [rax+4Eh]; Size
0x18001124c  call    memset_0
0x180011251  lea     rax, [rbp+57h+arg_10]
0x180011255  mov     [rbp+57h+arg_8], 0
0x18001125c  mov     [rsp+0C0h+pcbData], rax; pcbData
0x180011261  lea     r8, aAutoapprovehar; "AutoApproveHardeningClaims"
0x180011268  lea     rax, [rbp+57h+arg_8]
0x18001126c  mov     [rbp+57h+arg_10], 4
0x180011273  xorps   xmm0, xmm0
0x180011276  mov     [rsp+0C0h+pvData], rax; pvData
0x18001127b  mov     r9d, 10h; dwFlags
0x180011281  mov     [rsp+0C0h+pdwType], 0; pdwType
0x18001128a  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180011291  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180011298  movups  [rbp+57h+var_78], xmm0
0x18001129c  call    cs:__imp_RegGetValueW
0x1800112a2  mov     r9d, 1
0x1800112a8  test    eax, eax
0x1800112aa  jnz     short loc_1800112C3
0x1800112ac  cmp     [rbp+57h+arg_8], eax
0x1800112af  jnz     short loc_1800112C3
0x1800112b1  movzx   eax, cs:word_18004B630
0x1800112b8  lea     rcx, word_18004B632
0x1800112bf  xor     dl, dl
0x1800112c1  jmp     short loc_1800112D4
0x1800112c3  movzx   eax, cs:word_1800492B0
0x1800112ca  lea     rcx, word_1800492B2
0x1800112d1  mov     dl, r9b
0x1800112d4  movsd   xmm0, qword ptr [rcx]
0x1800112d8  mov     r8d, 2
0x1800112de  mov     [rbp+57h+var_50], ax
0x1800112e2  test    dl, dl
0x1800112e4  mov     eax, [rcx+8]
0x1800112e7  mov     [rbp+57h+var_46], eax
0x1800112ea  movzx   eax, word ptr [rcx+0Ch]
0x1800112ee  lea     rcx, qword_1800492D0
0x1800112f5  mov     [rbp+57h+var_42], ax
0x1800112f9  lea     rax, [rbp+57h+arg_18]
0x1800112fd  mov     [rbp+57h+var_30], rax
0x180011301  lea     rax, asc_1800492C0; "\"$"
0x180011308  cmovz   rax, rcx
0x18001130c  movsd   [rbp+57h+var_4E], xmm0
0x180011311  mov     [rbp+57h+var_38], r9d
0x180011315  mov     rcx, rbx; TokenHandle
0x180011318  mov     [rbp+57h+var_10], r9d
0x18001131c  mov     dword ptr [rbp+57h+var_78], r9d
0x180011320  lea     r9d, [r8+0Eh]; TokenInformationLength
0x180011324  movups  xmm0, xmmword ptr [rax]
0x180011327  lea     rax, [rbp+57h+arg_18]
0x18001132b  mov     [rbp+57h+var_40], r8w
0x180011330  mov     [rbp+57h+var_8], rax
0x180011334  lea     edx, [r9+17h]; TokenInformationClass
0x180011338  lea     rax, [rbp+57h+var_50]
0x18001133c  mov     [rbp+57h+var_18], r8w
0x180011341  mov     qword ptr [rbp+57h+var_78+8], rax
0x180011345  lea     rax, [rbp+57h+var_78]
0x180011349  mov     qword ptr [rbp+57h+TokenInformation], rax
0x18001134d  lea     rax, [rbp+57h+var_80]
0x180011351  mov     dword ptr [rbp+57h+var_78+4], r8d
0x180011355  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180011359  mov     qword ptr [rbp+57h+TokenInformation+8], rax
0x18001135d  mov     [rbp+57h+arg_18], 0
0x180011365  mov     [rbp+57h+var_3C], 0C0h
0x18001136c  movdqu  [rbp+57h+var_28], xmm0
0x180011371  mov     [rbp+57h+var_14], 40h ; '@'
0x180011378  mov     [rbp+57h+var_80], 4
0x18001137f  mov     [rbp+57h+var_7C], 4
0x180011386  call    cs:__imp_NtSetInformationToken
0x18001138c  mov     rbx, [rsp+0C0h+arg_0]
0x180011394  add     rsp, 0C0h
0x18001139b  pop     rbp
0x18001139c  retn
```
