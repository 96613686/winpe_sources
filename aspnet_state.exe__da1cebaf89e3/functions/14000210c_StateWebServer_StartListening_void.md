# StateWebServer::StartListening(void)

- ea: `0x14000210c`
- end: `0x1400021b8`
- name: `?StartListening@StateWebServer@@AEAAJXZ`
- size: `172`
- prototype: `__int64 __fastcall(StateWebServer *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140001a20`
- `0x140002678`

## callees

- `0x140001d64`
- `0x140001de4`
- `0x140001f74`
- `0x14000210c`
- `0x1400021b8`
- `0x140002318`
- `0x140004f0c`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x14000213d`
- `KERNEL32!GetSystemInfo` at `0x14000213d`

## pseudocode

```c
__int64 __fastcall StateWebServer::StartListening(StateWebServer *this)
{
  unsigned int AllowRemoteConnectionFromReg; // edi
  DWORD dwNumberOfProcessors; // esi
  unsigned int v5; // eax
  int v6; // ebp
  int v7; // esi
  _SYSTEM_INFO SystemInfo; // [rsp+20h] [rbp-38h] BYREF

  if ( *((_BYTE *)this + 72) )
    return 0;
  AllowRemoteConnectionFromReg = StateWebServer::GetAllowRemoteConnectionFromReg(this);
  if ( AllowRemoteConnectionFromReg )
    goto LABEL_12;
  GetSystemInfo(&SystemInfo);
  dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
  v5 = *((_BYTE *)this + 75) ? StateWebServer::BindToSocketV6(this) : StateWebServer::BindToSocketV4(this);
  AllowRemoteConnectionFromReg = v5;
  if ( v5 )
    goto LABEL_12;
  v6 = 3 * dwNumberOfProcessors;
  *((_BYTE *)this + 72) = 1;
  v7 = v6;
  if ( v6 > 0 )
  {
    while ( 1 )
    {
      AllowRemoteConnectionFromReg = StateWebServer::AcceptNewConnection(this);
      if ( AllowRemoteConnectionFromReg )
        break;
      if ( --v7 <= 0 )
        goto LABEL_11;
    }
LABEL_12:
    StateWebServer::StopListening(this);
    return AllowRemoteConnectionFromReg;
  }
LABEL_11:
  XspLogEvent_0(1073742900, L"%d", (unsigned int)v6);
  return AllowRemoteConnectionFromReg;
}

```

## disassembly

```asm
0x14000210c  mov     [rsp+arg_0], rbx
0x140002111  mov     [rsp+arg_8], rbp
0x140002116  mov     [rsp+arg_10], rsi
0x14000211b  push    rdi
0x14000211c  sub     rsp, 50h
0x140002120  cmp     byte ptr [rcx+48h], 0
0x140002124  mov     rbx, rcx
0x140002127  jz      short loc_14000212D
0x140002129  xor     eax, eax
0x14000212b  jmp     short loc_1400021A3
0x14000212d  call    ?GetAllowRemoteConnectionFromReg@StateWebServer@@AEAAJXZ; StateWebServer::GetAllowRemoteConnectionFromReg(void)
0x140002132  mov     edi, eax
0x140002134  test    eax, eax
0x140002136  jnz     short loc_140002199
0x140002138  lea     rcx, [rsp+58h+SystemInfo]; lpSystemInfo
0x14000213d  call    cs:__imp_GetSystemInfo
0x140002143  mov     rcx, rbx; this
0x140002146  mov     esi, [rsp+58h+SystemInfo.dwNumberOfProcessors]
0x14000214a  cmp     [rbx+4Bh], dil
0x14000214e  jz      short loc_140002157
0x140002150  call    ?BindToSocketV6@StateWebServer@@AEAAJXZ; StateWebServer::BindToSocketV6(void)
0x140002155  jmp     short loc_14000215C
0x140002157  call    ?BindToSocketV4@StateWebServer@@AEAAJXZ; StateWebServer::BindToSocketV4(void)
0x14000215c  mov     edi, eax
0x14000215e  test    eax, eax
0x140002160  jnz     short loc_140002199
0x140002162  lea     ebp, [rsi+rsi*2]
0x140002165  mov     byte ptr [rbx+48h], 1
0x140002169  mov     esi, ebp
0x14000216b  test    ebp, ebp
0x14000216d  jle     short loc_140002183
0x14000216f  mov     rcx, rbx; this
0x140002172  call    ?AcceptNewConnection@StateWebServer@@QEAAJXZ; StateWebServer::AcceptNewConnection(void)
0x140002177  mov     edi, eax
0x140002179  test    eax, eax
0x14000217b  jnz     short loc_140002199
0x14000217d  dec     esi
0x14000217f  test    esi, esi
0x140002181  jg      short loc_14000216F
0x140002183  mov     r8d, ebp
0x140002186  lea     rdx, aD; "%d"
0x14000218d  mov     ecx, 40000434h
0x140002192  call    XspLogEvent_0
0x140002197  jmp     short loc_1400021A1
0x140002199  mov     rcx, rbx; this
0x14000219c  call    ?StopListening@StateWebServer@@AEAAXXZ; StateWebServer::StopListening(void)
0x1400021a1  mov     eax, edi
0x1400021a3  mov     rbx, [rsp+58h+arg_0]
0x1400021a8  mov     rbp, [rsp+58h+arg_8]
0x1400021ad  mov     rsi, [rsp+58h+arg_10]
0x1400021b2  add     rsp, 50h
0x1400021b6  pop     rdi
0x1400021b7  retn
```
