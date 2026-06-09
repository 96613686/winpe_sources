# AuthBrokerFreeClientContext

- ea: `0x180006200`
- end: `0x1800062b3`
- name: `AuthBrokerFreeClientContext`
- size: `179`
- prototype: `HRESULT __fastcall(void *clientContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006200`
- `0x180011fd4`
- `0x180012128`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000626e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000626e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006277`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006277`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000625f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000625f`

## pseudocode

```c
__int64 __fastcall AuthBrokerFreeClientContext(_DWORD *clientContext, __int64 a2, const _GUID *a3)
{
  void *v4; // rcx
  void *v5; // rcx

  if ( clientContext )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
      && WPP_GLOBAL_Control[1].Control.Level >= 5u )
    {
      WPP_SF_qd(WPP_GLOBAL_Control[1].Control.Logger, 0x5Fu, a3, clientContext, *clientContext);
    }
    if ( _InterlockedExchangeAdd(clientContext, 0xFFFFFFFF) == 1 )
    {
      v4 = (void *)*((_QWORD *)clientContext + 2);
      if ( v4 )
        CoTaskMemFree(v4);
      v5 = (void *)*((_QWORD *)clientContext + 4);
      if ( v5 )
        CloseHandle(v5);
      LocalFree(clientContext);
    }
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control[1].Control.Logger, 0x6Bu, a3, clientContext);
  }
  return 0;
}

```

## disassembly

```asm
0x180006200  mov     [rsp+arg_0], rbx
0x180006205  push    rdi
0x180006206  sub     rsp, 30h
0x18000620a  lea     rdi, WPP_GLOBAL_Control
0x180006211  mov     rbx, clientContext
0x180006214  test    clientContext, clientContext
0x180006217  jz      short loc_18000627D
0x180006219  mov     clientContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180006220  cmp     clientContext, rdi
0x180006223  jz      short loc_180006248
0x180006225  test    byte ptr [clientContext+44h], 10h
0x180006229  jz      short loc_180006248
0x18000622b  cmp     byte ptr [clientContext+41h], 5
0x18000622f  jb      short loc_180006248
0x180006231  mov     eax, [rbx]
0x180006233  mov     edx, 5Fh ; '_'; id
0x180006238  mov     clientContext, [clientContext+38h]; Logger
0x18000623c  mov     r9, rbx; _a2
0x18000623f  mov     [rsp+38h+Logger], eax; Logger
0x180006243  call    WPP_SF_qd
0x180006248  mov     eax, 0FFFFFFFFh
0x18000624d  lock xadd [rbx], eax
0x180006251  cmp     eax, 1
0x180006254  jnz     short loc_18000627D
0x180006256  mov     clientContext, [rbx+10h]; pv
0x18000625a  test    clientContext, clientContext
0x18000625d  jz      short loc_180006265
0x18000625f  call    cs:__imp_CoTaskMemFree
0x180006265  mov     clientContext, [rbx+20h]; hObject
0x180006269  test    clientContext, clientContext
0x18000626c  jz      short loc_180006274
0x18000626e  call    cs:__imp_CloseHandle
0x180006274  mov     clientContext, rbx; hMem
0x180006277  call    cs:__imp_LocalFree
0x18000627d  mov     clientContext, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180006284  cmp     clientContext, rdi
0x180006287  jz      short loc_1800062A6
0x180006289  test    byte ptr [clientContext+44h], 10h
0x18000628d  jz      short loc_1800062A6
0x18000628f  cmp     byte ptr [clientContext+41h], 5
0x180006293  jb      short loc_1800062A6
0x180006295  mov     clientContext, [clientContext+38h]; Logger
0x180006299  mov     edx, 6Bh ; 'k'; id
0x18000629e  mov     r9, rbx; Logger
0x1800062a1  call    WPP_SF_q
0x1800062a6  mov     rbx, [rsp+38h+arg_0]
0x1800062ab  xor     eax, eax
0x1800062ad  add     rsp, 30h
0x1800062b1  pop     rdi
0x1800062b2  retn
```
