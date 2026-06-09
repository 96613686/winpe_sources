# CD3DShaderCacheInstaller::RegisterServiceDriverUpdateTrigger(SC_HANDLE__ *)

- ea: `0x18012c170`
- end: `0x18012c382`
- name: `?RegisterServiceDriverUpdateTrigger@CD3DShaderCacheInstaller@@UEAAJPEAUSC_HANDLE__@@@Z`
- size: `530`
- prototype: `int(CD3DShaderCacheInstaller *__hidden this, struct SC_HANDLE__ *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b920`
- `0x18000bfd8`
- `0x1800bb480`
- `0x18012c170`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c1ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c337`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c1ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c337`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18012c1b0`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18012c225`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18012c1b0`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18012c225`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18012c32d`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18012c32d`

## pseudocode

```c
__int64 __fastcall CD3DShaderCacheInstaller::RegisterServiceDriverUpdateTrigger(
        CD3DShaderCacheInstaller *this,
        SC_HANDLE a2)
{
  DWORD v3; // eax
  DWORD v4; // eax
  DWORD v6; // eax
  BYTE *v7; // rax
  BYTE *v8; // rbx
  __int64 v9; // r8
  unsigned int v10; // edx
  __int64 v11; // rcx
  unsigned int v12; // r10d
  unsigned int v13; // r9d
  unsigned int v14; // ebx
  DWORD cbBufSize; // [rsp+30h] [rbp-40h] BYREF
  BYTE *v16; // [rsp+38h] [rbp-38h] BYREF
  _DWORD v17[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 *v18; // [rsp+48h] [rbp-28h]
  __int64 v19; // [rsp+50h] [rbp-20h] BYREF
  GUID v20; // [rsp+58h] [rbp-18h] BYREF

  cbBufSize = 0;
  if ( !QueryServiceConfig2W(a2, 8u, 0, 0, &cbBufSize) )
  {
    v3 = GetLastError() - 5;
    if ( !v3 )
      return 2147942405LL;
    v4 = v3 - 1;
    if ( !v4 )
      return 2147942487LL;
    if ( v4 != 116 )
      return 2147500037LL;
  }
  v6 = cbBufSize;
  if ( !cbBufSize )
    v6 = 24;
  v7 = (BYTE *)operator new(v6 + 32);
  v8 = v7;
  v16 = v7;
  if ( cbBufSize && !QueryServiceConfig2W(a2, 8u, v7, cbBufSize, &cbBufSize) )
    goto LABEL_25;
  if ( *(_DWORD *)v8 )
  {
    v9 = *((_QWORD *)v8 + 1);
    v10 = 0;
    while ( 1 )
    {
      v11 = 32LL * v10;
      if ( *(_DWORD *)(v11 + v9) == 7 && *(_DWORD *)(v11 + v9 + 4) == 1 )
      {
        v12 = *(_DWORD *)(v11 + v9 + 16);
        if ( v12 )
          break;
      }
LABEL_20:
      if ( ++v10 >= *(_DWORD *)v8 )
        goto LABEL_21;
    }
    v13 = 0;
    while ( **(_QWORD **)(*(_QWORD *)(v11 + v9 + 24) + 16LL * v13 + 8) != WNF_DX_ADVANCED_SHADER_DELIVERY_CHANGE )
    {
      if ( ++v13 >= v12 )
        goto LABEL_20;
    }
    v14 = -2005270474;
    goto LABEL_29;
  }
LABEL_21:
  v19 = WNF_DX_ADVANCED_SHADER_DELIVERY_CHANGE;
  v18 = &v19;
  v20 = CUSTOM_SYSTEM_STATE_CHANGE_EVENT_GUID;
  v17[0] = 1;
  v17[1] = 8;
  if ( !*(_DWORD *)v8 )
    *((_QWORD *)v8 + 1) = v8 + 24;
  *(_DWORD *)(32LL * *(unsigned int *)v8 + *((_QWORD *)v8 + 1)) = 7;
  *(_DWORD *)(32LL * *(unsigned int *)v8 + *((_QWORD *)v8 + 1) + 4) = 1;
  *(_QWORD *)(32LL * *(unsigned int *)v8 + *((_QWORD *)v8 + 1) + 8) = &v20;
  *(_DWORD *)(32LL * *(unsigned int *)v8 + *((_QWORD *)v8 + 1) + 16) = 1;
  *(_QWORD *)(32LL * (unsigned int)(*(_DWORD *)v8)++ + *((_QWORD *)v8 + 1) + 24) = v17;
  if ( ChangeServiceConfig2W(a2, 8u, v8) )
  {
    v14 = 0;
    goto LABEL_29;
  }
  if ( GetLastError() == 5 )
    v14 = -2147024891;
  else
LABEL_25:
    v14 = -2147467259;
LABEL_29:
  Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(&v16);
  return v14;
}

```

