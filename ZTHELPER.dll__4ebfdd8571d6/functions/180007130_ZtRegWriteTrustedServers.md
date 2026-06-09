# ZtRegWriteTrustedServers

- ea: `0x180007130`
- end: `0x1800072aa`
- name: `ZtRegWriteTrustedServers`
- size: `378`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int64, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180005134`

## callees

- `0x180006940`
- `0x180007130`
- `0x18000cdd8`
- `0x180015008`
- `0x1800152b0`
- `0x180015618`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007295`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007295`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x1800071db`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x1800071db`

## pseudocode

```c
__int64 __fastcall ZtRegWriteTrustedServers(unsigned int a1, __int64 a2, __int64 a3, HKEY a4)
{
  int Key; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // r8
  unsigned int v12; // edi
  USHORT v13; // dx
  HKEY hKey[9]; // [rsp+50h] [rbp-48h] BYREF

  hKey[0] = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_dq(1026, 0x37u, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, a1, a2);
  Key = DnsRegDeleteTree(a4, L"ZtTrustedServers");
  v9 = Key;
  if ( Key )
  {
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_21;
    v13 = 56;
    goto LABEL_18;
  }
  if ( !a2 )
    goto LABEL_19;
  Key = RegCreateKeyExInternalW(a4, L"ZtTrustedServers", 0, 0, 0, 196639, 0, hKey, 0, a3);
  v9 = Key;
  if ( Key )
  {
    if ( (xmmword_18001F260 & 4) == 0 )
      goto LABEL_21;
    v13 = 57;
    goto LABEL_18;
  }
  v12 = 0;
  if ( !a1 )
    goto LABEL_19;
  while ( 1 )
  {
    if ( (xmmword_18001F260 & 4) != 0 )
      WPP_SF__SOCKADDR_(v10, 58, v11, a2 + ((unsigned __int64)v12 << 6) + 16);
    Key = ZtSetTrustedServer(a2 + ((unsigned __int64)v12 << 6), (__int64)hKey[0], a3);
    v9 = Key;
    if ( Key )
      break;
    if ( ++v12 >= a1 )
      goto LABEL_19;
  }
  if ( (xmmword_18001F260 & 4) != 0 )
  {
    v13 = 59;
LABEL_18:
    WPP_SF_d(1026, v13, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, Key);
LABEL_19:
    if ( (xmmword_18001F260 & 4) != 0 )
      WPP_SF_d(1026, 0x3Cu, (ULONGLONG)WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids, v9);
  }
LABEL_21:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v9;
}

```

## disassembly

```asm
0x180007130  push    rbx
0x180007132  push    rbp
0x180007133  push    rsi
0x180007134  push    rdi
0x180007135  push    r13
0x180007137  push    r14
0x180007139  sub     rsp, 68h
0x18000713d  mov     rdi, r9
0x180007140  mov     [rsp+98h+hKey], 0
0x180007149  mov     r14, r8
0x18000714c  mov     rbp, rdx
0x18000714f  mov     esi, ecx
0x180007151  test    byte ptr cs:xmmword_18001F260, 4
0x180007158  mov     r13d, 402h
0x18000715e  jz      short loc_18000717C
0x180007160  mov     edx, 37h ; '7'
0x180007165  mov     [rsp+98h+var_78], rbp
0x18000716a  mov     ecx, r13d
0x18000716d  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x180007174  mov     r9d, esi
0x180007177  call    WPP_SF_dq
0x18000717c  lea     rdx, aZttrustedserve; "ZtTrustedServers"
0x180007183  mov     rcx, rdi; hKey
0x180007186  call    DnsRegDeleteTree
0x18000718b  mov     ebx, eax
0x18000718d  test    eax, eax
0x18000718f  jnz     loc_18000724B
0x180007195  test    rbp, rbp
0x180007198  jz      loc_18000726B
0x18000719e  mov     [rsp+98h+var_50], r14
0x1800071a3  lea     rax, [rsp+98h+hKey]
0x1800071a8  mov     [rsp+98h+var_58], 0
0x1800071b1  lea     rdx, aZttrustedserve; "ZtTrustedServers"
0x1800071b8  mov     [rsp+98h+var_60], rax
0x1800071bd  xor     r9d, r9d
0x1800071c0  mov     [rsp+98h+var_68], 0
0x1800071c9  xor     r8d, r8d
0x1800071cc  mov     [rsp+98h+var_70], 3001Fh
0x1800071d4  mov     rcx, rdi
0x1800071d7  mov     dword ptr [rsp+98h+var_78], ebx
0x1800071db  call    cs:__imp_RegCreateKeyExInternalW
0x1800071e1  mov     ebx, eax
0x1800071e3  test    eax, eax
0x1800071e5  jnz     short loc_18000723B
0x1800071e7  xor     edi, edi
0x1800071e9  test    esi, esi
0x1800071eb  jz      short loc_18000726B
0x1800071ed  mov     ebx, edi
0x1800071ef  shl     rbx, 6
0x1800071f3  add     rbx, rbp
0x1800071f6  test    byte ptr cs:xmmword_18001F260, 4
0x1800071fd  jz      short loc_18000720D
0x1800071ff  lea     r9, [rbx+10h]
0x180007203  mov     edx, 3Ah ; ':'
0x180007208  call    WPP_SF__SOCKADDR_
0x18000720d  mov     rdx, [rsp+98h+hKey]
0x180007212  mov     r8, r14
0x180007215  mov     rcx, rbx
0x180007218  call    ZtSetTrustedServer
0x18000721d  mov     ebx, eax
0x18000721f  test    eax, eax
0x180007221  jnz     short loc_18000722B
0x180007223  inc     edi
0x180007225  cmp     edi, esi
0x180007227  jb      short loc_1800071ED
0x180007229  jmp     short loc_18000726B
0x18000722b  test    byte ptr cs:xmmword_18001F260, 4
0x180007232  jz      short loc_18000728B
0x180007234  mov     edx, 3Bh ; ';'
0x180007239  jmp     short loc_180007259
0x18000723b  test    byte ptr cs:xmmword_18001F260, 4
0x180007242  jz      short loc_18000728B
0x180007244  mov     edx, 39h ; '9'
0x180007249  jmp     short loc_180007259
0x18000724b  test    byte ptr cs:xmmword_18001F260, 4
0x180007252  jz      short loc_18000728B
0x180007254  mov     edx, 38h ; '8'
0x180007259  mov     r9d, eax
0x18000725c  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x180007263  mov     ecx, r13d
0x180007266  call    WPP_SF_d
0x18000726b  test    byte ptr cs:xmmword_18001F260, 4
0x180007272  jz      short loc_18000728B
0x180007274  mov     edx, 3Ch ; '<'
0x180007279  lea     r8, WPP_dff83a7d5ad539b51697dc88a001ac55_Traceguids
0x180007280  mov     ecx, r13d
0x180007283  mov     r9d, ebx
0x180007286  call    WPP_SF_d
0x18000728b  mov     rcx, [rsp+98h+hKey]; hKey
0x180007290  test    rcx, rcx
0x180007293  jz      short loc_18000729B
0x180007295  call    cs:__imp_RegCloseKey
0x18000729b  mov     eax, ebx
0x18000729d  add     rsp, 68h
0x1800072a1  pop     r14
0x1800072a3  pop     r13
0x1800072a5  pop     rdi
0x1800072a6  pop     rsi
0x1800072a7  pop     rbp
0x1800072a8  pop     rbx
0x1800072a9  retn
```
