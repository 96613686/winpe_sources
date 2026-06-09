# CAdapter::CompleteOidRequest(_NDIS_OID_REQUEST *,int)

- ea: `0x14002e878`
- end: `0x14002e9b5`
- name: `?CompleteOidRequest@CAdapter@@QEAAXPEAU_NDIS_OID_REQUEST@@H@Z`
- size: `317`
- prototype: `void(CAdapter *__hidden this, struct _NDIS_OID_REQUEST *, int)`
- caller_count: `35`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14001af50`
- `0x14001b3e0`
- `0x14002e070`
- `0x14002e180`
- `0x14002e270`
- `0x14002e850`
- `0x140044f50`
- `0x140046030`
- `0x14005a270`
- `0x1400697a0`
- `0x14006ad70`
- `0x14006b000`
- `0x14006f650`
- `0x140071b40`
- `0x140071ea0`
- `0x140072630`
- `0x140073030`
- `0x1400754b0`
- `0x140075ff0`
- `0x140078e30`
- `0x14007b910`
- `0x14007c0e0`
- `0x14007c560`
- `0x1400999f0`
- `0x1400a9580`
- `0x1400bfe40`
- `0x1400c4290`
- `0x1400c6b90`
- `0x1400c8620`
- `0x1400c86f0`
- `0x1400cc230`
- `0x1400cc300`
- `0x1400d1500`
- `0x1400d26b0`
- `0x1400d5cf0`

## callees

- `0x14002e878`
- `0x14002e9bc`
- `0x1400da680`

## import_xrefs

- `NDIS!NdisMOidRequestComplete` at `0x14002e9a7`
- `NDIS!NdisMOidRequestComplete` at `0x14002e9a7`

## pseudocode

```c
void __fastcall CAdapter::CompleteOidRequest(CAdapter *this, struct _NDIS_OID_REQUEST *a2, int a3)
{
  int v4; // esi
  __int64 i; // rdx
  CPort *v7; // rcx
  void *m_MiniportAdapterHandle; // rcx
  _NDIS_REQUEST_TYPE RequestType; // eax
  unsigned int Oid; // eax

  v4 = a3;
  for ( i = 0; (unsigned int)i < 5; i = (unsigned int)(i + 1) )
  {
    v7 = this->m_pPortList[i];
    if ( v7 && v7->m_NdisPortNumber == a2->PortNumber )
    {
      if ( v7->m_LastOidInfo.pOidRequest == a2 )
      {
        v7->m_LastOidInfo.pOidRequest = 0;
        v7->m_LastOidInfo.OidStatus = a3;
        v7->m_LastOidInfo.OidCompletedTime = MEMORY[0xFFFFF78000000014];
      }
      break;
    }
  }
  this->m_DebugLastOidRequest = 0;
  this->m_DebugLastOidStatus = a3;
  this->m_DebugLastOidCompletedTime = MEMORY[0xFFFFF78000000014];
  if ( *(unsigned __int8 **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_Dddq(WPP_GLOBAL_Control->DeviceExtension, i, 20, 88);
  if ( this->m_lResetRecovery )
  {
    RequestType = a2->RequestType;
    if ( RequestType == NdisRequestSetInformation || RequestType == NdisRequestMethod )
    {
      Oid = a2->DATA.Oid;
      if ( Oid == 66088 || Oid == 235143426 || Oid == -50265845 || Oid == -50265841 )
        v4 = 0;
    }
  }
  m_MiniportAdapterHandle = this->m_MiniportAdapterHandle;
  if ( g_pWdiDriver->m_NdisHook.m_NdisSupportsHook )
    g_pWdiDriver->m_NdisHook.m_NdisRawDispatch.RawOidRequestComplete(m_MiniportAdapterHandle, a2, v4);
  else
    NdisMOidRequestComplete(m_MiniportAdapterHandle, a2, v4);
}

```

## disassembly

```asm
0x14002e878  mov     [rsp+arg_0], rbx
0x14002e87d  mov     [rsp+arg_8], rsi
0x14002e882  push    rdi
0x14002e883  sub     rsp, 50h
0x14002e887  mov     rbx, rdx
0x14002e88a  mov     esi, r8d
0x14002e88d  xor     edx, edx
0x14002e88f  mov     rdi, rcx
0x14002e892  mov     r8, 0FFFFF78000000014h
0x14002e89c  cmp     edx, 5
0x14002e89f  jnb     short loc_14002E8DE
0x14002e8a1  mov     rcx, [rdi+rdx*8+1318h]
0x14002e8a9  test    rcx, rcx
0x14002e8ac  jz      short loc_14002E8B6
0x14002e8ae  mov     eax, [rbx+8]
0x14002e8b1  cmp     [rcx+60h], eax
0x14002e8b4  jz      short loc_14002E8BA
0x14002e8b6  inc     edx
0x14002e8b8  jmp     short loc_14002E892
0x14002e8ba  cmp     [rcx+458h], rbx
0x14002e8c1  jnz     short loc_14002E8DE
0x14002e8c3  mov     qword ptr [rcx+458h], 0
0x14002e8ce  mov     [rcx+464h], esi
0x14002e8d4  mov     rax, [r8]
0x14002e8d7  mov     [rcx+470h], rax
0x14002e8de  mov     qword ptr [rdi+888h], 0
0x14002e8e9  mov     [rdi+894h], esi
0x14002e8ef  mov     rax, [r8]
0x14002e8f2  mov     [rdi+8A0h], rax
0x14002e8f9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002e900  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002e907  jz      short loc_14002E93A
0x14002e909  mov     rax, [rdi+58h]
0x14002e90d  mov     r9d, 58h ; 'X'
0x14002e913  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e91a  mov     [rsp+58h+var_18], rax
0x14002e91f  mov     eax, [rbx+8]
0x14002e922  mov     [rsp+58h+var_20], esi
0x14002e926  mov     rcx, [rcx+40h]
0x14002e92a  mov     [rsp+58h+var_28], eax
0x14002e92e  mov     eax, [rbx+20h]
0x14002e931  mov     [rsp+58h+var_30], eax
0x14002e935  call    WPP_RECORDER_SF_Dddq
0x14002e93a  cmp     dword ptr [rdi+15C8h], 0
0x14002e941  jnz     short loc_14002E977
0x14002e943  mov     rax, cs:?g_pWdiDriver@@3PEAVCWdiDriver@@EA; CWdiDriver * g_pWdiDriver
0x14002e94a  mov     r8d, esi; Status
0x14002e94d  mov     rcx, [rdi+58h]; MiniportAdapterHandle
0x14002e951  mov     rdx, rbx; OidRequest
0x14002e954  cmp     byte ptr [rax+50h], 0
0x14002e958  jz      short loc_14002E9A7
0x14002e95a  mov     rax, [rax+0C8h]
0x14002e961  call    _guard_dispatch_icall
0x14002e966  mov     rbx, [rsp+58h+arg_0]
0x14002e96b  mov     rsi, [rsp+58h+arg_8]
0x14002e970  add     rsp, 50h
0x14002e974  pop     rdi
0x14002e975  retn
0x14002e977  mov     eax, [rbx+4]
0x14002e97a  cmp     eax, 1
0x14002e97d  jz      short loc_14002E984
0x14002e97f  cmp     eax, 0Ch
0x14002e982  jnz     short loc_14002E943
0x14002e984  mov     eax, [rbx+20h]
0x14002e987  cmp     eax, 10228h
0x14002e98c  jz      short loc_14002E9A3
0x14002e98e  cmp     eax, 0E040102h
0x14002e993  jz      short loc_14002E9A3
0x14002e995  cmp     eax, 0FD01010Bh
0x14002e99a  jz      short loc_14002E9A3
0x14002e99c  cmp     eax, 0FD01010Fh
0x14002e9a1  jnz     short loc_14002E943
0x14002e9a3  xor     esi, esi
0x14002e9a5  jmp     short loc_14002E943
0x14002e9a7  call    cs:__imp_NdisMOidRequestComplete
0x14002e9ae  nop     dword ptr [rax+rax+00h]
0x14002e9b3  jmp     short loc_14002E966
```
