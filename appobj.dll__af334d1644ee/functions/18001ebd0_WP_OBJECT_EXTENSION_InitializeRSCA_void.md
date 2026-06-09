# WP_OBJECT_EXTENSION::InitializeRSCA(void)

- ea: `0x18001ebd0`
- end: `0x18001ec44`
- name: `?InitializeRSCA@WP_OBJECT_EXTENSION@@AEAAJXZ`
- size: `116`
- prototype: `__int64 __fastcall(WP_OBJECT_EXTENSION *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001e590`

## callees

- `0x18001ebd0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ebfe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001ebfe`

## pseudocode

```c
__int64 __fastcall WP_OBJECT_EXTENSION::InitializeRSCA(LPVOID *this)
{
  HRESULT Instance; // ebx
  _QWORD *v2; // rdi

  Instance = 0;
  v2 = this + 6;
  if ( !this[6] )
  {
    Instance = CoCreateInstance(&CLSID_RSCA_WAS, 0, 0x15u, &IID_IRSCA_WAS, this + 6);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v2 + 24LL))(*v2, 0);
      if ( Instance < 0 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
        *v2 = 0;
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001ebd0  mov     [rsp+arg_0], rbx
0x18001ebd5  push    rdi
0x18001ebd6  sub     rsp, 30h
0x18001ebda  xor     ebx, ebx
0x18001ebdc  lea     rdi, [rcx+30h]
0x18001ebe0  cmp     [rdi], rbx
0x18001ebe3  jnz     short loc_18001EC37
0x18001ebe5  lea     r9, IID_IRSCA_WAS; riid
0x18001ebec  mov     [rsp+38h+ppv], rdi; ppv
0x18001ebf1  xor     edx, edx; pUnkOuter
0x18001ebf3  lea     r8d, [rbx+15h]; dwClsContext
0x18001ebf7  lea     rcx, CLSID_RSCA_WAS; rclsid
0x18001ebfe  call    cs:__imp_CoCreateInstance
0x18001ec04  mov     ebx, eax
0x18001ec06  test    eax, eax
0x18001ec08  js      short loc_18001EC37
0x18001ec0a  mov     rcx, [rdi]
0x18001ec0d  xor     edx, edx
0x18001ec0f  mov     rax, [rcx]
0x18001ec12  mov     rax, [rax+18h]
0x18001ec16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec1b  mov     ebx, eax
0x18001ec1d  test    eax, eax
0x18001ec1f  jns     short loc_18001EC37
0x18001ec21  mov     rcx, [rdi]
0x18001ec24  mov     rax, [rcx]
0x18001ec27  mov     rax, [rax+10h]
0x18001ec2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec30  mov     qword ptr [rdi], 0
0x18001ec37  mov     eax, ebx
0x18001ec39  mov     rbx, [rsp+38h+arg_0]
0x18001ec3e  add     rsp, 30h
0x18001ec42  pop     rdi
0x18001ec43  retn
```
