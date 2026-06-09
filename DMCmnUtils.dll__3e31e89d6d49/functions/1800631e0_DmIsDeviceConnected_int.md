# DmIsDeviceConnected(int *)

- ea: `0x1800631e0`
- end: `0x180063289`
- name: `?DmIsDeviceConnected@@YAJPEAH@Z`
- size: `169`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800631e0`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063225`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180063225`

## pseudocode

```c
__int64 __fastcall DmIsDeviceConnected(int *a1)
{
  HRESULT v2; // ebx
  __int16 v4; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  v4 = -1;
  *a1 = 0;
  v2 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b, &ppv);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 96LL))(ppv, &v4);
    if ( v2 >= 0 && v4 == -1 )
      *a1 = 1;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800631e0  mov     rax, rsp
0x1800631e3  mov     [rax+18h], rbx
0x1800631e7  mov     [rax+20h], rbp
0x1800631eb  push    rdi
0x1800631ec  sub     rsp, 30h
0x1800631f0  or      ebp, 0FFFFFFFFh
0x1800631f3  mov     qword ptr [rax+10h], 0
0x1800631fb  mov     [rax+8], bp
0x1800631ff  lea     rax, [rax+10h]
0x180063203  mov     rdi, rcx
0x180063206  mov     dword ptr [rcx], 0
0x18006320c  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x180063213  mov     [rsp+38h+ppv], rax; ppv
0x180063218  lea     r8d, [rbp+2]; dwClsContext
0x18006321c  xor     edx, edx; pUnkOuter
0x18006321e  lea     rcx, CLSID_NetworkListManager; rclsid
0x180063225  call    cs:__imp_CoCreateInstance
0x18006322c  nop     dword ptr [rax+rax+00h]
0x180063231  mov     ebx, eax
0x180063233  test    eax, eax
0x180063235  js      short loc_180063260
0x180063237  mov     rcx, [rsp+38h+arg_8]
0x18006323c  lea     rdx, [rsp+38h+arg_0]
0x180063241  mov     rax, [rcx]
0x180063244  mov     rax, [rax+60h]
0x180063248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006324d  mov     ebx, eax
0x18006324f  test    eax, eax
0x180063251  js      short loc_180063260
0x180063253  cmp     bp, [rsp+38h+arg_0]
0x180063258  jnz     short loc_180063260
0x18006325a  mov     dword ptr [rdi], 1
0x180063260  mov     rcx, [rsp+38h+arg_8]
0x180063265  test    rcx, rcx
0x180063268  jz      short loc_180063276
0x18006326a  mov     rax, [rcx]
0x18006326d  mov     rax, [rax+10h]
0x180063271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063276  mov     rbp, [rsp+38h+arg_18]
0x18006327b  mov     eax, ebx
0x18006327d  mov     rbx, [rsp+38h+arg_10]
0x180063282  add     rsp, 30h
0x180063286  pop     rdi
0x180063287  retn
```
