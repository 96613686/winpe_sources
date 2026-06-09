# AipMarkAutoApprovedToken(void *)

- ea: `0x180012740`
- end: `0x180012884`
- name: `?AipMarkAutoApprovedToken@@YAJPEAX@Z`
- size: `324`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024a98`

## callees

- `0x180012740`
- `0x1800449fa`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800127a2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800127a2`
- `ntdll!NtSetInformationToken` at `0x18001286c`
- `ntdll!NtSetInformationToken` at `0x18001286c`

## pseudocode

```c
NTSTATUS __fastcall AipMarkAutoApprovedToken(HANDLE TokenHandle)
{
  __int128 *v2; // rax
  char v3; // cl
  __int128 v4; // xmm0
  const wchar_t *v5; // rax
  __int128 v6; // xmm0
  _DWORD v8[2]; // [rsp+40h] [rbp-39h] BYREF
  _DWORD v9[2]; // [rsp+48h] [rbp-31h] BYREF
  __int128 *v10; // [rsp+50h] [rbp-29h]
  _QWORD TokenInformation[3]; // [rsp+58h] [rbp-21h] BYREF
  __int128 v12; // [rsp+70h] [rbp-9h] BYREF
  __int16 v13; // [rsp+80h] [rbp+7h]
  int v14; // [rsp+84h] [rbp+Bh]
  int v15; // [rsp+88h] [rbp+Fh]
  __int64 *v16; // [rsp+90h] [rbp+17h]
  __int128 v17; // [rsp+98h] [rbp+1Fh]
  __int16 v18; // [rsp+A8h] [rbp+2Fh]
  int v19; // [rsp+ACh] [rbp+33h]
  int v20; // [rsp+B0h] [rbp+37h]
  __int64 *v21; // [rsp+B8h] [rbp+3Fh]
  int pvData; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD pcbData; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v24; // [rsp+F8h] [rbp+7Fh] BYREF

  LOWORD(v12) = 0;
  memset_0((char *)&v12 + 2, 0, 0x4Eu);
  pvData = 0;
  pcbData = 4;
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
    v2 = (__int128 *)&unk_1800472A0;
    v3 = 1;
  }
  else
  {
    v2 = (__int128 *)&unk_180049430;
    v3 = 0;
  }
  v4 = *v2;
  v15 = 1;
  v20 = 1;
  v9[0] = 1;
  v13 = 2;
  v16 = &v24;
  v12 = v4;
  v18 = 2;
  v5 = L"\"$";
  if ( !v3 )
    v5 = (const wchar_t *)&unk_1800472C0;
  v9[1] = 2;
  v24 = 0;
  v14 = 192;
  v19 = 64;
  v6 = *(_OWORD *)v5;
  v8[0] = 4;
  v21 = &v24;
  v10 = &v12;
  TokenInformation[0] = v9;
  TokenInformation[1] = v8;
  v17 = v6;
  v8[1] = 4;
  return NtSetInformationToken(TokenHandle, TokenSecurityAttributes, TokenInformation, 0x10u);
}

```

## disassembly

```asm
0x180012740  push    rbp
0x180012742  push    rbx
0x180012743  push    rdi
0x180012744  lea     rbp, [rsp-47h]
0x180012749  sub     rsp, 0C0h
0x180012750  xor     edi, edi
0x180012752  mov     rbx, rcx
0x180012755  xor     edx, edx; Val
0x180012757  mov     word ptr [rbp+57h+var_60], di
0x18001275b  lea     rcx, [rbp+57h+var_60+2]; void *
0x18001275f  lea     r8d, [rdi+4Eh]; Size
0x180012763  call    memset_0
0x180012768  lea     rax, [rbp+57h+arg_10]
0x18001276c  mov     [rbp+57h+arg_8], edi
0x18001276f  mov     [rsp+0D0h+pcbData], rax; pcbData
0x180012774  lea     r9d, [rdi+10h]; dwFlags
0x180012778  lea     rax, [rbp+57h+arg_8]
0x18001277c  mov     [rbp+57h+arg_10], 4
0x180012783  mov     [rsp+0D0h+pvData], rax; pvData
0x180012788  lea     r8, aAutoapprovehar; "AutoApproveHardeningClaims"
0x18001278f  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180012796  mov     [rsp+0D0h+pdwType], rdi; pdwType
0x18001279b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800127a2  call    cs:__imp_RegGetValueW
0x1800127a9  nop     dword ptr [rax+rax+00h]
0x1800127ae  lea     r9d, [rdi+1]
0x1800127b2  test    eax, eax
0x1800127b4  jnz     short loc_1800127C7
0x1800127b6  cmp     [rbp+57h+arg_8], edi
0x1800127b9  jnz     short loc_1800127C7
0x1800127bb  lea     rax, unk_180049430
0x1800127c2  mov     cl, dil
0x1800127c5  jmp     short loc_1800127D1
0x1800127c7  lea     rax, unk_1800472A0
0x1800127ce  mov     cl, r9b
0x1800127d1  movups  xmm0, xmmword ptr [rax]
0x1800127d4  mov     r8d, 2
0x1800127da  mov     [rbp+57h+var_48], r9d
0x1800127de  test    cl, cl
0x1800127e0  mov     [rbp+57h+var_20], r9d
0x1800127e4  lea     rdx, unk_1800472C0
0x1800127eb  mov     [rbp+57h+var_88], r9d
0x1800127ef  lea     rax, [rbp+57h+arg_18]
0x1800127f3  mov     [rbp+57h+var_50], r8w
0x1800127f8  mov     [rbp+57h+var_40], rax
0x1800127fc  lea     r9d, [r8+0Eh]; TokenInformationLength
0x180012800  movdqu  [rbp+57h+var_60], xmm0
0x180012805  mov     [rbp+57h+var_28], r8w
0x18001280a  lea     rax, asc_1800472B0; "\"$"
0x180012811  cmovz   rax, rdx
0x180012815  mov     [rbp+57h+var_84], r8d
0x180012819  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18001281d  mov     [rbp+57h+arg_18], rdi
0x180012821  lea     edx, [r9+17h]; TokenInformationClass
0x180012825  mov     [rbp+57h+var_4C], 0C0h
0x18001282c  mov     rcx, rbx; TokenHandle
0x18001282f  mov     [rbp+57h+var_24], 40h ; '@'
0x180012836  movups  xmm0, xmmword ptr [rax]
0x180012839  lea     rax, [rbp+57h+arg_18]
0x18001283d  mov     [rbp+57h+var_90], 4
0x180012844  mov     [rbp+57h+var_18], rax
0x180012848  lea     rax, [rbp+57h+var_60]
0x18001284c  mov     [rbp+57h+var_80], rax
0x180012850  lea     rax, [rbp+57h+var_88]
0x180012854  mov     [rbp+57h+TokenInformation], rax
0x180012858  lea     rax, [rbp+57h+var_90]
0x18001285c  mov     [rbp+57h+var_70], rax
0x180012860  movdqu  [rbp+57h+var_38], xmm0
0x180012865  mov     [rbp+57h+var_8C], 4
0x18001286c  call    cs:__imp_NtSetInformationToken
0x180012873  nop     dword ptr [rax+rax+00h]
0x180012878  add     rsp, 0C0h
0x18001287f  pop     rdi
0x180012880  pop     rbx
0x180012881  pop     rbp
0x180012882  retn
```
