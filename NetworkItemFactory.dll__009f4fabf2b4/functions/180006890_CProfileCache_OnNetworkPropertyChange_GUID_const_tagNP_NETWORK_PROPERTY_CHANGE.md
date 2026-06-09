# CProfileCache::OnNetworkPropertyChange(_GUID const *,tagNP_NETWORK_PROPERTY_CHANGE)

- ea: `0x180006890`
- end: `0x18000690f`
- name: `?OnNetworkPropertyChange@CProfileCache@@UEAAJPEBU_GUID@@W4tagNP_NETWORK_PROPERTY_CHANGE@@@Z`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180006890`
- `0x180006ef4`
- `0x180007080`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x1800068f7`
- `SHELL32!SHChangeNotify` at `0x1800068f7`

## pseudocode

```c
__int64 __fastcall CProfileCache::OnNetworkPropertyChange(CProfileCache *a1, __int64 a2, __int64 a3)
{
  char v3; // di
  int updated; // ebx
  const void *v6; // r8

  v3 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (unsigned int)a3);
  }
  updated = CProfileCache::_UpdateMapping(a1);
  if ( updated >= 0 )
  {
    v6 = (const void *)*((_QWORD *)a1 + 12);
    if ( v6 )
    {
      if ( (v3 & 4) != 0 )
        SHChangeNotify(4096, 0, v6, 0);
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180006890  mov     [rsp+arg_0], rbx
0x180006895  mov     [rsp+arg_8], rsi
0x18000689a  push    rdi
0x18000689b  sub     rsp, 20h
0x18000689f  mov     edi, r8d
0x1800068a2  mov     rsi, rcx
0x1800068a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068ac  lea     rax, WPP_GLOBAL_Control
0x1800068b3  cmp     rcx, rax
0x1800068b6  jz      short loc_1800068D0
0x1800068b8  cmp     byte ptr [rcx+19h], 4
0x1800068bc  jb      short loc_1800068D0
0x1800068be  test    byte ptr [rcx+1Ch], 2
0x1800068c2  jz      short loc_1800068D0
0x1800068c4  mov     rcx, [rcx+10h]
0x1800068c8  mov     r9d, r8d
0x1800068cb  call    WPP_SF_D
0x1800068d0  mov     rcx, rsi; this
0x1800068d3  call    ?_UpdateMapping@CProfileCache@@AEAAJXZ; CProfileCache::_UpdateMapping(void)
0x1800068d8  mov     ebx, eax
0x1800068da  test    eax, eax
0x1800068dc  js      short loc_1800068FD
0x1800068de  mov     r8, [rsi+60h]; dwItem1
0x1800068e2  test    r8, r8
0x1800068e5  jz      short loc_1800068FD
0x1800068e7  test    dil, 4
0x1800068eb  jz      short loc_1800068FD
0x1800068ed  xor     r9d, r9d; dwItem2
0x1800068f0  xor     edx, edx; uFlags
0x1800068f2  mov     ecx, 1000h; wEventId
0x1800068f7  call    cs:__imp_SHChangeNotify
0x1800068fd  mov     rsi, [rsp+28h+arg_8]
0x180006902  mov     eax, ebx
0x180006904  mov     rbx, [rsp+28h+arg_0]
0x180006909  add     rsp, 20h
0x18000690d  pop     rdi
0x18000690e  retn
```
