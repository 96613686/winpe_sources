# SITE_OBJECT_EXTENSION::InitializeRSCA(void)

- ea: `0x180011f30`
- end: `0x180011fbb`
- name: `?InitializeRSCA@SITE_OBJECT_EXTENSION@@AEAAJXZ`
- size: `139`
- prototype: `__int64 __fastcall(SITE_OBJECT_EXTENSION *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800113c8`
- `0x180011dc4`

## callees

- `0x180011f30`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011f6d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011f6d`

## pseudocode

```c
__int64 __fastcall SITE_OBJECT_EXTENSION::InitializeRSCA(SITE_OBJECT_EXTENSION *this)
{
  HRESULT Instance; // ebx
  LPVOID *ppv; // rdi

  Instance = 0;
  ppv = (LPVOID *)((char *)this + 56);
  if ( !*((_QWORD *)this + 7) )
  {
    Instance = *((_DWORD *)this + 16);
    if ( Instance >= 0 )
    {
      Instance = CoCreateInstance(&CLSID_RSCA_W3SVC, 0, 0x15u, &IID_IRSCA_W3SVC, ppv);
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)*ppv + 24LL))(*ppv, 0);
        if ( Instance < 0 )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)*ppv + 16LL))(*ppv);
          *ppv = 0;
        }
      }
    }
  }
  *((_DWORD *)this + 16) = Instance;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180011f30  mov     [rsp+arg_0], rbx
0x180011f35  mov     [rsp+arg_8], rsi
0x180011f3a  push    rdi
0x180011f3b  sub     rsp, 30h
0x180011f3f  xor     ebx, ebx
0x180011f41  lea     rdi, [rcx+38h]
0x180011f45  mov     rsi, rcx
0x180011f48  cmp     [rdi], rbx
0x180011f4b  jnz     short loc_180011FA6
0x180011f4d  mov     ebx, [rcx+40h]
0x180011f50  test    ebx, ebx
0x180011f52  js      short loc_180011FA6
0x180011f54  xor     edx, edx; pUnkOuter
0x180011f56  mov     [rsp+38h+ppv], rdi; ppv
0x180011f5b  lea     r9, IID_IRSCA_W3SVC; riid
0x180011f62  lea     rcx, CLSID_RSCA_W3SVC; rclsid
0x180011f69  lea     r8d, [rdx+15h]; dwClsContext
0x180011f6d  call    cs:__imp_CoCreateInstance
0x180011f73  mov     ebx, eax
0x180011f75  test    eax, eax
0x180011f77  js      short loc_180011FA6
0x180011f79  mov     rcx, [rdi]
0x180011f7c  xor     edx, edx
0x180011f7e  mov     rax, [rcx]
0x180011f81  mov     rax, [rax+18h]
0x180011f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f8a  mov     ebx, eax
0x180011f8c  test    eax, eax
0x180011f8e  jns     short loc_180011FA6
0x180011f90  mov     rcx, [rdi]
0x180011f93  mov     rax, [rcx]
0x180011f96  mov     rax, [rax+10h]
0x180011f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f9f  mov     qword ptr [rdi], 0
0x180011fa6  mov     [rsi+40h], ebx
0x180011fa9  mov     eax, ebx
0x180011fab  mov     rbx, [rsp+38h+arg_0]
0x180011fb0  mov     rsi, [rsp+38h+arg_8]
0x180011fb5  add     rsp, 30h
0x180011fb9  pop     rdi
0x180011fba  retn
```
