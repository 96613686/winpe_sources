# DllGetClassObject

- ea: `0x180056420`
- end: `0x1800564e6`
- name: `DllGetClassObject`
- size: `198`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180056420`
- `0x180056c10`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800564c7`
- `RPCRT4!NdrDllGetClassObject` at `0x1800564c7`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  char v6; // r8
  unsigned int v7; // ebx
  HRESULT v8; // r9d
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  __int64 v11; // rax

  if ( !ppv )
    return -2147024809;
  v6 = 0;
  v7 = 0;
  v8 = -2147221231;
  do
  {
    if ( v6 )
      break;
    v9 = 56LL * (int)v7;
    v10 = *(__int64 (**)[2])((char *)&off_180106110 + v9);
    v11 = *(_QWORD *)&rclsid->Data1 - *v10;
    if ( *(_QWORD *)&rclsid->Data1 == *v10 )
      v11 = *(_QWORD *)rclsid->Data4 - v10[1];
    if ( !v11 )
    {
      v8 = sub_180056C10(
             *(__int64 (**)[2])((char *)&off_180106110 + v9 + 32),
             *(__int64 (**)[2])((char *)&off_180106110 + v9 + 48),
             riid,
             ppv);
      v6 = 1;
    }
    ++v7;
  }
  while ( v7 < 0x11 );
  if ( v8 == -2147221231 )
    return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&pProxyFileList, &pclsid, &pPSFactoryBuffer);
  return v8;
}

```

## disassembly

```asm
0x180056420  push    rbx
0x180056422  push    rbp
0x180056423  push    rsi
0x180056424  push    rdi
0x180056425  push    r15
0x180056427  sub     rsp, 30h
0x18005642b  mov     rdi, r8
0x18005642e  mov     rbp, rdx
0x180056431  mov     rsi, rcx
0x180056434  test    r8, r8
0x180056437  jz      loc_1800564D2
0x18005643d  xor     r8b, r8b
0x180056440  lea     r15, off_180106110
0x180056447  xor     ebx, ebx
0x180056449  mov     r9d, 80040111h
0x18005644f  test    r8b, r8b
0x180056452  jnz     short loc_180056496
0x180056454  movsxd  rax, ebx
0x180056457  imul    rcx, rax, 38h ; '8'
0x18005645b  mov     rax, [rsi]
0x18005645e  mov     rdx, [rcx+r15]
0x180056462  sub     rax, [rdx]
0x180056465  jnz     short loc_18005646F
0x180056467  mov     rax, [rsi+8]
0x18005646b  sub     rax, [rdx+8]
0x18005646f  test    rax, rax
0x180056472  jnz     short loc_18005648F
0x180056474  mov     rdx, [rcx+r15+30h]
0x180056479  mov     r9, rdi
0x18005647c  mov     rcx, [rcx+r15+20h]
0x180056481  mov     r8, rbp
0x180056484  call    sub_180056C10
0x180056489  mov     r9d, eax
0x18005648c  mov     r8b, 1
0x18005648f  inc     ebx
0x180056491  cmp     ebx, 11h
0x180056494  jb      short loc_18005644F
0x180056496  cmp     r9d, 80040111h
0x18005649d  jnz     short loc_1800564D8
0x18005649f  lea     rax, pPSFactoryBuffer
0x1800564a6  mov     r8, rdi; ppv
0x1800564a9  mov     [rsp+58h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x1800564ae  lea     r9, pProxyFileList; pProxyFileList
0x1800564b5  lea     rax, pclsid
0x1800564bc  mov     rdx, rbp; riid
0x1800564bf  mov     rcx, rsi; rclsid
0x1800564c2  mov     [rsp+58h+pclsid], rax; pclsid
0x1800564c7  call    cs:NdrDllGetClassObject
0x1800564cd  mov     r9d, eax
0x1800564d0  jmp     short loc_1800564D8
0x1800564d2  mov     r9d, 80070057h
0x1800564d8  mov     eax, r9d
0x1800564db  add     rsp, 30h
0x1800564df  pop     r15
0x1800564e1  pop     rdi
0x1800564e2  pop     rsi
0x1800564e3  pop     rbp
0x1800564e4  pop     rbx
0x1800564e5  retn
```
