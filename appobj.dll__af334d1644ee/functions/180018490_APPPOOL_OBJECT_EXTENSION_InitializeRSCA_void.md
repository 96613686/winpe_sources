# APPPOOL_OBJECT_EXTENSION::InitializeRSCA(void)

- ea: `0x180018490`
- end: `0x18001851b`
- name: `?InitializeRSCA@APPPOOL_OBJECT_EXTENSION@@AEAAJXZ`
- size: `139`
- prototype: `__int64 __fastcall(APPPOOL_OBJECT_EXTENSION *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017a24`
- `0x18001833c`

## callees

- `0x180018490`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800184cd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800184cd`

## pseudocode

```c
__int64 __fastcall APPPOOL_OBJECT_EXTENSION::InitializeRSCA(APPPOOL_OBJECT_EXTENSION *this)
{
  HRESULT Instance; // ebx
  LPVOID *ppv; // rdi

  Instance = 0;
  ppv = (LPVOID *)((char *)this + 48);
  if ( !*((_QWORD *)this + 6) )
  {
    Instance = *((_DWORD *)this + 14);
    if ( Instance >= 0 )
    {
      Instance = CoCreateInstance(&CLSID_RSCA_WAS, 0, 0x15u, &IID_IRSCA_WAS, ppv);
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
  *((_DWORD *)this + 14) = Instance;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180018490  mov     [rsp+arg_0], rbx
0x180018495  mov     [rsp+arg_8], rsi
0x18001849a  push    rdi
0x18001849b  sub     rsp, 30h
0x18001849f  xor     ebx, ebx
0x1800184a1  lea     rdi, [rcx+30h]
0x1800184a5  mov     rsi, rcx
0x1800184a8  cmp     [rdi], rbx
0x1800184ab  jnz     short loc_180018506
0x1800184ad  mov     ebx, [rcx+38h]
0x1800184b0  test    ebx, ebx
0x1800184b2  js      short loc_180018506
0x1800184b4  xor     edx, edx; pUnkOuter
0x1800184b6  mov     [rsp+38h+ppv], rdi; ppv
0x1800184bb  lea     r9, IID_IRSCA_WAS; riid
0x1800184c2  lea     rcx, CLSID_RSCA_WAS; rclsid
0x1800184c9  lea     r8d, [rdx+15h]; dwClsContext
0x1800184cd  call    cs:__imp_CoCreateInstance
0x1800184d3  mov     ebx, eax
0x1800184d5  test    eax, eax
0x1800184d7  js      short loc_180018506
0x1800184d9  mov     rcx, [rdi]
0x1800184dc  xor     edx, edx
0x1800184de  mov     rax, [rcx]
0x1800184e1  mov     rax, [rax+18h]
0x1800184e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184ea  mov     ebx, eax
0x1800184ec  test    eax, eax
0x1800184ee  jns     short loc_180018506
0x1800184f0  mov     rcx, [rdi]
0x1800184f3  mov     rax, [rcx]
0x1800184f6  mov     rax, [rax+10h]
0x1800184fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184ff  mov     qword ptr [rdi], 0
0x180018506  mov     [rsi+38h], ebx
0x180018509  mov     eax, ebx
0x18001850b  mov     rbx, [rsp+38h+arg_0]
0x180018510  mov     rsi, [rsp+38h+arg_8]
0x180018515  add     rsp, 30h
0x180018519  pop     rdi
0x18001851a  retn
```
