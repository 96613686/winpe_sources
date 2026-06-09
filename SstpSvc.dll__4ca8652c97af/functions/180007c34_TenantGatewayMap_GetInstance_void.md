# TenantGatewayMap::GetInstance(void)

- ea: `0x180007c34`
- end: `0x180007c7a`
- name: `?GetInstance@TenantGatewayMap@@SAPEAV1@XZ`
- size: `70`
- prototype: `struct TenantGatewayMap *(void)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x180005280`
- `0x18000ff74`
- `0x1800103e8`
- `0x1800132c0`
- `0x180013464`
- `0x1800138c0`
- `0x180014170`
- `0x180014490`
- `0x180014840`

## callees

- `0x180007c34`
- `0x180008700`
- `0x18000f974`

## pseudocode

```c
struct TenantGatewayMap *TenantGatewayMap::GetInstance(void)
{
  struct TenantGatewayMap *result; // rax

  if ( TenantGatewayMap::fInitialized )
    return TenantGatewayMap::pInstance;
  result = (struct TenantGatewayMap *)operator new(0x68u);
  if ( result )
    result = (struct TenantGatewayMap *)TenantGatewayMap::TenantGatewayMap((WCHAR *)result);
  TenantGatewayMap::pInstance = result;
  TenantGatewayMap::fInitialized = 1;
  return result;
}

```

## disassembly

```asm
0x180007c34  sub     rsp, 28h
0x180007c38  cmp     cs:?fInitialized@TenantGatewayMap@@0_NA, 0; bool TenantGatewayMap::fInitialized
0x180007c3f  jnz     short loc_180007C6E
0x180007c41  mov     ecx, 68h ; 'h'; Size
0x180007c46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007c4b  mov     [rsp+28h+arg_0], rax
0x180007c50  test    rax, rax
0x180007c53  jz      short loc_180007C5E
0x180007c55  mov     rcx, rax; SRWLock
0x180007c58  call    ??0TenantGatewayMap@@AEAA@XZ; TenantGatewayMap::TenantGatewayMap(void)
0x180007c5d  nop
0x180007c5e  mov     cs:?pInstance@TenantGatewayMap@@0PEAV1@EA, rax; TenantGatewayMap * TenantGatewayMap::pInstance
0x180007c65  mov     cs:?fInitialized@TenantGatewayMap@@0_NA, 1; bool TenantGatewayMap::fInitialized
0x180007c6c  jmp     short loc_180007C75
0x180007c6e  mov     rax, cs:?pInstance@TenantGatewayMap@@0PEAV1@EA; TenantGatewayMap * TenantGatewayMap::pInstance
0x180007c75  add     rsp, 28h
0x180007c79  retn
```
