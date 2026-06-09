# Windows::System::CMemoryManager::Init(void)

- ea: `0x180002750`
- end: `0x180002855`
- name: `?Init@CMemoryManager@System@Windows@@CAJXZ`
- size: `261`
- prototype: `__int64(void)`
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001420`
- `0x180001f30`
- `0x180001ff0`
- `0x180002320`
- `0x1800109e0`
- `0x180019010`
- `0x180019070`

## callees

- `0x180001f68`
- `0x180002750`
- `0x180002ee8`
- `0x180002f50`
- `0x1800148c0`
- `0x18001c010`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002772`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800027c9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800027f3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002830`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002772`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800027c9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800027f3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002830`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000275b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000275b`

## pseudocode

```c
__int64 Windows::System::CMemoryManager::Init(void)
{
  ModernResourceManagerProxy *v1; // rax
  ModernResourceManagerProxy *v2; // rbx
  int v3; // eax
  void (*v4)(struct _RM_COMMIT_LEVEL_CHANGE_PAYLOAD *); // rdx
  void (*v5)(unsigned __int64, unsigned __int64); // r8
  int v6; // edi

  RtlAcquireSRWLockExclusive(&Windows::System::CMemoryManager::s_Lock);
  if ( Windows::System::CMemoryManager::s_pProxy )
  {
    RtlReleaseSRWLockExclusive(&Windows::System::CMemoryManager::s_Lock);
    return 0;
  }
  else
  {
    v1 = (ModernResourceManagerProxy *)operator new(0x70u);
    if ( v1 && (v2 = ModernResourceManagerProxy::ModernResourceManagerProxy(v1)) != 0 )
    {
      v3 = CempRpcBindToServer(qword_18001D170);
      v6 = v3 | 0x10000000;
      if ( v3 < 0 || (v6 = ModernResourceManagerProxy::RegisterCommitMemoryCallback(v2, v4, v5), v6 < 0) )
      {
        RtlReleaseSRWLockExclusive(&Windows::System::CMemoryManager::s_Lock);
        (*(void (__fastcall **)(ModernResourceManagerProxy *))(*(_QWORD *)v2 + 16LL))(v2);
        return (unsigned int)v6;
      }
      else
      {
        if ( Windows::System::CMemoryManager::s_pProxy )
          (*(void (__fastcall **)(ModernResourceManagerProxy *))(*(_QWORD *)Windows::System::CMemoryManager::s_pProxy
                                                               + 16LL))(Windows::System::CMemoryManager::s_pProxy);
        Windows::System::CMemoryManager::s_pProxy = v2;
        RtlReleaseSRWLockExclusive(&Windows::System::CMemoryManager::s_Lock);
        return 0;
      }
    }
    else
    {
      RtlReleaseSRWLockExclusive(&Windows::System::CMemoryManager::s_Lock);
      return 2147942414LL;
    }
  }
}

```

## disassembly

```asm
0x180002750  sub     rsp, 28h
0x180002754  lea     rcx, ?s_Lock@CMemoryManager@System@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::System::CMemoryManager::s_Lock
0x18000275b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180002761  cmp     cs:?s_pProxy@CMemoryManager@System@Windows@@0V?$ComPtr@VModernResourceManagerProxy@@@WRL@Microsoft@@A, 0; Microsoft::WRL::ComPtr<ModernResourceManagerProxy> Windows::System::CMemoryManager::s_pProxy
0x180002769  jz      short loc_18000277F
0x18000276b  lea     rcx, ?s_Lock@CMemoryManager@System@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::System::CMemoryManager::s_Lock
0x180002772  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002778  xor     eax, eax
0x18000277a  add     rsp, 28h
0x18000277e  retn
0x18000277f  mov     ecx, 70h ; 'p'; Size
0x180002784  mov     [rsp+28h+arg_0], rbx
0x180002789  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000278e  test    rax, rax
0x180002791  jz      short loc_1800027EC
0x180002793  mov     rcx, rax; this
0x180002796  call    ??0ModernResourceManagerProxy@@QEAA@XZ; ModernResourceManagerProxy::ModernResourceManagerProxy(void)
0x18000279b  mov     rbx, rax
0x18000279e  test    rax, rax
0x1800027a1  jz      short loc_1800027EC
0x1800027a3  mov     [rsp+28h+var_8], rdi
0x1800027a8  lea     rdx, [rax+10h]
0x1800027ac  lea     rcx, qword_18001D170; IfSpec
0x1800027b3  call    CempRpcBindToServer
0x1800027b8  mov     edi, eax
0x1800027ba  or      edi, 10000000h
0x1800027c0  jge     short loc_180002808
0x1800027c2  lea     rcx, ?s_Lock@CMemoryManager@System@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::System::CMemoryManager::s_Lock
0x1800027c9  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800027cf  mov     rax, [rbx]
0x1800027d2  mov     rcx, rbx
0x1800027d5  mov     rax, [rax+10h]
0x1800027d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027de  mov     rbx, [rsp+28h+arg_0]
0x1800027e3  mov     eax, edi
0x1800027e5  mov     rdi, [rsp+28h+var_8]
0x1800027ea  jmp     short loc_18000277A
0x1800027ec  lea     rcx, ?s_Lock@CMemoryManager@System@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::System::CMemoryManager::s_Lock
0x1800027f3  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800027f9  mov     rbx, [rsp+28h+arg_0]
0x1800027fe  mov     eax, 8007000Eh
0x180002803  jmp     loc_18000277A
0x180002808  mov     rcx, rbx; this
0x18000280b  call    ?RegisterCommitMemoryCallback@ModernResourceManagerProxy@@QEAAJP6AXPEAU_RM_COMMIT_LEVEL_CHANGE_PAYLOAD@@@ZP6AX_K2@Z@Z; ModernResourceManagerProxy::RegisterCommitMemoryCallback(void (*)(_RM_COMMIT_LEVEL_CHANGE_PAYLOAD *),void (*)(unsigned __int64,unsigned __int64))
0x180002810  mov     edi, eax
0x180002812  test    eax, eax
0x180002814  js      short loc_1800027C2
0x180002816  mov     rcx, cs:?s_pProxy@CMemoryManager@System@Windows@@0V?$ComPtr@VModernResourceManagerProxy@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ModernResourceManagerProxy> Windows::System::CMemoryManager::s_pProxy
0x18000281d  test    rcx, rcx
0x180002820  jnz     short loc_180002847
0x180002822  lea     rcx, ?s_Lock@CMemoryManager@System@Windows@@0U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::System::CMemoryManager::s_Lock
0x180002829  mov     cs:?s_pProxy@CMemoryManager@System@Windows@@0V?$ComPtr@VModernResourceManagerProxy@@@WRL@Microsoft@@A, rbx; Microsoft::WRL::ComPtr<ModernResourceManagerProxy> Windows::System::CMemoryManager::s_pProxy
0x180002830  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002836  mov     rdi, [rsp+28h+var_8]
0x18000283b  xor     eax, eax
0x18000283d  mov     rbx, [rsp+28h+arg_0]
0x180002842  jmp     loc_18000277A
0x180002847  mov     rax, [rcx]
0x18000284a  mov     rax, [rax+10h]
0x18000284e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002853  jmp     short loc_180002822
```
