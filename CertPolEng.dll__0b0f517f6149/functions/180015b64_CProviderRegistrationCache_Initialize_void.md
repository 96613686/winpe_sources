# CProviderRegistrationCache::Initialize(void)

- ea: `0x180015b64`
- end: `0x180015bbd`
- name: `?Initialize@CProviderRegistrationCache@@QEAAKXZ`
- size: `89`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800077b0`

## callees

- `0x180015b64`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x180015b94`
- `ntdll!RtlInitializeResource` at `0x180015b94`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::Initialize(CProviderRegistrationCache *this)
{
  unsigned int v1; // ebx
  _DWORD *v2; // rdi

  v1 = 0;
  v2 = (_DWORD *)((char *)g_pProvRegCache + 8);
  if ( *((_DWORD *)g_pProvRegCache + 2) )
  {
    return 5023;
  }
  else
  {
    RtlInitializeResource((PRTL_RESOURCE)((char *)g_pProvRegCache + 16));
    *v2 = 1;
  }
  return v1;
}

```

## disassembly

```asm
0x180015b64  mov     [rsp+arg_8], rbx
0x180015b69  mov     [rsp+arg_0], rcx
0x180015b6e  push    rdi
0x180015b6f  sub     rsp, 20h
0x180015b73  mov     rcx, cs:?g_pProvRegCache@@3PEAVCProviderRegistrationCache@@EA; CProviderRegistrationCache * g_pProvRegCache
0x180015b7a  xor     ebx, ebx
0x180015b7c  lea     rdi, [rcx+8]
0x180015b80  mov     [rsp+28h+arg_0], rdi
0x180015b85  cmp     [rdi], ebx
0x180015b87  jz      short loc_180015B90
0x180015b89  mov     ebx, 139Fh
0x180015b8e  jmp     short loc_180015BB0
0x180015b90  add     rcx, 10h; Resource
0x180015b94  call    cs:__imp_RtlInitializeResource
0x180015b9a  jmp     short loc_180015BA6
0x180015b9c  mov     ebx, 0Eh
0x180015ba1  mov     rdi, [rsp+28h+arg_0]
0x180015ba6  test    ebx, ebx
0x180015ba8  jnz     short loc_180015BB0
0x180015baa  mov     dword ptr [rdi], 1
0x180015bb0  mov     eax, ebx
0x180015bb2  mov     rbx, [rsp+28h+arg_8]
0x180015bb7  add     rsp, 20h
0x180015bbb  pop     rdi
0x180015bbc  retn
```
