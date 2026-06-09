# Broker::RpcClientToken::~RpcClientToken(void)

- ea: `0x180004218`
- end: `0x18000426b`
- name: `??1RpcClientToken@Broker@@QEAA@XZ`
- size: `83`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003700`
- `0x180003ac0`
- `0x180004274`
- `0x180004be0`
- `0x18000ef50`
- `0x1800118e0`
- `0x180011c20`
- `0x1800147b0`
- `0x1800149d0`
- `0x180019ec2`
- `0x18001a432`
- `0x18001accb`
- `0x18001b5b7`

## callees

- `0x180003800`
- `0x180004218`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004242`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004220`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004220`

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
0x180004218  sub     rsp, 28h
0x18000421c  mov     rcx, [rcx+8]; hObject
0x180004220  call    cs:__imp_CloseHandle
0x180004226  test    eax, eax
0x180004228  jz      short loc_18000422F
0x18000422a  add     rsp, 28h
0x18000422e  retn
0x18000422f  mov     rax, cs:WPP_GLOBAL_Control
0x180004236  test    byte ptr [rax+1Ch], 8
0x18000423a  jz      short loc_18000422A
0x18000423c  cmp     byte ptr [rax+19h], 2
0x180004240  jb      short loc_18000422A
0x180004242  call    cs:__imp_GetLastError
0x180004248  mov     rcx, cs:WPP_GLOBAL_Control
0x18000424f  lea     r8, WPP_ff69e5fc345e3f69d8452dbf82a25c63_Traceguids
0x180004256  mov     edx, 12h
0x18000425b  mov     r9d, eax
0x18000425e  mov     rcx, [rcx+10h]
0x180004262  add     rsp, 28h
0x180004266  jmp     WPP_SF_d
```
