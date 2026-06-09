# SE_COM_AddServer

- ea: `0x1800535c0`
- end: `0x1800536b8`
- name: `SE_COM_AddServer`
- size: `248`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180032000`
- `0x180032690`

## callees

- `0x180009a14`
- `0x18000f114`
- `0x18001f6d0`
- `0x1800535c0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180053658`
- `ntdll!RtlLeaveCriticalSection` at `0x180053658`
- `ntdll!RtlEnterCriticalSection` at `0x180053606`
- `ntdll!RtlEnterCriticalSection` at `0x180053606`

## string_xrefs

- `0x1800535e9`: `SE_COM_AddServer`
- `0x180053644`: `SeComRouterAddDll`
- `0x180053637`: `Failed to add dll name`

## pseudocode

```c
__int64 __fastcall SE_COM_AddServer(__int64 a1, unsigned int a2)
{
  const char *v4; // r9
  __int64 v5; // r8
  unsigned int v6; // ebx
  struct _RTL_CRITICAL_SECTION *v7; // rbx
  int v8; // edi
  _QWORD *pShimData; // rcx

  if ( !g_Engine )
  {
    v4 = "Engine not initialized";
    v5 = 1615;
LABEL_3:
    v6 = 0;
    AslLogCallPrintf(1, "SE_COM_AddServer", v5, v4);
    return v6;
  }
  v7 = *(struct _RTL_CRITICAL_SECTION **)(g_Engine + 56);
  v8 = 0;
  RtlEnterCriticalSection(v7);
  if ( (unsigned int)SeInExIsExcluded(v7[4].LockSemaphore, a1) != a2 )
  {
    v8 = SeInExAppend(v7[4].LockSemaphore, a1, a2);
    if ( v8 < 0 )
      AslLogCallPrintf(1, "SeComRouterAddDll", 368, "Failed to add dll name");
  }
  RtlLeaveCriticalSection(v7);
  pShimData = NtCurrentPeb()->pShimData;
  if ( !pShimData )
  {
    v4 = "Shim data is not found";
    v5 = 1632;
    goto LABEL_3;
  }
  if ( (__int64 (__usercall *)@<rax>(wchar_t *@<rcx>, __int64))pShimData[558] != SE_HookComInterface )
  {
    g_HookComInterface = pShimData[558];
    pShimData[558] = SE_HookComInterface;
  }
  return v8 >= 0;
}

```

## disassembly

```asm
0x1800535c0  push    rbx
0x1800535c2  push    rbp
0x1800535c3  push    rsi
0x1800535c4  push    rdi
0x1800535c5  sub     rsp, 28h
0x1800535c9  mov     rbx, cs:g_Engine
0x1800535d0  mov     esi, edx
0x1800535d2  mov     rbp, rcx
0x1800535d5  test    rbx, rbx
0x1800535d8  jnz     short loc_1800535FD
0x1800535da  lea     r9, aEngineNotIniti_0; "Engine not initialized"
0x1800535e1  mov     r8d, 64Fh
0x1800535e7  xor     ebx, ebx
0x1800535e9  lea     rdx, aSeComAddserver_0; "SE_COM_AddServer"
0x1800535f0  lea     ecx, [rbx+1]
0x1800535f3  call    AslLogCallPrintf
0x1800535f8  jmp     loc_1800536AD
0x1800535fd  mov     rbx, [rbx+38h]
0x180053601  xor     edi, edi
0x180053603  mov     rcx, rbx; CriticalSection
0x180053606  call    cs:__imp_RtlEnterCriticalSection
0x18005360c  mov     rcx, [rbx+0B8h]
0x180053613  mov     rdx, rbp
0x180053616  call    SeInExIsExcluded
0x18005361b  cmp     eax, esi
0x18005361d  jz      short loc_180053655
0x18005361f  mov     rcx, [rbx+0B8h]
0x180053626  mov     r8d, esi
0x180053629  mov     rdx, rbp
0x18005362c  call    SeInExAppend
0x180053631  mov     edi, eax
0x180053633  test    eax, eax
0x180053635  jns     short loc_180053655
0x180053637  lea     r9, aFailedToAddDll; "Failed to add dll name"
0x18005363e  mov     r8d, 170h
0x180053644  lea     rdx, aSecomrouteradd; "SeComRouterAddDll"
0x18005364b  mov     ecx, 1
0x180053650  call    AslLogCallPrintf
0x180053655  mov     rcx, rbx; CriticalSection
0x180053658  call    cs:__imp_RtlLeaveCriticalSection
0x18005365e  mov     rax, gs:60h
0x180053667  mov     rcx, [rax+2D8h]
0x18005366e  test    rcx, rcx
0x180053671  jnz     short loc_180053685
0x180053673  lea     r9, aShimDataIsNotF; "Shim data is not found"
0x18005367a  mov     r8d, 660h
0x180053680  jmp     loc_1800535E7
0x180053685  mov     rax, [rcx+1170h]
0x18005368c  lea     rdx, SE_HookComInterface
0x180053693  cmp     rax, rdx
0x180053696  jz      short loc_1800536A6
0x180053698  mov     cs:g_HookComInterface, rax
0x18005369f  mov     [rcx+1170h], rdx
0x1800536a6  xor     ebx, ebx
0x1800536a8  test    edi, edi
0x1800536aa  setns   bl
0x1800536ad  mov     eax, ebx
0x1800536af  add     rsp, 28h
0x1800536b3  pop     rdi
0x1800536b4  pop     rsi
0x1800536b5  pop     rbp
0x1800536b6  pop     rbx
0x1800536b7  retn
```