## disassembly

```asm
0x18012c170  mov     [rsp-8+arg_0], rbx
0x18012c175  mov     [rsp-8+arg_10], rdi
0x18012c17a  push    rbp
0x18012c17b  mov     rbp, rsp
0x18012c17e  sub     rsp, 70h
0x18012c182  mov     rax, cs:__security_cookie
0x18012c189  xor     rax, rsp
0x18012c18c  mov     [rbp+var_8], rax
0x18012c190  mov     rdi, rdx
0x18012c193  mov     [rbp+cbBufSize], 0
0x18012c19a  xor     r9d, r9d; cbBufSize
0x18012c19d  lea     rax, [rbp+cbBufSize]
0x18012c1a1  xor     r8d, r8d; lpBuffer
0x18012c1a4  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18012c1a9  mov     rcx, rdi; hService
0x18012c1ac  lea     edx, [r9+8]; dwInfoLevel
0x18012c1b0  call    cs:__imp_QueryServiceConfig2W
0x18012c1b6  test    eax, eax
0x18012c1b8  jnz     short loc_18012C1ED
0x18012c1ba  call    cs:__imp_GetLastError
0x18012c1c0  sub     eax, 5
0x18012c1c3  jz      short loc_18012C1E3
0x18012c1c5  sub     eax, 1
0x18012c1c8  jz      short loc_18012C1D9
0x18012c1ca  cmp     eax, 74h ; 't'
0x18012c1cd  jz      short loc_18012C1ED
0x18012c1cf  mov     eax, 80004005h
0x18012c1d4  jmp     loc_18012C364
0x18012c1d9  mov     eax, 80070057h
0x18012c1de  jmp     loc_18012C364
0x18012c1e3  mov     eax, 80070005h
0x18012c1e8  jmp     loc_18012C364
0x18012c1ed  mov     eax, [rbp+cbBufSize]
0x18012c1f0  test    eax, eax
0x18012c1f2  jnz     short loc_18012C1F9
0x18012c1f4  mov     eax, 18h
0x18012c1f9  lea     ecx, [rax+20h]; dwBytes
0x18012c1fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012c201  mov     r9d, [rbp+cbBufSize]; cbBufSize
0x18012c205  mov     rbx, rax
0x18012c208  mov     [rbp+var_38], rax
0x18012c20c  test    r9d, r9d
0x18012c20f  jz      short loc_18012C233
0x18012c211  lea     rax, [rbp+cbBufSize]
0x18012c215  mov     r8, rbx; lpBuffer
0x18012c218  mov     edx, 8; dwInfoLevel
0x18012c21d  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18012c222  mov     rcx, rdi; hService
0x18012c225  call    cs:__imp_QueryServiceConfig2W
0x18012c22b  test    eax, eax
0x18012c22d  jz      loc_18012C342
0x18012c233  cmp     dword ptr [rbx], 0
0x18012c236  mov     rax, cs:WNF_DX_ADVANCED_SHADER_DELIVERY_CHANGE
0x18012c23d  jbe     short loc_18012C28E
0x18012c23f  mov     r8, [rbx+8]
0x18012c243  xor     edx, edx
0x18012c245  mov     ecx, edx
0x18012c247  shl     rcx, 5
0x18012c24b  cmp     dword ptr [rcx+r8], 7
0x18012c250  jnz     short loc_18012C288
0x18012c252  cmp     dword ptr [rcx+r8+4], 1
0x18012c258  jnz     short loc_18012C288
0x18012c25a  mov     r10d, [rcx+r8+10h]
0x18012c25f  test    r10d, r10d
0x18012c262  jz      short loc_18012C288
0x18012c264  mov     r11, [rcx+r8+18h]
0x18012c269  xor     r9d, r9d
0x18012c26c  mov     ecx, r9d
0x18012c26f  add     rcx, rcx
0x18012c272  mov     rcx, [r11+rcx*8+8]
0x18012c277  cmp     [rcx], rax
0x18012c27a  jz      loc_18012C349
0x18012c280  inc     r9d
0x18012c283  cmp     r9d, r10d
0x18012c286  jb      short loc_18012C26C
0x18012c288  inc     edx
0x18012c28a  cmp     edx, [rbx]
0x18012c28c  jb      short loc_18012C245
0x18012c28e  movups  xmm0, xmmword ptr cs:CUSTOM_SYSTEM_STATE_CHANGE_EVENT_GUID.Data1
0x18012c295  mov     [rbp+var_20], rax
0x18012c299  lea     rax, [rbp+var_20]
0x18012c29d  mov     [rbp+var_28], rax
0x18012c2a1  movdqu  [rbp+var_18], xmm0
0x18012c2a6  mov     [rbp+var_30], 1
0x18012c2ad  mov     [rbp+var_2C], 8
0x18012c2b4  cmp     dword ptr [rbx], 0
0x18012c2b7  jnz     short loc_18012C2C1
0x18012c2b9  lea     rax, [rbx+18h]
0x18012c2bd  mov     [rbx+8], rax
0x18012c2c1  mov     ecx, [rbx]
0x18012c2c3  mov     edx, 8; dwInfoLevel
0x18012c2c8  mov     rax, [rbx+8]
0x18012c2cc  shl     rcx, 5
0x18012c2d0  mov     dword ptr [rcx+rax], 7
0x18012c2d7  mov     ecx, [rbx]
0x18012c2d9  mov     rax, [rbx+8]
0x18012c2dd  shl     rcx, 5
0x18012c2e1  mov     dword ptr [rcx+rax+4], 1
0x18012c2e9  lea     rcx, [rbp+var_18]
0x18012c2ed  mov     r8d, [rbx]
0x18012c2f0  mov     rax, [rbx+8]
0x18012c2f4  shl     r8, 5
0x18012c2f8  mov     [r8+rax+8], rcx
0x18012c2fd  lea     rcx, [rbp+var_30]
0x18012c301  mov     r8d, [rbx]
0x18012c304  mov     rax, [rbx+8]
0x18012c308  shl     r8, 5
0x18012c30c  mov     dword ptr [r8+rax+10h], 1
0x18012c315  mov     r8d, [rbx]
0x18012c318  mov     rax, [rbx+8]
0x18012c31c  shl     r8, 5
0x18012c320  mov     [r8+rax+18h], rcx
0x18012c325  mov     r8, rbx; lpInfo
0x18012c328  inc     dword ptr [rbx]
0x18012c32a  mov     rcx, rdi; hService
0x18012c32d  call    cs:__imp_ChangeServiceConfig2W
0x18012c333  test    eax, eax
0x18012c335  jnz     short loc_18012C357
0x18012c337  call    cs:__imp_GetLastError
0x18012c33d  cmp     eax, 5
0x18012c340  jz      short loc_18012C350
0x18012c342  mov     ebx, 80004005h
0x18012c347  jmp     short loc_18012C359
0x18012c349  mov     ebx, 887A0036h
0x18012c34e  jmp     short loc_18012C359
0x18012c350  mov     ebx, 80070005h
0x18012c355  jmp     short loc_18012C359
0x18012c357  xor     ebx, ebx
0x18012c359  lea     rcx, [rbp+var_38]
0x18012c35d  call    ??1?$MakeAllocator@UCD3DShaderCacheInstallerFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(void)
0x18012c362  mov     eax, ebx
0x18012c364  mov     rcx, [rbp+var_8]
0x18012c368  xor     rcx, rsp; StackCookie
0x18012c36b  call    __security_check_cookie
0x18012c370  lea     r11, [rsp+70h+var_s0]
0x18012c375  mov     rbx, [r11+10h]
0x18012c379  mov     rdi, [r11+20h]
0x18012c37d  mov     rsp, r11
0x18012c380  pop     rbp
0x18012c381  retn
```
