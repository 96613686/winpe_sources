# CNetworkItemFactory::_StartAllFDQueries(void)

- ea: `0x180005058`
- end: `0x180005149`
- name: `?_StartAllFDQueries@CNetworkItemFactory@@AEAAJXZ`
- size: `241`
- prototype: `__int64 __fastcall(CNetworkItemFactory *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004db0`

## callees

- `0x180003ca0`
- `0x180005058`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005106`
- `KERNEL32!GetLastError` at `0x180005106`
- `KERNEL32!WaitForSingleObject` at `0x180005123`
- `KERNEL32!WaitForSingleObject` at `0x180005123`
- `KERNEL32!CreateEventW` at `0x1800050bf`
- `KERNEL32!CreateEventW` at `0x1800050d5`
- `KERNEL32!CreateEventW` at `0x1800050bf`
- `KERNEL32!CreateEventW` at `0x1800050d5`
- `SHLWAPI!__imp_SHCreateThread` at `0x1800050fc`
- `SHLWAPI!__imp_SHCreateThread` at `0x1800050fc`

## pseudocode

```c
signed int __fastcall CNetworkItemFactory::_StartAllFDQueries(CNetworkItemFactory *this)
{
  __int64 v1; // rbx
  signed __int32 *v3; // rdi
  int v4; // edx
  bool v5; // zf
  signed __int32 v6; // edx
  HANDLE EventW; // rax
  signed int result; // eax
  bool v9; // sf

  v1 = *((_QWORD *)this + 16);
  v3 = (signed __int32 *)(v1 + 12);
  CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v1 + 12));
  *(_DWORD *)(v1 + 32) = 1;
  v4 = *(_DWORD *)(v1 + 16) - 1;
  v5 = (((*(_BYTE *)(v1 + 16) - 1) & 3) != 0 ? v4 : 0) == 0;
  _InterlockedExchange((volatile __int32 *)(v1 + 16), ((*(_BYTE *)(v1 + 16) - 1) & 3) != 0 ? v4 : 0);
  if ( v5 )
  {
    _m_prefetchw(v3);
    do
      v6 = *v3;
    while ( v6 != _InterlockedCompareExchange(v3, (v6 - 0x10000) & 0xFFFF0000, v6) );
  }
  *((_QWORD *)this + 13) = CreateEventW(0, 1, 0, 0);
  EventW = CreateEventW(0, 1, 0, 0);
  v5 = *((_QWORD *)this + 13) == 0;
  *((_QWORD *)this + 14) = EventW;
  if ( v5 || !EventW )
    return -2147467259;
  if ( SHCreateThread(FDBackgroundThreadHandler, this, 0x10u, 0) )
    return WaitForSingleObject(*((HANDLE *)this + 14), 0xFFFFFFFF) != 0 ? 0x80004005 : 0;
  result = GetLastError();
  v9 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v9 = result < 0;
  }
  if ( !v9 )
    return WaitForSingleObject(*((HANDLE *)this + 14), 0xFFFFFFFF) != 0 ? 0x80004005 : 0;
  return result;
}

```

## disassembly

```asm
0x180005058  mov     [rsp+arg_0], rbx
0x18000505d  mov     [rsp+arg_8], rsi
0x180005062  push    rdi
0x180005063  sub     rsp, 20h
0x180005067  mov     rbx, [rcx+80h]
0x18000506e  mov     rsi, rcx
0x180005071  lea     rdi, [rbx+0Ch]
0x180005075  mov     rcx, rdi; this
0x180005078  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000507d  mov     dword ptr [rbx+20h], 1
0x180005084  mov     edx, [rdi+4]
0x180005087  dec     edx
0x180005089  mov     eax, edx
0x18000508b  and     al, 3
0x18000508d  neg     al
0x18000508f  sbb     ecx, ecx
0x180005091  and     ecx, edx
0x180005093  xchg    ecx, [rdi+4]
0x180005096  jnz     short loc_1800050B3
0x180005098  prefetchw byte ptr [rdi]
0x18000509b  mov     edx, [rdi]
0x18000509d  mov     eax, edx
0x18000509f  lea     ecx, [rdx-10000h]
0x1800050a5  and     ecx, 0FFFF0000h
0x1800050ab  lock cmpxchg [rdi], ecx
0x1800050af  cmp     edx, eax
0x1800050b1  jnz     short loc_18000509B
0x1800050b3  xor     r9d, r9d; lpName
0x1800050b6  xor     r8d, r8d; bInitialState
0x1800050b9  xor     ecx, ecx; lpEventAttributes
0x1800050bb  lea     edx, [r9+1]; bManualReset
0x1800050bf  call    cs:__imp_CreateEventW
0x1800050c5  xor     r9d, r9d; lpName
0x1800050c8  xor     r8d, r8d; bInitialState
0x1800050cb  xor     ecx, ecx; lpEventAttributes
0x1800050cd  mov     [rsi+68h], rax
0x1800050d1  lea     edx, [r9+1]; bManualReset
0x1800050d5  call    cs:__imp_CreateEventW
0x1800050db  cmp     qword ptr [rsi+68h], 0
0x1800050e0  mov     [rsi+70h], rax
0x1800050e4  jz      short loc_180005134
0x1800050e6  test    rax, rax
0x1800050e9  jz      short loc_180005134
0x1800050eb  xor     r9d, r9d; pfnCallback
0x1800050ee  lea     rcx, ?FDBackgroundThreadHandler@@YAKPEAX@Z; pfnThreadProc
0x1800050f5  mov     rdx, rsi; pData
0x1800050f8  lea     r8d, [r9+10h]; flags
0x1800050fc  call    cs:__imp_SHCreateThread
0x180005102  test    eax, eax
0x180005104  jnz     short loc_18000511C
0x180005106  call    cs:__imp_GetLastError
0x18000510c  test    eax, eax
0x18000510e  jle     short loc_18000511A
0x180005110  movzx   eax, ax
0x180005113  or      eax, 80070000h
0x180005118  test    eax, eax
0x18000511a  js      short loc_180005139
0x18000511c  mov     rcx, [rsi+70h]; hHandle
0x180005120  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005123  call    cs:__imp_WaitForSingleObject
0x180005129  neg     eax
0x18000512b  sbb     eax, eax
0x18000512d  and     eax, 80004005h
0x180005132  jmp     short loc_180005139
0x180005134  mov     eax, 80004005h
0x180005139  mov     rbx, [rsp+28h+arg_0]
0x18000513e  mov     rsi, [rsp+28h+arg_8]
0x180005143  add     rsp, 20h
0x180005147  pop     rdi
0x180005148  retn
```
