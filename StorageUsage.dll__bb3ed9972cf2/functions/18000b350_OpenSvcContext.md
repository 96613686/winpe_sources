# OpenSvcContext

- ea: `0x18000b350`
- end: `0x18000b509`
- name: `OpenSvcContext`
- size: `441`
- prototype: `__int64()`
- caller_count: `36`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180008430`
- `0x180008680`
- `0x1800088d0`
- `0x180008b20`
- `0x180008d70`
- `0x180008fb0`
- `0x1800091f0`
- `0x180009440`
- `0x1800096e0`
- `0x180009960`
- `0x180009bf0`
- `0x180009e50`
- `0x18000a0a0`
- `0x18000a2f0`
- `0x18000a530`
- `0x18000a780`
- `0x18000a9d0`
- `0x18000ac30`
- `0x18000ae90`
- `0x18000b0e0`
- `0x18000b510`
- `0x18000b760`
- `0x18000b990`
- `0x18000bbd0`
- `0x18000be20`
- `0x18000c070`
- `0x18000c2a0`
- `0x18000c530`
- `0x18000c770`
- `0x18000c9c0`
- `0x18000cc20`
- `0x18000ce60`
- `0x18000d0a0`
- `0x18000d2f0`
- `0x18000d530`
- `0x18000d770`

## callees

- `0x1800010b0`
- `0x1800050f0`
- `0x18000b350`
- `0x1800254c0`
- `0x1800267e0`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000b3bf`
- `RPCRT4!RpcBindingFree` at `0x18000b3bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b37e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b3c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b37e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000b3c5`

## pseudocode

