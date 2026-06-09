# TerminateModule(void)

- ea: `0x18004ae78`
- end: `0x18004afbd`
- name: `?TerminateModule@@YAXXZ`
- size: `325`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800913b8`

## callees

- `0x18004aa54`
- `0x18004aca8`
- `0x18004ae78`
- `0x18004ceb0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18004aedc`
- `KERNEL32!DeleteCriticalSection` at `0x18004aee9`
- `KERNEL32!DeleteCriticalSection` at `0x18004aef6`
- `KERNEL32!DeleteCriticalSection` at `0x18004af03`
- `KERNEL32!DeleteCriticalSection` at `0x18004af10`
- `KERNEL32!DeleteCriticalSection` at `0x18004af1d`
- `KERNEL32!DeleteCriticalSection` at `0x18004af2a`
- `KERNEL32!DeleteCriticalSection` at `0x18004af37`
- `KERNEL32!DeleteCriticalSection` at `0x18004af44`
- `KERNEL32!DeleteCriticalSection` at `0x18004af51`
- `KERNEL32!DeleteCriticalSection` at `0x18004af5e`
- `KERNEL32!DeleteCriticalSection` at `0x18004af6b`
- `KERNEL32!DeleteCriticalSection` at `0x18004af78`
- `KERNEL32!DeleteCriticalSection` at `0x18004af85`
- `KERNEL32!DeleteCriticalSection` at `0x18004aedc`
- `KERNEL32!DeleteCriticalSection` at `0x18004aee9`
- `KERNEL32!DeleteCriticalSection` at `0x18004aef6`
- `KERNEL32!DeleteCriticalSection` at `0x18004af03`
- `KERNEL32!DeleteCriticalSection` at `0x18004af10`
- `KERNEL32!DeleteCriticalSection` at `0x18004af1d`
- `KERNEL32!DeleteCriticalSection` at `0x18004af2a`
- `KERNEL32!DeleteCriticalSection` at `0x18004af37`
- `KERNEL32!DeleteCriticalSection` at `0x18004af44`
- `KERNEL32!DeleteCriticalSection` at `0x18004af51`
- `KERNEL32!DeleteCriticalSection` at `0x18004af5e`
- `KERNEL32!DeleteCriticalSection` at `0x18004af6b`
- `KERNEL32!DeleteCriticalSection` at `0x18004af78`
- `KERNEL32!DeleteCriticalSection` at `0x18004af85`
- `KERNEL32!DeleteCriticalSection` at `0x18004af96`
- `KERNEL32!GetCurrentThreadId` at `0x18004ae84`
- `KERNEL32!GetCurrentThreadId` at `0x18004ae84`
- `KERNEL32!TlsFree` at `0x18004af9d`
- `KERNEL32!TlsFree` at `0x18004af9d`
- `KERNEL32!FreeLibrary` at `0x18004afb2`
- `KERNEL32!FreeLibrary` at `0x18004afb2`

## pseudocode

```c
void TerminateModule(void)
{
  unsigned __int64 v0; // [rsp+30h] [rbp+8h]

  v0 = GetCurrentThreadId() | 0xFFFFFFFF00000000uLL;
  CheckAllHandlesClosed(0, v0);
  FreeGlobals();
  CAPITempBuffer<unsigned short,1>::Destroy(&off_180306150);
  if ( g_dwImpersonationSlot != -1 )
  {
    TlsFree(g_dwImpersonationSlot);
    g_dwImpersonationSlot = -1;
  }
  if ( g_hMsgInstance )
    FreeLibrary(g_hMsgInstance);
  g_hMsgInstance = 0;
  DeleteCriticalSection(&g_csMessageDll);
  DeleteCriticalSection(&g_csWriteLog);
  DeleteCriticalSection(&g_csImpersonationLock);
  DeleteCriticalSection(&g_csSharedServicesLock);
  DeleteCriticalSection(&g_csRecacheResolveSourceLock);
  DeleteCriticalSection(&g_csThreadImpersonationLock);
  DeleteCriticalSection(&g_csTransactionLock);
  DeleteCriticalSection(&g_csEnumLock);
  DeleteCriticalSection(&g_csPolicyTableLock);
  DeleteCriticalSection(&CRestartManagerWrapper::m_csAccessControl);
  DeleteCriticalSection(&g_csLUIDLock);
  DeleteCriticalSection(&g_csEnumStateManagerLock);
  DeleteCriticalSection(&g_csConfigManagerLock);
  DeleteCriticalSection(&g_csServerInterfaceLock);
  DeleteCriticalSection(&CMsiHandle::m_csLock);
}

