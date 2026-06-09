# CProfileCache::OnNetworkDisconnected(_GUID const *)

- ea: `0x1800067b0`
- end: `0x18000687d`
- name: `?OnNetworkDisconnected@CProfileCache@@UEAAJPEBU_GUID@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(CProfileCache *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004db0`
- `0x18000589c`
- `0x1800067b0`
- `0x180006ef4`
- `0x1800076c8`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x180006859`
- `SHELL32!SHChangeNotify` at `0x180006859`

## pseudocode

```c
__int64 __fastcall CProfileCache::OnNetworkDisconnected(CProfileCache *this, const struct _GUID *a2)
{
  int updated; // eax
  volatile signed __int32 *v4; // rcx
  int refreshed; // edi
  signed __int32 v6; // r9d
  CNetworkItemFactory *v7; // rcx
  signed __int32 v8; // edx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_cf095e51d6be376dc6c0faef7764f3c8_Traceguids);
  }
  updated = CProfileCache::_UpdateMapping(this);
  v4 = (volatile signed __int32 *)((char *)this + 48);
  refreshed = updated;
  v6 = *((_DWORD *)this + 12);
  if ( (v6 & 0xFFFF8000) != 0 || v6 != _InterlockedCompareExchange(v4, v6 + 1, v6) )
    CReaderWriterLock3::_LockSpin(v4, 2);
  if ( refreshed >= 0 )
  {
    v7 = (CNetworkItemFactory *)*((_QWORD *)this + 13);
    if ( v7 )
    {
      refreshed = CNetworkItemFactory::_RefreshQuery(v7, *((LPCITEMIDLIST *)this + 12), 1, 1);
      if ( refreshed >= 0 )
        SHChangeNotify(4096, 0, *((LPCVOID *)this + 12), 0);
    }
  }
  do
    v8 = *((_DWORD *)this + 12);
  while ( v8 != _InterlockedCompareExchange((volatile signed __int32 *)this + 12, v8 - 1, v8) );
  return (unsigned int)refreshed;
}

```

## disassembly

```asm
0x1800067b0  mov     [rsp+arg_0], rbx
0x1800067b5  push    rdi
0x1800067b6  sub     rsp, 20h
0x1800067ba  mov     rbx, rcx
0x1800067bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067c4  lea     rax, WPP_GLOBAL_Control
0x1800067cb  cmp     rcx, rax
0x1800067ce  jz      short loc_1800067F1
0x1800067d0  cmp     byte ptr [rcx+19h], 4
0x1800067d4  jb      short loc_1800067F1
0x1800067d6  test    byte ptr [rcx+1Ch], 2
0x1800067da  jz      short loc_1800067F1
0x1800067dc  mov     rcx, [rcx+10h]
0x1800067e0  lea     r8, WPP_cf095e51d6be376dc6c0faef7764f3c8_Traceguids
0x1800067e7  mov     edx, 0Ch
0x1800067ec  call    WPP_SF_
0x1800067f1  mov     rcx, rbx; this
0x1800067f4  call    ?_UpdateMapping@CProfileCache@@AEAAJXZ; CProfileCache::_UpdateMapping(void)
0x1800067f9  lea     rcx, [rbx+30h]
0x1800067fd  mov     edi, eax
0x1800067ff  mov     r9d, [rcx]
0x180006802  test    r9d, 0FFFF8000h
0x180006809  jnz     short loc_18000681C
0x18000680b  lea     r8d, [r9+1]
0x18000680f  mov     eax, r9d
0x180006812  lock cmpxchg [rcx], r8d
0x180006817  cmp     r9d, eax
0x18000681a  jz      short loc_180006826
0x18000681c  mov     edx, 2
0x180006821  call    ?_LockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z; CReaderWriterLock3::_LockSpin(CReaderWriterLock3::SPIN_TYPE)
0x180006826  test    edi, edi
0x180006828  js      short loc_18000685F
0x18000682a  mov     rcx, [rbx+68h]; this
0x18000682e  test    rcx, rcx
0x180006831  jz      short loc_18000685F
0x180006833  mov     rdx, [rbx+60h]; pidl
0x180006837  mov     r8d, 1; int
0x18000683d  mov     r9d, r8d; int
0x180006840  call    ?_RefreshQuery@CNetworkItemFactory@@AEAAJPEFBU_ITEMIDLIST@@HH@Z; CNetworkItemFactory::_RefreshQuery(_ITEMIDLIST const *,int,int)
0x180006845  mov     edi, eax
0x180006847  test    eax, eax
0x180006849  js      short loc_18000685F
0x18000684b  mov     r8, [rbx+60h]; dwItem1
0x18000684f  xor     r9d, r9d; dwItem2
0x180006852  xor     edx, edx; uFlags
0x180006854  mov     ecx, 1000h; wEventId
0x180006859  call    cs:__imp_SHChangeNotify
0x18000685f  mov     edx, [rbx+30h]
0x180006862  mov     eax, edx
0x180006864  lea     ecx, [rdx-1]
0x180006867  lock cmpxchg [rbx+30h], ecx
0x18000686c  cmp     edx, eax
0x18000686e  jnz     short loc_18000685F
0x180006870  mov     rbx, [rsp+28h+arg_0]
0x180006875  mov     eax, edi
0x180006877  add     rsp, 20h
0x18000687b  pop     rdi
0x18000687c  retn
```