```c
__int64 OpenSvcContext()
{
  signed __int64 *v0; // rbp
  int v1; // ebx
  ULONGLONG TickCount64; // rdi
  __int64 v3; // r8
  ULONGLONG v4; // r8
  RPC_BINDING_HANDLE Binding[8]; // [rsp+70h] [rbp+0h] BYREF

  v0 = (signed __int64 *)((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL);
  v1 = 0;
  TickCount64 = GetTickCount64();
  if ( !g_hSvcContext )
  {
    *v0 = 0;
    v1 = StorageSvcInit((RPC_BINDING_HANDLE *)((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL));
    if ( v1 >= 0 && _InterlockedCompareExchange64(&g_hSvcContext, *v0, 0) && *v0 )
      RpcBindingFree((RPC_BINDING_HANDLE *)((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL));
  }
  GetTickCount64();
  if ( (unsigned int)dword_180040048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040048, 0x400000000000LL) )
  {
    v4 = v3 - TickCount64;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) = v4;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0x90) = ((unsigned __int64)Binding
                                                                             & 0xFFFFFFFFFFFFFFC0uLL)
                                                                            + 72;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = v4;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0xA0) = ((unsigned __int64)Binding
                                                                             & 0xFFFFFFFFFFFFFFC0uLL)
                                                                            + 80;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) = v4;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0xB0) = ((unsigned __int64)Binding
                                                                             & 0xFFFFFFFFFFFFFFC0uLL)
                                                                            + 88;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0x48) = 1;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0xC0) = ((unsigned __int64)Binding
                                                                             & 0xFFFFFFFFFFFFFFC0uLL)
                                                                            + 96;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0x98) = 8;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0xD0) = ((unsigned __int64)Binding
                                                                             & 0xFFFFFFFFFFFFFFC0uLL)
                                                                            + 64;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0xE0) = (unsigned __int64)Binding
                                                                            & 0xFFFFFFFFFFFFFFC0uLL;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0xF0) = ((unsigned __int64)Binding
                                                                             & 0xFFFFFFFFFFFFFFC0uLL)
                                                                            + 104;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0xA8) = 8;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0xB8) = 8;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0xC8) = 8;
    *(_DWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = 0;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0xD8) = 4;
    *(_DWORD *)v0 = v1;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0xE8) = 4;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0x68) = 0x1000000;
    *(_QWORD *)(((unsigned __int64)Binding & 0xFFFFFFFFFFFFFFC0uLL) + 0xF8) = 8;
    tlgWriteAgg((unsigned int)&dword_180040048, (unsigned int)&word_1800365D6, 0, 9, (__int64)(v0 + 14));
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000b350  mov     [rsp-8+arg_0], rbx
0x18000b355  mov     [rsp-8+arg_8], rdi
0x18000b35a  push    rbp
0x18000b35b  sub     rsp, 180h
0x18000b362  lea     rbp, [rsp+70h]
0x18000b367  and     rbp, 0FFFFFFFFFFFFFFC0h
0x18000b36b  mov     rax, cs:__security_cookie
0x18000b372  xor     rax, rsp
0x18000b375  mov     [rbp+110h+var_10], rax
0x18000b37c  xor     ebx, ebx
0x18000b37e  call    cs:__imp_GetTickCount64
0x18000b384  cmp     cs:g_hSvcContext, rbx
0x18000b38b  mov     rdi, rax
0x18000b38e  jnz     short loc_18000B3C5
0x18000b390  lea     rcx, [rbp+110h+Binding]; Binding
0x18000b394  mov     [rbp+110h+Binding], rbx
0x18000b398  call    StorageSvcInit
0x18000b39d  mov     ebx, eax
0x18000b39f  test    eax, eax
0x18000b3a1  js      short loc_18000B3C5
0x18000b3a3  mov     rcx, [rbp+110h+Binding]
0x18000b3a7  xor     eax, eax
0x18000b3a9  lock cmpxchg cs:g_hSvcContext, rcx
0x18000b3b2  jz      short loc_18000B3C5
0x18000b3b4  cmp     [rbp+110h+Binding], 0
0x18000b3b9  jz      short loc_18000B3C5
0x18000b3bb  lea     rcx, [rbp+110h+Binding]; Binding
0x18000b3bf  call    cs:__imp_RpcBindingFree
0x18000b3c5  call    cs:__imp_GetTickCount64
0x18000b3cb  mov     ecx, cs:dword_180040048
0x18000b3d1  mov     r8, rax
0x18000b3d4  cmp     ecx, 5
0x18000b3d7  jbe     loc_18000B4E3
0x18000b3dd  mov     rdx, 400000000000h
0x18000b3e7  lea     rcx, dword_180040048
0x18000b3ee  call    _tlgKeywordOn
0x18000b3f3  test    al, al
0x18000b3f5  jz      loc_18000B4E3
0x18000b3fb  sub     r8, rdi
0x18000b3fe  lea     rax, [rbp+110h+var_C8]
0x18000b402  mov     [rbp+110h+var_C0], r8
0x18000b406  mov     [rbp+110h+var_80], rax
0x18000b40d  lea     rdx, word_1800365D6
0x18000b414  lea     rax, [rbp+110h+var_C0]
0x18000b418  mov     [rbp+110h+var_B8], r8
0x18000b41c  mov     [rbp+110h+var_70], rax
0x18000b423  lea     rcx, dword_180040048
0x18000b42a  lea     rax, [rbp+110h+var_B8]
0x18000b42e  mov     [rbp+110h+var_B0], r8
0x18000b432  mov     [rbp+110h+var_60], rax
0x18000b439  mov     r9d, 9
0x18000b43f  lea     rax, [rbp+110h+var_B0]
0x18000b443  mov     [rbp+110h+var_C8], 1
0x18000b44b  mov     [rbp+110h+var_50], rax
0x18000b452  xor     r8d, r8d
0x18000b455  lea     rax, [rbp+110h+var_D0]
0x18000b459  mov     [rbp+110h+var_78], 8
0x18000b464  mov     [rbp+110h+var_40], rax
0x18000b46b  lea     rax, [rbp+110h+Binding]
0x18000b46f  mov     [rbp+110h+var_30], rax
0x18000b476  lea     rax, [rbp+110h+var_A8]
0x18000b47a  mov     [rbp+110h+var_20], rax
0x18000b481  lea     rax, [rbp+110h+var_A0]
0x18000b485  mov     [rsp+180h+var_160], rax
0x18000b48a  mov     [rbp+110h+var_68], 8
0x18000b495  mov     [rbp+110h+var_58], 8
0x18000b4a0  mov     [rbp+110h+var_48], 8
0x18000b4ab  mov     [rbp+110h+var_D0], 0
0x18000b4b2  mov     [rbp+110h+var_38], 4
0x18000b4bd  mov     dword ptr [rbp+110h+Binding], ebx
0x18000b4c0  mov     [rbp+110h+var_28], 4
0x18000b4cb  mov     [rbp+110h+var_A8], 1000000h
0x18000b4d3  mov     [rbp+110h+var_18], 8
0x18000b4de  call    _tlgWriteAgg
0x18000b4e3  mov     eax, ebx
0x18000b4e5  mov     rcx, [rbp+110h+var_10]
0x18000b4ec  xor     rcx, rsp; StackCookie
0x18000b4ef  call    __security_check_cookie
0x18000b4f4  lea     r11, [rsp+180h+var_s0]
0x18000b4fc  mov     rbx, [r11+10h]
0x18000b500  mov     rdi, [r11+18h]
0x18000b504  mov     rsp, r11
0x18000b507  pop     rbp
0x18000b508  retn
```
