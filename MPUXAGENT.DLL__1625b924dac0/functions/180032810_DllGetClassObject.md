# DllGetClassObject

- ea: `0x180032810`
- end: `0x1800328eb`
- name: `DllGetClassObject`
- size: `219`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18003130c`
- `0x180032810`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x1800328bc`
- `RPCRT4!NdrDllGetClassObject` at `0x1800328bc`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  char v6; // r8
  wchar_t **v7; // rbx
  int v8; // esi
  HRESULT v9; // r9d
  _QWORD *v10; // rcx

  if ( !ppv )
    return -2147024809;
  v6 = 0;
  v7 = &off_180096EA0;
  v8 = 0;
  v9 = -2147221231;
  do
  {
    if ( v6 )
      break;
    v10 = *(v7 - 6);
    if ( *(_QWORD *)&rclsid->Data1 == *v10 && *(_QWORD *)rclsid->Data4 == v10[1] )
    {
      v9 = sub_18003130C(*(v7 - 2), *v7, riid, ppv);
      v6 = 1;
    }
    ++v8;
    v7 += 7;
  }
  while ( !v8 );
  if ( v9 == -2147221231 )
    return NdrDllGetClassObject(rclsid, riid, ppv, (const ProxyFileInfo **)&pProxyFileList, &pclsid, &pPSFactoryBuffer);
  return v9;
}

```

## disassembly

```asm
0x180032810  mov     rax, rsp
0x180032813  mov     [rax+8], rbx
0x180032817  mov     [rax+10h], rbp
0x18003281b  mov     [rax+18h], rsi
0x18003281f  mov     [rax+20h], rdi
0x180032823  push    r14
0x180032825  sub     rsp, 30h
0x180032829  mov     rdi, r8
0x18003282c  mov     rbp, rdx
0x18003282f  mov     r14, rcx
0x180032832  test    r8, r8
0x180032835  jz      loc_1800328C7
0x18003283b  xor     r8b, r8b
0x18003283e  lea     rbx, off_180096EA0; "O:BAG:BAD:(A;;0x3;;;SY)(A;;0x3;;;BA)(A;"...
0x180032845  xor     esi, esi
0x180032847  mov     r9d, 80040111h
0x18003284d  test    r8b, r8b
0x180032850  jnz     short loc_18003288B
0x180032852  mov     rcx, [rbx-30h]
0x180032856  mov     rax, [r14]
0x180032859  cmp     rax, [rcx]
0x18003285c  jnz     short loc_180032880
0x18003285e  mov     rax, [r14+8]
0x180032862  cmp     rax, [rcx+8]
0x180032866  jnz     short loc_180032880
0x180032868  mov     rdx, [rbx]
0x18003286b  mov     r9, rdi
0x18003286e  mov     rcx, [rbx-10h]
0x180032872  mov     r8, rbp
0x180032875  call    sub_18003130C
0x18003287a  mov     r9d, eax
0x18003287d  mov     r8b, 1
0x180032880  inc     esi
0x180032882  add     rbx, 38h ; '8'
0x180032886  cmp     esi, 1
0x180032889  jb      short loc_18003284D
0x18003288b  cmp     r9d, 80040111h
0x180032892  jnz     short loc_1800328CD
0x180032894  lea     rax, pPSFactoryBuffer
0x18003289b  mov     r8, rdi; ppv
0x18003289e  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x1800328a3  lea     r9, pProxyFileList; pProxyFileList
0x1800328aa  lea     rax, pclsid
0x1800328b1  mov     rdx, rbp; riid
0x1800328b4  mov     rcx, r14; rclsid
0x1800328b7  mov     [rsp+38h+pclsid], rax; pclsid
0x1800328bc  call    cs:NdrDllGetClassObject
0x1800328c2  mov     r9d, eax
0x1800328c5  jmp     short loc_1800328CD
0x1800328c7  mov     r9d, 80070057h
0x1800328cd  mov     rbx, [rsp+38h+arg_0]
0x1800328d2  mov     eax, r9d
0x1800328d5  mov     rbp, [rsp+38h+arg_8]
0x1800328da  mov     rsi, [rsp+38h+arg_10]
0x1800328df  mov     rdi, [rsp+38h+arg_18]
0x1800328e4  add     rsp, 30h
0x1800328e8  pop     r14
0x1800328ea  retn
```