```

## disassembly

```asm
0x18004ae78  sub     rsp, 28h
0x18004ae7c  mov     dword ptr [rsp+28h+arg_0+4], 0FFFFFFFFh
0x18004ae84  call    cs:__imp_GetCurrentThreadId
0x18004ae8a  mov     dword ptr [rsp+28h+arg_0], eax
0x18004ae8e  xor     ecx, ecx
0x18004ae90  mov     rdx, [rsp+28h+arg_0]
0x18004ae95  call    ?CheckAllHandlesClosed@@YAI_NUUniqueThreadID@@@Z; CheckAllHandlesClosed(bool,UniqueThreadID)
0x18004ae9a  call    ?FreeGlobals@@YAXXZ; FreeGlobals(void)
0x18004ae9f  lea     rcx, off_180306150
0x18004aea6  call    ?Destroy@?$CAPITempBuffer@G$00@@QEAAXXZ; CAPITempBuffer<ushort,1>::Destroy(void)
0x18004aeab  mov     ecx, cs:?g_dwImpersonationSlot@@3KA; dwTlsIndex
0x18004aeb1  cmp     ecx, 0FFFFFFFFh
0x18004aeb4  jnz     loc_18004AF9D
0x18004aeba  mov     rcx, cs:?g_hMsgInstance@@3PEAUHINSTANCE__@@EA; hLibModule
0x18004aec1  test    rcx, rcx
0x18004aec4  jnz     loc_18004AFB2
0x18004aeca  lea     rcx, ?g_csMessageDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004aed1  mov     cs:?g_hMsgInstance@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hMsgInstance
0x18004aedc  call    cs:__imp_DeleteCriticalSection
0x18004aee2  lea     rcx, ?g_csWriteLog@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004aee9  call    cs:__imp_DeleteCriticalSection
0x18004aeef  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004aef6  call    cs:__imp_DeleteCriticalSection
0x18004aefc  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004af03  call    cs:__imp_DeleteCriticalSection
0x18004af09  lea     rcx, ?g_csRecacheResolveSourceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004af10  call    cs:__imp_DeleteCriticalSection
0x18004af16  lea     rcx, ?g_csThreadImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004af1d  call    cs:__imp_DeleteCriticalSection
0x18004af23  lea     rcx, ?g_csTransactionLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004af2a  call    cs:__imp_DeleteCriticalSection
0x18004af30  lea     rcx, ?g_csEnumLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004af37  call    cs:__imp_DeleteCriticalSection
0x18004af3d  lea     rcx, ?g_csPolicyTableLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004af44  call    cs:__imp_DeleteCriticalSection
0x18004af4a  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004af51  call    cs:__imp_DeleteCriticalSection
0x18004af57  lea     rcx, ?g_csLUIDLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004af5e  call    cs:__imp_DeleteCriticalSection
0x18004af64  lea     rcx, ?g_csEnumStateManagerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004af6b  call    cs:__imp_DeleteCriticalSection
0x18004af71  lea     rcx, ?g_csConfigManagerLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004af78  call    cs:__imp_DeleteCriticalSection
0x18004af7e  lea     rcx, ?g_csServerInterfaceLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004af85  call    cs:__imp_DeleteCriticalSection
0x18004af8b  lea     rcx, ?m_csLock@CMsiHandle@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION CMsiHandle::m_csLock
0x18004af92  add     rsp, 28h
0x18004af96  jmp     cs:__imp_DeleteCriticalSection
0x18004af9d  call    cs:__imp_TlsFree
0x18004afa3  mov     cs:?g_dwImpersonationSlot@@3KA, 0FFFFFFFFh; ulong g_dwImpersonationSlot
0x18004afad  jmp     loc_18004AEBA
0x18004afb2  call    cs:__imp_FreeLibrary
0x18004afb8  jmp     loc_18004AECA
```
