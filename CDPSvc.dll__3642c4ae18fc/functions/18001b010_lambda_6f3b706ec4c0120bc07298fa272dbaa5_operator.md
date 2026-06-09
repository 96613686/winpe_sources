# _lambda_6f3b706ec4c0120bc07298fa272dbaa5_::operator()

- ea: `0x18001b010`
- end: `0x18001b10f`
- name: `_lambda_6f3b706ec4c0120bc07298fa272dbaa5_::operator()`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002ae40`

## callees

- `0x18001b010`
- `0x18001b118`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18001b0db`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18001b0db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b0ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b0ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b0c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b0ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b0c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b0ca`

## pseudocode

```c
__int64 __fastcall lambda_6f3b706ec4c0120bc07298fa272dbaa5_::operator()(__int64 a1, _OWORD *a2)
{
  SIZE_T v4; // rcx
  void *v5; // rax
  void *v6; // r12
  const char *v7; // r14
  __int64 v8; // rax
  rsize_t v9; // r15
  char *v10; // rax
  char *v11; // rbx
  unsigned int v12; // ebx
  __int128 v14; // [rsp+20h] [rbp-30h]
  __int128 v15; // [rsp+30h] [rbp-20h]
  LPVOID pv[2]; // [rsp+40h] [rbp-10h]

  DWORD1(v15) = 0;
  DWORD1(v14) = 0;
  LODWORD(v14) = **(_DWORD **)a1;
  pv[0] = 0;
  v4 = **(unsigned int **)(a1 + 8);
  LODWORD(v15) = v4;
  *((_QWORD *)&v15 + 1) = **(_QWORD **)(a1 + 16);
  v5 = CoTaskMemAlloc(v4);
  *((_QWORD *)&v14 + 1) = v5;
  v6 = v5;
  if ( !v5 )
    goto LABEL_6;
  std::_Copy_memmove<std::pair<enum CDPComDeviceTypes,CDPComDeviceResult> * *,std::pair<enum CDPComDeviceTypes,CDPComDeviceResult> * *>(
    **(void ***)(a1 + 24),
    **(_QWORD **)(a1 + 24) + **(unsigned int **)(a1 + 8),
    v5);
  pv[1] = 0;
  v7 = **(const char ***)(a1 + 32);
  if ( !v7 )
  {
LABEL_8:
    v12 = 0;
    *a2 = v14;
    a2[1] = v15;
    a2[2] = *(_OWORD *)pv;
    return v12;
  }
  v8 = -1;
  do
    ++v8;
  while ( v7[v8] );
  v9 = v8 + 1;
  v10 = (char *)CoTaskMemAlloc(v8 + 1);
  v11 = v10;
  if ( v10 )
  {
    strcpy_s(v10, v9, v7);
    pv[1] = v11;
    goto LABEL_8;
  }
LABEL_6:
  v12 = -2147024882;
  CoTaskMemFree(v6);
  CoTaskMemFree(0);
  return v12;
}

