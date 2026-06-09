# Broker::RpcClientToken::~RpcClientToken(void)

- ea: `0x180003170`
- end: `0x1800031c1`
- name: `??1RpcClientToken@Broker@@QEAA@XZ`
- size: `81`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800029c0`
- `0x180010e50`
- `0x18001aee0`
- `0x18001b5d0`
- `0x18001bb90`
- `0x18001e150`
- `0x1800227a2`
- `0x180022b83`
- `0x1800235e0`
- `0x180023b00`
- `0x180023f60`
- `0x1800243a0`
- `0x180024c70`
- `0x180025828`
- `0x1800258f4`
- `0x180025d1a`

## callees

- `0x1800030e0`
- `0x180003170`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000319a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000319a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003178`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003178`

## pseudocode

```c
void __fastcall Broker::RpcClientToken::~RpcClientToken(HANDLE *this)
{
  DWORD LastError; // eax

  if ( !CloseHandle(this[1])
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids, LastError);
  }
}

```

## disassembly

```asm
0x180003170  sub     rsp, 28h
0x180003174  mov     rcx, [rcx+8]; hObject
0x180003178  call    cs:__imp_CloseHandle
0x18000317e  test    eax, eax
0x180003180  jz      short loc_180003187
0x180003182  add     rsp, 28h
0x180003186  retn
0x180003187  mov     rax, cs:WPP_GLOBAL_Control
0x18000318e  test    byte ptr [rax+1Ch], 8
0x180003192  jz      short loc_180003182
0x180003194  cmp     byte ptr [rax+19h], 2
0x180003198  jb      short loc_180003182
0x18000319a  call    cs:__imp_GetLastError
0x1800031a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031a7  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x1800031ae  mov     edx, 12h
0x1800031b3  mov     r9d, eax
0x1800031b6  mov     rcx, [rcx+10h]
0x1800031ba  call    WPP_SF_d
0x1800031bf  jmp     short loc_180003182
```
