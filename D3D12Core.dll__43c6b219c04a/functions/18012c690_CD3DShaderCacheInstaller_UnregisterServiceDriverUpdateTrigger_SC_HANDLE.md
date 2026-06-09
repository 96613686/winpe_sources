# CD3DShaderCacheInstaller::UnregisterServiceDriverUpdateTrigger(SC_HANDLE__ *)

- ea: `0x18012c690`
- end: `0x18012c89b`
- name: `?UnregisterServiceDriverUpdateTrigger@CD3DShaderCacheInstaller@@UEAAJPEAUSC_HANDLE__@@@Z`
- size: `523`
- prototype: `int(CD3DShaderCacheInstaller *__hidden this, struct SC_HANDLE__ *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b920`
- `0x18000bfd8`
- `0x1800bc088`
- `0x18012c690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c6d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c6d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012c842`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18012c6c7`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18012c73a`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18012c6c7`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfig2W` at `0x18012c73a`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18012c838`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x18012c838`

## pseudocode

```c
__int64 __fastcall CD3DShaderCacheInstaller::UnregisterServiceDriverUpdateTrigger(
        CD3DShaderCacheInstaller *this,
        SC_HANDLE a2)
{
  DWORD v3; // eax
  DWORD v4; // eax
  _QWORD *v6; // rbx
  unsigned int v7; // ecx
  __int64 v8; // rax
  char v9; // r8
  unsigned int v10; // ebp
  __int64 v11; // rsi
  __int64 v12; // rdi
  unsigned int v13; // edx
  unsigned int i; // r14d
  __int64 v15; // r9
  unsigned int v16; // ebx
  DWORD cbBufSize; // [rsp+70h] [rbp+18h] BYREF
  _QWORD *v18; // [rsp+78h] [rbp+20h] BYREF

  cbBufSize = 0;
  if ( QueryServiceConfig2W(a2, 8u, 0, 0, &cbBufSize) )
    goto LABEL_5;
  v3 = GetLastError() - 5;
  if ( !v3 )
    return 2147942405LL;
  v4 = v3 - 1;
  if ( !v4 )
    return 2147942487LL;
  if ( v4 == 116 )
  {
LABEL_5:
    if ( !cbBufSize )
      return 2289696770LL;
    v6 = operator new(cbBufSize);
    v18 = v6;
    if ( QueryServiceConfig2W(a2, 8u, (LPBYTE)v6, cbBufSize, &cbBufSize) )
    {
      v7 = *(_DWORD *)v6;
      if ( !*(_DWORD *)v6 )
        goto LABEL_27;
      v8 = WNF_DX_ADVANCED_SHADER_DELIVERY_CHANGE;
      v9 = 0;
      v10 = 0;
      do
      {
        v11 = v6[1];
        v12 = 32LL * v10;
        if ( *(_DWORD *)(v12 + v11) == 7 && *(_DWORD *)(v12 + v11 + 4) == 1 )
        {
          v13 = *(_DWORD *)(v12 + v11 + 16);
          if ( !v13 )
            goto LABEL_20;
          for ( i = 0; i < v13; ++i )
          {
            v15 = *(_QWORD *)(v12 + v11 + 24);
            if ( **(_QWORD **)(v15 + 16LL * i + 8) == v8 )
            {
              memmove_0((void *)(v15 + 16LL * i), (const void *)(v15 + 16LL * (i + 1)), 16LL * (v13 + ~i));
              --*(_DWORD *)(v12 + v11 + 16);
              v9 = 1;
              v13 = *(_DWORD *)(v12 + v11 + 16);
              --i;
              v8 = WNF_DX_ADVANCED_SHADER_DELIVERY_CHANGE;
            }
          }
          v11 = v6[1];
          v7 = *(_DWORD *)v6;
          if ( !v13 )
          {
LABEL_20:
            memmove_0((void *)(v12 + v11), (const void *)(v11 + 32LL * (v10 + 1)), 32LL * (v7 + ~v10));
            --*(_DWORD *)v6;
            v9 = 1;
            v7 = *(_DWORD *)v6;
            --v10;
            v8 = WNF_DX_ADVANCED_SHADER_DELIVERY_CHANGE;
          }
        }
        ++v10;
      }
      while ( v10 < v7 );
      if ( !v9 )
      {
LABEL_27:
        v16 = -2005270526;
        goto LABEL_28;
      }
      if ( ChangeServiceConfig2W(a2, 8u, v6) )
      {
        Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(&v18);
        return 0;
      }
      if ( GetLastError() == 5 )
      {
        v16 = -2147024891;
LABEL_28:
        Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(&v18);
        return v16;
      }
    }
    Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(&v18);
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18012c690  mov     rax, rsp
0x18012c693  mov     [rax+8], rbx
0x18012c697  mov     [rax+10h], rbp
0x18012c69b  push    rsi
0x18012c69c  push    rdi
0x18012c69d  push    r13
0x18012c69f  push    r14
0x18012c6a1  push    r15
0x18012c6a3  sub     rsp, 30h
0x18012c6a7  mov     r15, rdx
0x18012c6aa  mov     dword ptr [rax+18h], 0
0x18012c6b1  xor     r9d, r9d; cbBufSize
0x18012c6b4  lea     rax, [rax+18h]
0x18012c6b8  xor     r8d, r8d; lpBuffer
0x18012c6bb  mov     [rsp+58h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18012c6c0  mov     rcx, r15; hService
0x18012c6c3  lea     edx, [r9+8]; dwInfoLevel
0x18012c6c7  call    cs:__imp_QueryServiceConfig2W
0x18012c6cd  test    eax, eax
0x18012c6cf  jnz     short loc_18012C6EA
0x18012c6d1  call    cs:__imp_GetLastError
0x18012c6d7  sub     eax, 5
0x18012c6da  jz      short loc_18012C706
0x18012c6dc  sub     eax, 1
0x18012c6df  jz      short loc_18012C6FC
0x18012c6e1  cmp     eax, 74h ; 't'
0x18012c6e4  jnz     loc_18012C87F
0x18012c6ea  mov     eax, [rsp+58h+cbBufSize]
0x18012c6ee  test    eax, eax
0x18012c6f0  jnz     short loc_18012C710
0x18012c6f2  mov     eax, 887A0002h
0x18012c6f7  jmp     loc_18012C884
0x18012c6fc  mov     eax, 80070057h
0x18012c701  jmp     loc_18012C884
0x18012c706  mov     eax, 80070005h
0x18012c70b  jmp     loc_18012C884
0x18012c710  mov     rcx, rax; dwBytes
0x18012c713  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012c718  mov     r9d, [rsp+58h+cbBufSize]; cbBufSize
0x18012c71d  mov     rbx, rax
0x18012c720  mov     [rsp+58h+arg_18], rax
0x18012c725  mov     r8, rbx; lpBuffer
0x18012c728  lea     rax, [rsp+58h+cbBufSize]
0x18012c72d  mov     edx, 8; dwInfoLevel
0x18012c732  mov     rcx, r15; hService
0x18012c735  mov     [rsp+58h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18012c73a  call    cs:__imp_QueryServiceConfig2W
0x18012c740  test    eax, eax
0x18012c742  jz      loc_18012C875
0x18012c748  mov     ecx, [rbx]
0x18012c74a  test    ecx, ecx
0x18012c74c  jz      loc_18012C862
0x18012c752  mov     rax, cs:WNF_DX_ADVANCED_SHADER_DELIVERY_CHANGE
0x18012c759  xor     r8b, r8b
0x18012c75c  xor     ebp, ebp
0x18012c75e  or      r13d, 0FFFFFFFFh
0x18012c762  mov     rsi, [rbx+8]
0x18012c766  mov     edi, ebp
0x18012c768  shl     rdi, 5
0x18012c76c  cmp     dword ptr [rdi+rsi], 7
0x18012c770  jnz     loc_18012C81E
0x18012c776  cmp     dword ptr [rdi+rsi+4], 1
0x18012c77b  jnz     loc_18012C81E
0x18012c781  mov     edx, [rdi+rsi+10h]
0x18012c785  test    edx, edx
0x18012c787  jz      short loc_18012C7EC
0x18012c789  xor     r14d, r14d
0x18012c78c  mov     r9, [rdi+rsi+18h]
0x18012c791  mov     r10d, r14d
0x18012c794  shl     r10, 4
0x18012c798  add     r10, r9
0x18012c79b  mov     rcx, [r10+8]
0x18012c79f  cmp     [rcx], rax
0x18012c7a2  jnz     short loc_18012C7DA
0x18012c7a4  mov     r8d, r14d
0x18012c7a7  mov     rcx, r10; void *
0x18012c7aa  not     r8d
0x18012c7ad  add     r8d, edx
0x18012c7b0  lea     edx, [r14+1]
0x18012c7b4  shl     rdx, 4
0x18012c7b8  add     rdx, r9; Src
0x18012c7bb  shl     r8, 4; Size
0x18012c7bf  call    memmove_0
0x18012c7c4  add     [rdi+rsi+10h], r13d
0x18012c7c9  mov     r8b, 1
0x18012c7cc  mov     edx, [rdi+rsi+10h]
0x18012c7d0  add     r14d, r13d
0x18012c7d3  mov     rax, cs:WNF_DX_ADVANCED_SHADER_DELIVERY_CHANGE
0x18012c7da  inc     r14d
0x18012c7dd  cmp     r14d, edx
0x18012c7e0  jb      short loc_18012C78C
0x18012c7e2  mov     rsi, [rbx+8]
0x18012c7e6  mov     ecx, [rbx]
0x18012c7e8  test    edx, edx
0x18012c7ea  jnz     short loc_18012C81E
0x18012c7ec  mov     r8d, ebp
0x18012c7ef  lea     edx, [rbp+1]
0x18012c7f2  not     r8d
0x18012c7f5  shl     rdx, 5
0x18012c7f9  add     r8d, ecx
0x18012c7fc  add     rdx, rsi; Src
0x18012c7ff  shl     r8, 5; Size
0x18012c803  lea     rcx, [rdi+rsi]; void *
0x18012c807  call    memmove_0
0x18012c80c  add     [rbx], r13d
0x18012c80f  mov     r8b, 1
0x18012c812  mov     ecx, [rbx]
0x18012c814  add     ebp, r13d
0x18012c817  mov     rax, cs:WNF_DX_ADVANCED_SHADER_DELIVERY_CHANGE
0x18012c81e  inc     ebp
0x18012c820  cmp     ebp, ecx
0x18012c822  jb      loc_18012C762
0x18012c828  test    r8b, r8b
0x18012c82b  jz      short loc_18012C862
0x18012c82d  mov     r8, rbx; lpInfo
0x18012c830  mov     edx, 8; dwInfoLevel
0x18012c835  mov     rcx, r15; hService
0x18012c838  call    cs:__imp_ChangeServiceConfig2W
0x18012c83e  test    eax, eax
0x18012c840  jnz     short loc_18012C854
0x18012c842  call    cs:__imp_GetLastError
0x18012c848  cmp     eax, 5
0x18012c84b  jnz     short loc_18012C875
0x18012c84d  mov     ebx, 80070005h
0x18012c852  jmp     short loc_18012C867
0x18012c854  lea     rcx, [rsp+58h+arg_18]
0x18012c859  call    ??1?$MakeAllocator@UCD3DShaderCacheInstallerFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(void)
0x18012c85e  xor     eax, eax
0x18012c860  jmp     short loc_18012C884
0x18012c862  mov     ebx, 887A0002h
0x18012c867  lea     rcx, [rsp+58h+arg_18]
0x18012c86c  call    ??1?$MakeAllocator@UCD3DShaderCacheInstallerFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(void)
0x18012c871  mov     eax, ebx
0x18012c873  jmp     short loc_18012C884
0x18012c875  lea     rcx, [rsp+58h+arg_18]
0x18012c87a  call    ??1?$MakeAllocator@UCD3DShaderCacheInstallerFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CD3DShaderCacheInstallerFactory>::~MakeAllocator<CD3DShaderCacheInstallerFactory>(void)
0x18012c87f  mov     eax, 80004005h
0x18012c884  mov     rbx, [rsp+58h+arg_0]
0x18012c889  mov     rbp, [rsp+58h+arg_8]
0x18012c88e  add     rsp, 30h
0x18012c892  pop     r15
0x18012c894  pop     r14
0x18012c896  pop     r13
0x18012c898  pop     rdi
0x18012c899  pop     rsi
0x18012c89a  retn
```
