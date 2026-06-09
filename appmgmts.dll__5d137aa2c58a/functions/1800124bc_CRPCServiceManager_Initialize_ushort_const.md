# CRPCServiceManager::Initialize(ushort const *)

- ea: `0x1800124bc`
- end: `0x180012565`
- name: `?Initialize@CRPCServiceManager@@SAKPEBG@Z`
- size: `169`
- prototype: `DWORD __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000dd00`

## callees

- `0x180012234`
- `0x18001231c`
- `0x1800124bc`
- `0x180013780`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001251d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001251d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800124cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800124cc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012507`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012507`

## pseudocode

```c
DWORD __fastcall CRPCServiceManager::Initialize(const unsigned __int16 *a1)
{
  CRPCServiceManager *v1; // rax
  const unsigned __int16 *v2; // rdx
  DWORD result; // eax
  HANDLE EventW; // rax
  CGPRPCServerBase *v5; // rcx

  v1 = (CRPCServiceManager *)LocalAlloc(0, 0x90u);
  if ( v1 )
    v1 = CRPCServiceManager::CRPCServiceManager(v1, v2);
  CRPCServiceManager::_pSingletonManager = v1;
  if ( !v1 )
    return 14;
  EventW = CreateEventW(0, 1, 0, 0);
  v5 = CRPCServiceManager::_pSingletonManager;
  *((_QWORD *)CRPCServiceManager::_pSingletonManager + 8) = EventW;
  if ( !EventW )
  {
    result = GetLastError();
    if ( result )
      return result;
    v5 = CRPCServiceManager::_pSingletonManager;
  }
  CRequestManager::EnableNewRequests((CGPRPCServerBase *)((char *)v5 + 72));
  result = 87;
  if ( !CGPRPCServerBase::m_instance )
  {
    result = *((_DWORD *)CRPCServiceManager::_pSingletonManager + 2);
    if ( !result )
    {
      CGPRPCServerBase::m_instance = CRPCServiceManager::_pSingletonManager;
      return CGPRPCServerBase::StartRPCServer(CRPCServiceManager::_pSingletonManager);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800124bc  mov     [rsp+arg_0], rcx
0x1800124c1  sub     rsp, 28h
0x1800124c5  mov     edx, 90h; uBytes
0x1800124ca  xor     ecx, ecx; uFlags
0x1800124cc  call    cs:__imp_LocalAlloc
0x1800124d2  mov     [rsp+28h+arg_0], rax
0x1800124d7  test    rax, rax
0x1800124da  jz      short loc_1800124E5
0x1800124dc  mov     rcx, rax; this
0x1800124df  call    ??0CRPCServiceManager@@AEAA@PEBG@Z; CRPCServiceManager::CRPCServiceManager(ushort const *)
0x1800124e4  nop
0x1800124e5  mov     cs:?_pSingletonManager@CRPCServiceManager@@0PEAV1@EA, rax; CRPCServiceManager * CRPCServiceManager::_pSingletonManager
0x1800124ec  test    rax, rax
0x1800124ef  jnz     short loc_1800124FB
0x1800124f1  mov     eax, 0Eh
0x1800124f6  add     rsp, 28h
0x1800124fa  retn
0x1800124fb  xor     r9d, r9d; lpName
0x1800124fe  xor     r8d, r8d; bInitialState
0x180012501  lea     edx, [r9+1]; bManualReset
0x180012505  xor     ecx, ecx; lpEventAttributes
0x180012507  call    cs:__imp_CreateEventW
0x18001250d  mov     rcx, cs:?_pSingletonManager@CRPCServiceManager@@0PEAV1@EA; CRPCServiceManager * CRPCServiceManager::_pSingletonManager
0x180012514  mov     [rcx+40h], rax
0x180012518  test    rax, rax
0x18001251b  jnz     short loc_18001252E
0x18001251d  call    cs:__imp_GetLastError
0x180012523  test    eax, eax
0x180012525  jnz     short loc_180012560
0x180012527  mov     rcx, cs:?_pSingletonManager@CRPCServiceManager@@0PEAV1@EA; CRPCServiceManager * CRPCServiceManager::_pSingletonManager
0x18001252e  add     rcx, 48h ; 'H'; this
0x180012532  call    ?EnableNewRequests@CRequestManager@@QEAAKXZ; CRequestManager::EnableNewRequests(void)
0x180012537  mov     eax, 57h ; 'W'
0x18001253c  cmp     cs:?m_instance@CGPRPCServerBase@@1PEAV1@EA, 0; CGPRPCServerBase * CGPRPCServerBase::m_instance
0x180012544  jnz     short loc_180012560
0x180012546  mov     rcx, cs:?_pSingletonManager@CRPCServiceManager@@0PEAV1@EA; this
0x18001254d  mov     eax, [rcx+8]
0x180012550  test    eax, eax
0x180012552  jnz     short loc_180012560
0x180012554  mov     cs:?m_instance@CGPRPCServerBase@@1PEAV1@EA, rcx; CGPRPCServerBase * CGPRPCServerBase::m_instance
0x18001255b  call    ?StartRPCServer@CGPRPCServerBase@@QEAAKXZ; CGPRPCServerBase::StartRPCServer(void)
0x180012560  add     rsp, 28h
0x180012564  retn
```