```

## disassembly

```asm
0x18001b010  push    rbp
0x18001b012  push    rbx
0x18001b013  push    rsi
0x18001b014  push    rdi
0x18001b015  push    r12
0x18001b017  push    r14
0x18001b019  push    r15
0x18001b01b  mov     rbp, rsp
0x18001b01e  sub     rsp, 50h
0x18001b022  mov     rax, [rcx]
0x18001b025  xorps   xmm0, xmm0
0x18001b028  mov     rbx, rcx
0x18001b02b  mov     rsi, rdx
0x18001b02e  movups  [rbp+var_20], xmm0
0x18001b032  mov     r8d, [rax]
0x18001b035  mov     rax, [rcx+8]
0x18001b039  movups  [rbp+var_30], xmm0
0x18001b03d  mov     dword ptr [rbp+var_30], r8d
0x18001b041  movups  xmmword ptr [rbp+pv], xmm0
0x18001b045  mov     ecx, [rax]; cb
0x18001b047  mov     rax, [rbx+10h]
0x18001b04b  mov     dword ptr [rbp+var_20], ecx
0x18001b04e  mov     rdx, [rax]
0x18001b051  mov     qword ptr [rbp+var_20+8], rdx
0x18001b055  call    cs:__imp_CoTaskMemAlloc
0x18001b05b  mov     qword ptr [rbp+var_30+8], rax
0x18001b05f  mov     r12, rax
0x18001b062  test    rax, rax
0x18001b065  jnz     short loc_18001B06D
0x18001b067  mov     rdi, [rbp+pv+8]
0x18001b06b  jmp     short loc_18001B0B9
0x18001b06d  mov     rax, [rbx+18h]
0x18001b071  mov     r8, r12
0x18001b074  mov     rcx, [rax]; Src
0x18001b077  mov     rax, [rbx+8]
0x18001b07b  mov     edx, [rax]
0x18001b07d  add     rdx, rcx
0x18001b080  call    ??$_Copy_memmove@PEAPEAU?$pair@W4CDPComDeviceTypes@@UCDPComDeviceResult@@@std@@PEAPEAU12@@std@@YAPEAPEAU?$pair@W4CDPComDeviceTypes@@UCDPComDeviceResult@@@0@PEAPEAU10@00@Z; std::_Copy_memmove<std::pair<CDPComDeviceTypes,CDPComDeviceResult> * *,std::pair<CDPComDeviceTypes,CDPComDeviceResult> * *>(std::pair<CDPComDeviceTypes,CDPComDeviceResult> * *,std::pair<CDPComDeviceTypes,CDPComDeviceResult> * *,std::pair<CDPComDeviceTypes,CDPComDeviceResult> * *)
0x18001b085  mov     rax, [rbx+20h]
0x18001b089  xor     edi, edi
0x18001b08b  mov     [rbp+pv+8], rdi
0x18001b08f  mov     r14, [rax]
0x18001b092  test    r14, r14
0x18001b095  jz      short loc_18001B0E5
0x18001b097  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b09b  inc     rax
0x18001b09e  cmp     [r14+rax], dil
0x18001b0a2  jnz     short loc_18001B09B
0x18001b0a4  lea     r15, [rax+1]
0x18001b0a8  mov     rcx, r15; cb
0x18001b0ab  call    cs:__imp_CoTaskMemAlloc
0x18001b0b1  mov     rbx, rax
0x18001b0b4  test    rax, rax
0x18001b0b7  jnz     short loc_18001B0D2
0x18001b0b9  mov     rcx, r12; pv
0x18001b0bc  mov     ebx, 8007000Eh
0x18001b0c1  call    cs:__imp_CoTaskMemFree
0x18001b0c7  mov     rcx, rdi; pv
0x18001b0ca  call    cs:__imp_CoTaskMemFree
0x18001b0d0  jmp     short loc_18001B0FE
0x18001b0d2  mov     r8, r14; Source
0x18001b0d5  mov     rdx, r15; SizeInBytes
0x18001b0d8  mov     rcx, rbx; Destination
0x18001b0db  call    cs:__imp_strcpy_s
0x18001b0e1  mov     [rbp+pv+8], rbx
0x18001b0e5  movups  xmm0, [rbp+var_30]
0x18001b0e9  xor     ebx, ebx
0x18001b0eb  movups  xmm1, [rbp+var_20]
0x18001b0ef  movups  xmmword ptr [rsi], xmm0
0x18001b0f2  movups  xmm0, xmmword ptr [rbp+pv]
0x18001b0f6  movups  xmmword ptr [rsi+10h], xmm1
0x18001b0fa  movups  xmmword ptr [rsi+20h], xmm0
0x18001b0fe  mov     eax, ebx
0x18001b100  add     rsp, 50h
0x18001b104  pop     r15
0x18001b106  pop     r14
0x18001b108  pop     r12
0x18001b10a  pop     rdi
0x18001b10b  pop     rsi
0x18001b10c  pop     rbx
0x18001b10d  pop     rbp
0x18001b10e  retn
```
