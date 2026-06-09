# DisconnectCallback

- ea: `0x140007110`
- end: `0x1400071a5`
- name: `DisconnectCallback`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140007110`
- `0x140017658`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x14000716e`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x14000716e`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140007137`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140007137`

## string_xrefs

- `0x14000717a`: `Unable to disconnect context from COM.`

## pseudocode

```c
__int64 DisconnectCallback()
{
  unsigned int i; // ebx
  __int64 v1; // rdi
  DWORD v2; // ecx
  __int64 v3; // rcx
  HRESULT v4; // eax
  unsigned int v5; // ebx

  for ( i = 0; i < 4; ++i )
  {
    v1 = 32LL * (int)i;
    v2 = *(_DWORD *)((char *)&vrgComInfo + v1 + 24);
    if ( v2 )
    {
      CoRevokeClassObject(v2);
      *(_DWORD *)((char *)&vrgComInfo + v1 + 24) = 0;
    }
    v3 = *(__int64 *)((char *)&vrgComInfo + v1 + 16);
    if ( v3 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      *(struct COM_INFORMATION near **)((char *)&vrgComInfo + v1 + 16) = 0;
    }
  }
  v4 = CoDisconnectContext(0xFFFFFFFF);
  v5 = v4;
  if ( v4 < 0 )
    CBSWdsLogLight(0x4000000u, (unsigned int)v4, (size_t *)1, "Unable to disconnect context from COM.");
  return v5;
}

```

## disassembly

```asm
0x140007110  mov     [rsp+arg_0], rbx
0x140007115  mov     [rsp+arg_8], rsi
0x14000711a  push    rdi
0x14000711b  sub     rsp, 20h
0x14000711f  xor     ebx, ebx
0x140007121  lea     rsi, ?vrgComInfo@@3PAUCOM_INFORMATION@@A; COM_INFORMATION near * vrgComInfo
0x140007128  movsxd  rdi, ebx
0x14000712b  shl     rdi, 5
0x14000712f  mov     ecx, [rdi+rsi+18h]; dwRegister
0x140007133  test    ecx, ecx
0x140007135  jz      short loc_140007145
0x140007137  call    cs:__imp_CoRevokeClassObject
0x14000713d  mov     dword ptr [rdi+rsi+18h], 0
0x140007145  mov     rcx, [rdi+rsi+10h]
0x14000714a  test    rcx, rcx
0x14000714d  jz      short loc_140007164
0x14000714f  mov     rax, [rcx]
0x140007152  mov     rax, [rax+10h]
0x140007156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000715b  mov     qword ptr [rdi+rsi+10h], 0
0x140007164  inc     ebx
0x140007166  cmp     ebx, 4
0x140007169  jb      short loc_140007128
0x14000716b  or      ecx, 0FFFFFFFFh; dwTimeout
0x14000716e  call    cs:__imp_CoDisconnectContext
0x140007174  mov     ebx, eax
0x140007176  test    eax, eax
0x140007178  jns     short loc_140007193
0x14000717a  lea     r9, aUnableToDiscon_0; "Unable to disconnect context from COM."
0x140007181  mov     r8d, 1
0x140007187  mov     edx, eax
0x140007189  mov     ecx, 4000000h
0x14000718e  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140007193  mov     rsi, [rsp+28h+arg_8]
0x140007198  mov     eax, ebx
0x14000719a  mov     rbx, [rsp+28h+arg_0]
0x14000719f  add     rsp, 20h
0x1400071a3  pop     rdi
0x1400071a4  retn
```
